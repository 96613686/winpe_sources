# IsBulkVideoEndpoint

- ea: `0x14000c95c`
- end: `0x14000c9dc`
- name: `IsBulkVideoEndpoint`
- size: `128`
- prototype: `__int64 __fastcall(PVOID DescriptorBuffer, PVOID StartPosition)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015234`
- `0x1400166ac`
- `0x1400171d0`
- `0x140017ed0`

## callees

- `0x14000c95c`
- `0x14000ca50`
- `0x14000d2d0`
- `0x14000d434`
- `0x14001709c`

## pseudocode

```c
bool __fastcall IsBulkVideoEndpoint(struct _USB_CONFIGURATION_DESCRIPTOR *DescriptorBuffer, UCHAR *StartPosition)
{
  char v2; // bl
  PUSB_COMMON_DESCRIPTOR EndpointDescriptor; // rax
  char v7; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v7 = 0;
  if ( (int)GetVideoEndpointAddress(DescriptorBuffer, StartPosition, (UCHAR *)&v7) >= 0 )
  {
    if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() )
      EndpointDescriptor = GetEndpointDescriptorEx((char *)DescriptorBuffer, StartPosition, v7, 0, 0, 0);
    else
      EndpointDescriptor = (PUSB_COMMON_DESCRIPTOR)GetEndpointDescriptor(
                                                     (unsigned __int16 *)&DescriptorBuffer->bLength,
                                                     StartPosition,
                                                     v7,
                                                     0,
                                                     0);
    if ( EndpointDescriptor )
      return (EndpointDescriptor[1].bDescriptorType & 3) == 2;
  }
  return v2;
}

```

## disassembly

```asm
0x14000c95c  mov     rax, rsp
0x14000c95f  mov     [rax+8], rbx
0x14000c963  mov     [rax+10h], rsi
0x14000c967  push    rdi
0x14000c968  sub     rsp, 30h
0x14000c96c  xor     bl, bl
0x14000c96e  lea     r8, [rax+18h]
0x14000c972  mov     [rax+18h], bl
0x14000c975  mov     rdi, rdx
0x14000c978  mov     rsi, rcx
0x14000c97b  call    GetVideoEndpointAddress
0x14000c980  test    eax, eax
0x14000c982  js      short loc_14000C9C9
0x14000c984  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x14000c989  mov     r8b, [rsp+38h+arg_10]
0x14000c98e  xor     r9d, r9d
0x14000c991  mov     rdx, rdi; StartPosition
0x14000c994  mov     rcx, rsi; DescriptorBuffer
0x14000c997  test    eax, eax
0x14000c999  jz      short loc_14000C9AC
0x14000c99b  mov     [rsp+38h+var_10], r9; __int64
0x14000c9a0  mov     [rsp+38h+var_18], r9; __int64
0x14000c9a5  call    GetEndpointDescriptorEx
0x14000c9aa  jmp     short loc_14000C9BA
0x14000c9ac  mov     [rsp+38h+var_18], 0; __int64
0x14000c9b5  call    GetEndpointDescriptor
0x14000c9ba  test    rax, rax
0x14000c9bd  jz      short loc_14000C9C9
0x14000c9bf  mov     al, [rax+3]
0x14000c9c2  and     al, 3
0x14000c9c4  cmp     al, 2
0x14000c9c6  setz    bl
0x14000c9c9  mov     rsi, [rsp+38h+arg_8]
0x14000c9ce  mov     al, bl
0x14000c9d0  mov     rbx, [rsp+38h+arg_0]
0x14000c9d5  add     rsp, 30h
0x14000c9d9  pop     rdi
0x14000c9da  retn
```
