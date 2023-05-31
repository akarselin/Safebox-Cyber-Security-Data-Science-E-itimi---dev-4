# Safebox-Cyber-Security-Data-Science-E-itimi---dev-4
Safebox Cyber Security Data Science Eğitimi - Ödev 4
Stored Procedure ve Trigger neden kullanılır?
Trigger, kod çalıştığında otomatik olarak çalıştırılan bir oluşumdur. Örneğin insert, delete gibi komutlar kullanıldığında trigger gizli bir şekilde otomatik olarak çalışır. Şunun gibi bir Trigger oluşturabiliriz:

CREATE TRIGGER TriggerName
ON [dbo].[TableName]
FOR DELETE, INSERT, UPDATE
AS
BEGIN
    SET NOCOUNT ON
END 

Triggerda değer dönmez. Bir trigger içinde başka bir trigger döndürülemez.
Stored Procedure ise execute gibi komutlar kullanıldığında açıkça çağırılan bir değerdir. Stored Procedure içinde farklı bir procedure çalıştırabiliriz.
Stored Procedure'de birçok programlama işi yapabilir ve tekrar tekrar çalıştırabiliriz.
Stored Procedure daha güvenlidir.
Stored Procedure yuvalanabilir ve yuvalanmış çağrı ile tekrar tekrar çağrılabilir. Bunun gibi bir Stored Procedure oluşturabiliriz:

CREATE PROCEDURE dbo.Sample_Procedure 
    @param1 int = 0,
    @param2 int  
AS
    SELECT @param1,@param2 
    RETURN 0;

Trigger, olay meydana geldiğinde otomatik olarak yürütülür ve tablonun ve verilerin veritabanından silinmesine veya bırakılmasına karşı raporlama ve veri koruması için kullanılabilir. Triggerı önleyebiliriz. Öte yandan, bir Stored Procedure birisi tarafından çağrılması gerekir.
Trigger, özel bir Stored Procedure türüdür. Bir tabloya eklenir ve yalnızca bir ekleme, güncelleme veya silme gerçekleştiğinde tetiklenir.
