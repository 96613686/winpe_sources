# SHGetConnectedIdentityProviderForCurrentUser(_GUID *)

- ea: `0x180069000`
- end: `0x1800691fa`
- name: `?SHGetConnectedIdentityProviderForCurrentUser@@YAJPEAU_GUID@@@Z`
- size: `506`
- prototype: `__int64 __fastcall(GUID *pguid)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010ba0`
- `0x180059ba8`

## callees

- `0x180069000`
- `0x180069488`
- `0x1800694d8`
- `0x180078010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18006909e`
- `msvcrt!memcpy_s` at `0x18006909e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006919c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800691c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006919c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800691c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006907c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006907c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006905a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006905a`
- `PROPSYS!PropVariantToGUID` at `0x180069190`
- `PROPSYS!PropVariantToGUID` at `0x180069190`

## pseudocode

```c
__int64 __fastcall SHGetConnectedIdentityProviderForCurrentUser(GUID *pguid)
{
  HRESULT v2; // ebx
  void *v3; // rax
  int v4; // eax
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v8; // [rsp+48h] [rbp-28h]
  PROPVARIANT propvar[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v10; // [rsp+60h] [rbp-10h]
  int v11; // [rsp+90h] [rbp+20h] BYREF
  __int64 v12; // [rsp+98h] [rbp+28h] BYREF
  __int64 v13; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v14; // [rsp+A8h] [rbp+38h] BYREF

  *pguid = GUID_NULL;
  if ( (unsigned __int8)ConnectedIdentityDisabledByRegistry() || (unsigned int)SHIsConnectedIdentityProviderAvailable() )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    ppv = 0;
    v2 = CoCreateInstance(
           &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
           0,
           1u,
           &GUID_df586fa5_6f35_44f1_b209_b38e169772eb,
           &ppv);
    if ( v2 >= 0 )
    {
      *(_OWORD *)pvar = 0;
      v8 = 0;
      v3 = CoTaskMemAlloc(0x14u);
      pvar[1] = v3;
      if ( v3 )
      {
        memcpy_s(v3, 0x14u, L"Connected", 0x14u);
        v14 = 0;
        LOWORD(pvar[0]) = 31;
        v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, const PROPERTYKEY *, PROPVARIANT *, __int64 *))(*(_QWORD *)ppv + 56LL))(
               ppv,
               1,
               &PKEY_Keywords,
               pvar,
               &v14);
        if ( v2 >= 0 )
        {
          v13 = 0;
          v12 = 0;
          v11 = 0;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v14 + 24LL))(
                 v14,
                 1,
                 &v12,
                 &v11);
          v2 = v4;
          if ( v4 >= 0 )
          {
            if ( v4 )
            {
              v2 = -2147467259;
            }
            else
            {
              v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
                     v12,
                     &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                     &v13);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            }
            if ( v2 >= 0 )
            {
              v10 = 0;
              *(_OWORD *)propvar = 0;
              v2 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v13 + 40LL))(
                     v13,
                     &PKEY_Identity_ProviderID,
                     propvar);
              if ( v2 >= 0 )
              {
                v2 = PropVariantToGUID(propvar, pguid);
                PropVariantClear(propvar);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        PropVariantClear(pvar);
      }
      else
      {
        *(_OWORD *)pvar = 0;
        v8 = 0;
        v2 = -2147024882;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180069000  push    rbp
0x180069002  push    rbx
0x180069003  push    rdi
0x180069004  mov     rbp, rsp
0x180069007  sub     rsp, 70h
0x18006900b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180069012  mov     rdi, rcx
0x180069015  movdqu  xmmword ptr [rcx], xmm0
0x180069019  call    _ConnectedIdentityDisabledByRegistry
0x18006901e  test    al, al
0x180069020  jnz     short loc_18006902B
0x180069022  call    ?SHIsConnectedIdentityProviderAvailable@@YAJXZ; SHIsConnectedIdentityProviderAvailable(void)
0x180069027  test    eax, eax
0x180069029  jz      short loc_180069035
0x18006902b  mov     ebx, 80004005h
0x180069030  jmp     loc_1800691F0
0x180069035  xor     edx, edx; pUnkOuter
0x180069037  mov     [rbp+var_40], 0
0x18006903f  lea     rax, [rbp+var_40]
0x180069043  lea     r9, _GUID_df586fa5_6f35_44f1_b209_b38e169772eb; riid
0x18006904a  mov     [rsp+70h+ppv], rax; ppv
0x18006904f  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x180069056  lea     r8d, [rdx+1]; dwClsContext
0x18006905a  call    cs:__imp_CoCreateInstance
0x180069060  mov     ebx, eax
0x180069062  test    eax, eax
0x180069064  js      loc_1800691F0
0x18006906a  xor     eax, eax
0x18006906c  xorps   xmm0, xmm0
0x18006906f  movups  xmmword ptr [rbp+pvar], xmm0
0x180069073  mov     [rbp+var_28], rax
0x180069077  lea     ebx, [rax+14h]
0x18006907a  mov     ecx, ebx; cb
0x18006907c  call    cs:__imp_CoTaskMemAlloc
0x180069082  mov     [rbp+pvar+8], rax
0x180069086  test    rax, rax
0x180069089  jz      loc_1800691CE
0x18006908f  mov     r9d, ebx; SourceSize
0x180069092  lea     r8, aConnected; "Connected"
0x180069099  mov     edx, ebx; DestinationSize
0x18006909b  mov     rcx, rax; Destination
0x18006909e  call    cs:__imp_memcpy_s
0x1800690a4  mov     rcx, [rbp+var_40]
0x1800690a8  lea     rdx, [rbp+arg_18]
0x1800690ac  lea     eax, [rbx+0Bh]
0x1800690af  mov     [rbp+arg_18], 0
0x1800690b7  mov     word ptr [rbp+pvar], ax
0x1800690bb  lea     r9, [rbp+pvar]
0x1800690bf  mov     [rsp+70h+ppv], rdx
0x1800690c4  lea     r8, PKEY_Keywords
0x1800690cb  mov     rax, [rcx]
0x1800690ce  lea     edx, [rbx-13h]
0x1800690d1  mov     rax, [rax+38h]
0x1800690d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690da  mov     ebx, eax
0x1800690dc  test    eax, eax
0x1800690de  js      loc_1800691C2
0x1800690e4  mov     rcx, [rbp+arg_18]
0x1800690e8  lea     r9, [rbp+arg_0]
0x1800690ec  mov     [rbp+arg_10], 0
0x1800690f4  lea     r8, [rbp+arg_8]
0x1800690f8  mov     edx, 1
0x1800690fd  mov     [rbp+arg_8], 0
0x180069105  mov     [rbp+arg_0], 0
0x18006910c  mov     rax, [rcx]
0x18006910f  mov     rax, [rax+18h]
0x180069113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069118  mov     ebx, eax
0x18006911a  test    eax, eax
0x18006911c  js      loc_1800691B2
0x180069122  jnz     short loc_180069152
0x180069124  mov     rcx, [rbp+arg_8]
0x180069128  lea     r8, [rbp+arg_10]
0x18006912c  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180069133  mov     rax, [rcx]
0x180069136  mov     rax, [rax]
0x180069139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006913e  mov     rcx, [rbp+arg_8]
0x180069142  mov     ebx, eax
0x180069144  mov     rax, [rcx]
0x180069147  mov     rax, [rax+10h]
0x18006914b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069150  jmp     short loc_180069157
0x180069152  mov     ebx, 80004005h
0x180069157  test    ebx, ebx
0x180069159  js      short loc_1800691B2
0x18006915b  mov     rcx, [rbp+arg_10]
0x18006915f  lea     r8, [rbp+propvar]
0x180069163  xor     eax, eax
0x180069165  lea     rdx, PKEY_Identity_ProviderID
0x18006916c  mov     [rbp+var_10], rax
0x180069170  xorps   xmm0, xmm0
0x180069173  movups  xmmword ptr [rbp+propvar], xmm0
0x180069177  mov     rax, [rcx]
0x18006917a  mov     rax, [rax+28h]
0x18006917e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069183  mov     ebx, eax
0x180069185  test    eax, eax
0x180069187  js      short loc_1800691A2
0x180069189  mov     rdx, rdi; pguid
0x18006918c  lea     rcx, [rbp+propvar]; propvar
0x180069190  call    cs:__imp_PropVariantToGUID
0x180069196  lea     rcx, [rbp+propvar]; pvar
0x18006919a  mov     ebx, eax
0x18006919c  call    cs:__imp_PropVariantClear
0x1800691a2  mov     rcx, [rbp+arg_10]
0x1800691a6  mov     rax, [rcx]
0x1800691a9  mov     rax, [rax+10h]
0x1800691ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691b2  mov     rcx, [rbp+arg_18]
0x1800691b6  mov     rax, [rcx]
0x1800691b9  mov     rax, [rax+10h]
0x1800691bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691c2  lea     rcx, [rbp+pvar]; pvar
0x1800691c6  call    cs:__imp_PropVariantClear
0x1800691cc  jmp     short loc_1800691E0
0x1800691ce  xorps   xmm0, xmm0
0x1800691d1  xor     eax, eax
0x1800691d3  movups  xmmword ptr [rbp+pvar], xmm0
0x1800691d7  mov     [rbp+var_28], rax
0x1800691db  mov     ebx, 8007000Eh
0x1800691e0  mov     rcx, [rbp+var_40]
0x1800691e4  mov     rax, [rcx]
0x1800691e7  mov     rax, [rax+10h]
0x1800691eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691f0  mov     eax, ebx
0x1800691f2  add     rsp, 70h
0x1800691f6  pop     rdi
0x1800691f7  pop     rbx
0x1800691f8  pop     rbp
0x1800691f9  retn
```
