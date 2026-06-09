# CStopwatch::CurrentMs(void)

- ea: `0x1800247d4`
- end: `0x18002483a`
- name: `?CurrentMs@CStopwatch@@QEAA_KXZ`
- size: `102`
- prototype: `unsigned __int64 __fastcall(CStopwatch *__hidden this)`
- caller_count: `43`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003e18`
- `0x18000b560`
- `0x18000c8c0`
- `0x18000cb74`
- `0x18000cfa0`
- `0x18000d060`
- `0x18000de34`
- `0x18000f688`
- `0x18000fa3c`
- `0x1800100f8`
- `0x18001050c`
- `0x180010c44`
- `0x1800112f4`
- `0x180011530`
- `0x1800122a4`
- `0x180012530`
- `0x1800126a8`
- `0x180012a60`
- `0x1800132cc`
- `0x180013620`
- `0x1800148b4`
- `0x1800154b4`
- `0x180015c34`
- `0x180016548`
- `0x180016e70`
- `0x18001754c`
- `0x1800175b4`
- `0x180017924`
- `0x180017a50`
- `0x180017b50`
- `0x180017bd0`
- `0x180017c60`
- `0x180017dc0`
- `0x18001a784`
- `0x18001d560`
- `0x18001d730`
- `0x18001d8a8`
- `0x18001dab0`
- `0x18001dd2c`
- `0x18001df44`
- `0x18001e16c`
- `0x18001e398`
- `0x18001e73c`

## callees

- `0x1800227d4`
- `0x1800247d4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800247e9`
- `KERNEL32!QueryPerformanceCounter` at `0x1800247e9`

## string_xrefs

- `0x180024801`: `onecore\base\eco\wds\wdslib\common\src\stopwatch.cpp`

## pseudocode

```c
LONGLONG __fastcall CStopwatch::CurrentMs(CStopwatch *this)
{
  int v2; // r9d
  __int64 v3; // rdx
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+8h] BYREF

  PerformanceCount.QuadPart = 0;
  if ( !QueryPerformanceCounter(&PerformanceCount) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\stopwatch.cpp",
      0x6Du,
      "QueryPerformanceCounter(&liTimeStamp)",
      v2,
      0);
  v3 = (*(unsigned __int64 *)this * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
  return PerformanceCount.QuadPart / ((v3 + ((unsigned __int64)(*(_QWORD *)this - v3) >> 1)) >> 9);
}

```

## disassembly

```asm
0x1800247d4  push    rbx
0x1800247d6  sub     rsp, 30h
0x1800247da  mov     rbx, rcx
0x1800247dd  xor     eax, eax
0x1800247df  lea     rcx, [rsp+38h+PerformanceCount]; lpPerformanceCount
0x1800247e4  mov     qword ptr [rsp+38h+PerformanceCount], rax
0x1800247e9  call    cs:__imp_QueryPerformanceCounter
0x1800247ef  test    eax, eax
0x1800247f1  jnz     short loc_18002480D
0x1800247f3  and     [rsp+38h+var_18], eax
0x1800247f7  lea     r8, aQueryperforman_0; "QueryPerformanceCounter(&liTimeStamp)"
0x1800247fe  lea     edx, [rax+6Dh]; unsigned int
0x180024801  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024808  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18002480d  mov     rcx, [rbx]
0x180024810  mov     rax, 624DD2F1A9FBE77h
0x18002481a  mul     rcx
0x18002481d  mov     rax, qword ptr [rsp+38h+PerformanceCount]
0x180024822  sub     rcx, rdx
0x180024825  shr     rcx, 1
0x180024828  add     rcx, rdx
0x18002482b  xor     edx, edx
0x18002482d  shr     rcx, 9
0x180024831  div     rcx
0x180024834  add     rsp, 30h
0x180024838  pop     rbx
0x180024839  retn
```
