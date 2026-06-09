# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x1800156e4`
- end: `0x180015819`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010b80`
- `0x180010f28`
- `0x180011994`
- `0x180014590`

## callees

- `0x180001e40`
- `0x1800156e4`
- `0x180015a68`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015772`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015772`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015789`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015789`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015708`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800157c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001580f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800157c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001580f`

## string_xrefs

- `0x18001576b`: `kernelbase.dll`

## pseudocode

```c
char __fastcall tip2::details::shared_data<1,0,0>::begin_update(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int v3; // esi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  void *v7; // rcx
  __int128 v8; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-38h]
  __int128 v10; // [rsp+50h] [rbp-28h]

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  ++*(_DWORD *)(a1 + 232);
  if ( (*(_DWORD *)(a1 + 64) & 0x100) != 0 )
    return 0;
  v2 = *(_QWORD *)(a1 + 240);
  if ( v2 && *(_DWORD *)(a1 + 232) == 1 )
  {
    v8 = 0;
    *(_OWORD *)pv = 0;
    v10 = 0;
    v3 = *(_DWORD *)(a1 + 184);
    ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
    if ( !`TestQueryData'::`2'::s_pfnTestQueryData )
    {
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestQueryData");
      `TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress;
      if ( !ProcAddress )
      {
        v8 = 0;
        *(_OWORD *)pv = 0;
        v10 = 0;
LABEL_10:
        CoTaskMemFree(pv[1]);
        return 0;
      }
    }
    if ( !((unsigned int (__fastcall *)(__int64, __int64, _QWORD, __int128 *))ProcAddress)(v2, 1, v3, &v8) )
      goto LABEL_10;
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    v7 = pv[1];
    if ( pv[1] )
    {
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v8);
      v7 = pv[1];
    }
    else
    {
      *(_DWORD *)(a1 + 184) = pv[0];
    }
    CoTaskMemFree(v7);
  }
  return 1;
}

```

## disassembly

```asm
0x1800156e4  push    rbp
0x1800156e6  push    rbx
0x1800156e7  push    rsi
0x1800156e8  push    rdi
0x1800156e9  mov     rbp, rsp
0x1800156ec  sub     rsp, 78h
0x1800156f0  mov     rax, cs:__security_cookie
0x1800156f7  xor     rax, rsp
0x1800156fa  mov     [rbp+var_18], rax
0x1800156fe  mov     rbx, rcx
0x180015701  add     rcx, 0C0h; lpCriticalSection
0x180015708  call    cs:__imp_EnterCriticalSection
0x18001570e  inc     dword ptr [rbx+0E8h]
0x180015714  test    dword ptr [rbx+40h], 100h
0x18001571b  jnz     loc_1800157CE
0x180015721  mov     rdi, [rbx+0F0h]
0x180015728  test    rdi, rdi
0x18001572b  jz      loc_180015815
0x180015731  cmp     dword ptr [rbx+0E8h], 1
0x180015738  jnz     loc_180015815
0x18001573e  xorps   xmm0, xmm0
0x180015741  movups  [rbp+var_48], xmm0
0x180015745  movups  xmmword ptr [rbp+pv], xmm0
0x180015749  movups  [rbp+var_28], xmm0
0x18001574d  mov     esi, [rbx+0B8h]
0x180015753  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18001575a  test    rax, rax
0x18001575d  jnz     short loc_1800157AC
0x18001575f  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180015766  test    rax, rax
0x180015769  jnz     short loc_18001577F
0x18001576b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180015772  call    cs:__imp_GetModuleHandleW
0x180015778  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001577f  lea     rdx, aTestquerydata; "TestQueryData"
0x180015786  mov     rcx, rax; hModule
0x180015789  call    cs:__imp_GetProcAddress
0x18001578f  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180015796  test    rax, rax
0x180015799  jnz     short loc_1800157AC
0x18001579b  xorps   xmm0, xmm0
0x18001579e  movups  [rbp+var_48], xmm0
0x1800157a2  movups  xmmword ptr [rbp+pv], xmm0
0x1800157a6  movups  [rbp+var_28], xmm0
0x1800157aa  jmp     short loc_1800157C4
0x1800157ac  lea     r9, [rbp+var_48]
0x1800157b0  mov     r8d, esi
0x1800157b3  mov     edx, 1
0x1800157b8  mov     rcx, rdi
0x1800157bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157c0  test    eax, eax
0x1800157c2  jnz     short loc_1800157E5
0x1800157c4  mov     rcx, [rbp+pv+8]; pv
0x1800157c8  call    cs:__imp_CoTaskMemFree
0x1800157ce  xor     al, al
0x1800157d0  mov     rcx, [rbp+var_18]
0x1800157d4  xor     rcx, rsp; StackCookie
0x1800157d7  call    __security_check_cookie
0x1800157dc  add     rsp, 78h
0x1800157e0  pop     rdi
0x1800157e1  pop     rsi
0x1800157e2  pop     rbx
0x1800157e3  pop     rbp
0x1800157e4  retn
0x1800157e5  mov     eax, dword ptr [rbp+pv+4]
0x1800157e8  or      [rbx+40h], eax
0x1800157eb  mov     rcx, [rbp+pv+8]; pv
0x1800157ef  test    rcx, rcx
0x1800157f2  jz      short loc_180015806
0x1800157f4  lea     rdx, [rbp+var_48]
0x1800157f8  mov     rcx, rbx
0x1800157fb  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180015800  mov     rcx, [rbp+pv+8]
0x180015804  jmp     short loc_18001580F
0x180015806  mov     edx, dword ptr [rbp+pv]
0x180015809  mov     [rbx+0B8h], edx
0x18001580f  call    cs:__imp_CoTaskMemFree
0x180015815  mov     al, 1
0x180015817  jmp     short loc_1800157D0
```
