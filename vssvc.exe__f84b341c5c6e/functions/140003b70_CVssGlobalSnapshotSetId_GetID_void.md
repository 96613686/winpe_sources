# CVssGlobalSnapshotSetId::GetID(void)

- ea: `0x140003b70`
- end: `0x140003d76`
- name: `?GetID@CVssGlobalSnapshotSetId@@SA?AU_GUID@@XZ`
- size: `518`
- prototype: `struct _GUID *__fastcall(struct _GUID *__return_ptr __struct_ptr retstr)`
- caller_count: `19`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003320`
- `0x14002e39c`
- `0x14003f1ec`
- `0x140042688`
- `0x1400437e0`
- `0x140044d60`
- `0x14004500c`
- `0x1400550f4`
- `0x1400553b0`
- `0x140056798`
- `0x140056be8`
- `0x1400718a0`
- `0x140079cf8`
- `0x14009b8a8`
- `0x1400a347c`
- `0x1400a57d4`
- `0x1400a5c18`
- `0x1400a60fc`
- `0x1400a6f44`

## callees

- `0x140003b70`
- `0x140011440`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015950`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140003c10`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140003c10`
- `VssTrace!__imp_VssTraceMessage` at `0x140003d6b`
- `VssTrace!__imp_VssTraceMessage` at `0x140003d6b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140003d04`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140003d04`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140003c54`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140003c54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003cee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _GUID *__fastcall CVssGlobalSnapshotSetId::GetID(struct _GUID *__return_ptr retstr)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 i; // rbx
  void *v5; // rcx
  int v7; // eax
  unsigned __int64 v8; // [rsp+50h] [rbp-B0h] BYREF
  int v9; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v10; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v11; // [rsp+68h] [rbp-98h]
  unsigned int v12; // [rsp+70h] [rbp-90h]
  int v13; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v14; // [rsp+78h] [rbp-88h]
  unsigned int v15; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  int v17; // [rsp+88h] [rbp-78h]
  __int128 v18; // [rsp+90h] [rbp-70h]
  __int128 v19; // [rsp+A0h] [rbp-60h]
  __int64 v20; // [rsp+B0h] [rbp-50h]
  LPCRITICAL_SECTION v21; // [rsp+C0h] [rbp-40h] BYREF
  char v22; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v23; // [rsp+D0h] [rbp-30h]
  const wchar_t *v24; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v25; // [rsp+E0h] [rbp-20h]
  int v26; // [rsp+E8h] [rbp-18h]
  int v27; // [rsp+ECh] [rbp-14h]
  int v28; // [rsp+F0h] [rbp-10h]
  LPVOID pv[15]; // [rsp+F8h] [rbp-8h] BYREF
  int v30; // [rsp+170h] [rbp+70h]
  __int64 v31; // [rsp+1B0h] [rbp+B0h] BYREF

  v21 = &g_SnapshotSetCS;
  v23 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v24 = L"CVssAutomaticLock2::CVssAutomaticLock2";
  v25 = L"INCTYPEH";
  v26 = 256;
  v27 = 11;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v9 = 0;
  v14 = L"CVssAutomaticLock2::CVssAutomaticLock2";
  v10 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v11 = L"INCTYPEH";
  v12 = 256;
  v13 = 11;
  TickCount = GetTickCount();
  v17 = 255;
  v8 = 0xFFFFFFFF00000000uLL;
  v20 = 0;
  v18 = 0;
  v19 = 0;
  v31 = 0;
  if ( (int)VssGetTracingContextPerThread(&v31) >= 0 )
  {
    v7 = VssSetTracingContextPerThread(&v8);
    v2 = v20;
    if ( v7 >= 0 )
      v2 = v31;
    v20 = v2;
  }
  else
  {
    v2 = v20;
  }
  if ( v2 )
    v15 = *(_DWORD *)(v2 + 48) + 1;
  else
    v15 = 0;
  v3 = 160;
  if ( v17 != 255 )
    v3 = v17;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v8) )
    VssTraceMessage(v10, v11, v12, v15, v13, v14, L"ENTER", v3, 0);
  if ( HIBYTE(v30) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v5 = pv[i];
      if ( v5 )
      {
        CoTaskMemFree(v5);
        pv[i] = 0;
      }
    }
  }
  CVssCriticalSection::Lock(&g_SnapshotSetCS);
  v22 = 1;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v8);
  *retstr = CVssGlobalSnapshotSetId::m_SnapshotSetID;
  CVssAutomaticLock2::~CVssAutomaticLock2(&v21);
  return retstr;
}

```

## disassembly

```asm
0x140003b70  push    rbp
0x140003b72  push    rbx
0x140003b73  push    rdi
0x140003b74  push    r15
0x140003b76  lea     rbp, [rsp-88h]
0x140003b7e  sub     rsp, 188h
0x140003b85  mov     rdi, rcx
0x140003b88  lea     r15, ?g_SnapshotSetCS@@3VCVssCriticalSection@@A; CVssCriticalSection g_SnapshotSetCS
0x140003b8f  mov     [rbp+0A0h+var_E0], r15
0x140003b93  lea     rax, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x140003b9a  mov     [rbp+0A0h+var_D0], rax
0x140003b9e  lea     rax, aCvssautomaticl_0; "CVssAutomaticLock2::CVssAutomaticLock2"
0x140003ba5  mov     [rbp+0A0h+var_C8], rax
0x140003ba9  lea     rax, aInctypeh; "INCTYPEH"
0x140003bb0  mov     [rbp+0A0h+var_C0], rax
0x140003bb4  mov     [rbp+0A0h+var_B8], 100h
0x140003bbb  mov     [rbp+0A0h+var_B4], 0Bh
0x140003bc2  mov     [rbp+0A0h+var_B0], 0FFh
0x140003bc9  mov     [rbp+0A0h+var_30], 1000000h
0x140003bd0  xor     edx, edx; Val
0x140003bd2  lea     r8d, [rdx+78h]; Size
0x140003bd6  lea     rcx, [rbp+0A0h+pv]; void *
0x140003bda  call    memset_0
0x140003bdf  mov     [rsp+1A0h+var_148], 0
0x140003be7  mov     rax, [rbp+0A0h+var_C8]
0x140003beb  mov     [rsp+1A0h+var_128], rax
0x140003bf0  mov     rax, [rbp+0A0h+var_D0]
0x140003bf4  mov     [rsp+1A0h+var_140], rax
0x140003bf9  mov     rax, [rbp+0A0h+var_C0]
0x140003bfd  mov     [rsp+1A0h+var_138], rax
0x140003c02  mov     eax, [rbp+0A0h+var_B8]
0x140003c05  mov     [rsp+1A0h+var_130], eax
0x140003c09  mov     eax, [rbp+0A0h+var_B4]
0x140003c0c  mov     [rsp+1A0h+var_12C], eax
0x140003c10  call    cs:__imp_GetTickCount
0x140003c16  mov     [rbp+0A0h+var_11C], eax
0x140003c19  mov     [rsp+1A0h+var_14C], 0FFFFFFFFh
0x140003c21  mov     eax, [rbp+0A0h+var_B0]
0x140003c24  mov     [rbp+0A0h+var_118], eax
0x140003c27  mov     [rsp+1A0h+var_150], 0
0x140003c2f  mov     [rbp+0A0h+var_F0], 0
0x140003c37  xorps   xmm0, xmm0
0x140003c3a  movups  [rbp+0A0h+var_110], xmm0
0x140003c3e  movups  [rbp+0A0h+var_100], xmm0
0x140003c42  mov     [rbp+0A0h+arg_0], 0
0x140003c4d  lea     rcx, [rbp+0A0h+arg_0]
0x140003c54  call    cs:__imp_VssGetTracingContextPerThread
0x140003c5a  test    eax, eax
0x140003c5c  jns     loc_140003CFF
0x140003c62  mov     rcx, [rbp+0A0h+var_F0]
0x140003c66  test    rcx, rcx
0x140003c69  jz      loc_140003D21
0x140003c6f  mov     eax, [rcx+30h]
0x140003c72  inc     eax
0x140003c74  mov     [rbp+0A0h+var_120], eax
0x140003c77  mov     ebx, 0A0h
0x140003c7c  cmp     [rbp+0A0h+var_118], 0FFh
0x140003c83  cmovnz  ebx, [rbp+0A0h+var_118]
0x140003c87  lea     rcx, [rsp+1A0h+var_150]; this
0x140003c8c  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140003c91  test    eax, eax
0x140003c93  jnz     loc_140003D2D
0x140003c99  cmp     byte ptr [rbp+0A0h+var_30+3], 0
0x140003c9d  jz      short loc_140003CB4
0x140003c9f  xor     ebx, ebx
0x140003ca1  mov     rcx, [rbp+rbx*8+0A0h+pv]; pv
0x140003ca6  test    rcx, rcx
0x140003ca9  jnz     short loc_140003CEE
0x140003cab  inc     rbx
0x140003cae  cmp     rbx, 0Fh
0x140003cb2  jnz     short loc_140003CA1
0x140003cb4  mov     rcx, r15; lpCriticalSection
0x140003cb7  call    ?Lock@CVssCriticalSection@@QEAAXXZ; CVssCriticalSection::Lock(void)
0x140003cbc  mov     [rbp+0A0h+var_D8], 1
0x140003cc0  lea     rcx, [rsp+1A0h+var_150]; this
0x140003cc5  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140003cca  movups  xmm0, xmmword ptr cs:?m_SnapshotSetID@CVssGlobalSnapshotSetId@@0U_GUID@@A.Data1; _GUID CVssGlobalSnapshotSetId::m_SnapshotSetID ...
0x140003cd1  movdqu  xmmword ptr [rdi], xmm0
0x140003cd5  lea     rcx, [rbp+0A0h+var_E0]; this
0x140003cd9  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x140003cde  mov     rax, rdi
0x140003ce1  add     rsp, 188h
0x140003ce8  pop     r15
0x140003cea  pop     rdi
0x140003ceb  pop     rbx
0x140003cec  pop     rbp
0x140003ced  retn
0x140003cee  call    cs:__imp_CoTaskMemFree
0x140003cf4  mov     [rbp+rbx*8+0A0h+pv], 0
0x140003cfd  jmp     short loc_140003CAB
0x140003cff  lea     rcx, [rsp+1A0h+var_150]
0x140003d04  call    cs:__imp_VssSetTracingContextPerThread
0x140003d0a  mov     rcx, [rbp+0A0h+var_F0]
0x140003d0e  test    eax, eax
0x140003d10  cmovns  rcx, [rbp+0A0h+arg_0]
0x140003d18  mov     [rbp+0A0h+var_F0], rcx
0x140003d1c  jmp     loc_140003C66
0x140003d21  mov     [rbp+0A0h+var_120], 0
0x140003d28  jmp     loc_140003C77
0x140003d2d  mov     [rsp+1A0h+var_160], 0
0x140003d36  mov     [rsp+1A0h+var_168], ebx
0x140003d3a  lea     rax, aEnter; "ENTER"
0x140003d41  mov     [rsp+1A0h+var_170], rax
0x140003d46  mov     rax, [rsp+1A0h+var_128]
0x140003d4b  mov     [rsp+1A0h+var_178], rax
0x140003d50  mov     eax, [rsp+1A0h+var_12C]
0x140003d54  mov     [rsp+1A0h+var_180], eax
0x140003d58  mov     r9d, [rbp+0A0h+var_120]
0x140003d5c  mov     r8d, [rsp+1A0h+var_130]
0x140003d61  mov     rdx, [rsp+1A0h+var_138]
0x140003d66  mov     rcx, [rsp+1A0h+var_140]
0x140003d6b  call    cs:__imp_VssTraceMessage
0x140003d71  jmp     loc_140003C99
```
