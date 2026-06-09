# BroadcastDVRComponent::IsExpandedResources(IApplicationView *,bool *)

- ea: `0x180016504`
- end: `0x180016ad5`
- name: `?IsExpandedResources@BroadcastDVRComponent@@AEAAJPEAUIApplicationView@@PEA_N@Z`
- size: `1489`
- prototype: `__int64 __fastcall(BroadcastDVRComponent *__hidden this, struct IApplicationView *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001590c`
- `0x180052510`

## callees

- `0x180016504`
- `0x1800237c8`
- `0x180031200`
- `0x18008a6f0`
- `0x1802dd470`
- `0x180356360`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001668f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800167e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001694a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001668f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800167e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001694a`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180016780`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180016780`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016662`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001667e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001685b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016877`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001691d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016939`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800169ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800169e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016a2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016a89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016662`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001667e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001685b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016877`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001691d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016939`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800169ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800169e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016a2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016a89`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800167ac`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800167ac`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180016635`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180016635`

## string_xrefs

- `0x1800167c5`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`
- `0x1800168ef`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`
- `0x180016a01`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`
- `0x180016a54`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`
- `0x180016ab1`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall BroadcastDVRComponent::IsExpandedResources(
        BroadcastDVRComponent *this,
        struct IApplicationView *a2,
        bool *a3)
{
  int (__fastcall *v5)(struct IApplicationView *, GUID *, __int64 *); // rbx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD **); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int v11; // eax
  int v12; // edi
  int v13; // eax
  HLOCAL *v14; // rcx
  unsigned int i; // edi
  _QWORD *v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rcx
  const wchar_t *v20; // rax
  const char *v21; // r9
  int v22; // eax
  unsigned int k; // ebx
  unsigned int v24; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  HLOCAL *v27; // rcx
  unsigned int v28; // edi
  _QWORD *v29; // rcx
  __int64 v30; // rcx
  unsigned int v31; // r14d
  HLOCAL *v32; // rcx
  unsigned int n; // edi
  _QWORD *v34; // rcx
  __int64 v35; // rcx
  HLOCAL *v36; // rcx
  unsigned int j; // esi
  int v38; // esi
  HLOCAL *v39; // rcx
  unsigned int m; // edi
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned int v42; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h]
  __int64 v48; // [rsp+80h] [rbp-80h]
  __int128 v49; // [rsp+88h] [rbp-78h] BYREF
  struct IApplicationView *v50; // [rsp+98h] [rbp-68h] BYREF
  _BYTE pSid2[48]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v52[48]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *a3 = 0;
  v50 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct IApplicationView *))(*(_QWORD *)a2 + 8LL))(a2);
  v45 = 0;
  v5 = **(int (__fastcall ***)(struct IApplicationView *, GUID *, __int64 *))a2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  if ( v5(a2, &GUID_d8b456d0_bec6_4f57_bb1d_50559a14384b, &v45) < 0 )
  {
LABEL_45:
    v30 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    (*(void (__fastcall **)(struct IApplicationView *))(*(_QWORD *)a2 + 16LL))(a2);
    return 0;
  }
  v44 = 0;
  v6 = v45;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v45 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  v8 = v7(v6, &v44);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73B,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
      (const char *)(unsigned int)v8,
      v41);
    goto LABEL_61;
  }
  pv = 0;
  v47 = 0;
  v48 = 0;
  v10 = *v44;
  v47 = -1;
  v48 = -1;
  v11 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, LPVOID *))(v10 + 120))(v44, 0, &pv);
  v9 = v11;
  v12 = -2147023728;
  if ( v11 == -2147023728 )
  {
LABEL_60:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    v9 = v12;
LABEL_61:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    return v9;
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x740,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
      (const char *)(unsigned int)v11,
      v41);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v47 = 0;
    v48 = 0;
    v25 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
    }
    v26 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    (*(void (__fastcall **)(struct IApplicationView *))(*(_QWORD *)a2 + 16LL))(a2);
    return v9;
  }
  hMem = 0;
  v42 = 0;
  v13 = QueryApplicationCapabilities(pv, &hMem, &v42, 0);
  v12 = v13;
  if ( v13 == -2147024444 )
  {
    v14 = (HLOCAL *)hMem;
    if ( hMem )
    {
      for ( i = 0; i < v42; v14 = (HLOCAL *)hMem )
      {
        LocalFree(v14[i]);
        *((_QWORD *)hMem + i++) = 0;
      }
      LocalFree(v14);
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v47 = 0;
    v48 = 0;
    v16 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    }
    v17 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    (*(void (__fastcall **)(struct IApplicationView *))(*(_QWORD *)a2 + 16LL))(a2);
    return 2147942852LL;
  }
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75C,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
      (const char *)(unsigned int)v13,
      0);
    v36 = (HLOCAL *)hMem;
    if ( hMem )
    {
      for ( j = 0; j < v42; v36 = (HLOCAL *)hMem )
      {
        LocalFree(v36[j]);
        *((_QWORD *)hMem + j++) = 0;
      }
      LocalFree(v36);
    }
    goto LABEL_60;
  }
  v49 = 0;
  v19 = 0x7FFF;
  v20 = L"expandedResources";
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v19;
  }
  while ( v19 );
  v21 = v19 == 0 ? (const char *)0xC000000DLL : 0LL;
  if ( v19 )
  {
    LOWORD(v49) = -2 - 2 * v19;
    WORD1(v49) = -2 * v19;
    *((_QWORD *)&v49 + 1) = L"expandedResources";
    v22 = RtlDeriveCapabilitySidsFromName(&v49, v52, pSid2, v21);
    if ( v22 >= 0 )
    {
      for ( k = 0; ; ++k )
      {
        v24 = v42;
        if ( k >= v42 )
          break;
        if ( EqualSid(*((PSID *)hMem + k), pSid2) )
        {
          *a3 = 1;
          v24 = v42;
          break;
        }
      }
      v27 = (HLOCAL *)hMem;
      if ( hMem )
      {
        v28 = 0;
        if ( v24 )
        {
          do
          {
            LocalFree(v27[v28]);
            *((_QWORD *)hMem + v28++) = 0;
            v27 = (HLOCAL *)hMem;
          }
          while ( v28 < v42 );
        }
        LocalFree(v27);
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v47 = 0;
      v48 = 0;
      v29 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
      }
      goto LABEL_45;
    }
    v38 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x76D,
            (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
            (const char *)(unsigned int)v22,
            0);
    v39 = (HLOCAL *)hMem;
    if ( hMem )
    {
      for ( m = 0; m < v42; v39 = (HLOCAL *)hMem )
      {
        LocalFree(v39[m]);
        *((_QWORD *)hMem + m++) = 0;
      }
      LocalFree(v39);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    v9 = v38;
    goto LABEL_61;
  }
  v31 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x762,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
          v21,
          0);
  v32 = (HLOCAL *)hMem;
  if ( hMem )
  {
    for ( n = 0; n < v42; v32 = (HLOCAL *)hMem )
    {
      LocalFree(v32[n]);
      *((_QWORD *)hMem + n++) = 0;
    }
    LocalFree(v32);
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v47 = 0;
  v48 = 0;
  v34 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
  }
  v35 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  (*(void (__fastcall **)(struct IApplicationView *))(*(_QWORD *)a2 + 16LL))(a2);
  return v31;
}

```

## disassembly

```asm
0x180016504  push    rbp
0x180016506  push    rbx
0x180016507  push    rsi
0x180016508  push    rdi
0x180016509  push    r14
0x18001650b  push    r15
0x18001650d  lea     rbp, [rsp-18h]
0x180016512  sub     rsp, 118h
0x180016519  mov     rax, cs:__security_cookie
0x180016520  xor     rax, rsp
0x180016523  mov     [rbp+40h+var_40], rax
0x180016527  mov     r14, r8
0x18001652a  mov     rsi, rdx
0x18001652d  xor     r15d, r15d
0x180016530  mov     [r8], r15b
0x180016533  mov     [rbp+40h+var_A8], rdx
0x180016537  test    rdx, rdx
0x18001653a  jz      short loc_18001654C
0x18001653c  mov     rax, [rdx]
0x18001653f  mov     rcx, rdx
0x180016542  mov     rax, [rax+8]
0x180016546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001654b  nop
0x18001654c  mov     [rsp+140h+var_D8], r15
0x180016551  mov     rax, [rsi]
0x180016554  mov     rbx, [rax]
0x180016557  lea     rcx, [rsp+140h+var_D8]
0x18001655c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016561  lea     r8, [rsp+140h+var_D8]
0x180016566  lea     rdx, _GUID_d8b456d0_bec6_4f57_bb1d_50559a14384b
0x18001656d  mov     rcx, rsi
0x180016570  mov     rax, rbx
0x180016573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016578  nop
0x180016579  test    eax, eax
0x18001657b  js      loc_1800168B8
0x180016581  mov     [rsp+140h+var_E0], r15
0x180016586  mov     rdi, [rsp+140h+var_D8]
0x18001658b  mov     rax, [rdi]
0x18001658e  mov     rbx, [rax+18h]
0x180016592  lea     rcx, [rsp+140h+var_E0]
0x180016597  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001659c  lea     rdx, [rsp+140h+var_E0]
0x1800165a1  mov     rcx, rdi
0x1800165a4  mov     rax, rbx
0x1800165a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165ac  mov     ebx, eax
0x1800165ae  test    eax, eax
0x1800165b0  js      loc_180016AAA
0x1800165b6  mov     [rsp+140h+pv], r15
0x1800165bb  mov     [rsp+140h+var_C8], r15
0x1800165c0  mov     [rbp+40h+var_C0], r15
0x1800165c4  mov     rcx, [rsp+140h+var_E0]
0x1800165c9  mov     rax, [rcx]
0x1800165cc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800165d0  mov     [rsp+140h+var_C8], rdx
0x1800165d5  mov     [rbp+40h+var_C0], rdx
0x1800165d9  lea     r8, [rsp+140h+pv]
0x1800165de  xor     edx, edx
0x1800165e0  mov     rax, [rax+78h]
0x1800165e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165e9  mov     ebx, eax
0x1800165eb  mov     edi, 80070490h
0x1800165f0  cmp     eax, edi
0x1800165f2  jz      loc_1800169B5
0x1800165f8  test    eax, eax
0x1800165fa  js      loc_1800167BE
0x180016600  mov     [rsp+140h+hMem], r15
0x180016605  mov     [rsp+140h+var_F0], r15d
0x18001660a  mov     [rsp+140h+var_100], r15
0x18001660f  mov     [rsp+140h+var_108], r15
0x180016614  mov     [rsp+140h+var_110], r15
0x180016619  mov     [rsp+140h+var_118], r15
0x18001661e  mov     qword ptr [rsp+140h+var_120], r15; int
0x180016623  xor     r9d, r9d
0x180016626  lea     r8, [rsp+140h+var_F0]
0x18001662b  lea     rdx, [rsp+140h+hMem]
0x180016630  mov     rcx, [rsp+140h+pv]
0x180016635  call    cs:__imp_QueryApplicationCapabilities
0x18001663b  mov     edi, eax
0x18001663d  cmp     eax, 800701C4h
0x180016642  jnz     loc_18001670C
0x180016648  mov     rcx, [rsp+140h+hMem]
0x18001664d  test    rcx, rcx
0x180016650  jz      short loc_180016685
0x180016652  mov     edi, r15d
0x180016655  cmp     [rsp+140h+var_F0], r15d
0x18001665a  jbe     short loc_18001667E
0x18001665c  mov     ebx, edi
0x18001665e  mov     rcx, [rcx+rbx*8]; hMem
0x180016662  call    cs:__imp_LocalFree
0x180016668  mov     rax, [rsp+140h+hMem]
0x18001666d  mov     [rax+rbx*8], r15
0x180016671  inc     edi
0x180016673  mov     rcx, [rsp+140h+hMem]; hMem
0x180016678  cmp     edi, [rsp+140h+var_F0]
0x18001667c  jb      short loc_18001665C
0x18001667e  call    cs:__imp_LocalFree
0x180016684  nop
0x180016685  mov     rcx, [rsp+140h+pv]; pv
0x18001668a  test    rcx, rcx
0x18001668d  jz      short loc_18001669A
0x18001668f  call    cs:__imp_CoTaskMemFree
0x180016695  mov     [rsp+140h+pv], r15
0x18001669a  mov     [rsp+140h+var_C8], r15
0x18001669f  mov     [rbp+40h+var_C0], r15
0x1800166a3  mov     rcx, [rsp+140h+var_E0]
0x1800166a8  test    rcx, rcx
0x1800166ab  jz      short loc_1800166BF
0x1800166ad  mov     [rsp+140h+var_E0], r15
0x1800166b2  mov     rax, [rcx]
0x1800166b5  mov     rax, [rax+10h]
0x1800166b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166be  nop
0x1800166bf  mov     rcx, [rsp+140h+var_D8]
0x1800166c4  test    rcx, rcx
0x1800166c7  jz      short loc_1800166DB
0x1800166c9  mov     [rsp+140h+var_D8], r15
0x1800166ce  mov     rax, [rcx]
0x1800166d1  mov     rax, [rax+10h]
0x1800166d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166da  nop
0x1800166db  mov     rcx, [rsi]
0x1800166de  mov     rax, [rcx+10h]
0x1800166e2  mov     rcx, rsi
0x1800166e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166ea  nop
0x1800166eb  mov     eax, 800701C4h
0x1800166f0  mov     rcx, [rbp+40h+var_40]
0x1800166f4  xor     rcx, rsp; StackCookie
0x1800166f7  call    __security_check_cookie
0x1800166fc  add     rsp, 118h
0x180016703  pop     r15
0x180016705  pop     r14
0x180016707  pop     rdi
0x180016708  pop     rsi
0x180016709  pop     rbx
0x18001670a  pop     rbp
0x18001670b  retn
0x18001670c  test    edi, edi
0x18001670e  js      loc_1800169FA
0x180016714  xorps   xmm0, xmm0
0x180016717  movups  [rbp+40h+var_B8], xmm0
0x18001671b  mov     ecx, 7FFFh
0x180016720  lea     r8, aExpandedresour; "expandedResources"
0x180016727  mov     rax, r8
0x18001672a  mov     edx, 2
0x18001672f  cmp     [rax], r15w
0x180016733  jz      short loc_18001673E
0x180016735  add     rax, rdx
0x180016738  sub     rcx, 1
0x18001673c  jnz     short loc_18001672F
0x18001673e  mov     rax, rcx
0x180016741  neg     rax
0x180016744  sbb     r9d, r9d
0x180016747  not     r9d
0x18001674a  and     r9d, 0C000000Dh; char *
0x180016751  test    rcx, rcx
0x180016754  jz      loc_1800168EB
0x18001675a  add     cx, cx
0x18001675d  mov     eax, 0FFFEh
0x180016762  sub     ax, cx
0x180016765  mov     word ptr [rbp+40h+var_B8], ax
0x180016769  add     ax, dx
0x18001676c  mov     word ptr [rbp+40h+var_B8+2], ax
0x180016770  mov     qword ptr [rbp+40h+var_B8+8], r8
0x180016774  lea     r8, [rbp+40h+pSid2]
0x180016778  lea     rdx, [rbp+40h+var_70]
0x18001677c  lea     rcx, [rbp+40h+var_B8]
0x180016780  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180016786  test    eax, eax
0x180016788  js      loc_180016A4D
0x18001678e  mov     ebx, r15d
0x180016791  mov     eax, [rsp+140h+var_F0]
0x180016795  cmp     ebx, eax
0x180016797  jnb     loc_180016844
0x18001679d  mov     eax, ebx
0x18001679f  lea     rdx, [rbp+40h+pSid2]; pSid2
0x1800167a3  mov     rcx, [rsp+140h+hMem]
0x1800167a8  mov     rcx, [rcx+rax*8]; pSid1
0x1800167ac  call    cs:__imp_EqualSid
0x1800167b2  test    eax, eax
0x1800167b4  jnz     loc_180016AC7
0x1800167ba  inc     ebx
0x1800167bc  jmp     short loc_180016791
0x1800167be  mov     rcx, [rbp+48h]; this
0x1800167c2  mov     r9d, ebx; char *
0x1800167c5  lea     r8, aPcshellTwinuiB_2; "pcshell\\twinui\\broadcastdvrcomponent"...
0x1800167cc  mov     edx, 740h; void *
0x1800167d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800167d6  nop
0x1800167d7  mov     rcx, [rsp+140h+pv]; pv
0x1800167dc  test    rcx, rcx
0x1800167df  jz      short loc_1800167EC
0x1800167e1  call    cs:__imp_CoTaskMemFree
0x1800167e7  mov     [rsp+140h+pv], r15
0x1800167ec  mov     [rsp+140h+var_C8], r15
0x1800167f1  mov     [rbp+40h+var_C0], r15
0x1800167f5  mov     rcx, [rsp+140h+var_E0]
0x1800167fa  test    rcx, rcx
0x1800167fd  jz      short loc_180016811
0x1800167ff  mov     [rsp+140h+var_E0], r15
0x180016804  mov     rax, [rcx]
0x180016807  mov     rax, [rax+10h]
0x18001680b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016810  nop
0x180016811  mov     rcx, [rsp+140h+var_D8]
0x180016816  test    rcx, rcx
0x180016819  jz      short loc_18001682D
0x18001681b  mov     [rsp+140h+var_D8], r15
0x180016820  mov     rax, [rcx]
0x180016823  mov     rax, [rax+10h]
0x180016827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001682c  nop
0x18001682d  mov     rax, [rsi]
0x180016830  mov     rcx, rsi
0x180016833  mov     rax, [rax+10h]
0x180016837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001683c  nop
0x18001683d  mov     eax, ebx
0x18001683f  jmp     loc_1800166F0
0x180016844  mov     rcx, [rsp+140h+hMem]
0x180016849  test    rcx, rcx
0x18001684c  jz      short loc_18001687E
0x18001684e  mov     edi, r15d
0x180016851  test    eax, eax
0x180016853  jz      short loc_180016877
0x180016855  mov     ebx, edi
0x180016857  mov     rcx, [rcx+rbx*8]; hMem
0x18001685b  call    cs:__imp_LocalFree
0x180016861  mov     rax, [rsp+140h+hMem]
0x180016866  mov     [rax+rbx*8], r15
0x18001686a  inc     edi
0x18001686c  mov     rcx, [rsp+140h+hMem]; hMem
0x180016871  cmp     edi, [rsp+140h+var_F0]
0x180016875  jb      short loc_180016855
0x180016877  call    cs:__imp_LocalFree
0x18001687d  nop
0x18001687e  mov     rcx, [rsp+140h+pv]; pv
0x180016883  test    rcx, rcx
0x180016886  jz      short loc_180016893
0x180016888  call    cs:__imp_CoTaskMemFree
0x18001688e  mov     [rsp+140h+pv], r15
0x180016893  mov     [rsp+140h+var_C8], r15
0x180016898  mov     [rbp+40h+var_C0], r15
0x18001689c  mov     rcx, [rsp+140h+var_E0]
0x1800168a1  test    rcx, rcx
0x1800168a4  jz      short loc_1800168B8
0x1800168a6  mov     [rsp+140h+var_E0], r15
0x1800168ab  mov     rax, [rcx]
0x1800168ae  mov     rax, [rax+10h]
0x1800168b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b7  nop
0x1800168b8  mov     rcx, [rsp+140h+var_D8]
0x1800168bd  test    rcx, rcx
0x1800168c0  jz      short loc_1800168D4
0x1800168c2  mov     [rsp+140h+var_D8], r15
0x1800168c7  mov     rax, [rcx]
0x1800168ca  mov     rax, [rax+10h]
0x1800168ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168d3  nop
0x1800168d4  mov     rax, [rsi]
0x1800168d7  mov     rcx, rsi
0x1800168da  mov     rax, [rax+10h]
0x1800168de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e3  nop
0x1800168e4  xor     eax, eax
0x1800168e6  jmp     loc_1800166F0
0x1800168eb  mov     rcx, [rbp+48h]; this
0x1800168ef  lea     r8, aPcshellTwinuiB_2; "pcshell\\twinui\\broadcastdvrcomponent"...
0x1800168f6  mov     edx, 762h; void *
0x1800168fb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180016900  mov     r14d, eax
0x180016903  mov     rcx, [rsp+140h+hMem]
0x180016908  test    rcx, rcx
0x18001690b  jz      short loc_180016940
0x18001690d  mov     edi, r15d
0x180016910  cmp     [rsp+140h+var_F0], r15d
0x180016915  jbe     short loc_180016939
0x180016917  mov     ebx, edi
0x180016919  mov     rcx, [rcx+rbx*8]; hMem
0x18001691d  call    cs:__imp_LocalFree
0x180016923  mov     rax, [rsp+140h+hMem]
0x180016928  mov     [rax+rbx*8], r15
0x18001692c  inc     edi
0x18001692e  mov     rcx, [rsp+140h+hMem]; hMem
0x180016933  cmp     edi, [rsp+140h+var_F0]
0x180016937  jb      short loc_180016917
0x180016939  call    cs:__imp_LocalFree
0x18001693f  nop
0x180016940  mov     rcx, [rsp+140h+pv]; pv
0x180016945  test    rcx, rcx
0x180016948  jz      short loc_180016955
0x18001694a  call    cs:__imp_CoTaskMemFree
0x180016950  mov     [rsp+140h+pv], r15
0x180016955  mov     [rsp+140h+var_C8], r15
0x18001695a  mov     [rbp+40h+var_C0], r15
0x18001695e  mov     rcx, [rsp+140h+var_E0]
0x180016963  test    rcx, rcx
0x180016966  jz      short loc_18001697A
  ... truncated ...
```
