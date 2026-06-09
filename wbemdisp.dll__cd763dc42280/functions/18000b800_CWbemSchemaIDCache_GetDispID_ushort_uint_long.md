# CWbemSchemaIDCache::GetDispID(ushort * *,uint,long *)

- ea: `0x18000b800`
- end: `0x18000bc15`
- name: `?GetDispID@CWbemSchemaIDCache@@QEAAJPEAPEAGIPEAJ@Z`
- size: `1045`
- prototype: `__int64 __fastcall(CWbemSchemaIDCache *__hidden this, unsigned __int16 **, unsigned int, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000b740`

## callees

- `0x18000b800`
- `0x18000bc20`
- `0x18000bc4c`
- `0x18000c0b0`
- `0x18000c0e0`
- `0x1800118b0`
- `0x180016fe4`
- `0x18002441c`
- `0x1800244d8`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b873`
- `msvcrt!_wcsicmp` at `0x18000b873`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b836`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b970`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b836`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b970`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b887`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ba50`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b887`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ba50`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000bbc5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000bbdc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000bbc5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000bbdc`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CWbemSchemaIDCache::GetDispID(
        CWbemSchemaIDCache *this,
        const OLECHAR **a2,
        unsigned int a3,
        int *a4)
{
  __int64 v7; // rcx
  wchar_t *v8; // rbx
  __int64 *v9; // rdi
  __int64 *v10; // rsi
  __int64 *v11; // rsi
  const wchar_t *v12; // rdx
  int v13; // eax
  __int64 v14; // rbx
  bool v15; // si
  const OLECHAR *v16; // rcx
  wchar_t **v17; // rbx
  unsigned int v18; // edi
  int v19; // ebx
  int v20; // ebx
  __int64 v21; // r8
  int v23; // eax
  __int64 v24; // rax
  unsigned int v25; // esi
  char Method; // al
  int *v27; // rbx
  char v28; // al
  unsigned __int64 v29; // rax
  __int64 v30; // rcx
  __int64 *v31; // r8
  wchar_t **v32; // rdx
  char v33; // dl
  int v34; // [rsp+20h] [rbp-69h]
  char v35; // [rsp+40h] [rbp-49h]
  char v36; // [rsp+41h] [rbp-48h]
  int v37; // [rsp+44h] [rbp-45h] BYREF
  wchar_t **v38; // [rsp+48h] [rbp-41h] BYREF
  int v39; // [rsp+50h] [rbp-39h]
  __int64 v40[2]; // [rsp+58h] [rbp-31h] BYREF
  BSTR bstrString[2]; // [rsp+68h] [rbp-21h] BYREF
  int v42; // [rsp+78h] [rbp-11h]
  SAFEARRAY *psa; // [rsp+80h] [rbp-9h] BYREF
  SAFEARRAY *v44; // [rsp+88h] [rbp-1h] BYREF
  __int64 v45; // [rsp+90h] [rbp+7h] BYREF
  BSTR v46[9]; // [rsp+98h] [rbp+Fh] BYREF
  int v47; // [rsp+100h] [rbp+77h] BYREF
  int *v48; // [rsp+108h] [rbp+7Fh]

  v48 = a4;
  if ( !a3 )
    return 2147500037LL;
  v8 = SysAllocString(*a2);
  v40[0] = (__int64)v8;
  v9 = (__int64 *)*((_QWORD *)this + 2);
  v10 = (__int64 *)v9[1];
  while ( !*((_BYTE *)v10 + 25) )
  {
    if ( (unsigned __int8)BSTRless::operator()(v7, v10 + 4, v40) )
    {
      v10 = (__int64 *)v10[2];
    }
    else
    {
      v9 = v10;
      v10 = (__int64 *)*v10;
    }
  }
  v11 = (__int64 *)*((_QWORD *)this + 2);
  if ( v9 != v11 )
  {
    if ( !v8
      || (v12 = (const wchar_t *)v9[4]) != 0
      && (v13 = _wcsicmp(v8, v12), v11 = (__int64 *)*((_QWORD *)this + 2), v13 <= 0) )
    {
      v11 = v9;
    }
  }
  SysFreeString(v8);
  if ( v11 != *((__int64 **)this + 2) )
  {
    *v48 = *((_DWORD *)v11 + 12);
    return 0;
  }
  if ( a3 == 1 && (v14 = *((_QWORD *)this + 4)) != 0 )
  {
    v15 = 0;
    v16 = *a2;
    v40[0] = (__int64)*a2;
    v17 = *(wchar_t ***)(v14 + 16);
    v38 = v17;
    if ( v17 )
    {
      (*((void (__fastcall **)(wchar_t **))*v17 + 1))(v17);
      v16 = (const OLECHAR *)v40[0];
    }
    v18 = 0;
    if ( v17 )
    {
      v47 = 0;
      if ( (*((int (__fastcall **)(wchar_t **, const OLECHAR *, _QWORD, _QWORD, _QWORD, int *))*v17 + 4))(
             v17,
             v16,
             0,
             0,
             0,
             &v47) >= 0 )
        v15 = (v47 & 0x40) == 0;
    }
    if ( v17 )
      (*((void (__fastcall **)(wchar_t **))*v17 + 2))(v17);
    if ( v15 )
    {
      v38 = (wchar_t **)&CWbemDispID::`vftable';
      v39 = 0;
      v19 = ++*((_DWORD *)this + 2);
      if ( v19 > 0x7FFFFF )
      {
        return (unsigned int)-2147467259;
      }
      else
      {
        v20 = v19 | 0x1800000;
        v39 = v20;
        *v48 = v20;
        bstrString[0] = SysAllocString(*a2);
        bstrString[1] = (BSTR)&CWbemDispID::`vftable';
        v42 = v20;
        LOBYTE(v34) = byte_180045B59;
        std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Insert_nohint<std::pair<ATL::CComBSTR const,CWbemDispID>,std::_Nil>(
          (char *)this + 16,
          v40,
          v21,
          bstrString,
          v34);
        SysFreeString(bstrString[0]);
      }
      return v18;
    }
  }
  else
  {
    v18 = 0;
  }
  v25 = 1;
  psa = 0;
  v44 = 0;
  v40[0] = 0;
  v45 = 0;
  v35 = 0;
  v37 = 0;
  LOBYTE(v47) = 0;
  Method = CWbemSchemaIDCache::GetMethod(
             (_DWORD)this,
             (unsigned int)*a2,
             (unsigned int)&psa,
             (unsigned int)&v44,
             (__int64)v40,
             (__int64)&v45);
  v27 = v48;
  if ( !Method )
  {
    v28 = 0;
    v33 = 0;
    goto LABEL_56;
  }
  v35 = 1;
  v36 = 1;
  v28 = 0;
  while ( v25 < a3 )
  {
    v29 = v25;
    bstrString[0] = (BSTR)v25;
    if ( psa )
    {
      v38 = (wchar_t **)&a2[v25];
      if ( CWbemSchemaIDCache::FindMemberInArray(*v38, psa) )
      {
        v31 = v40;
        v32 = v38;
LABEL_42:
        if ( (unsigned __int8)CWbemSchemaIDCache::GetIdOfMethodParameter(v30, *v32, v31, &v37) )
          v27[(__int64)bstrString[0]] = v37;
        else
          v36 = 0;
        v28 = v47;
        goto LABEL_51;
      }
      v29 = (unsigned __int64)bstrString[0];
    }
    else
    {
      bstrString[0] = (BSTR)v25;
    }
    if ( v44 )
    {
      v38 = (wchar_t **)&a2[v29];
      if ( CWbemSchemaIDCache::FindMemberInArray(*v38, v44) )
      {
        v31 = &v45;
        v32 = v38;
        goto LABEL_42;
      }
      v29 = (unsigned __int64)bstrString[0];
    }
    v27[v29] = -1;
    v28 = 1;
    LOBYTE(v47) = 1;
LABEL_51:
    ++v25;
    if ( !v36 )
    {
      v33 = 0;
      v35 = 0;
      LOBYTE(v47) = v28;
      goto LABEL_56;
    }
  }
  v33 = 1;
LABEL_56:
  if ( psa )
  {
    SafeArrayDestroy(psa);
    v28 = v47;
    v33 = v35;
  }
  if ( v44 )
  {
    SafeArrayDestroy(v44);
    v28 = v47;
    v33 = v35;
  }
  if ( v33 )
  {
    if ( v28 )
    {
      v18 = -2147352570;
    }
    else
    {
      v38 = (wchar_t **)&CWbemDispID::`vftable';
      v39 = 0;
      v23 = ++*((_DWORD *)this + 2);
      if ( v23 > 0x7FFFFF )
      {
        v18 = -2147467259;
      }
      else
      {
        v39 = v23 | 0x1000000;
        *v27 = v23 | 0x1000000;
        v24 = std::pair<ATL::CComBSTR const,CWbemDispID>::pair<ATL::CComBSTR const,CWbemDispID>(v46, a2, &v38);
        std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::insert(
          (char *)this + 16,
          bstrString,
          v24);
        v46[1] = (BSTR)&CWbemDispID::`vftable';
        SysFreeString(v46[0]);
      }
    }
  }
  else
  {
    v18 = -2147467259;
  }
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v45);
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(v40);
  return v18;
}

```

## disassembly

```asm
0x18000b800  mov     [rsp-8+arg_0], rbx
0x18000b805  mov     [rsp-8+arg_18], r9
0x18000b80a  push    rbp
0x18000b80b  push    rsi
0x18000b80c  push    rdi
0x18000b80d  push    r12
0x18000b80f  push    r13
0x18000b811  push    r14
0x18000b813  push    r15
0x18000b815  lea     rbp, [rsp-27h]
0x18000b81a  sub     rsp, 0B0h
0x18000b821  mov     r13d, r8d
0x18000b824  mov     r12, rdx
0x18000b827  mov     r14, rcx
0x18000b82a  test    r8d, r8d
0x18000b82d  jz      loc_18000B9EE
0x18000b833  mov     rcx, [rdx]; psz
0x18000b836  call    cs:__imp_SysAllocString
0x18000b83c  mov     rbx, rax
0x18000b83f  mov     [rbp+57h+var_88], rax
0x18000b843  mov     rdi, [r14+10h]
0x18000b847  mov     rsi, [rdi+8]
0x18000b84b  cmp     byte ptr [rsi+19h], 0
0x18000b84f  jz      loc_18000BA71
0x18000b855  mov     rsi, [r14+10h]
0x18000b859  cmp     rdi, rsi
0x18000b85c  jz      short loc_18000B884
0x18000b85e  test    rbx, rbx
0x18000b861  jz      short loc_18000B881
0x18000b863  mov     rdx, [rdi+20h]; String2
0x18000b867  test    rdx, rdx
0x18000b86a  jz      loc_18000B9D5
0x18000b870  mov     rcx, rbx; String1
0x18000b873  call    cs:__imp__wcsicmp
0x18000b879  mov     rsi, [r14+10h]
0x18000b87d  test    eax, eax
0x18000b87f  jg      short loc_18000B884
0x18000b881  mov     rsi, rdi
0x18000b884  mov     rcx, rbx; bstrString
0x18000b887  call    cs:__imp_SysFreeString
0x18000b88d  cmp     rsi, [r14+10h]
0x18000b891  jnz     loc_18000B9C6
0x18000b897  cmp     r13d, 1
0x18000b89b  jnz     loc_18000BA99
0x18000b8a1  mov     rbx, [r14+20h]
0x18000b8a5  test    rbx, rbx
0x18000b8a8  jz      loc_18000BA99
0x18000b8ae  xor     sil, sil
0x18000b8b1  mov     rcx, [r12]
0x18000b8b5  mov     [rbp+57h+var_88], rcx
0x18000b8b9  mov     rbx, [rbx+10h]
0x18000b8bd  mov     [rbp+57h+var_98], rbx
0x18000b8c1  test    rbx, rbx
0x18000b8c4  jz      short loc_18000B8D9
0x18000b8c6  mov     rax, [rbx]
0x18000b8c9  mov     rcx, rbx
0x18000b8cc  mov     rax, [rax+8]
0x18000b8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8d5  mov     rcx, [rbp+57h+var_88]
0x18000b8d9  xor     edi, edi
0x18000b8db  test    rbx, rbx
0x18000b8de  jz      short loc_18000B91D
0x18000b8e0  mov     [rbp+57h+arg_10], edi
0x18000b8e3  mov     rax, [rbx]
0x18000b8e6  lea     rdx, [rbp+57h+arg_10]
0x18000b8ea  mov     [rsp+0E0h+var_B8], rdx
0x18000b8ef  mov     [rsp+0E0h+var_C0], rdi
0x18000b8f4  xor     r9d, r9d
0x18000b8f7  xor     r8d, r8d
0x18000b8fa  mov     rdx, rcx
0x18000b8fd  mov     rcx, rbx
0x18000b900  mov     rax, [rax+20h]
0x18000b904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b909  test    eax, eax
0x18000b90b  js      short loc_18000B91D
0x18000b90d  test    byte ptr [rbp+57h+arg_10], 40h
0x18000b911  movzx   esi, sil
0x18000b915  mov     eax, 1
0x18000b91a  cmovz   esi, eax
0x18000b91d  test    rbx, rbx
0x18000b920  jz      short loc_18000B932
0x18000b922  mov     rax, [rbx]
0x18000b925  mov     rcx, rbx
0x18000b928  mov     rax, [rax+10h]
0x18000b92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b931  nop
0x18000b932  test    sil, sil
0x18000b935  jz      loc_18000BA9B
0x18000b93b  lea     rsi, ??_7CWbemDispID@@6B@; const CWbemDispID::`vftable'
0x18000b942  mov     [rbp+57h+var_98], rsi
0x18000b946  mov     [rbp+57h+var_90], edi
0x18000b949  inc     dword ptr [r14+8]
0x18000b94d  mov     ebx, [r14+8]
0x18000b951  cmp     ebx, 7FFFFFh
0x18000b957  jg      loc_18000B9F5
0x18000b95d  or      ebx, 1800000h
0x18000b963  mov     [rbp+57h+var_90], ebx
0x18000b966  mov     rax, [rbp+57h+arg_18]
0x18000b96a  mov     [rax], ebx
0x18000b96c  mov     rcx, [r12]; psz
0x18000b970  call    cs:__imp_SysAllocString
0x18000b976  mov     [rbp+57h+bstrString], rax
0x18000b97a  mov     [rbp+57h+var_70], rsi
0x18000b97e  mov     [rbp+57h+var_68], ebx
0x18000b981  movzx   eax, cs:byte_180045B59
0x18000b988  mov     byte ptr [rsp+0E0h+var_C0], al
0x18000b98c  lea     r9, [rbp+57h+bstrString]
0x18000b990  lea     rdx, [rbp+57h+var_88]
0x18000b994  lea     rcx, [r14+10h]
0x18000b998  call    ??$_Insert_nohint@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@U_Nil@2@@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCWbemDispID@@UBSTRless@@V?$CWbemAllocator@VCWbemDispID@@@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@@std@@@std@@@std@@_N@1@_N$$QEAU?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@1@U_Nil@1@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::_Insert_nohint<std::pair<ATL::CComBSTR const,CWbemDispID>,std::_Nil>(bool,std::pair<ATL::CComBSTR const,CWbemDispID> &&,std::_Nil)
0x18000b99d  nop
0x18000b99e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000b9a2  call    cs:__imp_SysFreeString
0x18000b9a8  nop
0x18000b9a9  mov     eax, edi
0x18000b9ab  mov     rbx, [rsp+0E0h+arg_0]
0x18000b9b3  add     rsp, 0B0h
0x18000b9ba  pop     r15
0x18000b9bc  pop     r14
0x18000b9be  pop     r13
0x18000b9c0  pop     r12
0x18000b9c2  pop     rdi
0x18000b9c3  pop     rsi
0x18000b9c4  pop     rbp
0x18000b9c5  retn
0x18000b9c6  xor     edi, edi
0x18000b9c8  mov     ecx, [rsi+30h]
0x18000b9cb  mov     rax, [rbp+57h+arg_18]
0x18000b9cf  mov     [rax], ecx
0x18000b9d1  mov     eax, edi
0x18000b9d3  jmp     short loc_18000B9AB
0x18000b9d5  test    rbx, rbx
0x18000b9d8  jz      loc_18000B881
0x18000b9de  cmp     qword ptr [rdi+20h], 0
0x18000b9e3  jz      loc_18000B884
0x18000b9e9  jmp     loc_18000B881
0x18000b9ee  mov     eax, 80004005h
0x18000b9f3  jmp     short loc_18000B9AB
0x18000b9f5  mov     edi, 80004005h
0x18000b9fa  jmp     short loc_18000B9A9
0x18000b9fc  lea     rsi, ??_7CWbemDispID@@6B@; const CWbemDispID::`vftable'
0x18000ba03  mov     [rbp+57h+var_98], rsi
0x18000ba07  mov     [rbp+57h+var_90], edi
0x18000ba0a  inc     dword ptr [r14+8]
0x18000ba0e  mov     eax, [r14+8]
0x18000ba12  cmp     eax, 7FFFFFh
0x18000ba17  jg      loc_18000BC0A
0x18000ba1d  bts     eax, 18h
0x18000ba21  mov     [rbp+57h+var_90], eax
0x18000ba24  mov     [rbx], eax
0x18000ba26  lea     r8, [rbp+57h+var_98]
0x18000ba2a  mov     rdx, r12
0x18000ba2d  lea     rcx, [rbp+57h+var_48]
0x18000ba31  call    ??$?0AEAPEAGAEAVCWbemDispID@@@?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@QEAA@AEAPEAGAEAVCWbemDispID@@PEAPEAX@Z; std::pair<ATL::CComBSTR const,CWbemDispID>::pair<ATL::CComBSTR const,CWbemDispID>(ushort * &,CWbemDispID &,void * *)
0x18000ba36  nop
0x18000ba37  mov     r8, rax
0x18000ba3a  lea     rdx, [rbp+57h+bstrString]
0x18000ba3e  lea     rcx, [r14+10h]
0x18000ba42  call    ?insert@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCWbemDispID@@UBSTRless@@V?$CWbemAllocator@VCWbemDispID@@@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CWbemDispID,BSTRless,CWbemAllocator<CWbemDispID>,0>>::insert(std::pair<ATL::CComBSTR const,CWbemDispID> &&)
0x18000ba47  nop
0x18000ba48  mov     [rbp+57h+var_40], rsi
0x18000ba4c  mov     rcx, [rbp+57h+var_48]; bstrString
0x18000ba50  call    cs:__imp_SysFreeString
0x18000ba56  nop
0x18000ba57  lea     rcx, [rbp+57h+var_50]
0x18000ba5b  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18000ba60  nop
0x18000ba61  lea     rcx, [rbp+57h+var_88]
0x18000ba65  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18000ba6a  mov     eax, edi
0x18000ba6c  jmp     loc_18000B9AB
0x18000ba71  lea     rdx, [rsi+20h]
0x18000ba75  lea     r8, [rbp+57h+var_88]
0x18000ba79  call    ??RBSTRless@@QEBA_NAEBVCComBSTR@ATL@@0@Z; BSTRless::operator()(ATL::CComBSTR const &,ATL::CComBSTR const &)
0x18000ba7e  test    al, al
0x18000ba80  jz      short loc_18000BA88
0x18000ba82  mov     rsi, [rsi+10h]
0x18000ba86  jmp     short loc_18000BA8E
0x18000ba88  mov     rdi, rsi
0x18000ba8b  mov     rsi, [rsi]
0x18000ba8e  cmp     byte ptr [rsi+19h], 0
0x18000ba92  jz      short loc_18000BA71
0x18000ba94  jmp     loc_18000B855
0x18000ba99  xor     edi, edi
0x18000ba9b  mov     esi, 1
0x18000baa0  mov     [rbp+57h+psa], rdi
0x18000baa4  mov     [rbp+57h+var_58], rdi
0x18000baa8  mov     [rbp+57h+var_88], rdi
0x18000baac  mov     [rbp+57h+var_50], rdi
0x18000bab0  mov     [rbp+57h+var_A0], 0
0x18000bab4  mov     [rbp+57h+var_9C], edi
0x18000bab7  mov     byte ptr [rbp+57h+arg_10], 0
0x18000babb  lea     rax, [rbp+57h+var_50]
0x18000babf  mov     [rsp+0E0h+var_B8], rax
0x18000bac4  lea     rax, [rbp+57h+var_88]
0x18000bac8  mov     [rsp+0E0h+var_C0], rax
0x18000bacd  lea     r9, [rbp+57h+var_58]
0x18000bad1  lea     r8, [rbp+57h+psa]
0x18000bad5  mov     rdx, [r12]
0x18000bad9  mov     rcx, r14
0x18000badc  call    ?GetMethod@CWbemSchemaIDCache@@AEAA_NPEAGPEAPEAUtagSAFEARRAY@@1AEAV?$CComPtr@UIWbemClassObject@@@ATL@@2@Z; CWbemSchemaIDCache::GetMethod(ushort *,tagSAFEARRAY * *,tagSAFEARRAY * *,ATL::CComPtr<IWbemClassObject> &,ATL::CComPtr<IWbemClassObject> &)
0x18000bae1  mov     rbx, [rbp+57h+arg_18]
0x18000bae5  test    al, al
0x18000bae7  jz      loc_18000BBB2
0x18000baed  mov     [rbp+57h+var_A0], sil
0x18000baf1  mov     [rbp+57h+var_9F], sil
0x18000baf5  xor     al, al
0x18000baf7  cmp     esi, r13d
0x18000bafa  jnb     loc_18000BBB8
0x18000bb00  mov     eax, esi
0x18000bb02  mov     [rbp+57h+bstrString], rax
0x18000bb06  mov     rcx, [rbp+57h+psa]
0x18000bb0a  test    rcx, rcx
0x18000bb0d  jz      short loc_18000BB5E
0x18000bb0f  lea     rax, [r12+rax*8]
0x18000bb13  mov     [rbp+57h+var_98], rax
0x18000bb17  mov     rdx, rcx; psa
0x18000bb1a  mov     rcx, [rax]; String2
0x18000bb1d  call    ?FindMemberInArray@CWbemSchemaIDCache@@CA_NPEAGPEAUtagSAFEARRAY@@@Z; CWbemSchemaIDCache::FindMemberInArray(ushort *,tagSAFEARRAY *)
0x18000bb22  test    al, al
0x18000bb24  jz      short loc_18000BB58
0x18000bb26  lea     r8, [rbp+57h+var_88]
0x18000bb2a  mov     rdx, [rbp+57h+var_98]
0x18000bb2e  jmp     short loc_18000BB38
0x18000bb30  lea     r8, [rbp+57h+var_50]
0x18000bb34  mov     rdx, [rbp+57h+var_98]
0x18000bb38  lea     r9, [rbp+57h+var_9C]
0x18000bb3c  mov     rdx, [rdx]
0x18000bb3f  call    ?GetIdOfMethodParameter@CWbemSchemaIDCache@@AEAA_NPEAGAEAV?$CComPtr@UIWbemClassObject@@@ATL@@PEAJ@Z; CWbemSchemaIDCache::GetIdOfMethodParameter(ushort *,ATL::CComPtr<IWbemClassObject> &,long *)
0x18000bb44  test    al, al
0x18000bb46  jz      short loc_18000BBA8
0x18000bb48  mov     eax, [rbp+57h+var_9C]
0x18000bb4b  mov     rcx, [rbp+57h+bstrString]
0x18000bb4f  mov     [rbx+rcx*4], eax
0x18000bb52  movzx   eax, byte ptr [rbp+57h+arg_10]
0x18000bb56  jmp     short loc_18000BB92
0x18000bb58  mov     rax, [rbp+57h+bstrString]
0x18000bb5c  jmp     short loc_18000BB62
0x18000bb5e  mov     [rbp+57h+bstrString], rax
0x18000bb62  mov     rcx, [rbp+57h+var_58]
0x18000bb66  test    rcx, rcx
0x18000bb69  jz      short loc_18000BB86
0x18000bb6b  lea     rax, [r12+rax*8]
0x18000bb6f  mov     [rbp+57h+var_98], rax
0x18000bb73  mov     rdx, rcx; psa
0x18000bb76  mov     rcx, [rax]; String2
0x18000bb79  call    ?FindMemberInArray@CWbemSchemaIDCache@@CA_NPEAGPEAUtagSAFEARRAY@@@Z; CWbemSchemaIDCache::FindMemberInArray(ushort *,tagSAFEARRAY *)
0x18000bb7e  test    al, al
0x18000bb80  jnz     short loc_18000BB30
0x18000bb82  mov     rax, [rbp+57h+bstrString]
0x18000bb86  mov     dword ptr [rbx+rax*4], 0FFFFFFFFh
0x18000bb8d  mov     al, 1
0x18000bb8f  mov     byte ptr [rbp+57h+arg_10], al
0x18000bb92  inc     esi
0x18000bb94  cmp     [rbp+57h+var_9F], 0
0x18000bb98  jnz     loc_18000BAF7
0x18000bb9e  xor     dl, dl
0x18000bba0  mov     [rbp+57h+var_A0], dl
0x18000bba3  mov     byte ptr [rbp+57h+arg_10], al
0x18000bba6  jmp     short loc_18000BBBC
0x18000bba8  mov     [rbp+57h+var_9F], 0
0x18000bbac  movzx   eax, byte ptr [rbp+57h+arg_10]
0x18000bbb0  jmp     short loc_18000BB92
0x18000bbb2  xor     al, al
0x18000bbb4  xor     dl, dl
0x18000bbb6  jmp     short loc_18000BBBC
0x18000bbb8  movzx   edx, [rbp+57h+var_A0]
0x18000bbbc  mov     rcx, [rbp+57h+psa]; psa
0x18000bbc0  test    rcx, rcx
0x18000bbc3  jz      short loc_18000BBD3
0x18000bbc5  call    cs:__imp_SafeArrayDestroy
0x18000bbcb  movzx   eax, byte ptr [rbp+57h+arg_10]
0x18000bbcf  movzx   edx, [rbp+57h+var_A0]
0x18000bbd3  mov     rcx, [rbp+57h+var_58]; psa
0x18000bbd7  test    rcx, rcx
0x18000bbda  jz      short loc_18000BBEA
0x18000bbdc  call    cs:__imp_SafeArrayDestroy
0x18000bbe2  movzx   eax, byte ptr [rbp+57h+arg_10]
0x18000bbe6  movzx   edx, [rbp+57h+var_A0]
0x18000bbea  test    dl, dl
0x18000bbec  jnz     short loc_18000BBF8
0x18000bbee  mov     edi, 80004005h
0x18000bbf3  jmp     loc_18000BA57
0x18000bbf8  test    al, al
0x18000bbfa  jz      loc_18000B9FC
0x18000bc00  mov     edi, 80020006h
0x18000bc05  jmp     loc_18000BA57
0x18000bc0a  mov     edi, 80004005h
0x18000bc0f  jmp     loc_18000BA57
```
