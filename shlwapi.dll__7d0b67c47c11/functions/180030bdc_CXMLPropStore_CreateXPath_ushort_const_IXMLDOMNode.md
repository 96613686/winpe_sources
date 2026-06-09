# CXMLPropStore::_CreateXPath(ushort const *,IXMLDOMNode * *)

- ea: `0x180030bdc`
- end: `0x180030d84`
- name: `?_CreateXPath@CXMLPropStore@@IEAAJPEBGPEAPEAUIXMLDOMNode@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(CXMLPropStore *__hidden this, LPCWSTR psz, struct IXMLDOMNode **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f380`
- `0x180032b44`

## callees

- `0x180012550`
- `0x180015590`
- `0x18002d55c`
- `0x18002d858`
- `0x18002db6c`
- `0x18002f2e4`
- `0x1800308ec`
- `0x180030bdc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180030c72`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180030d1b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180030c72`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180030d1b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180030c16`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180030d0b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180030c16`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180030d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030d4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030d4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030d58`
- `OLEAUT32!__imp_SysFreeString` at `0x180030cbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180030cbf`

## pseudocode

```c
__int64 __fastcall CXMLPropStore::_CreateXPath(CXMLPropStore *this, LPCWSTR psz, struct IXMLDOMNode **a3)
{
  HRESULT RelativeXPath; // ebx
  const unsigned __int16 *v7; // rax
  LPWSTR v8; // rdi
  int v9; // eax
  int v10; // edx
  int i; // r8d
  WCHAR v12; // ax
  bool v13; // zf
  int v14; // eax
  OLECHAR *v15; // r10
  unsigned __int16 *v16; // r8
  LPWSTR ppwsz; // [rsp+20h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-18h] BYREF
  struct IXMLDOMNode *v20; // [rsp+30h] [rbp-10h] BYREF

  *a3 = 0;
  ppwsz = 0;
  RelativeXPath = SHStrDupW(psz, &ppwsz);
  if ( RelativeXPath >= 0 )
  {
    ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&v20);
    v7 = ppwsz;
    while ( 1 )
    {
      bstrString = 0;
      RelativeXPath = SHSysAllocString(v7, &bstrString);
      if ( RelativeXPath >= 0 )
      {
        RelativeXPath = (*(__int64 (__fastcall **)(_QWORD, BSTR, struct IXMLDOMNode **))(**((_QWORD **)this + 7) + 296LL))(
                          *((_QWORD *)this + 7),
                          bstrString,
                          &v20);
        if ( RelativeXPath == 1 )
        {
          v8 = ppwsz;
          v9 = lstrlenW(ppwsz);
          if ( v9 )
          {
            v10 = 0;
            for ( i = v9 - 1; i >= 0; --i )
            {
              if ( !i || (v12 = v8[i], v12 == 47) && v10 <= 0 )
              {
                v8[i] = 0;
                break;
              }
              if ( v12 == 93 )
              {
                ++v10;
              }
              else if ( v12 == 91 )
              {
                --v10;
              }
            }
          }
        }
      }
      SysFreeString(bstrString);
      if ( RelativeXPath != 1 )
        break;
      v13 = (unsigned __int8)ATL::CComPtrBase<IXMLDOMNode>::operator!(&v20) == 0;
      v7 = ppwsz;
      if ( v13 )
      {
        if ( *ppwsz )
          goto LABEL_24;
LABEL_22:
        ATL::CComPtr<IXMLDOMNode>::operator=(&v20, (char *)this + 56);
        goto LABEL_24;
      }
      if ( !*ppwsz )
        goto LABEL_22;
    }
    if ( RelativeXPath < 0 )
      goto LABEL_28;
LABEL_24:
    bstrString = 0;
    RelativeXPath = SHStrDupW(psz, &bstrString);
    if ( RelativeXPath >= 0 )
    {
      v14 = lstrlenW(ppwsz);
      v15 = &bstrString[v14];
      v16 = v15 + 1;
      if ( *v15 != 47 )
        v16 = &bstrString[v14];
      RelativeXPath = CXMLPropStore::_CreateRelativeXPath(this, v20, v16, a3);
      CoTaskMemFree(bstrString);
    }
LABEL_28:
    CoTaskMemFree(ppwsz);
    ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&v20);
  }
  return (unsigned int)RelativeXPath;
}

```

## disassembly

```asm
0x180030bdc  push    rbp
0x180030bde  push    rbx
0x180030bdf  push    rsi
0x180030be0  push    rdi
0x180030be1  push    r12
0x180030be3  push    r14
0x180030be5  push    r15
0x180030be7  mov     rbp, rsp
0x180030bea  sub     rsp, 40h
0x180030bee  mov     rax, cs:__security_cookie
0x180030bf5  xor     rax, rsp
0x180030bf8  mov     [rbp+var_8], rax
0x180030bfc  mov     r14, rdx
0x180030bff  mov     rsi, rcx
0x180030c02  xor     r12d, r12d
0x180030c05  lea     rdx, [rbp+ppwsz]; ppwsz
0x180030c09  mov     rcx, r14; psz
0x180030c0c  mov     [r8], r12
0x180030c0f  mov     r15, r8
0x180030c12  mov     [rbp+ppwsz], r12
0x180030c16  call    cs:__imp_SHStrDupW
0x180030c1c  mov     ebx, eax
0x180030c1e  test    eax, eax
0x180030c20  js      loc_180030D67
0x180030c26  lea     rcx, [rbp+var_10]
0x180030c2a  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x180030c2f  mov     rax, [rbp+ppwsz]
0x180030c33  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180030c37  mov     [rbp+bstrString], r12
0x180030c3b  mov     rcx, rax; unsigned __int16 *
0x180030c3e  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x180030c43  mov     ebx, eax
0x180030c45  test    eax, eax
0x180030c47  js      short loc_180030CBB
0x180030c49  mov     rcx, [rsi+38h]
0x180030c4d  lea     r8, [rbp+var_10]
0x180030c51  mov     rdx, [rbp+bstrString]
0x180030c55  mov     rax, [rcx]
0x180030c58  mov     rax, [rax+128h]
0x180030c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c64  mov     ebx, eax
0x180030c66  cmp     eax, 1
0x180030c69  jnz     short loc_180030CBB
0x180030c6b  mov     rdi, [rbp+ppwsz]
0x180030c6f  mov     rcx, rdi; lpString
0x180030c72  call    cs:__imp_lstrlenW
0x180030c78  test    eax, eax
0x180030c7a  jz      short loc_180030CBB
0x180030c7c  mov     edx, r12d
0x180030c7f  lea     r8d, [rax-1]
0x180030c83  test    r8d, r8d
0x180030c86  js      short loc_180030CBB
0x180030c88  movsxd  rax, r8d
0x180030c8b  lea     rcx, [rax+rax]
0x180030c8f  jz      short loc_180030CB6
0x180030c91  movzx   eax, word ptr [rdi+rcx]
0x180030c95  cmp     ax, 2Fh ; '/'
0x180030c99  jnz     short loc_180030C9F
0x180030c9b  test    edx, edx
0x180030c9d  jle     short loc_180030CB6
0x180030c9f  cmp     ax, 5Dh ; ']'
0x180030ca3  jnz     short loc_180030CA9
0x180030ca5  inc     edx
0x180030ca7  jmp     short loc_180030CB1
0x180030ca9  cmp     ax, 5Bh ; '['
0x180030cad  jnz     short loc_180030CB1
0x180030caf  dec     edx
0x180030cb1  dec     r8d
0x180030cb4  jmp     short loc_180030C83
0x180030cb6  mov     [rcx+rdi], r12w
0x180030cbb  mov     rcx, [rbp+bstrString]; bstrString
0x180030cbf  call    cs:__imp_SysFreeString
0x180030cc5  cmp     ebx, 1
0x180030cc8  jnz     short loc_180030CFC
0x180030cca  lea     rcx, [rbp+var_10]
0x180030cce  call    ??7?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IXMLDOMNode>::operator!(void)
0x180030cd3  test    al, al
0x180030cd5  mov     rax, [rbp+ppwsz]
0x180030cd9  jz      short loc_180030CE7
0x180030cdb  cmp     [rax], r12w
0x180030cdf  jnz     loc_180030C33
0x180030ce5  jmp     short loc_180030CED
0x180030ce7  cmp     [rax], r12w
0x180030ceb  jnz     short loc_180030D00
0x180030ced  lea     rdx, [rsi+38h]
0x180030cf1  lea     rcx, [rbp+var_10]
0x180030cf5  call    ??4?$CComPtr@UIXMLDOMNode@@@ATL@@QEAAPEAUIXMLDOMNode@@AEBV01@@Z; ATL::CComPtr<IXMLDOMNode>::operator=(ATL::CComPtr<IXMLDOMNode> const &)
0x180030cfa  jmp     short loc_180030D00
0x180030cfc  test    ebx, ebx
0x180030cfe  js      short loc_180030D54
0x180030d00  lea     rdx, [rbp+bstrString]; ppwsz
0x180030d04  mov     [rbp+bstrString], r12
0x180030d08  mov     rcx, r14; psz
0x180030d0b  call    cs:__imp_SHStrDupW
0x180030d11  mov     ebx, eax
0x180030d13  test    eax, eax
0x180030d15  js      short loc_180030D54
0x180030d17  mov     rcx, [rbp+ppwsz]; lpString
0x180030d1b  call    cs:__imp_lstrlenW
0x180030d21  movsxd  rdx, eax
0x180030d24  mov     r9, r15; struct IXMLDOMNode **
0x180030d27  mov     rax, [rbp+bstrString]
0x180030d2b  mov     rcx, rsi; this
0x180030d2e  lea     r10, [rax+rdx*2]
0x180030d32  mov     rdx, [rbp+var_10]; struct IXMLDOMNode *
0x180030d36  cmp     word ptr [r10], 2Fh ; '/'
0x180030d3b  lea     r8, [r10+2]
0x180030d3f  cmovnz  r8, r10; unsigned __int16 *
0x180030d43  call    ?_CreateRelativeXPath@CXMLPropStore@@IEAAJPEAUIXMLDOMNode@@PEAGPEAPEAU2@@Z; CXMLPropStore::_CreateRelativeXPath(IXMLDOMNode *,ushort *,IXMLDOMNode * *)
0x180030d48  mov     rcx, [rbp+bstrString]; pv
0x180030d4c  mov     ebx, eax
0x180030d4e  call    cs:__imp_CoTaskMemFree
0x180030d54  mov     rcx, [rbp+ppwsz]; pv
0x180030d58  call    cs:__imp_CoTaskMemFree
0x180030d5e  lea     rcx, [rbp+var_10]
0x180030d62  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x180030d67  mov     eax, ebx
0x180030d69  mov     rcx, [rbp+var_8]
0x180030d6d  xor     rcx, rsp; StackCookie
0x180030d70  call    __security_check_cookie
0x180030d75  add     rsp, 40h
0x180030d79  pop     r15
0x180030d7b  pop     r14
0x180030d7d  pop     r12
0x180030d7f  pop     rdi
0x180030d80  pop     rsi
0x180030d81  pop     rbx
0x180030d82  pop     rbp
0x180030d83  retn
```
