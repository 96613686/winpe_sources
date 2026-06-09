# tip2::tip_test<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::start(void)

- ea: `0x18000d988`
- end: `0x18000dbe2`
- name: `?start@?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `602`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c4a0`

## callees

- `0x180005950`
- `0x1800061f0`
- `0x1800065e0`
- `0x18000d988`
- `0x18000de94`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d9fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d9fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dba1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000db22`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000db22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db39`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dbaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dbaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da75`

## string_xrefs

- `0x18000db2f`: `TestCreate`
- `0x18000db1b`: `kernelbase.dll`

## pseudocode

```c
_OWORD *__fastcall tip2::tip_test<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::start(
        struct _RTL_CRITICAL_SECTION **a1,
        _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // r12
  struct _RTL_CRITICAL_SECTION **v6; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rdx
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // rsi
  __int64 v12; // r8
  unsigned int LockSemaphore_high; // r13d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  char DebugInfo; // [rsp+40h] [rbp-C0h]
  unsigned int LockSemaphore; // [rsp+44h] [rbp-BCh]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v20; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+59h] [rbp-A7h] BYREF
  char v23; // [rsp+5Dh] [rbp-A3h]
  _BYTE v24[2050]; // [rsp+5Eh] [rbp-A2h] BYREF
  int *v25; // [rsp+860h] [rbp+760h]
  _BYTE *v26; // [rsp+868h] [rbp+768h]
  _BYTE *v27; // [rsp+870h] [rbp+770h]

  v4 = *a1;
  v5 = 0;
  if ( *a1 && (*(_QWORD *)&v4[6].LockCount || (v4[1].SpinCount & 0x100) != 0) )
  {
    *a1 = 0;
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(v4);
      CoTaskMemFree(v4);
    }
  }
  if ( !*a1 )
  {
    v6 = (struct _RTL_CRITICAL_SECTION **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>,>(&pv);
    v7 = *v6;
    *v6 = 0;
    v8 = *a1;
    *a1 = v7;
    if ( v8 && _InterlockedExchangeAdd(&v8[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(v8);
      CoTaskMemFree(v8);
    }
    v9 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(v9);
      CoTaskMemFree(v9);
    }
  }
  v10 = *a1;
  v11 = *a1 + 5;
  EnterCriticalSection(v11);
  memset(v24, 0, sizeof(v24));
  v20 = 0;
  v21 = 0;
  v25 = &v22;
  v27 = &v24[2043];
  v22 = -2143256512;
  v23 = 0;
  v26 = v24;
  if ( (v10[1].SpinCount & 0x800) != 0 )
    v5 = tip2::details::shared_data<1,0,0>::serialize_data(&v10->LockCount, &v20, 1);
  LockSemaphore_high = HIDWORD(v10->LockSemaphore);
  DebugInfo = (char)v10[1].DebugInfo;
  LockSemaphore = (unsigned int)v10->LockSemaphore;
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_20;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestCreate");
  `TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_20:
    LOBYTE(v12) = DebugInfo;
    ProcAddress = (FARPROC)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, ULONG_PTR *))ProcAddress)(
                             LockSemaphore,
                             0,
                             v12,
                             LockSemaphore_high,
                             v5,
                             &v10[3].SpinCount);
  }
  else
  {
    *(_OWORD *)&v10[3].SpinCount = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(
    &v10[6].LockCount,
    ProcAddress);
  LODWORD(v10[4].SpinCount) = 1;
  *a2 = *(_OWORD *)&v10[3].SpinCount;
  if ( v20 )
    CoTaskMemFree(v20);
  if ( v11 )
    LeaveCriticalSection(v11);
  return a2;
}

```

## disassembly

```asm
0x18000d988  mov     [rsp-8+arg_10], rbx
0x18000d98d  push    rbp
0x18000d98e  push    rsi
0x18000d98f  push    rdi
0x18000d990  push    r12
0x18000d992  push    r13
0x18000d994  push    r14
0x18000d996  push    r15
0x18000d998  lea     rbp, [rsp-790h]
0x18000d9a0  sub     rsp, 890h
0x18000d9a7  mov     rax, cs:__security_cookie
0x18000d9ae  xor     rax, rsp
0x18000d9b1  mov     [rbp+7C0h+var_40], rax
0x18000d9b8  mov     r15, rdx
0x18000d9bb  mov     rdi, rcx
0x18000d9be  mov     rbx, [rcx]
0x18000d9c1  or      esi, 0FFFFFFFFh
0x18000d9c4  xor     r12d, r12d
0x18000d9c7  test    rbx, rbx
0x18000d9ca  jz      short loc_18000DA00
0x18000d9cc  cmp     [rbx+0F8h], r12
0x18000d9d3  jnz     short loc_18000D9DE
0x18000d9d5  test    dword ptr [rbx+48h], 100h
0x18000d9dc  jz      short loc_18000DA00
0x18000d9de  mov     [rcx], r12
0x18000d9e1  mov     eax, esi
0x18000d9e3  lock xadd [rbx+120h], eax
0x18000d9eb  add     eax, esi
0x18000d9ed  jnz     short loc_18000DA00
0x18000d9ef  mov     rcx, rbx
0x18000d9f2  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000d9f7  mov     rcx, rbx; pv
0x18000d9fa  call    cs:__imp_CoTaskMemFree
0x18000da00  cmp     [rdi], r12
0x18000da03  jnz     short loc_18000DA68
0x18000da05  lea     rcx, [rsp+8C0h+pv]
0x18000da0a  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>,>(void)
0x18000da0f  mov     rdx, [rax]
0x18000da12  mov     [rax], r12
0x18000da15  mov     rbx, [rdi]
0x18000da18  mov     [rdi], rdx
0x18000da1b  test    rbx, rbx
0x18000da1e  jz      short loc_18000DA3F
0x18000da20  mov     eax, esi
0x18000da22  lock xadd [rbx+120h], eax
0x18000da2a  add     eax, esi
0x18000da2c  jnz     short loc_18000DA3F
0x18000da2e  mov     rcx, rbx
0x18000da31  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000da36  mov     rcx, rbx; pv
0x18000da39  call    cs:__imp_CoTaskMemFree
0x18000da3f  mov     rbx, [rsp+8C0h+pv]
0x18000da44  test    rbx, rbx
0x18000da47  jz      short loc_18000DA68
0x18000da49  mov     eax, esi
0x18000da4b  lock xadd [rbx+120h], eax
0x18000da53  add     eax, esi
0x18000da55  jnz     short loc_18000DA68
0x18000da57  mov     rcx, rbx
0x18000da5a  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000da5f  mov     rcx, rbx; pv
0x18000da62  call    cs:__imp_CoTaskMemFree
0x18000da68  mov     rbx, [rdi]
0x18000da6b  lea     rsi, [rbx+0C8h]
0x18000da72  mov     rcx, rsi; lpCriticalSection
0x18000da75  call    cs:__imp_EnterCriticalSection
0x18000da7b  xor     edx, edx; Val
0x18000da7d  mov     r8d, 802h; Size
0x18000da83  lea     rcx, [rsp+8C0h+var_862]; void *
0x18000da88  call    memset
0x18000da8d  mov     [rsp+8C0h+var_870], r12
0x18000da92  mov     [rsp+8C0h+var_868], r12b
0x18000da97  lea     rax, [rsp+8C0h+var_867]
0x18000da9c  mov     [rbp+7C0h+var_60], rax
0x18000daa3  lea     rax, [rbp+7C0h+var_67]
0x18000daaa  mov     [rbp+7C0h+var_50], rax
0x18000dab1  mov     [rsp+8C0h+var_867], 80408040h
0x18000dab9  mov     [rsp+8C0h+var_863], r12b
0x18000dabe  lea     rax, [rsp+8C0h+var_862]
0x18000dac3  mov     [rbp+7C0h+var_58], rax
0x18000daca  test    dword ptr [rbx+48h], 800h
0x18000dad1  jz      short loc_18000DAEA
0x18000dad3  mov     r8d, 1
0x18000dad9  lea     rdx, [rsp+8C0h+var_870]
0x18000dade  lea     rcx, [rbx+8]
0x18000dae2  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18000dae7  mov     r12, rax
0x18000daea  lea     r14, [rbx+98h]
0x18000daf1  mov     r13d, [rbx+1Ch]
0x18000daf5  mov     al, [rbx+28h]
0x18000daf8  mov     [rsp+8C0h+var_880], al
0x18000dafc  mov     eax, [rbx+18h]
0x18000daff  mov     [rsp+8C0h+var_87C], eax
0x18000db03  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18000db0a  test    rax, rax
0x18000db0d  jnz     short loc_18000DB55
0x18000db0f  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000db16  test    rax, rax
0x18000db19  jnz     short loc_18000DB2F
0x18000db1b  lea     rcx, ModuleName; "kernelbase.dll"
0x18000db22  call    cs:__imp_GetModuleHandleW
0x18000db28  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000db2f  lea     rdx, aTestcreate; "TestCreate"
0x18000db36  mov     rcx, rax; hModule
0x18000db39  call    cs:__imp_GetProcAddress
0x18000db3f  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18000db46  test    rax, rax
0x18000db49  jnz     short loc_18000DB55
0x18000db4b  xorps   xmm0, xmm0
0x18000db4e  movdqu  xmmword ptr [r14], xmm0
0x18000db53  jmp     short loc_18000DB72
0x18000db55  mov     [rsp+8C0h+var_898], r14
0x18000db5a  mov     [rsp+8C0h+var_8A0], r12
0x18000db5f  mov     r9d, r13d
0x18000db62  mov     r8b, [rsp+8C0h+var_880]
0x18000db67  xor     edx, edx
0x18000db69  mov     ecx, [rsp+8C0h+var_87C]
0x18000db6d  call    _guard_dispatch_icall
0x18000db72  lea     rcx, [rbx+0F8h]
0x18000db79  mov     rdx, rax
0x18000db7c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18000db81  mov     dword ptr [rbx+0C0h], 1
0x18000db8b  movups  xmm0, xmmword ptr [rbx+98h]
0x18000db92  movdqu  xmmword ptr [r15], xmm0
0x18000db97  mov     rcx, [rsp+8C0h+var_870]; pv
0x18000db9c  test    rcx, rcx
0x18000db9f  jz      short loc_18000DBA7
0x18000dba1  call    cs:__imp_CoTaskMemFree
0x18000dba7  test    rsi, rsi
0x18000dbaa  jz      short loc_18000DBB5
0x18000dbac  mov     rcx, rsi; lpCriticalSection
0x18000dbaf  call    cs:__imp_LeaveCriticalSection
0x18000dbb5  mov     rax, r15
0x18000dbb8  mov     rcx, [rbp+7C0h+var_40]
0x18000dbbf  xor     rcx, rsp; StackCookie
0x18000dbc2  call    __security_check_cookie
0x18000dbc7  mov     rbx, [rsp+8C0h+arg_10]
0x18000dbcf  add     rsp, 890h
0x18000dbd6  pop     r15
0x18000dbd8  pop     r14
0x18000dbda  pop     r13
0x18000dbdc  pop     r12
0x18000dbde  pop     rdi
0x18000dbdf  pop     rsi
0x18000dbe0  pop     rbp
0x18000dbe1  retn
```
