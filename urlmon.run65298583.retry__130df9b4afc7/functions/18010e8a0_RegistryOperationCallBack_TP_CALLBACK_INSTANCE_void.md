# RegistryOperationCallBack(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x18010e8a0`
- end: `0x18010eb4a`
- name: `?RegistryOperationCallBack@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `682`
- prototype: `void(struct _TP_CALLBACK_INSTANCE *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180030880`
- `0x18010e8a0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010e904`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010e950`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010e9b3`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010ea04`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010ea74`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010eabc`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010e904`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010e950`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010e9b3`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010ea04`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010ea74`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010eabc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18010eb34`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18010eb34`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18010e8b9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18010e8b9`

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
0x18010e8a0  mov     [rsp-8+arg_0], rbx
0x18010e8a5  mov     [rsp-8+arg_8], rdi
0x18010e8aa  push    rbp
0x18010e8ab  mov     rbp, rsp
0x18010e8ae  sub     rsp, 30h
0x18010e8b2  mov     rbx, rdx
0x18010e8b5  xor     ecx, ecx; pvReserved
0x18010e8b7  xor     edx, edx; dwCoInit
0x18010e8b9  call    cs:__imp_CoInitializeEx
0x18010e8bf  xor     edi, edi
0x18010e8c1  test    eax, eax
0x18010e8c3  js      loc_18010EB3A
0x18010e8c9  mov     ecx, [rbx]
0x18010e8cb  test    ecx, ecx
0x18010e8cd  jz      loc_18010EAB4
0x18010e8d3  sub     ecx, 1
0x18010e8d6  jz      loc_18010EA6C
0x18010e8dc  sub     ecx, 1
0x18010e8df  jz      loc_18010E9FC
0x18010e8e5  sub     ecx, 1
0x18010e8e8  jz      loc_18010E9AB
0x18010e8ee  sub     ecx, 1
0x18010e8f1  jz      short loc_18010E948
0x18010e8f3  cmp     ecx, 1
0x18010e8f6  jnz     loc_18010EB2C
0x18010e8fc  lea     rcx, [rbp+arg_18]
0x18010e900  mov     [rbp+arg_18], rdi
0x18010e904  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18010e90a  test    eax, eax
0x18010e90c  js      loc_18010EB2C
0x18010e912  mov     rcx, [rbp+arg_18]
0x18010e916  lea     r8, [rbp+arg_10]
0x18010e91a  mov     [rbp+arg_10], rdi
0x18010e91e  lea     rdx, IID_IERegHelperBroker
0x18010e925  mov     rax, [rcx]
0x18010e928  mov     rax, [rax]
0x18010e92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e930  test    eax, eax
0x18010e932  js      loc_18010EA57
0x18010e938  mov     rcx, [rbp+arg_10]
0x18010e93c  mov     rax, [rcx]
0x18010e93f  mov     rax, [rax+40h]
0x18010e943  jmp     loc_18010EA3F
0x18010e948  lea     rcx, [rbp+arg_18]
0x18010e94c  mov     [rbp+arg_18], rdi
0x18010e950  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18010e956  test    eax, eax
0x18010e958  js      loc_18010EB23
0x18010e95e  mov     rcx, [rbp+arg_18]
0x18010e962  lea     r8, [rbp+arg_10]
0x18010e966  mov     [rbp+arg_10], rdi
0x18010e96a  lea     rdx, IID_IERegHelperBroker
0x18010e971  mov     rax, [rcx]
0x18010e974  mov     rax, [rax]
0x18010e977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e97c  test    eax, eax
0x18010e97e  js      loc_18010EB13
0x18010e984  mov     rcx, [rbp+arg_10]
0x18010e988  mov     rax, [rcx]
0x18010e98b  mov     rax, [rax+38h]
0x18010e98f  mov     edx, [rbx+18h]
0x18010e992  mov     r8d, [rbx+8]
0x18010e996  mov     r9, [rbx+10h]
0x18010e99a  mov     [rsp+30h+var_10], edx
0x18010e99e  mov     edx, [rbx+4]
0x18010e9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e9a6  jmp     loc_18010EB03
0x18010e9ab  lea     rcx, [rbp+arg_18]
0x18010e9af  mov     [rbp+arg_18], rdi
0x18010e9b3  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18010e9b9  test    eax, eax
0x18010e9bb  js      loc_18010EB2C
0x18010e9c1  mov     rcx, [rbp+arg_18]
0x18010e9c5  lea     r8, [rbp+arg_10]
0x18010e9c9  mov     [rbp+arg_10], rdi
0x18010e9cd  lea     rdx, IID_IERegHelperBroker
0x18010e9d4  mov     rax, [rcx]
0x18010e9d7  mov     rax, [rax]
0x18010e9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e9df  test    eax, eax
0x18010e9e1  js      short loc_18010EA57
0x18010e9e3  mov     rcx, [rbp+arg_10]
0x18010e9e7  mov     r8d, [rbx+8]
0x18010e9eb  mov     edx, [rbx+4]
0x18010e9ee  mov     rax, [rcx]
0x18010e9f1  mov     rax, [rax+20h]
0x18010e9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e9fa  jmp     short loc_18010EA47
0x18010e9fc  lea     rcx, [rbp+arg_18]
0x18010ea00  mov     [rbp+arg_18], rdi
0x18010ea04  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18010ea0a  test    eax, eax
0x18010ea0c  js      loc_18010EB2C
0x18010ea12  mov     rcx, [rbp+arg_18]
0x18010ea16  lea     r8, [rbp+arg_10]
0x18010ea1a  mov     [rbp+arg_10], rdi
0x18010ea1e  lea     rdx, IID_IERegHelperBroker
0x18010ea25  mov     rax, [rcx]
0x18010ea28  mov     rax, [rax]
0x18010ea2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ea30  test    eax, eax
0x18010ea32  js      short loc_18010EA57
0x18010ea34  mov     rcx, [rbp+arg_10]
0x18010ea38  mov     rax, [rcx]
0x18010ea3b  mov     rax, [rax+18h]
0x18010ea3f  mov     edx, [rbx+4]
0x18010ea42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ea47  mov     rcx, [rbp+arg_10]
0x18010ea4b  mov     rax, [rcx]
0x18010ea4e  mov     rax, [rax+10h]
0x18010ea52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ea57  mov     rcx, [rbp+arg_18]
0x18010ea5b  mov     rax, [rcx]
0x18010ea5e  mov     rax, [rax+10h]
0x18010ea62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ea67  jmp     loc_18010EB2C
0x18010ea6c  lea     rcx, [rbp+arg_18]
0x18010ea70  mov     [rbp+arg_18], rdi
0x18010ea74  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18010ea7a  test    eax, eax
0x18010ea7c  js      loc_18010EB23
0x18010ea82  mov     rcx, [rbp+arg_18]
0x18010ea86  lea     r8, [rbp+arg_10]
0x18010ea8a  mov     [rbp+arg_10], rdi
0x18010ea8e  lea     rdx, IID_IERegHelperBroker
0x18010ea95  mov     rax, [rcx]
0x18010ea98  mov     rax, [rax]
0x18010ea9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010eaa0  test    eax, eax
0x18010eaa2  js      short loc_18010EB13
0x18010eaa4  mov     rcx, [rbp+arg_10]
0x18010eaa8  mov     rax, [rcx]
0x18010eaab  mov     rax, [rax+30h]
0x18010eaaf  jmp     loc_18010E98F
0x18010eab4  lea     rcx, [rbp+arg_18]
0x18010eab8  mov     [rbp+arg_18], rdi
0x18010eabc  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18010eac2  test    eax, eax
0x18010eac4  js      short loc_18010EB23
0x18010eac6  mov     rcx, [rbp+arg_18]
0x18010eaca  lea     r8, [rbp+arg_10]
0x18010eace  mov     [rbp+arg_10], rdi
0x18010ead2  lea     rdx, IID_IERegHelperBroker
0x18010ead9  mov     rax, [rcx]
0x18010eadc  mov     rax, [rax]
0x18010eadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010eae4  test    eax, eax
0x18010eae6  js      short loc_18010EB13
0x18010eae8  mov     rcx, [rbp+arg_10]
0x18010eaec  mov     r9d, [rbx+18h]
0x18010eaf0  mov     r8, [rbx+10h]
0x18010eaf4  mov     edx, [rbx+4]
0x18010eaf7  mov     rax, [rcx]
0x18010eafa  mov     rax, [rax+28h]
0x18010eafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010eb03  mov     rcx, [rbp+arg_10]
0x18010eb07  mov     rax, [rcx]
0x18010eb0a  mov     rax, [rax+10h]
0x18010eb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010eb13  mov     rcx, [rbp+arg_18]
0x18010eb17  mov     rax, [rcx]
0x18010eb1a  mov     rax, [rax+10h]
0x18010eb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010eb23  mov     rcx, [rbx+10h]; void *
0x18010eb27  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18010eb2c  mov     rcx, rbx; void *
0x18010eb2f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18010eb34  call    cs:__imp_CoUninitialize
0x18010eb3a  mov     rbx, [rsp+30h+arg_0]
0x18010eb3f  mov     rdi, [rsp+30h+arg_8]
0x18010eb44  add     rsp, 30h
0x18010eb48  pop     rbp
0x18010eb49  retn
```
