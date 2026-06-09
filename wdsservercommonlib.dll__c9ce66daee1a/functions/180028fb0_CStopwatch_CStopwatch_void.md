# CStopwatch::CStopwatch(void)

- ea: `0x180028fb0`
- end: `0x180029009`
- name: `??0CStopwatch@@QEAA@XZ`
- size: `89`
- prototype: `CStopwatch *__fastcall(CStopwatch *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180027900`
- `0x180028fb0`

## import_xrefs

- `KERNEL32!QueryPerformanceFrequency` at `0x180028fc9`
- `KERNEL32!QueryPerformanceFrequency` at `0x180028fc9`

## string_xrefs

- `0x180028feb`: `onecore\base\eco\wds\wdslib\common\src\stopwatch.cpp`

## pseudocode

```c
CStopwatch *__fastcall CStopwatch::CStopwatch(CStopwatch *this)
{
  LARGE_INTEGER Frequency; // [rsp+40h] [rbp+8h] BYREF

  Frequency.QuadPart = 0;
  if ( !QueryPerformanceFrequency(&Frequency) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\stopwatch.cpp",
      0x35u,
      "QueryPerformanceFrequency(&liFrequency)",
      1,
      0);
  *(LARGE_INTEGER *)this = Frequency;
  return this;
}

```

## disassembly

```asm
0x180028fb0  push    rbx
0x180028fb2  sub     rsp, 30h
0x180028fb6  and     dword ptr [rsp+38h+Frequency], 0
0x180028fbb  mov     rbx, rcx
0x180028fbe  xor     eax, eax
0x180028fc0  lea     rcx, [rsp+38h+Frequency]; lpFrequency
0x180028fc5  mov     dword ptr [rsp+38h+Frequency+4], eax
0x180028fc9  call    cs:__imp_QueryPerformanceFrequency
0x180028fd0  nop     dword ptr [rax+rax+00h]
0x180028fd5  test    eax, eax
0x180028fd7  jnz     short loc_180028FF7
0x180028fd9  and     [rsp+38h+var_18], eax
0x180028fdd  lea     r9d, [rax+1]; int
0x180028fe1  lea     r8, aQueryperforman; "QueryPerformanceFrequency(&liFrequency)"
0x180028fe8  lea     edx, [rax+35h]; unsigned int
0x180028feb  lea     rcx, aOnecoreBaseEco_22; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028ff2  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180028ff7  mov     rax, qword ptr [rsp+38h+Frequency]
0x180028ffc  mov     [rbx], rax
0x180028fff  mov     rax, rbx
0x180029002  add     rsp, 30h
0x180029006  pop     rbx
0x180029007  retn
```
