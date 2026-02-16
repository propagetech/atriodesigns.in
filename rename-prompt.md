You are a naming assistant. Given a list of file paths and minimal context from a static website, suggest a new filename (basename only, same extension) for each file. Rules:
- Lowercase, kebab-case, no spaces. SEO-friendly and human-readable.
- For HTML: use page purpose (e.g. about-us.html, contact.html). Keep index.html as index.html.
- For CSS/JS: use purpose (e.g. main-styles.css, analytics.js).
- For images: use content (e.g. logo-infygate.webp, hero-banner.webp). Use alt/title when provided.
- Return a JSON object: keys = exact original path strings, values = new basename only (e.g. "main.css"). Preserve extension.
- Do not change path prefix (e.g. css/ stays css/ by returning "name.css" not "css/name.css").

Files and context:
[
  {
    "path": "3floorshousedesign.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Independent House G+3"
    }
  },
  {
    "path": "404.html",
    "context": {
      "title": "",
      "first_heading": "404"
    }
  },
  {
    "path": "about-us.html",
    "context": {
      "title": "Atrio Design Studio | About Us",
      "first_heading": "ABOUT US"
    }
  },
  {
    "path": "actual-completed-work.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Residential Interior - Onsite Clicks"
    }
  },
  {
    "path": "ahad-euphoria-gaurav-taruna.html",
    "context": {
      "title": "Atrio Design Studio | Ahad Euphoria \u2013 Gaurav & Taruna",
      "first_heading": "Ahad Euphoria - 2BHK Apartment"
    }
  },
  {
    "path": "architectural.html",
    "context": {
      "title": "Atrio Design Studio | Architectural",
      "first_heading": "Four Storey Villa"
    }
  },
  {
    "path": "assetz-marq-2-bhk-apartment.html",
    "context": {
      "title": "Atrio Design Studio | Assetz Marq 2 BHK Apartment",
      "first_heading": "Assetz Marq - 2 BHK Apartment"
    }
  },
  {
    "path": "assetz-marq-3-bhk-apartment.html",
    "context": {
      "title": "Atrio Design Studio | Assetz Marq 3 BHK Apartment",
      "first_heading": "Assetz Marq - 3 BHK Apartment"
    }
  },
  {
    "path": "bedroom-designs.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Bedroom Designs"
    }
  },
  {
    "path": "blog.html",
    "context": {
      "title": "Atrio Design Studio | Blogs",
      "first_heading": "BLOGS"
    }
  },
  {
    "path": "blog_designing-a-future-ready-house.html",
    "context": {
      "title": "Designing a Future Ready House",
      "first_heading": "Designing a Future Ready House"
    }
  },
  {
    "path": "blog_principles-of-interior-design.html",
    "context": {
      "title": "Principles of Interior Design",
      "first_heading": "Principles of Interior Design"
    }
  },
  {
    "path": "blog_wellness-focused-interior-design.html",
    "context": {
      "title": "Wellness Focused Interior Design",
      "first_heading": "Wellness Focused Interior Design"
    }
  },
  {
    "path": "blog_why-a-designer-.html",
    "context": {
      "title": "Why a Designer?",
      "first_heading": "Why a Designer?"
    }
  },
  {
    "path": "cafe-the-hidden-garden.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "The Hidden Garden - Cafe House"
    }
  },
  {
    "path": "commercial-office-spaces.html",
    "context": {
      "title": "Atrio Design Studio | Commercial Office Spaces",
      "first_heading": "Corporate Office Space"
    }
  },
  {
    "path": "commercial-retstaurant.html",
    "context": {
      "title": "Atrio Design Studio | Commercial Restaurant",
      "first_heading": "D'Marina Resto Bar"
    }
  },
  {
    "path": "contact-us.html",
    "context": {
      "title": "Atrio Design Studio | Contact Us",
      "first_heading": "CONTACT US"
    }
  },
  {
    "path": "css/138575cd4810b87ba229d0ae35cbc7b8.css",
    "context": {
      "path": "css/138575cd4810b87ba229d0ae35cbc7b8.css"
    }
  },
  {
    "path": "css/4846897a8ea4821d99984bafb364df80.css",
    "context": {
      "path": "css/4846897a8ea4821d99984bafb364df80.css"
    }
  },
  {
    "path": "css/4957171073492227171d872757d04770.css",
    "context": {
      "path": "css/4957171073492227171d872757d04770.css"
    }
  },
  {
    "path": "css/559e64bf161e61fa0aca6e864c78191d.css",
    "context": {
      "path": "css/559e64bf161e61fa0aca6e864c78191d.css"
    }
  },
  {
    "path": "css/84d4a0216f16f715d9b301db3a8da352.css",
    "context": {
      "path": "css/84d4a0216f16f715d9b301db3a8da352.css"
    }
  },
  {
    "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css",
    "context": {
      "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css"
    }
  },
  {
    "path": "css/a47c50adb0720737ea9623c7c0d89616.css",
    "context": {
      "path": "css/a47c50adb0720737ea9623c7c0d89616.css"
    }
  },
  {
    "path": "css/internal-styles.css",
    "context": {
      "path": "css/internal-styles.css"
    }
  },
  {
    "path": "design-options.html",
    "context": {
      "title": "Atrio Design Studio | Design Themes",
      "first_heading": "DESIGN OPTIONS"
    }
  },
  {
    "path": "dlf-westend-heights-mr-prakash-3-5-bhk.html",
    "context": {
      "title": "Atrio Design Studio | DLF Westend Heights - Mr Prakash 3.5 BHK",
      "first_heading": "DLF Westend Heights -\u00a0 3.5 BHK\u00a0Apartment"
    }
  },
  {
    "path": "dlf-woodland-heights-niraj-neha.html",
    "context": {
      "title": "Atrio Design Studio | DLF Woodland Heights \u2013 Niraj & Neha",
      "first_heading": "DLF Woodland Heights \u2013 3 BHK\u00a0Apartment"
    }
  },
  {
    "path": "duplex-villa-nksingh.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Duplex Villa"
    }
  },
  {
    "path": "einstein-mont-pre-school.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Einstein Mont Pre School"
    }
  },
  {
    "path": "faqs.html",
    "context": {
      "title": "Atrio Design Studio | FAQs",
      "first_heading": "FAQS"
    }
  },
  {
    "path": "farm-house-coorg.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Farm House and Landscape Design"
    }
  },
  {
    "path": "imgs/015ebe082d7327db7faca40f290b9c1c.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja Unit - Veneer Finish & Laser cut Doors",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/016cf535cc069f8f7f9e40cb4cc303f1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/017b8086a57e0f257a2141a5f572997c.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Slider Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/02048d352b21fcd313832ebdcf70e354.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/022b74e17f28eccac5a5682956e6423e.webp",
    "context": {
      "refs": [
        {
          "alt": "Farm House Evening View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/02afdc5d857a7f5f0aa6c8cfed207bb0.webp",
    "context": {
      "refs": [
        {
          "alt": "Layout Plan - First Floor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/038603126036af5536a82291e2954ad8.webp",
    "context": {
      "refs": [
        {
          "alt": "JD Palace Designer Pillar Element",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/038638fd8a0daf938ec41f79bbaa951d.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja and Dining Room View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/03c26d9bb9c46b93b4474bdcb152d151.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom with Green and Grey paint on the wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0553a587cd67c24751eb39e899bd224e.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Club House Complex - Architecture Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/062a8e02c1b234a9904424980e84b7de.webp",
    "context": {
      "refs": [
        {
          "alt": "Home Interior Design Options",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/07cf1ed9cc6e4018726d80c9c4208772.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Terrace Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/07e9f144a884be19c4fae63b3ad904ee.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/07f25f7ab92508b4e52f236396a08b51.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Area with Laser cut False ceiling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/07f285f35181d6551b541c281178df5b.webp",
    "context": {
      "refs": [
        {
          "alt": "Work out area view",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/080efc8e314a077074635180679496f6.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/08361034f1158ce2d854f2f7b4813e57.webp",
    "context": {
      "refs": [
        {
          "alt": "JD Palace Garden and Pool Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/090eab8ed6c7c02b4a957f9eb0529938.webp",
    "context": {
      "refs": [
        {
          "alt": "Cycling section",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/096b81f8cfe143f08d8c1b148e771c31.webp",
    "context": {
      "refs": [
        {
          "alt": "Class Room 1 View 4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0a52d1bfbdfafddec647f487a013609d.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe and Dressing Unit View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0a72041bd18f34ad2ac6c1103b35a708.webp",
    "context": {
      "refs": [
        {
          "alt": "Design Stage",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0b24bcf392b8c54e8eacb98cccb38d62.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Breakfast Conter 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0b3fb5f238731569d70bd3660cc288aa.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom Wardrobe View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0b481a7418a93a94326d7697342bfe30.webp",
    "context": {
      "refs": [
        {
          "alt": "False Ceiling Moulding Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0cf7d5e87a6cf6bee6bb42ee162ca8a0.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Shoe Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0d80fb548d871972951c88a4f0660dc7.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Bird Eye View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0e984a998562107584f3d03f7caa3ce7.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom Wardrobe Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0f0b55c78aa0062b77e7e87930238082.webp",
    "context": {
      "refs": [
        {
          "alt": "False Ceiling with Wooden Battens",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0f52212fe76769d4c11e18e02d2d3a6e.webp",
    "context": {
      "refs": [
        {
          "alt": "Open plan office space",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/106da0a080d94320c8458e2310af979f.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen -L shaped",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/113727e5f00a75c2189246375ee9ff9b.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Club House Complex - Architecture Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/11fcd0091e912ba2000ed284cb274bd6.webp",
    "context": {
      "refs": [
        {
          "alt": "Family TV Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/12335aabe78ee36882919c99c4a77c35.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/129b68694af379faf0088340f0397eea.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR Study",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/12e6256a8842f2d579b76646a28b6aa8.webp",
    "context": {
      "refs": [
        {
          "alt": "False Ceiling Moulding Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/13372883503a7dc108302d20f8f09bc6.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Family Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/134c613c1cb984c802d8975fc0cee14c.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bed Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1386bf61f1db491df2513ebc2f8d534c.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Elevation",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/13891589119e8d5ab79cd1630047bbf9.webp",
    "context": {
      "refs": [
        {
          "alt": "TV Unit and Crockery Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1423be88998ba855a20b2a666cfdb14e.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Front Elevation Bird Eye View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/142529e527db497cc7fa6209c2decf7e.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Room View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/145c870c1bc8723e6840101cb45f51b9.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Area Mirror Feature wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/146e5dd5a4a957f8f4ab796a08ac2f71.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/14991b466b0742f41171fa43c90d8189.webp",
    "context": {
      "refs": [
        {
          "alt": "Why a Designer",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/155b398620224759de3de74eb8686dd4.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR Study",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/15c3e338f7795f9d750e5c1de7c30e69.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR Wardrobe - Aristo Slider Door System",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/16e509158146fcc37f4989f93848179d.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1765781187ce97f231457b72eac4bf73.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/178cc5b3b27412e9f397f909f6e60d6f.webp",
    "context": {
      "refs": [
        {
          "alt": "Floating Mandap",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/179dc083898b801fdd9bc71e48ee1f24.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Unit and Cupboard with Smart Lighting",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/17a6c610647a949c45018b815d6a48d1.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1834f832e30d53774da3037dac4f1d64.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR Headboard and Mirror Paneling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/18e566564d8defee9e9125a9d771234f.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room Colourful Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/191bbe945a434ad816a320271961a0cb.webp",
    "context": {
      "refs": [
        {
          "alt": "Layout Plan - First Floor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1942449b241eb844693d45616fa46972.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe Internal",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1948741c3798e6e956cf72803d316eea.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Terrace Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/19850eaaaff0b752b6f1b425b4266883.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/19f9640dfc6ca0ae5873e66ed2e5bd7f.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom Wardrobe, Study Unit and Bed",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1a46947e395a4eba1cfe938b28f1e672.webp",
    "context": {
      "refs": [
        {
          "alt": "Entrance Foyer Unit with Wallpaper and Green Coloured Wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1aa20c242212ae0e976c7c7ef0791794.webp",
    "context": {
      "refs": [
        {
          "alt": "TV",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1c1baa6dd1ed55b9ad503772d6edd8b2.webp",
    "context": {
      "refs": [
        {
          "alt": "Kingsize Bed with Headboard and Wall Painting",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1c9d85863093687741c3da37bb68daad.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1ce0a63e14bd4e60cb9a91281553d65b.webp",
    "context": {
      "refs": [
        {
          "alt": "Colourful Kids Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1d1f6a668f058ade6f20ff6fad6f53e7.webp",
    "context": {
      "refs": [
        {
          "alt": "Wooden Texture Laminate finish Foyer Area and Gate paneling with 3D wallpaper",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1d8b684717ec08d73ffad01f94f0f077.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1e75df319a6a3c5547bf13cc20cafe98.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1e779425bb50f5430afe36c7a11a4fef.webp",
    "context": {
      "refs": [
        {
          "alt": "3D Layout Floor Plan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1e8f7c4abaae8ff579e7345f9048f644.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Commercial Complex - Architecture Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1e9377cdd2751705b44f4884d8a2d373.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen with Breakfast Nook",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1ed60a4010be6edcf43d5d03d13341ea.webp",
    "context": {
      "refs": [
        {
          "alt": "GBR Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1f42eea6f24a813750d77f6a21273895.webp",
    "context": {
      "refs": [
        {
          "alt": "Utility Side 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1fe284ec73cbc1b92bb8e514aea08d6e.webp",
    "context": {
      "refs": [
        {
          "alt": "Independent House G+3 - Architecture Design",
          "title": ""
        },
        {
          "alt": "Elevation Side View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1fef507cbdd54badc8c525fc06d7bb39.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2074c2faa5ac45d63ed90739cb144972.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/211682bf0fcbfb0e01e9ab6ab372caf5.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2133a10b1de5a05a88386bc90788dbcf.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Room View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/219013a66ef4a41454e3f79e06699559.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Breakfast unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/21993d0b3925a8b868a7e4726b081a16.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/21a3635dc42dd817d8157b55d4d58399.webp",
    "context": {
      "refs": [
        {
          "alt": "Laundry Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/21de01f79492bb7d83024c4fb1ec54c8.webp",
    "context": {
      "refs": [
        {
          "alt": "Family TV Room View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/222fe770b1482dfcece2dad07559efd4.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Commercial Complex - Architecture Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/22a0250483ceb261204b98cf8de6d19d.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Built-In Bed and False ceiling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/23237fe35d2ff28439c5f1e0adbe5967.webp",
    "context": {
      "refs": [
        {
          "alt": "TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/23ac3ce87cb70f00770f0305f9303e93.webp",
    "context": {
      "refs": [
        {
          "alt": "Partition unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/25801f645735ac11075ff58c8621081d.webp",
    "context": {
      "refs": [
        {
          "alt": "Family Room TV Unit with Acrylic Finish with backlight",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/26ec9530cf2396f1c388d5fe3df3f46d.webp",
    "context": {
      "refs": [
        {
          "alt": "Execution Stage",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/27ac6a8bfba3824d8ab951302824263a.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV Unit and False Ceiling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/27e78f35e89ada25006fe00e33a31310.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Elevation V1",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/28ef10e5092dd6dfd8a8a37f3b8901b5.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom Bed",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/294797d73c433535354d198bfbbf85d8.webp",
    "context": {
      "refs": [
        {
          "alt": "Farm House Side View with Landscape",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/294ff20a8e5ded4f8d09bb6b0ed0f720.webp",
    "context": {
      "refs": [
        {
          "alt": "Island Kitchen with Gate Paneling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2953ff2473cee28162eeaaef8876cce2.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room Acrylic Finish TV Unit with Textured Wall Paint",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/298ef1df47a148abb438802d9b85695d.webp",
    "context": {
      "refs": [
        {
          "alt": "Elevation View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/29f5ae3dfb780f607a3102e130196b4f.webp",
    "context": {
      "refs": [
        {
          "alt": "Commercial Interiors",
          "title": ""
        },
        {
          "alt": "Commercial\u00a0Interiors",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2b75fe239198711ad00d9474e26c56ec.webp",
    "context": {
      "refs": [
        {
          "alt": "Shoe Rack",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2b96ff046c9034b76d34db86852567c8.webp",
    "context": {
      "refs": [
        {
          "alt": "Laminate finished Foyer area with wall paint",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2bc86962c740ba332e68227af5663d7c.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe Op1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2bcc0af6b2c2aa3a750a80d4f95651b5.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2c12507b9768bf6fb8f36e0928a0ae2d.webp",
    "context": {
      "refs": [
        {
          "alt": "Modular Kitchen View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2c6199a8d2e29cf9f3d902ee75661c9e.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Dressing Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2d550208fda518e2aaa46606733ad448.webp",
    "context": {
      "refs": [
        {
          "alt": "Shoe Rack",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2d5d072d0b934b71e1b774bcb3972280.webp",
    "context": {
      "refs": [
        {
          "alt": "Timeless Sophistication: Luxury Home Interiors | Klassik Landmark, Bangalore | Atrio Design Studio",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2d8fc939fd0540dd1c5233f08d8a0529.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Front Elevation Day View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2dde21d497b35a0bbbeeca6b68d9a30a.webp",
    "context": {
      "refs": [
        {
          "alt": "Activity Area View 3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2e0ff1181c4db56c5db8eddc9ef09526.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja Room with Veneer Finish & Mirror Paneling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2e56e0c1264d99d761be53e19a149a56.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2e93527d8d90c7057c836170f50bf081.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2f6153dbcce68e56bd527514720691be.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2fc2f931bbced95308fbe85a300cd8e7.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/300dfff5837ec79838e63d21285d4cf2.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen with Tall Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/304206eca1c0b1a9648f9c5e6648c805.webp",
    "context": {
      "refs": [
        {
          "alt": "Living and Dining Area View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/305b90b6a46a0b59213aa2eeb5132161.webp",
    "context": {
      "refs": [
        {
          "alt": "Farm House Day View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/311e066c00d3b9239cfae9b20f7b07f6.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Dining Partition Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/31f78885726399129f9b99ad2fb6fd3b.webp",
    "context": {
      "refs": [
        {
          "alt": "Dressing Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/32fb633265179203114f0b85fe4d761c.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/33be800a644861a379c551858f599bb2.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Elevation Vertical Gardening",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/342663e020d51542e8ed4049ae1a9a57.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/343394974ddd2d19f4bed033b4cf625d.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Integrated Bed Option",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/34b503084a93fa8bf3af947cc58847cf.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/34d9ab4d04ab7aebd1ed95b94f547597.webp",
    "context": {
      "refs": [
        {
          "alt": "Open plan office space",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/34e3368059b9625eba932775ada37a8d.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Room - Wardrobe and Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/34f006c48644f3b5d487f5bc861bdfed.webp",
    "context": {
      "refs": [
        {
          "alt": "Complete View of Work out area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/35238bb40471a2f8b797591cf544376d.webp",
    "context": {
      "refs": [
        {
          "alt": "JD Palace",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/354a2351fd5b598e0f0aadb705d679d2.webp",
    "context": {
      "refs": [
        {
          "alt": "TV Unit and Crockery Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3669e5530a150dac7f3ef80e44f00c02.webp",
    "context": {
      "refs": [
        {
          "alt": "Wardrobe Dresser with Smart Lighting system",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/36a59ed1272723039ae7d4c48a4de16d.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room False ceiling with lighting",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/36a6d4ce30655a96d911d9b298a25ab4.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe with Red Coloured wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/38dc7b85abc2593cb0369908317c32c2.webp",
    "context": {
      "refs": [
        {
          "alt": "Terrace 3D Plan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/39165037f59870053bea28e3e7bda5c7.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Dining Partition Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/39cafd59e188cd91d26deea271132a52.webp",
    "context": {
      "refs": [
        {
          "alt": "Living room with designer wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3ad93cb55cb5597aa2acfe0b02e18348.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3b52d9f1759c5bbd2bf1aedce406eedc.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3c397bcfeb280c24ed0d343708ae035e.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3d6d002e112037a3df52331413913f73.webp",
    "context": {
      "refs": [
        {
          "alt": "Principles of Interior Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3d93a07b60c44a8eccbec8c6b65fa6bc.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen with False ceiling and Lighting",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3e86197c119448f3f6ce6bfbcf500d4e.webp",
    "context": {
      "refs": [
        {
          "alt": "Nambiar Bellezea Villa G+2 Interiors",
          "title": ""
        },
        {
          "alt": "MBR Headboard and Mirror Paneling",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3f1516bfc4839b5a16cf94946e836f0c.webp",
    "context": {
      "refs": [
        {
          "alt": "Terrace Floor Plan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3f240ae7154faa8c5964f864cca298b1.webp",
    "context": {
      "refs": [
        {
          "alt": "Electrical Plan Ground Floor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3f4d6a81d1658b8a79cf52b7807b93b4.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3fa749bf70485f46a54365537fbf9351.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen View 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/417aa9b86aec0359f55ea62ea3dcd62c.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/41c97eb663540b77c9008c53dca5a789.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/41e4feef41902edab2a83c724d51107d.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Room View 3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/41ea1dd4d0a31e06ac58eeb50fcfe682.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room with Trundle Bed",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4263f8465f49832ec0ad81b1a7551fc6.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom Wardrobe and Study",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/42a951a5608acf05627dda5fa699f5a2.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/43697fcf3a3841fa3e032703d5946a18.webp",
    "context": {
      "refs": [
        {
          "alt": "Living and Dining Area with wall painting",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/437fb9c9d4f7e8f38c7a73c97d3dbb8a.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/43d2c2358a488df741727b6a4274073b.webp",
    "context": {
      "refs": [
        {
          "alt": "Foyer Area Seating and Partition Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4462535100d5f3b77109d47e39c4aabe.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room with Wallpaper on the wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4592fdbcf343ef39aee3e516a5ca6650.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Club House Complex - Architecture Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4846e8e804456e4e2296fe0f5a4a6c09.webp",
    "context": {
      "refs": [
        {
          "alt": "JD Palace Garden Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/498baa1be7b2eba7b84580f08b5935dc.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV Unit with Acrylic and Texture Laminate Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4a02f7fb789bd013358b25f893af6546.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4a271a9e1946ac71f676c3c16ebd48db.webp",
    "context": {
      "refs": [
        {
          "alt": "Elevation Evening View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4a33ba66546d0798c17ffcb6ec26bde9.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Bird Eye View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4aa363796873414a936830b8f6c6744e.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja Unit and Partition Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4aac1326336cc371fb4b308cade8e4e5.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Area TV and Partition Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4b3196a6a79b8dd0631d5baa1ca56f8c.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Area TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4b4eaffc2bb232690bdbeeab15b23d5a.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4b7a695e258c2a3ad5b53db277561e4d.webp",
    "context": {
      "refs": [
        {
          "alt": "Floor Plan - Second Floor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4bcb40f82eb22f2acded2a0b16da77f2.webp",
    "context": {
      "refs": [
        {
          "alt": "Gym Cardio and Cycling Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4c84d4e8ca5131af5c6ff0f0f3cbdc32.webp",
    "context": {
      "refs": [
        {
          "alt": "Laser Cut Pooja Doors with Designer Mirror Paneling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4c9d09f32c5b18b8fccd78cb15d367b4.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR 1 Dressing Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4cb3be05c8e597e9a0ca90f8e3b4625d.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Area with Crockery Unit and Photo Feature Wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4d186648946fe9f3a89dbfecf1d6d690.webp",
    "context": {
      "refs": [
        {
          "alt": "\u200bWedding convention pool area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4d58caeb88cf8ffa3d3411881a85877f.webp",
    "context": {
      "refs": [
        {
          "alt": "Huddle and Discussion Rooms",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4d876dd561cfc5f72d492b89668d97c1.webp",
    "context": {
      "refs": [
        {
          "alt": "Office Reception Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4de7a8b3e8d4b68487192c049cbc4b59.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4dfee16a0d69ef0dd99800e74004efef.webp",
    "context": {
      "refs": [
        {
          "alt": "Parallel Kitchen side 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4e2ef0f7ad06752649520707526e7ef3.webp",
    "context": {
      "refs": [
        {
          "alt": "Layout Plan - Ground Floor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4e995efcbb20886e95cbad6404fd3abb.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja Unit with Partition",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4f4e46c3413292ba543b6527ed0dc9d3.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4f6742e3749c4bb6e1533b748d4bd1a0.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Area Crockery Unit and False Ceiling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4fc2d20a1ee613ccf1b316914c1a96ea.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen and Tall Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5147276265a30bfc99060f72a8970ab3.webp",
    "context": {
      "refs": [
        {
          "alt": "Teakwood Finish Bed Headboard and Mirror Paneling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5164e3be16aafbac87314b6e139ba141.webp",
    "context": {
      "refs": [
        {
          "alt": "Media Room View 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/517959d40e5b827ff85aff3fb152c8bd.webp",
    "context": {
      "refs": [
        {
          "alt": "Conference Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/51a745770e5700e6473ddecb55ce2ebf.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Elevation",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/51b5ddf593f05b54ed56da57deeb5669.webp",
    "context": {
      "refs": [
        {
          "alt": "Wardrobe with Openable Shutter Doors and Dressing Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/52962301988f572f246205df8ae2b592.webp",
    "context": {
      "refs": [
        {
          "alt": "Layout Plan - Ground Floor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/536137e0c01e5edb1924267d581ca8ea.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/53a3e5f251b397cab82b695029a09b23.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Lighting",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/54913e1351ff762163e4dfc1d18a68df.webp",
    "context": {
      "refs": [
        {
          "alt": "Wardrobe with Openable Doors",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/55377f2fc83236e9f14ebfd16492ec28.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5568a7d8c6cab917c221f4d53b4baa80.webp",
    "context": {
      "refs": [
        {
          "alt": "Gate Paneling and Kitchen",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/556c9d2793bc35e69213bd68cbe0b9bd.webp",
    "context": {
      "refs": [
        {
          "alt": "Visitor Waiting Lounge",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/558660c8d34d45e00664a35b25b393f7.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room and Wooden False Ceiling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5654c07b5a9d1b51538e38d1a33b74d3.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom Bed with Headboard",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5757a1489ed3f430bb62310f26e3c61e.webp",
    "context": {
      "refs": [
        {
          "alt": "TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/576f66ebc6738cb9012ae94cc869e57b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/579ca7899c08c1b651d79fe15e7229f3.webp",
    "context": {
      "refs": [
        {
          "alt": "Media Room View 3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/59c3eb8953c363f37ea7c4be1e63329f.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom complete view",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5a209973decaf68f5989099ceda627d3.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Dressing",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5ae9e813bce3c7d1008ac089f89a3853.webp",
    "context": {
      "refs": [
        {
          "alt": "Treadmill and Cycling - cardio workouts section",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5d1defb0c3cc550a507a7b420963f758.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Built-In Bed and False ceiling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5d239611884e4d2eb22b2d49018a93a1.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom - Slider Wardrobe with Acrylic Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5d3b5a8eecadb87dc1f75baec773f164.webp",
    "context": {
      "refs": [
        {
          "alt": "3D Elevation View 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5e67013bc87092a61782dfb82e7da08e.webp",
    "context": {
      "refs": [
        {
          "alt": "Living and Dining Area with False ceiling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5eaae0b8abe86d5db85f2edf4ddbd5a6.webp",
    "context": {
      "refs": [
        {
          "alt": "Weight Training section",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5ed57e850cbf07e9ac06b41faadb34e6.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV Unit",
          "title": ""
        },
        {
          "alt": "Prestige Kew Gardens - 2.5BHK Interiors",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5f37a0cd7f79b6a580fea648962a5227.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Front Elevation Night View",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5f416c6ebfeb7c27b87c87ea671b1ff6.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room Wardrobe with Study",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5ff5248322058417f812029edaf8acd5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/62600450bd98649ac893fe482d388e60.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Elevation Front View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/637cf6863b89a883268790ed314ac2f5.webp",
    "context": {
      "refs": [
        {
          "alt": "Foyer Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/63cbff4e86e141554c5665d4ba577087.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Area TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6410beec2103976b3b870ffd3bd0b0cf.webp",
    "context": {
      "refs": [
        {
          "alt": "3D Elevation View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/64967c78fa7f0b4328053a517e2b0f14.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/65d9a3774752968888cb3c7600012790.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Family Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6680d8e924718078bd125360d6a7b16a.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Terrace Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/66b1b756cac40aa7f795225922b00000.webp",
    "context": {
      "refs": [
        {
          "alt": "2 Doors Sliding Wardrobe and Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/66ef5bd349493bbd385f3b7e7ba76312.webp",
    "context": {
      "refs": [
        {
          "alt": "Residential Interiors",
          "title": ""
        },
        {
          "alt": "Residential Interiors",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/66f80b913ebbcecc1d0dc61d4d85a6a7.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen with Membrane Doors",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/672646b69626fd4ab52e049f8d33a820.webp",
    "context": {
      "refs": [
        {
          "alt": "3D Elevation View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/69193dfacdcaa4984c8469da6227dc4c.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/69fbf10199cd4a98805cc44b873124b5.webp",
    "context": {
      "refs": [
        {
          "alt": "Play School Furniture Layout Plan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6a640024f45684d86f536a1cccd84cc1.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6b36860a42f9d716e54fee23839e6952.webp",
    "context": {
      "refs": [
        {
          "alt": "Master BedRoom False ceiling Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6bd6cbaabdbde69d189f4c014f2df452.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6bdf3d3de9faef6a9e6490978403f7fe.webp",
    "context": {
      "refs": [
        {
          "alt": "Home Interior Design Options",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6be60e4a238d18223ceaa26b00309b34.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Family Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6cac439f74525b4cfb93ed848eaaa071.webp",
    "context": {
      "refs": [
        {
          "alt": "Wavefit - Gym and Fitness Studio - Interior Design",
          "title": ""
        },
        {
          "alt": "Reception Area",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6cbaa80d7c58c5fc0d7e9150da024373.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen with Metallic Finish with Rolling Shutter",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6cd855b11a4298a5030063fcc33d2447.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Room View 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6d3a010b9e33ec6764a057a3ef6127dc.webp",
    "context": {
      "refs": [
        {
          "alt": "Principles of Interior Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6e159c6be71ee72c39784c6b51c1c21b.webp",
    "context": {
      "refs": [
        {
          "alt": "Family TV Room False ceiling Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6e52d1b4d095e06e1c512104d0af4906.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6e6748b2031bd53cd24c7a945db4eb69.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Base Cabinets with Acrylic Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/712373bae5f01d2241ae557ea65981ec.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen side 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/717cdc49ed867766e116b2b42bda707b.webp",
    "context": {
      "refs": [
        {
          "alt": "Climbing Workout Section",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/720a5432cd6208fc09e8683f3129ec75.webp",
    "context": {
      "refs": [
        {
          "alt": "Terrace Cafe Bird View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/72ee0f1163991cdc208c2756e65c0369.webp",
    "context": {
      "refs": [
        {
          "alt": "JD Palace Bird Eye View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/73528b4262cdce184a871e2911035263.webp",
    "context": {
      "refs": [
        {
          "alt": "Living and Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7362fcc52d750ac032909db99ac8a15f.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/73918b6fcbeeeadde7c0cd734bf35c61.webp",
    "context": {
      "refs": [
        {
          "alt": "Modular Kitchen View 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7477179a49c25674c4b724d77b9ee02d.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room Wardrobe and Bunkbed",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/74b4d35b65bf68ace82e2dd2fc7e060f.webp",
    "context": {
      "refs": [
        {
          "alt": "Front Elevation View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/74d5882531b1c99299393586ab109bc0.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom Wardrobe, Study Unit and Bed",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7532390b804511b6a7103745cecea27a.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Elevation Corner View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/75484791186c068c3b8da7cdb6f9c7ee.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV and Crockery",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/759b249e762828a807d96a66dca1c7ca.webp",
    "context": {
      "refs": [
        {
          "alt": "Floor Plan - Third Floor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/75b34a3abdd9956abd7bca641e457eeb.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom TV and Study",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/75bd6e5bcf67e109ef50af0c03c90674.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom other side view",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/761ec8aaeeff0792bf663618106752ad.webp",
    "context": {
      "refs": [
        {
          "alt": "Class Room 1 View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7645a7aba403560766cbd88794459243.webp",
    "context": {
      "refs": [
        {
          "alt": "False Ceiling Design with Wooden Battens",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7709c33881ccbabca61212adb62f9dcb.webp",
    "context": {
      "refs": [
        {
          "alt": "Cafe Counter",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/775193d20667807da670408be6d29613.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/780495075c44979cdf1a6a23ca1e68bf.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Room \u2013 3 Door Wardrobe, Study unit and Diwan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/78dbbc9d3a7b42a6ff28b2bc13feac77.webp",
    "context": {
      "refs": [
        {
          "alt": "Class Room 1 View 3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7906575c19e28c9b746456bd6e7b2e8a.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7989d8293f90558d36a5a9cd353dd5c5.webp",
    "context": {
      "refs": [
        {
          "alt": "Enchanting Kids%27 Room Interiors | Klassik Landmark, Bangalore",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/79f2e2a1e4d4d047a91f05b27b14e1a3.webp",
    "context": {
      "refs": [
        {
          "alt": "Foyer Partition",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/79f3fd55731b8b6b6792eab53c3235ab.webp",
    "context": {
      "refs": [
        {
          "alt": "Huddle and Discussion Rooms",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7a892fffa267bb6ec6707424c731f65b.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR Wardrobe 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7ac349587ba861aed39a886a6120c868.webp",
    "context": {
      "refs": [
        {
          "alt": "GBR Internal",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7b37690e89f6f68275517196005aebb2.webp",
    "context": {
      "refs": [
        {
          "alt": "Visitors Waiting Lounge",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7b925333295efe71d2c9b37799b776b1.webp",
    "context": {
      "refs": [
        {
          "alt": "Class Room 2 View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7bb624eae8a95060d7d34915bfc762ad.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Terrace Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7c0510ae048c4d048674fdf2d31858cd.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom- King Size Bed and Paneling with Ceiling Lights",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7cc76b99d2d8604a47c6e75addc18c5e.webp",
    "context": {
      "refs": [
        {
          "alt": "Elevation Night View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7d4d634930cd6d1439475f2df72a25fe.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Terrace Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7dee0001f9e1fb89eb9376612a19c028.webp",
    "context": {
      "refs": [
        {
          "alt": "Parallel Kitchen View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7e497facb6f7ddcf223a02d65ad7c184.webp",
    "context": {
      "refs": [
        {
          "alt": "Farm House Front View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7e5bada467768fcc64ad5c9c71453de6.webp",
    "context": {
      "refs": [
        {
          "alt": "Activity Area View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7fb3dfa89def7e0efafe94c9402e17a4.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7fca1a18b7adc4fb322434dbfda45ef1.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room with Feature Wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7fd29e570680c4a153959d0f7df29f3f.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom - Bed with Headboard",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8081e0baa54c67af36a0548bb05fb3a7.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Bird Eye View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/80e65843d3d3cb56514c6dec13c6033f.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8138d496aa866d870f13f1485da39b7d.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Area Crockery Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/81471c241f3f0c3351f04fe2ca746c1e.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/82022c12e63e5ac6233ef8f49d0c0b8e.webp",
    "context": {
      "refs": [
        {
          "alt": "Elevation Side View",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/829b40e758df57a16e4090c33601d148.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/83053c1cb7d5c4af56b63594b901aacf.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/83647b438258ac2343342b532e7159e0.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR Wardrobe side 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/84165d69b3d5a65ed0b6012d53cc875c.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Commercial and Club House - Architcteure Design",
          "title": ""
        },
        {
          "alt": "Mitta Iris - Commercial Complex - Architecture Design",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8442fb815397e8e9e3aa03dfafa17df9.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/849bad9e88d8eb0c05abfc6b9a77e997.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR Internal",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/84a5dfc13443e115a851cb5bf67b7c8c.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/84f03d3f3dcb6efb436db8c6d3e20b30.webp",
    "context": {
      "refs": [
        {
          "alt": "Turnkey Interior Service",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/84f4ca6551c2c5dbbb97bddc3e91fde5.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Other side view",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8516cd8a4c769318c5a5ccf66d4d33f6.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room Openable Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/86633b6aac08e2a25ef4eb10979aecdb.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR Wardrobe Internal",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/86cf229316a703875f0270fca08fa00c.webp",
    "context": {
      "refs": [
        {
          "alt": "TV Unit with Acrylic Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/876b773060ad9172e47ee47845fd07c7.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja Unit with Teakwood temple and Laser cut door",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/877ffdd723b7fa906bf0fc01ae7b1a94.webp",
    "context": {
      "refs": [
        {
          "alt": "TV and Crockery Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/87c47089a7bdecec7379c12adcbfd8a4.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Crockery Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8840405903fa1e63fbf964bee5829493.webp",
    "context": {
      "refs": [
        {
          "alt": "Modular Kitchen View",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/88c56c9300c768f0c341972d5998f758.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom Wardrobe and study unit with Single Bed",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/897b0956f768036fb81700639714a61b.webp",
    "context": {
      "refs": [
        {
          "alt": "Reception and Waiting Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/89b5420e876fbb4c69a8a9be00504485.webp",
    "context": {
      "refs": [
        {
          "alt": "Activity Area View 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8a0cdc1dfb4b583fe7722755a6f67928.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8aa75eb82552bc26602c603298e9a6c9.webp",
    "context": {
      "refs": [
        {
          "alt": "Electrical Plan First Floor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8aef0ee2e872ec2668821851f12a8252.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR Study",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8b615fe6b8ecf9af0f97871dff916005.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8b9b0c17e625233497eaae32de795e26.webp",
    "context": {
      "refs": [
        {
          "alt": "Living area with TV unit and Dining with Mirror Feature wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8c88b2db0d5e61778adc16ab13b9b73f.webp",
    "context": {
      "refs": [
        {
          "alt": "Treadmill - cardio workouts section",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8dc4a0fbd51b0245a4f12748b7568c06.webp",
    "context": {
      "refs": [
        {
          "alt": "3D Layout Plan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8ec021e8557cc5491a185f189b8d04f9.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen View 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8f4d02c67aa55126cd78fa80d166d824.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8f57128468f13134a2366fa53e71a5e7.webp",
    "context": {
      "refs": [
        {
          "alt": "Walking Wardrobe with Aristo Doors",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8f7d98652a153f5573408e17bf63509b.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8f8d8caeb254caba5f25499b097313eb.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Bar Counter Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8f9df15591cea68dd9ad19d793ead6c1.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR Wardrobe side 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/904da6bb80f7e185849e3f8d5fa2ceba.webp",
    "context": {
      "refs": [
        {
          "alt": "Modular Kitchen View 3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/90a6c105dc7f5878dad8a57a1d394bc4.webp",
    "context": {
      "refs": [
        {
          "alt": "Modular Kitchen View 5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/90e8c73f45074478f69b641316ad3887.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room 2 Doors Sliding Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/918f56f7de468139fb42b589b2941051.webp",
    "context": {
      "refs": [
        {
          "alt": "Environment Room View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/91a406dfbf17424293eb981afa0dcd5f.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/928dda5fbc6412d2a9debe96786f6b3e.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/92ae32e4afcdaf8e818bf8ac41824542.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Rom TV Unit and Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/93ecfe3e2d7c2b7785156cf2a367006e.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja and Mirror Paneling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/942a71466ccad8885981a94776ce76bd.webp",
    "context": {
      "refs": [
        {
          "alt": "Shoe Unit with Umbrella Stand - Veneer Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/94e5d894fb37039cbc2088e1d9d2bb3e.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Room False ceiling Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/956c748198a28cbe42d7f4a7724c3449.webp",
    "context": {
      "refs": [
        {
          "alt": "Office Interiors",
          "title": ""
        },
        {
          "alt": "Architectural Services",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/96da5c69d65ad6584f41a2bed35ef959.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Bar Counter Area",
          "title": ""
        },
        {
          "alt": "D' Marina Resto Bar - Interior Design",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/97886bab7f820b82d914b4cbf35d3be4.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom Bed",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/97bd8b86316f793b55d439a88d9cf976.webp",
    "context": {
      "refs": [
        {
          "alt": "Foyer Area Shoe Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/97db5dd409399e97f0b1fc1b1dab9fc7.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Sliding Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/98faf01b7e08fa05372443d9aa6b3a4d.webp",
    "context": {
      "refs": [
        {
          "alt": "TV Unit - Veneer Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/991f08e73e78ea03f627e0a15175f96c.webp",
    "context": {
      "refs": [
        {
          "alt": "Open plan office space",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/99c2fb22f23b6e817e650238c003111b.webp",
    "context": {
      "refs": [
        {
          "alt": "Activity Area View 4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/99c3665b84dcd0ae510a56b37b0e515c.webp",
    "context": {
      "refs": [
        {
          "alt": "False Ceiling and Lighting",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9af4db1ec0c52d2ff4f3462a56297ef3.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room with Pooja Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9afea5c63b51cc2f1f85a5f9b1efbbd5.webp",
    "context": {
      "refs": [
        {
          "alt": "JD Palace Front Closeup View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9b52e0a19dc45269a3d62cff959a5df0.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Side 3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9b5bab98c42beecc745786100c914d7e.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Tall Unit with Acrylic Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9b6fcc95c4cc39f876e66e32fdb5df3e.webp",
    "context": {
      "refs": [
        {
          "alt": "Modular Kitchen with Hob and Chimney",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9cde4534f41e4b7ecc36943f9012b8ee.webp",
    "context": {
      "refs": [
        {
          "alt": "Parent Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9db9ed0ca01a1d097070568e8cf7bdf4.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom complete view",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9ddbfe95f1ef40640a14a34082869f45.webp",
    "context": {
      "refs": [
        {
          "alt": "Common Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9e03e432afd549131aad868776a849ae.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9e28290e4b110c58a0b4c503c610a51b.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen one side view",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9ed0a8ca67667a86d283958310b2a484.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Commercial Complex - Architecture Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9f190847db3595061f683573c2c08ea1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9f3085b077eaac281ecc9bcf98fc9077.webp",
    "context": {
      "refs": [
        {
          "alt": "Class Room 2 View 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9fe4b5e3498905b6b97f9504f6b6447f.webp",
    "context": {
      "refs": [
        {
          "alt": "Conference Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a09951d2e8d2ad1eb82ac71b23185a0c.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Room False ceiling Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a0be48850485996ceff8c50bff250816.webp",
    "context": {
      "refs": [
        {
          "alt": "Media Room View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a2d8363341584ab802942c280af8eb20.webp",
    "context": {
      "refs": [
        {
          "alt": "GBR Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a2f5f906840a3f6cb6672ea38b6856e1.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Reception Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a41a27c63462e60d90ab2629b368f277.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe Internal",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a45921972487deaea364c4899af06e63.webp",
    "context": {
      "refs": [
        {
          "alt": "Feature Wall and Partition",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a483caef833668e71c9ec267fac941a2.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room False ceiling Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a4ae06509fcb20d6b9e926a4bfec9a38.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Side 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a4efb34a610d16946c2cd1db89d074af.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a5845742049f3787bd774add762f70f5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a5f994ae19638d772d58e482681c1716.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Crockery with Pooja Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a621761665bd53b58fa258fa7807bc80.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a690554b6094dd1ebffe48d3b0bf3e8a.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Family Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a7211986e208b342c64b467b78f30cd3.webp",
    "context": {
      "refs": [
        {
          "alt": "Night View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a76973d5c8ab0cf64312a77be6f16f4a.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Terrace Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a8d448b03fd4bfc87f3fd8ba2b4a7da6.webp",
    "context": {
      "refs": [
        {
          "alt": "Terrace 3D Plan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a948158d2d33a61fe43f5ba3e4d503e4.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/aa222e23d536987c2ff30d08822ec171.webp",
    "context": {
      "refs": [
        {
          "alt": "Kingsize Bed with Headboard and Dressing Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ad4f3852d0a63cbcc5c4922f34406268.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Builtin Bed",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ad6d5bbe703316a9eafc2af69fb5a76a.webp",
    "context": {
      "refs": [
        {
          "alt": "Offers and Promotions",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ad8188aea9f768d741b4e488b7a89617.webp",
    "context": {
      "refs": [
        {
          "alt": "Residential Design Options",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/aeba883f38f60fe188b864bdae7d0a79.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR 1 Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/af528289a98d8d45a82d0e1490dbf855.webp",
    "context": {
      "refs": [
        {
          "alt": "Open Cafe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/af7936af2947ecc6fbe7ed70851433ba.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen View 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b03d1f04431e7441196dcb23afff11ca.webp",
    "context": {
      "refs": [
        {
          "alt": "Designer Partition Element",
          "title": ""
        },
        {
          "alt": "Corporate Office Space - Corporate Interior Design",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b095b574b8e228d57da87519055eca3a.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV Unit and Textured paint on the wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b1322cfc694600d390956fc471cb3077.webp",
    "context": {
      "refs": [
        {
          "alt": "Residential Design Options",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b1c8a563a3e76195ab7f2c3db53e3732.webp",
    "context": {
      "refs": [
        {
          "alt": "Media Room View 4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b372cee34badd7be5dadd4ebabd8ecbe.webp",
    "context": {
      "refs": [
        {
          "alt": "Foyer Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b43a4ad29c969e06bc7bb867afd5bf15.webp",
    "context": {
      "refs": [
        {
          "alt": "Farm House Design - Architecture Design",
          "title": ""
        },
        {
          "alt": "Farm House Night View",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b4ca9bbd16ab5d8e49cefa22e07ee3ab.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b76e8aa74f1c1056c8c795a28d018392.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Side 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b77fa4d62804a5204d4d1472e4e17d4d.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b843f8856f12fb67be5a9645d9ab9b64.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen Complete View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b867687ce0bc2535d7afdd77154ffa6a.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Room complete view",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b86c63df32fd828733088972786f4703.webp",
    "context": {
      "refs": [
        {
          "alt": "Open Cafe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b93e6b9990acad476f46f2c4a57c7233.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Area Feature Wall and False Ceiling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ba00e0af15924d3ede8944cefe700615.webp",
    "context": {
      "refs": [
        {
          "alt": "JD Palace Resort - Architecture Design",
          "title": ""
        },
        {
          "alt": "JD Palace Front View",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ba0fd25facf479336e4acb66b4f52d60.webp",
    "context": {
      "refs": [
        {
          "alt": "View of Work out area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bb00f40de1f9703fabcbf66d03372860.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen with Glossy Finish Laminate",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bb3d44aad06a398fee8db9c3192e5e2d.webp",
    "context": {
      "refs": [
        {
          "alt": "Living TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bc0db41d9a5b05fb44acb6e05fa3e2ab.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bd76e3712babc34affd257bc76d51528.webp",
    "context": {
      "refs": [
        {
          "alt": "TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bdb24686476c633a6179b3ab5b864664.webp",
    "context": {
      "refs": [
        {
          "alt": "Kingsize Cantilever Bed with Headboard and Wallpapers",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/beddd53b25efc102b810cef7b8b18df7.webp",
    "context": {
      "refs": [
        {
          "alt": "Night View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bfd69a85e12cd98c5ff420a537ccb261.webp",
    "context": {
      "refs": [
        {
          "alt": "Wardrobe with Mirrors on doors",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bfe748923fbd1b0cb6cbbf9e71ef963a.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Front Elevation Day View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c0acc0a033d350781521bf33085b4b83.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Resto Bar 3D plan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c2466c6f8fe478a2e5e783b63641805c.webp",
    "context": {
      "refs": [
        {
          "alt": "Veneer Paneling Work",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c28728c1e147fe95355b1b396fce725d.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c2ac03e2ec1a78ac6c1c48992fcb8c6d.webp",
    "context": {
      "refs": [
        {
          "alt": "Kingsize Cantilever Bed with Headboard and Dressing Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c2b0c17eb5b5c912d6c6441a81c341da.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c2b58efa4092e6581e4dffc54e8bd8aa.webp",
    "context": {
      "refs": [
        {
          "alt": "Wardrobe with Veneer Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c2f75cb1e3760c6ac994607c6f0a96b7.webp",
    "context": {
      "refs": [
        {
          "alt": "Farm House Top Bird Eye View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c337bc8a2abe27d7d51415c9392e3f83.webp",
    "context": {
      "refs": [
        {
          "alt": "Boxing HIIT session section",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c3c1539d1e213a261b6e165fdd4c1863.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c3cd858492647cf198705b19a2158c01.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c40194fddb93ce2524751284b09de844.webp",
    "context": {
      "refs": [
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c6474778deeb5431e8b7a3ddce79a9e8.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom and Dressing Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c6763ce82e21df16f341c25176b1c4d5.webp",
    "context": {
      "refs": [
        {
          "alt": "SNN Raj Etternia - 3BHK Interiors",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c68b47137dbce13c2818ee3cf634ece6.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c6ec749edbd97b5e723b53d485ea2422.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Front Elevation Day View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c6fe5d3b382582a638df3cd58766d26a.webp",
    "context": {
      "refs": [
        {
          "alt": "Turnkey Construction Service",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c76dddba0f22e69425ede12aa60e292e.webp",
    "context": {
      "refs": [
        {
          "alt": "Montessori Pre School - Interior Design",
          "title": ""
        },
        {
          "alt": "Environment Room View 1",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c79df4c765e5bc1d9f823cdedd61a35c.webp",
    "context": {
      "refs": [
        {
          "alt": "Discover You",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c7ee46978fa0d7b334e9586e442d9618.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Area Crockery and Pooja Unit with Photo Wall",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c8371528da200fc2b617605377c38edc.webp",
    "context": {
      "refs": [
        {
          "alt": "Island Kitchen with Acrylic Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c91bbe8c3af8b80fcad9a3598e588953.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c93e587b03718c52877ee5aae2608d4b.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Elevation Front View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ca05d4ed852096c002c14d2a5474c557.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ca8ff967bf2cd03f271823345241ec4f.webp",
    "context": {
      "refs": [
        {
          "alt": "Wardrobe - Openable Doors with Corner Shelves",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/caa9b57d4fe17d615eca44ab9cf70857.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room Slider Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/caadd31a06a2c36640c9ed0001b7056f.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Pooja and Partition",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cb1a4e372768c2ea8e1541b2d7bb7475.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Club House Complex - Architecture Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cc156ea66584b035094576de0bbd9769.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Builtin Bed",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ccba7bc9d590b114b9cd8f72d31ec322.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ccc95d8e1b42183c153d037fb9df56d9.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cccf9408b27169a1e3c408d54f6789ad.webp",
    "context": {
      "refs": [
        {
          "alt": "Modular Kitchen View 4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cd46a18bda2521e576e395546c80ca33.webp",
    "context": {
      "refs": [
        {
          "alt": "Foyer Area with Seating",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cdbab0127affcb48f7b42c93bb520e40.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cdc18723dc1d94d92f23613d7679b93c.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Club House Complex - Architecture Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cddd290c716ecce96f3602ee4c048e39.webp",
    "context": {
      "refs": [
        {
          "alt": "Crockery with Designer Mirror",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ce0e0338d0a0fd9acd4b4d89f2035d18.webp",
    "context": {
      "refs": [
        {
          "alt": "Office Reception Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cf8fb57245609c0a6b7946a275f9fa1d.webp",
    "context": {
      "refs": [
        {
          "alt": "Open plan office space",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d036eaeda92487146a1a9045e7aaf722.webp",
    "context": {
      "refs": [
        {
          "alt": "Foyer Area - Wooden Partition with Laser design and Seating",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d03f6fa6def20eb612363b4c8f8df92b.webp",
    "context": {
      "refs": [
        {
          "alt": "Crockery",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d0631167310129d345197a237da0e33d.webp",
    "context": {
      "refs": [
        {
          "alt": "Shoe Rack Internal",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d11e198e81b372e382b9fe537e253787.webp",
    "context": {
      "refs": [
        {
          "alt": "View of Open Cafe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d1e72c4febc2d4feaabfd3365b8031a3.webp",
    "context": {
      "refs": [
        {
          "alt": "Kitchen - Duco Paint Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d1feeb5d2b1eafbdd5cf646eaadd7251.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d27269caa2e5bbbd176281a7758e18da.webp",
    "context": {
      "refs": [
        {
          "alt": "The Hidden Garden - Cafe House - Interior Design",
          "title": ""
        },
        {
          "alt": "Reception Area",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d72ac8ad076dbc331a8b1d66097ed1d9.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room with False Ceiling Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d7a39e567dd26b6959d58082bb1112c1.webp",
    "context": {
      "refs": [
        {
          "alt": "Parallel Kitchen side 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d7d8cbe15b02ec7c9591741888060f6f.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR Bedroom other side view",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d88817a17d6c08025f99e99cd81b2699.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Front View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d8b02a8b019ef8c36b0e874d113b8933.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d9195fe54febc74d9fef98fc7e047d84.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV and Foyer Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d954f4a6204de3a1233cbe9d374e87de.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/daadff3167a693b30a8c5adb189d648d.webp",
    "context": {
      "refs": [
        {
          "alt": "Master bedroom - Headboard Paneling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dab259d73db77f6e4fde049f839ca7b0.webp",
    "context": {
      "refs": [
        {
          "alt": "Bird View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/daf069ad6c0c331bbb22e7df77239612.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja and Designer Mirror Paneling",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/db235a53bfb464ac49bca5f0864a3729.webp",
    "context": {
      "refs": [
        {
          "alt": "D'Marina Restaurant Dining Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dbb0dc1ede65352af31fa59d1adea01d.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Pooja Partition",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dbb559865ad489fb4849b1cb1192b6c0.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom complete view",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dc61e5055b909878392125d007fe8510.webp",
    "context": {
      "refs": [
        {
          "alt": "L-Shape Handle Less Kitchen View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dc8c1fef626be1c5cca5e58d072fde77.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dc8e09b2ade0914daaeb7107409f2969.webp",
    "context": {
      "refs": [
        {
          "alt": "Class Room 1 View 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dc9c872d46899cc7e2c1b0c0c4b2d6f4.webp",
    "context": {
      "refs": [
        {
          "alt": "Elevation Side View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dd6eb5a500276489703835a7c0425b15.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Commercial Complex - Architecture Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ddb46f2a90a6980bc4d75c974940ca14.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room \u2013 TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/df00c0af6c940abf47f63f8ec547e535.webp",
    "context": {
      "refs": [
        {
          "alt": "Villa Elevation V2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/df5f2c364d9733669027a881be0713e6.webp",
    "context": {
      "refs": [
        {
          "alt": "Shoe Rack",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e02d633e80505cde0d0092f44131d22c.webp",
    "context": {
      "refs": [
        {
          "alt": "Modular Kitchen Acrylic Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e074ed94cd2a4c9cc42e0cdfd81a8d0b.webp",
    "context": {
      "refs": [
        {
          "alt": "Mitta Iris - Club House Complex - Architecture Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e0b1a8832d2863762c0509cddbc063df.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR wardrobe with King Size Bed",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e1f7462b2a1e1ed0df83f3f98031d7af.webp",
    "context": {
      "refs": [
        {
          "alt": "Open plan office space - Bird Eye View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e2d56bbc616e76664a4b6fa6f001d5f2.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e44f8b108d9216df87eee3f1909d8d07.webp",
    "context": {
      "refs": [
        {
          "alt": "Farm House Evening View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e561d2c0e3a6f3de49394e7812fb5f01.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e60b3b7a98d86c1e1ee10e2f7f22bf73.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e7fe3769ba80b638a1cbf13cdc89c8b9.webp",
    "context": {
      "refs": [
        {
          "alt": "Rope HIIT Workout section",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e8592ffc61d691fa3ab09221d1a64920.webp",
    "context": {
      "refs": [
        {
          "alt": "TV Living Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e922281b7a33c6ea47c6778a8dd288c7.webp",
    "context": {
      "refs": [
        {
          "alt": "Study Room View 4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e972d28f0dd7924b5b0da5273b12abc5.webp",
    "context": {
      "refs": [
        {
          "alt": "Office Reception Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ea58aa64ff98af50d15c631b67e9602a.webp",
    "context": {
      "refs": [
        {
          "alt": "Bedroom with Designer Mirror and Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ea984f04b5a2b87d6f8d39c086b2d9d5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ec22a65eb655611af64cf661b0ce4620.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ed125bdea66765261db53e41cdba6d22.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ee9c77d0aa9fcef08257e7209cc6974b.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Room Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/eea6c5991325674958465d60cae21d50.webp",
    "context": {
      "refs": [
        {
          "alt": "TV and Crockery Unit, False ceiling with Laser cut partition",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/eebff7d5a21336dded9fa478d39f8295.webp",
    "context": {
      "refs": [
        {
          "alt": "Guest Bedroom Complete view",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ef51dc80a44f63e14519dbedeed20c9c.webp",
    "context": {
      "refs": [
        {
          "alt": "GBR",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ef9a336019e08e4ffeb54becec10e5fa.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR Wardrobe 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f15c4f7771cdbbdda3e133bfe4a58cd2.webp",
    "context": {
      "refs": [
        {
          "alt": "L shaped Kitchen",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f2be7e64c771842b1c92b59de06ab71b.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room TV Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f2e61dbe301b8b0f6e51baf322da13cd.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja Unit and Partition Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f355451c1c0b1cc84de8196c92d82e59.webp",
    "context": {
      "refs": [
        {
          "alt": "Utility Side 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f35c3da1791aa4940e4549cd4c8b3e57.webp",
    "context": {
      "refs": [
        {
          "alt": "3 Doors Sliding Wardrobe with Glossy Laminate Finish",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f392b67b901b8cb76d67229f82874c7c.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f479d719b365199cf967254d154c2b8d.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room False Ceiling Design",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f5571e0222e045fbc4e1039405a2c7e4.webp",
    "context": {
      "refs": [
        {
          "alt": "MBR Built-in Bed and Dressing",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f5e6127ffb6b2abc3c78be2e8f1311d5.webp",
    "context": {
      "refs": [
        {
          "alt": "Pooja Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f6b1ecc4a114cf0a2c5d626ff9849940.webp",
    "context": {
      "refs": [
        {
          "alt": "KBR 1 Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f82e8e61a10393a68ac35271a8b7e956.webp",
    "context": {
      "refs": [
        {
          "alt": "Kids Bedroom Study Unit",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f8415d6c8efb614151f43cd0a808729f.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f8432415231cc8df7d0ff2ae6e390fd9.webp",
    "context": {
      "refs": [
        {
          "alt": "Living Room View",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f880d10ed4754135a3a52f3462d73f7b.webp",
    "context": {
      "refs": [
        {
          "alt": "Dining Room",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f962df912b3496e47c18fb3d691c3d70.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f9f0ab13cc62b19b393edd0e14b5f9de.webp",
    "context": {
      "refs": [
        {
          "alt": "Foyer Area with Seating with Mirror",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/faad969107395498987a600327e5f3ce.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fc0f1b3a92ed35ca1392f98a6fdf81dd.webp",
    "context": {
      "refs": [
        {
          "alt": "Activity Area View 5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fc83524c34ded2523d158a126f75d8ab.webp",
    "context": {
      "refs": [
        {
          "alt": "Cabin Rooms",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fe038513b79b0f094a1e6f9d9b750b0d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fece6ed336373969c2227806b0081926.webp",
    "context": {
      "refs": [
        {
          "alt": "GBR Internal Partitions",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ff0a32c5e55013e375d52dc8d1331516.webp",
    "context": {
      "refs": [
        {
          "alt": "Master Bedroom Wardrobe Op2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ff7072e3521c4a48524e78064a055187.webp",
    "context": {
      "refs": [
        {
          "alt": "Foyer Area",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "index.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Architecture & Interior DesignswithCost Effective & Efficient Space Utilisation"
    }
  },
  {
    "path": "interior-3d-vs-actual.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Interior - 3D vs Actual Completed Work"
    }
  },
  {
    "path": "js/03b2eaae6007054a68c38e495f894dba.js",
    "context": {
      "path": "js/03b2eaae6007054a68c38e495f894dba.js"
    }
  },
  {
    "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js",
    "context": {
      "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js"
    }
  },
  {
    "path": "js/0c46896987137b0016246f6bc2243099.js",
    "context": {
      "path": "js/0c46896987137b0016246f6bc2243099.js"
    }
  },
  {
    "path": "js/165d7b0ddfa33362140feea997351b77.js",
    "context": {
      "path": "js/165d7b0ddfa33362140feea997351b77.js"
    }
  },
  {
    "path": "js/16df9ef05001a1741857bf99f5a5738f.js",
    "context": {
      "path": "js/16df9ef05001a1741857bf99f5a5738f.js"
    }
  },
  {
    "path": "js/2a85c11e395a8380b5915443e926b569.js",
    "context": {
      "path": "js/2a85c11e395a8380b5915443e926b569.js"
    }
  },
  {
    "path": "js/34be5330971fdbd18985525bd994b0aa.js",
    "context": {
      "path": "js/34be5330971fdbd18985525bd994b0aa.js"
    }
  },
  {
    "path": "js/35c5f9e096d4da33d2a62031daf14248.js",
    "context": {
      "path": "js/35c5f9e096d4da33d2a62031daf14248.js"
    }
  },
  {
    "path": "js/3d70953a848219e749fedc2cdb906675.js",
    "context": {
      "path": "js/3d70953a848219e749fedc2cdb906675.js"
    }
  },
  {
    "path": "js/3e940a33e44b65c1c0af8bb80a893530.js",
    "context": {
      "path": "js/3e940a33e44b65c1c0af8bb80a893530.js"
    }
  },
  {
    "path": "js/544d012df7acf9c3f0920f67c9e322b9.js",
    "context": {
      "path": "js/544d012df7acf9c3f0920f67c9e322b9.js"
    }
  },
  {
    "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js",
    "context": {
      "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js"
    }
  },
  {
    "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js",
    "context": {
      "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js"
    }
  },
  {
    "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js",
    "context": {
      "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js"
    }
  },
  {
    "path": "js/7260bab328b0ad74815a5efb377bcc67.js",
    "context": {
      "path": "js/7260bab328b0ad74815a5efb377bcc67.js"
    }
  },
  {
    "path": "js/893de96f1b6da546bd7c814964723eca.js",
    "context": {
      "path": "js/893de96f1b6da546bd7c814964723eca.js"
    }
  },
  {
    "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js",
    "context": {
      "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js"
    }
  },
  {
    "path": "js/9455859483e31e4da0e28f10d0742c2a.js",
    "context": {
      "path": "js/9455859483e31e4da0e28f10d0742c2a.js"
    }
  },
  {
    "path": "js/9db10375d298678e53777a2347b87073.js",
    "context": {
      "path": "js/9db10375d298678e53777a2347b87073.js"
    }
  },
  {
    "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js",
    "context": {
      "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js"
    }
  },
  {
    "path": "js/a2261649751fa61b606222c9b2ea3b80.js",
    "context": {
      "path": "js/a2261649751fa61b606222c9b2ea3b80.js"
    }
  },
  {
    "path": "js/a267b9c2db3a101763e2cc5a22b00fe1.js",
    "context": {
      "path": "js/a267b9c2db3a101763e2cc5a22b00fe1.js"
    }
  },
  {
    "path": "js/b0bade6d42c2702ca85774296cc507c4.js",
    "context": {
      "path": "js/b0bade6d42c2702ca85774296cc507c4.js"
    }
  },
  {
    "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js",
    "context": {
      "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js"
    }
  },
  {
    "path": "js/cecb447a04bbe3e8982190dd6e697120.js",
    "context": {
      "path": "js/cecb447a04bbe3e8982190dd6e697120.js"
    }
  },
  {
    "path": "js/d80b370d82680fc786dcc943a327b9f2.js",
    "context": {
      "path": "js/d80b370d82680fc786dcc943a327b9f2.js"
    }
  },
  {
    "path": "js/df1baf343353959d07d006b669e54d1e.js",
    "context": {
      "path": "js/df1baf343353959d07d006b669e54d1e.js"
    }
  },
  {
    "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js",
    "context": {
      "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js"
    }
  },
  {
    "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js",
    "context": {
      "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js"
    }
  },
  {
    "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js",
    "context": {
      "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js"
    }
  },
  {
    "path": "js/faf9ce4e848522206b5c3043551fb2d7.js",
    "context": {
      "path": "js/faf9ce4e848522206b5c3043551fb2d7.js"
    }
  },
  {
    "path": "mitta-iris-architecture-design.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Mitta Iris - Commercial and Club HouseArchitcteure Design"
    }
  },
  {
    "path": "nambiar-villa321.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Nambiar Bellezea Villa G+2 Interiors"
    }
  },
  {
    "path": "oceanus-vista-i-gaurav-saumya.html",
    "context": {
      "title": "Atrio Design Studio | Oceanus Vista-I Gaurav & Saumya",
      "first_heading": "Oceanus Vista I - 2.5 BHK\u00a0Apartment"
    }
  },
  {
    "path": "oceanus-vista-i-giri-manju.html",
    "context": {
      "title": "Atrio Design Studio | Oceanus Vista-I Giri & Manju",
      "first_heading": "Oceanus Vista I - 3 BHK\u00a0Apartment"
    }
  },
  {
    "path": "oceanus-vista-ii-anubhav-gunjan.html",
    "context": {
      "title": "Atrio Design Studio | Oceanus Vista-II Anubhav & Gunjan",
      "first_heading": "Oceanus Vista II - 3.5 BHK Apartment"
    }
  },
  {
    "path": "oceanus-vista-prashant-sindhu.html",
    "context": {
      "title": "Atrio Design Studio | Oceanus Vista - II T7-303 Prashant & Sindhu",
      "first_heading": "Oceanus Vista II - 3.5 BHK\u00a0\u00a0Apartment"
    }
  },
  {
    "path": "offers-and-promotions.html",
    "context": {
      "title": "Atrio Design Studio | Products & Offers",
      "first_heading": "PRODUCTS & OFFERS"
    }
  },
  {
    "path": "offers.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Offers and Promotions"
    }
  },
  {
    "path": "pkg-abhishek-2.5bhk.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Prestige Kew Garden - 2.5 BHK Interiors"
    }
  },
  {
    "path": "portfolio.html",
    "context": {
      "title": "Atrio Design Studio | Portfolio",
      "first_heading": "PORTFOLIO"
    }
  },
  {
    "path": "prestige-ferns-residency-parth-nidhi.html",
    "context": {
      "title": "Atrio Design Studio | Prestige Ferns Residency - Parth & Nidhi",
      "first_heading": "Prestige Ferns Residency - 2.5 BHK\u00a0Apartment"
    }
  },
  {
    "path": "prestige-sunrise-park-ec-gururajan.html",
    "context": {
      "title": "Atrio Design Studio | Prestige Sunrise Park EC \u2013 Mr Gururajan",
      "first_heading": "Prestige Sunrise Park \u2013 2.5 BHK\u00a0Apartment"
    }
  },
  {
    "path": "prestige-sunrise-park-ec-mr-kunal-narula.html",
    "context": {
      "title": "Atrio Design Studio | Prestige Sunrise Park \u2013 EC \u2013 Mr Kunal Narula",
      "first_heading": "Prestige Sunrise Park - 2 BHK\u00a0Apartment"
    }
  },
  {
    "path": "prestige-sunrise-park-mr-rajul-3bhk.html",
    "context": {
      "title": "Atrio Design Studio | Prestige Sunrise Park \u2013 Mr Rajul 3BHK",
      "first_heading": "Prestige Sunrise Park - 3 BHK\u00a0Apartment"
    }
  },
  {
    "path": "prestige-sunrise-park-mr-vivek-2bhk.html",
    "context": {
      "title": "Atrio Design Studio | Prestige Sunrise Park \u2013 Mr Vivek 2BHK",
      "first_heading": "Prestige Sunrise Park - 2 BHK Apartment"
    }
  },
  {
    "path": "resort-jdpalace.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "Resort - J D Palace"
    }
  },
  {
    "path": "salarpuria-laurel-heights-arun-poornima.html",
    "context": {
      "title": "Atrio Design Studio | Salarpuria Sattva Laurel Heights \u2013 Mr Arun & Ms. Poornima",
      "first_heading": "Salarpuria Sattva Laurel Heights - 3BHK\u00a0Apartment"
    }
  },
  {
    "path": "services.html",
    "context": {
      "title": "Atrio Design Studio | Services",
      "first_heading": "OUR SERVICES"
    }
  },
  {
    "path": "shanders-dwellington-arun.html",
    "context": {
      "title": "Atrio Design Studio | Shanders Dwellington \u2013 Arun",
      "first_heading": "Shanders Dwellington \u2013 3 BHK Apartment"
    }
  },
  {
    "path": "snn-raj-etternia-3bhk-shobhit-anju.html",
    "context": {
      "title": "Atrio Design Studio | SNN Raj Etternia \u2013 3BHK Mr. Shobhit @ Ms. Anju",
      "first_heading": "SNN Raj Etternia \u2013 3BHK Apartment"
    }
  },
  {
    "path": "team.html",
    "context": {
      "title": "Atrio Design Studio | Team",
      "first_heading": "TEAM"
    }
  },
  {
    "path": "uber-verdant-varun-parul.html",
    "context": {
      "title": "Atrio Design Studio | Uber Verdant \u2013 Varun & Parul",
      "first_heading": "Uber Verdant \u2013 2 BHK\u00a0Apartment"
    }
  },
  {
    "path": "warranty.html",
    "context": {
      "title": "Atrio Design Studio | T&C / Warranty / Policy",
      "first_heading": "T&C, Warranty and Policy"
    }
  },
  {
    "path": "wavefitgym.html",
    "context": {
      "title": "Atrio Design Studio | Home",
      "first_heading": "WAVEFIT gym and fitness studio"
    }
  }
]

Return only a JSON object mapping each path to its new basename (same extension). No other text.