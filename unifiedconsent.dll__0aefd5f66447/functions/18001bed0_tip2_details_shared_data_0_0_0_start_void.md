# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x18001bed0`
- end: `0x18001c0ea`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: ``
- caller_count: `15`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012870`
- `0x180021124`
- `0x1800254a8`
- `0x1800264c0`
- `0x180029504`
- `0x18002aae0`
- `0x1800334a0`
- `0x180036900`
- `0x180041410`
- `0x180052980`
- `0x18005fe6c`
- `0x18005ff6c`
- `0x18006006c`
- `0x1800685c8`
- `0x18006cad0`

## callees

- `0x180002810`
- `0x18001bc0c`
- `0x18001bed0`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c0a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c0a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bfd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c061`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bfd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c061`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bfc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c04a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bfc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c04a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c0b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c0b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c022`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c07e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c07e`

## string_xrefs

- `0x18001bfbb`: `kernelbase.dll`
- `0x18001c043`: `kernelbase.dll`
- `0x18001bfcf`: `TestCreate`

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
0x18001bed0  mov     [rsp-8+arg_10], rbx
0x18001bed5  push    rbp
0x18001bed6  push    rsi
0x18001bed7  push    rdi
0x18001bed8  push    r12
0x18001beda  push    r13
0x18001bedc  push    r14
0x18001bede  push    r15
0x18001bee0  lea     rbp, [rsp-790h]
0x18001bee8  sub     rsp, 890h
0x18001beef  mov     rax, cs:__security_cookie
0x18001bef6  xor     rax, rsp
0x18001bef9  mov     [rbp+7C0h+var_40], rax
0x18001bf00  mov     r13, rdx
0x18001bf03  mov     rbx, rcx
0x18001bf06  lea     rsi, [rcx+0C0h]
0x18001bf0d  mov     rcx, rsi; lpCriticalSection
0x18001bf10  call    cs:__imp_EnterCriticalSection
0x18001bf16  mov     [rsp+8C0h+pv], 0
0x18001bf1f  mov     [rsp+8C0h+var_868], 0
0x18001bf24  lea     rax, [rsp+8C0h+var_867]
0x18001bf29  mov     [rbp+7C0h+var_60], rax
0x18001bf30  lea     rax, [rbp+7C0h+var_67]
0x18001bf37  mov     [rbp+7C0h+var_50], rax
0x18001bf3e  mov     [rsp+8C0h+var_867], 80408040h
0x18001bf46  mov     [rsp+8C0h+var_863], 0
0x18001bf4b  lea     rax, [rsp+8C0h+var_862]
0x18001bf50  mov     [rbp+7C0h+var_58], rax
0x18001bf57  test    dword ptr [rbx+40h], 800h
0x18001bf5e  jz      short loc_18001BF6D
0x18001bf60  test    dword ptr [rbx+14h], 8000h
0x18001bf67  jnz     short loc_18001BF6D
0x18001bf69  mov     al, 1
0x18001bf6b  jmp     short loc_18001BF6F
0x18001bf6d  xor     al, al
0x18001bf6f  lea     r14, [rbx+90h]
0x18001bf76  test    al, al
0x18001bf78  jz      short loc_18001BF92
0x18001bf7a  mov     r8d, 1
0x18001bf80  lea     rdx, [rsp+8C0h+pv]
0x18001bf85  mov     rcx, rbx
0x18001bf88  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18001bf8d  mov     r15, rax
0x18001bf90  jmp     short loc_18001BF95
0x18001bf92  xor     r15d, r15d
0x18001bf95  mov     edi, [rbx+14h]
0x18001bf98  mov     r12b, [rbx+20h]
0x18001bf9c  mov     eax, [rbx+10h]
0x18001bf9f  mov     [rsp+8C0h+var_880], eax
0x18001bfa3  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18001bfaa  test    rax, rax
0x18001bfad  jnz     short loc_18001BFF8
0x18001bfaf  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001bfb6  test    rax, rax
0x18001bfb9  jnz     short loc_18001BFCF
0x18001bfbb  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001bfc2  call    cs:__imp_GetModuleHandleW
0x18001bfc8  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001bfcf  lea     rdx, aTestcreate; "TestCreate"
0x18001bfd6  mov     rcx, rax; hModule
0x18001bfd9  call    cs:__imp_GetProcAddress
0x18001bfdf  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18001bfe6  test    rax, rax
0x18001bfe9  jnz     short loc_18001BFF8
0x18001bfeb  xorps   xmm0, xmm0
0x18001bfee  movdqu  xmmword ptr [r14], xmm0
0x18001bff3  xor     r12d, r12d
0x18001bff6  jmp     short loc_18001C016
0x18001bff8  mov     [rsp+8C0h+var_898], r14
0x18001bffd  mov     [rsp+8C0h+var_8A0], r15
0x18001c002  mov     r9d, edi
0x18001c005  mov     r8b, r12b
0x18001c008  xor     edx, edx
0x18001c00a  mov     ecx, [rsp+8C0h+var_880]
0x18001c00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c013  mov     r12, rax
0x18001c016  mov     rdi, [rbx+0F0h]
0x18001c01d  test    rdi, rdi
0x18001c020  jz      short loc_18001C084
0x18001c022  call    cs:__imp_GetLastError
0x18001c028  mov     r15d, eax
0x18001c02b  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18001c032  test    rax, rax
0x18001c035  jnz     short loc_18001C073
0x18001c037  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001c03e  test    rax, rax
0x18001c041  jnz     short loc_18001C057
0x18001c043  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001c04a  call    cs:__imp_GetModuleHandleW
0x18001c050  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001c057  lea     rdx, aTestclose; "TestClose"
0x18001c05e  mov     rcx, rax; hModule
0x18001c061  call    cs:__imp_GetProcAddress
0x18001c067  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18001c06e  test    rax, rax
0x18001c071  jz      short loc_18001C07B
0x18001c073  mov     rcx, rdi
0x18001c076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c07b  mov     ecx, r15d; dwErrCode
0x18001c07e  call    cs:__imp_SetLastError
0x18001c084  mov     [rbx+0F0h], r12
0x18001c08b  mov     dword ptr [rbx+0B8h], 1
0x18001c095  movups  xmm0, xmmword ptr [r14]
0x18001c099  movdqu  xmmword ptr [r13+0], xmm0
0x18001c09f  mov     rcx, [rsp+8C0h+pv]; pv
0x18001c0a4  test    rcx, rcx
0x18001c0a7  jz      short loc_18001C0AF
0x18001c0a9  call    cs:__imp_CoTaskMemFree
0x18001c0af  test    rsi, rsi
0x18001c0b2  jz      short loc_18001C0BD
0x18001c0b4  mov     rcx, rsi; lpCriticalSection
0x18001c0b7  call    cs:__imp_LeaveCriticalSection
0x18001c0bd  mov     rax, r13
0x18001c0c0  mov     rcx, [rbp+7C0h+var_40]
0x18001c0c7  xor     rcx, rsp; StackCookie
0x18001c0ca  call    __security_check_cookie
0x18001c0cf  mov     rbx, [rsp+8C0h+arg_10]
0x18001c0d7  add     rsp, 890h
0x18001c0de  pop     r15
0x18001c0e0  pop     r14
0x18001c0e2  pop     r13
0x18001c0e4  pop     r12
0x18001c0e6  pop     rdi
0x18001c0e7  pop     rsi
0x18001c0e8  pop     rbp
0x18001c0e9  retn
```
