# InitCryptoLib(void)

- ea: `0x18000683c`
- end: `0x1800068db`
- name: `?InitCryptoLib@@YAHXZ`
- size: `159`
- prototype: `__int64(void)`
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000597c`
- `0x180005a1c`
- `0x180005e68`
- `0x180006098`
- `0x18004f3b4`
- `0x18004f8c4`
- `0x180053818`
- `0x1800719e8`

## callees

- `0x1800054a4`
- `0x18000683c`
- `0x180027214`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180006864`
- `KERNEL32!LoadLibraryW` at `0x180006896`
- `KERNEL32!LoadLibraryW` at `0x180006864`
- `KERNEL32!LoadLibraryW` at `0x180006896`

## string_xrefs

- `0x18000685d`: `CRYPT32.DLL`
- `0x18000688f`: `ADVAPI32.DLL`

## pseudocode

```c
__int64 InitCryptoLib(void)
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rax

  if ( gfPrevCryptoLoadFailed == 1 )
    return 0;
  if ( ghCryptoDLLInst )
  {
    v1 = ghAdvApiDLLInst;
  }
  else
  {
    if ( ghAdvApiDLLInst )
      goto LABEL_8;
    LibraryW = LoadLibraryW(L"CRYPT32.DLL");
    ghCryptoDLLInst = LibraryW;
    if ( !LibraryW )
      goto LABEL_8;
    if ( !(unsigned int)GetApiProcAddresses(LibraryW, (struct _APIFCN *)&Crypt32CryptoAPIList, 0x13u) )
      goto LABEL_8;
    v1 = LoadLibraryW(L"ADVAPI32.DLL");
    ghAdvApiDLLInst = v1;
    if ( !v1 || !ghCryptoDLLInst )
      goto LABEL_8;
  }
  if ( !v1 )
  {
LABEL_8:
    gfPrevCryptoLoadFailed = 1;
    DeinitCryptoLib();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000683c  sub     rsp, 28h
0x180006840  cmp     cs:?gfPrevCryptoLoadFailed@@3HA, 1; int gfPrevCryptoLoadFailed
0x180006847  jz      short loc_1800068C1
0x180006849  cmp     cs:?ghCryptoDLLInst@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghCryptoDLLInst
0x180006851  jnz     short loc_1800068C8
0x180006853  cmp     cs:?ghAdvApiDLLInst@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghAdvApiDLLInst
0x18000685b  jnz     short loc_1800068B2
0x18000685d  lea     rcx, LibFileName; "CRYPT32.DLL"
0x180006864  call    cs:__imp_LoadLibraryW
0x18000686a  mov     cs:?ghCryptoDLLInst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghCryptoDLLInst
0x180006871  test    rax, rax
0x180006874  jz      short loc_1800068B2
0x180006876  mov     r8d, 13h; unsigned int
0x18000687c  lea     rdx, ?Crypt32CryptoAPIList@@3PAU_APIFCN@@A; struct _APIFCN *
0x180006883  mov     rcx, rax; hModule
0x180006886  call    ?GetApiProcAddresses@@YAHPEAUHINSTANCE__@@PEAU_APIFCN@@I@Z; GetApiProcAddresses(HINSTANCE__ *,_APIFCN *,uint)
0x18000688b  test    eax, eax
0x18000688d  jz      short loc_1800068B2
0x18000688f  lea     rcx, aAdvapi32Dll_0; "ADVAPI32.DLL"
0x180006896  call    cs:__imp_LoadLibraryW
0x18000689c  mov     cs:?ghAdvApiDLLInst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghAdvApiDLLInst
0x1800068a3  test    rax, rax
0x1800068a6  jz      short loc_1800068B2
0x1800068a8  cmp     cs:?ghCryptoDLLInst@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghCryptoDLLInst
0x1800068b0  jnz     short loc_1800068CF
0x1800068b2  mov     cs:?gfPrevCryptoLoadFailed@@3HA, 1; int gfPrevCryptoLoadFailed
0x1800068bc  call    ?DeinitCryptoLib@@YAXXZ; DeinitCryptoLib(void)
0x1800068c1  xor     eax, eax
0x1800068c3  add     rsp, 28h
0x1800068c7  retn
0x1800068c8  mov     rax, cs:?ghAdvApiDLLInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghAdvApiDLLInst
0x1800068cf  test    rax, rax
0x1800068d2  jz      short loc_1800068B2
0x1800068d4  mov     eax, 1
0x1800068d9  jmp     short loc_1800068C3
```
