# RandomIdsDb
10 million randomly generated ids for Sql Server
e.g.:
3693720165
1231855582
1020190224
2499768406
2749148391
1720855607
3122889697
3141281537
2459068190
2527365701
2756147857

SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[YourIds](
	[Id] [int] IDENTITY(1,1) PRIMARY KEY NOT NULL,
	[YourId] [bigint] NOT NULL,
	[USED] [bit] NOT NULL DEFAULT(0),
	[CREATED] [datetime] NULL)



DECLARE @newId BIGINT;
UPDATE TOP (1)
    n
SET Used = 1,
    Created = GETUTCDATE(),
    @newId = ncid
FROM YourDb.YourTable n
WHERE Used = 0;
