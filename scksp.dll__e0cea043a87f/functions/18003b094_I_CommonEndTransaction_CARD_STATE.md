# I_CommonEndTransaction(_CARD_STATE *)

- ea: `0x18003b094`
- end: `0x18003b267`
- name: `?I_CommonEndTransaction@@YAKPEAU_CARD_STATE@@@Z`
- size: `467`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003b920`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x18002eb6c`
- `0x18003b094`
- `0x18003d010`

## import_xrefs

- `WinSCard!SCardReleaseContext` at `0x18003b1e2`
- `WinSCard!SCardReleaseContext` at `0x18003b1e2`
- `WinSCard!SCardDisconnect` at `0x18003b1c8`
- `WinSCard!SCardDisconnect` at `0x18003b1c8`
- `WinSCard!SCardEndTransaction` at `0x18003b1a8`
- `WinSCard!SCardEndTransaction` at `0x18003b1a8`

## pseudocode

```c
__int64 __fastcall I_CommonEndTransaction(struct _CARD_STATE *a1)
{
  DWORD v2; // edi
  PVOID v3; // rcx
  __int64 v4; // rax
  unsigned int v5; // edi
  int v6; // r9d
  PVOID v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  LONG v10; // eax

  v2 = *((_DWORD *)a1 + 178) != 0;
  WppTraceIndent((__int64)a1, 0);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids, WPP_pszIndent);
  }
  v4 = *((_QWORD *)a1 + 1);
  if ( !v4 )
  {
    v5 = 87;
    WppTraceIndent((__int64)v3, 2u);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
        v6,
        (__int64)"pCardState->pCardData");
    }
    goto LABEL_20;
  }
  v8 = *((unsigned int *)a1 + 178);
  if ( (_DWORD)v8 )
  {
    if ( *(_DWORD *)v4 >= 6u )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(v4 + 376))(*((_QWORD *)a1 + 1), v8, 0);
      goto LABEL_15;
    }
    if ( *(_QWORD *)(v4 + 200) )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(v4 + 200))(*((_QWORD *)a1 + 1), L"user", 0);
LABEL_15:
      if ( !v9 )
        v2 = 0;
    }
  }
  v10 = SCardEndTransaction(*(_QWORD *)(*((_QWORD *)a1 + 1) + 104LL), v2);
  v5 = v10;
  if ( v10 && v10 != -2146434968 )
  {
    SCardDisconnect(*(_QWORD *)(*((_QWORD *)a1 + 1) + 104LL), 1u);
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 104LL) = 0;
    SCardReleaseContext(*(_QWORD *)(*((_QWORD *)a1 + 1) + 96LL));
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 96LL) = 0;
  }
LABEL_20:
  *((_DWORD *)a1 + 178) = 0;
  *((_DWORD *)a1 + 148) = 0;
  *((_DWORD *)a1 + 155) = 0;
  WppTraceIndent((__int64)v7, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
      (_DWORD)WPP_pszIndent,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18003b094  mov     [rsp+arg_0], rbx
0x18003b099  mov     [rsp+arg_8], rdi
0x18003b09e  push    r12
0x18003b0a0  sub     rsp, 30h
0x18003b0a4  xor     edi, edi
0x18003b0a6  mov     rbx, rcx
0x18003b0a9  cmp     [rcx+2C8h], edi
0x18003b0af  setnz   dil
0x18003b0b3  xor     edx, edx
0x18003b0b5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003b0ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b0c1  lea     r12, WPP_GLOBAL_Control
0x18003b0c8  cmp     rcx, r12
0x18003b0cb  jz      short loc_18003B0F5
0x18003b0cd  test    byte ptr [rcx+1Ch], 2
0x18003b0d1  jz      short loc_18003B0F5
0x18003b0d3  cmp     byte ptr [rcx+19h], 5
0x18003b0d7  jb      short loc_18003B0F5
0x18003b0d9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003b0e0  lea     r8, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18003b0e7  mov     rcx, [rcx+10h]
0x18003b0eb  mov     edx, 0Dh
0x18003b0f0  call    WPP_SF_s
0x18003b0f5  mov     rax, [rbx+8]
0x18003b0f9  test    rax, rax
0x18003b0fc  jnz     short loc_18003B151
0x18003b0fe  lea     edx, [rax+2]
0x18003b101  lea     edi, [rax+57h]
0x18003b104  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003b109  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b110  cmp     rcx, r12
0x18003b113  jz      loc_18003B1F4
0x18003b119  test    byte ptr [rcx+1Ch], 1
0x18003b11d  jz      loc_18003B1F4
0x18003b123  cmp     byte ptr [rcx+19h], 2
0x18003b127  jb      loc_18003B1F4
0x18003b12d  mov     rcx, [rcx+10h]
0x18003b131  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18003b138  lea     edx, [rdi-49h]
0x18003b13b  mov     [rsp+38h+var_18], rax
0x18003b140  lea     r8, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18003b147  call    WPP_SF_ss
0x18003b14c  jmp     loc_18003B1F4
0x18003b151  mov     edx, [rbx+2C8h]
0x18003b157  test    edx, edx
0x18003b159  jz      short loc_18003B19E
0x18003b15b  cmp     dword ptr [rax], 6
0x18003b15e  jb      short loc_18003B174
0x18003b160  mov     rcx, rax
0x18003b163  xor     r8d, r8d
0x18003b166  mov     rax, [rax+178h]
0x18003b16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b172  jmp     short loc_18003B195
0x18003b174  mov     r9, [rax+0C8h]
0x18003b17b  test    r9, r9
0x18003b17e  jz      short loc_18003B19E
0x18003b180  mov     rcx, rax
0x18003b183  lea     rdx, aUser; "user"
0x18003b18a  mov     rax, r9
0x18003b18d  xor     r8d, r8d
0x18003b190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b195  mov     ecx, eax
0x18003b197  xor     eax, eax
0x18003b199  test    ecx, ecx
0x18003b19b  cmovz   edi, eax
0x18003b19e  mov     rcx, [rbx+8]
0x18003b1a2  mov     edx, edi; dwDisposition
0x18003b1a4  mov     rcx, [rcx+68h]; hCard
0x18003b1a8  call    cs:__imp_SCardEndTransaction
0x18003b1ae  mov     edi, eax
0x18003b1b0  test    eax, eax
0x18003b1b2  jz      short loc_18003B1F4
0x18003b1b4  cmp     eax, 80100068h
0x18003b1b9  jz      short loc_18003B1F4
0x18003b1bb  mov     rcx, [rbx+8]
0x18003b1bf  mov     edx, 1; dwDisposition
0x18003b1c4  mov     rcx, [rcx+68h]; hCard
0x18003b1c8  call    cs:__imp_SCardDisconnect
0x18003b1ce  mov     rcx, [rbx+8]
0x18003b1d2  mov     qword ptr [rcx+68h], 0
0x18003b1da  mov     rcx, [rbx+8]
0x18003b1de  mov     rcx, [rcx+60h]; hContext
0x18003b1e2  call    cs:__imp_SCardReleaseContext
0x18003b1e8  mov     rax, [rbx+8]
0x18003b1ec  mov     qword ptr [rax+60h], 0
0x18003b1f4  mov     edx, 1
0x18003b1f9  mov     dword ptr [rbx+2C8h], 0
0x18003b203  mov     dword ptr [rbx+250h], 0
0x18003b20d  mov     dword ptr [rbx+26Ch], 0
0x18003b217  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003b21c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b223  cmp     rcx, r12
0x18003b226  jz      short loc_18003B254
0x18003b228  test    byte ptr [rcx+1Ch], 2
0x18003b22c  jz      short loc_18003B254
0x18003b22e  cmp     byte ptr [rcx+19h], 5
0x18003b232  jb      short loc_18003B254
0x18003b234  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003b23b  lea     r8, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18003b242  mov     rcx, [rcx+10h]
0x18003b246  mov     edx, 0Fh
0x18003b24b  mov     dword ptr [rsp+38h+var_18], edi
0x18003b24f  call    WPP_SF_sd
0x18003b254  mov     rbx, [rsp+38h+arg_0]
0x18003b259  mov     eax, edi
0x18003b25b  mov     rdi, [rsp+38h+arg_8]
0x18003b260  add     rsp, 30h
0x18003b264  pop     r12
0x18003b266  retn
```
