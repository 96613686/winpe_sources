# CspCreateContainer

- ea: `0x18002d368`
- end: `0x18002d43d`
- name: `CspCreateContainer`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016adc`

## callees

- `0x180011fd8`
- `0x18002d368`
- `0x18002eb6c`
- `0x18002fd88`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CspCreateContainer(
        __int64 a1,
        char a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  unsigned int v10; // ebx
  int v11; // r9d
  __int64 v12; // rdx
  int v14; // [rsp+60h] [rbp+8h] BYREF
  __int16 v15; // [rsp+64h] [rbp+Ch]

  if ( *(_QWORD *)(a1 + 8) )
  {
    v14 = 0;
    v15 = 0;
    v10 = CspIncrementCacheFreshness((struct _CARD_STATE *)a1, 2, (__int64)&v14);
    if ( !v10 )
    {
      v12 = a5;
      LOBYTE(v12) = a2;
      return (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, unsigned int, __int64))(*(_QWORD *)(a1 + 8) + 144LL))(
               *(_QWORD *)(a1 + 8),
               v12,
               a3,
               a4,
               a5,
               a6);
    }
  }
  else
  {
    v10 = 87;
    WppTraceIndent(a1, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
        v11,
        (__int64)"pCardState->pCardData");
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18002d368  mov     [rsp+arg_8], rbx
0x18002d36d  mov     [rsp+arg_10], rbp
0x18002d372  push    rsi
0x18002d373  push    rdi
0x18002d374  push    r14
0x18002d376  sub     rsp, 40h
0x18002d37a  cmp     qword ptr [rcx+8], 0
0x18002d37f  mov     r14b, dl
0x18002d382  mov     edx, 2
0x18002d387  mov     esi, r9d
0x18002d38a  mov     ebp, r8d
0x18002d38d  mov     rdi, rcx
0x18002d390  jnz     short loc_18002D3DA
0x18002d392  lea     ebx, [rdx+55h]
0x18002d395  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3a1  lea     rax, WPP_GLOBAL_Control
0x18002d3a8  cmp     rcx, rax
0x18002d3ab  jz      short loc_18002D428
0x18002d3ad  test    byte ptr [rcx+1Ch], 1
0x18002d3b1  jz      short loc_18002D428
0x18002d3b3  cmp     byte ptr [rcx+19h], 2
0x18002d3b7  jb      short loc_18002D428
0x18002d3b9  mov     rcx, [rcx+10h]
0x18002d3bd  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002d3c4  lea     edx, [rbx-4Ah]
0x18002d3c7  mov     [rsp+58h+var_38], rax
0x18002d3cc  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002d3d3  call    WPP_SF_ss
0x18002d3d8  jmp     short loc_18002D428
0x18002d3da  xor     eax, eax
0x18002d3dc  lea     r8, [rsp+58h+arg_0]
0x18002d3e1  mov     [rsp+58h+arg_0], eax
0x18002d3e5  mov     [rsp+58h+arg_4], ax
0x18002d3ea  call    CspIncrementCacheFreshness
0x18002d3ef  mov     ebx, eax
0x18002d3f1  test    eax, eax
0x18002d3f3  jnz     short loc_18002D428
0x18002d3f5  mov     rdx, [rsp+58h+arg_28]
0x18002d3fd  mov     r9d, esi
0x18002d400  mov     rcx, [rdi+8]
0x18002d404  mov     r8d, ebp
0x18002d407  mov     [rsp+58h+var_30], rdx
0x18002d40c  mov     edx, [rsp+58h+arg_20]
0x18002d413  mov     dword ptr [rsp+58h+var_38], edx
0x18002d417  mov     dl, r14b
0x18002d41a  mov     rax, [rcx+90h]
0x18002d421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d426  mov     ebx, eax
0x18002d428  mov     rbp, [rsp+58h+arg_10]
0x18002d42d  mov     eax, ebx
0x18002d42f  mov     rbx, [rsp+58h+arg_8]
0x18002d434  add     rsp, 40h
0x18002d438  pop     r14
0x18002d43a  pop     rdi
0x18002d43b  pop     rsi
0x18002d43c  retn
```
