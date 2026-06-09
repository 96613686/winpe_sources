# Windows::ApplicationModel::Contacts::Internal::ContactDisplayInformation::_InitializeContactDisplayName(Windows::ApplicationModel::Contacts::IContact2 *)

- ea: `0x1801c95c8`
- end: `0x1801c9892`
- name: `?_InitializeContactDisplayName@ContactDisplayInformation@Internal@Contacts@ApplicationModel@Windows@@AEAAJPEAUIContact2@345@@Z`
- size: `714`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Contacts::Internal::ContactDisplayInformation *__hidden this, struct Windows::ApplicationModel::Contacts::IContact2 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801c9898`

## callees

- `0x18000b7e8`
- `0x1800e6b28`
- `0x1801c4314`
- `0x1801c95c8`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c965b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c968f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c96c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c976b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c97f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c982e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c985e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9872`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c965b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c968f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c96c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c976b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c97f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c982e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c985e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9872`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactDisplayInformation::_InitializeContactDisplayName(
        HSTRING *this,
        __int64 (__fastcall ***a2)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *))
{
  __int64 (__fastcall **v2)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  __int64 (__fastcall **v15)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v16)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  HSTRING v17; // rsi
  HSTRING v18; // rdi
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rdi
  HSTRING v21; // rcx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  int v24; // eax
  __int64 (__fastcall **v25)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v26)(struct Windows::ApplicationModel::Contacts::IContact2 *, __int64 *); // rbx
  _lambda_aec159daf75c9a566e43618f77172940_ *v27; // rax
  HSTRING v28; // rcx
  __int64 v30; // [rsp+20h] [rbp-30h] BYREF
  HSTRING v31; // [rsp+28h] [rbp-28h] BYREF
  __int64 v32; // [rsp+30h] [rbp-20h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v34[16]; // [rsp+40h] [rbp-10h] BYREF
  HSTRING v35; // [rsp+98h] [rbp+48h] BYREF
  HSTRING v36; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v37; // [rsp+A8h] [rbp+58h] BYREF

  v2 = *a2;
  v37 = 0;
  v5 = *v2;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
  v6 = v5((struct Windows::ApplicationModel::Contacts::IContact2 *)a2, &GUID_f404e97b_9034_453c_8ebf_140a38c86f1d, &v37);
  if ( v6 >= 0 )
  {
    v7 = v37;
    v36 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 48LL);
    WindowsDeleteString(0);
    v36 = 0;
    v6 = v8(v7, &v36);
    if ( v6 < 0 )
    {
LABEL_34:
      WindowsDeleteString(v36);
      goto LABEL_35;
    }
    v9 = v37;
    v35 = 0;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 64LL);
    WindowsDeleteString(0);
    v35 = 0;
    v6 = v10(v9, &v35);
    if ( v6 < 0 )
    {
LABEL_33:
      WindowsDeleteString(v35);
      goto LABEL_34;
    }
    v11 = v37;
    v31 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 96LL);
    WindowsDeleteString(0);
    v31 = 0;
    v6 = v12(v11, &v31);
    if ( v6 < 0 )
    {
LABEL_32:
      WindowsDeleteString(v31);
      goto LABEL_33;
    }
    v13 = v37;
    string = 0;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 112LL);
    WindowsDeleteString(0);
    string = 0;
    v6 = v14(v13, &string);
    if ( v6 < 0 )
    {
LABEL_31:
      WindowsDeleteString(string);
      goto LABEL_32;
    }
    v15 = *a2;
    v30 = 0;
    v16 = *v15;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v30);
    v6 = v16(
           (struct Windows::ApplicationModel::Contacts::IContact2 *)a2,
           &GUID_811233d1_3151_4e14_83da_ad47404c0b41,
           &v30);
    if ( v6 < 0 )
    {
LABEL_30:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v30);
      goto LABEL_31;
    }
    v17 = v36;
    v18 = v35;
    if ( v36 && v35 )
    {
      v19 = v30;
      v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 72LL);
LABEL_28:
      WindowsDeleteString(this[6]);
      this[6] = 0;
      v24 = v20(v19, this + 6);
      goto LABEL_29;
    }
    if ( string )
    {
      if ( v31 )
      {
        if ( !v36 )
        {
          v21 = this[6];
          if ( !v35 )
          {
            v22 = v30;
            v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 80LL);
            WindowsDeleteString(v21);
            this[6] = 0;
            v24 = v23(v22, this + 6);
LABEL_29:
            v6 = v24;
            goto LABEL_30;
          }
          goto LABEL_24;
        }
LABEL_26:
        v28 = this[6];
        v36 = 0;
        WindowsDeleteString(v28);
        this[6] = v17;
        goto LABEL_30;
      }
    }
    else if ( v31 )
    {
      if ( v36 )
        goto LABEL_26;
      goto LABEL_27;
    }
    if ( !string )
    {
      if ( v36 )
        goto LABEL_26;
      if ( !v35 )
      {
        v25 = *a2;
        v32 = 0;
        v26 = (__int64 (__fastcall *)(struct Windows::ApplicationModel::Contacts::IContact2 *, __int64 *))v25[16];
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
        v6 = v26((struct Windows::ApplicationModel::Contacts::IContact2 *)a2, &v32);
        if ( v6 >= 0 )
        {
          v27 = _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(
                  (_lambda_aec159daf75c9a566e43618f77172940_ *)v34,
                  (struct CSearchSuggestionsProvider *)this);
          v6 = IterateOverVector_Windows::ApplicationModel::Contacts::ContactJobInfo__lambda_1322b4bfb983f315d52d35d98b81b5ca___(
                 v32,
                 v27);
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
        goto LABEL_30;
      }
LABEL_23:
      v21 = this[6];
LABEL_24:
      v35 = 0;
      WindowsDeleteString(v21);
      this[6] = v18;
      goto LABEL_30;
    }
    if ( v35 )
      goto LABEL_23;
LABEL_27:
    v19 = v30;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 80LL);
    goto LABEL_28;
  }
LABEL_35:
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801c95c8  push    rbp
0x1801c95ca  push    rbx
0x1801c95cb  push    rsi
0x1801c95cc  push    rdi
0x1801c95cd  push    r12
0x1801c95cf  push    r14
0x1801c95d1  push    r15
0x1801c95d3  mov     rbp, rsp
0x1801c95d6  sub     rsp, 50h
0x1801c95da  mov     rax, [rdx]
0x1801c95dd  mov     r14, rcx
0x1801c95e0  xor     r12d, r12d
0x1801c95e3  lea     rcx, [rbp+arg_18]
0x1801c95e7  mov     r15, rdx
0x1801c95ea  mov     [rbp+arg_18], r12
0x1801c95ee  mov     rbx, [rax]
0x1801c95f1  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801c95f6  lea     r8, [rbp+arg_18]
0x1801c95fa  mov     rcx, r15
0x1801c95fd  lea     rdx, _GUID_f404e97b_9034_453c_8ebf_140a38c86f1d
0x1801c9604  mov     rax, rbx
0x1801c9607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c960c  mov     ebx, eax
0x1801c960e  test    eax, eax
0x1801c9610  js      loc_1801C9878
0x1801c9616  mov     rdi, [rbp+arg_18]
0x1801c961a  xor     ecx, ecx; string
0x1801c961c  mov     [rbp+arg_10], r12
0x1801c9620  mov     rax, [rdi]
0x1801c9623  mov     rbx, [rax+30h]
0x1801c9627  call    cs:__imp_WindowsDeleteString
0x1801c962d  lea     rdx, [rbp+arg_10]
0x1801c9631  mov     [rbp+arg_10], r12
0x1801c9635  mov     rcx, rdi
0x1801c9638  mov     rax, rbx
0x1801c963b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9640  mov     ebx, eax
0x1801c9642  test    eax, eax
0x1801c9644  js      loc_1801C986E
0x1801c964a  mov     rdi, [rbp+arg_18]
0x1801c964e  xor     ecx, ecx; string
0x1801c9650  mov     [rbp+arg_8], r12
0x1801c9654  mov     rax, [rdi]
0x1801c9657  mov     rbx, [rax+40h]
0x1801c965b  call    cs:__imp_WindowsDeleteString
0x1801c9661  lea     rdx, [rbp+arg_8]
0x1801c9665  mov     [rbp+arg_8], r12
0x1801c9669  mov     rcx, rdi
0x1801c966c  mov     rax, rbx
0x1801c966f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9674  mov     ebx, eax
0x1801c9676  test    eax, eax
0x1801c9678  js      loc_1801C9864
0x1801c967e  mov     rdi, [rbp+arg_18]
0x1801c9682  xor     ecx, ecx; string
0x1801c9684  mov     [rbp+var_28], r12
0x1801c9688  mov     rax, [rdi]
0x1801c968b  mov     rbx, [rax+60h]
0x1801c968f  call    cs:__imp_WindowsDeleteString
0x1801c9695  lea     rdx, [rbp+var_28]
0x1801c9699  mov     [rbp+var_28], r12
0x1801c969d  mov     rcx, rdi
0x1801c96a0  mov     rax, rbx
0x1801c96a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c96a8  mov     ebx, eax
0x1801c96aa  test    eax, eax
0x1801c96ac  js      loc_1801C985A
0x1801c96b2  mov     rdi, [rbp+arg_18]
0x1801c96b6  xor     ecx, ecx; string
0x1801c96b8  mov     [rbp+string], r12
0x1801c96bc  mov     rax, [rdi]
0x1801c96bf  mov     rbx, [rax+70h]
0x1801c96c3  call    cs:__imp_WindowsDeleteString
0x1801c96c9  lea     rdx, [rbp+string]
0x1801c96cd  mov     [rbp+string], r12
0x1801c96d1  mov     rcx, rdi
0x1801c96d4  mov     rax, rbx
0x1801c96d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c96dc  mov     ebx, eax
0x1801c96de  test    eax, eax
0x1801c96e0  js      loc_1801C9850
0x1801c96e6  mov     rax, [r15]
0x1801c96e9  lea     rcx, [rbp+var_30]
0x1801c96ed  mov     [rbp+var_30], r12
0x1801c96f1  mov     rbx, [rax]
0x1801c96f4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801c96f9  lea     r8, [rbp+var_30]
0x1801c96fd  mov     rcx, r15
0x1801c9700  lea     rdx, _GUID_811233d1_3151_4e14_83da_ad47404c0b41
0x1801c9707  mov     rax, rbx
0x1801c970a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c970f  mov     ebx, eax
0x1801c9711  test    eax, eax
0x1801c9713  js      loc_1801C9847
0x1801c9719  mov     rsi, [rbp+arg_10]
0x1801c971d  mov     rdi, [rbp+arg_8]
0x1801c9721  test    rsi, rsi
0x1801c9724  jz      short loc_1801C973B
0x1801c9726  test    rdi, rdi
0x1801c9729  jz      short loc_1801C973B
0x1801c972b  mov     rsi, [rbp+var_30]
0x1801c972f  mov     rax, [rsi]
0x1801c9732  mov     rdi, [rax+48h]
0x1801c9736  jmp     loc_1801C9827
0x1801c973b  mov     rax, [rbp+string]
0x1801c973f  test    rax, rax
0x1801c9742  jz      short loc_1801C9784
0x1801c9744  cmp     [rbp+var_28], r12
0x1801c9748  jz      short loc_1801C978A
0x1801c974a  test    rsi, rsi
0x1801c974d  jnz     loc_1801C9808
0x1801c9753  mov     rcx, [r14+30h]; string
0x1801c9757  test    rdi, rdi
0x1801c975a  jnz     loc_1801C97F3
0x1801c9760  mov     rdi, [rbp+var_30]
0x1801c9764  mov     rax, [rdi]
0x1801c9767  mov     rbx, [rax+50h]
0x1801c976b  call    cs:__imp_WindowsDeleteString
0x1801c9771  lea     rdx, [r14+30h]
0x1801c9775  mov     [r14+30h], r12
0x1801c9779  mov     rcx, rdi
0x1801c977c  mov     rax, rbx
0x1801c977f  jmp     loc_1801C9840
0x1801c9784  cmp     [rbp+var_28], r12
0x1801c9788  jnz     short loc_1801C9803
0x1801c978a  test    rax, rax
0x1801c978d  jnz     short loc_1801C97EA
0x1801c978f  test    rsi, rsi
0x1801c9792  jnz     short loc_1801C9808
0x1801c9794  test    rdi, rdi
0x1801c9797  jnz     short loc_1801C97EF
0x1801c9799  mov     rax, [r15]
0x1801c979c  lea     rcx, [rbp+var_20]
0x1801c97a0  mov     [rbp+var_20], r12
0x1801c97a4  mov     rbx, [rax+80h]
0x1801c97ab  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801c97b0  lea     rdx, [rbp+var_20]
0x1801c97b4  mov     rcx, r15
0x1801c97b7  mov     rax, rbx
0x1801c97ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c97bf  mov     ebx, eax
0x1801c97c1  test    eax, eax
0x1801c97c3  js      short loc_1801C97DF
0x1801c97c5  mov     rdx, r14; struct CSearchSuggestionsProvider *
0x1801c97c8  lea     rcx, [rbp+var_10]; this
0x1801c97cc  call    ??0_lambda_aec159daf75c9a566e43618f77172940_@@QEAA@PEAVCSearchSuggestionsProvider@@@Z; _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(CSearchSuggestionsProvider *)
0x1801c97d1  mov     rcx, [rbp+var_20]
0x1801c97d5  mov     rdx, rax
0x1801c97d8  call    IterateOverVector_Windows__ApplicationModel__Contacts__ContactJobInfo__lambda_1322b4bfb983f315d52d35d98b81b5ca___
0x1801c97dd  mov     ebx, eax
0x1801c97df  lea     rcx, [rbp+var_20]
0x1801c97e3  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801c97e8  jmp     short loc_1801C9847
0x1801c97ea  test    rdi, rdi
0x1801c97ed  jz      short loc_1801C981C
0x1801c97ef  mov     rcx, [r14+30h]; string
0x1801c97f3  mov     [rbp+arg_8], r12
0x1801c97f7  call    cs:__imp_WindowsDeleteString
0x1801c97fd  mov     [r14+30h], rdi
0x1801c9801  jmp     short loc_1801C9847
0x1801c9803  test    rsi, rsi
0x1801c9806  jz      short loc_1801C981C
0x1801c9808  mov     rcx, [r14+30h]; string
0x1801c980c  mov     [rbp+arg_10], r12
0x1801c9810  call    cs:__imp_WindowsDeleteString
0x1801c9816  mov     [r14+30h], rsi
0x1801c981a  jmp     short loc_1801C9847
0x1801c981c  mov     rsi, [rbp+var_30]
0x1801c9820  mov     rax, [rsi]
0x1801c9823  mov     rdi, [rax+50h]
0x1801c9827  lea     rbx, [r14+30h]
0x1801c982b  mov     rcx, [rbx]; string
0x1801c982e  call    cs:__imp_WindowsDeleteString
0x1801c9834  mov     rdx, rbx
0x1801c9837  mov     [rbx], r12
0x1801c983a  mov     rcx, rsi
0x1801c983d  mov     rax, rdi
0x1801c9840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9845  mov     ebx, eax
0x1801c9847  lea     rcx, [rbp+var_30]
0x1801c984b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801c9850  mov     rcx, [rbp+string]; string
0x1801c9854  call    cs:__imp_WindowsDeleteString
0x1801c985a  mov     rcx, [rbp+var_28]; string
0x1801c985e  call    cs:__imp_WindowsDeleteString
0x1801c9864  mov     rcx, [rbp+arg_8]; string
0x1801c9868  call    cs:__imp_WindowsDeleteString
0x1801c986e  mov     rcx, [rbp+arg_10]; string
0x1801c9872  call    cs:__imp_WindowsDeleteString
0x1801c9878  lea     rcx, [rbp+arg_18]
0x1801c987c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801c9881  mov     eax, ebx
0x1801c9883  add     rsp, 50h
0x1801c9887  pop     r15
0x1801c9889  pop     r14
0x1801c988b  pop     r12
0x1801c988d  pop     rdi
0x1801c988e  pop     rsi
0x1801c988f  pop     rbx
0x1801c9890  pop     rbp
0x1801c9891  retn
```
