# WHvSetPartitionProperty
**Note: A prerelease of this API is available starting in the Windows Insiders Preview Build 17083**

## Syntax
```C
HRESULT
WINAPI
WHvSetPartitionProperty(
    _In_ WHV_PARTITION_HANDLE Partition,
    _In_ WHV_PARTITION_PROPERTY_CODE PropertyCode,
    _In_reads_bytes_(PropertyBufferSizeInBytes) const VOID* PropertyBuffer,
    _In_ UINT32 PropertyBufferSizeInBytes
    );
```
### Parameters

`Partition`

Handle to the partition object. 

`PropertyCode`

Specifies the property that is being set.

`PropertyBuffer`

Specifies the input buffer that provides the property value. 

`PropertyBufferSizeInBytes`

Specifies the size of the input buffer, in bytes. 

## Return Value

If the operation completed successfully, the return value is `S_OK`. 

The function returns `E_WHV_UNKNOWN_PROPERTY` for attempts to configure a property that is not available on the current system. 

The function returns `E_WHV_INVALID_PARTITION_STATE` if the property cannot be modified in the current state of the partition, particularly for attempts to set a property that can only be modified prior to executing the partition but a virtual processor in the partition already started executing. 

