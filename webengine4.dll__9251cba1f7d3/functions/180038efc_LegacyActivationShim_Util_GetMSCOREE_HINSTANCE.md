# LegacyActivationShim::Util::GetMSCOREE(HINSTANCE__ * *)

- ea: `0x180038efc`
- end: `0x180038f79`
- name: `?GetMSCOREE@Util@LegacyActivationShim@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(LegacyActivationShim::Util *__hidden this, HINSTANCE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003703c`
- `0x180038a60`

## callees

- `0x180038efc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180038f26`
- `KERNEL32!GetLastError` at `0x180038f26`
- `KERNEL32!FreeLibrary` at `0x180038f61`
- `KERNEL32!FreeLibrary` at `0x180038f61`
- `KERNEL32!LoadLibraryW` at `0x180038f18`
- `KERNEL32!LoadLibraryW` at `0x180038f18`

## string_xrefs

- `0x180038f11`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall LegacyActivationShim::Util::GetMSCOREE(LegacyActivationShim::Util *this, HINSTANCE *a2)
{
  HINSTANCE v2; // rax
  HMODULE LibraryW; // rax
  signed int LastError; // ecx
  __int64 result; // rax

  v2 = LegacyActivationShim::Util::g_hModMscoree;
  if ( LegacyActivationShim::Util::g_hModMscoree )
    goto LABEL_9;
  LibraryW = LoadLibraryW(L"mscoree.dll");
  if ( LibraryW )
  {
    if ( _InterlockedCompareExchange64(
           (volatile signed __int64 *)&LegacyActivationShim::Util::g_hModMscoree,
           (signed __int64)LibraryW,
           0) )
    {
      FreeLibrary(LibraryW);
      v2 = LegacyActivationShim::Util::g_hModMscoree;
    }
    else
    {
      v2 = LegacyActivationShim::Util::g_hModMscoree;
      LegacyActivationShim::Util::g_hModMscoreeHolder = LegacyActivationShim::Util::g_hModMscoree;
      byte_18008EDE8 = 1;
    }
LABEL_9:
    *(_QWORD *)this = v2;
    return 0;
  }
  LastError = GetLastError();
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x180038efc  push    rbx
0x180038efe  sub     rsp, 20h
0x180038f02  mov     rax, cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x180038f09  mov     rbx, rcx
0x180038f0c  test    rax, rax
0x180038f0f  jnz     short loc_180038F6E
0x180038f11  lea     rcx, aMscoreeDll_0; "mscoree.dll"
0x180038f18  call    cs:__imp_LoadLibraryW
0x180038f1e  mov     rcx, rax; hLibModule
0x180038f21  test    rax, rax
0x180038f24  jnz     short loc_180038F3D
0x180038f26  call    cs:__imp_GetLastError
0x180038f2c  mov     ecx, eax
0x180038f2e  movzx   eax, ax
0x180038f31  or      eax, 80070000h
0x180038f36  test    ecx, ecx
0x180038f38  cmovle  eax, ecx
0x180038f3b  jmp     short loc_180038F73
0x180038f3d  xor     eax, eax
0x180038f3f  lock cmpxchg cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x180038f48  jnz     short loc_180038F61
0x180038f4a  mov     rax, cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x180038f51  mov     cs:?g_hModMscoreeHolder@Util@LegacyActivationShim@@3VZeroInitGlobalHMODULEHolder@12@A, rax; LegacyActivationShim::Util::ZeroInitGlobalHMODULEHolder LegacyActivationShim::Util::g_hModMscoreeHolder
0x180038f58  mov     cs:byte_18008EDE8, 1
0x180038f5f  jmp     short loc_180038F6E
0x180038f61  call    cs:__imp_FreeLibrary
0x180038f67  mov     rax, cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x180038f6e  mov     [rbx], rax
0x180038f71  xor     eax, eax
0x180038f73  add     rsp, 20h
0x180038f77  pop     rbx
0x180038f78  retn
```
