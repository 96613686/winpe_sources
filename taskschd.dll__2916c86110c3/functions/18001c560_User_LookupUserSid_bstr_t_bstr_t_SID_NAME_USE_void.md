# User::LookupUserSid(_bstr_t &,_bstr_t &,_SID_NAME_USE &,void *)

- ea: `0x18001c560`
- end: `0x18001c7ee`
- name: `?LookupUserSid@User@@CAHAEAV_bstr_t@@0AEAW4_SID_NAME_USE@@PEAX@Z`
- size: `654`
- prototype: `__int64 __fastcall(struct _bstr_t *this, struct _bstr_t *, enum _SID_NAME_USE *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008e40`

## callees

- `0x180007aa0`
- `0x180008d30`
- `0x18001c440`
- `0x18001c560`
- `0x180038404`
- `0x180039524`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5c1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c663`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c686`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c663`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c686`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c62b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c635`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c63e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c647`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c6ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c6df`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c70c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c716`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c62b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c635`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c63e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c647`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c6ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c6df`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c70c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c716`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001c6b7`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001c6e8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001c6b7`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001c6e8`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001c6c2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001c6f3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001c6c2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001c6f3`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001c5bb`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001c61b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001c5bb`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001c61b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall User::LookupUserSid(struct _bstr_t *this, struct _bstr_t *a2, enum _SID_NAME_USE *a3, void *a4)
{
  WCHAR *v7; // rbx
  BSTR v8; // r14
  BSTR v9; // rsi
  UINT v10; // edx
  WCHAR *v11; // rdi
  UINT v12; // edx
  unsigned int v13; // r15d
  UINT v15; // eax
  UINT v16; // eax
  volatile signed __int32 *v17; // rax
  struct IErrorInfo *v18; // rdx
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rax
  struct IErrorInfo *v21; // rdx
  volatile signed __int32 *v22; // rbx
  DWORD ui; // [rsp+30h] [rbp-38h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-34h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-30h] BYREF
  BSTR v26; // [rsp+40h] [rbp-28h]
  WCHAR *v27; // [rsp+48h] [rbp-20h]
  volatile signed __int32 *v28; // [rsp+50h] [rbp-18h]
  BSTR v29; // [rsp+58h] [rbp-10h]

  v7 = 0;
  cchName = 0;
  ui = 0;
  peUse = SidTypeUnknown;
  v8 = 0;
  v29 = 0;
  v9 = 0;
  v26 = 0;
  LookupAccountSidLocalW(a4, 0, &cchName, 0, &ui, &peUse);
  if ( GetLastError() == 122 )
  {
    v10 = cchName++;
    if ( v10 )
    {
      v11 = SysAllocStringLen(0, v10);
      v27 = v11;
      if ( !v11 )
        ATL::PrivateAtlThrow(-2147024882);
    }
    else
    {
      v11 = 0;
      v27 = 0;
    }
    v12 = ui++;
    if ( v12 )
    {
      v7 = SysAllocStringLen(0, v12);
      v28 = (volatile signed __int32 *)v7;
      if ( !v7 )
        ATL::PrivateAtlThrow(-2147024882);
    }
    else
    {
      v28 = 0;
    }
    v13 = LookupAccountSidLocalW(a4, v11, &cchName, v7, &ui, &peUse);
    if ( v13 )
    {
      if ( v11 )
      {
        SysFreeString(0);
        v15 = SysStringByteLen(v11);
        v8 = SysAllocStringByteLen((LPCSTR)v11, v15);
        v29 = v8;
        if ( !v8 )
          goto LABEL_28;
      }
      if ( v7 )
      {
        SysFreeString(0);
        v16 = SysStringByteLen(v7);
        v9 = SysAllocStringByteLen((LPCSTR)v7, v16);
        v26 = v9;
        if ( !v9 )
LABEL_28:
          ATL::PrivateAtlThrow(-2147024882);
      }
      SysFreeString(v7);
      SysFreeString(v11);
      v17 = (volatile signed __int32 *)operator new(0x18u);
      v19 = v17;
      v28 = v17;
      v13 = 1;
      if ( v17 )
      {
        *((_QWORD *)v17 + 1) = 0;
        *((_DWORD *)v17 + 4) = 1;
        *(_QWORD *)v17 = v9;
      }
      else
      {
        v19 = 0;
      }
      if ( !v19 )
        _com_raise_error(-2147024882, v18);
      _InterlockedIncrement(v19 + 4);
      _bstr_t::_Free(this);
      *(_QWORD *)this = v19;
      _bstr_t::Data_t::Release((_bstr_t::Data_t *)v19);
      v26 = 0;
      v20 = (volatile signed __int32 *)operator new(0x18u);
      v22 = v20;
      v28 = v20;
      if ( v20 )
      {
        *((_QWORD *)v20 + 1) = 0;
        *((_DWORD *)v20 + 4) = 1;
        *(_QWORD *)v20 = v8;
      }
      else
      {
        v22 = 0;
      }
      if ( !v22 )
        _com_raise_error(-2147024882, v21);
      _InterlockedIncrement(v22 + 4);
      _bstr_t::_Free(a2);
      *(_QWORD *)a2 = v22;
      _bstr_t::Data_t::Release((_bstr_t::Data_t *)v22);
      *a3 = peUse;
    }
    else
    {
      SysFreeString(v7);
      SysFreeString(v11);
    }
  }
  else
  {
    v13 = 0;
  }
  SysFreeString(0);
  SysFreeString(0);
  return v13;
}

```

## disassembly

```asm
0x18001c560  mov     [rsp-40h+arg_10], r8
0x18001c565  push    rbp
0x18001c566  push    rbx
0x18001c567  push    rsi
0x18001c568  push    rdi
0x18001c569  push    r12
0x18001c56b  push    r13
0x18001c56d  push    r14
0x18001c56f  push    r15
0x18001c571  mov     rbp, rsp
0x18001c574  sub     rsp, 68h
0x18001c578  mov     r15, r9
0x18001c57b  mov     r13, rdx
0x18001c57e  mov     r12, rcx
0x18001c581  xor     ebx, ebx
0x18001c583  mov     [rbp+cchName], ebx
0x18001c586  mov     [rbp+ui], ebx
0x18001c589  mov     [rbp+var_30], 8
0x18001c590  mov     r14d, ebx
0x18001c593  mov     [rbp+var_10], rbx
0x18001c597  mov     esi, ebx
0x18001c599  mov     [rbp+var_28], rbx
0x18001c59d  lea     rax, [rbp+var_30]
0x18001c5a1  mov     [rsp+68h+peUse], rax; peUse
0x18001c5a6  lea     rax, [rbp+ui]
0x18001c5aa  mov     [rsp+68h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001c5af  xor     r9d, r9d; ReferencedDomainName
0x18001c5b2  lea     r8, [rbp+cchName]; cchName
0x18001c5b6  xor     edx, edx; Name
0x18001c5b8  mov     rcx, r15; Sid
0x18001c5bb  call    cs:__imp_LookupAccountSidLocalW
0x18001c5c1  call    cs:__imp_GetLastError
0x18001c5c7  cmp     eax, 7Ah ; 'z'
0x18001c5ca  jnz     loc_18001C7B4
0x18001c5d0  mov     edx, [rbp+cchName]; ui
0x18001c5d3  lea     eax, [rdx+1]
0x18001c5d6  mov     [rbp+cchName], eax
0x18001c5d9  test    edx, edx
0x18001c5db  jnz     loc_18001C661
0x18001c5e1  mov     edi, ebx
0x18001c5e3  mov     [rbp+var_20], rbx
0x18001c5e7  mov     edx, [rbp+ui]; ui
0x18001c5ea  lea     eax, [rdx+1]
0x18001c5ed  mov     [rbp+ui], eax
0x18001c5f0  test    edx, edx
0x18001c5f2  jnz     loc_18001C684
0x18001c5f8  mov     [rbp+var_18], rbx
0x18001c5fc  lea     rax, [rbp+var_30]
0x18001c600  mov     [rsp+68h+peUse], rax; peUse
0x18001c605  lea     rax, [rbp+ui]
0x18001c609  mov     [rsp+68h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001c60e  mov     r9, rbx; ReferencedDomainName
0x18001c611  lea     r8, [rbp+cchName]; cchName
0x18001c615  mov     rdx, rdi; Name
0x18001c618  mov     rcx, r15; Sid
0x18001c61b  call    cs:__imp_LookupAccountSidLocalW
0x18001c621  mov     r15d, eax
0x18001c624  test    eax, eax
0x18001c626  jnz     short loc_18001C6A7
0x18001c628  mov     rcx, rbx; bstrString
0x18001c62b  call    cs:__imp_SysFreeString
0x18001c631  nop
0x18001c632  mov     rcx, rdi; bstrString
0x18001c635  call    cs:__imp_SysFreeString
0x18001c63b  nop
0x18001c63c  xor     ecx, ecx; bstrString
0x18001c63e  call    cs:__imp_SysFreeString
0x18001c644  nop
0x18001c645  xor     ecx, ecx; bstrString
0x18001c647  call    cs:__imp_SysFreeString
0x18001c64d  mov     eax, r15d
0x18001c650  add     rsp, 68h
0x18001c654  pop     r15
0x18001c656  pop     r14
0x18001c658  pop     r13
0x18001c65a  pop     r12
0x18001c65c  pop     rdi
0x18001c65d  pop     rsi
0x18001c65e  pop     rbx
0x18001c65f  pop     rbp
0x18001c660  retn
0x18001c661  xor     ecx, ecx; strIn
0x18001c663  call    cs:__imp_SysAllocStringLen
0x18001c669  mov     rdi, rax
0x18001c66c  mov     [rbp+var_20], rax
0x18001c670  test    rax, rax
0x18001c673  jnz     loc_18001C5E7
0x18001c679  mov     ecx, 8007000Eh; int
0x18001c67e  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18001c684  xor     ecx, ecx; strIn
0x18001c686  call    cs:__imp_SysAllocStringLen
0x18001c68c  mov     rbx, rax
0x18001c68f  mov     [rbp+var_18], rax
0x18001c693  test    rax, rax
0x18001c696  jnz     loc_18001C5FC
0x18001c69c  mov     ecx, 8007000Eh; int
0x18001c6a1  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18001c6a7  test    rdi, rdi
0x18001c6aa  jz      short loc_18001C6D8
0x18001c6ac  xor     ecx, ecx; bstrString
0x18001c6ae  call    cs:__imp_SysFreeString
0x18001c6b4  mov     rcx, rdi; bstr
0x18001c6b7  call    cs:__imp_SysStringByteLen
0x18001c6bd  mov     edx, eax; len
0x18001c6bf  mov     rcx, rdi; psz
0x18001c6c2  call    cs:__imp_SysAllocStringByteLen
0x18001c6c8  mov     r14, rax
0x18001c6cb  mov     [rbp+var_10], rax
0x18001c6cf  test    rax, rax
0x18001c6d2  jz      loc_18001C7BC
0x18001c6d8  test    rbx, rbx
0x18001c6db  jz      short loc_18001C709
0x18001c6dd  xor     ecx, ecx; bstrString
0x18001c6df  call    cs:__imp_SysFreeString
0x18001c6e5  mov     rcx, rbx; bstr
0x18001c6e8  call    cs:__imp_SysStringByteLen
0x18001c6ee  mov     edx, eax; len
0x18001c6f0  mov     rcx, rbx; psz
0x18001c6f3  call    cs:__imp_SysAllocStringByteLen
0x18001c6f9  mov     rsi, rax
0x18001c6fc  mov     [rbp+var_28], rax
0x18001c700  test    rax, rax
0x18001c703  jz      loc_18001C7BC
0x18001c709  mov     rcx, rbx; bstrString
0x18001c70c  call    cs:__imp_SysFreeString
0x18001c712  nop
0x18001c713  mov     rcx, rdi; bstrString
0x18001c716  call    cs:__imp_SysFreeString
0x18001c71c  mov     ecx, 18h; unsigned __int64
0x18001c721  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c726  mov     rbx, rax
0x18001c729  mov     [rbp+var_18], rax
0x18001c72d  mov     r15d, 1
0x18001c733  test    rax, rax
0x18001c736  jz      short loc_18001C757
0x18001c738  mov     qword ptr [rax+8], 0
0x18001c740  mov     [rax+10h], r15d
0x18001c744  mov     [rax], rsi
0x18001c747  test    rbx, rbx
0x18001c74a  jnz     short loc_18001C75B
0x18001c74c  mov     ecx, 8007000Eh; int
0x18001c751  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001c757  xor     ebx, ebx
0x18001c759  jmp     short loc_18001C747
0x18001c75b  lock inc dword ptr [rbx+10h]
0x18001c75f  mov     rcx, r12; this
0x18001c762  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001c767  mov     [r12], rbx
0x18001c76b  mov     rcx, rbx; this
0x18001c76e  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18001c773  mov     [rbp+var_28], 0
0x18001c77b  mov     ecx, 18h; unsigned __int64
0x18001c780  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c785  mov     rbx, rax
0x18001c788  mov     [rbp+var_18], rax
0x18001c78c  test    rax, rax
0x18001c78f  jz      short loc_18001C7B0
0x18001c791  mov     qword ptr [rax+8], 0
0x18001c799  mov     [rax+10h], r15d
0x18001c79d  mov     [rax], r14
0x18001c7a0  test    rbx, rbx
0x18001c7a3  jnz     short loc_18001C7C7
0x18001c7a5  mov     ecx, 8007000Eh; int
0x18001c7aa  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001c7b0  xor     ebx, ebx
0x18001c7b2  jmp     short loc_18001C7A0
0x18001c7b4  mov     r15d, ebx
0x18001c7b7  jmp     loc_18001C63C
0x18001c7bc  mov     ecx, 8007000Eh; int
0x18001c7c1  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18001c7c7  lock inc dword ptr [rbx+10h]
0x18001c7cb  mov     rcx, r13; this
0x18001c7ce  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001c7d3  mov     [r13+0], rbx
0x18001c7d7  mov     rcx, rbx; this
0x18001c7da  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18001c7df  mov     eax, [rbp+var_30]
0x18001c7e2  mov     rcx, [rbp+arg_10]
0x18001c7e6  mov     [rcx], eax
0x18001c7e8  jmp     loc_18001C63C
```
