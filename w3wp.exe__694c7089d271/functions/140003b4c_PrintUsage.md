# PrintUsage

- ea: `0x140003b4c`
- end: `0x140003bf9`
- name: `PrintUsage`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140002fa4`

## callees

- `0x140001a78`
- `0x1400021c8`
- `0x140003b4c`
- `0x140003c96`
- `0x140003cc0`

## import_xrefs

- `msvcrt!wprintf` at `0x140003bc2`
- `msvcrt!wprintf` at `0x140003bc2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x140003bd3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x140003bd3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x140003b8c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x140003b8c`

## pseudocode

```c
void __fastcall PrintUsage(__int64 a1)
{
  LPWSTR v2[8]; // [rsp+20h] [rbp-858h] BYREF
  unsigned __int16 v3[1024]; // [rsp+60h] [rbp-818h] BYREF

  memset_0(v3, 0, sizeof(v3));
  STRU::STRU((STRU *)v2, v3, 0x400u);
  SetConsoleLocale();
  if ( (int)GetResourceString(0x61A9u, v2) >= 0 )
    wprintf(v2[4], a1, L"u", L"u");
  STRU::~STRU((STRU *)v2);
}

```

## disassembly

```asm
0x140003b4c  push    rbx
0x140003b4e  sub     rsp, 870h
0x140003b55  mov     rax, cs:__security_cookie
0x140003b5c  xor     rax, rsp
0x140003b5f  mov     [rsp+878h+var_18], rax
0x140003b67  mov     rbx, rcx
0x140003b6a  xor     edx, edx; Val
0x140003b6c  lea     rcx, [rsp+878h+var_818]; void *
0x140003b71  mov     r8d, 800h; Size
0x140003b77  call    memset_0
0x140003b7c  mov     r8d, 400h
0x140003b82  lea     rdx, [rsp+878h+var_818]
0x140003b87  lea     rcx, [rsp+878h+var_858]
0x140003b8c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x140003b93  nop     dword ptr [rax+rax+00h]
0x140003b98  call    ?SetConsoleLocale@@YAXXZ; SetConsoleLocale(void)
0x140003b9d  lea     rdx, [rsp+878h+var_858]; struct STRU *
0x140003ba2  mov     ecx, 61A9h; uID
0x140003ba7  call    ?GetResourceString@@YAJKPEAVSTRU@@@Z; GetResourceString(ulong,STRU *)
0x140003bac  test    eax, eax
0x140003bae  js      short loc_140003BCE
0x140003bb0  mov     rcx, [rsp+878h+Format]; Format
0x140003bb5  lea     r8, aU; "u"
0x140003bbc  mov     r9, r8
0x140003bbf  mov     rdx, rbx
0x140003bc2  call    cs:__imp_wprintf
0x140003bc9  nop     dword ptr [rax+rax+00h]
0x140003bce  lea     rcx, [rsp+878h+var_858]
0x140003bd3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x140003bda  nop     dword ptr [rax+rax+00h]
0x140003bdf  mov     rcx, [rsp+878h+var_18]
0x140003be7  xor     rcx, rsp; StackCookie
0x140003bea  call    __security_check_cookie
0x140003bef  add     rsp, 870h
0x140003bf6  pop     rbx
0x140003bf7  retn
```
