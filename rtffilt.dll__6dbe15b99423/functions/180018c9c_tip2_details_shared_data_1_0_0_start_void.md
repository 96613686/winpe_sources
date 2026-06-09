# tip2::details::shared_data<1,0,0>::start(void)

- ea: `0x180018c9c`
- end: `0x180018ea4`
- name: `?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `520`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010b80`
- `0x180010f28`

## callees

- `0x180001e40`
- `0x1800189d8`
- `0x180018c9c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018d7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018e04`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018d7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018e04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018d92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018e1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018d92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018e1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018e71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018e71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018cdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018cdc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e63`

## string_xrefs

- `0x180018d74`: `kernelbase.dll`
- `0x180018dfd`: `kernelbase.dll`
- `0x180018d88`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<1,0,0>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  __int64 v5; // r8
  _OWORD *v6; // r12
  __int64 v7; // rsi
  unsigned int v8; // r15d
  char v9; // r13
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v12; // r13
  __int64 v13; // rsi
  DWORD LastError; // r15d
  FARPROC v15; // rax
  HMODULE v16; // rax
  unsigned int v18; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+59h] [rbp-A7h] BYREF
  char v22; // [rsp+5Dh] [rbp-A3h]
  char v23; // [rsp+5Eh] [rbp-A2h] BYREF
  char v24; // [rsp+859h] [rbp+759h] BYREF
  int *v25; // [rsp+860h] [rbp+760h]
  char *v26; // [rsp+868h] [rbp+768h]
  char *v27; // [rsp+870h] [rbp+770h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  pv = 0;
  v20 = 0;
  v25 = &v21;
  v27 = &v24;
  v21 = -2143256512;
  v22 = 0;
  v26 = &v23;
  v6 = (_OWORD *)(a1 + 144);
  if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
    v7 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &pv, 1);
  else
    v7 = 0;
  v8 = *(_DWORD *)(a1 + 20);
  v9 = *(_BYTE *)(a1 + 32);
  v18 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_9;
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
LABEL_9:
    LOBYTE(v5) = v9;
    v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v18,
            0,
            v5,
            v8,
            v7,
            a1 + 144);
  }
  else
  {
    *v6 = 0;
    v12 = 0;
  }
  v13 = *(_QWORD *)(a1 + 240);
  if ( v13 )
  {
    LastError = GetLastError();
    v15 = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_15;
    v16 = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      v16 = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = v16;
    }
    v15 = GetProcAddress(v16, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)v15;
    if ( v15 )
LABEL_15:
      ((void (__fastcall *)(__int64))v15)(v13);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 240) = v12;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v6;
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 )
    LeaveCriticalSection(v4);
  return a2;
}

```

## disassembly

```asm
0x180018c9c  mov     [rsp-8+arg_10], rbx
0x180018ca1  push    rbp
0x180018ca2  push    rsi
0x180018ca3  push    rdi
0x180018ca4  push    r12
0x180018ca6  push    r13
0x180018ca8  push    r14
0x180018caa  push    r15
0x180018cac  lea     rbp, [rsp-790h]
0x180018cb4  sub     rsp, 890h
0x180018cbb  mov     rax, cs:__security_cookie
0x180018cc2  xor     rax, rsp
0x180018cc5  mov     [rbp+7C0h+var_40], rax
0x180018ccc  mov     r14, rdx
0x180018ccf  mov     rbx, rcx
0x180018cd2  lea     rdi, [rcx+0C0h]
0x180018cd9  mov     rcx, rdi; lpCriticalSection
0x180018cdc  call    cs:__imp_EnterCriticalSection
0x180018ce2  mov     [rsp+8C0h+pv], 0
0x180018ceb  mov     [rsp+8C0h+var_868], 0
0x180018cf0  lea     rax, [rsp+8C0h+var_867]
0x180018cf5  mov     [rbp+7C0h+var_60], rax
0x180018cfc  lea     rax, [rbp+7C0h+var_67]
0x180018d03  mov     [rbp+7C0h+var_50], rax
0x180018d0a  mov     [rsp+8C0h+var_867], 80408040h
0x180018d12  mov     [rsp+8C0h+var_863], 0
0x180018d17  lea     rax, [rsp+8C0h+var_862]
0x180018d1c  mov     [rbp+7C0h+var_58], rax
0x180018d23  lea     r12, [rbx+90h]
0x180018d2a  test    dword ptr [rbx+40h], 800h
0x180018d31  jz      short loc_180018D4B
0x180018d33  mov     r8d, 1
0x180018d39  lea     rdx, [rsp+8C0h+pv]
0x180018d3e  mov     rcx, rbx
0x180018d41  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180018d46  mov     rsi, rax
0x180018d49  jmp     short loc_180018D4D
0x180018d4b  xor     esi, esi
0x180018d4d  mov     r15d, [rbx+14h]
0x180018d51  mov     r13b, [rbx+20h]
0x180018d55  mov     eax, [rbx+10h]
0x180018d58  mov     [rsp+8C0h+var_880], eax
0x180018d5c  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180018d63  test    rax, rax
0x180018d66  jnz     short loc_180018DB2
0x180018d68  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180018d6f  test    rax, rax
0x180018d72  jnz     short loc_180018D88
0x180018d74  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180018d7b  call    cs:__imp_GetModuleHandleW
0x180018d81  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180018d88  lea     rdx, aTestcreate; "TestCreate"
0x180018d8f  mov     rcx, rax; hModule
0x180018d92  call    cs:__imp_GetProcAddress
0x180018d98  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180018d9f  test    rax, rax
0x180018da2  jnz     short loc_180018DB2
0x180018da4  xorps   xmm0, xmm0
0x180018da7  movdqu  xmmword ptr [r12], xmm0
0x180018dad  xor     r13d, r13d
0x180018db0  jmp     short loc_180018DD0
0x180018db2  mov     [rsp+8C0h+var_898], r12
0x180018db7  mov     [rsp+8C0h+var_8A0], rsi
0x180018dbc  mov     r9d, r15d
0x180018dbf  mov     r8b, r13b
0x180018dc2  xor     edx, edx
0x180018dc4  mov     ecx, [rsp+8C0h+var_880]
0x180018dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dcd  mov     r13, rax
0x180018dd0  mov     rsi, [rbx+0F0h]
0x180018dd7  test    rsi, rsi
0x180018dda  jz      short loc_180018E3E
0x180018ddc  call    cs:__imp_GetLastError
0x180018de2  mov     r15d, eax
0x180018de5  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180018dec  test    rax, rax
0x180018def  jnz     short loc_180018E2D
0x180018df1  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180018df8  test    rax, rax
0x180018dfb  jnz     short loc_180018E11
0x180018dfd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180018e04  call    cs:__imp_GetModuleHandleW
0x180018e0a  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180018e11  lea     rdx, aTestclose; "TestClose"
0x180018e18  mov     rcx, rax; hModule
0x180018e1b  call    cs:__imp_GetProcAddress
0x180018e21  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180018e28  test    rax, rax
0x180018e2b  jz      short loc_180018E35
0x180018e2d  mov     rcx, rsi
0x180018e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e35  mov     ecx, r15d; dwErrCode
0x180018e38  call    cs:__imp_SetLastError
0x180018e3e  mov     [rbx+0F0h], r13
0x180018e45  mov     dword ptr [rbx+0B8h], 1
0x180018e4f  movups  xmm0, xmmword ptr [r12]
0x180018e54  movdqu  xmmword ptr [r14], xmm0
0x180018e59  mov     rcx, [rsp+8C0h+pv]; pv
0x180018e5e  test    rcx, rcx
0x180018e61  jz      short loc_180018E69
0x180018e63  call    cs:__imp_CoTaskMemFree
0x180018e69  test    rdi, rdi
0x180018e6c  jz      short loc_180018E77
0x180018e6e  mov     rcx, rdi; lpCriticalSection
0x180018e71  call    cs:__imp_LeaveCriticalSection
0x180018e77  mov     rax, r14
0x180018e7a  mov     rcx, [rbp+7C0h+var_40]
0x180018e81  xor     rcx, rsp; StackCookie
0x180018e84  call    __security_check_cookie
0x180018e89  mov     rbx, [rsp+8C0h+arg_10]
0x180018e91  add     rsp, 890h
0x180018e98  pop     r15
0x180018e9a  pop     r14
0x180018e9c  pop     r13
0x180018e9e  pop     r12
0x180018ea0  pop     rdi
0x180018ea1  pop     rsi
0x180018ea2  pop     rbp
0x180018ea3  retn
```
