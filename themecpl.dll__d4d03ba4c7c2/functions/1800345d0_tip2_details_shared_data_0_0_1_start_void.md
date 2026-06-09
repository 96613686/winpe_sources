# tip2::details::shared_data<0,0,1>::start(void)

- ea: `0x1800345d0`
- end: `0x1800347ca`
- name: `?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f458`

## callees

- `0x180002280`
- `0x180034340`
- `0x1800345d0`
- `0x180034df0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800346e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800346e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800346c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800346c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034790`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034610`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034610`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003474b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003474b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003477c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003477c`

## string_xrefs

- `0x1800346c0`: `kernelbase.dll`
- `0x1800346da`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,1>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  __int64 v5; // r8
  bool v6; // al
  _OWORD *v7; // r15
  __int64 v8; // rsi
  unsigned int v9; // ebx
  char v10; // r12
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v13; // r12
  __int64 v14; // rsi
  DWORD LastError; // ebx
  unsigned int v17; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+59h] [rbp-A7h] BYREF
  char v21; // [rsp+5Dh] [rbp-A3h]
  char v22; // [rsp+5Eh] [rbp-A2h] BYREF
  char v23; // [rsp+859h] [rbp+759h] BYREF
  int *v24; // [rsp+860h] [rbp+760h]
  char *v25; // [rsp+868h] [rbp+768h]
  char *v26; // [rsp+870h] [rbp+770h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  pv = 0;
  v19 = 0;
  v24 = &v20;
  v26 = &v23;
  v20 = -2143256512;
  v21 = 0;
  v25 = &v22;
  v6 = (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0;
  v7 = (_OWORD *)(a1 + 144);
  if ( v6 )
    v8 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, 1);
  else
    v8 = 0;
  v9 = *(_DWORD *)(a1 + 20);
  v10 = *(_BYTE *)(a1 + 32);
  v17 = *(_DWORD *)(a1 + 16);
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
            v17,
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
    TestClose(v14);
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
0x1800345d0  mov     [rsp-8+arg_10], rbx
0x1800345d5  push    rbp
0x1800345d6  push    rsi
0x1800345d7  push    rdi
0x1800345d8  push    r12
0x1800345da  push    r13
0x1800345dc  push    r14
0x1800345de  push    r15
0x1800345e0  lea     rbp, [rsp-790h]
0x1800345e8  sub     rsp, 890h
0x1800345ef  mov     rax, cs:__security_cookie
0x1800345f6  xor     rax, rsp
0x1800345f9  mov     [rbp+7C0h+var_40], rax
0x180034600  mov     r13, rdx
0x180034603  mov     rdi, rcx
0x180034606  lea     r14, [rcx+0C0h]
0x18003460d  mov     rcx, r14; lpCriticalSection
0x180034610  call    cs:__imp_EnterCriticalSection
0x180034617  nop     dword ptr [rax+rax+00h]
0x18003461c  mov     [rsp+8C0h+pv], 0
0x180034625  mov     [rsp+8C0h+var_868], 0
0x18003462a  lea     rax, [rsp+8C0h+var_867]
0x18003462f  mov     [rbp+7C0h+var_60], rax
0x180034636  lea     rax, [rbp+7C0h+var_67]
0x18003463d  mov     [rbp+7C0h+var_50], rax
0x180034644  mov     [rsp+8C0h+var_867], 80408040h
0x18003464c  mov     [rsp+8C0h+var_863], 0
0x180034651  lea     rax, [rsp+8C0h+var_862]
0x180034656  mov     [rbp+7C0h+var_58], rax
0x18003465d  test    dword ptr [rdi+40h], 800h
0x180034664  jz      short loc_180034673
0x180034666  test    dword ptr [rdi+14h], 8000h
0x18003466d  jnz     short loc_180034673
0x18003466f  mov     al, 1
0x180034671  jmp     short loc_180034675
0x180034673  xor     al, al
0x180034675  lea     r15, [rdi+90h]
0x18003467c  test    al, al
0x18003467e  jz      short loc_180034698
0x180034680  mov     r8d, 1
0x180034686  lea     rdx, [rsp+8C0h+pv]
0x18003468b  mov     rcx, rdi
0x18003468e  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180034693  mov     rsi, rax
0x180034696  jmp     short loc_18003469A
0x180034698  xor     esi, esi
0x18003469a  mov     ebx, [rdi+14h]
0x18003469d  mov     r12b, [rdi+20h]
0x1800346a1  mov     eax, [rdi+10h]
0x1800346a4  mov     [rsp+8C0h+var_880], eax
0x1800346a8  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800346af  test    rax, rax
0x1800346b2  jnz     short loc_180034709
0x1800346b4  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800346bb  test    rax, rax
0x1800346be  jnz     short loc_1800346DA
0x1800346c0  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800346c7  call    cs:__imp_GetModuleHandleW
0x1800346ce  nop     dword ptr [rax+rax+00h]
0x1800346d3  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800346da  lea     rdx, aTestcreate; "TestCreate"
0x1800346e1  mov     rcx, rax; hModule
0x1800346e4  call    cs:__imp_GetProcAddress
0x1800346eb  nop     dword ptr [rax+rax+00h]
0x1800346f0  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800346f7  test    rax, rax
0x1800346fa  jnz     short loc_180034709
0x1800346fc  xorps   xmm0, xmm0
0x1800346ff  movdqu  xmmword ptr [r15], xmm0
0x180034704  xor     r12d, r12d
0x180034707  jmp     short loc_180034727
0x180034709  mov     [rsp+8C0h+var_898], r15
0x18003470e  mov     [rsp+8C0h+var_8A0], rsi
0x180034713  mov     r9d, ebx
0x180034716  mov     r8b, r12b
0x180034719  xor     edx, edx
0x18003471b  mov     ecx, [rsp+8C0h+var_880]
0x18003471f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034724  mov     r12, rax
0x180034727  mov     rsi, [rdi+0F0h]
0x18003472e  test    rsi, rsi
0x180034731  jz      short loc_180034757
0x180034733  call    cs:__imp_GetLastError
0x18003473a  nop     dword ptr [rax+rax+00h]
0x18003473f  mov     ebx, eax
0x180034741  mov     rcx, rsi
0x180034744  call    TestClose
0x180034749  mov     ecx, ebx; dwErrCode
0x18003474b  call    cs:__imp_SetLastError
0x180034752  nop     dword ptr [rax+rax+00h]
0x180034757  mov     [rdi+0F0h], r12
0x18003475e  mov     dword ptr [rdi+0B8h], 1
0x180034768  movups  xmm0, xmmword ptr [r15]
0x18003476c  movdqu  xmmword ptr [r13+0], xmm0
0x180034772  mov     rcx, [rsp+8C0h+pv]; pv
0x180034777  test    rcx, rcx
0x18003477a  jz      short loc_180034788
0x18003477c  call    cs:__imp_CoTaskMemFree
0x180034783  nop     dword ptr [rax+rax+00h]
0x180034788  test    r14, r14
0x18003478b  jz      short loc_18003479C
0x18003478d  mov     rcx, r14; lpCriticalSection
0x180034790  call    cs:__imp_LeaveCriticalSection
0x180034797  nop     dword ptr [rax+rax+00h]
0x18003479c  mov     rax, r13
0x18003479f  mov     rcx, [rbp+7C0h+var_40]
0x1800347a6  xor     rcx, rsp; StackCookie
0x1800347a9  call    __security_check_cookie
0x1800347ae  mov     rbx, [rsp+8C0h+arg_10]
0x1800347b6  add     rsp, 890h
0x1800347bd  pop     r15
0x1800347bf  pop     r14
0x1800347c1  pop     r13
0x1800347c3  pop     r12
0x1800347c5  pop     rdi
0x1800347c6  pop     rsi
0x1800347c7  pop     rbp
0x1800347c8  retn
```
