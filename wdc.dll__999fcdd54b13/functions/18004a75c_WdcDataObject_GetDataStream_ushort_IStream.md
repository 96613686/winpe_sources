# WdcDataObject::GetDataStream(ushort,IStream *)

- ea: `0x18004a75c`
- end: `0x18004a9dd`
- name: `?GetDataStream@WdcDataObject@@AEAAJGPEAUIStream@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(WdcDataObject *__hidden this, unsigned __int16, struct IStream *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a520`
- `0x18004a5e0`

## callees

- `0x18000b854`
- `0x180019990`
- `0x18004a75c`
- `0x18004ab9c`
- `0x18004aec0`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004a88d`
- `OLEAUT32!__imp_SysAllocString` at `0x18004a88d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a878`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a9cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a878`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a9cd`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004a824`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004a824`
- `ole32!StringFromCLSID` at `0x18004a93c`
- `ole32!StringFromCLSID` at `0x18004a93c`

## pseudocode

```c
__int64 __fastcall WdcDataObject::GetDataStream(WdcDataObject *this, __int64 a2, struct IStream *a3)
{
  WdcBaseNode *v5; // rcx
  __int64 v6; // rax
  unsigned int v7; // ebx
  HRESULT ComputerNameW; // eax
  OLECHAR *v9; // rcx
  UINT v10; // eax
  __int64 v11; // r8
  LPOLESTR v12; // rdx
  OLECHAR *v13; // rax
  GUID *v14; // rdx
  __int64 v15; // r8
  OLECHAR *v16; // rax
  const IID *v17; // rax
  __int64 v19; // [rsp+20h] [rbp-20h]
  WdcDataObject *v20; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-8h] BYREF
  BSTR bstr; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v23; // [rsp+68h] [rbp+28h] BYREF
  LPOLESTR lpsz; // [rsp+78h] [rbp+38h] BYREF

  v21 = 0;
  v5 = (WdcBaseNode *)*((_QWORD *)this + 3);
  v23 = 0;
  lpsz = 0;
  bstr = 0;
  v20 = 0;
  if ( (_WORD)a2 == WdcDataObject::s_cfDisplayName || (_WORD)a2 == WdcDataObject::s_cfSZNodeType )
  {
    v15 = *(_QWORD *)v5;
    if ( (_WORD)a2 == WdcDataObject::s_cfDisplayName )
    {
      v16 = (OLECHAR *)(*(__int64 (__fastcall **)(WdcBaseNode *, _QWORD))(v15 + 8))(v5, 0);
      lpsz = v16;
      if ( !v16 )
        goto LABEL_20;
    }
    else
    {
      v17 = (const IID *)(*(__int64 (**)(void))(v15 + 16))();
      ComputerNameW = StringFromCLSID(v17, &lpsz);
      v7 = ComputerNameW;
      if ( ComputerNameW < 0 )
        goto LABEL_37;
      v16 = lpsz;
    }
    ComputerNameW = StringCbLengthW(v16, 0x7FFFFFFFu, &v21);
    v7 = ComputerNameW;
    if ( ComputerNameW < 0 )
      goto LABEL_37;
    if ( v21 + 2 < v21 )
      goto LABEL_11;
    ComputerNameW = ULongLongToULong(v21 + 2, &v23);
    v7 = ComputerNameW;
    if ( ComputerNameW < 0 )
      goto LABEL_37;
    v11 = v23;
    v12 = lpsz;
LABEL_35:
    ComputerNameW = (*(__int64 (__fastcall **)(struct IStream *, LPOLESTR, __int64, _QWORD))(*(_QWORD *)a3 + 32LL))(
                      a3,
                      v12,
                      v11,
                      0);
LABEL_36:
    v7 = ComputerNameW;
    if ( ComputerNameW >= 0 )
      goto LABEL_39;
    goto LABEL_37;
  }
  if ( (_WORD)a2 == WdcDataObject::s_cfNodeType )
  {
    v14 = (GUID *)(*(__int64 (__fastcall **)(WdcBaseNode *, __int64, WdcDataObject *))(*(_QWORD *)v5 + 16LL))(
                    v5,
                    a2,
                    this);
    goto LABEL_25;
  }
  if ( (_WORD)a2 == WdcDataObject::s_cfSnapinClsid )
  {
    v14 = &CLSID_ComponentData;
LABEL_25:
    ComputerNameW = (*(__int64 (__fastcall **)(struct IStream *, GUID *, __int64, _QWORD))(*(_QWORD *)a3 + 32LL))(
                      a3,
                      v14,
                      16,
                      0);
    goto LABEL_36;
  }
  if ( (_WORD)a2 == WdcDataObject::s_cfInternal )
  {
    v6 = *(_QWORD *)a3;
    v20 = this;
    v7 = (*(__int64 (__fastcall **)(struct IStream *, WdcDataObject **, __int64))(v6 + 32))(a3, &v20, 8);
    goto LABEL_39;
  }
  if ( (_WORD)a2 == 13 )
  {
    ComputerNameW = (*(__int64 (__fastcall **)(WdcBaseNode *, BSTR *, WdcDataObject *))(*(_QWORD *)v5 + 152LL))(
                      v5,
                      &bstr,
                      this);
    v7 = ComputerNameW;
    if ( ComputerNameW < 0 )
    {
LABEL_37:
      LODWORD(v19) = ComputerNameW;
      goto LABEL_38;
    }
    v9 = bstr;
    goto LABEL_10;
  }
  if ( (_WORD)a2 != WdcDataObject::s_cfMmcMachineName )
    return (unsigned int)-2147221404;
  ComputerNameW = WdcBaseNode::GetComputerNameW(v5, &bstr);
  v7 = ComputerNameW;
  if ( ComputerNameW < 0 )
    goto LABEL_37;
  v9 = bstr;
  if ( bstr )
  {
    if ( *bstr )
    {
LABEL_10:
      v10 = SysStringByteLen(v9);
      v11 = v10 + 2;
      if ( (unsigned int)v11 < v10 )
      {
LABEL_11:
        ComputerNameW = -2147024362;
        v7 = -2147024362;
        goto LABEL_37;
      }
      v12 = bstr;
      goto LABEL_35;
    }
    SysFreeString(bstr);
    bstr = 0;
  }
  v13 = SysAllocString(&pszTargetName);
  v9 = v13;
  if ( v13 )
  {
    bstr = v13;
    goto LABEL_10;
  }
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
    "WdcAssignString",
    0,
    L"FAILURE: 0x%08x",
    -2147024882);
LABEL_20:
  v7 = -2147024882;
  LODWORD(v19) = -2147024882;
LABEL_38:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\dataobj.cpp",
    "WdcDataObject::GetDataStream",
    0,
    L"FAILURE: 0x%08x",
    v19);
LABEL_39:
  if ( bstr )
    SysFreeString(bstr);
  return v7;
}

```

## disassembly

```asm
0x18004a75c  push    rbp
0x18004a75e  push    rbx
0x18004a75f  push    rdi
0x18004a760  mov     rbp, rsp
0x18004a763  sub     rsp, 40h
0x18004a767  movzx   eax, cs:?s_cfDisplayName@WdcDataObject@@2GA; ushort WdcDataObject::s_cfDisplayName
0x18004a76e  mov     rdi, r8
0x18004a771  mov     [rbp+var_8], 0
0x18004a779  mov     r8, rcx
0x18004a77c  mov     rcx, [rcx+18h]; this
0x18004a780  mov     [rbp+arg_8], 0
0x18004a787  mov     [rbp+lpsz], 0
0x18004a78f  mov     [rbp+bstr], 0
0x18004a797  mov     [rbp+var_10], 0
0x18004a79f  cmp     dx, ax
0x18004a7a2  jz      loc_18004A909
0x18004a7a8  cmp     dx, cs:?s_cfSZNodeType@WdcDataObject@@2GA; ushort WdcDataObject::s_cfSZNodeType
0x18004a7af  jz      loc_18004A909
0x18004a7b5  cmp     dx, cs:?s_cfNodeType@WdcDataObject@@2GA; ushort WdcDataObject::s_cfNodeType
0x18004a7bc  jz      loc_18004A8E8
0x18004a7c2  cmp     dx, cs:?s_cfSnapinClsid@WdcDataObject@@2GA; ushort WdcDataObject::s_cfSnapinClsid
0x18004a7c9  jz      loc_18004A8DF
0x18004a7cf  cmp     dx, cs:?s_cfInternal@WdcDataObject@@2GA; ushort WdcDataObject::s_cfInternal
0x18004a7d6  jnz     short loc_18004A7FD
0x18004a7d8  mov     rax, [rdi]
0x18004a7db  lea     rdx, [rbp+var_10]
0x18004a7df  xor     r9d, r9d
0x18004a7e2  mov     [rbp+var_10], r8
0x18004a7e6  mov     rcx, rdi
0x18004a7e9  mov     rax, [rax+20h]
0x18004a7ed  lea     r8d, [r9+8]
0x18004a7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7f6  mov     ebx, eax
0x18004a7f8  jmp     loc_18004A9C4
0x18004a7fd  cmp     dx, 0Dh
0x18004a801  jnz     short loc_18004A848
0x18004a803  mov     rax, [rcx]
0x18004a806  lea     rdx, [rbp+bstr]
0x18004a80a  mov     rax, [rax+98h]
0x18004a811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a816  mov     ebx, eax
0x18004a818  test    eax, eax
0x18004a81a  js      loc_18004A9A3
0x18004a820  mov     rcx, [rbp+bstr]; bstr
0x18004a824  call    cs:__imp_SysStringByteLen
0x18004a82a  lea     r8d, [rax+2]
0x18004a82e  cmp     r8d, eax
0x18004a831  jnb     short loc_18004A83F
0x18004a833  mov     eax, 80070216h
0x18004a838  mov     ebx, eax
0x18004a83a  jmp     loc_18004A9A3
0x18004a83f  mov     rdx, [rbp+bstr]
0x18004a843  jmp     loc_18004A98B
0x18004a848  cmp     dx, cs:?s_cfMmcMachineName@WdcDataObject@@2GA; ushort WdcDataObject::s_cfMmcMachineName
0x18004a84f  jnz     loc_18004A8D5
0x18004a855  lea     rdx, [rbp+bstr]; unsigned __int16 **
0x18004a859  call    ?GetComputerNameW@WdcBaseNode@@QEAAJPEAPEAG@Z; WdcBaseNode::GetComputerNameW(ushort * *)
0x18004a85e  mov     ebx, eax
0x18004a860  test    eax, eax
0x18004a862  js      loc_18004A9A3
0x18004a868  mov     rcx, [rbp+bstr]; bstrString
0x18004a86c  test    rcx, rcx
0x18004a86f  jz      short loc_18004A886
0x18004a871  xor     eax, eax
0x18004a873  cmp     ax, [rcx]
0x18004a876  jnz     short loc_18004A824
0x18004a878  call    cs:__imp_SysFreeString
0x18004a87e  mov     [rbp+bstr], 0
0x18004a886  lea     rcx, pszTargetName; psz
0x18004a88d  call    cs:__imp_SysAllocString
0x18004a893  mov     rcx, rax
0x18004a896  test    rax, rax
0x18004a899  jnz     short loc_18004A8CC
0x18004a89b  mov     edi, 8007000Eh
0x18004a8a0  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18004a8a7  xor     r8d, r8d; int
0x18004a8aa  mov     [rsp+40h+var_20], edi
0x18004a8ae  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18004a8b5  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18004a8bc  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18004a8c1  mov     ebx, edi
0x18004a8c3  mov     [rsp+40h+var_20], edi
0x18004a8c7  jmp     loc_18004A9A7
0x18004a8cc  mov     [rbp+bstr], rax
0x18004a8d0  jmp     loc_18004A824
0x18004a8d5  mov     ebx, 80040064h
0x18004a8da  jmp     loc_18004A9D3
0x18004a8df  lea     rdx, CLSID_ComponentData
0x18004a8e6  jmp     short loc_18004A8F7
0x18004a8e8  mov     rax, [rcx]
0x18004a8eb  mov     rax, [rax+10h]
0x18004a8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8f4  mov     rdx, rax
0x18004a8f7  mov     rcx, [rdi]
0x18004a8fa  mov     r8d, 10h
0x18004a900  mov     rax, [rcx+20h]
0x18004a904  jmp     loc_18004A992
0x18004a909  mov     r8, [rcx]
0x18004a90c  cmp     dx, ax
0x18004a90f  jnz     short loc_18004A92C
0x18004a911  mov     rax, [r8+8]
0x18004a915  xor     edx, edx
0x18004a917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a91c  mov     [rbp+lpsz], rax
0x18004a920  test    rax, rax
0x18004a923  jnz     short loc_18004A94C
0x18004a925  mov     edi, 8007000Eh
0x18004a92a  jmp     short loc_18004A8C1
0x18004a92c  mov     rax, [r8+10h]
0x18004a930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a935  mov     rcx, rax; rclsid
0x18004a938  lea     rdx, [rbp+lpsz]; lplpsz
0x18004a93c  call    cs:__imp_StringFromCLSID
0x18004a942  mov     ebx, eax
0x18004a944  test    eax, eax
0x18004a946  js      short loc_18004A9A3
0x18004a948  mov     rax, [rbp+lpsz]
0x18004a94c  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18004a950  mov     edx, 7FFFFFFFh; unsigned __int64
0x18004a955  mov     rcx, rax; unsigned __int16 *
0x18004a958  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004a95d  mov     ebx, eax
0x18004a95f  test    eax, eax
0x18004a961  js      short loc_18004A9A3
0x18004a963  mov     rax, [rbp+var_8]
0x18004a967  lea     rcx, [rax+2]; unsigned __int64
0x18004a96b  cmp     rcx, rax
0x18004a96e  jb      loc_18004A833
0x18004a974  lea     rdx, [rbp+arg_8]; unsigned int *
0x18004a978  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004a97d  mov     ebx, eax
0x18004a97f  test    eax, eax
0x18004a981  js      short loc_18004A9A3
0x18004a983  mov     r8d, [rbp+arg_8]
0x18004a987  mov     rdx, [rbp+lpsz]
0x18004a98b  mov     rax, [rdi]
0x18004a98e  mov     rax, [rax+20h]
0x18004a992  xor     r9d, r9d
0x18004a995  mov     rcx, rdi
0x18004a998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a99d  mov     ebx, eax
0x18004a99f  test    eax, eax
0x18004a9a1  jns     short loc_18004A9C4
0x18004a9a3  mov     [rsp+40h+var_20], eax
0x18004a9a7  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18004a9ae  xor     r8d, r8d; int
0x18004a9b1  lea     rdx, aWdcdataobjectG; "WdcDataObject::GetDataStream"
0x18004a9b8  lea     rcx, aBaseDiagnosisP_24; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18004a9bf  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18004a9c4  mov     rcx, [rbp+bstr]; bstrString
0x18004a9c8  test    rcx, rcx
0x18004a9cb  jz      short loc_18004A9D3
0x18004a9cd  call    cs:__imp_SysFreeString
0x18004a9d3  mov     eax, ebx
0x18004a9d5  add     rsp, 40h
0x18004a9d9  pop     rdi
0x18004a9da  pop     rbx
0x18004a9db  pop     rbp
0x18004a9dc  retn
```
