# ServerXMLUpdateHandler::NetworkId2Name(_GUID const &,_bstr_t &)

- ea: `0x18007d5dc`
- end: `0x18007d854`
- name: `?NetworkId2Name@ServerXMLUpdateHandler@@AEAAJAEBU_GUID@@AEAV_bstr_t@@@Z`
- size: `632`
- prototype: `__int64 __fastcall(ServerXMLUpdateHandler *__hidden this, const struct _GUID *, struct _bstr_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180041760`
- `0x18004ab10`

## callees

- `0x1800339c0`
- `0x180054084`
- `0x180078b04`
- `0x18007d5dc`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d79b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d79b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007d65b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007d65b`

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
0x18007d5dc  mov     [rsp-18h+arg_8], rbx
0x18007d5e1  mov     [rsp-18h+arg_0], rcx
0x18007d5e6  push    rbp
0x18007d5e7  push    rsi
0x18007d5e8  push    rdi
0x18007d5e9  mov     rbp, rsp
0x18007d5ec  sub     rsp, 40h
0x18007d5f0  mov     rsi, r8
0x18007d5f3  mov     rdi, rdx
0x18007d5f6  xorps   xmm0, xmm0
0x18007d5f9  mov     [rbp+pv], 0
0x18007d601  mov     [rbp+arg_18], 0
0x18007d609  mov     [rbp+arg_0], 0
0x18007d611  mov     rcx, [rdx]
0x18007d614  movq    rax, xmm0
0x18007d619  sub     rcx, rax
0x18007d61c  jnz     short loc_18007D62F
0x18007d61e  mov     rcx, [rdx+8]
0x18007d622  psrldq  xmm0, 8
0x18007d627  movq    rax, xmm0
0x18007d62c  sub     rcx, rax
0x18007d62f  test    rcx, rcx
0x18007d632  jnz     short loc_18007D63E
0x18007d634  mov     eax, 80041318h
0x18007d639  jmp     loc_18007D847
0x18007d63e  lea     rax, [rbp+arg_18]
0x18007d642  mov     [rsp+40h+ppv], rax; ppv
0x18007d647  lea     r9, IID_INetworkListManagerPrivate; riid
0x18007d64e  xor     edx, edx; pUnkOuter
0x18007d650  lea     r8d, [rdx+4]; dwClsContext
0x18007d654  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18007d65b  call    cs:__imp_CoCreateInstance
0x18007d661  mov     ebx, eax
0x18007d663  test    eax, eax
0x18007d665  jns     short loc_18007D6D7
0x18007d667  lea     rdx, WPP_GLOBAL_Control
0x18007d66e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d675  cmp     rcx, rdx
0x18007d678  jz      short loc_18007D69F
0x18007d67a  test    byte ptr [rcx+1Ch], 80h
0x18007d67e  jz      short loc_18007D69F
0x18007d680  cmp     byte ptr [rcx+19h], 2
0x18007d684  jb      short loc_18007D69F
0x18007d686  mov     edx, 0Dh
0x18007d68b  mov     r9d, eax
0x18007d68e  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x18007d695  mov     rcx, [rcx+10h]
0x18007d699  call    WPP_SF_d
0x18007d69e  nop
0x18007d69f  mov     rcx, [rbp+arg_0]
0x18007d6a3  test    rcx, rcx
0x18007d6a6  jz      short loc_18007D6B4
0x18007d6a8  mov     rax, [rcx]
0x18007d6ab  mov     rax, [rax+10h]
0x18007d6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d6b4  mov     [rbp+arg_0], 0
0x18007d6bc  mov     rcx, [rbp+arg_18]
0x18007d6c0  test    rcx, rcx
0x18007d6c3  jz      short loc_18007D6D2
0x18007d6c5  mov     rax, [rcx]
0x18007d6c8  mov     rax, [rax+10h]
0x18007d6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d6d1  nop
0x18007d6d2  jmp     loc_18007D845
0x18007d6d7  mov     rcx, [rbp+arg_18]
0x18007d6db  mov     rax, [rcx]
0x18007d6de  lea     r8, [rbp+arg_0]
0x18007d6e2  mov     rdx, rdi
0x18007d6e5  mov     rax, [rax+30h]
0x18007d6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d6ee  mov     ebx, eax
0x18007d6f0  mov     rcx, [rbp+arg_0]
0x18007d6f4  test    eax, eax
0x18007d6f6  js      loc_18007D7D7
0x18007d6fc  test    rcx, rcx
0x18007d6ff  jz      loc_18007D7D7
0x18007d705  mov     rax, [rcx]
0x18007d708  lea     rdx, [rbp+pv]
0x18007d70c  mov     rax, [rax+18h]
0x18007d710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d715  mov     ebx, eax
0x18007d717  test    eax, eax
0x18007d719  jns     short loc_18007D78B
0x18007d71b  lea     rdx, WPP_GLOBAL_Control
0x18007d722  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d729  cmp     rcx, rdx
0x18007d72c  jz      short loc_18007D753
0x18007d72e  test    byte ptr [rcx+1Ch], 80h
0x18007d732  jz      short loc_18007D753
0x18007d734  cmp     byte ptr [rcx+19h], 2
0x18007d738  jb      short loc_18007D753
0x18007d73a  mov     edx, 0Fh
0x18007d73f  mov     r9d, eax
0x18007d742  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x18007d749  mov     rcx, [rcx+10h]
0x18007d74d  call    WPP_SF_d
0x18007d752  nop
0x18007d753  mov     rcx, [rbp+arg_0]
0x18007d757  test    rcx, rcx
0x18007d75a  jz      short loc_18007D768
0x18007d75c  mov     rax, [rcx]
0x18007d75f  mov     rax, [rax+10h]
0x18007d763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d768  mov     [rbp+arg_0], 0
0x18007d770  mov     rcx, [rbp+arg_18]
0x18007d774  test    rcx, rcx
0x18007d777  jz      short loc_18007D786
0x18007d779  mov     rax, [rcx]
0x18007d77c  mov     rax, [rax+10h]
0x18007d780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d785  nop
0x18007d786  jmp     loc_18007D845
0x18007d78b  mov     rdx, [rbp+pv]
0x18007d78f  mov     rcx, rsi
0x18007d792  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18007d797  mov     rcx, [rbp+pv]; pv
0x18007d79b  call    cs:__imp_CoTaskMemFree
0x18007d7a1  nop
0x18007d7a2  mov     rcx, [rbp+arg_0]
0x18007d7a6  test    rcx, rcx
0x18007d7a9  jz      short loc_18007D7B7
0x18007d7ab  mov     rax, [rcx]
0x18007d7ae  mov     rax, [rax+10h]
0x18007d7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7b7  mov     [rbp+arg_0], 0
0x18007d7bf  mov     rcx, [rbp+arg_18]
0x18007d7c3  test    rcx, rcx
0x18007d7c6  jz      short loc_18007D7D5
0x18007d7c8  mov     rax, [rcx]
0x18007d7cb  mov     rax, [rax+10h]
0x18007d7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7d4  nop
0x18007d7d5  jmp     short loc_18007D845
0x18007d7d7  lea     rdx, WPP_GLOBAL_Control
0x18007d7de  mov     rax, cs:WPP_GLOBAL_Control
0x18007d7e5  cmp     rax, rdx
0x18007d7e8  jz      short loc_18007D816
0x18007d7ea  test    byte ptr [rax+1Ch], 80h
0x18007d7ee  jz      short loc_18007D816
0x18007d7f0  cmp     byte ptr [rax+19h], 2
0x18007d7f4  jb      short loc_18007D816
0x18007d7f6  mov     edx, 0Eh
0x18007d7fb  mov     dword ptr [rsp+40h+ppv], ebx
0x18007d7ff  mov     r9, rdi
0x18007d802  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x18007d809  mov     rcx, [rax+10h]
0x18007d80d  call    WPP_SF__guid_D
0x18007d812  mov     rcx, [rbp+arg_0]
0x18007d816  test    rcx, rcx
0x18007d819  jz      short loc_18007D827
0x18007d81b  mov     rax, [rcx]
0x18007d81e  mov     rax, [rax+10h]
0x18007d822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d827  mov     [rbp+arg_0], 0
0x18007d82f  mov     rcx, [rbp+arg_18]
0x18007d833  test    rcx, rcx
0x18007d836  jz      short loc_18007D845
0x18007d838  mov     rax, [rcx]
0x18007d83b  mov     rax, [rax+10h]
0x18007d83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d844  nop
0x18007d845  mov     eax, ebx
0x18007d847  mov     rbx, [rsp+40h+arg_8]
0x18007d84c  add     rsp, 40h
0x18007d850  pop     rdi
0x18007d851  pop     rsi
0x18007d852  pop     rbp
0x18007d853  retn
```
