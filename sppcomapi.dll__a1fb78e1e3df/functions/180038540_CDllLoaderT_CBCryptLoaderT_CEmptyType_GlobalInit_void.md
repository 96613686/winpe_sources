# CDllLoaderT<CBCryptLoaderT<CEmptyType>>::GlobalInit(void)

- ea: `0x180038540`
- end: `0x1800385c3`
- name: `?GlobalInit@?$CDllLoaderT@V?$CBCryptLoaderT@VCEmptyType@@@@@@KAJXZ`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180038540`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038552`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038552`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003857d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003857d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003859b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003859b`

## pseudocode

```c
__int64 CDllLoaderT<CBCryptLoaderT<CEmptyType>>::GlobalInit()
{
  unsigned int v0; // ebx
  signed int LastError; // eax

  if ( hLibModule )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
  }
  v0 = -2147467259;
  CBCryptLoaderT<CEmptyType>::g_Instance = -2147467259;
  if ( InitializeCriticalSectionAndSpinCount(&CriticalSection, 0) )
  {
    dword_180047128 = 1;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      else
        return (unsigned int)LastError;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180038540  push    rbx
0x180038542  sub     rsp, 20h
0x180038546  mov     rcx, cs:hLibModule; hLibModule
0x18003854d  test    rcx, rcx
0x180038550  jz      short loc_180038569
0x180038552  call    cs:__imp_FreeLibrary
0x180038559  nop     dword ptr [rax+rax+00h]
0x18003855e  mov     cs:hLibModule, 0
0x180038569  mov     ebx, 80004005h
0x18003856e  lea     rcx, CriticalSection; lpCriticalSection
0x180038575  xor     edx, edx; dwSpinCount
0x180038577  mov     cs:?g_Instance@?$CBCryptLoaderT@VCEmptyType@@@@0V1@A, ebx; CBCryptLoaderT<CEmptyType> CBCryptLoaderT<CEmptyType>::g_Instance
0x18003857d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180038584  nop     dword ptr [rax+rax+00h]
0x180038589  test    eax, eax
0x18003858b  jz      short loc_18003859B
0x18003858d  mov     cs:dword_180047128, 1
0x180038597  xor     ebx, ebx
0x180038599  jmp     short loc_1800385BA
0x18003859b  call    cs:__imp_GetLastError
0x1800385a2  nop     dword ptr [rax+rax+00h]
0x1800385a7  test    eax, eax
0x1800385a9  jz      short loc_1800385BA
0x1800385ab  jg      short loc_1800385B1
0x1800385ad  mov     ebx, eax
0x1800385af  jmp     short loc_1800385BA
0x1800385b1  movzx   ebx, ax
0x1800385b4  or      ebx, 80070000h
0x1800385ba  mov     eax, ebx
0x1800385bc  add     rsp, 20h
0x1800385c0  pop     rbx
0x1800385c1  retn
```
