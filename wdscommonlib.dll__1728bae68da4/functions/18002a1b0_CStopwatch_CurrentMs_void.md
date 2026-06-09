# CStopwatch::CurrentMs(void)

- ea: `0x18002a1b0`
- end: `0x18002a225`
- name: `?CurrentMs@CStopwatch@@QEAA_KXZ`
- size: `117`
- prototype: `unsigned __int64 __fastcall(CStopwatch *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180028a50`
- `0x18002a1b0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18002a1c9`
- `KERNEL32!QueryPerformanceCounter` at `0x18002a1c9`

## string_xrefs

- `0x18002a1eb`: `onecore\base\eco\wds\wdslib\common\src\stopwatch.cpp`

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
0x18002a1b0  push    rbx
0x18002a1b2  sub     rsp, 30h
0x18002a1b6  and     dword ptr [rsp+38h+PerformanceCount], 0
0x18002a1bb  mov     rbx, rcx
0x18002a1be  xor     eax, eax
0x18002a1c0  lea     rcx, [rsp+38h+PerformanceCount]; lpPerformanceCount
0x18002a1c5  mov     dword ptr [rsp+38h+PerformanceCount+4], eax
0x18002a1c9  call    cs:__imp_QueryPerformanceCounter
0x18002a1d0  nop     dword ptr [rax+rax+00h]
0x18002a1d5  test    eax, eax
0x18002a1d7  jnz     short loc_18002A1F7
0x18002a1d9  and     [rsp+38h+var_18], eax
0x18002a1dd  lea     r9d, [rax+1]; int
0x18002a1e1  lea     r8, aQueryperforman_0; "QueryPerformanceCounter(&liTimeStamp)"
0x18002a1e8  lea     edx, [rax+6Dh]; unsigned int
0x18002a1eb  lea     rcx, aOnecoreBaseEco_21; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002a1f2  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18002a1f7  mov     rcx, [rbx]
0x18002a1fa  mov     rax, 624DD2F1A9FBE77h
0x18002a204  mul     rcx
0x18002a207  mov     rax, qword ptr [rsp+38h+PerformanceCount]
0x18002a20c  sub     rcx, rdx
0x18002a20f  shr     rcx, 1
0x18002a212  add     rcx, rdx
0x18002a215  xor     edx, edx
0x18002a217  shr     rcx, 9
0x18002a21b  div     rcx
0x18002a21e  add     rsp, 30h
0x18002a222  pop     rbx
0x18002a223  retn
```
