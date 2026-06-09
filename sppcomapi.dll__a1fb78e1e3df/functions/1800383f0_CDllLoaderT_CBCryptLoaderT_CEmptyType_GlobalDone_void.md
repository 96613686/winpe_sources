# CDllLoaderT<CBCryptLoaderT<CEmptyType>>::GlobalDone(void)

- ea: `0x1800383f0`
- end: `0x180038459`
- name: `?GlobalDone@?$CDllLoaderT@V?$CBCryptLoaderT@VCEmptyType@@@@@@KAJXZ`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800383f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038400`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038400`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038431`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038431`

## pseudocode

```c
__int64 CDllLoaderT<CBCryptLoaderT<CEmptyType>>::GlobalDone()
{
  if ( hLibModule )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
  }
  CBCryptLoaderT<CEmptyType>::g_Instance = -2147467259;
  if ( dword_180047128 )
  {
    DeleteCriticalSection(&CriticalSection);
    dword_180047128 = 0;
  }
  dword_18004712C = 0;
  return 0;
}

```

## disassembly

```asm
0x1800383f0  sub     rsp, 28h
0x1800383f4  mov     rcx, cs:hLibModule; hLibModule
0x1800383fb  test    rcx, rcx
0x1800383fe  jz      short loc_180038417
0x180038400  call    cs:__imp_FreeLibrary
0x180038407  nop     dword ptr [rax+rax+00h]
0x18003840c  mov     cs:hLibModule, 0
0x180038417  cmp     cs:dword_180047128, 0
0x18003841e  mov     cs:?g_Instance@?$CBCryptLoaderT@VCEmptyType@@@@0V1@A, 80004005h; CBCryptLoaderT<CEmptyType> CBCryptLoaderT<CEmptyType>::g_Instance
0x180038428  jz      short loc_180038447
0x18003842a  lea     rcx, CriticalSection; lpCriticalSection
0x180038431  call    cs:__imp_DeleteCriticalSection
0x180038438  nop     dword ptr [rax+rax+00h]
0x18003843d  mov     cs:dword_180047128, 0
0x180038447  mov     cs:dword_18004712C, 0
0x180038451  xor     eax, eax
0x180038453  add     rsp, 28h
0x180038457  retn
```
