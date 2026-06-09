# CDataFormatStore::GetFormatIds(IDataObject *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *)

- ea: `0x18002f53c`
- end: `0x18002f71c`
- name: `?GetFormatIds@CDataFormatStore@@QEAAJPEAUIDataObject@@PEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180057d80`

## callees

- `0x180002ad0`
- `0x180008b68`
- `0x18001b19c`
- `0x18002f53c`
- `0x18002f724`
- `0x180043b6c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002f68e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002f68e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f6b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f6b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f597`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f597`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f5b3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f5b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDataFormatStore::GetFormatIds(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rbx
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  HRESULT ActivationFactory; // ebx
  __int64 v11; // rcx
  HSTRING v12; // rcx
  __int64 v13; // rcx
  HSTRING v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // rdi
  HSTRING v18; // rcx
  HSTRING newString; // [rsp+20h] [rbp-40h] BYREF
  __int64 v21; // [rsp+28h] [rbp-38h] BYREF
  HSTRING v22; // [rsp+30h] [rbp-30h]
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF

  *a3 = 0;
  v22 = 0;
  v21 = 0;
  v6 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v21);
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x18002F71BLL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, v6);
  if ( ActivationFactory >= 0 )
  {
    newString = 0;
    ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}(v21, &newString);
    if ( ActivationFactory >= 0 )
    {
      v14 = newString;
      newString = 0;
      v22 = v14;
      v15 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      ActivationFactory = 0;
    }
    else
    {
      v12 = newString;
      if ( newString )
      {
        newString = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v12 + 16LL))(v12);
      }
      v13 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
  }
  else
  {
    v11 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  if ( ActivationFactory >= 0 )
  {
    if ( a2 )
      ActivationFactory = GetFormatIdsFromDataObject(a2, v22);
    v16 = *(_QWORD *)(a1 + 16);
    v17 = 0;
    while ( ActivationFactory >= 0 )
    {
      if ( v17 >= v16 )
      {
        ActivationFactory = (*(__int64 (__fastcall **)(HSTRING, _QWORD *))(*(_QWORD *)v22 + 64LL))(v22, a3);
        break;
      }
      newString = 0;
      ActivationFactory = WindowsDuplicateString(
                            *(HSTRING *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v17) + 8LL),
                            &newString);
      if ( ActivationFactory >= 0 )
        ActivationFactory = (*(__int64 (__fastcall **)(HSTRING, HSTRING))(*(_QWORD *)v22 + 104LL))(v22, newString);
      if ( newString )
        WindowsDeleteString(newString);
      ++v17;
    }
  }
  v18 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18002f53c  push    rbp
0x18002f53e  push    rbx
0x18002f53f  push    rsi
0x18002f540  push    rdi
0x18002f541  push    r12
0x18002f543  push    r14
0x18002f545  push    r15
0x18002f547  mov     rbp, rsp
0x18002f54a  sub     rsp, 60h
0x18002f54e  mov     rax, cs:__security_cookie
0x18002f555  xor     rax, rsp
0x18002f558  mov     [rbp+var_8], rax
0x18002f55c  mov     r15, r8
0x18002f55f  mov     rdi, rdx
0x18002f562  mov     r14, rcx
0x18002f565  xor     r12d, r12d
0x18002f568  mov     [r8], r12
0x18002f56b  mov     [rbp+var_30], r12
0x18002f56f  mov     [rbp+var_38], r12
0x18002f573  lea     rcx, [rbp+var_38]
0x18002f577  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18002f57c  mov     rbx, rax
0x18002f57f  mov     [rbp+string], r12
0x18002f583  lea     r9, [rbp+string]; string
0x18002f587  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002f58b  lea     edx, [r12+2Ch]; length
0x18002f590  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002f597  call    cs:__imp_WindowsCreateStringReference
0x18002f59d  test    eax, eax
0x18002f59f  js      loc_18002F714
0x18002f5a5  mov     r8, rbx
0x18002f5a8  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002f5af  mov     rcx, [rbp+string]
0x18002f5b3  call    cs:__imp_RoGetActivationFactory
0x18002f5b9  mov     ebx, eax
0x18002f5bb  test    eax, eax
0x18002f5bd  jns     short loc_18002F5DB
0x18002f5bf  mov     rcx, [rbp+var_38]
0x18002f5c3  test    rcx, rcx
0x18002f5c6  jz      short loc_18002F5D9
0x18002f5c8  mov     [rbp+var_38], r12
0x18002f5cc  mov     rax, [rcx]
0x18002f5cf  mov     rax, [rax+10h]
0x18002f5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5d8  nop
0x18002f5d9  jmp     short loc_18002F651
0x18002f5db  mov     [rbp+newString], r12
0x18002f5df  lea     rdx, [rbp+newString]
0x18002f5e3  mov     rcx, [rbp+var_38]
0x18002f5e7  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BNA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}
0x18002f5ec  mov     ebx, eax
0x18002f5ee  test    eax, eax
0x18002f5f0  jns     short loc_18002F628
0x18002f5f2  mov     rcx, [rbp+newString]
0x18002f5f6  test    rcx, rcx
0x18002f5f9  jz      short loc_18002F60C
0x18002f5fb  mov     [rbp+newString], r12
0x18002f5ff  mov     rax, [rcx]
0x18002f602  mov     rax, [rax+10h]
0x18002f606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f60b  nop
0x18002f60c  mov     rcx, [rbp+var_38]
0x18002f610  test    rcx, rcx
0x18002f613  jz      short loc_18002F626
0x18002f615  mov     [rbp+var_38], r12
0x18002f619  mov     rax, [rcx]
0x18002f61c  mov     rax, [rax+10h]
0x18002f620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f625  nop
0x18002f626  jmp     short loc_18002F651
0x18002f628  mov     rax, [rbp+newString]
0x18002f62c  mov     [rbp+newString], r12
0x18002f630  mov     [rbp+var_30], rax
0x18002f634  mov     rcx, [rbp+var_38]
0x18002f638  test    rcx, rcx
0x18002f63b  jz      short loc_18002F64E
0x18002f63d  mov     [rbp+var_38], r12
0x18002f641  mov     rax, [rcx]
0x18002f644  mov     rax, [rax+10h]
0x18002f648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f64d  nop
0x18002f64e  mov     ebx, r12d
0x18002f651  test    ebx, ebx
0x18002f653  js      loc_18002F6DD
0x18002f659  test    rdi, rdi
0x18002f65c  jz      short loc_18002F66C
0x18002f65e  mov     rdx, [rbp+var_30]
0x18002f662  mov     rcx, rdi
0x18002f665  call    ?GetFormatIdsFromDataObject@@YAJPEAUIDataObject@@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z; GetFormatIdsFromDataObject(IDataObject *,Windows::Foundation::Collections::IVector<HSTRING__ *> *)
0x18002f66a  mov     ebx, eax
0x18002f66c  mov     rsi, [r14+10h]
0x18002f670  mov     rdi, r12
0x18002f673  jmp     short loc_18002F6C2
0x18002f675  cmp     rdi, rsi
0x18002f678  jnb     short loc_18002F6C8
0x18002f67a  mov     [rbp+newString], r12
0x18002f67e  mov     rax, [r14+8]
0x18002f682  mov     rcx, [rax+rdi*8]
0x18002f686  lea     rdx, [rbp+newString]; newString
0x18002f68a  mov     rcx, [rcx+8]; string
0x18002f68e  call    cs:__imp_WindowsDuplicateString
0x18002f694  mov     ebx, eax
0x18002f696  test    eax, eax
0x18002f698  js      short loc_18002F6B0
0x18002f69a  mov     rcx, [rbp+var_30]
0x18002f69e  mov     rax, [rcx]
0x18002f6a1  mov     rdx, [rbp+newString]
0x18002f6a5  mov     rax, [rax+68h]
0x18002f6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6ae  mov     ebx, eax
0x18002f6b0  mov     rcx, [rbp+newString]; string
0x18002f6b4  test    rcx, rcx
0x18002f6b7  jz      short loc_18002F6BF
0x18002f6b9  call    cs:__imp_WindowsDeleteString
0x18002f6bf  inc     rdi
0x18002f6c2  test    ebx, ebx
0x18002f6c4  jns     short loc_18002F675
0x18002f6c6  jmp     short loc_18002F6DD
0x18002f6c8  mov     rcx, [rbp+var_30]
0x18002f6cc  mov     rax, [rcx]
0x18002f6cf  mov     rdx, r15
0x18002f6d2  mov     rax, [rax+40h]
0x18002f6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6db  mov     ebx, eax
0x18002f6dd  mov     rcx, [rbp+var_30]
0x18002f6e1  test    rcx, rcx
0x18002f6e4  jz      short loc_18002F6F7
0x18002f6e6  mov     [rbp+var_30], r12
0x18002f6ea  mov     rax, [rcx]
0x18002f6ed  mov     rax, [rax+10h]
0x18002f6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6f6  nop
0x18002f6f7  mov     eax, ebx
0x18002f6f9  mov     rcx, [rbp+var_8]
0x18002f6fd  xor     rcx, rsp; StackCookie
0x18002f700  call    __security_check_cookie
0x18002f705  add     rsp, 60h
0x18002f709  pop     r15
0x18002f70b  pop     r14
0x18002f70d  pop     r12
0x18002f70f  pop     rdi
0x18002f710  pop     rsi
0x18002f711  pop     rbx
0x18002f712  pop     rbp
0x18002f713  retn
0x18002f714  mov     ecx, eax; this
0x18002f716  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
