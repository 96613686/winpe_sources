# MatchesRequiredForOpenAuthorityKeySet(_CARD_STATE *,uchar *)

- ea: `0x1800342c4`
- end: `0x1800343ef`
- name: `?MatchesRequiredForOpenAuthorityKeySet@@YAKPEAU_CARD_STATE@@PEAE@Z`
- size: `299`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800339ac`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x1800342c4`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall MatchesRequiredForOpenAuthorityKeySet(struct _CARD_STATE *a1, unsigned __int8 *a2)
{
  PVOID v4; // rcx
  __int64 v5; // rax
  unsigned int v6; // ebx
  int v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = 0;
  WppTraceIndent((__int64)a1, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  v5 = *((_QWORD *)a1 + 1);
  if ( *(_DWORD *)(v5 + 512) )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, int *))(v5 + 520))(*((_QWORD *)a1 + 1), &v8);
    if ( v6 )
    {
      WppTraceIndent((__int64)v4, 2u);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          (_DWORD)WPP_pszIndent,
          v6);
      }
    }
    else
    {
      *a2 = v8;
    }
  }
  else
  {
    v6 = -2146435024;
  }
  WppTraceIndent((__int64)v4, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800342c4  mov     [rsp+arg_8], rbx
0x1800342c9  mov     [rsp+arg_10], rbp
0x1800342ce  push    rdi
0x1800342cf  sub     rsp, 30h
0x1800342d3  mov     rdi, rdx
0x1800342d6  mov     [rsp+38h+arg_0], 0
0x1800342de  xor     edx, edx
0x1800342e0  mov     rbx, rcx
0x1800342e3  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800342e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342ef  lea     rbp, WPP_GLOBAL_Control
0x1800342f6  cmp     rcx, rbp
0x1800342f9  jz      short loc_180034323
0x1800342fb  test    byte ptr [rcx+1Ch], 2
0x1800342ff  jz      short loc_180034323
0x180034301  cmp     byte ptr [rcx+19h], 5
0x180034305  jb      short loc_180034323
0x180034307  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003430e  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034315  mov     rcx, [rcx+10h]
0x180034319  mov     edx, 26h ; '&'
0x18003431e  call    WPP_SF_s
0x180034323  mov     rax, [rbx+8]
0x180034327  cmp     dword ptr [rax+200h], 1
0x18003432e  jnb     short loc_180034337
0x180034330  mov     ebx, 80100030h
0x180034335  jmp     short loc_18003439B
0x180034337  mov     rcx, rax
0x18003433a  lea     rdx, [rsp+38h+arg_0]
0x18003433f  mov     rax, [rax+208h]
0x180034346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003434b  mov     ebx, eax
0x18003434d  test    eax, eax
0x18003434f  jz      short loc_180034395
0x180034351  mov     edx, 2
0x180034356  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003435b  mov     rcx, cs:WPP_GLOBAL_Control
0x180034362  cmp     rcx, rbp
0x180034365  jz      short loc_18003439B
0x180034367  test    byte ptr [rcx+1Ch], 1
0x18003436b  jz      short loc_18003439B
0x18003436d  cmp     byte ptr [rcx+19h], 2
0x180034371  jb      short loc_18003439B
0x180034373  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003437a  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034381  mov     rcx, [rcx+10h]
0x180034385  mov     edx, 27h ; '''
0x18003438a  mov     [rsp+38h+var_18], ebx
0x18003438e  call    WPP_SF_sd
0x180034393  jmp     short loc_18003439B
0x180034395  mov     al, byte ptr [rsp+38h+arg_0]
0x180034399  mov     [rdi], al
0x18003439b  mov     edx, 1
0x1800343a0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800343a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800343ac  cmp     rcx, rbp
0x1800343af  jz      short loc_1800343DD
0x1800343b1  test    byte ptr [rcx+1Ch], 2
0x1800343b5  jz      short loc_1800343DD
0x1800343b7  cmp     byte ptr [rcx+19h], 5
0x1800343bb  jb      short loc_1800343DD
0x1800343bd  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800343c4  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800343cb  mov     rcx, [rcx+10h]
0x1800343cf  mov     edx, 28h ; '('
0x1800343d4  mov     [rsp+38h+var_18], ebx
0x1800343d8  call    WPP_SF_sd
0x1800343dd  mov     rbp, [rsp+38h+arg_10]
0x1800343e2  mov     eax, ebx
0x1800343e4  mov     rbx, [rsp+38h+arg_8]
0x1800343e9  add     rsp, 30h
0x1800343ed  pop     rdi
0x1800343ee  retn
```
