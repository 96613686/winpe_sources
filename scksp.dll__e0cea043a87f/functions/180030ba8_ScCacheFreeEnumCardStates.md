# ScCacheFreeEnumCardStates

- ea: `0x180030ba8`
- end: `0x180030c7d`
- name: `ScCacheFreeEnumCardStates`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180034aa0`
- `0x180035d6c`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x18002ce34`
- `0x180030ba8`
- `0x1800374f4`

## pseudocode

```c
__int64 __fastcall ScCacheFreeEnumCardStates(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int i; // ebx
  unsigned int v7; // ebx
  __int64 v8; // rcx

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
  }
  for ( i = 0; i < a3; ++i )
    CardStateReleaseRef(**(_QWORD **)(a2 + 16LL * i + 8), 0);
  v7 = ScCacheFreeEnumItems(a1, a2, a3);
  WppTraceIndent(v8, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      (_DWORD)WPP_pszIndent,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180030ba8  push    rbx
0x180030baa  push    rbp
0x180030bab  push    rsi
0x180030bac  push    rdi
0x180030bad  push    r14
0x180030baf  sub     rsp, 30h
0x180030bb3  mov     rsi, rdx
0x180030bb6  mov     edi, r8d
0x180030bb9  xor     edx, edx
0x180030bbb  mov     rbp, rcx
0x180030bbe  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180030bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180030bca  lea     r14, WPP_GLOBAL_Control
0x180030bd1  cmp     rcx, r14
0x180030bd4  jz      short loc_180030BFE
0x180030bd6  test    byte ptr [rcx+1Ch], 2
0x180030bda  jz      short loc_180030BFE
0x180030bdc  cmp     byte ptr [rcx+19h], 5
0x180030be0  jb      short loc_180030BFE
0x180030be2  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030be9  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180030bf0  mov     rcx, [rcx+10h]
0x180030bf4  mov     edx, 25h ; '%'
0x180030bf9  call    WPP_SF_s
0x180030bfe  xor     ebx, ebx
0x180030c00  test    edi, edi
0x180030c02  jz      short loc_180030C1E
0x180030c04  mov     eax, ebx
0x180030c06  xor     edx, edx
0x180030c08  add     rax, rax
0x180030c0b  mov     rcx, [rsi+rax*8+8]
0x180030c10  mov     rcx, [rcx]
0x180030c13  call    CardStateReleaseRef
0x180030c18  inc     ebx
0x180030c1a  cmp     ebx, edi
0x180030c1c  jb      short loc_180030C04
0x180030c1e  mov     r8d, edi
0x180030c21  mov     rdx, rsi
0x180030c24  mov     rcx, rbp
0x180030c27  call    ScCacheFreeEnumItems
0x180030c2c  mov     edx, 1
0x180030c31  mov     ebx, eax
0x180030c33  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180030c38  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c3f  cmp     rcx, r14
0x180030c42  jz      short loc_180030C70
0x180030c44  test    byte ptr [rcx+1Ch], 2
0x180030c48  jz      short loc_180030C70
0x180030c4a  cmp     byte ptr [rcx+19h], 5
0x180030c4e  jb      short loc_180030C70
0x180030c50  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030c57  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180030c5e  mov     rcx, [rcx+10h]
0x180030c62  mov     edx, 26h ; '&'
0x180030c67  mov     [rsp+58h+var_38], ebx
0x180030c6b  call    WPP_SF_sd
0x180030c70  mov     eax, ebx
0x180030c72  add     rsp, 30h
0x180030c76  pop     r14
0x180030c78  pop     rdi
0x180030c79  pop     rsi
0x180030c7a  pop     rbp
0x180030c7b  pop     rbx
0x180030c7c  retn
```
