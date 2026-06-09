# PrintResourceString(ulong)

- ea: `0x140001ff8`
- end: `0x140002089`
- name: `?PrintResourceString@@YAXK@Z`
- size: `145`
- prototype: `void __fastcall(UINT uID)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140001840`
- `0x140001fa0`
- `0x14000215c`

## callees

- `0x140001a20`
- `0x140001ff8`
- `0x1400038b6`
- `0x1400038e0`

## import_xrefs

- `msvcrt!wprintf` at `0x140002052`
- `msvcrt!wprintf` at `0x14000205f`
- `msvcrt!wprintf` at `0x140002052`
- `msvcrt!wprintf` at `0x14000205f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x14000206a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x14000206a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x140002037`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x140002037`

## pseudocode

```c
void __fastcall PrintResourceString(UINT uID)
{
  LPWSTR v2[8]; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int16 v3[256]; // [rsp+60h] [rbp-218h] BYREF

  memset_0(v3, 0, sizeof(v3));
  STRU::STRU((STRU *)v2, v3, 0x100u);
  if ( (int)GetResourceString(uID, v2) >= 0 )
  {
    wprintf(v2[4]);
    wprintf(L"\r\n");
  }
  STRU::~STRU((STRU *)v2);
}

```

## disassembly

```asm
0x140001ff8  push    rbx
0x140001ffa  sub     rsp, 270h
0x140002001  mov     rax, cs:__security_cookie
0x140002008  xor     rax, rsp
0x14000200b  mov     [rsp+278h+var_18], rax
0x140002013  mov     ebx, ecx
0x140002015  xor     edx, edx; Val
0x140002017  lea     rcx, [rsp+278h+var_218]; void *
0x14000201c  mov     r8d, 200h; Size
0x140002022  call    memset_0
0x140002027  mov     r8d, 100h
0x14000202d  lea     rdx, [rsp+278h+var_218]
0x140002032  lea     rcx, [rsp+278h+var_258]
0x140002037  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x14000203d  lea     rdx, [rsp+278h+var_258]; struct STRU *
0x140002042  mov     ecx, ebx; uID
0x140002044  call    ?GetResourceString@@YAJKPEAVSTRU@@@Z; GetResourceString(ulong,STRU *)
0x140002049  test    eax, eax
0x14000204b  js      short loc_140002065
0x14000204d  mov     rcx, [rsp+278h+Format]; Format
0x140002052  call    cs:__imp_wprintf
0x140002058  lea     rcx, Format; "\r\n"
0x14000205f  call    cs:__imp_wprintf
0x140002065  lea     rcx, [rsp+278h+var_258]
0x14000206a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x140002070  mov     rcx, [rsp+278h+var_18]
0x140002078  xor     rcx, rsp; StackCookie
0x14000207b  call    __security_check_cookie
0x140002080  add     rsp, 270h
0x140002087  pop     rbx
0x140002088  retn
```
