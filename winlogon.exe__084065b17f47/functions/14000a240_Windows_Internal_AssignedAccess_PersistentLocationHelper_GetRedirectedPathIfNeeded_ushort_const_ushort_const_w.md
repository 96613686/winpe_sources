# Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x14000a240`
- end: `0x14000a679`
- name: `?GetRedirectedPathIfNeeded@PersistentLocationHelper@AssignedAccess@Internal@Windows@@SAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1081`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140009860`
- `0x140009900`
- `0x14000a0d0`
- `0x14000a680`

## callees

- `0x14000a240`
- `0x14000aa04`
- `0x140032c50`
- `0x1400364b0`
- `0x140053720`
- `0x140054406`
- `0x1400544e0`
- `0x1400587c0`
- `0x1400587ec`
- `0x14009cc54`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a2e4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a448`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a2e4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a615`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a628`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a628`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000a2b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000a415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000a4cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000a2b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000a415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000a4cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a31d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a5d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a63e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a31d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a5d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a63e`

## string_xrefs

- `0x14000a64e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x14000a667`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x14000a586`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
        _WORD *Src,
        __int64 a2,
        char *a3,
        const char *a4)
{
  _WORD *v5; // rdi
  __int64 v6; // rax
  size_t v7; // rbx
  size_t v8; // r14
  char *v9; // rax
  char *v10; // rsi
  void *v12; // rdi
  const char *v13; // r9
  int v14; // r14d
  char *v15; // rax
  __int64 v16; // rax
  char *v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // r12
  SIZE_T v21; // r14
  char *v22; // rax
  char *v23; // rsi
  size_t v24; // rbx
  void *v25; // rbx
  __int64 v26; // rdx
  unsigned __int64 v27; // rsi
  __int64 v28; // rax
  __int64 v29; // rbx
  _WORD *v30; // rax
  void *v31; // rsi
  DWORD LastError; // ebx
  int v33; // [rsp+20h] [rbp-E0h]
  LPVOID p_pv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v36; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v38[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v39; // [rsp+60h] [rbp-A0h] BYREF
  char v40; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v41[13]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *v42; // [rsp+E8h] [rbp-18h]
  _BYTE Srca[512]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]
  __int64 v45; // [rsp+348h] [rbp+248h] BYREF

  v45 = a2;
  v39 = Src;
  v5 = Src;
  if ( !a2 )
  {
    if ( !Src )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        a4);
    v6 = 0x7FFFFFFF;
    do
    {
      if ( !*Src )
        break;
      ++Src;
      --v6;
    }
    while ( v6 );
    v7 = 2 * (Src - v5);
    v8 = v7 + 2;
    v9 = (char *)CoTaskMemAlloc(v7 + 2);
    v10 = v9;
    if ( v9 )
    {
      if ( v7 )
      {
        if ( v8 < v7 )
        {
          memset_0(v9, 0, v8);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v9, v5, v7);
        }
      }
      *(_WORD *)&v10[v7] = 0;
    }
    pv = v10;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a3,
      &pv);
    if ( pv )
    {
      CoTaskMemFree(pv);
      return 0;
    }
    return 0;
  }
  v41[0] = &wistd::__function::__func<_lambda_6166c63e326ec22a386edc375e0b06c9_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v36 = 0;
  v41[1] = &v39;
  v41[2] = &v45;
  v42 = (wil::details::in1diag3 *)v41;
  memset_0(Srca, 0, sizeof(Srca));
  pv = 0;
  p_pv = &pv;
  v37 = 256;
  v38[0] = Srca;
  v12 = 0;
  v14 = wistd::__function::__func<_lambda_6166c63e326ec22a386edc375e0b06c9_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
          v41,
          v38,
          &v37,
          &p_pv);
  if ( v14 >= 0 )
  {
    v15 = (char *)pv;
    if ( (unsigned __int64)pv > 0x100 )
    {
      while ( 1 )
      {
        v27 = (unsigned __int64)v15;
        v28 = (__int64)(v15 - 1);
        if ( v28 == -1 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xF89,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
            v13);
        v29 = v28;
        v30 = CoTaskMemAlloc(2 * v28 + 2);
        if ( v30 )
        {
          *v30 = 0;
          v30[v29] = 0;
        }
        p_pv = v30;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v36,
          &p_pv);
        if ( p_pv )
          CoTaskMemFree(p_pv);
        v25 = v36;
        if ( !v36 )
        {
          v26 = 378;
          goto LABEL_45;
        }
        v38[0] = &pv;
        v37 = v27;
        p_pv = v36;
        if ( !v42 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
        v14 = (*(__int64 (__fastcall **)(wil::details::in1diag3 *, LPVOID *, __int64 *, _QWORD *))(*(_QWORD *)v42 + 32LL))(
                v42,
                &p_pv,
                &v37,
                v38);
        if ( v14 < 0 )
          break;
        v15 = (char *)pv;
        if ( (unsigned __int64)pv <= v27 )
          goto LABEL_41;
      }
      if ( v25 )
        CoTaskMemFree(v25);
    }
    else
    {
      v16 = 0x7FFFFFFF;
      v17 = Srca;
      if ( (char *)pv - 1 >= (char *)0x7FFFFFFF || (v16 = (__int64)pv - 1, pv != (LPVOID)1) )
      {
        do
        {
          if ( !*(_WORD *)v17 )
            break;
          v17 += 2;
          --v16;
        }
        while ( v16 );
      }
      v18 = (v17 - Srca) >> 1;
      v19 = v18;
      if ( pv )
        v19 = (__int64)pv - 1;
      v20 = 2 * v19;
      v21 = 2 * v19 + 2;
      v22 = (char *)CoTaskMemAlloc(v21);
      v23 = v22;
      if ( v22 )
      {
        v24 = 2 * v18;
        if ( v24 )
        {
          if ( v21 < v24 )
          {
            memset_0(v22, 0, v21);
            *(_DWORD *)_o__errno() = 34;
            invalid_parameter_noinfo();
          }
          else
          {
            memcpy_0(v22, Srca, v24);
          }
        }
        *(_WORD *)&v23[v24] = 0;
        *(_WORD *)&v23[v20] = 0;
      }
      p_pv = v23;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v36,
        &p_pv);
      if ( p_pv )
        CoTaskMemFree(p_pv);
      v25 = v36;
      if ( v36 )
      {
LABEL_41:
        v12 = v25;
        v14 = 0;
      }
      else
      {
        v26 = 367;
LABEL_45:
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
          (const char *)0x8007000ELL,
          v33);
      }
    }
  }
  if ( v42 )
    (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v42 + 24LL))(v42);
  if ( v14 >= 0 )
  {
    if ( a3 == &v40 )
    {
      if ( v12 )
        CoTaskMemFree(v12);
      return 0;
    }
    v31 = *(void **)a3;
    if ( *(_QWORD *)a3 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v31);
      SetLastError(LastError);
    }
    *(_QWORD *)a3 = v12;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\inc\\persistentlocationhelper.h",
      (const char *)(unsigned int)v14,
      v33);
    if ( v12 )
      CoTaskMemFree(v12);
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x14000a240  mov     [rsp-8+arg_8], rdx
0x14000a245  push    rbp
0x14000a246  push    rbx
0x14000a247  push    rsi
0x14000a248  push    rdi
0x14000a249  push    r13
0x14000a24b  push    r14
0x14000a24d  push    r15
0x14000a24f  lea     rbp, [rsp-200h]
0x14000a257  sub     rsp, 300h
0x14000a25e  mov     rax, cs:__security_cookie
0x14000a265  xor     rax, rsp
0x14000a268  mov     [rbp+230h+var_40], rax
0x14000a26f  mov     [rsp+330h+var_2D0], rcx
0x14000a274  mov     r13, r8
0x14000a277  mov     rdi, rcx
0x14000a27a  test    rdx, rdx
0x14000a27d  jnz     loc_14000A32A
0x14000a283  test    rcx, rcx
0x14000a286  jz      loc_14000A660
0x14000a28c  mov     eax, 7FFFFFFFh
0x14000a291  cmp     word ptr [rcx], 0
0x14000a295  jz      short loc_14000A2A1
0x14000a297  add     rcx, 2
0x14000a29b  sub     rax, 1
0x14000a29f  jnz     short loc_14000A291
0x14000a2a1  sub     rcx, rdi
0x14000a2a4  sar     rcx, 1
0x14000a2a7  lea     rbx, [rcx+rcx]
0x14000a2ab  lea     r14, [rbx+2]
0x14000a2af  mov     rcx, r14; cb
0x14000a2b2  call    cs:__imp_CoTaskMemAlloc
0x14000a2b8  mov     rsi, rax
0x14000a2bb  test    rax, rax
0x14000a2be  jz      short loc_14000A2FD
0x14000a2c0  test    rbx, rbx
0x14000a2c3  jz      short loc_14000A2F5
0x14000a2c5  mov     rcx, rax; void *
0x14000a2c8  cmp     r14, rbx
0x14000a2cb  jb      short loc_14000A2DA
0x14000a2cd  mov     r8, rbx; Size
0x14000a2d0  mov     rdx, rdi; Src
0x14000a2d3  call    memcpy_0
0x14000a2d8  jmp     short loc_14000A2F5
0x14000a2da  mov     r8, r14; Size
0x14000a2dd  xor     edx, edx; Val
0x14000a2df  call    memset_0
0x14000a2e4  call    cs:__imp__o__errno
0x14000a2ea  mov     dword ptr [rax], 22h ; '"'
0x14000a2f0  call    _invalid_parameter_noinfo
0x14000a2f5  xor     r15d, r15d
0x14000a2f8  mov     [rbx+rsi], r15w
0x14000a2fd  lea     rdx, [rsp+330h+pv]
0x14000a302  mov     [rsp+330h+pv], rsi
0x14000a307  mov     rcx, r13
0x14000a30a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x14000a30f  mov     rcx, [rsp+330h+pv]; pv
0x14000a314  test    rcx, rcx
0x14000a317  jz      loc_14000A644
0x14000a31d  call    cs:__imp_CoTaskMemFree
0x14000a323  xor     eax, eax
0x14000a325  jmp     loc_14000A5E1
0x14000a32a  lea     rax, ??_7?$__func@V_lambda_6166c63e326ec22a386edc375e0b06c9_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_6166c63e326ec22a386edc375e0b06c9_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x14000a331  xor     r15d, r15d
0x14000a334  mov     [rbp+230h+var_2B0], rax
0x14000a338  lea     rcx, [rbp+230h+Src]; void *
0x14000a33c  lea     rax, [rsp+330h+var_2D0]
0x14000a341  mov     [rsp+330h+var_2F0], r15
0x14000a346  mov     [rbp+230h+var_2A8], rax
0x14000a34a  xor     edx, edx; Val
0x14000a34c  lea     rax, [rbp+230h+arg_8]
0x14000a353  mov     r8d, 200h; Size
0x14000a359  mov     [rbp+230h+var_2A0], rax
0x14000a35d  lea     rax, [rbp+230h+var_2B0]
0x14000a361  mov     [rbp+230h+var_248], rax
0x14000a365  call    memset_0
0x14000a36a  lea     rax, [rsp+330h+pv]
0x14000a36f  mov     [rsp+330h+pv], r15
0x14000a374  mov     [rsp+330h+var_300], rax
0x14000a379  lea     r9, [rsp+330h+var_300]
0x14000a37e  lea     rax, [rbp+230h+Src]
0x14000a382  mov     [rsp+330h+var_2E8], 100h
0x14000a38b  lea     r8, [rsp+330h+var_2E8]
0x14000a390  mov     [rsp+330h+var_2E0], rax
0x14000a395  lea     rdx, [rsp+330h+var_2E0]
0x14000a39a  mov     edi, r15d
0x14000a39d  lea     rcx, [rbp+230h+var_2B0]
0x14000a3a1  call    ??R?$__func@V_lambda_6166c63e326ec22a386edc375e0b06c9_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z; wistd::__function::__func<_lambda_6166c63e326ec22a386edc375e0b06c9_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)
0x14000a3a6  mov     r14d, eax
0x14000a3a9  test    eax, eax
0x14000a3ab  js      loc_14000A59B
0x14000a3b1  mov     rax, [rsp+330h+pv]
0x14000a3b6  cmp     rax, 100h
0x14000a3bc  ja      loc_14000A4B0
0x14000a3c2  lea     rcx, [rax-1]
0x14000a3c6  mov     [rsp+330h+arg_18], r12
0x14000a3ce  mov     eax, 7FFFFFFFh
0x14000a3d3  lea     rbx, [rbp+230h+Src]
0x14000a3d7  cmp     rcx, rax
0x14000a3da  jnb     short loc_14000A3E4
0x14000a3dc  mov     rax, rcx
0x14000a3df  test    rcx, rcx
0x14000a3e2  jz      short loc_14000A3F4
0x14000a3e4  cmp     [rbx], r15w
0x14000a3e8  jz      short loc_14000A3F4
0x14000a3ea  add     rbx, 2
0x14000a3ee  sub     rax, 1
0x14000a3f2  jnz     short loc_14000A3E4
0x14000a3f4  lea     rax, [rbp+230h+Src]
0x14000a3f8  sub     rbx, rax
0x14000a3fb  sar     rbx, 1
0x14000a3fe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000a402  mov     rax, rbx
0x14000a405  cmovnz  rax, rcx
0x14000a409  lea     r12, [rax+rax]
0x14000a40d  lea     r14, [r12+2]
0x14000a412  mov     rcx, r14; cb
0x14000a415  call    cs:__imp_CoTaskMemAlloc
0x14000a41b  mov     rsi, rax
0x14000a41e  test    rax, rax
0x14000a421  jz      short loc_14000A463
0x14000a423  add     rbx, rbx
0x14000a426  jz      short loc_14000A459
0x14000a428  mov     rcx, rax; void *
0x14000a42b  cmp     r14, rbx
0x14000a42e  jb      short loc_14000A43E
0x14000a430  mov     r8, rbx; Size
0x14000a433  lea     rdx, [rbp+230h+Src]; Src
0x14000a437  call    memcpy_0
0x14000a43c  jmp     short loc_14000A459
0x14000a43e  mov     r8, r14; Size
0x14000a441  xor     edx, edx; Val
0x14000a443  call    memset_0
0x14000a448  call    cs:__imp__o__errno
0x14000a44e  mov     dword ptr [rax], 22h ; '"'
0x14000a454  call    _invalid_parameter_noinfo
0x14000a459  mov     [rsi+rbx], r15w
0x14000a45e  mov     [r12+rsi], r15w
0x14000a463  lea     rdx, [rsp+330h+var_300]
0x14000a468  mov     [rsp+330h+var_300], rsi
0x14000a46d  lea     rcx, [rsp+330h+var_2F0]
0x14000a472  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x14000a477  mov     rcx, [rsp+330h+var_300]; pv
0x14000a47c  mov     r12, [rsp+330h+arg_18]
0x14000a484  test    rcx, rcx
0x14000a487  jz      short loc_14000A48F
0x14000a489  call    cs:__imp_CoTaskMemFree
0x14000a48f  mov     rbx, [rsp+330h+var_2F0]
0x14000a494  test    rbx, rbx
0x14000a497  jnz     loc_14000A562
0x14000a49d  mov     edx, 16Fh
0x14000a4a2  jmp     loc_14000A57F
0x14000a4b0  mov     rcx, [rbp+238h]; this
0x14000a4b7  mov     rsi, rax
0x14000a4ba  dec     rax
0x14000a4bd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a4c1  jz      loc_14000A64E
0x14000a4c7  lea     rbx, [rax+rax]
0x14000a4cb  lea     rcx, [rbx+2]; cb
0x14000a4cf  call    cs:__imp_CoTaskMemAlloc
0x14000a4d5  test    rax, rax
0x14000a4d8  jz      short loc_14000A4E3
0x14000a4da  mov     [rax], r15w
0x14000a4de  mov     [rax+rbx], r15w
0x14000a4e3  lea     rdx, [rsp+330h+var_300]
0x14000a4e8  mov     [rsp+330h+var_300], rax
0x14000a4ed  lea     rcx, [rsp+330h+var_2F0]
0x14000a4f2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x14000a4f7  mov     rcx, [rsp+330h+var_300]; pv
0x14000a4fc  test    rcx, rcx
0x14000a4ff  jz      short loc_14000A507
0x14000a501  call    cs:__imp_CoTaskMemFree
0x14000a507  mov     rbx, [rsp+330h+var_2F0]
0x14000a50c  test    rbx, rbx
0x14000a50f  jz      short loc_14000A57A
0x14000a511  mov     rcx, [rbp+230h+var_248]; this
0x14000a515  lea     rax, [rsp+330h+pv]
0x14000a51a  mov     [rsp+330h+var_2E0], rax
0x14000a51f  mov     [rsp+330h+var_2E8], rsi
0x14000a524  mov     [rsp+330h+var_300], rbx
0x14000a529  test    rcx, rcx
0x14000a52c  jz      loc_14000A648
0x14000a532  mov     rax, [rcx]
0x14000a535  lea     r9, [rsp+330h+var_2E0]
0x14000a53a  lea     r8, [rsp+330h+var_2E8]
0x14000a53f  lea     rdx, [rsp+330h+var_300]
0x14000a544  mov     rax, [rax+20h]
0x14000a548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a54d  mov     r14d, eax
0x14000a550  test    eax, eax
0x14000a552  js      short loc_14000A56A
0x14000a554  mov     rax, [rsp+330h+pv]
0x14000a559  cmp     rax, rsi
0x14000a55c  ja      loc_14000A4B0
0x14000a562  mov     rdi, rbx
0x14000a565  mov     r14d, r15d
0x14000a568  jmp     short loc_14000A59B
0x14000a56a  test    rbx, rbx
0x14000a56d  jz      short loc_14000A59B
0x14000a56f  mov     rcx, rbx; pv
0x14000a572  call    cs:__imp_CoTaskMemFree
0x14000a578  jmp     short loc_14000A59B
0x14000a57a  mov     edx, 17Ah; void *
0x14000a57f  mov     rcx, [rbp+238h]; this
0x14000a586  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000a58d  mov     r14d, 8007000Eh
0x14000a593  mov     r9d, r14d; char *
0x14000a596  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a59b  mov     rcx, [rbp+230h+var_248]
0x14000a59f  test    rcx, rcx
0x14000a5a2  jz      short loc_14000A5B0
0x14000a5a4  mov     rax, [rcx]
0x14000a5a7  mov     rax, [rax+18h]
0x14000a5ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5b0  test    r14d, r14d
0x14000a5b3  jns     short loc_14000A602
0x14000a5b5  mov     rcx, [rbp+238h]; this
0x14000a5bc  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x14000a5c3  mov     r9d, r14d; char *
0x14000a5c6  mov     edx, 1Fh; void *
0x14000a5cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a5d0  test    rdi, rdi
0x14000a5d3  jz      short loc_14000A5DE
0x14000a5d5  mov     rcx, rdi; pv
0x14000a5d8  call    cs:__imp_CoTaskMemFree
0x14000a5de  mov     eax, r14d
0x14000a5e1  mov     rcx, [rbp+230h+var_40]
0x14000a5e8  xor     rcx, rsp; StackCookie
0x14000a5eb  call    __security_check_cookie
0x14000a5f0  add     rsp, 300h
0x14000a5f7  pop     r15
0x14000a5f9  pop     r14
0x14000a5fb  pop     r13
0x14000a5fd  pop     rdi
0x14000a5fe  pop     rsi
0x14000a5ff  pop     rbx
0x14000a600  pop     rbp
0x14000a601  retn
0x14000a602  lea     rax, [rsp+330h+var_2C0]
0x14000a607  cmp     r13, rax
0x14000a60a  jz      short loc_14000A636
0x14000a60c  mov     rsi, [r13+0]
0x14000a610  test    rsi, rsi
0x14000a613  jz      short loc_14000A62E
0x14000a615  call    cs:__imp_GetLastError
0x14000a61b  mov     rcx, rsi; pv
0x14000a61e  mov     ebx, eax
0x14000a620  call    cs:__imp_CoTaskMemFree
0x14000a626  mov     ecx, ebx; dwErrCode
0x14000a628  call    cs:__imp_SetLastError
0x14000a62e  mov     [r13+0], rdi
0x14000a632  xor     eax, eax
0x14000a634  jmp     short loc_14000A5E1
0x14000a636  test    rdi, rdi
0x14000a639  jz      short loc_14000A644
0x14000a63b  mov     rcx, rdi; pv
0x14000a63e  call    cs:__imp_CoTaskMemFree
0x14000a644  xor     eax, eax
0x14000a646  jmp     short loc_14000A5E1
0x14000a648  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000a64e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000a655  mov     edx, 0F89h; void *
0x14000a65a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000a660  mov     rcx, [rbp+238h]; this
0x14000a667  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000a66e  mov     edx, 0F89h; void *
0x14000a673  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
