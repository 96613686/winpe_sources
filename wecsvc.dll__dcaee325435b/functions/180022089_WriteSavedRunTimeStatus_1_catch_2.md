# _WriteSavedRunTimeStatus_::_1_::catch$2

- ea: `0x180022089`
- end: `0x1800220fc`
- name: `_WriteSavedRunTimeStatus_::_1_::catch$2`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800116c4`
- `0x180022089`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall WriteSavedRunTimeStatus_::_1_::catch_2(__int64 a1, __int64 a2)
{
  char v3; // al
  int v4; // r8d

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 72))(*(_QWORD *)(a2 + 72));
    WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v4, *(_QWORD *)(a2 + 64), *(_QWORD *)(a2 + 56), v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180022089  mov     [rsp+arg_8], rdx
0x18002208e  push    rbp
0x18002208f  sub     rsp, 30h
0x180022093  mov     rbp, rdx
0x180022096  lea     rcx, WPP_GLOBAL_Control
0x18002209d  mov     rax, cs:WPP_GLOBAL_Control
0x1800220a4  cmp     rax, rcx
0x1800220a7  jz      short loc_1800220EB
0x1800220a9  test    byte ptr [rax+1Ch], 10h
0x1800220ad  jz      short loc_1800220EB
0x1800220af  cmp     byte ptr [rax+19h], 2
0x1800220b3  jb      short loc_1800220EB
0x1800220b5  mov     rcx, [rbp+48h]
0x1800220b9  mov     rax, [rcx]
0x1800220bc  mov     rax, [rax]
0x1800220bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220c4  mov     edx, 12h
0x1800220c9  mov     [rsp+38h+var_10], eax
0x1800220cd  mov     rax, [rbp+38h]
0x1800220d1  mov     [rsp+38h+var_18], rax
0x1800220d6  mov     r9, [rbp+40h]
0x1800220da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220e1  mov     rcx, [rcx+10h]
0x1800220e5  call    WPP_SF_SSD
0x1800220ea  nop
0x1800220eb  mov     rax, 0
0x1800220f5  add     rsp, 30h
0x1800220f9  pop     rbp
0x1800220fa  retn
```
