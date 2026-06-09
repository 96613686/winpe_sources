# ShellDDEExec::~ShellDDEExec(void)

- ea: `0x18011aa7c`
- end: `0x18011abe8`
- name: `??1ShellDDEExec@@UEAA@XZ`
- size: `364`
- prototype: `void __fastcall(ShellDDEExec *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180118ef4`
- `0x180535550`
- `0x18062e43c`

## callees

- `0x18000d6cc`
- `0x18000ee84`
- `0x18009d190`
- `0x18011aa7c`
- `0x18011abf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011abb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011abb9`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18011abd2`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18011abdd`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18011abd2`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18011abdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011aaf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011aaf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011ab98`

## pseudocode

```c
void __fastcall ShellDDEExec::~ShellDDEExec(ShellDDEExec *this)
{
  HKEY v2; // rcx
  struct _DSA *v3; // rcx
  ATOM v4; // cx
  ATOM v5; // cx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx

  *(_QWORD *)this = &ShellDDEExec::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &ShellDDEExec::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IDDEInitializerWithAssociationElement,IWeakReferenceSource,Windows::Internal::Storage::IDDEExecHelper>'};
  *((_QWORD *)this + 2) = &ShellDDEExec::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 3) = &ShellDDEExec::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::Storage::IDDEExecHelper>'};
  v2 = (HKEY)*((_QWORD *)this + 11);
  if ( v2 )
    RegCloseKey(v2);
  v3 = (struct _DSA *)*((_QWORD *)this + 13);
  if ( v3 )
  {
    DSA_Destroy(v3);
    *((_QWORD *)this + 13) = 0;
  }
  v4 = *((_WORD *)this + 37);
  if ( v4 )
    GlobalDeleteAtom(v4);
  v5 = *((_WORD *)this + 36);
  if ( v5 )
    GlobalDeleteAtom(v5);
  v6 = (void *)*((_QWORD *)this + 28);
  if ( v6 )
    CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)this + 27);
  if ( v7 )
    CoTaskMemFree(v7);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 192);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>((char *)this + 184);
  v8 = (void *)*((_QWORD *)this + 21);
  if ( v8 )
    CoTaskMemFree(v8);
  v9 = (void *)*((_QWORD *)this + 20);
  if ( v9 )
    CoTaskMemFree(v9);
  v10 = (void *)*((_QWORD *)this + 18);
  if ( v10 )
    CoTaskMemFree(v10);
  v11 = (void *)*((_QWORD *)this + 17);
  if ( v11 )
    CoTaskMemFree(v11);
  v12 = (void *)*((_QWORD *)this + 16);
  if ( v12 )
    CoTaskMemFree(v12);
  v13 = (void *)*((_QWORD *)this + 15);
  if ( v13 )
    CoTaskMemFree(v13);
  v14 = (void *)*((_QWORD *)this + 14);
  if ( v14 )
    CoTaskMemFree(v14);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageFolder *>,Windows::Foundation::Collections::IIterable<Windows::Storage::IStorageFolder *>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageFolder *>,Windows::Foundation::Collections::IIterable<Windows::Storage::IStorageFolder *>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>(this);
}

```

## disassembly

```asm
0x18011aa7c  mov     [rsp+arg_0], rbx
0x18011aa81  push    rdi
0x18011aa82  sub     rsp, 20h
0x18011aa86  lea     rax, ??_7ShellDDEExec@@6BIInspectable@@@; const ShellDDEExec::`vftable'{for `IInspectable'}
0x18011aa8d  mov     rbx, rcx
0x18011aa90  mov     [rcx], rax
0x18011aa93  xor     edi, edi
0x18011aa95  lea     rax, ??_7ShellDDEExec@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIDDEInitializerWithAssociationElement@@UIWeakReferenceSource@@UIDDEExecHelper@Storage@Internal@Windows@@@Details@WRL@Microsoft@@@; const ShellDDEExec::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IDDEInitializerWithAssociationElement,IWeakReferenceSource,Windows::Internal::Storage::IDDEExecHelper>'}
0x18011aa9c  mov     [rcx+8], rax
0x18011aaa0  lea     rax, ??_7ShellDDEExec@@6BIWeakReferenceSource@@@; const ShellDDEExec::`vftable'{for `IWeakReferenceSource'}
0x18011aaa7  mov     [rcx+10h], rax
0x18011aaab  lea     rax, ??_7ShellDDEExec@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIDDEExecHelper@Storage@Internal@Windows@@@Details@WRL@Microsoft@@@; const ShellDDEExec::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::Storage::IDDEExecHelper>'}
0x18011aab2  mov     [rcx+18h], rax
0x18011aab6  mov     rcx, [rcx+58h]; hKey
0x18011aaba  test    rcx, rcx
0x18011aabd  jnz     loc_18011ABB9
0x18011aac3  mov     rcx, [rbx+68h]; hdsa
0x18011aac7  test    rcx, rcx
0x18011aaca  jnz     loc_18011ABC4
0x18011aad0  movzx   ecx, word ptr [rbx+4Ah]; nAtom
0x18011aad4  test    cx, cx
0x18011aad7  jnz     loc_18011ABD2
0x18011aadd  movzx   ecx, word ptr [rbx+48h]; nAtom
0x18011aae1  test    cx, cx
0x18011aae4  jnz     loc_18011ABDD
0x18011aaea  mov     rcx, [rbx+0E0h]; pv
0x18011aaf1  test    rcx, rcx
0x18011aaf4  jz      short loc_18011AAFC
0x18011aaf6  call    cs:__imp_CoTaskMemFree
0x18011aafc  mov     rcx, [rbx+0D8h]; pv
0x18011ab03  test    rcx, rcx
0x18011ab06  jz      short loc_18011AB0E
0x18011ab08  call    cs:__imp_CoTaskMemFree
0x18011ab0e  lea     rcx, [rbx+0C0h]
0x18011ab15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18011ab1a  lea     rcx, [rbx+0B8h]
0x18011ab21  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18011ab26  mov     rcx, [rbx+0A8h]; pv
0x18011ab2d  test    rcx, rcx
0x18011ab30  jz      short loc_18011AB38
0x18011ab32  call    cs:__imp_CoTaskMemFree
0x18011ab38  mov     rcx, [rbx+0A0h]; pv
0x18011ab3f  test    rcx, rcx
0x18011ab42  jz      short loc_18011AB4A
0x18011ab44  call    cs:__imp_CoTaskMemFree
0x18011ab4a  mov     rcx, [rbx+90h]; pv
0x18011ab51  test    rcx, rcx
0x18011ab54  jz      short loc_18011AB5C
0x18011ab56  call    cs:__imp_CoTaskMemFree
0x18011ab5c  mov     rcx, [rbx+88h]; pv
0x18011ab63  test    rcx, rcx
0x18011ab66  jz      short loc_18011AB6E
0x18011ab68  call    cs:__imp_CoTaskMemFree
0x18011ab6e  mov     rcx, [rbx+80h]; pv
0x18011ab75  test    rcx, rcx
0x18011ab78  jz      short loc_18011AB80
0x18011ab7a  call    cs:__imp_CoTaskMemFree
0x18011ab80  mov     rcx, [rbx+78h]; pv
0x18011ab84  test    rcx, rcx
0x18011ab87  jz      short loc_18011AB8F
0x18011ab89  call    cs:__imp_CoTaskMemFree
0x18011ab8f  mov     rcx, [rbx+70h]; pv
0x18011ab93  test    rcx, rcx
0x18011ab96  jz      short loc_18011AB9E
0x18011ab98  call    cs:__imp_CoTaskMemFree
0x18011ab9e  lea     rcx, [rbx+40h]
0x18011aba2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18011aba7  mov     rcx, rbx
0x18011abaa  mov     rbx, [rsp+28h+arg_0]
0x18011abaf  add     rsp, 20h
0x18011abb3  pop     rdi
0x18011abb4  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IVector@PEAUIStorageFolder@Storage@Windows@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIStorageFolder@Storage@Windows@@@567@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageFolder *>,Windows::Foundation::Collections::IIterable<Windows::Storage::IStorageFolder *>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageFolder *>,Windows::Foundation::Collections::IIterable<Windows::Storage::IStorageFolder *>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>(void)
0x18011abb9  call    cs:__imp_RegCloseKey
0x18011abbf  jmp     loc_18011AAC3
0x18011abc4  call    DSA_Destroy
0x18011abc9  mov     [rbx+68h], rdi
0x18011abcd  jmp     loc_18011AAD0
0x18011abd2  call    cs:__imp_GlobalDeleteAtom
0x18011abd8  jmp     loc_18011AADD
0x18011abdd  call    cs:__imp_GlobalDeleteAtom
0x18011abe3  jmp     loc_18011AAEA
```
