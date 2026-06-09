# SHSkipJunction

- ea: `0x1800078e0`
- end: `0x180007ab6`
- name: `SHSkipJunction`
- size: `470`
- prototype: `BOOL __stdcall(IBindCtx *pbc, const CLSID *pclsid)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1800078e0`
- `0x180012550`
- `0x180037010`

## import_xrefs

- `SHCORE!__imp_IUnknown_GetClassID` at `0x18000794c`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x180007a2e`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x18000794c`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x180007a2e`

## string_xrefs

- `0x180007925`: `Skip Binding CLSID`
- `0x180007971`: `SkipBindingCLSIDArray`

## pseudocode

```c
BOOL __stdcall SHSkipJunction(IBindCtx *pbc, const CLSID *pclsid)
{
  BOOL v2; // ebx
  struct IBindCtxVtbl *lpVtbl; // rax
  struct IBindCtxVtbl *v7; // rax
  int v8; // edi
  unsigned int v9; // edi
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+38h] [rbp-40h] BYREF
  __int64 v14; // [rsp+40h] [rbp-38h] BYREF
  __int128 v15; // [rsp+48h] [rbp-30h] BYREF
  __int128 v16; // [rsp+58h] [rbp-20h] BYREF

  v2 = 0;
  if ( !pbc )
    return v2;
  lpVtbl = pbc->lpVtbl;
  v13 = 0;
  if ( ((int (__fastcall *)(IBindCtx *, const wchar_t *, __int64 *))lpVtbl->GetObjectParam)(
         pbc,
         L"Skip Binding CLSID",
         &v13) < 0 )
  {
LABEL_6:
    v7 = pbc->lpVtbl;
    v14 = 0;
    v12 = 0;
    if ( ((int (__fastcall *)(IBindCtx *, const wchar_t *, __int64 *))v7->GetObjectParam)(
           pbc,
           L"SkipBindingCLSIDArray",
           &v12) >= 0 )
    {
      v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
             v12,
             &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
             &v14);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v8 >= 0 )
      {
        LODWORD(v12) = 0;
        if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 24LL))(v14, &v12) >= 0 )
        {
          v9 = 0;
          do
          {
            if ( v9 >= (unsigned int)v12 )
              break;
            *(_QWORD *)&v15 = 0;
            if ( (*(int (__fastcall **)(__int64, _QWORD, GUID *, __int128 *))(*(_QWORD *)v14 + 32LL))(
                   v14,
                   v9,
                   &GUID_00000000_0000_0000_c000_000000000046,
                   &v15) >= 0 )
            {
              v16 = 0;
              if ( (int)IUnknown_GetClassID(v15, &v16) < 0 )
                goto LABEL_13;
              v11 = v16 - *(_QWORD *)&pclsid->Data1;
              if ( (_QWORD)v16 == *(_QWORD *)&pclsid->Data1 )
                v11 = *((_QWORD *)&v16 + 1) - *(_QWORD *)pclsid->Data4;
              if ( v11 )
LABEL_13:
                v2 = 0;
              else
                v2 = 1;
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 16LL))(v15);
            }
            ++v9;
          }
          while ( !v2 );
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    return v2;
  }
  v15 = 0;
  if ( (int)IUnknown_GetClassID(v13, &v15) < 0 )
    goto LABEL_5;
  v10 = v15 - *(_QWORD *)&pclsid->Data1;
  if ( (_QWORD)v15 == *(_QWORD *)&pclsid->Data1 )
    v10 = *((_QWORD *)&v15 + 1) - *(_QWORD *)pclsid->Data4;
  if ( v10 )
  {
LABEL_5:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_6;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return 1;
}

```

## disassembly

```asm
0x1800078e0  push    rbp
0x1800078e2  push    rbx
0x1800078e3  push    rsi
0x1800078e4  push    rdi
0x1800078e5  mov     rbp, rsp
0x1800078e8  sub     rsp, 78h
0x1800078ec  mov     rax, cs:__security_cookie
0x1800078f3  xor     rax, rsp
0x1800078f6  mov     [rbp+var_10], rax
0x1800078fa  xor     ebx, ebx
0x1800078fc  mov     rsi, rdx
0x1800078ff  mov     rdi, rcx
0x180007902  test    rcx, rcx
0x180007905  jnz     short loc_18000791E
0x180007907  mov     eax, ebx
0x180007909  mov     rcx, [rbp+var_10]
0x18000790d  xor     rcx, rsp; StackCookie
0x180007910  call    __security_check_cookie
0x180007915  add     rsp, 78h
0x180007919  pop     rdi
0x18000791a  pop     rsi
0x18000791b  pop     rbx
0x18000791c  pop     rbp
0x18000791d  retn
0x18000791e  mov     rax, [rcx]
0x180007921  lea     r8, [rbp+var_40]
0x180007925  lea     rdx, aSkipBindingCls; "Skip Binding CLSID"
0x18000792c  mov     [rbp+var_40], rbx
0x180007930  mov     rax, [rax+50h]
0x180007934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007939  test    eax, eax
0x18000793b  js      short loc_18000796A
0x18000793d  mov     rcx, [rbp+var_40]
0x180007941  lea     rdx, [rbp+var_30]
0x180007945  xorps   xmm0, xmm0
0x180007948  movups  [rbp+var_30], xmm0
0x18000794c  call    cs:__imp_IUnknown_GetClassID
0x180007952  test    eax, eax
0x180007954  jns     loc_180007A65
0x18000795a  mov     rcx, [rbp+var_40]
0x18000795e  mov     rax, [rcx]
0x180007961  mov     rax, [rax+10h]
0x180007965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000796a  mov     rax, [rdi]
0x18000796d  lea     r8, [rbp+var_48]
0x180007971  lea     rdx, aSkipbindingcls; "SkipBindingCLSIDArray"
0x180007978  mov     [rbp+var_38], 0
0x180007980  mov     rcx, rdi
0x180007983  mov     [rbp+var_48], 0
0x18000798b  mov     rax, [rax+50h]
0x18000798f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007994  test    eax, eax
0x180007996  js      loc_180007907
0x18000799c  mov     rcx, [rbp+var_48]
0x1800079a0  lea     r8, [rbp+var_38]
0x1800079a4  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x1800079ab  mov     rax, [rcx]
0x1800079ae  mov     rax, [rax]
0x1800079b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079b6  mov     rcx, [rbp+var_48]
0x1800079ba  mov     edi, eax
0x1800079bc  mov     rax, [rcx]
0x1800079bf  mov     rax, [rax+10h]
0x1800079c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079c8  test    edi, edi
0x1800079ca  js      loc_180007907
0x1800079d0  mov     rcx, [rbp+var_38]
0x1800079d4  lea     rdx, [rbp+var_48]
0x1800079d8  mov     dword ptr [rbp+var_48], 0
0x1800079df  mov     rax, [rcx]
0x1800079e2  mov     rax, [rax+18h]
0x1800079e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079eb  test    eax, eax
0x1800079ed  js      short loc_180007A50
0x1800079ef  xor     edi, edi
0x1800079f1  cmp     edi, dword ptr [rbp+var_48]
0x1800079f4  jnb     short loc_180007A50
0x1800079f6  mov     rcx, [rbp+var_38]
0x1800079fa  lea     r9, [rbp+var_30]
0x1800079fe  mov     qword ptr [rbp+var_30], 0
0x180007a06  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x180007a0d  mov     edx, edi
0x180007a0f  mov     rax, [rcx]
0x180007a12  mov     rax, [rax+20h]
0x180007a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a1b  test    eax, eax
0x180007a1d  js      short loc_180007A4A
0x180007a1f  mov     rcx, qword ptr [rbp+var_30]
0x180007a23  lea     rdx, [rbp+var_20]
0x180007a27  xorps   xmm0, xmm0
0x180007a2a  movups  [rbp+var_20], xmm0
0x180007a2e  call    cs:__imp_IUnknown_GetClassID
0x180007a34  test    eax, eax
0x180007a36  jns     short loc_180007A99
0x180007a38  xor     ebx, ebx
0x180007a3a  mov     rcx, qword ptr [rbp+var_30]
0x180007a3e  mov     rax, [rcx]
0x180007a41  mov     rax, [rax+10h]
0x180007a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a4a  inc     edi
0x180007a4c  test    ebx, ebx
0x180007a4e  jz      short loc_1800079F1
0x180007a50  mov     rcx, [rbp+var_38]
0x180007a54  mov     rdx, [rcx]
0x180007a57  mov     rax, [rdx+10h]
0x180007a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a60  jmp     loc_180007907
0x180007a65  mov     rax, qword ptr [rbp+var_30]
0x180007a69  sub     rax, [rsi]
0x180007a6c  jnz     short loc_180007A76
0x180007a6e  mov     rax, qword ptr [rbp+var_30+8]
0x180007a72  sub     rax, [rsi+8]
0x180007a76  test    rax, rax
0x180007a79  jnz     loc_18000795A
0x180007a7f  mov     rcx, [rbp+var_40]
0x180007a83  mov     rax, [rcx]
0x180007a86  mov     rax, [rax+10h]
0x180007a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a8f  mov     eax, 1
0x180007a94  jmp     loc_180007909
0x180007a99  mov     rax, qword ptr [rbp+var_20]
0x180007a9d  sub     rax, [rsi]
0x180007aa0  jnz     short loc_180007AAA
0x180007aa2  mov     rax, qword ptr [rbp+var_20+8]
0x180007aa6  sub     rax, [rsi+8]
0x180007aaa  test    rax, rax
0x180007aad  jnz     short loc_180007A38
0x180007aaf  mov     ebx, 1
0x180007ab4  jmp     short loc_180007A3A
```
