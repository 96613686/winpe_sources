# TmpCreateOrOpenLogTransactionManager

- ea: `0x14001ebb8`
- end: `0x14001ebf7`
- name: `TmpCreateOrOpenLogTransactionManager`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140014c50`

## callees

- `0x14001ebb8`
- `0x14001ec00`

## pseudocode

```c
__int64 __fastcall TmpCreateOrOpenLogTransactionManager(__int64 a1)
{
  __int64 result; // rax

  *(_DWORD *)(a1 + 64) = 2;
  result = TmpCreateLogFile(a1);
  if ( *(_DWORD *)(a1 + 64) == 2 && (int)result < 0 )
    *(_DWORD *)(a1 + 64) = 4;
  return result;
}

```

## disassembly

```asm
0x14001ebb8  mov     [rsp+arg_0], rcx
0x14001ebbd  push    rbx
0x14001ebbe  sub     rsp, 30h
0x14001ebc2  mov     rbx, rcx
0x14001ebc5  mov     [rsp+38h+var_18], 0
0x14001ebcd  mov     dword ptr [rcx+40h], 2
0x14001ebd4  call    TmpCreateLogFile
0x14001ebd9  mov     [rsp+38h+var_18], eax
0x14001ebdd  cmp     dword ptr [rbx+40h], 2
0x14001ebe1  jnz     short loc_14001EBE7
0x14001ebe3  test    eax, eax
0x14001ebe5  js      short loc_14001EBEE
0x14001ebe7  add     rsp, 30h
0x14001ebeb  pop     rbx
0x14001ebec  retn
0x14001ebee  mov     dword ptr [rbx+40h], 4
0x14001ebf5  jmp     short loc_14001EBE7
0x140021839  push    rbp
0x14002183b  sub     rsp, 20h
0x14002183f  mov     rbp, rdx
0x140021842  mov     rax, [rbp+40h]
0x140021846  cmp     dword ptr [rax+40h], 2
0x14002184a  jnz     short loc_140021859
0x14002184c  cmp     dword ptr [rbp+20h], 0
0x140021850  jge     short loc_140021859
0x140021852  mov     dword ptr [rax+40h], 4
0x140021859  add     rsp, 20h
0x14002185d  pop     rbp
0x14002185e  retn
```
