# TmpInsertTxTransactionManager

- ea: `0x14000cbf8`
- end: `0x14000cc59`
- name: `TmpInsertTxTransactionManager`
- size: `97`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400109a4`
- `0x140016f40`
- `0x14001ab8c`
- `0x14001ca60`

## callees

- `0x14000cbf8`
- `0x14001b444`

## pseudocode

```c
__int64 __fastcall TmpInsertTxTransactionManager(char *Object, __int64 a2)
{
  int v5; // ecx

  if ( *((_DWORD *)Object + 16) == 5 )
    return 3222863954LL;
  v5 = TmpNamespaceInsert((PRTL_AVL_TABLE)(Object + 176), Object, a2);
  if ( v5 >= 0 )
  {
    *(_QWORD *)(a2 + 512) = Object;
    v5 = 0;
    if ( (*((_DWORD *)Object + 32) & 0x10) != 0 )
      _InterlockedOr((volatile signed __int32 *)(a2 + 196), 0x10000u);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000cbf8  mov     [rsp+arg_0], rbx
0x14000cbfd  push    rdi
0x14000cbfe  sub     rsp, 20h
0x14000cc02  cmp     dword ptr [rcx+40h], 5
0x14000cc06  mov     rbx, rdx
0x14000cc09  mov     rdi, rcx
0x14000cc0c  jnz     short loc_14000CC15
0x14000cc0e  mov     eax, 0C0190052h
0x14000cc13  jmp     short loc_14000CC4D
0x14000cc15  add     rcx, 0B0h; Table
0x14000cc1c  mov     r8, rbx
0x14000cc1f  mov     rdx, rdi; Object
0x14000cc22  call    TmpNamespaceInsert
0x14000cc27  mov     ecx, eax
0x14000cc29  test    eax, eax
0x14000cc2b  js      short loc_14000CC4B
0x14000cc2d  mov     [rbx+200h], rdi
0x14000cc34  xor     ecx, ecx
0x14000cc36  mov     eax, [rdi+80h]
0x14000cc3c  test    al, 10h
0x14000cc3e  jz      short loc_14000CC4B
0x14000cc40  lock or dword ptr [rbx+0C4h], 10000h
0x14000cc4b  mov     eax, ecx
0x14000cc4d  mov     rbx, [rsp+28h+arg_0]
0x14000cc52  add     rsp, 20h
0x14000cc56  pop     rdi
0x14000cc57  retn
```
