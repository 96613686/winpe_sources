# PrintResourceString(ulong)

- ea: `0x140002118`
- end: `0x1400021c2`
- name: `?PrintResourceString@@YAXK@Z`
- size: `170`
- prototype: `void __fastcall(UINT uID)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140001840`
- `0x1400020c0`
- `0x1400022c4`

## callees

- `0x140001a78`
- `0x140002118`
- `0x140003c96`
- `0x140003cc0`

## import_xrefs

- `msvcrt!wprintf` at `0x140002178`
- `msvcrt!wprintf` at `0x14000218b`
- `msvcrt!wprintf` at `0x140002178`
- `msvcrt!wprintf` at `0x14000218b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x14000219c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x14000219c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x140002157`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x140002157`

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
0x140002118  push    rbx
0x14000211a  sub     rsp, 270h
0x140002121  mov     rax, cs:__security_cookie
0x140002128  xor     rax, rsp
0x14000212b  mov     [rsp+278h+var_18], rax
0x140002133  mov     ebx, ecx
0x140002135  xor     edx, edx; Val
0x140002137  lea     rcx, [rsp+278h+var_218]; void *
0x14000213c  mov     r8d, 200h; Size
0x140002142  call    memset_0
0x140002147  mov     r8d, 100h
0x14000214d  lea     rdx, [rsp+278h+var_218]
0x140002152  lea     rcx, [rsp+278h+var_258]
0x140002157  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x14000215e  nop     dword ptr [rax+rax+00h]
0x140002163  lea     rdx, [rsp+278h+var_258]; struct STRU *
0x140002168  mov     ecx, ebx; uID
0x14000216a  call    ?GetResourceString@@YAJKPEAVSTRU@@@Z; GetResourceString(ulong,STRU *)
0x14000216f  test    eax, eax
0x140002171  js      short loc_140002197
0x140002173  mov     rcx, [rsp+278h+Format]; Format
0x140002178  call    cs:__imp_wprintf
0x14000217f  nop     dword ptr [rax+rax+00h]
0x140002184  lea     rcx, Format; "\r\n"
0x14000218b  call    cs:__imp_wprintf
0x140002192  nop     dword ptr [rax+rax+00h]
0x140002197  lea     rcx, [rsp+278h+var_258]
0x14000219c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1400021a3  nop     dword ptr [rax+rax+00h]
0x1400021a8  mov     rcx, [rsp+278h+var_18]
0x1400021b0  xor     rcx, rsp; StackCookie
0x1400021b3  call    __security_check_cookie
0x1400021b8  add     rsp, 270h
0x1400021bf  pop     rbx
0x1400021c0  retn
```
