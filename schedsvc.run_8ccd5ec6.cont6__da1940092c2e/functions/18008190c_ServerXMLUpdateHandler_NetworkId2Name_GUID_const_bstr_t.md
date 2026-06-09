# ServerXMLUpdateHandler::NetworkId2Name(_GUID const &,_bstr_t &)

- ea: `0x18008190c`
- end: `0x180081b91`
- name: `?NetworkId2Name@ServerXMLUpdateHandler@@AEAAJAEBU_GUID@@AEAV_bstr_t@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(ServerXMLUpdateHandler *__hidden this, const struct _GUID *, struct _bstr_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180043d50`
- `0x18004cfa0`

## callees

- `0x180030620`
- `0x180056954`
- `0x18007cc60`
- `0x18008190c`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081ad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081ad1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008198b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008198b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ServerXMLUpdateHandler::NetworkId2Name(
        ServerXMLUpdateHandler *this,
        const struct _GUID *a2,
        struct _bstr_t *a3)
{
  unsigned __int64 v5; // rcx
  HRESULT v7; // eax
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  LPVOID pv[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+38h] BYREF

  pv[0] = 0;
  ppv = 0;
  v12 = 0;
  v5 = *(_QWORD *)&a2->Data1;
  if ( !*(_QWORD *)&a2->Data1 )
    v5 = *(_QWORD *)a2->Data4 - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( !v5 )
    return 2147750680LL;
  v7 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &IID_INetworkListManagerPrivate, &ppv);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64 *))(*(_QWORD *)ppv + 48LL))(ppv, a2, &v12);
    v9 = v12;
    if ( v8 >= 0 && v12 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 24LL))(v12, pv);
      v8 = v10;
      if ( v10 >= 0 )
      {
        _bstr_t::operator=(a3, pv[0]);
        CoTaskMemFree(pv[0]);
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        v12 = 0;
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids,
            (unsigned int)v10);
        }
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        v12 = 0;
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF__guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids, a2, v8);
        v9 = v12;
      }
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v12 = 0;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids,
        (unsigned int)v7);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008190c  mov     [rsp-18h+arg_8], rbx
0x180081911  mov     [rsp-18h+arg_0], rcx
0x180081916  push    rbp
0x180081917  push    rsi
0x180081918  push    rdi
0x180081919  mov     rbp, rsp
0x18008191c  sub     rsp, 40h
0x180081920  mov     rsi, r8
0x180081923  mov     rdi, rdx
0x180081926  xorps   xmm0, xmm0
0x180081929  mov     [rbp+pv], 0
0x180081931  mov     [rbp+arg_18], 0
0x180081939  mov     [rbp+arg_0], 0
0x180081941  mov     rcx, [rdx]
0x180081944  movq    rax, xmm0
0x180081949  sub     rcx, rax
0x18008194c  jnz     short loc_18008195F
0x18008194e  mov     rcx, [rdx+8]
0x180081952  psrldq  xmm0, 8
0x180081957  movq    rax, xmm0
0x18008195c  sub     rcx, rax
0x18008195f  test    rcx, rcx
0x180081962  jnz     short loc_18008196E
0x180081964  mov     eax, 80041318h
0x180081969  jmp     loc_180081B83
0x18008196e  lea     rax, [rbp+arg_18]
0x180081972  mov     [rsp+40h+ppv], rax; ppv
0x180081977  lea     r9, IID_INetworkListManagerPrivate; riid
0x18008197e  xor     edx, edx; pUnkOuter
0x180081980  lea     r8d, [rdx+4]; dwClsContext
0x180081984  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18008198b  call    cs:__imp_CoCreateInstance
0x180081992  nop     dword ptr [rax+rax+00h]
0x180081997  mov     ebx, eax
0x180081999  test    eax, eax
0x18008199b  jns     short loc_180081A0D
0x18008199d  lea     rdx, WPP_GLOBAL_Control
0x1800819a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800819ab  cmp     rcx, rdx
0x1800819ae  jz      short loc_1800819D5
0x1800819b0  test    byte ptr [rcx+1Ch], 80h
0x1800819b4  jz      short loc_1800819D5
0x1800819b6  cmp     byte ptr [rcx+19h], 2
0x1800819ba  jb      short loc_1800819D5
0x1800819bc  mov     edx, 0Dh
0x1800819c1  mov     r9d, eax
0x1800819c4  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x1800819cb  mov     rcx, [rcx+10h]
0x1800819cf  call    WPP_SF_d
0x1800819d4  nop
0x1800819d5  mov     rcx, [rbp+arg_0]
0x1800819d9  test    rcx, rcx
0x1800819dc  jz      short loc_1800819EA
0x1800819de  mov     rax, [rcx]
0x1800819e1  mov     rax, [rax+10h]
0x1800819e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800819ea  mov     [rbp+arg_0], 0
0x1800819f2  mov     rcx, [rbp+arg_18]
0x1800819f6  test    rcx, rcx
0x1800819f9  jz      short loc_180081A08
0x1800819fb  mov     rax, [rcx]
0x1800819fe  mov     rax, [rax+10h]
0x180081a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a07  nop
0x180081a08  jmp     loc_180081B81
0x180081a0d  mov     rcx, [rbp+arg_18]
0x180081a11  mov     rax, [rcx]
0x180081a14  lea     r8, [rbp+arg_0]
0x180081a18  mov     rdx, rdi
0x180081a1b  mov     rax, [rax+30h]
0x180081a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a24  mov     ebx, eax
0x180081a26  mov     rcx, [rbp+arg_0]
0x180081a2a  test    eax, eax
0x180081a2c  js      loc_180081B13
0x180081a32  test    rcx, rcx
0x180081a35  jz      loc_180081B13
0x180081a3b  mov     rax, [rcx]
0x180081a3e  lea     rdx, [rbp+pv]
0x180081a42  mov     rax, [rax+18h]
0x180081a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a4b  mov     ebx, eax
0x180081a4d  test    eax, eax
0x180081a4f  jns     short loc_180081AC1
0x180081a51  lea     rdx, WPP_GLOBAL_Control
0x180081a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180081a5f  cmp     rcx, rdx
0x180081a62  jz      short loc_180081A89
0x180081a64  test    byte ptr [rcx+1Ch], 80h
0x180081a68  jz      short loc_180081A89
0x180081a6a  cmp     byte ptr [rcx+19h], 2
0x180081a6e  jb      short loc_180081A89
0x180081a70  mov     edx, 0Fh
0x180081a75  mov     r9d, eax
0x180081a78  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x180081a7f  mov     rcx, [rcx+10h]
0x180081a83  call    WPP_SF_d
0x180081a88  nop
0x180081a89  mov     rcx, [rbp+arg_0]
0x180081a8d  test    rcx, rcx
0x180081a90  jz      short loc_180081A9E
0x180081a92  mov     rax, [rcx]
0x180081a95  mov     rax, [rax+10h]
0x180081a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a9e  mov     [rbp+arg_0], 0
0x180081aa6  mov     rcx, [rbp+arg_18]
0x180081aaa  test    rcx, rcx
0x180081aad  jz      short loc_180081ABC
0x180081aaf  mov     rax, [rcx]
0x180081ab2  mov     rax, [rax+10h]
0x180081ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081abb  nop
0x180081abc  jmp     loc_180081B81
0x180081ac1  mov     rdx, [rbp+pv]
0x180081ac5  mov     rcx, rsi
0x180081ac8  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180081acd  mov     rcx, [rbp+pv]; pv
0x180081ad1  call    cs:__imp_CoTaskMemFree
0x180081ad8  nop     dword ptr [rax+rax+00h]
0x180081add  nop
0x180081ade  mov     rcx, [rbp+arg_0]
0x180081ae2  test    rcx, rcx
0x180081ae5  jz      short loc_180081AF3
0x180081ae7  mov     rax, [rcx]
0x180081aea  mov     rax, [rax+10h]
0x180081aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081af3  mov     [rbp+arg_0], 0
0x180081afb  mov     rcx, [rbp+arg_18]
0x180081aff  test    rcx, rcx
0x180081b02  jz      short loc_180081B11
0x180081b04  mov     rax, [rcx]
0x180081b07  mov     rax, [rax+10h]
0x180081b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081b10  nop
0x180081b11  jmp     short loc_180081B81
0x180081b13  lea     rdx, WPP_GLOBAL_Control
0x180081b1a  mov     rax, cs:WPP_GLOBAL_Control
0x180081b21  cmp     rax, rdx
0x180081b24  jz      short loc_180081B52
0x180081b26  test    byte ptr [rax+1Ch], 80h
0x180081b2a  jz      short loc_180081B52
0x180081b2c  cmp     byte ptr [rax+19h], 2
0x180081b30  jb      short loc_180081B52
0x180081b32  mov     edx, 0Eh
0x180081b37  mov     dword ptr [rsp+40h+ppv], ebx
0x180081b3b  mov     r9, rdi
0x180081b3e  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x180081b45  mov     rcx, [rax+10h]
0x180081b49  call    WPP_SF__guid_D
0x180081b4e  mov     rcx, [rbp+arg_0]
0x180081b52  test    rcx, rcx
0x180081b55  jz      short loc_180081B63
0x180081b57  mov     rax, [rcx]
0x180081b5a  mov     rax, [rax+10h]
0x180081b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081b63  mov     [rbp+arg_0], 0
0x180081b6b  mov     rcx, [rbp+arg_18]
0x180081b6f  test    rcx, rcx
0x180081b72  jz      short loc_180081B81
0x180081b74  mov     rax, [rcx]
0x180081b77  mov     rax, [rax+10h]
0x180081b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081b80  nop
0x180081b81  mov     eax, ebx
0x180081b83  mov     rbx, [rsp+40h+arg_8]
0x180081b88  add     rsp, 40h
0x180081b8c  pop     rdi
0x180081b8d  pop     rsi
0x180081b8e  pop     rbp
0x180081b8f  retn
```
