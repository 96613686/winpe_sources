# tip2::details::shared_data<0,0,1>::end_update(void)

- ea: `0x1800570e0`
- end: `0x18005727c`
- name: `?end_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ`
- size: `412`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e5a0`
- `0x18000e874`
- `0x18000eb1c`
- `0x18000edc0`
- `0x18000f09c`
- `0x18000f340`
- `0x18000f5e8`
- `0x18003cd20`

## callees

- `0x180002ad0`
- `0x1800570e0`
- `0x18005ee70`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005725a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005725a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800571d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800571d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800571c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800571c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005723c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005723c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057247`

## string_xrefs

- `0x1800571ba`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::end_update(__int64 a1)
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
    v2 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, 1);
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
0x1800570e0  push    rbp
0x1800570e2  push    rbx
0x1800570e3  push    rsi
0x1800570e4  push    rdi
0x1800570e5  lea     rbp, [rsp-7A8h]
0x1800570ed  sub     rsp, 8A8h
0x1800570f4  mov     rax, cs:__security_cookie
0x1800570fb  xor     rax, rsp
0x1800570fe  mov     [rbp+7C0h+var_30], rax
0x180057105  mov     rbx, rcx
0x180057108  bts     dword ptr [rcx+40h], 0Bh
0x18005710d  cmp     qword ptr [rcx+0F0h], 0
0x180057115  jz      loc_18005724D
0x18005711b  test    dword ptr [rcx+40h], 100h
0x180057122  jnz     loc_18005724D
0x180057128  test    dword ptr [rcx+14h], 8000h
0x18005712f  jnz     loc_18005724D
0x180057135  xorps   xmm0, xmm0
0x180057138  movups  [rsp+8C0h+var_890], xmm0
0x18005713d  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x180057142  movups  [rsp+8C0h+var_870], xmm0
0x180057147  mov     [rsp+8C0h+pv], 0
0x180057150  mov     [rsp+8C0h+var_858], 0
0x180057155  lea     rax, [rsp+8C0h+var_857]
0x18005715a  mov     [rbp+7C0h+var_50], rax
0x180057161  lea     rax, [rbp+7C0h+var_57]
0x180057168  mov     [rbp+7C0h+var_40], rax
0x18005716f  mov     [rsp+8C0h+var_857], 80408040h
0x180057177  mov     [rsp+8C0h+var_853], 0
0x18005717c  lea     rax, [rsp+8C0h+var_852]
0x180057181  mov     [rbp+7C0h+var_48], rax
0x180057188  mov     r8d, 1
0x18005718e  lea     rdx, [rsp+8C0h+pv]
0x180057193  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180057198  mov     rdi, rax
0x18005719b  mov     rsi, [rbx+0F0h]
0x1800571a2  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800571a9  test    rax, rax
0x1800571ac  jnz     short loc_1800571FE
0x1800571ae  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800571b5  test    rax, rax
0x1800571b8  jnz     short loc_1800571CE
0x1800571ba  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800571c1  call    cs:__imp_GetModuleHandleW
0x1800571c7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800571ce  lea     rdx, aTestunlockdata; "TestUnlockData"
0x1800571d5  mov     rcx, rax; hModule
0x1800571d8  call    cs:__imp_GetProcAddress
0x1800571de  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800571e5  test    rax, rax
0x1800571e8  jnz     short loc_1800571FE
0x1800571ea  xorps   xmm0, xmm0
0x1800571ed  movups  [rsp+8C0h+var_890], xmm0
0x1800571f2  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x1800571f7  movups  [rsp+8C0h+var_870], xmm0
0x1800571fc  jmp     short loc_180057210
0x1800571fe  lea     r9, [rsp+8C0h+var_890]
0x180057203  mov     r8, rdi
0x180057206  xor     edx, edx
0x180057208  mov     rcx, rsi
0x18005720b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057210  mov     rdx, [rsp+8C0h+var_880]
0x180057215  mov     rax, rdx
0x180057218  shr     rax, 20h
0x18005721c  or      [rbx+40h], eax
0x18005721f  mov     rcx, [rsp+8C0h+var_880+8]
0x180057224  test    rcx, rcx
0x180057227  jnz     short loc_18005722F
0x180057229  mov     [rbx+0B8h], edx
0x18005722f  mov     rax, [rsp+8C0h+pv]
0x180057234  test    rax, rax
0x180057237  jz      short loc_180057247
0x180057239  mov     rcx, rax; pv
0x18005723c  call    cs:__imp_CoTaskMemFree
0x180057242  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x180057247  call    cs:__imp_CoTaskMemFree
0x18005724d  dec     dword ptr [rbx+0E8h]
0x180057253  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18005725a  call    cs:__imp_LeaveCriticalSection
0x180057260  nop
0x180057261  mov     rcx, [rbp+7C0h+var_30]
0x180057268  xor     rcx, rsp; StackCookie
0x18005726b  call    __security_check_cookie
0x180057270  add     rsp, 8A8h
0x180057277  pop     rdi
0x180057278  pop     rsi
0x180057279  pop     rbx
0x18005727a  pop     rbp
0x18005727b  retn
```
