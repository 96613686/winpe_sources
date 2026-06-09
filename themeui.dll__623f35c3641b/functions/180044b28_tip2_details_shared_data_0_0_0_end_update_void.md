# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180044b28`
- end: `0x180044c9e`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `374`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180003b00`
- `0x18003300c`

## callees

- `0x18001e880`
- `0x1800321d4`
- `0x180033a34`
- `0x1800358c0`
- `0x180044b28`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044c05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044c05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044c7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044c7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044c69`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  int v6; // ecx
  __int128 v7; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h]
  __int128 v9; // [rsp+50h] [rbp-B0h]
  __int64 v10; // [rsp+60h] [rbp-A0h] BYREF
  char v11; // [rsp+68h] [rbp-98h]
  int v12; // [rsp+69h] [rbp-97h] BYREF
  char v13; // [rsp+6Dh] [rbp-93h]
  char v14; // [rsp+6Eh] [rbp-92h] BYREF
  char v15; // [rsp+869h] [rbp+769h] BYREF
  int *v16; // [rsp+870h] [rbp+770h]
  char *v17; // [rsp+878h] [rbp+778h]
  char *v18; // [rsp+880h] [rbp+780h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
  {
    v7 = 0;
    *(_OWORD *)pv = 0;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v16 = &v12;
    v18 = &v15;
    v12 = -2143256512;
    v13 = 0;
    v17 = &v14;
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v10, 1);
    v3 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData
      || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
          ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestUnlockData"),
          (`TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v3, 0, v2, &v7);
    }
    else
    {
      v7 = 0;
      *(_OWORD *)pv = 0;
      v9 = 0;
    }
    v6 = (int)pv[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( !pv[1] )
      *(_DWORD *)(a1 + 184) = v6;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v10);
    CoTaskMemFree(pv[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x180044b28  push    rbp
0x180044b2a  push    rbx
0x180044b2b  push    rsi
0x180044b2c  push    rdi
0x180044b2d  lea     rbp, [rsp-7A8h]
0x180044b35  sub     rsp, 8A8h
0x180044b3c  mov     rax, cs:__security_cookie
0x180044b43  xor     rax, rsp
0x180044b46  mov     [rbp+7C0h+var_30], rax
0x180044b4d  mov     rbx, rcx
0x180044b50  bts     dword ptr [rcx+40h], 0Bh
0x180044b55  cmp     qword ptr [rcx+0F0h], 0
0x180044b5d  jz      loc_180044C6F
0x180044b63  test    dword ptr [rcx+40h], 100h
0x180044b6a  jnz     loc_180044C6F
0x180044b70  test    dword ptr [rcx+14h], 8000h
0x180044b77  jnz     loc_180044C6F
0x180044b7d  xorps   xmm0, xmm0
0x180044b80  movups  [rsp+8C0h+var_890], xmm0
0x180044b85  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180044b8a  movups  [rsp+8C0h+var_870], xmm0
0x180044b8f  mov     [rsp+8C0h+var_860], 0
0x180044b98  mov     [rsp+8C0h+var_858], 0
0x180044b9d  lea     rax, [rsp+8C0h+var_857]
0x180044ba2  mov     [rbp+7C0h+var_50], rax
0x180044ba9  lea     rax, [rbp+7C0h+var_57]
0x180044bb0  mov     [rbp+7C0h+var_40], rax
0x180044bb7  mov     [rsp+8C0h+var_857], 80408040h
0x180044bbf  mov     [rsp+8C0h+var_853], 0
0x180044bc4  lea     rax, [rsp+8C0h+var_852]
0x180044bc9  mov     [rbp+7C0h+var_48], rax
0x180044bd0  mov     r8d, 1
0x180044bd6  lea     rdx, [rsp+8C0h+var_860]
0x180044bdb  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180044be0  mov     rdi, rax
0x180044be3  mov     rsi, [rbx+0F0h]
0x180044bea  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180044bf1  test    rax, rax
0x180044bf4  jnz     short loc_180044C2B
0x180044bf6  call    tip_details_GetKernelBaseModuleHandle
0x180044bfb  mov     rcx, rax; hModule
0x180044bfe  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180044c05  call    cs:__imp_GetProcAddress
0x180044c0b  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180044c12  test    rax, rax
0x180044c15  jnz     short loc_180044C2B
0x180044c17  xorps   xmm0, xmm0
0x180044c1a  movups  [rsp+8C0h+var_890], xmm0
0x180044c1f  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180044c24  movups  [rsp+8C0h+var_870], xmm0
0x180044c29  jmp     short loc_180044C3D
0x180044c2b  lea     r9, [rsp+8C0h+var_890]
0x180044c30  mov     r8, rdi
0x180044c33  xor     edx, edx
0x180044c35  mov     rcx, rsi
0x180044c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c3d  mov     rcx, [rsp+8C0h+pv]
0x180044c42  mov     rax, rcx
0x180044c45  shr     rax, 20h
0x180044c49  or      [rbx+40h], eax
0x180044c4c  cmp     [rsp+8C0h+pv+8], 0
0x180044c52  jnz     short loc_180044C5A
0x180044c54  mov     [rbx+0B8h], ecx
0x180044c5a  lea     rcx, [rsp+8C0h+var_860]
0x180044c5f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180044c64  mov     rcx, [rsp+8C0h+pv+8]; pv
0x180044c69  call    cs:__imp_CoTaskMemFree
0x180044c6f  dec     dword ptr [rbx+0E8h]
0x180044c75  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180044c7c  call    cs:__imp_LeaveCriticalSection
0x180044c82  nop
0x180044c83  mov     rcx, [rbp+7C0h+var_30]
0x180044c8a  xor     rcx, rsp; StackCookie
0x180044c8d  call    __security_check_cookie
0x180044c92  add     rsp, 8A8h
0x180044c99  pop     rdi
0x180044c9a  pop     rsi
0x180044c9b  pop     rbx
0x180044c9c  pop     rbp
0x180044c9d  retn
```
