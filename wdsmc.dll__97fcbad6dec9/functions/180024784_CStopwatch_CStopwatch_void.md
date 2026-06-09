# CStopwatch::CStopwatch(void)

- ea: `0x180024784`
- end: `0x1800247ce`
- name: `??0CStopwatch@@QEAA@XZ`
- size: `74`
- prototype: `CStopwatch *__fastcall(CStopwatch *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003e18`
- `0x1800116d0`
- `0x180014370`
- `0x180016b90`

## callees

- `0x1800227d4`
- `0x180024784`

## import_xrefs

- `KERNEL32!QueryPerformanceFrequency` at `0x180024799`
- `KERNEL32!QueryPerformanceFrequency` at `0x180024799`

## string_xrefs

- `0x1800247b1`: `onecore\base\eco\wds\wdslib\common\src\stopwatch.cpp`

## pseudocode

```c
CStopwatch *__fastcall CStopwatch::CStopwatch(CStopwatch *this)
{
  int v2; // r9d
  LARGE_INTEGER Frequency; // [rsp+40h] [rbp+8h] BYREF

  Frequency.QuadPart = 0;
  if ( !QueryPerformanceFrequency(&Frequency) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\stopwatch.cpp",
      0x35u,
      "QueryPerformanceFrequency(&liFrequency)",
      v2,
      0);
  *(LARGE_INTEGER *)this = Frequency;
  return this;
}

```

## disassembly

```asm
0x180024784  push    rbx
0x180024786  sub     rsp, 30h
0x18002478a  mov     rbx, rcx
0x18002478d  xor     eax, eax
0x18002478f  lea     rcx, [rsp+38h+Frequency]; lpFrequency
0x180024794  mov     qword ptr [rsp+38h+Frequency], rax
0x180024799  call    cs:__imp_QueryPerformanceFrequency
0x18002479f  test    eax, eax
0x1800247a1  jnz     short loc_1800247BD
0x1800247a3  and     [rsp+38h+var_18], eax
0x1800247a7  lea     r8, aQueryperforman; "QueryPerformanceFrequency(&liFrequency)"
0x1800247ae  lea     edx, [rax+35h]; unsigned int
0x1800247b1  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800247b8  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800247bd  mov     rax, qword ptr [rsp+38h+Frequency]
0x1800247c2  mov     [rbx], rax
0x1800247c5  mov     rax, rbx
0x1800247c8  add     rsp, 30h
0x1800247cc  pop     rbx
0x1800247cd  retn
```
