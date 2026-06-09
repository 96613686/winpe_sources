# Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_CopyContactNameAndThumbnail(Windows::ApplicationModel::Contacts::IContact2 *,Windows::ApplicationModel::Contacts::IContact2 *)

- ea: `0x1801d6308`
- end: `0x1801d66e1`
- name: `?_CopyContactNameAndThumbnail@ContactActionControlBase@Internal@Contacts@ApplicationModel@Windows@@KAJPEAUIContact2@345@0@Z`
- size: `985`
- prototype: `__int64 __fastcall(struct Windows::ApplicationModel::Contacts::IContact2 *, struct Windows::ApplicationModel::Contacts::IContact2 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801d6a00`
- `0x1801d78a0`
- `0x1801d7940`
- `0x1801d7a80`

## callees

- `0x18000b7e8`
- `0x1801d6308`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6458`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d64aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d64e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d653b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d655a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d65b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d65eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d660d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d66a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d66ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6458`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d64aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d64e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d653b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d655a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d65b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d65eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d660d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d66a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d66ad`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_CopyContactNameAndThumbnail(
        __int64 (__fastcall ***a1)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *),
        __int64 (__fastcall ***a2)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *))
{
  __int64 (__fastcall **v2)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  __int64 (__fastcall **v9)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v10)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v11)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v12)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v13)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v14)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  HSTRING v30; // [rsp+20h] [rbp-10h] BYREF
  __int64 v31; // [rsp+28h] [rbp-8h] BYREF
  __int64 v32; // [rsp+60h] [rbp+30h] BYREF
  __int64 v33; // [rsp+70h] [rbp+40h] BYREF
  HSTRING string; // [rsp+78h] [rbp+48h] BYREF

  v2 = *a1;
  v31 = 0;
  v5 = *v2;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
  v6 = v5((struct Windows::ApplicationModel::Contacts::IContact2 *)a1, &GUID_ec0072f3_2118_4049_9ebc_17f0ab692b64, &v31);
  if ( v6 >= 0 )
  {
    v7 = v31;
    v33 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 64LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
    v6 = v8(v7, &v33);
    if ( v6 >= 0 )
    {
      v9 = *a2;
      v32 = 0;
      v10 = *v9;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
      v6 = v10(
             (struct Windows::ApplicationModel::Contacts::IContact2 *)a2,
             &GUID_ec0072f3_2118_4049_9ebc_17f0ab692b64,
             &v32);
      if ( v6 >= 0 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 72LL))(v32, v33);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
    if ( v6 >= 0 )
    {
      v11 = *a1;
      v33 = 0;
      v12 = *v11;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
      v6 = v12(
             (struct Windows::ApplicationModel::Contacts::IContact2 *)a1,
             &GUID_f404e97b_9034_453c_8ebf_140a38c86f1d,
             &v33);
      if ( v6 >= 0 )
      {
        v13 = *a2;
        v32 = 0;
        v14 = *v13;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
        v6 = v14(
               (struct Windows::ApplicationModel::Contacts::IContact2 *)a2,
               &GUID_f404e97b_9034_453c_8ebf_140a38c86f1d,
               &v32);
        if ( v6 >= 0 )
        {
          v15 = v33;
          v30 = 0;
          v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 48LL);
          WindowsDeleteString(0);
          v30 = 0;
          v6 = v16(v15, &v30);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 56LL))(v32, v30);
            if ( v6 >= 0 )
            {
              v17 = v33;
              string = 0;
              v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 64LL);
              WindowsDeleteString(0);
              string = 0;
              v6 = v18(v17, &string);
              if ( v6 >= 0 )
                v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 72LL))(v32, string);
              WindowsDeleteString(string);
              if ( v6 >= 0 )
              {
                v19 = v33;
                string = 0;
                v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 80LL);
                WindowsDeleteString(0);
                string = 0;
                v6 = v20(v19, &string);
                if ( v6 >= 0 )
                  v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 88LL))(v32, string);
                WindowsDeleteString(string);
                if ( v6 >= 0 )
                {
                  v21 = v33;
                  string = 0;
                  v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 96LL);
                  WindowsDeleteString(0);
                  string = 0;
                  v6 = v22(v21, &string);
                  if ( v6 >= 0 )
                    v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 104LL))(v32, string);
                  WindowsDeleteString(string);
                  if ( v6 >= 0 )
                  {
                    v23 = v33;
                    string = 0;
                    v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 112LL);
                    WindowsDeleteString(0);
                    string = 0;
                    v6 = v24(v23, &string);
                    if ( v6 >= 0 )
                      v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 120LL))(v32, string);
                    WindowsDeleteString(string);
                    if ( v6 >= 0 )
                    {
                      v25 = v33;
                      string = 0;
                      v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 128LL);
                      WindowsDeleteString(0);
                      string = 0;
                      v6 = v26(v25, &string);
                      if ( v6 >= 0 )
                        v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 136LL))(v32, string);
                      WindowsDeleteString(string);
                      if ( v6 >= 0 )
                      {
                        v27 = v33;
                        string = 0;
                        v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 144LL);
                        WindowsDeleteString(0);
                        string = 0;
                        v6 = v28(v27, &string);
                        if ( v6 >= 0 )
                          v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 152LL))(v32, string);
                        WindowsDeleteString(string);
                      }
                    }
                  }
                }
              }
            }
          }
          WindowsDeleteString(v30);
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
    }
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801d6308  mov     [rsp-28h+arg_8], rbx
0x1801d630d  push    rbp
0x1801d630e  push    rsi
0x1801d630f  push    rdi
0x1801d6310  push    r14
0x1801d6312  push    r15
0x1801d6314  mov     rbp, rsp
0x1801d6317  sub     rsp, 30h
0x1801d631b  mov     rax, [rcx]
0x1801d631e  mov     r14, rcx
0x1801d6321  xor     r15d, r15d
0x1801d6324  lea     rcx, [rbp+var_8]
0x1801d6328  mov     rsi, rdx
0x1801d632b  mov     [rbp+var_8], r15
0x1801d632f  mov     rbx, [rax]
0x1801d6332  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d6337  lea     r8, [rbp+var_8]
0x1801d633b  mov     rcx, r14
0x1801d633e  lea     rdx, _GUID_ec0072f3_2118_4049_9ebc_17f0ab692b64
0x1801d6345  mov     rax, rbx
0x1801d6348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d634d  mov     ebx, eax
0x1801d634f  test    eax, eax
0x1801d6351  js      loc_1801D66C5
0x1801d6357  mov     rdi, [rbp+var_8]
0x1801d635b  lea     rcx, [rbp+arg_10]
0x1801d635f  mov     [rbp+arg_10], r15
0x1801d6363  mov     rax, [rdi]
0x1801d6366  mov     rbx, [rax+40h]
0x1801d636a  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d636f  lea     rdx, [rbp+arg_10]
0x1801d6373  mov     rcx, rdi
0x1801d6376  mov     rax, rbx
0x1801d6379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d637e  mov     ebx, eax
0x1801d6380  test    eax, eax
0x1801d6382  js      short loc_1801D63D0
0x1801d6384  mov     rax, [rsi]
0x1801d6387  lea     rcx, [rbp+arg_0]
0x1801d638b  mov     [rbp+arg_0], r15
0x1801d638f  mov     rbx, [rax]
0x1801d6392  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d6397  lea     r8, [rbp+arg_0]
0x1801d639b  mov     rcx, rsi
0x1801d639e  lea     rdx, _GUID_ec0072f3_2118_4049_9ebc_17f0ab692b64
0x1801d63a5  mov     rax, rbx
0x1801d63a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d63ad  mov     ebx, eax
0x1801d63af  test    eax, eax
0x1801d63b1  js      short loc_1801D63C7
0x1801d63b3  mov     rcx, [rbp+arg_0]
0x1801d63b7  mov     rdx, [rbp+arg_10]
0x1801d63bb  mov     rax, [rcx]
0x1801d63be  mov     rax, [rax+48h]
0x1801d63c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d63c7  lea     rcx, [rbp+arg_0]
0x1801d63cb  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d63d0  lea     rcx, [rbp+arg_10]
0x1801d63d4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d63d9  test    ebx, ebx
0x1801d63db  js      loc_1801D66C5
0x1801d63e1  mov     rax, [r14]
0x1801d63e4  lea     rcx, [rbp+arg_10]
0x1801d63e8  mov     [rbp+arg_10], r15
0x1801d63ec  mov     rbx, [rax]
0x1801d63ef  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d63f4  lea     r8, [rbp+arg_10]
0x1801d63f8  mov     rcx, r14
0x1801d63fb  lea     rdx, _GUID_f404e97b_9034_453c_8ebf_140a38c86f1d
0x1801d6402  mov     rax, rbx
0x1801d6405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d640a  mov     ebx, eax
0x1801d640c  test    eax, eax
0x1801d640e  js      loc_1801D66BC
0x1801d6414  mov     rax, [rsi]
0x1801d6417  lea     rcx, [rbp+arg_0]
0x1801d641b  mov     [rbp+arg_0], r15
0x1801d641f  mov     rbx, [rax]
0x1801d6422  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d6427  lea     r8, [rbp+arg_0]
0x1801d642b  mov     rcx, rsi
0x1801d642e  lea     rdx, _GUID_f404e97b_9034_453c_8ebf_140a38c86f1d
0x1801d6435  mov     rax, rbx
0x1801d6438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d643d  mov     ebx, eax
0x1801d643f  test    eax, eax
0x1801d6441  js      loc_1801D66B3
0x1801d6447  mov     rdi, [rbp+arg_10]
0x1801d644b  xor     ecx, ecx; string
0x1801d644d  mov     [rbp+var_10], r15
0x1801d6451  mov     rax, [rdi]
0x1801d6454  mov     rbx, [rax+30h]
0x1801d6458  call    cs:__imp_WindowsDeleteString
0x1801d645e  lea     rdx, [rbp+var_10]
0x1801d6462  mov     [rbp+var_10], r15
0x1801d6466  mov     rcx, rdi
0x1801d6469  mov     rax, rbx
0x1801d646c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d6471  mov     ebx, eax
0x1801d6473  test    eax, eax
0x1801d6475  js      loc_1801D66A9
0x1801d647b  mov     rcx, [rbp+arg_0]
0x1801d647f  mov     rdx, [rbp+var_10]
0x1801d6483  mov     rax, [rcx]
0x1801d6486  mov     rax, [rax+38h]
0x1801d648a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d648f  mov     ebx, eax
0x1801d6491  test    eax, eax
0x1801d6493  js      loc_1801D66A9
0x1801d6499  mov     rdi, [rbp+arg_10]
0x1801d649d  xor     ecx, ecx; string
0x1801d649f  mov     [rbp+string], r15
0x1801d64a3  mov     rax, [rdi]
0x1801d64a6  mov     rbx, [rax+40h]
0x1801d64aa  call    cs:__imp_WindowsDeleteString
0x1801d64b0  lea     rdx, [rbp+string]
0x1801d64b4  mov     [rbp+string], r15
0x1801d64b8  mov     rcx, rdi
0x1801d64bb  mov     rax, rbx
0x1801d64be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d64c3  mov     ebx, eax
0x1801d64c5  test    eax, eax
0x1801d64c7  js      short loc_1801D64DF
0x1801d64c9  mov     rcx, [rbp+arg_0]
0x1801d64cd  mov     rdx, [rbp+string]
0x1801d64d1  mov     rax, [rcx]
0x1801d64d4  mov     rax, [rax+48h]
0x1801d64d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d64dd  mov     ebx, eax
0x1801d64df  mov     rcx, [rbp+string]; string
0x1801d64e3  call    cs:__imp_WindowsDeleteString
0x1801d64e9  test    ebx, ebx
0x1801d64eb  js      loc_1801D66A9
0x1801d64f1  mov     rdi, [rbp+arg_10]
0x1801d64f5  xor     ecx, ecx; string
0x1801d64f7  mov     [rbp+string], r15
0x1801d64fb  mov     rax, [rdi]
0x1801d64fe  mov     rbx, [rax+50h]
0x1801d6502  call    cs:__imp_WindowsDeleteString
0x1801d6508  lea     rdx, [rbp+string]
0x1801d650c  mov     [rbp+string], r15
0x1801d6510  mov     rcx, rdi
0x1801d6513  mov     rax, rbx
0x1801d6516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d651b  mov     ebx, eax
0x1801d651d  test    eax, eax
0x1801d651f  js      short loc_1801D6537
0x1801d6521  mov     rcx, [rbp+arg_0]
0x1801d6525  mov     rdx, [rbp+string]
0x1801d6529  mov     rax, [rcx]
0x1801d652c  mov     rax, [rax+58h]
0x1801d6530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d6535  mov     ebx, eax
0x1801d6537  mov     rcx, [rbp+string]; string
0x1801d653b  call    cs:__imp_WindowsDeleteString
0x1801d6541  test    ebx, ebx
0x1801d6543  js      loc_1801D66A9
0x1801d6549  mov     rdi, [rbp+arg_10]
0x1801d654d  xor     ecx, ecx; string
0x1801d654f  mov     [rbp+string], r15
0x1801d6553  mov     rax, [rdi]
0x1801d6556  mov     rbx, [rax+60h]
0x1801d655a  call    cs:__imp_WindowsDeleteString
0x1801d6560  lea     rdx, [rbp+string]
0x1801d6564  mov     [rbp+string], r15
0x1801d6568  mov     rcx, rdi
0x1801d656b  mov     rax, rbx
0x1801d656e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d6573  mov     ebx, eax
0x1801d6575  test    eax, eax
0x1801d6577  js      short loc_1801D658F
0x1801d6579  mov     rcx, [rbp+arg_0]
0x1801d657d  mov     rdx, [rbp+string]
0x1801d6581  mov     rax, [rcx]
0x1801d6584  mov     rax, [rax+68h]
0x1801d6588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d658d  mov     ebx, eax
0x1801d658f  mov     rcx, [rbp+string]; string
0x1801d6593  call    cs:__imp_WindowsDeleteString
0x1801d6599  test    ebx, ebx
0x1801d659b  js      loc_1801D66A9
0x1801d65a1  mov     rdi, [rbp+arg_10]
0x1801d65a5  xor     ecx, ecx; string
0x1801d65a7  mov     [rbp+string], r15
0x1801d65ab  mov     rax, [rdi]
0x1801d65ae  mov     rbx, [rax+70h]
0x1801d65b2  call    cs:__imp_WindowsDeleteString
0x1801d65b8  lea     rdx, [rbp+string]
0x1801d65bc  mov     [rbp+string], r15
0x1801d65c0  mov     rcx, rdi
0x1801d65c3  mov     rax, rbx
0x1801d65c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d65cb  mov     ebx, eax
0x1801d65cd  test    eax, eax
0x1801d65cf  js      short loc_1801D65E7
0x1801d65d1  mov     rcx, [rbp+arg_0]
0x1801d65d5  mov     rdx, [rbp+string]
0x1801d65d9  mov     rax, [rcx]
0x1801d65dc  mov     rax, [rax+78h]
0x1801d65e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d65e5  mov     ebx, eax
0x1801d65e7  mov     rcx, [rbp+string]; string
0x1801d65eb  call    cs:__imp_WindowsDeleteString
0x1801d65f1  test    ebx, ebx
0x1801d65f3  js      loc_1801D66A9
0x1801d65f9  mov     rdi, [rbp+arg_10]
0x1801d65fd  xor     ecx, ecx; string
0x1801d65ff  mov     [rbp+string], r15
0x1801d6603  mov     rax, [rdi]
0x1801d6606  mov     rbx, [rax+80h]
0x1801d660d  call    cs:__imp_WindowsDeleteString
0x1801d6613  lea     rdx, [rbp+string]
0x1801d6617  mov     [rbp+string], r15
0x1801d661b  mov     rcx, rdi
0x1801d661e  mov     rax, rbx
0x1801d6621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d6626  mov     ebx, eax
0x1801d6628  test    eax, eax
0x1801d662a  js      short loc_1801D6645
0x1801d662c  mov     rcx, [rbp+arg_0]
0x1801d6630  mov     rdx, [rbp+string]
0x1801d6634  mov     rax, [rcx]
0x1801d6637  mov     rax, [rax+88h]
0x1801d663e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d6643  mov     ebx, eax
0x1801d6645  mov     rcx, [rbp+string]; string
0x1801d6649  call    cs:__imp_WindowsDeleteString
0x1801d664f  test    ebx, ebx
0x1801d6651  js      short loc_1801D66A9
0x1801d6653  mov     rdi, [rbp+arg_10]
0x1801d6657  xor     ecx, ecx; string
0x1801d6659  mov     [rbp+string], r15
0x1801d665d  mov     rax, [rdi]
0x1801d6660  mov     rbx, [rax+90h]
0x1801d6667  call    cs:__imp_WindowsDeleteString
0x1801d666d  lea     rdx, [rbp+string]
0x1801d6671  mov     [rbp+string], r15
0x1801d6675  mov     rcx, rdi
0x1801d6678  mov     rax, rbx
0x1801d667b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d6680  mov     ebx, eax
0x1801d6682  test    eax, eax
0x1801d6684  js      short loc_1801D669F
0x1801d6686  mov     rcx, [rbp+arg_0]
0x1801d668a  mov     rdx, [rbp+string]
0x1801d668e  mov     rax, [rcx]
0x1801d6691  mov     rax, [rax+98h]
0x1801d6698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d669d  mov     ebx, eax
0x1801d669f  mov     rcx, [rbp+string]; string
0x1801d66a3  call    cs:__imp_WindowsDeleteString
0x1801d66a9  mov     rcx, [rbp+var_10]; string
0x1801d66ad  call    cs:__imp_WindowsDeleteString
0x1801d66b3  lea     rcx, [rbp+arg_0]
0x1801d66b7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d66bc  lea     rcx, [rbp+arg_10]
0x1801d66c0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d66c5  lea     rcx, [rbp+var_8]
0x1801d66c9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d66ce  mov     eax, ebx
0x1801d66d0  mov     rbx, [rsp+30h+arg_8]
0x1801d66d5  add     rsp, 30h
0x1801d66d9  pop     r15
0x1801d66db  pop     r14
0x1801d66dd  pop     rdi
0x1801d66de  pop     rsi
0x1801d66df  pop     rbp
0x1801d66e0  retn
```
