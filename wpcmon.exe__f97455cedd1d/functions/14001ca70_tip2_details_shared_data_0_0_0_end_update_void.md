# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x14001ca70`
- end: `0x14001cc0c`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `412`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000ce38`

## callees

- `0x140005530`
- `0x14001ca70`
- `0x14001e67c`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001cb68`
- `KERNEL32!GetProcAddress` at `0x14001cb68`
- `KERNEL32!GetModuleHandleW` at `0x14001cb51`
- `KERNEL32!GetModuleHandleW` at `0x14001cb51`
- `KERNEL32!LeaveCriticalSection` at `0x14001cbea`
- `KERNEL32!LeaveCriticalSection` at `0x14001cbea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001cbcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001cbd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001cbcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001cbd7`

## string_xrefs

- `0x14001cb4a`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v6; // edx
  void *v7; // rcx
  __int128 v8; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v9[2]; // [rsp+40h] [rbp-C0h]
  __int128 v10; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  char v12; // [rsp+68h] [rbp-98h]
  int v13; // [rsp+69h] [rbp-97h] BYREF
  char v14; // [rsp+6Dh] [rbp-93h]
  char v15; // [rsp+6Eh] [rbp-92h] BYREF
  char v16; // [rsp+869h] [rbp+769h] BYREF
  int *v17; // [rsp+870h] [rbp+770h]
  char *v18; // [rsp+878h] [rbp+778h]
  char *v19; // [rsp+880h] [rbp+780h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
  {
    v8 = 0;
    *(_OWORD *)v9 = 0;
    v10 = 0;
    pv = 0;
    v12 = 0;
    v17 = &v13;
    v19 = &v16;
    v13 = -2143256512;
    v14 = 0;
    v18 = &v15;
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
    v3 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_9;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestUnlockData");
    `TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)ProcAddress;
    if ( ProcAddress )
    {
LABEL_9:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v3, 0, v2, &v8);
    }
    else
    {
      v8 = 0;
      *(_OWORD *)v9 = 0;
      v10 = 0;
    }
    v6 = (int)v9[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(v9[0]);
    v7 = v9[1];
    if ( !v9[1] )
      *(_DWORD *)(a1 + 184) = v6;
    if ( pv )
    {
      CoTaskMemFree(pv);
      v7 = v9[1];
    }
    CoTaskMemFree(v7);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x14001ca70  push    rbp
0x14001ca72  push    rbx
0x14001ca73  push    rsi
0x14001ca74  push    rdi
0x14001ca75  lea     rbp, [rsp-7A8h]
0x14001ca7d  sub     rsp, 8A8h
0x14001ca84  mov     rax, cs:__security_cookie
0x14001ca8b  xor     rax, rsp
0x14001ca8e  mov     [rbp+7C0h+var_30], rax
0x14001ca95  mov     rbx, rcx
0x14001ca98  bts     dword ptr [rcx+40h], 0Bh
0x14001ca9d  cmp     qword ptr [rcx+0F0h], 0
0x14001caa5  jz      loc_14001CBDD
0x14001caab  test    dword ptr [rcx+40h], 100h
0x14001cab2  jnz     loc_14001CBDD
0x14001cab8  test    dword ptr [rcx+14h], 8000h
0x14001cabf  jnz     loc_14001CBDD
0x14001cac5  xorps   xmm0, xmm0
0x14001cac8  movups  [rsp+8C0h+var_890], xmm0
0x14001cacd  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x14001cad2  movups  [rsp+8C0h+var_870], xmm0
0x14001cad7  mov     [rsp+8C0h+pv], 0
0x14001cae0  mov     [rsp+8C0h+var_858], 0
0x14001cae5  lea     rax, [rsp+8C0h+var_857]
0x14001caea  mov     [rbp+7C0h+var_50], rax
0x14001caf1  lea     rax, [rbp+7C0h+var_57]
0x14001caf8  mov     [rbp+7C0h+var_40], rax
0x14001caff  mov     [rsp+8C0h+var_857], 80408040h
0x14001cb07  mov     [rsp+8C0h+var_853], 0
0x14001cb0c  lea     rax, [rsp+8C0h+var_852]
0x14001cb11  mov     [rbp+7C0h+var_48], rax
0x14001cb18  mov     r8d, 1
0x14001cb1e  lea     rdx, [rsp+8C0h+pv]
0x14001cb23  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14001cb28  mov     rdi, rax
0x14001cb2b  mov     rsi, [rbx+0F0h]
0x14001cb32  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x14001cb39  test    rax, rax
0x14001cb3c  jnz     short loc_14001CB8E
0x14001cb3e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x14001cb45  test    rax, rax
0x14001cb48  jnz     short loc_14001CB5E
0x14001cb4a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001cb51  call    cs:__imp_GetModuleHandleW
0x14001cb57  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14001cb5e  lea     rdx, aTestunlockdata; "TestUnlockData"
0x14001cb65  mov     rcx, rax; hModule
0x14001cb68  call    cs:__imp_GetProcAddress
0x14001cb6e  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x14001cb75  test    rax, rax
0x14001cb78  jnz     short loc_14001CB8E
0x14001cb7a  xorps   xmm0, xmm0
0x14001cb7d  movups  [rsp+8C0h+var_890], xmm0
0x14001cb82  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x14001cb87  movups  [rsp+8C0h+var_870], xmm0
0x14001cb8c  jmp     short loc_14001CBA0
0x14001cb8e  lea     r9, [rsp+8C0h+var_890]
0x14001cb93  mov     r8, rdi
0x14001cb96  xor     edx, edx
0x14001cb98  mov     rcx, rsi
0x14001cb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cba0  mov     rdx, [rsp+8C0h+var_880]
0x14001cba5  mov     rax, rdx
0x14001cba8  shr     rax, 20h
0x14001cbac  or      [rbx+40h], eax
0x14001cbaf  mov     rcx, [rsp+8C0h+var_880+8]
0x14001cbb4  test    rcx, rcx
0x14001cbb7  jnz     short loc_14001CBBF
0x14001cbb9  mov     [rbx+0B8h], edx
0x14001cbbf  mov     rax, [rsp+8C0h+pv]
0x14001cbc4  test    rax, rax
0x14001cbc7  jz      short loc_14001CBD7
0x14001cbc9  mov     rcx, rax; pv
0x14001cbcc  call    cs:__imp_CoTaskMemFree
0x14001cbd2  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x14001cbd7  call    cs:__imp_CoTaskMemFree
0x14001cbdd  dec     dword ptr [rbx+0E8h]
0x14001cbe3  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x14001cbea  call    cs:__imp_LeaveCriticalSection
0x14001cbf0  nop
0x14001cbf1  mov     rcx, [rbp+7C0h+var_30]
0x14001cbf8  xor     rcx, rsp; StackCookie
0x14001cbfb  call    __security_check_cookie
0x14001cc00  add     rsp, 8A8h
0x14001cc07  pop     rdi
0x14001cc08  pop     rsi
0x14001cc09  pop     rbx
0x14001cc0a  pop     rbp
0x14001cc0b  retn
```
