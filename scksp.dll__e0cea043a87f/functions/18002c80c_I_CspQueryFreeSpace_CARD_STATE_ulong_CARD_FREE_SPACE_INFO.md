# I_CspQueryFreeSpace(_CARD_STATE *,ulong,_CARD_FREE_SPACE_INFO *)

- ea: `0x18002c80c`
- end: `0x18002c996`
- name: `?I_CspQueryFreeSpace@@YAKPEAU_CARD_STATE@@KPEAU_CARD_FREE_SPACE_INFO@@@Z`
- size: `394`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned int, struct _CARD_FREE_SPACE_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002dc70`

## callees

- `0x18000d9d0`
- `0x180011fd8`
- `0x18002c80c`
- `0x18002cda8`
- `0x18002eb6c`
- `0x18002fb68`
- `0x180030378`
- `0x18003c240`
- `0x18003d010`

## string_xrefs

- `0x18002c855`: `Cached_FreeSpace`

## pseudocode

```c
__int64 __fastcall I_CspQueryFreeSpace(struct _CARD_STATE *a1, __int64 a2, struct _CARD_FREE_SPACE_INFO *a3)
{
  unsigned int CachedCardData; // eax
  __int64 v6; // rcx
  _OWORD *v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rax
  int v10; // r9d
  int v12; // [rsp+40h] [rbp-248h] BYREF
  _OWORD *v13; // [rsp+48h] [rbp-240h] BYREF
  unsigned __int16 v14[264]; // [rsp+50h] [rbp-238h] BYREF

  v13 = 0;
  v12 = 0;
  StringCbPrintfW(v14, 0x104u, L"%s", L"Cached_FreeSpace");
  CachedCardData = GetCachedCardData((__int64)a1, v14, 6u, 1u, &v13, &v12, 0);
  v7 = v13;
  v8 = CachedCardData;
  if ( CachedCardData )
  {
    if ( CachedCardData == 1168 )
    {
      v9 = *((_QWORD *)a1 + 1);
      if ( v9 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _CARD_FREE_SPACE_INFO *))(v9 + 288))(
               *((_QWORD *)a1 + 1),
               0,
               a3);
        if ( !v8 )
          v8 = AddCachedCardData((__int64)a1, v14, 6u, 1u, a3, 0x10u, 0);
      }
      else
      {
        v8 = 87;
        WppTraceIndent(v6, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
            v10,
            (__int64)"pCardState->pCardData");
        }
      }
    }
  }
  else if ( v12 == 16 )
  {
    *(_OWORD *)a3 = *v13;
  }
  else
  {
    v8 = -2146893820;
  }
  if ( v7 )
    CspFreeH(v7);
  return v8;
}

```

## disassembly

```asm
0x18002c80c  mov     [rsp+arg_8], rbx
0x18002c811  push    rbp
0x18002c812  push    rsi
0x18002c813  push    rdi
0x18002c814  sub     rsp, 270h
0x18002c81b  mov     rax, cs:__security_cookie
0x18002c822  xor     rax, rsp
0x18002c825  mov     [rsp+288h+var_28], rax
0x18002c82d  mov     rsi, r8
0x18002c830  mov     [rsp+288h+var_240], 0
0x18002c839  mov     rbp, rcx
0x18002c83c  mov     [rsp+288h+var_248], 0
0x18002c844  lea     r8, aS; "%s"
0x18002c84b  mov     edx, 104h; unsigned __int64
0x18002c850  lea     rcx, [rsp+288h+var_238]; unsigned __int16 *
0x18002c855  lea     r9, aCachedFreespac; "Cached_FreeSpace"
0x18002c85c  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c861  mov     r9d, 1
0x18002c867  mov     [rsp+288h+var_258], 0
0x18002c870  lea     rax, [rsp+288h+var_248]
0x18002c875  mov     rcx, rbp
0x18002c878  mov     [rsp+288h+var_260], rax
0x18002c87d  lea     rdx, [rsp+288h+var_238]
0x18002c882  lea     rax, [rsp+288h+var_240]
0x18002c887  lea     r8d, [r9+5]
0x18002c88b  mov     [rsp+288h+var_268], rax
0x18002c890  call    GetCachedCardData
0x18002c895  mov     rdi, [rsp+288h+var_240]
0x18002c89a  mov     ebx, eax
0x18002c89c  test    eax, eax
0x18002c89e  jz      loc_18002C94F
0x18002c8a4  cmp     eax, 490h
0x18002c8a9  jnz     loc_18002C964
0x18002c8af  mov     rax, [rbp+8]
0x18002c8b3  test    rax, rax
0x18002c8b6  jnz     short loc_18002C90B
0x18002c8b8  lea     edx, [rax+2]
0x18002c8bb  lea     ebx, [rax+57h]
0x18002c8be  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c8c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8ca  lea     rax, WPP_GLOBAL_Control
0x18002c8d1  cmp     rcx, rax
0x18002c8d4  jz      loc_18002C964
0x18002c8da  test    byte ptr [rcx+1Ch], 1
0x18002c8de  jz      loc_18002C964
0x18002c8e4  cmp     byte ptr [rcx+19h], 2
0x18002c8e8  jb      short loc_18002C964
0x18002c8ea  mov     rcx, [rcx+10h]
0x18002c8ee  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002c8f5  lea     edx, [rbx-38h]
0x18002c8f8  mov     [rsp+288h+var_268], rax
0x18002c8fd  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002c904  call    WPP_SF_ss
0x18002c909  jmp     short loc_18002C964
0x18002c90b  mov     rcx, rax
0x18002c90e  mov     r8, rsi
0x18002c911  mov     rax, [rax+120h]
0x18002c918  xor     edx, edx
0x18002c91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c91f  mov     ebx, eax
0x18002c921  test    eax, eax
0x18002c923  jnz     short loc_18002C964
0x18002c925  mov     dword ptr [rsp+288h+var_258], eax
0x18002c929  lea     r9d, [rax+1]
0x18002c92d  mov     dword ptr [rsp+288h+var_260], 10h
0x18002c935  lea     r8d, [rax+6]
0x18002c939  lea     rdx, [rsp+288h+var_238]
0x18002c93e  mov     [rsp+288h+var_268], rsi
0x18002c943  mov     rcx, rbp
0x18002c946  call    AddCachedCardData
0x18002c94b  mov     ebx, eax
0x18002c94d  jmp     short loc_18002C964
0x18002c94f  cmp     [rsp+288h+var_248], 10h
0x18002c954  jz      short loc_18002C95D
0x18002c956  mov     ebx, 80090004h
0x18002c95b  jmp     short loc_18002C964
0x18002c95d  movups  xmm0, xmmword ptr [rdi]
0x18002c960  movdqu  xmmword ptr [rsi], xmm0
0x18002c964  test    rdi, rdi
0x18002c967  jz      short loc_18002C971
0x18002c969  mov     rcx, rdi
0x18002c96c  call    CspFreeH
0x18002c971  mov     eax, ebx
0x18002c973  mov     rcx, [rsp+288h+var_28]
0x18002c97b  xor     rcx, rsp; StackCookie
0x18002c97e  call    __security_check_cookie
0x18002c983  mov     rbx, [rsp+288h+arg_8]
0x18002c98b  add     rsp, 270h
0x18002c992  pop     rdi
0x18002c993  pop     rsi
0x18002c994  pop     rbp
0x18002c995  retn
```
