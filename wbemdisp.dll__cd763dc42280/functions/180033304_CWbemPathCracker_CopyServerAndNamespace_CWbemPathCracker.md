# CWbemPathCracker::CopyServerAndNamespace(CWbemPathCracker &)

- ea: `0x180033304`
- end: `0x1800333ec`
- name: `?CopyServerAndNamespace@CWbemPathCracker@@AEAA_NAEAV1@@Z`
- size: `232`
- prototype: `bool __fastcall(CWbemPathCracker *__hidden this, struct CWbemPathCracker *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002f4c0`

## callees

- `0x180010acc`
- `0x180014570`
- `0x180016484`
- `0x180016fa4`
- `0x180017bf4`
- `0x180033304`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800333c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800333d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800333c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800333d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CWbemPathCracker::CopyServerAndNamespace(CWbemPathCracker *this, struct CWbemPathCracker *a2)
{
  bool v4; // bl
  unsigned int i; // esi
  __int64 v6; // rcx
  BSTR v8[5]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v9; // [rsp+60h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  v8[0] = 0;
  if ( CWbemPathCracker::GetServer(this, (struct ATL::CComBSTR *)v8)
    && CWbemPathCracker::SetServer(a2, (const struct ATL::CComBSTR *)v8) )
  {
    CWbemPathCracker::ClearNamespace(a2);
    v9 = 0;
    if ( CWbemPathCracker::GetNamespaceCount(this, &v9) )
    {
      v4 = 1;
      for ( i = 0; i < v9; ++i )
      {
        if ( !v4 )
          break;
        bstrString = 0;
        v4 = 0;
        if ( CWbemPathCracker::GetNamespaceAt(this, i, (struct ATL::CComBSTR *)&bstrString) && *((_DWORD *)a2 + 7) == 1 )
        {
          v6 = *((_QWORD *)a2 + 1);
          if ( v6 )
          {
            if ( (*(int (__fastcall **)(__int64, _QWORD, BSTR))(*(_QWORD *)v6 + 72LL))(v6, i, bstrString) >= 0 )
              v4 = 1;
          }
        }
        SysFreeString(bstrString);
      }
    }
  }
  SysFreeString(v8[0]);
  return v4;
}

```

## disassembly

```asm
0x180033304  mov     [rsp+arg_0], rbx
0x180033309  push    rbp
0x18003330a  push    rsi
0x18003330b  push    rdi
0x18003330c  sub     rsp, 30h
0x180033310  mov     rdi, rdx
0x180033313  mov     rbp, rcx
0x180033316  xor     bl, bl
0x180033318  mov     [rsp+48h+var_28], 0
0x180033321  lea     rdx, [rsp+48h+var_28]; struct ATL::CComBSTR *
0x180033326  call    ?GetServer@CWbemPathCracker@@QEAA_NAEAVCComBSTR@ATL@@@Z; CWbemPathCracker::GetServer(ATL::CComBSTR &)
0x18003332b  test    al, al
0x18003332d  jz      loc_1800333D2
0x180033333  lea     rdx, [rsp+48h+var_28]; struct ATL::CComBSTR *
0x180033338  mov     rcx, rdi; this
0x18003333b  call    ?SetServer@CWbemPathCracker@@QEAA_NAEBVCComBSTR@ATL@@@Z; CWbemPathCracker::SetServer(ATL::CComBSTR const &)
0x180033340  test    al, al
0x180033342  jz      loc_1800333D2
0x180033348  mov     rcx, rdi; this
0x18003334b  call    ?ClearNamespace@CWbemPathCracker@@AEAAXXZ; CWbemPathCracker::ClearNamespace(void)
0x180033350  mov     [rsp+48h+arg_10], 0
0x180033358  lea     rdx, [rsp+48h+arg_10]; unsigned int *
0x18003335d  mov     rcx, rbp; this
0x180033360  call    ?GetNamespaceCount@CWbemPathCracker@@QEAA_NAEAK@Z; CWbemPathCracker::GetNamespaceCount(ulong &)
0x180033365  test    al, al
0x180033367  jz      short loc_1800333D2
0x180033369  mov     bl, 1
0x18003336b  xor     esi, esi
0x18003336d  cmp     [rsp+48h+arg_10], esi
0x180033371  jbe     short loc_1800333D2
0x180033373  test    bl, bl
0x180033375  jz      short loc_1800333D2
0x180033377  mov     [rsp+48h+bstrString], 0
0x180033380  lea     r8, [rsp+48h+bstrString]; struct ATL::CComBSTR *
0x180033385  mov     edx, esi; unsigned int
0x180033387  mov     rcx, rbp; this
0x18003338a  call    ?GetNamespaceAt@CWbemPathCracker@@AEAA_NKAEAVCComBSTR@ATL@@@Z; CWbemPathCracker::GetNamespaceAt(ulong,ATL::CComBSTR &)
0x18003338f  test    al, al
0x180033391  jz      short loc_1800333BD
0x180033393  cmp     dword ptr [rdi+1Ch], 1
0x180033397  jnz     short loc_1800333BD
0x180033399  mov     rcx, [rdi+8]
0x18003339d  test    rcx, rcx
0x1800333a0  jz      short loc_1800333BD
0x1800333a2  mov     rax, [rcx]
0x1800333a5  mov     r8, [rsp+48h+bstrString]
0x1800333aa  mov     edx, esi
0x1800333ac  mov     rax, [rax+48h]
0x1800333b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333b5  test    eax, eax
0x1800333b7  js      short loc_1800333BD
0x1800333b9  mov     bl, 1
0x1800333bb  jmp     short loc_1800333BF
0x1800333bd  xor     bl, bl
0x1800333bf  mov     rcx, [rsp+48h+bstrString]; bstrString
0x1800333c4  call    cs:__imp_SysFreeString
0x1800333ca  inc     esi
0x1800333cc  cmp     esi, [rsp+48h+arg_10]
0x1800333d0  jb      short loc_180033373
0x1800333d2  mov     rcx, [rsp+48h+var_28]; bstrString
0x1800333d7  call    cs:__imp_SysFreeString
0x1800333dd  mov     al, bl
0x1800333df  mov     rbx, [rsp+48h+arg_0]
0x1800333e4  add     rsp, 30h
0x1800333e8  pop     rdi
0x1800333e9  pop     rsi
0x1800333ea  pop     rbp
0x1800333eb  retn
```
