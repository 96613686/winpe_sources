# CLauncherTipContextMenu::_CheckLinkHash(CPropertyStoreHelper const &,ulong *)

- ea: `0x1800c7480`
- end: `0x1800c7a4f`
- name: `?_CheckLinkHash@CLauncherTipContextMenu@@AEAAJAEBVCPropertyStoreHelper@@PEAK@Z`
- size: `1487`
- prototype: `__int64 __fastcall(CLauncherTipContextMenu *__hidden this, const struct CPropertyStoreHelper *, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180164d0c`
- `0x1806075a0`

## callees

- `0x1800290dc`
- `0x180086ac0`
- `0x1800c7480`
- `0x1800c7a60`
- `0x1800c7b00`
- `0x1800c7bc0`
- `0x1800c7c60`
- `0x1800c7d98`
- `0x1800c7e80`
- `0x180356360`
- `0x180356760`
- `0x18035b6a0`
- `0x18060a83c`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c752f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c75e6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c752f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c75e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7640`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7748`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c78c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c78e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7640`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7748`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c78c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c78e1`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800c7808`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800c7808`
- `api-ms-win-core-url-l1-1-0!HashData` at `0x1800c7863`
- `api-ms-win-core-url-l1-1-0!HashData` at `0x1800c7863`
- `PROPSYS!PropVariantToUInt32` at `0x1800c751b`
- `PROPSYS!PropVariantToUInt32` at `0x1800c751b`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800c75c8`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800c75c8`

## string_xrefs

- `0x1800c76e7`: `Do not prehash links.  This should only be done by the user.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CLauncherTipContextMenu::_CheckLinkHash(
        CLauncherTipContextMenu *this,
        const struct CPropertyStoreHelper *a2,
        unsigned int *a3)
{
  HRESULT As; // ebx
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rcx
  char *v9; // rcx
  __int64 v10; // r9
  unsigned __int16 *v11; // rax
  signed __int64 v12; // rax
  const wchar_t *v13; // rcx
  char *v14; // rdx
  unsigned __int16 *v15; // r8
  wchar_t v16; // ax
  __int64 v17; // rdx
  unsigned __int16 *i; // rax
  signed __int64 v19; // rdi
  int v20; // esi
  unsigned __int64 v21; // rax
  WCHAR *v22; // rax
  BYTE *v23; // rdi
  __int64 v24; // rax
  __int64 v25; // rcx
  char *v26; // rdi
  int v27; // edx
  int v28; // ecx
  unsigned __int16 *v29; // r15
  __int64 v30; // rdx
  int lpDestStr; // [rsp+20h] [rbp-E0h]
  PROPVARIANT propvarIn[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h]
  BYTE pbHash[4]; // [rsp+68h] [rbp-98h] BYREF
  ULONG pulRet; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int16 *v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h]
  __int64 v38; // [rsp+80h] [rbp-80h]
  PWSTR ppszOut; // [rsp+88h] [rbp-78h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h]
  __int64 v41; // [rsp+98h] [rbp-68h]
  PROPERTYKEY v42; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID pv[2]; // [rsp+C0h] [rbp-40h] BYREF
  GUID v44; // [rsp+D0h] [rbp-30h]
  GUID v45; // [rsp+E0h] [rbp-20h]
  GUID v46; // [rsp+F0h] [rbp-10h]
  unsigned __int16 v47[264]; // [rsp+100h] [rbp+0h] BYREF

  *a3 = 0;
  pulRet = 0;
  LOWORD(propvarIn[0]) = 0;
  v42.fmtid = (GUID)PKEY_Winx_Hash;
  v42.pid = 2;
  As = (*(__int64 (__fastcall **)(_QWORD, PROPERTYKEY *, PROPVARIANT *))(**(_QWORD **)a2 + 40LL))(
         *(_QWORD *)a2,
         &v42,
         propvarIn);
  if ( As >= 0 )
  {
    if ( LOWORD(propvarIn[0]) )
    {
      pulRet = 0;
      As = PropVariantToUInt32(propvarIn, &pulRet);
    }
    else
    {
      As = -2147023728;
    }
  }
  PropVariantClear(propvarIn);
  ppszOut = 0;
  v40 = 0;
  v41 = 0;
  if ( As >= 0 )
  {
    v40 = -1;
    v41 = -1;
    ppszOut = 0;
    LOWORD(propvarIn[0]) = 0;
    v42 = PKEY_Link_TargetParsingPath;
    As = (*(__int64 (__fastcall **)(_QWORD, PROPERTYKEY *, PROPVARIANT *))(**(_QWORD **)a2 + 40LL))(
           *(_QWORD *)a2,
           &v42,
           propvarIn);
    if ( As >= 0 )
    {
      if ( LOWORD(propvarIn[0]) )
      {
        if ( LOWORD(propvarIn[0]) == 31 && propvarIn[1] )
        {
          ppszOut = (PWSTR)propvarIn[1];
          *(_OWORD *)propvarIn = 0;
          v33 = 0;
          As = 0;
        }
        else
        {
          ppszOut = 0;
          As = PropVariantToStringAlloc(propvarIn, &ppszOut);
        }
      }
      else
      {
        As = -2147023728;
      }
    }
    PropVariantClear(propvarIn);
  }
  v6 = 0;
  propvarIn[0] = 0;
  propvarIn[1] = 0;
  v33 = 0;
  if ( As >= 0 )
  {
    v44 = FOLDERID_ProgramFiles;
    v45 = FOLDERID_System;
    v46 = FOLDERID_Windows;
    EncodeRelativePath(v47, ppszOut);
    As = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           propvarIn,
           v47,
           -1);
    v6 = (unsigned __int16 *)propvarIn[0];
    if ( As >= 0 && (!propvarIn[0] || !*(_WORD *)propvarIn[0]) )
    {
      As = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
             propvarIn,
             &ppszOut);
      v6 = (unsigned __int16 *)propvarIn[0];
    }
  }
  v7 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  if ( As >= 0 )
  {
    v37 = -1;
    v38 = -1;
    v42 = PKEY_Link_Arguments;
    As = CPropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(a2, &v42, &v36);
    if ( (int)(As + 0x80000000) >= 0 && As != -2147023728 )
      goto LABEL_41;
    if ( v36 )
    {
      v30 = -1;
      do
        ++v30;
      while ( v36[v30] );
    }
    else
    {
      v30 = 0;
    }
    if ( propvarIn[1] == (PROPVARIANT)-1LL )
    {
      if ( v6 )
      {
        v24 = -1;
        do
          ++v24;
        while ( v6[v24] );
        propvarIn[1] = (PROPVARIANT)v24;
      }
      else
      {
        propvarIn[1] = 0;
      }
    }
    v25 = -1;
    do
      ++v25;
    while ( ppszOut[v25] );
    v26 = (char *)propvarIn[1] + v25 + v30 + 61;
    pv[0] = 0;
    pv[1] = 0;
    CoTaskMemFree(0);
    As = _AllocStringWorker<CTCoAllocPolicy>(v28, v27, 0, (_DWORD)v26, lpDestStr, (__int64)pv);
    CoTaskMemFree(0);
    v29 = (unsigned __int16 *)pv[0];
    if ( As >= 0 )
    {
      if ( !v6 || !*v6 || (As = StringCchCopyW((unsigned __int16 *)pv[0], (unsigned __int64)v26, v6), As >= 0) )
      {
        if ( !v36 || (As = StringCchCatW(v29, (unsigned __int64)v26, v36), As >= 0) )
        {
          v10 = 2147483646;
          if ( (unsigned __int64)(v26 - 1) > 0x7FFFFFFE )
          {
            As = -2147024809;
          }
          else
          {
            v9 = v26;
            v11 = v29;
            while ( *v11 )
            {
              ++v11;
              if ( !--v9 )
              {
                v12 = 0;
                As = -2147024809;
                goto LABEL_30;
              }
            }
            v12 = v26 - v9;
            As = 0;
LABEL_30:
            if ( As >= 0 )
            {
              v13 = L"Do not prehash links.  This should only be done by the user.";
              v14 = &v26[-v12];
              v15 = &v29[v12];
              if ( v26 != (char *)v12 )
              {
                do
                {
                  if ( !v10 )
                    break;
                  v16 = *v13;
                  if ( !*v13 )
                    break;
                  ++v13;
                  *v15++ = v16;
                  --v10;
                  --v14;
                }
                while ( v14 );
              }
              v9 = (char *)(v15 - 1);
              if ( v14 )
                v9 = (char *)v15;
              *(_WORD *)v9 = 0;
              As = -2147024774;
              if ( v14 )
                As = 0;
            }
          }
        }
      }
    }
    v17 = 0;
    *(_DWORD *)pbHash = 0;
    if ( As < 0 )
    {
LABEL_40:
      CoTaskMemFree(v29);
LABEL_41:
      v7 = v36;
      goto LABEL_15;
    }
    if ( v29 && (unsigned __int64)v26 <= 0x7FFFFFFF )
    {
      v9 = v26;
      for ( i = v29; v9; --v9 )
      {
        if ( !*i )
          break;
        ++i;
      }
      As = -2147024809;
      if ( v9 )
        As = 0;
      v19 = v26 - v9;
      if ( v9 )
      {
        v20 = v19;
        v21 = 2 * (v19 + 1);
        if ( !is_mul_ok(v19 + 1, 2u) )
          v21 = -1;
        v22 = (WCHAR *)operator new[](v21, (const struct std::nothrow_t *)std::nothrow);
        v23 = (BYTE *)v22;
        if ( !v22 )
        {
          As = -2147024882;
          goto LABEL_40;
        }
        if ( LCMapStringEx(&pvData, 0x100u, v29, v20 + 1, v22, v20 + 1, 0, 0, 0)
          || (As = ResultFromKnownLastError(), As >= 0) )
        {
          As = HashData(v23, 2 * v20, pbHash, 4u);
        }
        operator delete(v23);
        v17 = *(unsigned int *)pbHash;
      }
    }
    else
    {
      As = -2147024809;
    }
    if ( As >= 0 )
    {
      if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
      {
        McTemplateU0qz_EventWriteTransfer(v9, v17, (unsigned int)v17, v29);
        LODWORD(v17) = *(_DWORD *)pbHash;
      }
      if ( pulRet == (_DWORD)v17 )
      {
        As = 0;
        *a3 = pulRet;
      }
      else
      {
        As = -2147467259;
      }
    }
    goto LABEL_40;
  }
LABEL_15:
  if ( v7 )
  {
    CoTaskMemFree(v7);
    v36 = 0;
  }
  v37 = 0;
  v38 = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  if ( ppszOut )
    CoTaskMemFree(ppszOut);
  return (unsigned int)As;
}

```

## disassembly

```asm
0x1800c7480  mov     [rsp-8+arg_0], rbx
0x1800c7485  push    rbp
0x1800c7486  push    rsi
0x1800c7487  push    rdi
0x1800c7488  push    r12
0x1800c748a  push    r13
0x1800c748c  push    r14
0x1800c748e  push    r15
0x1800c7490  lea     rbp, [rsp-220h]
0x1800c7498  sub     rsp, 320h
0x1800c749f  mov     rax, cs:__security_cookie
0x1800c74a6  xor     rax, rsp
0x1800c74a9  mov     [rbp+250h+var_40], rax
0x1800c74b0  mov     r12, r8
0x1800c74b3  mov     rdi, rdx
0x1800c74b6  xor     r13d, r13d
0x1800c74b9  mov     [r8], r13d
0x1800c74bc  movups  xmm0, cs:PKEY_Winx_Hash
0x1800c74c3  mov     ecx, cs:dword_180771920
0x1800c74c9  mov     [rsp+350h+pulRet], r13d
0x1800c74ce  mov     word ptr [rsp+350h+propvarIn], r13w
0x1800c74d4  movaps  [rbp+250h+var_2B0], xmm0
0x1800c74d8  mov     [rbp+250h+var_2A0], ecx
0x1800c74db  mov     rcx, [rdx]
0x1800c74de  mov     rax, [rcx]
0x1800c74e1  lea     r8, [rsp+350h+propvarIn]
0x1800c74e6  lea     rdx, [rbp+250h+var_2B0]
0x1800c74ea  mov     rax, [rax+28h]
0x1800c74ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c74f3  mov     ebx, eax
0x1800c74f5  test    eax, eax
0x1800c74f7  js      short loc_1800C752A
0x1800c74f9  movzx   eax, word ptr [rsp+350h+propvarIn]
0x1800c74fe  test    ax, ax
0x1800c7501  jz      short loc_1800C7525
0x1800c7503  mov     [rsp+350h+pulRet], r13d
0x1800c7508  test    ax, ax
0x1800c750b  jz      loc_1800C75D2
0x1800c7511  lea     rdx, [rsp+350h+pulRet]; pulRet
0x1800c7516  lea     rcx, [rsp+350h+propvarIn]; propvarIn
0x1800c751b  call    cs:__imp_PropVariantToUInt32
0x1800c7521  mov     ebx, eax
0x1800c7523  jmp     short loc_1800C752A
0x1800c7525  mov     ebx, 80070490h
0x1800c752a  lea     rcx, [rsp+350h+propvarIn]; pvar
0x1800c752f  call    cs:__imp_PropVariantClear
0x1800c7535  mov     [rbp+250h+ppszOut], r13
0x1800c7539  mov     [rbp+250h+var_2C0], r13
0x1800c753d  mov     [rbp+250h+var_2B8], r13
0x1800c7541  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800c7548  test    ebx, ebx
0x1800c754a  js      loc_1800C75EC
0x1800c7550  mov     [rbp+250h+var_2C0], rsi
0x1800c7554  mov     [rbp+250h+var_2B8], rsi
0x1800c7558  movups  xmm0, xmmword ptr cs:PKEY_Link_TargetParsingPath.fmtid.Data1
0x1800c755f  mov     ecx, cs:PKEY_Link_TargetParsingPath.pid
0x1800c7565  mov     [rbp+250h+ppszOut], r13
0x1800c7569  mov     word ptr [rsp+350h+propvarIn], r13w
0x1800c756f  movaps  [rbp+250h+var_2B0], xmm0
0x1800c7573  mov     [rbp+250h+var_2A0], ecx
0x1800c7576  mov     rcx, [rdi]
0x1800c7579  mov     rax, [rcx]
0x1800c757c  lea     r8, [rsp+350h+propvarIn]
0x1800c7581  lea     rdx, [rbp+250h+var_2B0]
0x1800c7585  mov     rax, [rax+28h]
0x1800c7589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c758e  mov     ebx, eax
0x1800c7590  test    eax, eax
0x1800c7592  js      short loc_1800C75E1
0x1800c7594  movzx   eax, word ptr [rsp+350h+propvarIn]
0x1800c7599  test    ax, ax
0x1800c759c  jz      short loc_1800C75DC
0x1800c759e  cmp     ax, 1Fh
0x1800c75a2  jnz     short loc_1800C75B2
0x1800c75a4  mov     rcx, [rsp+350h+propvarIn+8]
0x1800c75a9  test    rcx, rcx
0x1800c75ac  jnz     loc_1800C7A02
0x1800c75b2  mov     [rbp+250h+ppszOut], r13
0x1800c75b6  test    ax, ax
0x1800c75b9  jz      loc_1800C7A1D
0x1800c75bf  lea     rdx, [rbp+250h+ppszOut]; ppszOut
0x1800c75c3  lea     rcx, [rsp+350h+propvarIn]; propvar
0x1800c75c8  call    cs:__imp_PropVariantToStringAlloc
0x1800c75ce  mov     ebx, eax
0x1800c75d0  jmp     short loc_1800C75E1
0x1800c75d2  mov     ebx, 80070490h
0x1800c75d7  jmp     loc_1800C752A
0x1800c75dc  mov     ebx, 80070490h
0x1800c75e1  lea     rcx, [rsp+350h+propvarIn]; pvar
0x1800c75e6  call    cs:__imp_PropVariantClear
0x1800c75ec  mov     r14, r13
0x1800c75ef  mov     [rsp+350h+propvarIn], r13
0x1800c75f4  mov     [rsp+350h+propvarIn+8], r13
0x1800c75f9  mov     [rsp+350h+var_2F0], r13
0x1800c75fe  test    ebx, ebx
0x1800c7600  jns     loc_1800C7981
0x1800c7606  mov     rcx, r13; pv
0x1800c7609  mov     [rsp+350h+var_2E0], rcx
0x1800c760e  mov     [rsp+350h+var_2D8], r13
0x1800c7613  mov     [rbp+250h+var_2D0], r13
0x1800c7617  test    ebx, ebx
0x1800c7619  jns     loc_1800C7924
0x1800c761f  test    rcx, rcx
0x1800c7622  jz      short loc_1800C762F
0x1800c7624  call    cs:__imp_CoTaskMemFree
0x1800c762a  mov     [rsp+350h+var_2E0], r13
0x1800c762f  mov     [rsp+350h+var_2D8], r13
0x1800c7634  mov     [rbp+250h+var_2D0], r13
0x1800c7638  test    r14, r14
0x1800c763b  jz      short loc_1800C7647
0x1800c763d  mov     rcx, r14; pv
0x1800c7640  call    cs:__imp_CoTaskMemFree
0x1800c7646  nop
0x1800c7647  mov     rcx, [rbp+250h+ppszOut]; pv
0x1800c764b  test    rcx, rcx
0x1800c764e  jz      short loc_1800C7656
0x1800c7650  call    cs:__imp_CoTaskMemFree
0x1800c7656  mov     eax, ebx
0x1800c7658  mov     rcx, [rbp+250h+var_40]
0x1800c765f  xor     rcx, rsp; StackCookie
0x1800c7662  call    __security_check_cookie
0x1800c7667  mov     rbx, [rsp+350h+arg_0]
0x1800c766f  add     rsp, 320h
0x1800c7676  pop     r15
0x1800c7678  pop     r14
0x1800c767a  pop     r13
0x1800c767c  pop     r12
0x1800c767e  pop     rdi
0x1800c767f  pop     rsi
0x1800c7680  pop     rbp
0x1800c7681  retn
0x1800c7682  mov     r8, [rsp+350h+var_2E0]; unsigned __int16 *
0x1800c7687  test    r8, r8
0x1800c768a  jz      short loc_1800C76A1
0x1800c768c  mov     rdx, rdi; unsigned __int64
0x1800c768f  mov     rcx, r15; unsigned __int16 *
0x1800c7692  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c7697  mov     ebx, eax
0x1800c7699  test    eax, eax
0x1800c769b  js      loc_1800C773A
0x1800c76a1  lea     rax, [rdi-1]
0x1800c76a5  mov     r9d, 7FFFFFFEh
0x1800c76ab  cmp     rax, r9
0x1800c76ae  ja      loc_1800C7A31
0x1800c76b4  mov     rcx, rdi
0x1800c76b7  mov     rax, r15
0x1800c76ba  nop     word ptr [rax+rax+00h]
0x1800c76c0  cmp     word ptr [rax], 0
0x1800c76c4  jz      short loc_1800C76DA
0x1800c76c6  add     rax, 2
0x1800c76ca  sub     rcx, 1
0x1800c76ce  jnz     short loc_1800C76C0
0x1800c76d0  mov     rax, r13
0x1800c76d3  mov     ebx, 80070057h
0x1800c76d8  jmp     short loc_1800C76E3
0x1800c76da  mov     rax, rdi
0x1800c76dd  sub     rax, rcx
0x1800c76e0  mov     ebx, r13d
0x1800c76e3  test    ebx, ebx
0x1800c76e5  js      short loc_1800C773A
0x1800c76e7  lea     rcx, aDoNotPrehashLi; "Do not prehash links.  This should only"...
0x1800c76ee  mov     rdx, rdi
0x1800c76f1  sub     rdx, rax
0x1800c76f4  lea     r8, [r15+rax*2]
0x1800c76f8  jz      short loc_1800C7722
0x1800c76fa  nop     word ptr [rax+rax+00h]
0x1800c7700  test    r9, r9
0x1800c7703  jz      short loc_1800C7722
0x1800c7705  movzx   eax, word ptr [rcx]
0x1800c7708  test    ax, ax
0x1800c770b  jz      short loc_1800C7722
0x1800c770d  add     rcx, 2
0x1800c7711  mov     [r8], ax
0x1800c7715  add     r8, 2
0x1800c7719  dec     r9
0x1800c771c  sub     rdx, 1
0x1800c7720  jnz     short loc_1800C7700
0x1800c7722  lea     rcx, [r8-2]
0x1800c7726  test    rdx, rdx
0x1800c7729  cmovnz  rcx, r8
0x1800c772d  mov     [rcx], r13w
0x1800c7731  mov     ebx, 8007007Ah
0x1800c7736  cmovnz  ebx, r13d
0x1800c773a  mov     edx, r13d
0x1800c773d  mov     dword ptr [rsp+350h+pbHash], edx
0x1800c7741  test    ebx, ebx
0x1800c7743  jns     short loc_1800C7758
0x1800c7745  mov     rcx, r15; pv
0x1800c7748  call    cs:__imp_CoTaskMemFree
0x1800c774e  mov     rcx, [rsp+350h+var_2E0]
0x1800c7753  jmp     loc_1800C761F
0x1800c7758  test    r15, r15
0x1800c775b  jz      loc_1800C7A45
0x1800c7761  cmp     rdi, 7FFFFFFFh
0x1800c7768  ja      loc_1800C7A45
0x1800c776e  mov     rcx, rdi
0x1800c7771  mov     rax, r15
0x1800c7774  test    rdi, rdi
0x1800c7777  jz      short loc_1800C778F
0x1800c7779  nop     dword ptr [rax+00000000h]
0x1800c7780  cmp     [rax], dx
0x1800c7783  jz      short loc_1800C778F
0x1800c7785  add     rax, 2
0x1800c7789  sub     rcx, 1
0x1800c778d  jnz     short loc_1800C7780
0x1800c778f  mov     ebx, 80070057h
0x1800c7794  test    rcx, rcx
0x1800c7797  cmovnz  ebx, r13d
0x1800c779b  sub     rdi, rcx
0x1800c779e  mov     rsi, r13
0x1800c77a1  test    rcx, rcx
0x1800c77a4  cmovnz  rsi, rdi
0x1800c77a8  jz      short loc_1800C7829
0x1800c77aa  lea     rcx, [rsi+1]
0x1800c77ae  mov     eax, 2
0x1800c77b3  mul     rcx
0x1800c77b6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c77bd  cmovb   rax, rcx
0x1800c77c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c77c8  mov     rcx, rax; unsigned __int64
0x1800c77cb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800c77d0  mov     rdi, rax
0x1800c77d3  test    rax, rax
0x1800c77d6  jz      loc_1800C7A3B
0x1800c77dc  lea     r9d, [rsi+1]; cchSrc
0x1800c77e0  mov     [rsp+350h+sortHandle], r13; sortHandle
0x1800c77e5  mov     [rsp+350h+lpReserved], r13; lpReserved
0x1800c77ea  mov     [rsp+350h+lpVersionInformation], r13; lpVersionInformation
0x1800c77ef  mov     [rsp+350h+cchDest], r9d; cchDest
0x1800c77f4  mov     [rsp+350h+lpDestStr], rax; lpDestStr
0x1800c77f9  mov     r8, r15; lpSrcStr
0x1800c77fc  mov     edx, 100h; dwMapFlags
0x1800c7801  lea     rcx, pvData; lpLocaleName
0x1800c7808  call    cs:__imp_LCMapStringEx
0x1800c780e  test    eax, eax
0x1800c7810  jnz     short loc_1800C7852
0x1800c7812  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c7817  mov     ebx, eax
0x1800c7819  test    eax, eax
0x1800c781b  jns     short loc_1800C7852
0x1800c781d  mov     rcx, rdi; Block
0x1800c7820  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c7825  mov     edx, dword ptr [rsp+350h+pbHash]
0x1800c7829  test    ebx, ebx
0x1800c782b  js      loc_1800C7745
0x1800c7831  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x1800c7838  jz      loc_1806F14F0
0x1800c783e  mov     r9, r15
0x1800c7841  mov     r8d, edx
0x1800c7844  call    McTemplateU0qz_EventWriteTransfer
0x1800c7849  mov     edx, dword ptr [rsp+350h+pbHash]
0x1800c784d  jmp     loc_1806F14F0
0x1800c7852  lea     edx, [rsi+rsi]; cbData
0x1800c7855  mov     r9d, 4; cbHash
0x1800c785b  lea     r8, [rsp+350h+pbHash]; pbHash
0x1800c7860  mov     rcx, rdi; pbData
0x1800c7863  call    cs:__imp_HashData
0x1800c7869  mov     ebx, eax
0x1800c786b  jmp     short loc_1800C781D
0x1800c786d  cmp     [rsp+350h+propvarIn+8], 0FFFFFFFFFFFFFFFFh
0x1800c7873  jnz     short loc_1800C7891
0x1800c7875  test    r14, r14
0x1800c7878  jz      loc_1800C7A27
0x1800c787e  mov     rax, rsi
0x1800c7881  inc     rax
0x1800c7884  cmp     word ptr [r14+rax*2], 0
0x1800c788a  jnz     short loc_1800C7881
0x1800c788c  mov     [rsp+350h+propvarIn+8], rax
0x1800c7891  mov     rax, [rbp+250h+ppszOut]
0x1800c7895  mov     rcx, rsi
0x1800c7898  nop     dword ptr [rax+rax+00000000h]
0x1800c78a0  inc     rcx
0x1800c78a3  cmp     word ptr [rax+rcx*2], 0
0x1800c78a8  jnz     short loc_1800C78A0
0x1800c78aa  mov     rdi, [rsp+350h+propvarIn+8]
0x1800c78af  add     rdi, rcx
0x1800c78b2  add     rdx, 3Dh ; '='
0x1800c78b6  add     rdi, rdx
0x1800c78b9  mov     [rbp+250h+pv], r13
0x1800c78bd  mov     [rbp+250h+var_288], r13
0x1800c78c1  xor     ecx, ecx; pv
0x1800c78c3  call    cs:__imp_CoTaskMemFree
0x1800c78c9  lea     rax, [rbp+250h+pv]
0x1800c78cd  mov     qword ptr [rsp+350h+cchDest], rax
0x1800c78d2  mov     r9, rdi
0x1800c78d5  xor     r8d, r8d
0x1800c78d8  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800c78dd  mov     ebx, eax
0x1800c78df  xor     ecx, ecx; pv
0x1800c78e1  call    cs:__imp_CoTaskMemFree
0x1800c78e7  mov     r15, [rbp+250h+pv]
0x1800c78eb  test    ebx, ebx
0x1800c78ed  js      loc_1800C773A
0x1800c78f3  test    r14, r14
0x1800c78f6  jz      loc_1800C7682
0x1800c78fc  cmp     word ptr [r14], 0
0x1800c7901  jz      loc_1800C7682
0x1800c7907  mov     r8, r14; unsigned __int16 *
0x1800c790a  mov     rdx, rdi; unsigned __int64
0x1800c790d  mov     rcx, r15; unsigned __int16 *
  ... truncated ...
```
