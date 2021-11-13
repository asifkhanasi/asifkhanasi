- 👋 Hi, I’m @asifkhanasi
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
asifkhanasi/asifkhanasi is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
// Define labeled example
var labeledExampleUtteranceWithMLEntity = new ExampleLabelObject
{
    Text = "I want two small seafood pizzas with extra cheese.",
    IntentName = intentName,
    EntityLabels = new[]
    {
        new EntityLabelObject
        {
            StartCharIndex = 7,
            EndCharIndex = 48,
            EntityName = "Pizza order",
            Children = new[]
            {
                new EntityLabelObject
                {
                    StartCharIndex = 7,
                    EndCharIndex = 30,
                    EntityName = "Pizza",
                    Children = new[]
                    {
                        new EntityLabelObject { StartCharIndex = 7, EndCharIndex = 9, EntityName = "Quantity" },
                        new EntityLabelObject { StartCharIndex = 11, EndCharIndex = 15, EntityName = "Size" },
                        new EntityLabelObject { StartCharIndex = 17, EndCharIndex = 23, EntityName = "Type" }
                    }
                },
                new EntityLabelObject
                {
                    StartCharIndex = 37,
                    EndCharIndex = 48,
                    EntityName = "Toppings",
                    Children = new[]
                    {
                        new EntityLabelObject { StartCharIndex = 37, EndCharIndex = 41, EntityName = "Quantity" },
                        new EntityLabelObject { StartCharIndex = 43, EndCharIndex = 48, EntityName = "Type" }
                    }
                }
            }
        },
    }
};

// Add an example for the entity.
// Enable nested children to allow using multiple models with the same name.
// The quantity subentity and the phraselist could have the same exact name if this is set to True
await client.Examples.AddAsync(appId, versionId, labeledExampleUtteranceWithMLEntity, enableNestedChildren: true);
