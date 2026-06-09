# RegistryOperationCallBack(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x18011a5e0`
- end: `0x18011a8bb`
- name: `?RegistryOperationCallBack@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `731`
- prototype: `void(struct _TP_CALLBACK_INSTANCE *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18002fee0`
- `0x18011a5e0`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a64a`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a69c`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a705`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a75c`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a7d2`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a820`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a64a`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a69c`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a705`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a75c`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a7d2`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011a820`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18011a89e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18011a89e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18011a5f9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18011a5f9`

## pseudocode

```c
void __fastcall RegistryOperationCallBack(struct _TP_CALLBACK_INSTANCE *a1, unsigned int *a2)
{
  __int64 v3; // [rsp+50h] [rbp+20h] BYREF
  struct IEUserBroker *v4; // [rsp+58h] [rbp+28h] BYREF

  if ( CoInitializeEx(0, 0) >= 0 )
  {
    if ( *a2 )
    {
      if ( *a2 != 1 )
      {
        switch ( *a2 )
        {
          case 2u:
            v4 = 0;
            if ( (int)CoCreateUserBroker(&v4) >= 0 )
            {
              v3 = 0;
              if ( (**(int (__fastcall ***)(struct IEUserBroker *, GUID *, __int64 *))v4)(
                     v4,
                     &IID_IERegHelperBroker,
                     &v3) >= 0 )
              {
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 24LL))(v3, a2[1]);
                goto LABEL_21;
              }
LABEL_22:
              (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v4 + 16LL))(v4);
            }
            break;
          case 3u:
            v4 = 0;
            if ( (int)CoCreateUserBroker(&v4) >= 0 )
            {
              v3 = 0;
              if ( (**(int (__fastcall ***)(struct IEUserBroker *, GUID *, __int64 *))v4)(
                     v4,
                     &IID_IERegHelperBroker,
                     &v3) >= 0 )
              {
                (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, a2[1], a2[2]);
LABEL_21:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
                goto LABEL_22;
              }
              goto LABEL_22;
            }
            break;
          case 4u:
            v4 = 0;
            if ( (int)CoCreateUserBroker(&v4) >= 0 )
            {
              v3 = 0;
              if ( (**(int (__fastcall ***)(struct IEUserBroker *, GUID *, __int64 *))v4)(
                     v4,
                     &IID_IERegHelperBroker,
                     &v3) >= 0 )
              {
                (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned int))(*(_QWORD *)v3 + 56LL))(
                  v3,
                  a2[1],
                  a2[2],
                  *((_QWORD *)a2 + 2),
                  a2[6]);
                goto LABEL_29;
              }
LABEL_30:
              (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v4 + 16LL))(v4);
            }
LABEL_31:
            operator delete(*((void **)a2 + 2));
            break;
          case 5u:
            v4 = 0;
            if ( (int)CoCreateUserBroker(&v4) < 0 )
              break;
            v3 = 0;
            if ( (**(int (__fastcall ***)(struct IEUserBroker *, GUID *, __int64 *))v4)(v4, &IID_IERegHelperBroker, &v3) < 0 )
              goto LABEL_22;
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 64LL))(v3, a2[1]);
            goto LABEL_21;
          default:
            break;
        }
        operator delete(a2);
        CoUninitialize();
        return;
      }
      v4 = 0;
      if ( (int)CoCreateUserBroker(&v4) < 0 )
        goto LABEL_31;
      v3 = 0;
      if ( (**(int (__fastcall ***)(struct IEUserBroker *, GUID *, __int64 *))v4)(v4, &IID_IERegHelperBroker, &v3) < 0 )
        goto LABEL_30;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned int))(*(_QWORD *)v3 + 48LL))(
        v3,
        a2[1],
        a2[2],
        *((_QWORD *)a2 + 2),
        a2[6]);
    }
    else
    {
      v4 = 0;
      if ( (int)CoCreateUserBroker(&v4) < 0 )
        goto LABEL_31;
      v3 = 0;
      if ( (**(int (__fastcall ***)(struct IEUserBroker *, GUID *, __int64 *))v4)(v4, &IID_IERegHelperBroker, &v3) < 0 )
        goto LABEL_30;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v3 + 40LL))(
        v3,
        a2[1],
        *((_QWORD *)a2 + 2),
        a2[6]);
    }
LABEL_29:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x18011a5e0  mov     [rsp-8+arg_0], rbx
0x18011a5e5  mov     [rsp-8+arg_8], rdi
0x18011a5ea  push    rbp
0x18011a5eb  mov     rbp, rsp
0x18011a5ee  sub     rsp, 30h
0x18011a5f2  mov     rbx, rdx
0x18011a5f5  xor     ecx, ecx; pvReserved
0x18011a5f7  xor     edx, edx; dwCoInit
0x18011a5f9  call    cs:__imp_CoInitializeEx
0x18011a600  nop     dword ptr [rax+rax+00h]
0x18011a605  xor     edi, edi
0x18011a607  test    eax, eax
0x18011a609  js      loc_18011A8AA
0x18011a60f  mov     ecx, [rbx]
0x18011a611  test    ecx, ecx
0x18011a613  jz      loc_18011A818
0x18011a619  sub     ecx, 1
0x18011a61c  jz      loc_18011A7CA
0x18011a622  sub     ecx, 1
0x18011a625  jz      loc_18011A754
0x18011a62b  sub     ecx, 1
0x18011a62e  jz      loc_18011A6FD
0x18011a634  sub     ecx, 1
0x18011a637  jz      short loc_18011A694
0x18011a639  cmp     ecx, 1
0x18011a63c  jnz     loc_18011A896
0x18011a642  lea     rcx, [rbp+arg_18]
0x18011a646  mov     [rbp+arg_18], rdi
0x18011a64a  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18011a651  nop     dword ptr [rax+rax+00h]
0x18011a656  test    eax, eax
0x18011a658  js      loc_18011A896
0x18011a65e  mov     rcx, [rbp+arg_18]
0x18011a662  lea     r8, [rbp+arg_10]
0x18011a666  mov     [rbp+arg_10], rdi
0x18011a66a  lea     rdx, IID_IERegHelperBroker
0x18011a671  mov     rax, [rcx]
0x18011a674  mov     rax, [rax]
0x18011a677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a67c  test    eax, eax
0x18011a67e  js      loc_18011A7B5
0x18011a684  mov     rcx, [rbp+arg_10]
0x18011a688  mov     rax, [rcx]
0x18011a68b  mov     rax, [rax+40h]
0x18011a68f  jmp     loc_18011A79D
0x18011a694  lea     rcx, [rbp+arg_18]
0x18011a698  mov     [rbp+arg_18], rdi
0x18011a69c  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18011a6a3  nop     dword ptr [rax+rax+00h]
0x18011a6a8  test    eax, eax
0x18011a6aa  js      loc_18011A88D
0x18011a6b0  mov     rcx, [rbp+arg_18]
0x18011a6b4  lea     r8, [rbp+arg_10]
0x18011a6b8  mov     [rbp+arg_10], rdi
0x18011a6bc  lea     rdx, IID_IERegHelperBroker
0x18011a6c3  mov     rax, [rcx]
0x18011a6c6  mov     rax, [rax]
0x18011a6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a6ce  test    eax, eax
0x18011a6d0  js      loc_18011A87D
0x18011a6d6  mov     rcx, [rbp+arg_10]
0x18011a6da  mov     rax, [rcx]
0x18011a6dd  mov     rax, [rax+38h]
0x18011a6e1  mov     edx, [rbx+18h]
0x18011a6e4  mov     r8d, [rbx+8]
0x18011a6e8  mov     r9, [rbx+10h]
0x18011a6ec  mov     [rsp+30h+var_10], edx
0x18011a6f0  mov     edx, [rbx+4]
0x18011a6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a6f8  jmp     loc_18011A86D
0x18011a6fd  lea     rcx, [rbp+arg_18]
0x18011a701  mov     [rbp+arg_18], rdi
0x18011a705  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18011a70c  nop     dword ptr [rax+rax+00h]
0x18011a711  test    eax, eax
0x18011a713  js      loc_18011A896
0x18011a719  mov     rcx, [rbp+arg_18]
0x18011a71d  lea     r8, [rbp+arg_10]
0x18011a721  mov     [rbp+arg_10], rdi
0x18011a725  lea     rdx, IID_IERegHelperBroker
0x18011a72c  mov     rax, [rcx]
0x18011a72f  mov     rax, [rax]
0x18011a732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a737  test    eax, eax
0x18011a739  js      short loc_18011A7B5
0x18011a73b  mov     rcx, [rbp+arg_10]
0x18011a73f  mov     r8d, [rbx+8]
0x18011a743  mov     edx, [rbx+4]
0x18011a746  mov     rax, [rcx]
0x18011a749  mov     rax, [rax+20h]
0x18011a74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a752  jmp     short loc_18011A7A5
0x18011a754  lea     rcx, [rbp+arg_18]
0x18011a758  mov     [rbp+arg_18], rdi
0x18011a75c  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18011a763  nop     dword ptr [rax+rax+00h]
0x18011a768  test    eax, eax
0x18011a76a  js      loc_18011A896
0x18011a770  mov     rcx, [rbp+arg_18]
0x18011a774  lea     r8, [rbp+arg_10]
0x18011a778  mov     [rbp+arg_10], rdi
0x18011a77c  lea     rdx, IID_IERegHelperBroker
0x18011a783  mov     rax, [rcx]
0x18011a786  mov     rax, [rax]
0x18011a789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a78e  test    eax, eax
0x18011a790  js      short loc_18011A7B5
0x18011a792  mov     rcx, [rbp+arg_10]
0x18011a796  mov     rax, [rcx]
0x18011a799  mov     rax, [rax+18h]
0x18011a79d  mov     edx, [rbx+4]
0x18011a7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a7a5  mov     rcx, [rbp+arg_10]
0x18011a7a9  mov     rax, [rcx]
0x18011a7ac  mov     rax, [rax+10h]
0x18011a7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a7b5  mov     rcx, [rbp+arg_18]
0x18011a7b9  mov     rax, [rcx]
0x18011a7bc  mov     rax, [rax+10h]
0x18011a7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a7c5  jmp     loc_18011A896
0x18011a7ca  lea     rcx, [rbp+arg_18]
0x18011a7ce  mov     [rbp+arg_18], rdi
0x18011a7d2  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18011a7d9  nop     dword ptr [rax+rax+00h]
0x18011a7de  test    eax, eax
0x18011a7e0  js      loc_18011A88D
0x18011a7e6  mov     rcx, [rbp+arg_18]
0x18011a7ea  lea     r8, [rbp+arg_10]
0x18011a7ee  mov     [rbp+arg_10], rdi
0x18011a7f2  lea     rdx, IID_IERegHelperBroker
0x18011a7f9  mov     rax, [rcx]
0x18011a7fc  mov     rax, [rax]
0x18011a7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a804  test    eax, eax
0x18011a806  js      short loc_18011A87D
0x18011a808  mov     rcx, [rbp+arg_10]
0x18011a80c  mov     rax, [rcx]
0x18011a80f  mov     rax, [rax+30h]
0x18011a813  jmp     loc_18011A6E1
0x18011a818  lea     rcx, [rbp+arg_18]
0x18011a81c  mov     [rbp+arg_18], rdi
0x18011a820  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18011a827  nop     dword ptr [rax+rax+00h]
0x18011a82c  test    eax, eax
0x18011a82e  js      short loc_18011A88D
0x18011a830  mov     rcx, [rbp+arg_18]
0x18011a834  lea     r8, [rbp+arg_10]
0x18011a838  mov     [rbp+arg_10], rdi
0x18011a83c  lea     rdx, IID_IERegHelperBroker
0x18011a843  mov     rax, [rcx]
0x18011a846  mov     rax, [rax]
0x18011a849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a84e  test    eax, eax
0x18011a850  js      short loc_18011A87D
0x18011a852  mov     rcx, [rbp+arg_10]
0x18011a856  mov     r9d, [rbx+18h]
0x18011a85a  mov     r8, [rbx+10h]
0x18011a85e  mov     edx, [rbx+4]
0x18011a861  mov     rax, [rcx]
0x18011a864  mov     rax, [rax+28h]
0x18011a868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a86d  mov     rcx, [rbp+arg_10]
0x18011a871  mov     rax, [rcx]
0x18011a874  mov     rax, [rax+10h]
0x18011a878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a87d  mov     rcx, [rbp+arg_18]
0x18011a881  mov     rax, [rcx]
0x18011a884  mov     rax, [rax+10h]
0x18011a888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a88d  mov     rcx, [rbx+10h]; void *
0x18011a891  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011a896  mov     rcx, rbx; void *
0x18011a899  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011a89e  call    cs:__imp_CoUninitialize
0x18011a8a5  nop     dword ptr [rax+rax+00h]
0x18011a8aa  mov     rbx, [rsp+30h+arg_0]
0x18011a8af  mov     rdi, [rsp+30h+arg_8]
0x18011a8b4  add     rsp, 30h
0x18011a8b8  pop     rbp
0x18011a8b9  retn
```
