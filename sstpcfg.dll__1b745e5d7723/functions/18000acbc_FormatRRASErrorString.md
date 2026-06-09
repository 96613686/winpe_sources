# FormatRRASErrorString

- ea: `0x18000acbc`
- end: `0x18000ad09`
- name: `FormatRRASErrorString`
- size: `77`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `32`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a6c`
- `0x180001d10`
- `0x180002518`
- `0x180002a00`
- `0x180003280`
- `0x180003510`
- `0x180003820`
- `0x180003aac`
- `0x180003e10`
- `0x180004000`
- `0x1800044a0`
- `0x180004c30`
- `0x180004f10`
- `0x180005370`
- `0x180005830`
- `0x180005ea0`
- `0x180006168`
- `0x180006380`
- `0x180006590`
- `0x180006794`
- `0x180006a20`
- `0x1800070f0`
- `0x180007450`
- `0x18000863c`
- `0x180008968`
- `0x180008be4`
- `0x180008e70`
- `0x180009330`
- `0x180009550`
- `0x180009720`
- `0x180009b34`
- `0x180009ee4`

## callees

- `0x18000acbc`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000ace7`
- `msvcrt!_vsnwprintf` at `0x18000ace7`

## pseudocode

```c
unsigned int FormatRRASErrorString(wchar_t *a1, const wchar_t *a2, ...)
{
  unsigned int result; // eax
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  result = _vsnwprintf(a1, 0x3FFu, a2, va);
  if ( result > 0x3FE )
  {
    result = 0;
    a1[1023] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000acbc  mov     rax, rsp
0x18000acbf  mov     [rax+10h], rdx
0x18000acc3  mov     [rax+18h], r8
0x18000acc7  mov     [rax+20h], r9
0x18000accb  push    rbx
0x18000accc  sub     rsp, 30h
0x18000acd0  mov     r8, rdx; Format
0x18000acd3  mov     qword ptr [rax-18h], 0
0x18000acdb  mov     edx, 3FFh; BufferCount
0x18000ace0  lea     r9, [rax+18h]; Args
0x18000ace4  mov     rbx, rcx
0x18000ace7  call    cs:__imp__vsnwprintf
0x18000aced  test    eax, eax
0x18000acef  js      short loc_18000ACFA
0x18000acf1  cmp     eax, 3FFh
0x18000acf6  ja      short loc_18000ACFA
0x18000acf8  jnz     short loc_18000AD03
0x18000acfa  xor     eax, eax
0x18000acfc  mov     [rbx+7FEh], ax
0x18000ad03  add     rsp, 30h
0x18000ad07  pop     rbx
0x18000ad08  retn
```
