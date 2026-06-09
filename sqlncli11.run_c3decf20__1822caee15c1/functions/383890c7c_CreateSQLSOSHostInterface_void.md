# CreateSQLSOSHostInterface(void)

- ea: `0x383890c7c`
- end: `0x383890cc1`
- name: `?CreateSQLSOSHostInterface@@YAJXZ`
- size: `69`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x3838924f8`

## callees

- `0x383890c7c`
- `0x38391aed0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x383890c91`
- `KERNEL32!GetModuleHandleW` at `0x383890c91`
- `KERNEL32!GetLastError` at `0x3838f2b9a`
- `KERNEL32!GetLastError` at `0x3838f2b9a`
- `KERNEL32!GetProcAddress` at `0x3838f2b6c`
- `KERNEL32!GetProcAddress` at `0x3838f2b6c`

## string_xrefs

- `0x383890c8a`: `SQLOS.DLL`
- `0x3838f2b62`: `CreateVersionedSOSHostObject`

## pseudocode

```c
__int64 CreateSQLSOSHostInterface(void)
{
  HMODULE ModuleHandleW; // rax
  signed int v1; // ebx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  unsigned int v5; // eax

  g_pISOSHost = 0;
  ModuleHandleW = GetModuleHandleW(L"SQLOS.DLL");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "CreateVersionedSOSHostObject");
    if ( ProcAddress )
    {
      v1 = ((__int64 (__fastcall *)(GUID *, __int64, const wchar_t *, struct ISOSHost **))ProcAddress)(
             &GUID_3e1aeffe_a6ff_4774_a3ea_dc1517ed7dfa,
             26,
             L"SQLNCLI11",
             &g_pISOSHost);
    }
    else
    {
      LastError = GetLastError();
      v1 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v1 = LastError;
    }
  }
  else
  {
    v1 = -2147221497;
  }
  if ( v1 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(struct ISOSHost *, __int64, const wchar_t *, struct IMalloc **))(*(_QWORD *)g_pISOSHost + 368LL))(
           g_pISOSHost,
           515,
           L"MSDART",
           &g_pMO);
    g_AllocatorInUse = 0;
    v1 = v5;
    g_fDisableMpHeap = 1;
    if ( (bidGblFlags & 2) != 0 && off_383B4A178[0] )
      bidTraceW(off_383B434C0[0], 2359296, off_383B4A178[0], v5);
  }
  else
  {
    g_AllocatorInUse = 1;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x383890c7c  push    rbx
0x383890c7e  sub     rsp, 20h
0x383890c82  and     cs:?g_pISOSHost@@3PEAUISOSHost@@EA, 0; ISOSHost * g_pISOSHost
0x383890c8a  lea     rcx, ModuleName; "SQLOS.DLL"
0x383890c91  call    cs:__imp_GetModuleHandleW
0x383890c97  test    rax, rax
0x383890c9a  jnz     loc_3838F2B62
0x383890ca0  mov     ebx, 80040007h
0x383890ca5  test    ebx, ebx
0x383890ca7  jns     loc_3838F2BB3
0x383890cad  mov     cs:?g_AllocatorInUse@@3W4AllocatorEnum@@A, 1; AllocatorEnum g_AllocatorInUse
0x383890cb7  jmp     short $+2
0x383890cb9  mov     eax, ebx
0x383890cbb  add     rsp, 20h
0x383890cbf  pop     rbx
0x383890cc0  retn
0x3838f2b62  lea     rdx, aCreateversione; "CreateVersionedSOSHostObject"
0x3838f2b69  mov     rcx, rax; hModule
0x3838f2b6c  call    cs:__imp_GetProcAddress
0x3838f2b72  test    rax, rax
0x3838f2b75  jz      short loc_3838F2B9A
0x3838f2b77  lea     r9, ?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x3838f2b7e  lea     r8, aSqlncli11; "SQLNCLI11"
0x3838f2b85  lea     rcx, _GUID_3e1aeffe_a6ff_4774_a3ea_dc1517ed7dfa
0x3838f2b8c  mov     edx, 1Ah
0x3838f2b91  call    rax
0x3838f2b93  mov     ebx, eax
0x3838f2b95  jmp     loc_383890CA5
0x3838f2b9a  call    cs:__imp_GetLastError
0x3838f2ba0  movzx   ebx, ax
0x3838f2ba3  or      ebx, 80070000h
0x3838f2ba9  test    eax, eax
0x3838f2bab  cmovle  ebx, eax
0x3838f2bae  jmp     loc_383890CA5
0x3838f2bb3  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x3838f2bba  lea     r9, ?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838f2bc1  lea     r8, aMsdart; "MSDART"
0x3838f2bc8  mov     rax, [rcx]
0x3838f2bcb  mov     edx, 203h
0x3838f2bd0  call    qword ptr [rax+170h]
0x3838f2bd6  and     cs:?g_AllocatorInUse@@3W4AllocatorEnum@@A, 0; AllocatorEnum g_AllocatorInUse
0x3838f2bdd  test    byte ptr cs:_bidGblFlags, 2
0x3838f2be4  mov     ebx, eax
0x3838f2be6  mov     cs:?g_fDisableMpHeap@@3HA, 1; int g_fDisableMpHeap
0x3838f2bf0  jz      loc_383890CB9
0x3838f2bf6  mov     rcx, cs:off_383B4A178; "<CreateSQLSOSHostInterface|INFO> SOSHos"...
0x3838f2bfd  test    rcx, rcx
0x3838f2c00  jz      loc_383890CB9
0x3838f2c06  mov     r8, cs:off_383B4A178; "<CreateSQLSOSHostInterface|INFO> SOSHos"...
0x3838f2c0d  mov     rcx, cs:off_383B434C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838f2c14  mov     r9d, eax
0x3838f2c17  mov     edx, 240000h
0x3838f2c1c  call    _bidTraceW
0x3838f2c21  nop
0x3838f2c22  jmp     loc_383890CB9
```
