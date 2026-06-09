# CSusMap<CUpdateSession::tagSEulaInfoKey,CUpdateSession::tagSEulaInfo,CUpdateSession::CSusEulaInfoKeyListOps,CUpdateSession::CSusArrayListItemOpSEulaInfo>::CMapEntryOps::Compare(CSusMap<CUpdateSession::tagSEulaInfoKey,CUpdateSession::tagSEulaInfo,CUpdateSession::CSusEulaInfoKeyListOps,CUpdateSession::CSusArrayListItemOpSEulaInfo>::_tagMapEntry const &,CSusMap<CUpdateSession::tagSEulaInfoKey,CUpdateSession::tagSEulaInfo,CUpdateSession::CSusEulaInfoKeyListOps,CUpdateSession::CSusArrayListItemOpSEulaInfo>::_tagMapEntry const &)

- ea: `0x18003df44`
- end: `0x18003e0f1`
- name: `?Compare@CMapEntryOps@?$CSusMap@UtagSEulaInfoKey@CUpdateSession@@UtagSEulaInfo@2@VCSusEulaInfoKeyListOps@2@VCSusArrayListItemOpSEulaInfo@2@@@SAHAEBU_tagMapEntry@2@0@Z`
- size: `429`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003ce5c`
- `0x18003d034`
- `0x18003d980`

## callees

- `0x18003df44`
- `0x18008306c`
- `0x18009b050`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18003df7f`
- `RPCRT4!UuidToStringW` at `0x18003dfb5`
- `RPCRT4!UuidToStringW` at `0x18003df7f`
- `RPCRT4!UuidToStringW` at `0x18003dfb5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003dfec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003e02a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003dfec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003e02a`

## pseudocode

```c
__int64 __fastcall CSusMap<CUpdateSession::tagSEulaInfoKey,CUpdateSession::tagSEulaInfo,CUpdateSession::CSusEulaInfoKeyListOps,CUpdateSession::CSusArrayListItemOpSEulaInfo>::CMapEntryOps::Compare(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rsi
  const UUID *v3; // rdi
  int v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  unsigned int v9; // eax
  int v10; // eax
  RPC_WSTR v11; // rcx
  int v12; // eax
  RPC_WSTR lpString2; // [rsp+30h] [rbp-20h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-18h] BYREF

  v2 = a1 + 24;
  v3 = (const UUID *)(a2 + 24);
  StringUuid = 0;
  lpString2 = 0;
  v4 = UuidToStringW((const UUID *)(a1 + 24), &StringUuid);
  if ( v4 >= 1 )
    v4 = (unsigned __int16)v4 | 0x80010000;
  if ( v4 < 0 )
    goto LABEL_31;
  v5 = UuidToStringW(v3, &lpString2);
  if ( v5 >= 1 )
    v5 = (unsigned __int16)v5 | 0x80010000;
  if ( v5 < 0 || (v6 = -1, (v7 = CompareStringW(0x7Fu, 1u, StringUuid, -1, lpString2, -1)) == 0) )
  {
LABEL_31:
    v11 = lpString2;
    goto LABEL_32;
  }
  v8 = v7 - 1;
  if ( !v8 )
    goto LABEL_26;
  if ( v8 == 2 )
  {
LABEL_20:
    v11 = lpString2;
LABEL_21:
    if ( v11 )
    {
      XPtrRpcStringFree(v11);
      lpString2 = 0;
    }
    if ( StringUuid )
      XPtrRpcStringFree(StringUuid);
    return 1;
  }
  v9 = *(_DWORD *)(v2 + 16);
  if ( v9 < v3[1].Data1 )
  {
LABEL_26:
    v11 = lpString2;
LABEL_27:
    if ( v11 )
    {
      XPtrRpcStringFree(v11);
      lpString2 = 0;
    }
    if ( StringUuid )
      XPtrRpcStringFree(StringUuid);
    return v6;
  }
  if ( v9 > v3[1].Data1 )
    goto LABEL_20;
  v10 = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v2 + 24), -1, *(PCNZWCH *)(v2 + 24), -1);
  v11 = lpString2;
  if ( v10 )
  {
    v12 = v10 - 1;
    if ( v12 )
    {
      if ( v12 != 2 )
      {
        if ( lpString2 )
        {
          XPtrRpcStringFree(lpString2);
          lpString2 = 0;
        }
        if ( StringUuid )
          XPtrRpcStringFree(StringUuid);
        return 0;
      }
      goto LABEL_21;
    }
    goto LABEL_27;
  }
LABEL_32:
  if ( v11 )
  {
    XPtrRpcStringFree(v11);
    lpString2 = 0;
  }
  if ( StringUuid )
    XPtrRpcStringFree(StringUuid);
  return (unsigned int)-2;
}

```

## disassembly

```asm
0x18003df44  mov     [rsp-28h+arg_10], rbx
0x18003df49  push    rbp
0x18003df4a  push    rsi
0x18003df4b  push    rdi
0x18003df4c  push    r14
0x18003df4e  push    r15
0x18003df50  mov     rbp, rsp
0x18003df53  sub     rsp, 50h
0x18003df57  mov     rax, cs:__security_cookie
0x18003df5e  xor     rax, rsp
0x18003df61  mov     [rbp+var_10], rax
0x18003df65  lea     rsi, [rcx+18h]
0x18003df69  xor     r14d, r14d
0x18003df6c  lea     rdi, [rdx+18h]
0x18003df70  mov     [rbp+StringUuid], r14
0x18003df74  mov     rcx, rsi; Uuid
0x18003df77  mov     [rbp+var_20], r14
0x18003df7b  lea     rdx, [rbp+StringUuid]; StringUuid
0x18003df7f  call    cs:__imp_UuidToStringW
0x18003df85  lea     r15d, [r14+1]
0x18003df89  mov     ebx, 80010000h
0x18003df8e  cmp     eax, r15d
0x18003df91  jl      short loc_18003DF98
0x18003df93  movzx   eax, ax
0x18003df96  or      eax, ebx
0x18003df98  test    eax, eax
0x18003df9a  js      loc_18003E0AA
0x18003dfa0  mov     rcx, [rbp+var_20]; void *
0x18003dfa4  test    rcx, rcx
0x18003dfa7  jz      short loc_18003DFAE
0x18003dfa9  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18003dfae  lea     rdx, [rbp+var_20]; StringUuid
0x18003dfb2  mov     rcx, rdi; Uuid
0x18003dfb5  call    cs:__imp_UuidToStringW
0x18003dfbb  cmp     eax, r15d
0x18003dfbe  jl      short loc_18003DFC5
0x18003dfc0  movzx   eax, ax
0x18003dfc3  or      eax, ebx
0x18003dfc5  test    eax, eax
0x18003dfc7  js      loc_18003E0AA
0x18003dfcd  mov     rax, [rbp+var_20]
0x18003dfd1  or      ebx, 0FFFFFFFFh
0x18003dfd4  mov     r8, [rbp+StringUuid]; lpString1
0x18003dfd8  mov     r9d, ebx; cchCount1
0x18003dfdb  mov     [rsp+50h+cchCount2], ebx; cchCount2
0x18003dfdf  mov     edx, r15d; dwCmpFlags
0x18003dfe2  mov     ecx, 7Fh; Locale
0x18003dfe7  mov     [rsp+50h+lpString2], rax; lpString2
0x18003dfec  call    cs:__imp_CompareStringW
0x18003dff2  test    eax, eax
0x18003dff4  jz      loc_18003E0AA
0x18003dffa  sub     eax, r15d
0x18003dffd  jz      loc_18003E088
0x18003e003  cmp     eax, 2
0x18003e006  jz      short loc_18003E063
0x18003e008  mov     eax, [rsi+10h]
0x18003e00b  cmp     eax, [rdi+10h]
0x18003e00e  jb      short loc_18003E088
0x18003e010  ja      short loc_18003E063
0x18003e012  mov     r8, [rsi+18h]; lpString1
0x18003e016  mov     r9d, ebx; cchCount1
0x18003e019  mov     [rsp+50h+cchCount2], ebx; cchCount2
0x18003e01d  mov     edx, r15d; dwCmpFlags
0x18003e020  mov     ecx, 7Fh; Locale
0x18003e025  mov     [rsp+50h+lpString2], r8; lpString2
0x18003e02a  call    cs:__imp_CompareStringW
0x18003e030  mov     rcx, [rbp+var_20]; void *
0x18003e034  test    eax, eax
0x18003e036  jz      short loc_18003E0AE
0x18003e038  sub     eax, r15d
0x18003e03b  jz      short loc_18003E08C
0x18003e03d  cmp     eax, 2
0x18003e040  jz      short loc_18003E067
0x18003e042  test    rcx, rcx
0x18003e045  jz      short loc_18003E050
0x18003e047  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18003e04c  mov     [rbp+var_20], r14
0x18003e050  mov     rcx, [rbp+StringUuid]; void *
0x18003e054  test    rcx, rcx
0x18003e057  jz      short loc_18003E05E
0x18003e059  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18003e05e  mov     ebx, r14d
0x18003e061  jmp     short loc_18003E0CF
0x18003e063  mov     rcx, [rbp+var_20]; void *
0x18003e067  test    rcx, rcx
0x18003e06a  jz      short loc_18003E075
0x18003e06c  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18003e071  mov     [rbp+var_20], r14
0x18003e075  mov     rcx, [rbp+StringUuid]; void *
0x18003e079  test    rcx, rcx
0x18003e07c  jz      short loc_18003E083
0x18003e07e  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18003e083  mov     ebx, r15d
0x18003e086  jmp     short loc_18003E0CF
0x18003e088  mov     rcx, [rbp+var_20]; void *
0x18003e08c  test    rcx, rcx
0x18003e08f  jz      short loc_18003E09A
0x18003e091  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18003e096  mov     [rbp+var_20], r14
0x18003e09a  mov     rcx, [rbp+StringUuid]; void *
0x18003e09e  test    rcx, rcx
0x18003e0a1  jz      short loc_18003E0CF
0x18003e0a3  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18003e0a8  jmp     short loc_18003E0CF
0x18003e0aa  mov     rcx, [rbp+var_20]; void *
0x18003e0ae  test    rcx, rcx
0x18003e0b1  jz      short loc_18003E0BC
0x18003e0b3  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18003e0b8  mov     [rbp+var_20], r14
0x18003e0bc  mov     rcx, [rbp+StringUuid]; void *
0x18003e0c0  test    rcx, rcx
0x18003e0c3  jz      short loc_18003E0CA
0x18003e0c5  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18003e0ca  mov     ebx, 0FFFFFFFEh
0x18003e0cf  mov     eax, ebx
0x18003e0d1  mov     rcx, [rbp+var_10]
0x18003e0d5  xor     rcx, rsp; StackCookie
0x18003e0d8  call    __security_check_cookie
0x18003e0dd  mov     rbx, [rsp+50h+arg_10]
0x18003e0e5  add     rsp, 50h
0x18003e0e9  pop     r15
0x18003e0eb  pop     r14
0x18003e0ed  pop     rdi
0x18003e0ee  pop     rsi
0x18003e0ef  pop     rbp
0x18003e0f0  retn
```
