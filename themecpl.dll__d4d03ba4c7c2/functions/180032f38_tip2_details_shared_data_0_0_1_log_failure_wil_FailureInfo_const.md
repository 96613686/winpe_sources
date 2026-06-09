# tip2::details::shared_data<0,0,1>::log_failure(wil::FailureInfo const &)

- ea: `0x180032f38`
- end: `0x180033167`
- name: `?log_failure@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXAEBUFailureInfo@wil@@@Z`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800312c0`

## callees

- `0x180002280`
- `0x18000591c`
- `0x180007934`
- `0x180032f38`
- `0x180033264`
- `0x180034340`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800330a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800330a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180033085`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180033085`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032f76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032f76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003310c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003311d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003310c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003311d`

## string_xrefs

- `0x18003307e`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::log_failure(__int64 a1, const struct wil::FailureInfo *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  char v5; // bl
  __int64 v6; // rbx
  __int64 v7; // r14
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v10; // edx
  void *v11; // rcx
  __int128 v12; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v13[2]; // [rsp+40h] [rbp-C0h]
  __int128 v14; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  char v16; // [rsp+68h] [rbp-98h]
  int v17; // [rsp+69h] [rbp-97h] BYREF
  char v18; // [rsp+6Dh] [rbp-93h]
  char v19; // [rsp+6Eh] [rbp-92h] BYREF
  __int128 v20; // [rsp+F8h] [rbp-8h]
  char v21; // [rsp+869h] [rbp+769h] BYREF
  int *v22; // [rsp+870h] [rbp+770h]
  char *v23; // [rsp+878h] [rbp+778h]
  char *v24; // [rsp+880h] [rbp+780h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  ++*(_DWORD *)(a1 + 232);
  if ( (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v20 = 0;
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)&pv, a2);
    v5 = tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(a1 + 72, &pv);
    wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)&pv);
    if ( !v5 )
      *(_DWORD *)(a1 + 64) |= 0x100000u;
  }
  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
  {
    v12 = 0;
    *(_OWORD *)v13 = 0;
    v14 = 0;
    pv = 0;
    v16 = 0;
    v22 = &v17;
    v24 = &v21;
    v17 = -2143256512;
    v18 = 0;
    v23 = &v19;
    v6 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, 1);
    v7 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_12;
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
LABEL_12:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v7, 0, v6, &v12);
    }
    else
    {
      v12 = 0;
      *(_OWORD *)v13 = 0;
      v14 = 0;
    }
    v10 = (int)v13[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(v13[0]);
    v11 = v13[1];
    if ( !v13[1] )
      *(_DWORD *)(a1 + 184) = v10;
    if ( pv )
    {
      CoTaskMemFree(pv);
      v11 = v13[1];
    }
    CoTaskMemFree(v11);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x180032f38  mov     [rsp-8+arg_10], rbx
0x180032f3d  mov     [rsp-8+arg_18], rsi
0x180032f42  push    rbp
0x180032f43  push    rdi
0x180032f44  push    r14
0x180032f46  lea     rbp, [rsp-7A0h]
0x180032f4e  sub     rsp, 8A0h
0x180032f55  mov     rax, cs:__security_cookie
0x180032f5c  xor     rax, rsp
0x180032f5f  mov     [rbp+7B0h+var_20], rax
0x180032f66  mov     rbx, rdx
0x180032f69  mov     rdi, rcx
0x180032f6c  lea     rsi, [rcx+0C0h]
0x180032f73  mov     rcx, rsi; lpCriticalSection
0x180032f76  call    cs:__imp_EnterCriticalSection
0x180032f7d  nop     dword ptr [rax+rax+00h]
0x180032f82  inc     dword ptr [rdi+0E8h]
0x180032f88  mov     r14d, 100h
0x180032f8e  test    [rdi+40h], r14d
0x180032f92  jnz     short loc_180032FCC
0x180032f94  xorps   xmm0, xmm0
0x180032f97  movdqu  [rbp+7B0h+var_7B8], xmm0
0x180032f9c  mov     rdx, rbx; struct wil::FailureInfo *
0x180032f9f  lea     rcx, [rsp+8B0h+pv]; this
0x180032fa4  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x180032fa9  lea     rcx, [rdi+48h]
0x180032fad  lea     rdx, [rsp+8B0h+pv]
0x180032fb2  call    ?push_back@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N$$QEAVStoredFailureInfo@wil@@@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(wil::StoredFailureInfo &&)
0x180032fb7  mov     bl, al
0x180032fb9  lea     rcx, [rsp+8B0h+pv]; this
0x180032fbe  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180032fc3  test    bl, bl
0x180032fc5  jnz     short loc_180032FCC
0x180032fc7  bts     dword ptr [rdi+40h], 14h
0x180032fcc  bts     dword ptr [rdi+40h], 0Bh
0x180032fd1  cmp     qword ptr [rdi+0F0h], 0
0x180032fd9  jz      loc_180033129
0x180032fdf  test    [rdi+40h], r14d
0x180032fe3  jnz     loc_180033129
0x180032fe9  test    dword ptr [rdi+14h], 8000h
0x180032ff0  jnz     loc_180033129
0x180032ff6  xorps   xmm0, xmm0
0x180032ff9  movups  [rsp+8B0h+var_880], xmm0
0x180032ffe  movups  xmmword ptr [rsp+8B0h+var_870], xmm0
0x180033003  movups  [rsp+8B0h+var_860], xmm0
0x180033008  mov     [rsp+8B0h+pv], 0
0x180033011  mov     [rsp+8B0h+var_848], 0
0x180033016  lea     rax, [rsp+8B0h+var_847]
0x18003301b  mov     [rbp+7B0h+var_40], rax
0x180033022  lea     rax, [rbp+7B0h+var_47]
0x180033029  mov     [rbp+7B0h+var_30], rax
0x180033030  mov     [rsp+8B0h+var_847], 80408040h
0x180033038  mov     [rsp+8B0h+var_843], 0
0x18003303d  lea     rax, [rsp+8B0h+var_842]
0x180033042  mov     [rbp+7B0h+var_38], rax
0x180033049  mov     r8d, 1
0x18003304f  lea     rdx, [rsp+8B0h+pv]
0x180033054  mov     rcx, rdi
0x180033057  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18003305c  mov     rbx, rax
0x18003305f  mov     r14, [rdi+0F0h]
0x180033066  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18003306d  test    rax, rax
0x180033070  jnz     short loc_1800330CE
0x180033072  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180033079  test    rax, rax
0x18003307c  jnz     short loc_180033098
0x18003307e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180033085  call    cs:__imp_GetModuleHandleW
0x18003308c  nop     dword ptr [rax+rax+00h]
0x180033091  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180033098  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18003309f  mov     rcx, rax; hModule
0x1800330a2  call    cs:__imp_GetProcAddress
0x1800330a9  nop     dword ptr [rax+rax+00h]
0x1800330ae  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800330b5  test    rax, rax
0x1800330b8  jnz     short loc_1800330CE
0x1800330ba  xorps   xmm0, xmm0
0x1800330bd  movups  [rsp+8B0h+var_880], xmm0
0x1800330c2  movups  xmmword ptr [rsp+8B0h+var_870], xmm0
0x1800330c7  movups  [rsp+8B0h+var_860], xmm0
0x1800330cc  jmp     short loc_1800330E0
0x1800330ce  lea     r9, [rsp+8B0h+var_880]
0x1800330d3  mov     r8, rbx
0x1800330d6  xor     edx, edx
0x1800330d8  mov     rcx, r14
0x1800330db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330e0  mov     rdx, [rsp+8B0h+var_870]
0x1800330e5  mov     rax, rdx
0x1800330e8  shr     rax, 20h
0x1800330ec  or      [rdi+40h], eax
0x1800330ef  mov     rcx, [rsp+8B0h+var_870+8]
0x1800330f4  test    rcx, rcx
0x1800330f7  jnz     short loc_1800330FF
0x1800330f9  mov     [rdi+0B8h], edx
0x1800330ff  mov     rax, [rsp+8B0h+pv]
0x180033104  test    rax, rax
0x180033107  jz      short loc_18003311D
0x180033109  mov     rcx, rax; pv
0x18003310c  call    cs:__imp_CoTaskMemFree
0x180033113  nop     dword ptr [rax+rax+00h]
0x180033118  mov     rcx, [rsp+8B0h+var_870+8]; pv
0x18003311d  call    cs:__imp_CoTaskMemFree
0x180033124  nop     dword ptr [rax+rax+00h]
0x180033129  dec     dword ptr [rdi+0E8h]
0x18003312f  mov     rcx, rsi; lpCriticalSection
0x180033132  call    cs:__imp_LeaveCriticalSection
0x180033139  nop     dword ptr [rax+rax+00h]
0x18003313e  nop
0x18003313f  mov     rcx, [rbp+7B0h+var_20]
0x180033146  xor     rcx, rsp; StackCookie
0x180033149  call    __security_check_cookie
0x18003314e  lea     r11, [rsp+8B0h+var_10]
0x180033156  mov     rbx, [r11+30h]
0x18003315a  mov     rsi, [r11+38h]
0x18003315e  mov     rsp, r11
0x180033161  pop     r14
0x180033163  pop     rdi
0x180033164  pop     rbp
0x180033165  retn
```
