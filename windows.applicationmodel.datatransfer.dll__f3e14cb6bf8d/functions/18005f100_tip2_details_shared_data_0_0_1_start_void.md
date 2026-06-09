# tip2::details::shared_data<0,0,1>::start(void)

- ea: `0x18005f100`
- end: `0x18005f31a`
- name: `?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011810`

## callees

- `0x180002ad0`
- `0x18005ee70`
- `0x18005f100`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f2e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f2e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f140`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f140`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f209`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f291`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f209`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f291`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f1f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f27a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f1f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f27a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f2ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f2d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f2d9`

## string_xrefs

- `0x18005f1eb`: `kernelbase.dll`
- `0x18005f273`: `kernelbase.dll`
- `0x18005f1ff`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,1>::start(__int64 a1, _OWORD *a2)
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
    v8 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, 1);
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
0x18005f100  mov     [rsp-8+arg_10], rbx
0x18005f105  push    rbp
0x18005f106  push    rsi
0x18005f107  push    rdi
0x18005f108  push    r12
0x18005f10a  push    r13
0x18005f10c  push    r14
0x18005f10e  push    r15
0x18005f110  lea     rbp, [rsp-790h]
0x18005f118  sub     rsp, 890h
0x18005f11f  mov     rax, cs:__security_cookie
0x18005f126  xor     rax, rsp
0x18005f129  mov     [rbp+7C0h+var_40], rax
0x18005f130  mov     r13, rdx
0x18005f133  mov     rbx, rcx
0x18005f136  lea     rsi, [rcx+0C0h]
0x18005f13d  mov     rcx, rsi; lpCriticalSection
0x18005f140  call    cs:__imp_EnterCriticalSection
0x18005f146  mov     [rsp+8C0h+pv], 0
0x18005f14f  mov     [rsp+8C0h+var_868], 0
0x18005f154  lea     rax, [rsp+8C0h+var_867]
0x18005f159  mov     [rbp+7C0h+var_60], rax
0x18005f160  lea     rax, [rbp+7C0h+var_67]
0x18005f167  mov     [rbp+7C0h+var_50], rax
0x18005f16e  mov     [rsp+8C0h+var_867], 80408040h
0x18005f176  mov     [rsp+8C0h+var_863], 0
0x18005f17b  lea     rax, [rsp+8C0h+var_862]
0x18005f180  mov     [rbp+7C0h+var_58], rax
0x18005f187  test    dword ptr [rbx+40h], 800h
0x18005f18e  jz      short loc_18005F19D
0x18005f190  test    dword ptr [rbx+14h], 8000h
0x18005f197  jnz     short loc_18005F19D
0x18005f199  mov     al, 1
0x18005f19b  jmp     short loc_18005F19F
0x18005f19d  xor     al, al
0x18005f19f  lea     r14, [rbx+90h]
0x18005f1a6  test    al, al
0x18005f1a8  jz      short loc_18005F1C2
0x18005f1aa  mov     r8d, 1
0x18005f1b0  lea     rdx, [rsp+8C0h+pv]
0x18005f1b5  mov     rcx, rbx
0x18005f1b8  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18005f1bd  mov     r15, rax
0x18005f1c0  jmp     short loc_18005F1C5
0x18005f1c2  xor     r15d, r15d
0x18005f1c5  mov     edi, [rbx+14h]
0x18005f1c8  mov     r12b, [rbx+20h]
0x18005f1cc  mov     eax, [rbx+10h]
0x18005f1cf  mov     [rsp+8C0h+var_880], eax
0x18005f1d3  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18005f1da  test    rax, rax
0x18005f1dd  jnz     short loc_18005F228
0x18005f1df  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18005f1e6  test    rax, rax
0x18005f1e9  jnz     short loc_18005F1FF
0x18005f1eb  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18005f1f2  call    cs:__imp_GetModuleHandleW
0x18005f1f8  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18005f1ff  lea     rdx, aTestcreate; "TestCreate"
0x18005f206  mov     rcx, rax; hModule
0x18005f209  call    cs:__imp_GetProcAddress
0x18005f20f  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18005f216  test    rax, rax
0x18005f219  jnz     short loc_18005F228
0x18005f21b  xorps   xmm0, xmm0
0x18005f21e  movdqu  xmmword ptr [r14], xmm0
0x18005f223  xor     r12d, r12d
0x18005f226  jmp     short loc_18005F246
0x18005f228  mov     [rsp+8C0h+var_898], r14
0x18005f22d  mov     [rsp+8C0h+var_8A0], r15
0x18005f232  mov     r9d, edi
0x18005f235  mov     r8b, r12b
0x18005f238  xor     edx, edx
0x18005f23a  mov     ecx, [rsp+8C0h+var_880]
0x18005f23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f243  mov     r12, rax
0x18005f246  mov     rdi, [rbx+0F0h]
0x18005f24d  test    rdi, rdi
0x18005f250  jz      short loc_18005F2B4
0x18005f252  call    cs:__imp_GetLastError
0x18005f258  mov     r15d, eax
0x18005f25b  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18005f262  test    rax, rax
0x18005f265  jnz     short loc_18005F2A3
0x18005f267  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18005f26e  test    rax, rax
0x18005f271  jnz     short loc_18005F287
0x18005f273  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18005f27a  call    cs:__imp_GetModuleHandleW
0x18005f280  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18005f287  lea     rdx, aTestclose; "TestClose"
0x18005f28e  mov     rcx, rax; hModule
0x18005f291  call    cs:__imp_GetProcAddress
0x18005f297  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18005f29e  test    rax, rax
0x18005f2a1  jz      short loc_18005F2AB
0x18005f2a3  mov     rcx, rdi
0x18005f2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2ab  mov     ecx, r15d; dwErrCode
0x18005f2ae  call    cs:__imp_SetLastError
0x18005f2b4  mov     [rbx+0F0h], r12
0x18005f2bb  mov     dword ptr [rbx+0B8h], 1
0x18005f2c5  movups  xmm0, xmmword ptr [r14]
0x18005f2c9  movdqu  xmmword ptr [r13+0], xmm0
0x18005f2cf  mov     rcx, [rsp+8C0h+pv]; pv
0x18005f2d4  test    rcx, rcx
0x18005f2d7  jz      short loc_18005F2DF
0x18005f2d9  call    cs:__imp_CoTaskMemFree
0x18005f2df  test    rsi, rsi
0x18005f2e2  jz      short loc_18005F2ED
0x18005f2e4  mov     rcx, rsi; lpCriticalSection
0x18005f2e7  call    cs:__imp_LeaveCriticalSection
0x18005f2ed  mov     rax, r13
0x18005f2f0  mov     rcx, [rbp+7C0h+var_40]
0x18005f2f7  xor     rcx, rsp; StackCookie
0x18005f2fa  call    __security_check_cookie
0x18005f2ff  mov     rbx, [rsp+8C0h+arg_10]
0x18005f307  add     rsp, 890h
0x18005f30e  pop     r15
0x18005f310  pop     r14
0x18005f312  pop     r13
0x18005f314  pop     r12
0x18005f316  pop     rdi
0x18005f317  pop     rsi
0x18005f318  pop     rbp
0x18005f319  retn
```
