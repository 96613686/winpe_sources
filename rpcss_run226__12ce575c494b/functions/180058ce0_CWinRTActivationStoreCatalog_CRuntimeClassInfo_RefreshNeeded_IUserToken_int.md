# CWinRTActivationStoreCatalog::CRuntimeClassInfo::RefreshNeeded(IUserToken *,int *)

- ea: `0x180058ce0`
- end: `0x180058fa3`
- name: `?RefreshNeeded@CRuntimeClassInfo@CWinRTActivationStoreCatalog@@UEAAJPEAUIUserToken@@PEAH@Z`
- size: `707`
- prototype: `__int64 __fastcall(CWinRTActivationStoreCatalog::CRuntimeClassInfo *__hidden this, struct IUserToken *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000824c`
- `0x18000d4c4`
- `0x180034540`
- `0x180058ce0`
- `0x18008e98c`
- `0x1800d01d8`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058d90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058f0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058d90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058f0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180058d6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180058da1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180058d6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180058da1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180058f62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180058f62`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x180058e16`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x180058e16`

## pseudocode

```c
__int64 __fastcall CWinRTActivationStoreCatalog::CRuntimeClassInfo::RefreshNeeded(
        CWinRTActivationStoreCatalog::CRuntimeClassInfo *this,
        struct IUserToken *a2,
        int *a3)
{
  int v4; // ecx
  HRESULT RegistrationStoreContext; // edi
  int v8; // r9d
  __int64 v9; // rcx
  __int64 v10; // rcx
  HSTRING v11; // rbx
  HSTRING v12; // rbx
  __int64 v13; // rdx
  void (__fastcall ***v14)(_QWORD, GUID *, __int64 *, _QWORD); // rcx
  void (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // r9
  int v16; // ebx
  PCWSTR StringRawBuffer; // rax
  int v18; // edx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 *v23; // [rsp+20h] [rbp-40h]
  HSTRING newString; // [rsp+40h] [rbp-20h] BYREF
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h] BYREF
  __int64 v27; // [rsp+58h] [rbp-8h] BYREF
  int v28; // [rsp+A0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v30; // [rsp+B8h] [rbp+58h] BYREF

  v4 = *((_DWORD *)this + 26);
  RegistrationStoreContext = 0;
  v8 = 1;
  v28 = 1;
  if ( !v4 )
  {
LABEL_4:
    if ( s_pReadCatalogCache )
      v10 = *((_QWORD *)s_pReadCatalogCache + 2);
    else
      v10 = 0;
    *a3 = v10 > *((_QWORD *)this + 3);
    return (unsigned int)RegistrationStoreContext;
  }
  v9 = (unsigned int)(v4 - 1);
  if ( !(_DWORD)v9 )
  {
    if ( GetWinRTActivationStoreSequence() > *((_QWORD *)this + 3) )
      goto LABEL_28;
    v11 = (HSTRING)*((_QWORD *)this + 4);
    v27 = 0;
    v30 = 0;
    string = 0;
    WindowsDeleteString(0);
    newString = 0;
    RegistrationStoreContext = WindowsDuplicateString(v11, &newString);
    if ( RegistrationStoreContext >= 0 )
    {
      v12 = (HSTRING)*((_QWORD *)this + 7);
      if ( !v12 || (RegistrationStoreContext = 0, v12 != string) )
      {
        WindowsDeleteString(string);
        string = 0;
        RegistrationStoreContext = WindowsDuplicateString(v12, &string);
      }
    }
    if ( a2 )
    {
      v26 = -1;
      if ( RegistrationStoreContext >= 0 )
      {
        RegistrationStoreContext = (*(__int64 (__fastcall **)(struct IUserToken *, __int64 *))(*(_QWORD *)a2 + 48LL))(
                                     a2,
                                     &v26);
        if ( RegistrationStoreContext >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          v13 = v26;
LABEL_17:
          v23 = &v30;
          RegistrationStoreContext = RoGetRegistrationStoreContext(
                                       *((unsigned int *)this + 26),
                                       v13,
                                       4,
                                       &GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2);
          if ( RegistrationStoreContext >= 0 )
          {
            v23 = &v27;
            RegistrationStoreContext = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _QWORD))(*(_QWORD *)v30 + 192LL))(
                                         v30,
                                         string,
                                         newString,
                                         *((unsigned int *)this + 34));
            if ( RegistrationStoreContext >= 0 && *((_QWORD *)this + 18) == v27 )
            {
              if ( *((_DWORD *)this + 16) )
              {
                v14 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *, _QWORD))*((_QWORD *)this + 14);
                v15 = 0;
                v26 = 0;
                if ( v14 )
                {
                  (**v14)(v14, &GUID_5868bd9b_be16_4c83_a560_0121173c48f1, &v26, 0);
                  v15 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))v26;
                }
                v25 = 0;
                (**v15)(v15, &IID_ICacheRefresh, &v25);
                RegistrationStoreContext = (*(__int64 (__fastcall **)(__int64, struct IUserToken *, int *))(*(_QWORD *)v25 + 24LL))(
                                             v25,
                                             a2,
                                             &v28);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
              else
              {
                v28 = 0;
              }
            }
          }
        }
      }
    }
    else if ( RegistrationStoreContext >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
      v13 = 0;
      goto LABEL_17;
    }
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(newString);
    v9 = v30;
    newString = 0;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v8 = v28;
    goto LABEL_28;
  }
  if ( (_DWORD)v9 == 1 )
    goto LABEL_4;
LABEL_28:
  *a3 = v8;
  if ( RegistrationStoreContext < 0 )
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v16 = *((_DWORD *)this + 26);
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 4), 0);
      ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope,long>(
        v19,
        v18,
        v20,
        v21,
        (_DWORD)v23,
        (__int64)StringRawBuffer,
        v16,
        RegistrationStoreContext);
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
  }
  return (unsigned int)RegistrationStoreContext;
}

```

## disassembly

```asm
0x180058ce0  push    rbp
0x180058ce2  push    rbx
0x180058ce3  push    rsi
0x180058ce4  push    rdi
0x180058ce5  push    r12
0x180058ce7  push    r14
0x180058ce9  push    r15
0x180058ceb  mov     rbp, rsp
0x180058cee  sub     rsp, 60h
0x180058cf2  xor     r12d, r12d
0x180058cf5  mov     rsi, rcx
0x180058cf8  mov     ecx, [rcx+68h]
0x180058cfb  mov     r15, r8
0x180058cfe  mov     r14, rdx
0x180058d01  mov     edi, r12d
0x180058d04  lea     r9d, [r12+1]
0x180058d09  mov     [rbp+arg_0], r9d
0x180058d0d  test    ecx, ecx
0x180058d0f  jz      short loc_180058D1F
0x180058d11  sub     ecx, r9d
0x180058d14  jz      short loc_180058D38
0x180058d16  cmp     ecx, r9d
0x180058d19  jnz     loc_180058F34
0x180058d1f  mov     rax, cs:?s_pReadCatalogCache@@3PEAUCOM_CATALOG_CACHE_SECTION@@EA; COM_CATALOG_CACHE_SECTION * s_pReadCatalogCache
0x180058d26  test    rax, rax
0x180058d29  jz      loc_180058F81
0x180058d2f  mov     rcx, [rax+10h]
0x180058d33  jmp     loc_180058F84
0x180058d38  call    ?GetWinRTActivationStoreSequence@@YA_JXZ; GetWinRTActivationStoreSequence(void)
0x180058d3d  cmp     rax, [rsi+18h]
0x180058d41  jg      loc_180058F34
0x180058d47  mov     rbx, [rsi+20h]
0x180058d4b  xor     ecx, ecx; string
0x180058d4d  mov     [rbp+var_8], r12
0x180058d51  mov     [rbp+arg_18], r12
0x180058d55  mov     [rbp+newString], r12
0x180058d59  mov     [rbp+string], r12
0x180058d5d  call    cs:__imp_WindowsDeleteString
0x180058d63  lea     rdx, [rbp+newString]; newString
0x180058d67  mov     [rbp+newString], r12
0x180058d6b  mov     rcx, rbx; string
0x180058d6e  call    cs:__imp_WindowsDuplicateString
0x180058d74  mov     edi, eax
0x180058d76  test    eax, eax
0x180058d78  js      short loc_180058DA9
0x180058d7a  mov     rbx, [rsi+38h]
0x180058d7e  test    rbx, rbx
0x180058d81  jz      short loc_180058D8C
0x180058d83  mov     edi, r12d
0x180058d86  cmp     rbx, [rbp+string]
0x180058d8a  jz      short loc_180058DA9
0x180058d8c  mov     rcx, [rbp+string]; string
0x180058d90  call    cs:__imp_WindowsDeleteString
0x180058d96  lea     rdx, [rbp+string]; newString
0x180058d9a  mov     [rbp+string], r12
0x180058d9e  mov     rcx, rbx; string
0x180058da1  call    cs:__imp_WindowsDuplicateString
0x180058da7  mov     edi, eax
0x180058da9  test    r14, r14
0x180058dac  jz      short loc_180058DEA
0x180058dae  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x180058db6  test    edi, edi
0x180058db8  js      loc_180058EFB
0x180058dbe  mov     rax, [r14]
0x180058dc1  lea     rdx, [rbp+var_10]
0x180058dc5  mov     rcx, r14
0x180058dc8  mov     rax, [rax+30h]
0x180058dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058dd1  mov     edi, eax
0x180058dd3  test    eax, eax
0x180058dd5  js      loc_180058EFB
0x180058ddb  lea     rcx, [rbp+arg_18]
0x180058ddf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058de4  mov     rdx, [rbp+var_10]
0x180058de8  jmp     short loc_180058DFD
0x180058dea  test    edi, edi
0x180058dec  js      loc_180058EFB
0x180058df2  lea     rcx, [rbp+arg_18]
0x180058df6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058dfb  xor     edx, edx
0x180058dfd  mov     ecx, [rsi+68h]
0x180058e00  lea     rax, [rbp+arg_18]
0x180058e04  lea     r9, _GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2
0x180058e0b  mov     [rsp+60h+var_40], rax
0x180058e10  mov     r8d, 4
0x180058e16  call    cs:__imp_RoGetRegistrationStoreContext
0x180058e1c  mov     edi, eax
0x180058e1e  test    eax, eax
0x180058e20  js      loc_180058EFB
0x180058e26  mov     rcx, [rbp+arg_18]
0x180058e2a  lea     rdx, [rbp+var_8]
0x180058e2e  mov     r9d, [rsi+88h]
0x180058e35  mov     r8, [rbp+newString]
0x180058e39  mov     [rsp+60h+var_40], rdx
0x180058e3e  mov     rax, [rcx]
0x180058e41  mov     rdx, [rbp+string]
0x180058e45  mov     rax, [rax+0C0h]
0x180058e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e51  mov     edi, eax
0x180058e53  test    eax, eax
0x180058e55  js      loc_180058EFB
0x180058e5b  mov     rax, [rbp+var_8]
0x180058e5f  cmp     [rsi+90h], rax
0x180058e66  jnz     loc_180058EFB
0x180058e6c  cmp     [rsi+40h], r12d
0x180058e70  jnz     short loc_180058E7B
0x180058e72  mov     [rbp+arg_0], r12d
0x180058e76  jmp     loc_180058EFB
0x180058e7b  mov     rcx, [rsi+70h]
0x180058e7f  mov     r9, r12
0x180058e82  mov     [rbp+var_10], r12
0x180058e86  test    rcx, rcx
0x180058e89  jz      short loc_180058EA5
0x180058e8b  mov     rax, [rcx]
0x180058e8e  lea     r8, [rbp+var_10]
0x180058e92  lea     rdx, _GUID_5868bd9b_be16_4c83_a560_0121173c48f1
0x180058e99  mov     rax, [rax]
0x180058e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ea1  mov     r9, [rbp+var_10]
0x180058ea5  mov     [rbp+var_18], r12
0x180058ea9  lea     r8, [rbp+var_18]
0x180058ead  mov     rax, [r9]
0x180058eb0  lea     rdx, IID_ICacheRefresh
0x180058eb7  mov     rcx, r9
0x180058eba  mov     rax, [rax]
0x180058ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ec2  mov     rcx, [rbp+var_18]
0x180058ec6  lea     r8, [rbp+arg_0]
0x180058eca  mov     rdx, r14
0x180058ecd  mov     rax, [rcx]
0x180058ed0  mov     rax, [rax+18h]
0x180058ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ed9  mov     rcx, [rbp+var_18]
0x180058edd  mov     edi, eax
0x180058edf  mov     rax, [rcx]
0x180058ee2  mov     rax, [rax+10h]
0x180058ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058eeb  mov     rcx, [rbp+var_10]
0x180058eef  mov     rax, [rcx]
0x180058ef2  mov     rax, [rax+10h]
0x180058ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058efb  mov     rcx, [rbp+string]; string
0x180058eff  call    cs:__imp_WindowsDeleteString
0x180058f05  mov     rcx, [rbp+newString]; string
0x180058f09  mov     [rbp+string], r12
0x180058f0d  call    cs:__imp_WindowsDeleteString
0x180058f13  mov     rcx, [rbp+arg_18]
0x180058f17  mov     [rbp+newString], r12
0x180058f1b  test    rcx, rcx
0x180058f1e  jz      short loc_180058F30
0x180058f20  mov     [rbp+arg_18], r12
0x180058f24  mov     rax, [rcx]
0x180058f27  mov     rax, [rax+10h]
0x180058f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f30  mov     r9d, [rbp+arg_0]
0x180058f34  mov     [r15], r9d
0x180058f37  test    edi, edi
0x180058f39  jns     short loc_180058F92
0x180058f3b  mov     eax, cs:dword_18014E4B8
0x180058f41  test    eax, eax
0x180058f43  jnz     short loc_180058F59
0x180058f45  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180058f4c  jz      short loc_180058F7A
0x180058f4e  xor     ecx, ecx
0x180058f50  call    IsWppLevelEnabled
0x180058f55  test    al, al
0x180058f57  jz      short loc_180058F7A
0x180058f59  mov     rcx, [rsi+20h]; string
0x180058f5d  xor     edx, edx; length
0x180058f5f  mov     ebx, [rsi+68h]
0x180058f62  call    cs:__imp_WindowsGetStringRawBuffer
0x180058f68  mov     [rsp+60h+var_28], edi
0x180058f6c  mov     [rsp+60h+var_30], ebx
0x180058f70  mov     [rsp+60h+var_38], rax
0x180058f75  call    ??$ComTraceMessageT@PEBGW4RegistrationScope@Foundation@Windows@@J@@YAXPEBD0HW4TraceLevel@@PEBG2W4RegistrationScope@Foundation@Windows@@J@Z; ComTraceMessageT<ushort const *,Windows::Foundation::RegistrationScope,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,Windows::Foundation::RegistrationScope,long)
0x180058f7a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180058f7f  jmp     short loc_180058F92
0x180058f81  mov     rcx, r12
0x180058f84  cmp     rcx, [rsi+18h]
0x180058f88  jle     short loc_180058F8F
0x180058f8a  mov     [r8], r9d
0x180058f8d  jmp     short loc_180058F92
0x180058f8f  mov     [r8], r12d
0x180058f92  mov     eax, edi
0x180058f94  add     rsp, 60h
0x180058f98  pop     r15
0x180058f9a  pop     r14
0x180058f9c  pop     r12
0x180058f9e  pop     rdi
0x180058f9f  pop     rsi
0x180058fa0  pop     rbx
0x180058fa1  pop     rbp
0x180058fa2  retn
```
