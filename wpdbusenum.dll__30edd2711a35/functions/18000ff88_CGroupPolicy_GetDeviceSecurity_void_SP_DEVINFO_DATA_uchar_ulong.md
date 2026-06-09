# CGroupPolicy::GetDeviceSecurity(void *,_SP_DEVINFO_DATA *,uchar * *,ulong *)

- ea: `0x18000ff88`
- end: `0x1800100c1`
- name: `?GetDeviceSecurity@CGroupPolicy@@IEAAHPEAXPEAU_SP_DEVINFO_DATA@@PEAPEAEPEAK@Z`
- size: `313`
- prototype: `__int64 __fastcall(CGroupPolicy *this, void *, struct _SP_DEVINFO_DATA *, HLOCAL *, unsigned int *RequiredSize)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fb7c`

## callees

- `0x180002fa0`
- `0x18000ff88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010055`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010020`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010020`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010072`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010072`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18000ffd2`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18001004b`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18000ffd2`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18001004b`

## string_xrefs

- `0x18000ffef`: `StorGP: Error %d reading device security\n`
- `0x18001005b`: `StorGP: Error %d reading device security\n`
- `0x180010008`: `Security size %d\n`
- `0x18001009f`: `StorGP: Failed to alloc buffer for security\n`
- `0x180010084`: `StrGP: Read security %p of size %d\n`

## pseudocode

```c
__int64 __fastcall CGroupPolicy::GetDeviceSecurity(
        CGroupPolicy *this,
        void *a2,
        struct _SP_DEVINFO_DATA *a3,
        HLOCAL *a4,
        unsigned int *RequiredSize)
{
  DWORD v8; // eax
  unsigned __int8 *PropertyBuffer; // rax
  DWORD LastError; // eax

  *a4 = 0;
  *RequiredSize = 0;
  if ( SetupDiGetDeviceRegistryPropertyW(a2, a3, 0x17u, 0, 0, 0, RequiredSize)
    || (v8 = GetLastError(), v8 == 122) && *RequiredSize )
  {
    GPDebugPrintX(8u, "Security size %d\n", *RequiredSize);
    PropertyBuffer = (unsigned __int8 *)LocalAlloc(0x40u, *RequiredSize);
    *a4 = PropertyBuffer;
    if ( PropertyBuffer )
    {
      if ( SetupDiGetDeviceRegistryPropertyW(a2, a3, 0x17u, 0, PropertyBuffer, *RequiredSize, RequiredSize) )
      {
        GPDebugPrintX(8u, "StrGP: Read security %p of size %d\n", *a4, *RequiredSize);
        return 1;
      }
      LastError = GetLastError();
      GPDebugPrintX(2u, "StorGP: Error %d reading device security\n", LastError);
      LocalFree(*a4);
      *a4 = 0;
    }
    else
    {
      GPDebugPrintX(2u, "StorGP: Failed to alloc buffer for security\n");
    }
  }
  else
  {
    GPDebugPrintX(4u, "StorGP: Error %d reading device security\n", v8);
  }
  *RequiredSize = 0;
  return 0;
}

```

## disassembly

```asm
0x18000ff88  push    rbx
0x18000ff8a  push    rbp
0x18000ff8b  push    rsi
0x18000ff8c  push    rdi
0x18000ff8d  sub     rsp, 48h
0x18000ff91  mov     rbx, [rsp+68h+arg_20]
0x18000ff99  mov     rsi, r8
0x18000ff9c  mov     rbp, rdx
0x18000ff9f  mov     qword ptr [r9], 0
0x18000ffa6  mov     rdi, r9
0x18000ffa9  mov     [rsp+68h+RequiredSize], rbx; RequiredSize
0x18000ffae  xor     r9d, r9d; PropertyRegDataType
0x18000ffb1  mov     [rsp+68h+PropertyBufferSize], 0; PropertyBufferSize
0x18000ffb9  mov     rdx, rsi; DeviceInfoData
0x18000ffbc  mov     dword ptr [rbx], 0
0x18000ffc2  mov     rcx, rbp; DeviceInfoSet
0x18000ffc5  mov     [rsp+68h+PropertyBuffer], 0; PropertyBuffer
0x18000ffce  lea     r8d, [r9+17h]; Property
0x18000ffd2  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x18000ffd8  test    eax, eax
0x18000ffda  jnz     short loc_180010005
0x18000ffdc  call    cs:__imp_GetLastError
0x18000ffe2  cmp     eax, 7Ah ; 'z'
0x18000ffe5  jnz     short loc_18000FFEC
0x18000ffe7  cmp     dword ptr [rbx], 0
0x18000ffea  jnz     short loc_180010005
0x18000ffec  mov     r8d, eax
0x18000ffef  lea     rdx, aStorgpErrorDRe; "StorGP: Error %d reading device securit"...
0x18000fff6  mov     ecx, 4; unsigned int
0x18000fffb  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010000  jmp     loc_1800100B0
0x180010005  mov     r8d, [rbx]
0x180010008  lea     rdx, aSecuritySizeD; "Security size %d\n"
0x18001000f  mov     ecx, 8; unsigned int
0x180010014  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010019  mov     edx, [rbx]; uBytes
0x18001001b  mov     ecx, 40h ; '@'; uFlags
0x180010020  call    cs:__imp_LocalAlloc
0x180010026  mov     [rdi], rax
0x180010029  test    rax, rax
0x18001002c  jz      short loc_18001009F
0x18001002e  mov     ecx, [rbx]
0x180010030  xor     r9d, r9d; PropertyRegDataType
0x180010033  mov     [rsp+68h+RequiredSize], rbx; RequiredSize
0x180010038  mov     rdx, rsi; DeviceInfoData
0x18001003b  mov     [rsp+68h+PropertyBufferSize], ecx; PropertyBufferSize
0x18001003f  mov     rcx, rbp; DeviceInfoSet
0x180010042  mov     [rsp+68h+PropertyBuffer], rax; PropertyBuffer
0x180010047  lea     r8d, [r9+17h]; Property
0x18001004b  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x180010051  test    eax, eax
0x180010053  jnz     short loc_180010081
0x180010055  call    cs:__imp_GetLastError
0x18001005b  lea     rdx, aStorgpErrorDRe; "StorGP: Error %d reading device securit"...
0x180010062  mov     ecx, 2; unsigned int
0x180010067  mov     r8d, eax
0x18001006a  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18001006f  mov     rcx, [rdi]; hMem
0x180010072  call    cs:__imp_LocalFree
0x180010078  mov     qword ptr [rdi], 0
0x18001007f  jmp     short loc_1800100B0
0x180010081  mov     r9d, [rbx]
0x180010084  lea     rdx, aStrgpReadSecur; "StrGP: Read security %p of size %d\n"
0x18001008b  mov     r8, [rdi]
0x18001008e  mov     ecx, 8; unsigned int
0x180010093  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010098  mov     eax, 1
0x18001009d  jmp     short loc_1800100B8
0x18001009f  lea     rdx, aStorgpFailedTo; "StorGP: Failed to alloc buffer for secu"...
0x1800100a6  mov     ecx, 2; unsigned int
0x1800100ab  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800100b0  mov     dword ptr [rbx], 0
0x1800100b6  xor     eax, eax
0x1800100b8  add     rsp, 48h
0x1800100bc  pop     rdi
0x1800100bd  pop     rsi
0x1800100be  pop     rbp
0x1800100bf  pop     rbx
0x1800100c0  retn
```
