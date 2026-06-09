# EdpHelpers::ProtectFilesWithFileOperation(HWND__ *,IShellItemArray *,ushort const *,ulong)

- ea: `0x18003d154`
- end: `0x18003d372`
- name: `?ProtectFilesWithFileOperation@EdpHelpers@@YAJPEAUHWND__@@PEAUIShellItemArray@@PEBGK@Z`
- size: `542`
- prototype: `__int64 __fastcall(HWND this, HWND, struct IShellItemArray *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003cfac`

## callees

- `0x18001367c`
- `0x180031e94`
- `0x180036f50`
- `0x18003af14`
- `0x18003d154`
- `0x18003e1e0`
- `0x180071010`

## import_xrefs

- `PROPSYS!PSCreateSimplePropertyChange` at `0x18003d23b`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18003d23b`
- `PROPSYS!PSCreatePropertyChangeArray` at `0x18003d1e8`
- `PROPSYS!PSCreatePropertyChangeArray` at `0x18003d1e8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d18a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d353`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d18a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d353`

## pseudocode

```c
__int64 __fastcall EdpHelpers::ProtectFilesWithFileOperation(
        HWND this,
        HWND a2,
        struct IShellItemArray *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r9
  HRESULT v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  HRESULT v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  unsigned int v18; // edx
  const struct _GUID *v19; // r8
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  int riid; // [rsp+20h] [rbp-50h]
  int riida; // [rsp+20h] [rbp-50h]
  void *v28; // [rsp+30h] [rbp-40h] BYREF
  void *v29; // [rsp+38h] [rbp-38h] BYREF
  void *ppv; // [rsp+40h] [rbp-30h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  LOWORD(pvar) = 0;
  if ( a3 )
  {
    PropVariantClear(&pvar);
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)&a3->lpVtbl + v9) );
    if ( (int)_AllocStringWorker<CTCoAllocPolicy>(v8, v7, a3) >= 0 )
      LOWORD(pvar) = 31;
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, a2);
  v10 = PSCreatePropertyChangeArray(0, 0, 0, 0, &GUID_380f5cad_1b5e_42f2_805d_637fd392d31e, &ppv);
  v12 = v10;
  if ( v10 >= 0 )
  {
    v29 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29, v11);
    v14 = PSCreateSimplePropertyChange(
            PKA_SET,
            &PKEY_Security_EncryptionOwners,
            &pvar,
            &GUID_f917bc8a_1bba_4478_a245_1bde03eb9431,
            &v29);
    v12 = v14;
    if ( v14 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(void *, void *))(*(_QWORD *)ppv + 48LL))(ppv, v29);
      v12 = v14;
      if ( v14 >= 0 )
      {
        v28 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28, v17);
        v20 = SHCreateFileOperation(this, v18, v19, &v28);
        v12 = v20;
        if ( v20 >= 0 )
        {
          v20 = (*(__int64 (__fastcall **)(void *, void *))(*(_QWORD *)v28 + 64LL))(v28, ppv);
          v12 = v20;
          if ( v20 >= 0 )
          {
            v20 = (*(__int64 (__fastcall **)(void *, HWND))(*(_QWORD *)v28 + 88LL))(v28, a2);
            v12 = v20;
            if ( v20 >= 0 )
            {
              v20 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v28 + 168LL))(v28);
              v12 = v20;
              if ( v20 >= 0 )
              {
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28, v23);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29, v24);
                v12 = 0;
                goto LABEL_24;
              }
              v21 = 579;
            }
            else
            {
              v21 = 578;
            }
          }
          else
          {
            v21 = 577;
          }
        }
        else
        {
          v21 = 576;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\EdpHelpers.h",
          (const char *)(unsigned int)v20,
          riida);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28, v22);
        goto LABEL_11;
      }
      v15 = 573;
    }
    else
    {
      v15 = 572;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\EdpHelpers.h",
      (const char *)(unsigned int)v14,
      riida);
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29, v16);
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23A,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\EdpHelpers.h",
    (const char *)(unsigned int)v10,
    riid);
LABEL_24:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v13);
  PropVariantClear(&pvar);
  return v12;
}

```

## disassembly

```asm
0x18003d154  push    rbp
0x18003d156  push    rbx
0x18003d157  push    rsi
0x18003d158  push    rdi
0x18003d159  push    r14
0x18003d15b  mov     rbp, rsp
0x18003d15e  sub     rsp, 70h
0x18003d162  mov     rax, cs:__security_cookie
0x18003d169  xor     rax, rsp
0x18003d16c  mov     [rbp+var_10], rax
0x18003d170  xor     r14d, r14d
0x18003d173  mov     rbx, r8
0x18003d176  mov     word ptr [rbp+pvar], r14w
0x18003d17b  mov     rsi, rdx
0x18003d17e  mov     rdi, rcx
0x18003d181  test    r8, r8
0x18003d184  jz      short loc_18003D1BC
0x18003d186  lea     rcx, [rbp+pvar]; pvar
0x18003d18a  call    cs:__imp_PropVariantClear
0x18003d190  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003d194  inc     r9
0x18003d197  cmp     [rbx+r9*2], r14w
0x18003d19c  jnz     short loc_18003D194
0x18003d19e  lea     rax, [rbp+var_20]
0x18003d1a2  mov     r8, rbx
0x18003d1a5  mov     [rsp+70h+ppv], rax
0x18003d1aa  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18003d1af  test    eax, eax
0x18003d1b1  js      short loc_18003D1BC
0x18003d1b3  mov     eax, 1Fh
0x18003d1b8  mov     word ptr [rbp+pvar], ax
0x18003d1bc  lea     rcx, [rbp+var_30]
0x18003d1c0  mov     [rbp+var_30], r14
0x18003d1c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d1c9  lea     rax, [rbp+var_30]
0x18003d1cd  xor     r9d, r9d; cChanges
0x18003d1d0  mov     [rsp+70h+ppv], rax; ppv
0x18003d1d5  xor     r8d, r8d; rgpropvar
0x18003d1d8  lea     rax, _GUID_380f5cad_1b5e_42f2_805d_637fd392d31e
0x18003d1df  xor     edx, edx; rgflags
0x18003d1e1  xor     ecx, ecx; rgpropkey
0x18003d1e3  mov     [rsp+70h+riid], rax; int
0x18003d1e8  call    cs:__imp_PSCreatePropertyChangeArray
0x18003d1ee  mov     ebx, eax
0x18003d1f0  test    eax, eax
0x18003d1f2  jns     short loc_18003D211
0x18003d1f4  mov     rcx, [rbp+28h]; this
0x18003d1f8  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18003d1ff  mov     r9d, eax; char *
0x18003d202  mov     edx, 23Ah; void *
0x18003d207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d20c  jmp     loc_18003D346
0x18003d211  lea     rcx, [rbp+var_38]
0x18003d215  mov     [rbp+var_38], r14
0x18003d219  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d21e  lea     rax, [rbp+var_38]
0x18003d222  xor     ecx, ecx; flags
0x18003d224  lea     r9, _GUID_f917bc8a_1bba_4478_a245_1bde03eb9431; riid
0x18003d22b  mov     [rsp+70h+riid], rax; int
0x18003d230  lea     r8, [rbp+pvar]; propvar
0x18003d234  lea     rdx, PKEY_Security_EncryptionOwners; key
0x18003d23b  call    cs:__imp_PSCreateSimplePropertyChange
0x18003d241  mov     ebx, eax
0x18003d243  test    eax, eax
0x18003d245  jns     short loc_18003D26D
0x18003d247  mov     edx, 23Ch; void *
0x18003d24c  mov     rcx, [rbp+28h]; this
0x18003d250  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18003d257  mov     r9d, eax; char *
0x18003d25a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d25f  lea     rcx, [rbp+var_38]
0x18003d263  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d268  jmp     loc_18003D346
0x18003d26d  mov     rcx, [rbp+var_30]
0x18003d271  mov     rdx, [rbp+var_38]
0x18003d275  mov     rax, [rcx]
0x18003d278  mov     rax, [rax+30h]
0x18003d27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d281  mov     ebx, eax
0x18003d283  test    eax, eax
0x18003d285  jns     short loc_18003D28E
0x18003d287  mov     edx, 23Dh
0x18003d28c  jmp     short loc_18003D24C
0x18003d28e  lea     rcx, [rbp+var_40]
0x18003d292  mov     [rbp+var_40], r14
0x18003d296  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d29b  lea     r9, [rbp+var_40]; void **
0x18003d29f  mov     rcx, rdi; HWND
0x18003d2a2  call    ?SHCreateFileOperation@@YAJPEAUHWND__@@KAEBU_GUID@@PEAPEAX@Z; SHCreateFileOperation(HWND__ *,ulong,_GUID const &,void * *)
0x18003d2a7  mov     ebx, eax
0x18003d2a9  test    eax, eax
0x18003d2ab  jns     short loc_18003D2D0
0x18003d2ad  mov     edx, 240h; void *
0x18003d2b2  mov     rcx, [rbp+28h]; this
0x18003d2b6  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18003d2bd  mov     r9d, eax; char *
0x18003d2c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d2c5  lea     rcx, [rbp+var_40]
0x18003d2c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d2ce  jmp     short loc_18003D25F
0x18003d2d0  mov     rcx, [rbp+var_40]
0x18003d2d4  mov     rdx, [rbp+var_30]
0x18003d2d8  mov     rax, [rcx]
0x18003d2db  mov     rax, [rax+40h]
0x18003d2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2e4  mov     ebx, eax
0x18003d2e6  test    eax, eax
0x18003d2e8  jns     short loc_18003D2F1
0x18003d2ea  mov     edx, 241h
0x18003d2ef  jmp     short loc_18003D2B2
0x18003d2f1  mov     rcx, [rbp+var_40]
0x18003d2f5  mov     rdx, rsi
0x18003d2f8  mov     rax, [rcx]
0x18003d2fb  mov     rax, [rax+58h]
0x18003d2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d304  mov     ebx, eax
0x18003d306  test    eax, eax
0x18003d308  jns     short loc_18003D311
0x18003d30a  mov     edx, 242h
0x18003d30f  jmp     short loc_18003D2B2
0x18003d311  mov     rcx, [rbp+var_40]
0x18003d315  mov     rax, [rcx]
0x18003d318  mov     rax, [rax+0A8h]
0x18003d31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d324  mov     ebx, eax
0x18003d326  test    eax, eax
0x18003d328  jns     short loc_18003D331
0x18003d32a  mov     edx, 243h
0x18003d32f  jmp     short loc_18003D2B2
0x18003d331  lea     rcx, [rbp+var_40]
0x18003d335  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d33a  lea     rcx, [rbp+var_38]
0x18003d33e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d343  mov     ebx, r14d
0x18003d346  lea     rcx, [rbp+var_30]
0x18003d34a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d34f  lea     rcx, [rbp+pvar]; pvar
0x18003d353  call    cs:__imp_PropVariantClear
0x18003d359  mov     eax, ebx
0x18003d35b  mov     rcx, [rbp+var_10]
0x18003d35f  xor     rcx, rsp; StackCookie
0x18003d362  call    __security_check_cookie
0x18003d367  add     rsp, 70h
0x18003d36b  pop     r14
0x18003d36d  pop     rdi
0x18003d36e  pop     rsi
0x18003d36f  pop     rbx
0x18003d370  pop     rbp
0x18003d371  retn
```
