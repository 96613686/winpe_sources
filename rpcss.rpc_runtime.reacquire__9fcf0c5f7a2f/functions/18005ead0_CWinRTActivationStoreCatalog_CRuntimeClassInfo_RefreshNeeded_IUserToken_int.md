# CWinRTActivationStoreCatalog::CRuntimeClassInfo::RefreshNeeded(IUserToken *,int *)

- ea: `0x18005ead0`
- end: `0x18005edc4`
- name: `?RefreshNeeded@CRuntimeClassInfo@CWinRTActivationStoreCatalog@@UEAAJPEAUIUserToken@@PEAH@Z`
- size: `756`
- prototype: `__int64 __fastcall(CWinRTActivationStoreCatalog::CRuntimeClassInfo *__hidden this, struct IUserToken *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180008c04`
- `0x18002750c`
- `0x180034260`
- `0x18005ead0`
- `0x180095c0c`
- `0x1800d69ec`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eb4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eb8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eb4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eb8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005eb64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005eba3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005eb64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005eba3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ed7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ed7c`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x18005ec1e`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x18005ec1e`

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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x18005ead0  push    rbp
0x18005ead2  push    rbx
0x18005ead3  push    rsi
0x18005ead4  push    rdi
0x18005ead5  push    r12
0x18005ead7  push    r14
0x18005ead9  push    r15
0x18005eadb  mov     rbp, rsp
0x18005eade  sub     rsp, 60h
0x18005eae2  xor     r12d, r12d
0x18005eae5  mov     rsi, rcx
0x18005eae8  mov     ecx, [rcx+68h]
0x18005eaeb  mov     r15, r8
0x18005eaee  mov     r14, rdx
0x18005eaf1  mov     edi, r12d
0x18005eaf4  lea     r9d, [r12+1]
0x18005eaf9  mov     [rbp+arg_0], r9d
0x18005eafd  test    ecx, ecx
0x18005eaff  jz      short loc_18005EB0F
0x18005eb01  sub     ecx, r9d
0x18005eb04  jz      short loc_18005EB28
0x18005eb06  cmp     ecx, r9d
0x18005eb09  jnz     loc_18005ED4E
0x18005eb0f  mov     rax, cs:?s_pReadCatalogCache@@3PEAUCOM_CATALOG_CACHE_SECTION@@EA; COM_CATALOG_CACHE_SECTION * s_pReadCatalogCache
0x18005eb16  test    rax, rax
0x18005eb19  jz      loc_18005EDA1
0x18005eb1f  mov     rcx, [rax+10h]
0x18005eb23  jmp     loc_18005EDA4
0x18005eb28  call    ?GetWinRTActivationStoreSequence@@YA_JXZ; GetWinRTActivationStoreSequence(void)
0x18005eb2d  cmp     rax, [rsi+18h]
0x18005eb31  jg      loc_18005ED4E
0x18005eb37  mov     rbx, [rsi+20h]
0x18005eb3b  xor     ecx, ecx; string
0x18005eb3d  mov     [rbp+var_8], r12
0x18005eb41  mov     [rbp+arg_18], r12
0x18005eb45  mov     [rbp+newString], r12
0x18005eb49  mov     [rbp+string], r12
0x18005eb4d  call    cs:__imp_WindowsDeleteString
0x18005eb54  nop     dword ptr [rax+rax+00h]
0x18005eb59  lea     rdx, [rbp+newString]; newString
0x18005eb5d  mov     [rbp+newString], r12
0x18005eb61  mov     rcx, rbx; string
0x18005eb64  call    cs:__imp_WindowsDuplicateString
0x18005eb6b  nop     dword ptr [rax+rax+00h]
0x18005eb70  mov     edi, eax
0x18005eb72  test    eax, eax
0x18005eb74  js      short loc_18005EBB1
0x18005eb76  mov     rbx, [rsi+38h]
0x18005eb7a  test    rbx, rbx
0x18005eb7d  jz      short loc_18005EB88
0x18005eb7f  mov     edi, r12d
0x18005eb82  cmp     rbx, [rbp+string]
0x18005eb86  jz      short loc_18005EBB1
0x18005eb88  mov     rcx, [rbp+string]; string
0x18005eb8c  call    cs:__imp_WindowsDeleteString
0x18005eb93  nop     dword ptr [rax+rax+00h]
0x18005eb98  lea     rdx, [rbp+string]; newString
0x18005eb9c  mov     [rbp+string], r12
0x18005eba0  mov     rcx, rbx; string
0x18005eba3  call    cs:__imp_WindowsDuplicateString
0x18005ebaa  nop     dword ptr [rax+rax+00h]
0x18005ebaf  mov     edi, eax
0x18005ebb1  test    r14, r14
0x18005ebb4  jz      short loc_18005EBF2
0x18005ebb6  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x18005ebbe  test    edi, edi
0x18005ebc0  js      loc_18005ED09
0x18005ebc6  mov     rax, [r14]
0x18005ebc9  lea     rdx, [rbp+var_10]
0x18005ebcd  mov     rcx, r14
0x18005ebd0  mov     rax, [rax+30h]
0x18005ebd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ebd9  mov     edi, eax
0x18005ebdb  test    eax, eax
0x18005ebdd  js      loc_18005ED09
0x18005ebe3  lea     rcx, [rbp+arg_18]
0x18005ebe7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005ebec  mov     rdx, [rbp+var_10]
0x18005ebf0  jmp     short loc_18005EC05
0x18005ebf2  test    edi, edi
0x18005ebf4  js      loc_18005ED09
0x18005ebfa  lea     rcx, [rbp+arg_18]
0x18005ebfe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005ec03  xor     edx, edx
0x18005ec05  mov     ecx, [rsi+68h]
0x18005ec08  lea     rax, [rbp+arg_18]
0x18005ec0c  lea     r9, _GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2
0x18005ec13  mov     [rsp+60h+var_40], rax
0x18005ec18  mov     r8d, 4
0x18005ec1e  call    cs:__imp_RoGetRegistrationStoreContext
0x18005ec25  nop     dword ptr [rax+rax+00h]
0x18005ec2a  mov     edi, eax
0x18005ec2c  test    eax, eax
0x18005ec2e  js      loc_18005ED09
0x18005ec34  mov     rcx, [rbp+arg_18]
0x18005ec38  lea     rdx, [rbp+var_8]
0x18005ec3c  mov     r9d, [rsi+88h]
0x18005ec43  mov     r8, [rbp+newString]
0x18005ec47  mov     [rsp+60h+var_40], rdx
0x18005ec4c  mov     rax, [rcx]
0x18005ec4f  mov     rdx, [rbp+string]
0x18005ec53  mov     rax, [rax+0C0h]
0x18005ec5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ec5f  mov     edi, eax
0x18005ec61  test    eax, eax
0x18005ec63  js      loc_18005ED09
0x18005ec69  mov     rax, [rbp+var_8]
0x18005ec6d  cmp     [rsi+90h], rax
0x18005ec74  jnz     loc_18005ED09
0x18005ec7a  cmp     [rsi+40h], r12d
0x18005ec7e  jnz     short loc_18005EC89
0x18005ec80  mov     [rbp+arg_0], r12d
0x18005ec84  jmp     loc_18005ED09
0x18005ec89  mov     rcx, [rsi+70h]
0x18005ec8d  mov     r9, r12
0x18005ec90  mov     [rbp+var_10], r12
0x18005ec94  test    rcx, rcx
0x18005ec97  jz      short loc_18005ECB3
0x18005ec99  mov     rax, [rcx]
0x18005ec9c  lea     r8, [rbp+var_10]
0x18005eca0  lea     rdx, _GUID_5868bd9b_be16_4c83_a560_0121173c48f1
0x18005eca7  mov     rax, [rax]
0x18005ecaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ecaf  mov     r9, [rbp+var_10]
0x18005ecb3  mov     [rbp+var_18], r12
0x18005ecb7  lea     r8, [rbp+var_18]
0x18005ecbb  mov     rax, [r9]
0x18005ecbe  lea     rdx, IID_ICacheRefresh
0x18005ecc5  mov     rcx, r9
0x18005ecc8  mov     rax, [rax]
0x18005eccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ecd0  mov     rcx, [rbp+var_18]
0x18005ecd4  lea     r8, [rbp+arg_0]
0x18005ecd8  mov     rdx, r14
0x18005ecdb  mov     rax, [rcx]
0x18005ecde  mov     rax, [rax+18h]
0x18005ece2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ece7  mov     rcx, [rbp+var_18]
0x18005eceb  mov     edi, eax
0x18005eced  mov     rax, [rcx]
0x18005ecf0  mov     rax, [rax+10h]
0x18005ecf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ecf9  mov     rcx, [rbp+var_10]
0x18005ecfd  mov     rax, [rcx]
0x18005ed00  mov     rax, [rax+10h]
0x18005ed04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed09  mov     rcx, [rbp+string]; string
0x18005ed0d  call    cs:__imp_WindowsDeleteString
0x18005ed14  nop     dword ptr [rax+rax+00h]
0x18005ed19  mov     rcx, [rbp+newString]; string
0x18005ed1d  mov     [rbp+string], r12
0x18005ed21  call    cs:__imp_WindowsDeleteString
0x18005ed28  nop     dword ptr [rax+rax+00h]
0x18005ed2d  mov     rcx, [rbp+arg_18]
0x18005ed31  mov     [rbp+newString], r12
0x18005ed35  test    rcx, rcx
0x18005ed38  jz      short loc_18005ED4A
0x18005ed3a  mov     [rbp+arg_18], r12
0x18005ed3e  mov     rax, [rcx]
0x18005ed41  mov     rax, [rax+10h]
0x18005ed45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed4a  mov     r9d, [rbp+arg_0]
0x18005ed4e  mov     [r15], r9d
0x18005ed51  test    edi, edi
0x18005ed53  jns     short loc_18005EDB2
0x18005ed55  mov     eax, cs:dword_1801574B8
0x18005ed5b  test    eax, eax
0x18005ed5d  jnz     short loc_18005ED73
0x18005ed5f  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18005ed66  jz      short loc_18005ED9A
0x18005ed68  xor     ecx, ecx
0x18005ed6a  call    IsWppLevelEnabled
0x18005ed6f  test    al, al
0x18005ed71  jz      short loc_18005ED9A
0x18005ed73  mov     rcx, [rsi+20h]; string
0x18005ed77  xor     edx, edx; length
0x18005ed79  mov     ebx, [rsi+68h]
0x18005ed7c  call    cs:__imp_WindowsGetStringRawBuffer
0x18005ed83  nop     dword ptr [rax+rax+00h]
0x18005ed88  mov     [rsp+60h+var_28], edi
0x18005ed8c  mov     [rsp+60h+var_30], ebx
0x18005ed90  mov     [rsp+60h+var_38], rax
0x18005ed95  call    ??$ComTraceMessageT@PEBGW4RegistrationScope@Foundation@Windows@@J@@YAXPEBD0HW4TraceLevel@@PEBG2W4RegistrationScope@Foundation@Windows@@J@Z; ComTraceMessageT<ushort const *,Windows::Foundation::RegistrationScope,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,Windows::Foundation::RegistrationScope,long)
0x18005ed9a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005ed9f  jmp     short loc_18005EDB2
0x18005eda1  mov     rcx, r12
0x18005eda4  cmp     rcx, [rsi+18h]
0x18005eda8  jle     short loc_18005EDAF
0x18005edaa  mov     [r8], r9d
0x18005edad  jmp     short loc_18005EDB2
0x18005edaf  mov     [r8], r12d
0x18005edb2  mov     eax, edi
0x18005edb4  add     rsp, 60h
0x18005edb8  pop     r15
0x18005edba  pop     r14
0x18005edbc  pop     r12
0x18005edbe  pop     rdi
0x18005edbf  pop     rsi
0x18005edc0  pop     rbx
0x18005edc1  pop     rbp
0x18005edc2  retn
```
