# CspCreateFile

- ea: `0x18002d444`
- end: `0x18002d4fd`
- name: `CspCreateFile`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001a59c`
- `0x1800318e8`

## callees

- `0x180011fd8`
- `0x18002d444`
- `0x18002eb6c`
- `0x18002fd88`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CspCreateFile(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rax
  int v10; // r9d

  v8 = CspIncrementCacheFreshness((struct _CARD_STATE *)a1);
  if ( !v8 )
  {
    v9 = *(_QWORD *)(a1 + 8);
    if ( v9 )
    {
      return (*(unsigned int (__fastcall **)(_QWORD, const char *, __int64, _QWORD, int))(v9 + 240))(
               *(_QWORD *)(a1 + 8),
               "mscp",
               a3,
               a4,
               1);
    }
    else
    {
      v8 = 87;
      WppTraceIndent(v7, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
          v10,
          (__int64)"pCardState->pCardData");
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18002d444  mov     [rsp+arg_8], rdx
0x18002d449  push    rbx
0x18002d44a  push    rbp
0x18002d44b  push    rsi
0x18002d44c  push    rdi
0x18002d44d  sub     rsp, 38h
0x18002d451  xor     eax, eax
0x18002d453  mov     rbp, r8
0x18002d456  lea     r8, [rsp+58h+arg_8]
0x18002d45b  mov     dword ptr [rsp+58h+arg_8], eax
0x18002d45f  mov     esi, r9d
0x18002d462  mov     word ptr [rsp+58h+arg_8+4], ax
0x18002d467  mov     rdi, rcx
0x18002d46a  lea     edx, [rax+4]
0x18002d46d  call    CspIncrementCacheFreshness
0x18002d472  mov     ebx, eax
0x18002d474  test    eax, eax
0x18002d476  jnz     short loc_18002D4F2
0x18002d478  mov     rax, [rdi+8]
0x18002d47c  test    rax, rax
0x18002d47f  jnz     short loc_18002D4CC
0x18002d481  lea     edx, [rax+2]
0x18002d484  lea     ebx, [rax+57h]
0x18002d487  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d48c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d493  lea     rax, WPP_GLOBAL_Control
0x18002d49a  cmp     rcx, rax
0x18002d49d  jz      short loc_18002D4F2
0x18002d49f  test    byte ptr [rcx+1Ch], 1
0x18002d4a3  jz      short loc_18002D4F2
0x18002d4a5  cmp     byte ptr [rcx+19h], 2
0x18002d4a9  jb      short loc_18002D4F2
0x18002d4ab  mov     rcx, [rcx+10h]
0x18002d4af  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002d4b6  lea     edx, [rbx-3Dh]
0x18002d4b9  mov     [rsp+58h+var_38], rax
0x18002d4be  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002d4c5  call    WPP_SF_ss
0x18002d4ca  jmp     short loc_18002D4F2
0x18002d4cc  mov     rcx, rax
0x18002d4cf  mov     dword ptr [rsp+58h+var_38], 1
0x18002d4d7  mov     rax, [rax+0F0h]
0x18002d4de  lea     rdx, aMscp; "mscp"
0x18002d4e5  mov     r9d, esi
0x18002d4e8  mov     r8, rbp
0x18002d4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4f0  mov     ebx, eax
0x18002d4f2  mov     eax, ebx
0x18002d4f4  add     rsp, 38h
0x18002d4f8  pop     rdi
0x18002d4f9  pop     rsi
0x18002d4fa  pop     rbp
0x18002d4fb  pop     rbx
0x18002d4fc  retn
```
