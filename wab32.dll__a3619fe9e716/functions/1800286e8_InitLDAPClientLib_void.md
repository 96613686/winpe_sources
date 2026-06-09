# InitLDAPClientLib(void)

- ea: `0x1800286e8`
- end: `0x18002876b`
- name: `?InitLDAPClientLib@@YAHXZ`
- size: `131`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b94`
- `0x180026090`
- `0x180026a10`
- `0x180028014`
- `0x180028f08`
- `0x18002abc0`
- `0x18005ecd8`

## callees

- `0x180027214`
- `0x1800286e8`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800286fd`
- `KERNEL32!LoadLibraryW` at `0x1800286fd`
- `KERNEL32!FreeLibrary` at `0x180028734`
- `KERNEL32!FreeLibrary` at `0x180028734`

## string_xrefs

- `0x1800286f6`: `WLDAP32.DLL`

## pseudocode

```c
__int64 InitLDAPClientLib(void)
{
  HMODULE LibraryW; // rax
  unsigned int v2; // eax

  if ( ghLDAPDLLInst )
  {
    v2 = ulLDAPDLLRefCount;
  }
  else
  {
    LibraryW = LoadLibraryW(L"WLDAP32.DLL");
    ghLDAPDLLInst = LibraryW;
    if ( !LibraryW )
      return 0;
    if ( !(unsigned int)GetApiProcAddresses(LibraryW, (struct _APIFCN *)&LDAPAPIList, 0x24u) )
    {
      if ( ghLDAPDLLInst )
      {
        FreeLibrary(ghLDAPDLLInst);
        ghLDAPDLLInst = 0;
      }
      return 0;
    }
    v2 = ulLDAPDLLRefCount + 1;
  }
  ulLDAPDLLRefCount = v2 + 1;
  return 1;
}

```

## disassembly

```asm
0x1800286e8  sub     rsp, 28h
0x1800286ec  cmp     cs:?ghLDAPDLLInst@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghLDAPDLLInst
0x1800286f4  jnz     short loc_180028753
0x1800286f6  lea     rcx, aWldap32Dll; "WLDAP32.DLL"
0x1800286fd  call    cs:__imp_LoadLibraryW
0x180028703  mov     cs:?ghLDAPDLLInst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghLDAPDLLInst
0x18002870a  test    rax, rax
0x18002870d  jz      short loc_180028745
0x18002870f  mov     r8d, 24h ; '$'; unsigned int
0x180028715  lea     rdx, ?LDAPAPIList@@3PAU_APIFCN@@A; struct _APIFCN *
0x18002871c  mov     rcx, rax; hModule
0x18002871f  call    ?GetApiProcAddresses@@YAHPEAUHINSTANCE__@@PEAU_APIFCN@@I@Z; GetApiProcAddresses(HINSTANCE__ *,_APIFCN *,uint)
0x180028724  test    eax, eax
0x180028726  jnz     short loc_180028749
0x180028728  mov     rcx, cs:?ghLDAPDLLInst@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002872f  test    rcx, rcx
0x180028732  jz      short loc_180028745
0x180028734  call    cs:__imp_FreeLibrary
0x18002873a  mov     cs:?ghLDAPDLLInst@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghLDAPDLLInst
0x180028745  xor     eax, eax
0x180028747  jmp     short loc_180028766
0x180028749  mov     eax, cs:?ulLDAPDLLRefCount@@3KA; ulong ulLDAPDLLRefCount
0x18002874f  inc     eax
0x180028751  jmp     short loc_180028759
0x180028753  mov     eax, cs:?ulLDAPDLLRefCount@@3KA; ulong ulLDAPDLLRefCount
0x180028759  inc     eax
0x18002875b  mov     cs:?ulLDAPDLLRefCount@@3KA, eax; ulong ulLDAPDLLRefCount
0x180028761  mov     eax, 1
0x180028766  add     rsp, 28h
0x18002876a  retn
```
