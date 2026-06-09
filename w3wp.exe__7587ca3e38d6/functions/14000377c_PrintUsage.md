# PrintUsage

- ea: `0x14000377c`
- end: `0x140003816`
- name: `PrintUsage`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140002c58`

## callees

- `0x140001a20`
- `0x140002090`
- `0x14000377c`
- `0x1400038b6`
- `0x1400038e0`

## import_xrefs

- `msvcrt!wprintf` at `0x1400037ec`
- `msvcrt!wprintf` at `0x1400037ec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1400037f7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1400037f7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1400037bc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1400037bc`

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
0x14000377c  push    rbx
0x14000377e  sub     rsp, 870h
0x140003785  mov     rax, cs:__security_cookie
0x14000378c  xor     rax, rsp
0x14000378f  mov     [rsp+878h+var_18], rax
0x140003797  mov     rbx, rcx
0x14000379a  xor     edx, edx; Val
0x14000379c  lea     rcx, [rsp+878h+var_818]; void *
0x1400037a1  mov     r8d, 800h; Size
0x1400037a7  call    memset_0
0x1400037ac  mov     r8d, 400h
0x1400037b2  lea     rdx, [rsp+878h+var_818]
0x1400037b7  lea     rcx, [rsp+878h+var_858]
0x1400037bc  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1400037c2  call    ?SetConsoleLocale@@YAXXZ; SetConsoleLocale(void)
0x1400037c7  lea     rdx, [rsp+878h+var_858]; struct STRU *
0x1400037cc  mov     ecx, 61A9h; uID
0x1400037d1  call    ?GetResourceString@@YAJKPEAVSTRU@@@Z; GetResourceString(ulong,STRU *)
0x1400037d6  test    eax, eax
0x1400037d8  js      short loc_1400037F2
0x1400037da  mov     rcx, [rsp+878h+Format]; Format
0x1400037df  lea     r8, aU; "u"
0x1400037e6  mov     r9, r8
0x1400037e9  mov     rdx, rbx
0x1400037ec  call    cs:__imp_wprintf
0x1400037f2  lea     rcx, [rsp+878h+var_858]
0x1400037f7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1400037fd  mov     rcx, [rsp+878h+var_18]
0x140003805  xor     rcx, rsp; StackCookie
0x140003808  call    __security_check_cookie
0x14000380d  add     rsp, 870h
0x140003814  pop     rbx
0x140003815  retn
```
