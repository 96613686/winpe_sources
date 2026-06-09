# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x14001e940`
- end: `0x14001eb5a`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000ecbc`

## callees

- `0x140005530`
- `0x14001e67c`
- `0x14001e940`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001ea49`
- `KERNEL32!GetProcAddress` at `0x14001ead1`
- `KERNEL32!GetProcAddress` at `0x14001ea49`
- `KERNEL32!GetProcAddress` at `0x14001ead1`
- `KERNEL32!GetModuleHandleW` at `0x14001ea32`
- `KERNEL32!GetModuleHandleW` at `0x14001eaba`
- `KERNEL32!GetModuleHandleW` at `0x14001ea32`
- `KERNEL32!GetModuleHandleW` at `0x14001eaba`
- `KERNEL32!GetLastError` at `0x14001ea92`
- `KERNEL32!GetLastError` at `0x14001ea92`
- `KERNEL32!LeaveCriticalSection` at `0x14001eb27`
- `KERNEL32!LeaveCriticalSection` at `0x14001eb27`
- `KERNEL32!EnterCriticalSection` at `0x14001e980`
- `KERNEL32!EnterCriticalSection` at `0x14001e980`
- `KERNEL32!SetLastError` at `0x14001eaee`
- `KERNEL32!SetLastError` at `0x14001eaee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001eb19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001eb19`

## string_xrefs

- `0x14001ea2b`: `kernelbase.dll`
- `0x14001eab3`: `kernelbase.dll`
- `0x14001ea3f`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // r8
  bool v6; // al
  _OWORD *v7; // r14
  __int64 v8; // r15
  unsigned int v9; // edi
  char v10; // r12
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v13; // r12
  __int64 v14; // rdi
  DWORD LastError; // r15d
  FARPROC v16; // rax
  HMODULE v17; // rax
  unsigned int v19; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+59h] [rbp-A7h] BYREF
  char v23; // [rsp+5Dh] [rbp-A3h]
  char v24; // [rsp+5Eh] [rbp-A2h] BYREF
  char v25; // [rsp+859h] [rbp+759h] BYREF
  int *v26; // [rsp+860h] [rbp+760h]
  char *v27; // [rsp+868h] [rbp+768h]
  char *v28; // [rsp+870h] [rbp+770h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  pv = 0;
  v21 = 0;
  v26 = &v22;
  v28 = &v25;
  v22 = -2143256512;
  v23 = 0;
  v27 = &v24;
  v6 = (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0;
  v7 = (_OWORD *)(a1 + 144);
  if ( v6 )
    v8 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
  else
    v8 = 0;
  v9 = *(_DWORD *)(a1 + 20);
  v10 = *(_BYTE *)(a1 + 32);
  v19 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_13;
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
LABEL_13:
    LOBYTE(v5) = v10;
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v19,
            0,
            v5,
            v9,
            v8,
            a1 + 144);
  }
  else
  {
    *v7 = 0;
    v13 = 0;
  }
  v14 = *(_QWORD *)(a1 + 240);
  if ( v14 )
  {
    LastError = GetLastError();
    v16 = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_19;
    v17 = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      v17 = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = v17;
    }
    v16 = GetProcAddress(v17, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)v16;
    if ( v16 )
LABEL_19:
      ((void (__fastcall *)(__int64))v16)(v14);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 240) = v13;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v7;
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 )
    LeaveCriticalSection(v4);
  return a2;
}

```

## disassembly

```asm
0x14001e940  mov     [rsp-8+arg_10], rbx
0x14001e945  push    rbp
0x14001e946  push    rsi
0x14001e947  push    rdi
0x14001e948  push    r12
0x14001e94a  push    r13
0x14001e94c  push    r14
0x14001e94e  push    r15
0x14001e950  lea     rbp, [rsp-790h]
0x14001e958  sub     rsp, 890h
0x14001e95f  mov     rax, cs:__security_cookie
0x14001e966  xor     rax, rsp
0x14001e969  mov     [rbp+7C0h+var_40], rax
0x14001e970  mov     r13, rdx
0x14001e973  mov     rbx, rcx
0x14001e976  lea     rsi, [rcx+0C0h]
0x14001e97d  mov     rcx, rsi; lpCriticalSection
0x14001e980  call    cs:__imp_EnterCriticalSection
0x14001e986  mov     [rsp+8C0h+pv], 0
0x14001e98f  mov     [rsp+8C0h+var_868], 0
0x14001e994  lea     rax, [rsp+8C0h+var_867]
0x14001e999  mov     [rbp+7C0h+var_60], rax
0x14001e9a0  lea     rax, [rbp+7C0h+var_67]
0x14001e9a7  mov     [rbp+7C0h+var_50], rax
0x14001e9ae  mov     [rsp+8C0h+var_867], 80408040h
0x14001e9b6  mov     [rsp+8C0h+var_863], 0
0x14001e9bb  lea     rax, [rsp+8C0h+var_862]
0x14001e9c0  mov     [rbp+7C0h+var_58], rax
0x14001e9c7  test    dword ptr [rbx+40h], 800h
0x14001e9ce  jz      short loc_14001E9DD
0x14001e9d0  test    dword ptr [rbx+14h], 8000h
0x14001e9d7  jnz     short loc_14001E9DD
0x14001e9d9  mov     al, 1
0x14001e9db  jmp     short loc_14001E9DF
0x14001e9dd  xor     al, al
0x14001e9df  lea     r14, [rbx+90h]
0x14001e9e6  test    al, al
0x14001e9e8  jz      short loc_14001EA02
0x14001e9ea  mov     r8d, 1
0x14001e9f0  lea     rdx, [rsp+8C0h+pv]
0x14001e9f5  mov     rcx, rbx
0x14001e9f8  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14001e9fd  mov     r15, rax
0x14001ea00  jmp     short loc_14001EA05
0x14001ea02  xor     r15d, r15d
0x14001ea05  mov     edi, [rbx+14h]
0x14001ea08  mov     r12b, [rbx+20h]
0x14001ea0c  mov     eax, [rbx+10h]
0x14001ea0f  mov     [rsp+8C0h+var_880], eax
0x14001ea13  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14001ea1a  test    rax, rax
0x14001ea1d  jnz     short loc_14001EA68
0x14001ea1f  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x14001ea26  test    rax, rax
0x14001ea29  jnz     short loc_14001EA3F
0x14001ea2b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001ea32  call    cs:__imp_GetModuleHandleW
0x14001ea38  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14001ea3f  lea     rdx, aTestcreate; "TestCreate"
0x14001ea46  mov     rcx, rax; hModule
0x14001ea49  call    cs:__imp_GetProcAddress
0x14001ea4f  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14001ea56  test    rax, rax
0x14001ea59  jnz     short loc_14001EA68
0x14001ea5b  xorps   xmm0, xmm0
0x14001ea5e  movdqu  xmmword ptr [r14], xmm0
0x14001ea63  xor     r12d, r12d
0x14001ea66  jmp     short loc_14001EA86
0x14001ea68  mov     [rsp+8C0h+var_898], r14
0x14001ea6d  mov     [rsp+8C0h+var_8A0], r15
0x14001ea72  mov     r9d, edi
0x14001ea75  mov     r8b, r12b
0x14001ea78  xor     edx, edx
0x14001ea7a  mov     ecx, [rsp+8C0h+var_880]
0x14001ea7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ea83  mov     r12, rax
0x14001ea86  mov     rdi, [rbx+0F0h]
0x14001ea8d  test    rdi, rdi
0x14001ea90  jz      short loc_14001EAF4
0x14001ea92  call    cs:__imp_GetLastError
0x14001ea98  mov     r15d, eax
0x14001ea9b  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x14001eaa2  test    rax, rax
0x14001eaa5  jnz     short loc_14001EAE3
0x14001eaa7  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x14001eaae  test    rax, rax
0x14001eab1  jnz     short loc_14001EAC7
0x14001eab3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001eaba  call    cs:__imp_GetModuleHandleW
0x14001eac0  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14001eac7  lea     rdx, aTestclose; "TestClose"
0x14001eace  mov     rcx, rax; hModule
0x14001ead1  call    cs:__imp_GetProcAddress
0x14001ead7  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x14001eade  test    rax, rax
0x14001eae1  jz      short loc_14001EAEB
0x14001eae3  mov     rcx, rdi
0x14001eae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eaeb  mov     ecx, r15d; dwErrCode
0x14001eaee  call    cs:__imp_SetLastError
0x14001eaf4  mov     [rbx+0F0h], r12
0x14001eafb  mov     dword ptr [rbx+0B8h], 1
0x14001eb05  movups  xmm0, xmmword ptr [r14]
0x14001eb09  movdqu  xmmword ptr [r13+0], xmm0
0x14001eb0f  mov     rcx, [rsp+8C0h+pv]; pv
0x14001eb14  test    rcx, rcx
0x14001eb17  jz      short loc_14001EB1F
0x14001eb19  call    cs:__imp_CoTaskMemFree
0x14001eb1f  test    rsi, rsi
0x14001eb22  jz      short loc_14001EB2D
0x14001eb24  mov     rcx, rsi; lpCriticalSection
0x14001eb27  call    cs:__imp_LeaveCriticalSection
0x14001eb2d  mov     rax, r13
0x14001eb30  mov     rcx, [rbp+7C0h+var_40]
0x14001eb37  xor     rcx, rsp; StackCookie
0x14001eb3a  call    __security_check_cookie
0x14001eb3f  mov     rbx, [rsp+8C0h+arg_10]
0x14001eb47  add     rsp, 890h
0x14001eb4e  pop     r15
0x14001eb50  pop     r14
0x14001eb52  pop     r13
0x14001eb54  pop     r12
0x14001eb56  pop     rdi
0x14001eb57  pop     rsi
0x14001eb58  pop     rbp
0x14001eb59  retn
```
