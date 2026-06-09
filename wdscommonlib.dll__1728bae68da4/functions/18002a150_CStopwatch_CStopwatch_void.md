# CStopwatch::CStopwatch(void)

- ea: `0x18002a150`
- end: `0x18002a1a9`
- name: `??0CStopwatch@@QEAA@XZ`
- size: `89`
- prototype: `CStopwatch *__fastcall(CStopwatch *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180028a50`
- `0x18002a150`

## import_xrefs

- `KERNEL32!QueryPerformanceFrequency` at `0x18002a169`
- `KERNEL32!QueryPerformanceFrequency` at `0x18002a169`

## string_xrefs

- `0x18002a18b`: `onecore\base\eco\wds\wdslib\common\src\stopwatch.cpp`

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
0x18002a150  push    rbx
0x18002a152  sub     rsp, 30h
0x18002a156  and     dword ptr [rsp+38h+Frequency], 0
0x18002a15b  mov     rbx, rcx
0x18002a15e  xor     eax, eax
0x18002a160  lea     rcx, [rsp+38h+Frequency]; lpFrequency
0x18002a165  mov     dword ptr [rsp+38h+Frequency+4], eax
0x18002a169  call    cs:__imp_QueryPerformanceFrequency
0x18002a170  nop     dword ptr [rax+rax+00h]
0x18002a175  test    eax, eax
0x18002a177  jnz     short loc_18002A197
0x18002a179  and     [rsp+38h+var_18], eax
0x18002a17d  lea     r9d, [rax+1]; int
0x18002a181  lea     r8, aQueryperforman; "QueryPerformanceFrequency(&liFrequency)"
0x18002a188  lea     edx, [rax+35h]; unsigned int
0x18002a18b  lea     rcx, aOnecoreBaseEco_21; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002a192  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18002a197  mov     rax, qword ptr [rsp+38h+Frequency]
0x18002a19c  mov     [rbx], rax
0x18002a19f  mov     rax, rbx
0x18002a1a2  add     rsp, 30h
0x18002a1a6  pop     rbx
0x18002a1a7  retn
```
