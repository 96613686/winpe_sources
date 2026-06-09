# ApplySettings::AddCondition(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ISdoCollection *)

- ea: `0x180042d5c`
- end: `0x1800430f1`
- name: `?AddCondition@ApplySettings@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAUISdoCollection@@@Z`
- size: `917`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004520c`

## callees

- `0x180024cac`
- `0x18002cd74`
- `0x180042a80`
- `0x180042c98`
- `0x180042d5c`
- `0x180043d8c`
- `0x1800471b4`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180042dea`
- `KERNEL32!GetLastError` at `0x180042eea`
- `KERNEL32!GetLastError` at `0x180042f85`
- `KERNEL32!GetLastError` at `0x180043047`
- `KERNEL32!GetLastError` at `0x180042dea`
- `KERNEL32!GetLastError` at `0x180042eea`
- `KERNEL32!GetLastError` at `0x180042f85`
- `KERNEL32!GetLastError` at `0x180043047`
- `ole32!StringFromGUID2` at `0x180042db4`
- `ole32!StringFromGUID2` at `0x180042db4`
- `OLEAUT32!__imp_SysAllocString` at `0x180042dc5`
- `OLEAUT32!__imp_SysAllocString` at `0x180042dc5`
- `OLEAUT32!__imp_SysFreeString` at `0x180042ee0`
- `OLEAUT32!__imp_SysFreeString` at `0x180042ee0`
- `OLEAUT32!__imp_VariantInit` at `0x180043009`
- `OLEAUT32!__imp_VariantInit` at `0x180043009`
- `OLEAUT32!__imp_VariantClear` at `0x18004303d`
- `OLEAUT32!__imp_VariantClear` at `0x18004303d`
- `RPCRT4!UuidCreate` at `0x180042da0`
- `RPCRT4!UuidCreate` at `0x180042da0`

## string_xrefs

- `0x180042e47`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180042f47`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180042fe2`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180043098`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplySettings::AddCondition(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  OLECHAR *v7; // rbx
  unsigned int v8; // edi
  signed int LastError; // eax
  char v10; // bl
  const char *v11; // rsi
  int v12; // r8d
  int v13; // r9d
  int v14; // edx
  signed int v15; // eax
  signed int v16; // eax
  __int64 v17; // rcx
  signed int v18; // eax
  __int16 v20; // [rsp+30h] [rbp-69h] BYREF
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-61h] BYREF
  __int64 v22; // [rsp+40h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-51h] BYREF
  UUID Uuid; // [rsp+60h] [rbp-39h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-29h] BYREF

  ATL::CComPtr<IDispatch>::CComPtr<IDispatch>(&v21);
  Uuid = 0;
  UuidCreate(&Uuid);
  StringFromGUID2(&Uuid, sz, 40);
  v20 = -1;
  v7 = SysAllocString(sz);
  v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int16 *))(*(_QWORD *)a4 + 96LL))(a4, v7, &v20);
  if ( v8 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v10 = LastError;
    }
    else
    {
      v10 = 5;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v11 = "pColl->IsNameUnique";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
      v14 = 70;
LABEL_43:
      WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v12, v13, (__int64)v11, v10);
    }
  }
  else if ( v20 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD))(*(_QWORD *)a4 + 64LL))(a4, v7, &v21);
    SysFreeString(v7);
    if ( v8 )
    {
      v15 = GetLastError();
      v10 = v15;
      if ( v15 )
      {
        if ( v15 > 0 )
          v10 = v15;
      }
      else
      {
        v10 = 5;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v11 = "pColl->Add";
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
        v14 = 72;
        goto LABEL_43;
      }
    }
    else
    {
      v22 = 0;
      v8 = (**v21)(v21, &IID_ISdo, &v22);
      if ( v8 )
      {
        v16 = GetLastError();
        v10 = v16;
        if ( v16 )
        {
          if ( v16 > 0 )
            v10 = v16;
        }
        else
        {
          v10 = 5;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v11 = "QI(ISdo)";
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
          v14 = 73;
          goto LABEL_43;
        }
      }
      else
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        ApplySettings::GetVariant(v17, a3, a2, &pvarg);
        v8 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v22 + 72LL))(v22, 1024, &pvarg);
        VariantClear(&pvarg);
        if ( v8 )
        {
          v18 = GetLastError();
          v10 = v18;
          if ( v18 )
          {
            if ( v18 > 0 )
              v10 = v18;
          }
          else
          {
            v10 = 5;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v11 = "Condition pSdo->PutProperty";
            WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
            v14 = 74;
            goto LABEL_43;
          }
        }
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Name %S is not unique");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        (unsigned int)&WPP_70cc9e363f77355498ae630336bd681a_Traceguids,
        (unsigned int)"NPSDS",
        (__int64)v7);
    }
    v8 = -2147024809;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  return v8;
}

```

## disassembly

```asm
0x180042d5c  mov     [rsp-8+arg_0], rbx
0x180042d61  push    rbp
0x180042d62  push    rsi
0x180042d63  push    rdi
0x180042d64  push    r14
0x180042d66  push    r15
0x180042d68  lea     rbp, [rsp-37h]
0x180042d6d  sub     rsp, 0D0h
0x180042d74  mov     rax, cs:__security_cookie
0x180042d7b  xor     rax, rsp
0x180042d7e  mov     [rbp+57h+var_30], rax
0x180042d82  mov     rsi, r9
0x180042d85  mov     r15, r8
0x180042d88  mov     r14, rdx
0x180042d8b  lea     rcx, [rbp+57h+var_B8]
0x180042d8f  call    ??0?$CComPtr@UIDispatch@@@ATL@@QEAA@XZ; ATL::CComPtr<IDispatch>::CComPtr<IDispatch>(void)
0x180042d94  nop
0x180042d95  xorps   xmm0, xmm0
0x180042d98  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180042d9c  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180042da0  call    cs:__imp_UuidCreate
0x180042da6  mov     r8d, 28h ; '('; cchMax
0x180042dac  lea     rdx, [rbp+57h+sz]; lpsz
0x180042db0  lea     rcx, [rbp+57h+Uuid]; rguid
0x180042db4  call    cs:__imp_StringFromGUID2
0x180042dba  or      eax, 0FFFFFFFFh
0x180042dbd  mov     [rbp+57h+var_C0], ax
0x180042dc1  lea     rcx, [rbp+57h+sz]; psz
0x180042dc5  call    cs:__imp_SysAllocString
0x180042dcb  mov     rbx, rax
0x180042dce  mov     rcx, [rsi]
0x180042dd1  mov     rax, [rcx+60h]
0x180042dd5  lea     r8, [rbp+57h+var_C0]
0x180042dd9  mov     rdx, rbx
0x180042ddc  mov     rcx, rsi
0x180042ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042de4  mov     edi, eax
0x180042de6  test    eax, eax
0x180042de8  jz      short loc_180042E5D
0x180042dea  call    cs:__imp_GetLastError
0x180042df0  mov     ebx, eax
0x180042df2  test    eax, eax
0x180042df4  jz      short loc_180042E03
0x180042df6  jle     short loc_180042E08
0x180042df8  movzx   ebx, ax
0x180042dfb  or      ebx, 80070000h
0x180042e01  jmp     short loc_180042E08
0x180042e03  mov     ebx, 80004005h
0x180042e08  lea     rax, WPP_GLOBAL_Control
0x180042e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e16  cmp     rcx, rax
0x180042e19  jz      loc_1800430C3
0x180042e1f  cmp     byte ptr [rcx+19h], 2
0x180042e23  jb      loc_1800430C3
0x180042e29  test    byte ptr [rcx+1Ch], 10h
0x180042e2d  jz      loc_1800430C3
0x180042e33  mov     r9d, ebx
0x180042e36  lea     rsi, aPcollIsnameuni; "pColl->IsNameUnique"
0x180042e3d  mov     r8, rsi
0x180042e40  lea     rdx, aNpsds; "NPSDS"
0x180042e47  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180042e4e  call    WppDbgPrint
0x180042e53  mov     edx, 46h ; 'F'
0x180042e58  jmp     loc_1800430A9
0x180042e5d  xor     eax, eax
0x180042e5f  cmp     ax, [rbp+57h+var_C0]
0x180042e63  jnz     short loc_180042EC5
0x180042e65  lea     rax, WPP_GLOBAL_Control
0x180042e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e73  cmp     rcx, rax
0x180042e76  jz      short loc_180042EBB
0x180042e78  cmp     byte ptr [rcx+19h], 2
0x180042e7c  jb      short loc_180042EBB
0x180042e7e  test    byte ptr [rcx+1Ch], 10h
0x180042e82  jz      short loc_180042EBB
0x180042e84  mov     rdx, rbx
0x180042e87  lea     rcx, aNameSIsNotUniq; "Name %S is not unique"
0x180042e8e  call    WppDbgPrint
0x180042e93  mov     edx, 47h ; 'G'
0x180042e98  mov     [rsp+0F0h+var_D0], rbx
0x180042e9d  lea     r9, aNpsds; "NPSDS"
0x180042ea4  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x180042eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180042eb2  mov     rcx, [rcx+10h]
0x180042eb6  call    WPP_SF_sS
0x180042ebb  mov     edi, 80070057h
0x180042ec0  jmp     loc_1800430C3
0x180042ec5  mov     rax, [rsi]
0x180042ec8  lea     r8, [rbp+57h+var_B8]
0x180042ecc  mov     rdx, rbx
0x180042ecf  mov     rcx, rsi
0x180042ed2  mov     rax, [rax+40h]
0x180042ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042edb  mov     edi, eax
0x180042edd  mov     rcx, rbx; bstrString
0x180042ee0  call    cs:__imp_SysFreeString
0x180042ee6  test    edi, edi
0x180042ee8  jz      short loc_180042F5D
0x180042eea  call    cs:__imp_GetLastError
0x180042ef0  mov     ebx, eax
0x180042ef2  test    eax, eax
0x180042ef4  jz      short loc_180042F03
0x180042ef6  jle     short loc_180042F08
0x180042ef8  movzx   ebx, ax
0x180042efb  or      ebx, 80070000h
0x180042f01  jmp     short loc_180042F08
0x180042f03  mov     ebx, 80004005h
0x180042f08  lea     rax, WPP_GLOBAL_Control
0x180042f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042f16  cmp     rcx, rax
0x180042f19  jz      loc_1800430C3
0x180042f1f  cmp     byte ptr [rcx+19h], 2
0x180042f23  jb      loc_1800430C3
0x180042f29  test    byte ptr [rcx+1Ch], 10h
0x180042f2d  jz      loc_1800430C3
0x180042f33  mov     r9d, ebx
0x180042f36  lea     rsi, aPcollAdd; "pColl->Add"
0x180042f3d  mov     r8, rsi
0x180042f40  lea     rdx, aNpsds; "NPSDS"
0x180042f47  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180042f4e  call    WppDbgPrint
0x180042f53  mov     edx, 48h ; 'H'
0x180042f58  jmp     loc_1800430A9
0x180042f5d  mov     [rbp+57h+var_B0], 0
0x180042f65  mov     rcx, [rbp+57h+var_B8]
0x180042f69  mov     rax, [rcx]
0x180042f6c  lea     r8, [rbp+57h+var_B0]
0x180042f70  lea     rdx, IID_ISdo
0x180042f77  mov     rax, [rax]
0x180042f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f7f  mov     edi, eax
0x180042f81  test    eax, eax
0x180042f83  jz      short loc_180042FF8
0x180042f85  call    cs:__imp_GetLastError
0x180042f8b  mov     ebx, eax
0x180042f8d  test    eax, eax
0x180042f8f  jz      short loc_180042F9E
0x180042f91  jle     short loc_180042FA3
0x180042f93  movzx   ebx, ax
0x180042f96  or      ebx, 80070000h
0x180042f9c  jmp     short loc_180042FA3
0x180042f9e  mov     ebx, 80004005h
0x180042fa3  lea     rax, WPP_GLOBAL_Control
0x180042faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180042fb1  cmp     rcx, rax
0x180042fb4  jz      loc_1800430C3
0x180042fba  cmp     byte ptr [rcx+19h], 2
0x180042fbe  jb      loc_1800430C3
0x180042fc4  test    byte ptr [rcx+1Ch], 10h
0x180042fc8  jz      loc_1800430C3
0x180042fce  mov     r9d, ebx
0x180042fd1  lea     rsi, aQiIsdo; "QI(ISdo)"
0x180042fd8  mov     r8, rsi
0x180042fdb  lea     rdx, aNpsds; "NPSDS"
0x180042fe2  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180042fe9  call    WppDbgPrint
0x180042fee  mov     edx, 49h ; 'I'
0x180042ff3  jmp     loc_1800430A9
0x180042ff8  xorps   xmm0, xmm0
0x180042ffb  xor     eax, eax
0x180042ffd  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180043001  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180043005  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180043009  call    cs:__imp_VariantInit
0x18004300f  lea     r9, [rbp+57h+pvarg]
0x180043013  mov     r8, r14
0x180043016  mov     rdx, r15
0x180043019  call    ?GetVariant@ApplySettings@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAUtagVARIANT@@@Z; ApplySettings::GetVariant(std::wstring &,std::wstring &,tagVARIANT &)
0x18004301e  mov     rcx, [rbp+57h+var_B0]
0x180043022  mov     rax, [rcx]
0x180043025  lea     r8, [rbp+57h+pvarg]
0x180043029  mov     edx, 400h
0x18004302e  mov     rax, [rax+48h]
0x180043032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043037  mov     edi, eax
0x180043039  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004303d  call    cs:__imp_VariantClear
0x180043043  test    edi, edi
0x180043045  jz      short loc_1800430C3
0x180043047  call    cs:__imp_GetLastError
0x18004304d  mov     ebx, eax
0x18004304f  test    eax, eax
0x180043051  jz      short loc_180043060
0x180043053  jle     short loc_180043065
0x180043055  movzx   ebx, ax
0x180043058  or      ebx, 80070000h
0x18004305e  jmp     short loc_180043065
0x180043060  mov     ebx, 80004005h
0x180043065  lea     rax, WPP_GLOBAL_Control
0x18004306c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043073  cmp     rcx, rax
0x180043076  jz      short loc_1800430C3
0x180043078  cmp     byte ptr [rcx+19h], 2
0x18004307c  jb      short loc_1800430C3
0x18004307e  test    byte ptr [rcx+1Ch], 10h
0x180043082  jz      short loc_1800430C3
0x180043084  mov     r9d, ebx
0x180043087  lea     rsi, aConditionPsdoP; "Condition pSdo->PutProperty"
0x18004308e  mov     r8, rsi
0x180043091  lea     rdx, aNpsds; "NPSDS"
0x180043098  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18004309f  call    WppDbgPrint
0x1800430a4  mov     edx, 4Ah ; 'J'
0x1800430a9  mov     [rsp+0F0h+var_C8], ebx
0x1800430ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800430b4  mov     [rsp+0F0h+var_D0], rsi
0x1800430b9  mov     rcx, [rcx+10h]
0x1800430bd  call    WPP_SF_ssd
0x1800430c2  nop
0x1800430c3  lea     rcx, [rbp+57h+var_B8]
0x1800430c7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800430cc  mov     eax, edi
0x1800430ce  mov     rcx, [rbp+57h+var_30]
0x1800430d2  xor     rcx, rsp; StackCookie
0x1800430d5  call    __security_check_cookie
0x1800430da  mov     rbx, [rsp+0F0h+arg_0]
0x1800430e2  add     rsp, 0D0h
0x1800430e9  pop     r15
0x1800430eb  pop     r14
0x1800430ed  pop     rdi
0x1800430ee  pop     rsi
0x1800430ef  pop     rbp
0x1800430f0  retn
```
