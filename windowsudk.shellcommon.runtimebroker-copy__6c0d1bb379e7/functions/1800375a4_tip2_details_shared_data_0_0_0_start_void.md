# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x1800375a4`
- end: `0x1800377aa`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `518`
- prototype: ``
- caller_count: `15`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003d48`
- `0x180003e98`
- `0x180004780`
- `0x1800351c4`
- `0x180036798`
- `0x180036b98`
- `0x180037328`
- `0x180037500`
- `0x18006df80`
- `0x1800b9014`
- `0x1800cdc78`
- `0x1800ea988`
- `0x1802a2028`
- `0x180420ea8`
- `0x18042e98c`

## callees

- `0x1800375a4`
- `0x18004f234`
- `0x18004f258`
- `0x18006ccd8`
- `0x18015cb00`
- `0x18015d868`
- `0x1802a23fc`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800376a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800376a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003768b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003768b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037718`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037718`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800375e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800375e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003770a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003770a`

## string_xrefs

- `0x180037698`: `TestCreate`
- `0x180037684`: `kernelbase.dll`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  __int64 v5; // r8
  bool v6; // al
  _OWORD *v7; // rsi
  __int64 v8; // r15
  unsigned int v9; // edi
  char v10; // r13
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v13; // r15
  __int64 v14; // rdi
  _DWORD v16[4]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+59h] [rbp-A7h] BYREF
  char v20; // [rsp+5Dh] [rbp-A3h]
  _BYTE v21[2043]; // [rsp+5Eh] [rbp-A2h] BYREF
  char v22; // [rsp+859h] [rbp+759h] BYREF
  int *v23; // [rsp+860h] [rbp+760h]
  _BYTE *v24; // [rsp+868h] [rbp+768h]
  char *v25; // [rsp+870h] [rbp+770h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  memset_0(v21, 0, 0x802u);
  pv = 0;
  v18 = 0;
  v23 = &v19;
  v25 = &v22;
  v19 = -2143256512;
  v20 = 0;
  v24 = v21;
  v6 = (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0;
  v7 = (_OWORD *)(a1 + 144);
  if ( v6 )
    v8 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
  else
    v8 = 0;
  v9 = *(_DWORD *)(a1 + 20);
  v10 = *(_BYTE *)(a1 + 32);
  v16[0] = *(_DWORD *)(a1 + 16);
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
    LOBYTE(v5) = v10;
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v16[0],
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
    wil::last_error_context::last_error_context((wil::last_error_context *)v16);
    TestClose(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v16);
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
0x1800375a4  mov     [rsp-8+arg_10], rbx
0x1800375a9  push    rbp
0x1800375aa  push    rsi
0x1800375ab  push    rdi
0x1800375ac  push    r12
0x1800375ae  push    r13
0x1800375b0  push    r14
0x1800375b2  push    r15
0x1800375b4  lea     rbp, [rsp-790h]
0x1800375bc  sub     rsp, 890h
0x1800375c3  mov     rax, cs:__security_cookie
0x1800375ca  xor     rax, rsp
0x1800375cd  mov     [rbp+7C0h+var_40], rax
0x1800375d4  mov     r12, rdx
0x1800375d7  mov     rbx, rcx
0x1800375da  lea     r14, [rcx+0C0h]
0x1800375e1  mov     rcx, r14; lpCriticalSection
0x1800375e4  call    cs:__imp_EnterCriticalSection
0x1800375ea  xor     edx, edx; Val
0x1800375ec  mov     r8d, 802h; Size
0x1800375f2  lea     rcx, [rsp+8C0h+var_862]; void *
0x1800375f7  call    memset_0
0x1800375fc  mov     [rsp+8C0h+pv], 0
0x180037605  mov     [rsp+8C0h+var_868], 0
0x18003760a  lea     rax, [rsp+8C0h+var_867]
0x18003760f  mov     [rbp+7C0h+var_60], rax
0x180037616  lea     rax, [rbp+7C0h+var_67]
0x18003761d  mov     [rbp+7C0h+var_50], rax
0x180037624  mov     [rsp+8C0h+var_867], 80408040h
0x18003762c  mov     [rsp+8C0h+var_863], 0
0x180037631  lea     rax, [rsp+8C0h+var_862]
0x180037636  mov     [rbp+7C0h+var_58], rax
0x18003763d  test    dword ptr [rbx+40h], 800h
0x180037644  jnz     loc_18003774B
0x18003764a  xor     al, al
0x18003764c  lea     rsi, [rbx+90h]
0x180037653  test    al, al
0x180037655  jnz     loc_18003775F
0x18003765b  xor     r15d, r15d
0x18003765e  mov     edi, [rbx+14h]
0x180037661  mov     r13b, [rbx+20h]
0x180037665  mov     eax, [rbx+10h]
0x180037668  mov     [rsp+8C0h+var_880], eax
0x18003766c  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180037673  test    rax, rax
0x180037676  jnz     short loc_1800376B8
0x180037678  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18003767f  test    rax, rax
0x180037682  jnz     short loc_180037698
0x180037684  lea     rcx, ModuleName; "kernelbase.dll"
0x18003768b  call    cs:__imp_GetModuleHandleW
0x180037691  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180037698  lea     rdx, ProcName; "TestCreate"
0x18003769f  mov     rcx, rax; hModule
0x1800376a2  call    cs:__imp_GetProcAddress
0x1800376a8  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800376af  test    rax, rax
0x1800376b2  jz      loc_18003777A
0x1800376b8  mov     [rsp+8C0h+var_898], rsi
0x1800376bd  mov     [rsp+8C0h+var_8A0], r15
0x1800376c2  mov     r9d, edi
0x1800376c5  mov     r8b, r13b
0x1800376c8  xor     edx, edx
0x1800376ca  mov     ecx, [rsp+8C0h+var_880]
0x1800376ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376d3  mov     r15, rax
0x1800376d6  mov     rdi, [rbx+0F0h]
0x1800376dd  test    rdi, rdi
0x1800376e0  jnz     loc_180037789
0x1800376e6  mov     [rbx+0F0h], r15
0x1800376ed  mov     dword ptr [rbx+0B8h], 1
0x1800376f7  movups  xmm0, xmmword ptr [rsi]
0x1800376fa  movdqu  xmmword ptr [r12], xmm0
0x180037700  mov     rcx, [rsp+8C0h+pv]; pv
0x180037705  test    rcx, rcx
0x180037708  jz      short loc_180037710
0x18003770a  call    cs:__imp_CoTaskMemFree
0x180037710  test    r14, r14
0x180037713  jz      short loc_18003771E
0x180037715  mov     rcx, r14; lpCriticalSection
0x180037718  call    cs:__imp_LeaveCriticalSection
0x18003771e  mov     rax, r12
0x180037721  mov     rcx, [rbp+7C0h+var_40]
0x180037728  xor     rcx, rsp; StackCookie
0x18003772b  call    __security_check_cookie
0x180037730  mov     rbx, [rsp+8C0h+arg_10]
0x180037738  add     rsp, 890h
0x18003773f  pop     r15
0x180037741  pop     r14
0x180037743  pop     r13
0x180037745  pop     r12
0x180037747  pop     rdi
0x180037748  pop     rsi
0x180037749  pop     rbp
0x18003774a  retn
0x18003774b  test    dword ptr [rbx+14h], 8000h
0x180037752  jnz     loc_18003764A
0x180037758  mov     al, 1
0x18003775a  jmp     loc_18003764C
0x18003775f  mov     r8d, 1
0x180037765  lea     rdx, [rsp+8C0h+pv]
0x18003776a  mov     rcx, rbx
0x18003776d  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180037772  mov     r15, rax
0x180037775  jmp     loc_18003765E
0x18003777a  xorps   xmm0, xmm0
0x18003777d  movdqu  xmmword ptr [rsi], xmm0
0x180037781  xor     r15d, r15d
0x180037784  jmp     loc_1800376D6
0x180037789  lea     rcx, [rsp+8C0h+var_880]; this
0x18003778e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180037793  mov     rcx, rdi
0x180037796  call    TestClose
0x18003779b  lea     rcx, [rsp+8C0h+var_880]; this
0x1800377a0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800377a5  jmp     loc_1800376E6
```
