# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180019838`
- end: `0x1800199d4`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `412`
- prototype: ``
- caller_count: `17`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013b48`
- `0x18001ab6c`
- `0x180022c78`
- `0x180022d00`
- `0x180022d88`
- `0x180022e10`
- `0x180022e98`
- `0x18002f4bc`
- `0x180032a28`
- `0x180032ab0`
- `0x18004070c`
- `0x1800516bc`
- `0x1800585f4`
- `0x18005867c`
- `0x180058704`
- `0x180060ed8`
- `0x180069564`

## callees

- `0x180002810`
- `0x180019838`
- `0x18001bc0c`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001999f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001999f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019930`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019930`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019919`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019919`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800199b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800199b2`

## string_xrefs

- `0x180019912`: `kernelbase.dll`

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
0x180019838  push    rbp
0x18001983a  push    rbx
0x18001983b  push    rsi
0x18001983c  push    rdi
0x18001983d  lea     rbp, [rsp-7A8h]
0x180019845  sub     rsp, 8A8h
0x18001984c  mov     rax, cs:__security_cookie
0x180019853  xor     rax, rsp
0x180019856  mov     [rbp+7C0h+var_30], rax
0x18001985d  mov     rbx, rcx
0x180019860  bts     dword ptr [rcx+40h], 0Bh
0x180019865  cmp     qword ptr [rcx+0F0h], 0
0x18001986d  jz      loc_1800199A5
0x180019873  test    dword ptr [rcx+40h], 100h
0x18001987a  jnz     loc_1800199A5
0x180019880  test    dword ptr [rcx+14h], 8000h
0x180019887  jnz     loc_1800199A5
0x18001988d  xorps   xmm0, xmm0
0x180019890  movups  [rsp+8C0h+var_890], xmm0
0x180019895  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x18001989a  movups  [rsp+8C0h+var_870], xmm0
0x18001989f  mov     [rsp+8C0h+pv], 0
0x1800198a8  mov     [rsp+8C0h+var_858], 0
0x1800198ad  lea     rax, [rsp+8C0h+var_857]
0x1800198b2  mov     [rbp+7C0h+var_50], rax
0x1800198b9  lea     rax, [rbp+7C0h+var_57]
0x1800198c0  mov     [rbp+7C0h+var_40], rax
0x1800198c7  mov     [rsp+8C0h+var_857], 80408040h
0x1800198cf  mov     [rsp+8C0h+var_853], 0
0x1800198d4  lea     rax, [rsp+8C0h+var_852]
0x1800198d9  mov     [rbp+7C0h+var_48], rax
0x1800198e0  mov     r8d, 1
0x1800198e6  lea     rdx, [rsp+8C0h+pv]
0x1800198eb  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800198f0  mov     rdi, rax
0x1800198f3  mov     rsi, [rbx+0F0h]
0x1800198fa  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180019901  test    rax, rax
0x180019904  jnz     short loc_180019956
0x180019906  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001990d  test    rax, rax
0x180019910  jnz     short loc_180019926
0x180019912  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180019919  call    cs:__imp_GetModuleHandleW
0x18001991f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180019926  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18001992d  mov     rcx, rax; hModule
0x180019930  call    cs:__imp_GetProcAddress
0x180019936  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18001993d  test    rax, rax
0x180019940  jnz     short loc_180019956
0x180019942  xorps   xmm0, xmm0
0x180019945  movups  [rsp+8C0h+var_890], xmm0
0x18001994a  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x18001994f  movups  [rsp+8C0h+var_870], xmm0
0x180019954  jmp     short loc_180019968
0x180019956  lea     r9, [rsp+8C0h+var_890]
0x18001995b  mov     r8, rdi
0x18001995e  xor     edx, edx
0x180019960  mov     rcx, rsi
0x180019963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019968  mov     rdx, [rsp+8C0h+var_880]
0x18001996d  mov     rax, rdx
0x180019970  shr     rax, 20h
0x180019974  or      [rbx+40h], eax
0x180019977  mov     rcx, [rsp+8C0h+var_880+8]
0x18001997c  test    rcx, rcx
0x18001997f  jnz     short loc_180019987
0x180019981  mov     [rbx+0B8h], edx
0x180019987  mov     rax, [rsp+8C0h+pv]
0x18001998c  test    rax, rax
0x18001998f  jz      short loc_18001999F
0x180019991  mov     rcx, rax; pv
0x180019994  call    cs:__imp_CoTaskMemFree
0x18001999a  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x18001999f  call    cs:__imp_CoTaskMemFree
0x1800199a5  dec     dword ptr [rbx+0E8h]
0x1800199ab  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800199b2  call    cs:__imp_LeaveCriticalSection
0x1800199b8  nop
0x1800199b9  mov     rcx, [rbp+7C0h+var_30]
0x1800199c0  xor     rcx, rsp; StackCookie
0x1800199c3  call    __security_check_cookie
0x1800199c8  add     rsp, 8A8h
0x1800199cf  pop     rdi
0x1800199d0  pop     rsi
0x1800199d1  pop     rbx
0x1800199d2  pop     rbp
0x1800199d3  retn
```
