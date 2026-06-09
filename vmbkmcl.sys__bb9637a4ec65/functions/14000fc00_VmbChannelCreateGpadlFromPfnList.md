# VmbChannelCreateGpadlFromPfnList

- ea: `0x14000fc00`
- end: `0x14000fc60`
- name: `VmbChannelCreateGpadlFromPfnList`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000fc00`
- `0x140011ed0`

## pseudocode

```c
__int64 __fastcall VmbChannelCreateGpadlFromPfnList(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 1728) )
    return 3221225711LL;
  if ( !a3 || !a4 )
    return 3221225713LL;
  result = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(a1 + 2432))(*(_QWORD *)(a1 + 2368), a3, a4, a5);
  if ( (int)result >= 0 )
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 2816));
  return result;
}

```

## disassembly

```asm
0x14000fc00  push    rbx
0x14000fc02  sub     rsp, 30h
0x14000fc06  cmp     byte ptr [rcx+6C0h], 0
0x14000fc0d  mov     r10d, r9d
0x14000fc10  mov     r11, r8
0x14000fc13  mov     rbx, rcx
0x14000fc16  jz      short loc_14000FC1F
0x14000fc18  mov     eax, 0C00000EFh
0x14000fc1d  jmp     short loc_14000FC59
0x14000fc1f  test    r11, r11
0x14000fc22  jz      short loc_14000FC54
0x14000fc24  test    r10d, r10d
0x14000fc27  jz      short loc_14000FC54
0x14000fc29  mov     rax, [rcx+980h]
0x14000fc30  mov     r8d, r10d
0x14000fc33  mov     rcx, [rcx+940h]
0x14000fc3a  mov     rdx, r11
0x14000fc3d  mov     r9, [rsp+38h+arg_20]
0x14000fc42  call    _guard_dispatch_icall
0x14000fc47  test    eax, eax
0x14000fc49  js      short loc_14000FC59
0x14000fc4b  lock inc dword ptr [rbx+0B00h]
0x14000fc52  jmp     short loc_14000FC59
0x14000fc54  mov     eax, 0C00000F1h
0x14000fc59  add     rsp, 30h
0x14000fc5d  pop     rbx
0x14000fc5e  retn
```
