# MatchesRequiredForDeleteKeySetOnDefaultContainer(_CARD_STATE *,uchar *,ushort * *,int *)

- ea: `0x180033f5c`
- end: `0x1800340e0`
- name: `?MatchesRequiredForDeleteKeySetOnDefaultContainer@@YAKPEAU_CARD_STATE@@PEAEPEAPEAGPEAH@Z`
- size: `388`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned __int8 *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800339ac`

## callees

- `0x180009e82`
- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x180013ce4`
- `0x18002b140`
- `0x18002f034`
- `0x180033f5c`
- `0x18003c240`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180034005`
- `msvcrt!wcsnlen` at `0x180034005`

## pseudocode

```c
__int64 __fastcall MatchesRequiredForDeleteKeySetOnDefaultContainer(
        struct _CARD_STATE *a1,
        unsigned __int8 *a2,
        unsigned __int16 **a3,
        int *a4)
{
  __int64 v8; // rcx
  PVOID v9; // rcx
  unsigned int DefaultContainer; // ebx
  unsigned __int64 v11; // rdi
  unsigned __int16 *v12; // rax
  __int64 v13; // rcx
  wchar_t Source[48]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(Source, 0, 0x56u);
  WppTraceIndent(v8, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  DefaultContainer = ContainerMapGetDefaultContainer(a1, Source, a2);
  if ( DefaultContainer )
  {
    DefaultContainer = -2146435024;
  }
  else
  {
    v11 = (unsigned int)wcsnlen(Source, 0x28u) + 1;
    v12 = (unsigned __int16 *)MIDL_user_allocate(2 * v11);
    *a3 = v12;
    if ( v12 )
    {
      StringCchCopyNW(v12, v11, Source, 0x28u);
      *a4 = 1;
    }
    else
    {
      WppTraceIndent(v13, 2u);
      DefaultContainer = 8;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  WppTraceIndent((__int64)v9, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      DefaultContainer);
  }
  return DefaultContainer;
}

```

## disassembly

```asm
0x180033f5c  push    rbx
0x180033f5e  push    rsi
0x180033f5f  push    rdi
0x180033f60  push    r13
0x180033f62  push    r14
0x180033f64  sub     rsp, 0A0h
0x180033f6b  mov     rax, cs:__security_cookie
0x180033f72  xor     rax, rsp
0x180033f75  mov     [rsp+0C8h+var_38], rax
0x180033f7d  mov     rdi, rdx
0x180033f80  mov     r14, r8
0x180033f83  xor     edx, edx; Val
0x180033f85  mov     rbx, rcx
0x180033f88  lea     rcx, [rsp+0C8h+Source]; void *
0x180033f8d  mov     rsi, r9
0x180033f90  lea     r8d, [rdx+56h]; Size
0x180033f94  call    memset_0
0x180033f99  xor     edx, edx
0x180033f9b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180033fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fa7  lea     r13, WPP_GLOBAL_Control
0x180033fae  cmp     rcx, r13
0x180033fb1  jz      short loc_180033FDB
0x180033fb3  test    byte ptr [rcx+1Ch], 2
0x180033fb7  jz      short loc_180033FDB
0x180033fb9  cmp     byte ptr [rcx+19h], 5
0x180033fbd  jb      short loc_180033FDB
0x180033fbf  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180033fc6  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180033fcd  mov     rcx, [rcx+10h]
0x180033fd1  mov     edx, 2Bh ; '+'
0x180033fd6  call    WPP_SF_s
0x180033fdb  mov     r8, rdi
0x180033fde  lea     rdx, [rsp+0C8h+Source]
0x180033fe3  mov     rcx, rbx
0x180033fe6  call    ContainerMapGetDefaultContainer
0x180033feb  mov     ebx, eax
0x180033fed  test    eax, eax
0x180033fef  jz      short loc_180033FFB
0x180033ff1  mov     ebx, 80100030h
0x180033ff6  jmp     loc_18003407D
0x180033ffb  mov     edx, 28h ; '('; MaxCount
0x180034000  lea     rcx, [rsp+0C8h+Source]; Source
0x180034005  call    cs:__imp_wcsnlen
0x18003400b  inc     eax
0x18003400d  mov     edi, eax
0x18003400f  lea     rcx, [rax+rax]; size
0x180034013  call    MIDL_user_allocate
0x180034018  mov     [r14], rax
0x18003401b  test    rax, rax
0x18003401e  jnz     short loc_180034061
0x180034020  lea     edx, [rax+2]
0x180034023  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034028  mov     ebx, 8
0x18003402d  mov     rcx, cs:WPP_GLOBAL_Control
0x180034034  cmp     rcx, r13
0x180034037  jz      short loc_18003407D
0x180034039  test    byte ptr [rcx+1Ch], 1
0x18003403d  jz      short loc_18003407D
0x18003403f  cmp     byte ptr [rcx+19h], 2
0x180034043  jb      short loc_18003407D
0x180034045  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003404c  lea     edx, [rbx+24h]
0x18003404f  mov     rcx, [rcx+10h]
0x180034053  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18003405a  call    WPP_SF_s
0x18003405f  jmp     short loc_18003407D
0x180034061  mov     r9d, 28h ; '('; unsigned __int64
0x180034067  lea     r8, [rsp+0C8h+Source]; unsigned __int16 *
0x18003406c  mov     rdx, rdi; unsigned __int64
0x18003406f  mov     rcx, rax; unsigned __int16 *
0x180034072  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180034077  mov     dword ptr [rsi], 1
0x18003407d  mov     edx, 1
0x180034082  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034087  mov     rcx, cs:WPP_GLOBAL_Control
0x18003408e  cmp     rcx, r13
0x180034091  jz      short loc_1800340BF
0x180034093  test    byte ptr [rcx+1Ch], 2
0x180034097  jz      short loc_1800340BF
0x180034099  cmp     byte ptr [rcx+19h], 5
0x18003409d  jb      short loc_1800340BF
0x18003409f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800340a6  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800340ad  mov     rcx, [rcx+10h]
0x1800340b1  mov     edx, 2Dh ; '-'
0x1800340b6  mov     [rsp+0C8h+var_A8], ebx
0x1800340ba  call    WPP_SF_sd
0x1800340bf  mov     eax, ebx
0x1800340c1  mov     rcx, [rsp+0C8h+var_38]
0x1800340c9  xor     rcx, rsp; StackCookie
0x1800340cc  call    __security_check_cookie
0x1800340d1  add     rsp, 0A0h
0x1800340d8  pop     r14
0x1800340da  pop     r13
0x1800340dc  pop     rdi
0x1800340dd  pop     rsi
0x1800340de  pop     rbx
0x1800340df  retn
```
