# TdxIncrementNotReadyInterfaceCount

- ea: `0x14000e4ec`
- end: `0x14000e544`
- name: `TdxIncrementNotReadyInterfaceCount`
- size: `88`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000db08`
- `0x14000e368`
- `0x140014c84`

## callees

- `0x14000e4ec`
- `0x14001521c`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall TdxIncrementNotReadyInterfaceCount(unsigned int a1, __int64 a2, __int64 a3)
{
  PDEVICE_OBJECT *result; // rax

  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    result = (PDEVICE_OBJECT *)WPP_SF_ddd(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 10,
                                 a3,
                                 a1,
                                 qword_14001E508,
                                 WPP_MAIN_CB.ActiveThreadCount);
  }
  _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.ActiveThreadCount);
  return result;
}

```

## disassembly

```asm
0x14000e4ec  sub     rsp, 38h
0x14000e4f0  mov     r9d, ecx
0x14000e4f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4fa  lea     rax, WPP_GLOBAL_Control
0x14000e501  cmp     rcx, rax
0x14000e504  jz      short loc_14000E537
0x14000e506  cmp     byte ptr [rcx+29h], 3
0x14000e50a  jb      short loc_14000E537
0x14000e50c  test    dword ptr [rcx+2Ch], 200h
0x14000e513  jz      short loc_14000E537
0x14000e515  mov     eax, cs:WPP_MAIN_CB.ActiveThreadCount
0x14000e51b  mov     edx, 0Ah
0x14000e520  mov     rcx, [rcx+18h]
0x14000e524  mov     [rsp+38h+var_10], eax
0x14000e528  mov     eax, dword ptr cs:qword_14001E508
0x14000e52e  mov     [rsp+38h+var_18], eax
0x14000e532  call    WPP_SF_ddd
0x14000e537  lock inc cs:WPP_MAIN_CB.ActiveThreadCount
0x14000e53e  add     rsp, 38h
0x14000e542  retn
```
