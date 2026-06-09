# CStopwatch::CurrentMs(void)

- ea: `0x180029010`
- end: `0x180029085`
- name: `?CurrentMs@CStopwatch@@QEAA_KXZ`
- size: `117`
- prototype: `unsigned __int64 __fastcall(CStopwatch *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180027900`
- `0x180029010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180029029`
- `KERNEL32!QueryPerformanceCounter` at `0x180029029`

## string_xrefs

- `0x18002904b`: `onecore\base\eco\wds\wdslib\common\src\stopwatch.cpp`

## pseudocode

```c
LONGLONG __fastcall CStopwatch::CurrentMs(CStopwatch *this)
{
  __int64 v2; // rdx
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+8h] BYREF

  PerformanceCount.QuadPart = 0;
  if ( !QueryPerformanceCounter(&PerformanceCount) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\stopwatch.cpp",
      0x6Du,
      "QueryPerformanceCounter(&liTimeStamp)",
      1,
      0);
  v2 = (*(unsigned __int64 *)this * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
  return PerformanceCount.QuadPart / ((v2 + ((unsigned __int64)(*(_QWORD *)this - v2) >> 1)) >> 9);
}

```

## disassembly

```asm
0x180029010  push    rbx
0x180029012  sub     rsp, 30h
0x180029016  and     dword ptr [rsp+38h+PerformanceCount], 0
0x18002901b  mov     rbx, rcx
0x18002901e  xor     eax, eax
0x180029020  lea     rcx, [rsp+38h+PerformanceCount]; lpPerformanceCount
0x180029025  mov     dword ptr [rsp+38h+PerformanceCount+4], eax
0x180029029  call    cs:__imp_QueryPerformanceCounter
0x180029030  nop     dword ptr [rax+rax+00h]
0x180029035  test    eax, eax
0x180029037  jnz     short loc_180029057
0x180029039  and     [rsp+38h+var_18], eax
0x18002903d  lea     r9d, [rax+1]; int
0x180029041  lea     r8, aQueryperforman_0; "QueryPerformanceCounter(&liTimeStamp)"
0x180029048  lea     edx, [rax+6Dh]; unsigned int
0x18002904b  lea     rcx, aOnecoreBaseEco_22; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180029052  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180029057  mov     rcx, [rbx]
0x18002905a  mov     rax, 624DD2F1A9FBE77h
0x180029064  mul     rcx
0x180029067  mov     rax, qword ptr [rsp+38h+PerformanceCount]
0x18002906c  sub     rcx, rdx
0x18002906f  shr     rcx, 1
0x180029072  add     rcx, rdx
0x180029075  xor     edx, edx
0x180029077  shr     rcx, 9
0x18002907b  div     rcx
0x18002907e  add     rsp, 30h
0x180029082  pop     rbx
0x180029083  retn
```
