# InitCommonControlLib(void)

- ea: `0x180068538`
- end: `0x1800685f3`
- name: `?InitCommonControlLib@@YAHXZ`
- size: `187`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180074bf4`

## callees

- `0x180027214`
- `0x180068538`
- `0x18008ebb0`
- `0x18008ec20`
- `0x180093010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180068564`
- `KERNEL32!LoadLibraryW` at `0x180068564`
- `KERNEL32!FreeLibrary` at `0x1800685ce`
- `KERNEL32!FreeLibrary` at `0x1800685ce`

## string_xrefs

- `0x18006855d`: `COMCTL32.DLL`

## pseudocode

```c
__int64 InitCommonControlLib(void)
{
  __int64 result; // rax
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF
  int v2; // [rsp+38h] [rbp+10h] BYREF
  int v3; // [rsp+3Ch] [rbp+14h]

  if ( !ghCommCtrlDLLInst )
  {
    ulCookie = 0;
    SHActivateContext(&ulCookie);
    ghCommCtrlDLLInst = LoadLibraryW(L"COMCTL32.DLL");
    SHDeactivateContext(ulCookie);
    if ( !ghCommCtrlDLLInst )
      return 0;
    if ( !(unsigned int)GetApiProcAddresses(ghCommCtrlDLLInst, (struct _APIFCN *)&CommCtrlAPIList, 0xAu)
      || (v2 = 8, v3 = 42495, !(unsigned int)((__int64 (__fastcall *)(int *))gpfnInitCommonControlsEx)(&v2)) )
    {
      if ( ghCommCtrlDLLInst )
      {
        FreeLibrary(ghCommCtrlDLLInst);
        ghCommCtrlDLLInst = 0;
      }
      return 0;
    }
  }
  result = 1;
  ++gulCommCtrlDLLRefCount;
  return result;
}

```

## disassembly

```asm
0x180068538  sub     rsp, 28h
0x18006853c  cmp     cs:?ghCommCtrlDLLInst@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghCommCtrlDLLInst
0x180068544  jnz     loc_1800685E3
0x18006854a  lea     rcx, [rsp+28h+ulCookie]
0x18006854f  mov     [rsp+28h+ulCookie], 0
0x180068558  call    SHActivateContext
0x18006855d  lea     rcx, aComctl32Dll_0; "COMCTL32.DLL"
0x180068564  call    cs:__imp_LoadLibraryW
0x18006856a  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18006856f  mov     cs:?ghCommCtrlDLLInst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghCommCtrlDLLInst
0x180068576  call    SHDeactivateContext
0x18006857b  mov     rcx, cs:?ghCommCtrlDLLInst@@3PEAUHINSTANCE__@@EA; hModule
0x180068582  test    rcx, rcx
0x180068585  jz      short loc_1800685DF
0x180068587  mov     r8d, 0Ah; unsigned int
0x18006858d  lea     rdx, ?CommCtrlAPIList@@3PAU_APIFCN@@A; struct _APIFCN *
0x180068594  call    ?GetApiProcAddresses@@YAHPEAUHINSTANCE__@@PEAU_APIFCN@@I@Z; GetApiProcAddresses(HINSTANCE__ *,_APIFCN *,uint)
0x180068599  test    eax, eax
0x18006859b  jz      short loc_1800685C2
0x18006859d  mov     rax, cs:?gpfnInitCommonControlsEx@@3P6AHPEAUtagINITCOMMONCONTROLSEX@@@ZEA; int (*gpfnInitCommonControlsEx)(tagINITCOMMONCONTROLSEX *)
0x1800685a4  lea     rcx, [rsp+28h+arg_8]
0x1800685a9  mov     [rsp+28h+arg_8], 8
0x1800685b1  mov     [rsp+28h+arg_C], 0A5FFh
0x1800685b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800685be  test    eax, eax
0x1800685c0  jnz     short loc_1800685E3
0x1800685c2  mov     rcx, cs:?ghCommCtrlDLLInst@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800685c9  test    rcx, rcx
0x1800685cc  jz      short loc_1800685DF
0x1800685ce  call    cs:__imp_FreeLibrary
0x1800685d4  mov     cs:?ghCommCtrlDLLInst@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghCommCtrlDLLInst
0x1800685df  xor     eax, eax
0x1800685e1  jmp     short loc_1800685EE
0x1800685e3  mov     eax, 1
0x1800685e8  add     cs:?gulCommCtrlDLLRefCount@@3KA, eax; ulong gulCommCtrlDLLRefCount
0x1800685ee  add     rsp, 28h
0x1800685f2  retn
```
