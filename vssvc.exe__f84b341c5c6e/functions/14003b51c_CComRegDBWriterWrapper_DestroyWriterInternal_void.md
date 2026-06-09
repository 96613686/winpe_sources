# CComRegDBWriterWrapper::DestroyWriterInternal(void)

- ea: `0x14003b51c`
- end: `0x14003b81d`
- name: `?DestroyWriterInternal@CComRegDBWriterWrapper@@IEAAXXZ`
- size: `769`
- prototype: `void __fastcall(CComRegDBWriterWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140037edc`

## callees

- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x14003b51c`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003b6d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003b6d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003b5c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003b5c4`
- `VssTrace!__imp_VssTraceMessage` at `0x14003b688`
- `VssTrace!__imp_VssTraceMessage` at `0x14003b688`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003b609`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003b609`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003b5fb`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003b5fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003b6a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003b6a1`

## string_xrefs

- `0x14003b540`: `base\stor\vss\modules\writers\comregdbwriter.cxx`
- `0x14003b54c`: `CComRegDBWriterWrapper::DestroyWriterInternal`
- `0x14003b6cd`: `DestroyComRegDBWriter`
- `0x14003b71a`: `DestroyComRegDBWriter could not be loaded.  No COM+ writer`
- `0x14003b7ea`: `The COM+ writer was not initialized on startup.  m_bCreated: %s`
- `0x14003b780`: `DestroyComRegDBWriter failed with hr 0x%08lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CComRegDBWriterWrapper::DestroyWriterInternal(CComRegDBWriterWrapper *this)
{
  struct CComRegDBWriterWrapper *v1; // rdi
  int v2; // eax
  CComRegDBWriterWrapper *v3; // rcx
  int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  char v7; // bl
  HMODULE v8; // rcx
  __int64 (*ProcAddress)(void); // rax
  int v10; // ebx
  const wchar_t *v11; // r9
  const wchar_t *v12; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v13; // [rsp+58h] [rbp-A8h]
  const wchar_t *v14; // [rsp+60h] [rbp-A0h]
  int v15; // [rsp+68h] [rbp-98h]
  int v16; // [rsp+6Ch] [rbp-94h]
  int v17; // [rsp+70h] [rbp-90h]
  LPVOID pv[15]; // [rsp+78h] [rbp-88h] BYREF
  int v19; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v20; // [rsp+100h] [rbp+0h] BYREF
  int v21; // [rsp+108h] [rbp+8h]
  const wchar_t *v22; // [rsp+110h] [rbp+10h]
  const wchar_t *v23; // [rsp+118h] [rbp+18h]
  unsigned int v24; // [rsp+120h] [rbp+20h]
  int v25; // [rsp+124h] [rbp+24h]
  const wchar_t *v26; // [rsp+128h] [rbp+28h]
  unsigned int v27; // [rsp+130h] [rbp+30h]
  DWORD TickCount; // [rsp+134h] [rbp+34h]
  int v29; // [rsp+138h] [rbp+38h]
  __int128 v30; // [rsp+140h] [rbp+40h]
  __int128 v31; // [rsp+150h] [rbp+50h]
  CComRegDBWriterWrapper *v32; // [rsp+160h] [rbp+60h]
  CComRegDBWriterWrapper *v33; // [rsp+1C0h] [rbp+C0h] BYREF

  v33 = this;
  v1 = CComRegDBWriterWrapper::sm_pWriter;
  v12 = L"base\\stor\\vss\\modules\\writers\\comregdbwriter.cxx";
  v13 = L"CComRegDBWriterWrapper::DestroyWriterInternal";
  v14 = L"WRTCDBRC";
  v15 = 87;
  v16 = 4;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v21 = 0;
  v26 = L"CComRegDBWriterWrapper::DestroyWriterInternal";
  v22 = L"base\\stor\\vss\\modules\\writers\\comregdbwriter.cxx";
  v23 = L"WRTCDBRC";
  v24 = 87;
  v25 = 4;
  TickCount = GetTickCount();
  v29 = 255;
  v20 = 0xFFFFFFFF00000000uLL;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  v33 = 0;
  if ( (int)VssGetTracingContextPerThread(&v33) < 0 )
  {
    v3 = v32;
  }
  else
  {
    v2 = VssSetTracingContextPerThread(&v20);
    v3 = v32;
    if ( v2 >= 0 )
      v3 = v33;
    v32 = v3;
  }
  if ( v3 )
    v27 = *((_DWORD *)v3 + 12) + 1;
  else
    v27 = 0;
  v4 = 160;
  if ( v29 != 255 )
    v4 = v29;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v20) )
    VssTraceMessage(v22, v23, v24, v27, v25, v26, L"ENTER", v4, 0);
  if ( HIBYTE(v19) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v6 = pv[i];
      if ( v6 )
      {
        CoTaskMemFree(v6);
        pv[i] = 0;
      }
    }
  }
  v7 = *((_BYTE *)v1 + 24);
  if ( v7 && (v8 = (HMODULE)*((_QWORD *)v1 + 2)) != 0 )
  {
    ProcAddress = GetProcAddress(v8, "DestroyComRegDBWriter");
    if ( ProcAddress )
    {
      v10 = ProcAddress();
      v21 = v10;
      if ( v10 < 0 )
      {
        v12 = L"base\\stor\\vss\\modules\\writers\\comregdbwriter.cxx";
        v13 = L"CComRegDBWriterWrapper::DestroyWriterInternal";
        v14 = L"WRTCDBRC";
        v15 = 105;
        v16 = 4;
        v17 = 255;
        v19 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        CVssFunctionTracer::Trace(&v20, &v12, L"DestroyComRegDBWriter failed with hr 0x%08lx", (unsigned int)v10);
      }
      *((_BYTE *)v1 + 24) = 0;
    }
    else
    {
      v12 = L"base\\stor\\vss\\modules\\writers\\comregdbwriter.cxx";
      v13 = L"CComRegDBWriterWrapper::DestroyWriterInternal";
      v14 = L"WRTCDBRC";
      v15 = 99;
      v16 = 4;
      v17 = 255;
      v19 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      CVssFunctionTracer::Trace(&v20, &v12, L"DestroyComRegDBWriter could not be loaded.  No COM+ writer");
    }
  }
  else
  {
    v12 = L"base\\stor\\vss\\modules\\writers\\comregdbwriter.cxx";
    v13 = L"CComRegDBWriterWrapper::DestroyWriterInternal";
    v14 = L"WRTCDBRC";
    v15 = 91;
    v16 = 4;
    v17 = 255;
    v19 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    v11 = L"TRUE";
    if ( !v7 )
      v11 = L"FALSE";
    CVssFunctionTracer::Trace(&v20, &v12, L"The COM+ writer was not initialized on startup.  m_bCreated: %s", v11);
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v20);
}

```

## disassembly

```asm
0x14003b51c  mov     [rsp-8+arg_0], rcx
0x14003b521  push    rbp
0x14003b522  push    rbx
0x14003b523  push    rsi
0x14003b524  push    rdi
0x14003b525  push    r12
0x14003b527  push    r13
0x14003b529  push    r14
0x14003b52b  push    r15
0x14003b52d  lea     rbp, [rsp-78h]
0x14003b532  sub     rsp, 178h
0x14003b539  mov     rdi, cs:?sm_pWriter@CComRegDBWriterWrapper@@0PEAV1@EA; CComRegDBWriterWrapper * CComRegDBWriterWrapper::sm_pWriter
0x14003b540  lea     r15, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\writers\\comr"...
0x14003b547  mov     [rsp+1B0h+var_160], r15
0x14003b54c  lea     r12, aCcomregdbwrite_1; "CComRegDBWriterWrapper::DestroyWriterIn"...
0x14003b553  mov     [rsp+1B0h+var_158], r12
0x14003b558  lea     r13, aWrtcdbrc; "WRTCDBRC"
0x14003b55f  mov     [rsp+1B0h+var_150], r13
0x14003b564  mov     [rsp+1B0h+var_148], 57h ; 'W'
0x14003b56c  mov     [rsp+1B0h+var_144], 4
0x14003b574  mov     r14d, 0FFh
0x14003b57a  mov     [rsp+1B0h+var_140], r14d
0x14003b57f  xor     esi, esi
0x14003b581  mov     [rbp+0B0h+var_C0], 1000000h
0x14003b588  xor     edx, edx; Val
0x14003b58a  lea     r8d, [rsi+78h]; Size
0x14003b58e  lea     rcx, [rsp+1B0h+pv]; void *
0x14003b593  call    memset_0
0x14003b598  mov     [rbp+0B0h+var_A8], esi
0x14003b59b  mov     rax, [rsp+1B0h+var_158]
0x14003b5a0  mov     [rbp+0B0h+var_88], rax
0x14003b5a4  mov     rax, [rsp+1B0h+var_160]
0x14003b5a9  mov     [rbp+0B0h+var_A0], rax
0x14003b5ad  mov     rax, [rsp+1B0h+var_150]
0x14003b5b2  mov     [rbp+0B0h+var_98], rax
0x14003b5b6  mov     eax, [rsp+1B0h+var_148]
0x14003b5ba  mov     [rbp+0B0h+var_90], eax
0x14003b5bd  mov     eax, [rsp+1B0h+var_144]
0x14003b5c1  mov     [rbp+0B0h+var_8C], eax
0x14003b5c4  call    cs:__imp_GetTickCount
0x14003b5ca  mov     [rbp+0B0h+var_7C], eax
0x14003b5cd  mov     [rbp+0B0h+var_AC], 0FFFFFFFFh
0x14003b5d4  mov     eax, [rsp+1B0h+var_140]
0x14003b5d8  mov     [rbp+0B0h+var_78], eax
0x14003b5db  mov     [rbp+0B0h+var_B0], esi
0x14003b5de  mov     [rbp+0B0h+var_50], rsi
0x14003b5e2  xorps   xmm0, xmm0
0x14003b5e5  movups  [rbp+0B0h+var_70], xmm0
0x14003b5e9  movups  [rbp+0B0h+var_60], xmm0
0x14003b5ed  mov     [rbp+0B0h+arg_0], rsi
0x14003b5f4  lea     rcx, [rbp+0B0h+arg_0]
0x14003b5fb  call    cs:__imp_VssGetTracingContextPerThread
0x14003b601  test    eax, eax
0x14003b603  js      short loc_14003B623
0x14003b605  lea     rcx, [rbp+0B0h+var_B0]
0x14003b609  call    cs:__imp_VssSetTracingContextPerThread
0x14003b60f  mov     rcx, [rbp+0B0h+var_50]
0x14003b613  test    eax, eax
0x14003b615  cmovns  rcx, [rbp+0B0h+arg_0]
0x14003b61d  mov     [rbp+0B0h+var_50], rcx
0x14003b621  jmp     short loc_14003B627
0x14003b623  mov     rcx, [rbp+0B0h+var_50]
0x14003b627  test    rcx, rcx
0x14003b62a  jz      short loc_14003B636
0x14003b62c  mov     eax, [rcx+30h]
0x14003b62f  inc     eax
0x14003b631  mov     [rbp+0B0h+var_80], eax
0x14003b634  jmp     short loc_14003B639
0x14003b636  mov     [rbp+0B0h+var_80], esi
0x14003b639  mov     ebx, 0A0h
0x14003b63e  cmp     [rbp+0B0h+var_78], r14d
0x14003b642  cmovnz  ebx, [rbp+0B0h+var_78]
0x14003b646  lea     rcx, [rbp+0B0h+var_B0]; this
0x14003b64a  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003b64f  test    eax, eax
0x14003b651  jz      short loc_14003B68E
0x14003b653  mov     [rsp+1B0h+var_170], rsi
0x14003b658  mov     [rsp+1B0h+var_178], ebx
0x14003b65c  lea     rax, aEnter; "ENTER"
0x14003b663  mov     [rsp+1B0h+var_180], rax
0x14003b668  mov     rax, [rbp+0B0h+var_88]
0x14003b66c  mov     [rsp+1B0h+var_188], rax
0x14003b671  mov     eax, [rbp+0B0h+var_8C]
0x14003b674  mov     [rsp+1B0h+var_190], eax
0x14003b678  mov     r9d, [rbp+0B0h+var_80]
0x14003b67c  mov     r8d, [rbp+0B0h+var_90]
0x14003b680  mov     rdx, [rbp+0B0h+var_98]
0x14003b684  mov     rcx, [rbp+0B0h+var_A0]
0x14003b688  call    cs:__imp_VssTraceMessage
0x14003b68e  cmp     byte ptr [rbp+0B0h+var_C0+3], sil
0x14003b692  jz      short loc_14003B6B5
0x14003b694  mov     rbx, rsi
0x14003b697  mov     rcx, [rsp+rbx*8+1B0h+pv]; pv
0x14003b69c  test    rcx, rcx
0x14003b69f  jz      short loc_14003B6AC
0x14003b6a1  call    cs:__imp_CoTaskMemFree
0x14003b6a7  mov     [rsp+rbx*8+1B0h+pv], rsi
0x14003b6ac  inc     rbx
0x14003b6af  cmp     rbx, 0Fh
0x14003b6b3  jnz     short loc_14003B697
0x14003b6b5  mov     bl, [rdi+18h]
0x14003b6b8  test    bl, bl
0x14003b6ba  jz      loc_14003B79B
0x14003b6c0  mov     rcx, [rdi+10h]; hModule
0x14003b6c4  test    rcx, rcx
0x14003b6c7  jz      loc_14003B79B
0x14003b6cd  lea     rdx, aDestroycomregd; "DestroyComRegDBWriter"
0x14003b6d4  call    cs:__imp_GetProcAddress
0x14003b6da  test    rax, rax
0x14003b6dd  jnz     short loc_14003B734
0x14003b6df  mov     [rsp+1B0h+var_160], r15
0x14003b6e4  mov     [rsp+1B0h+var_158], r12
0x14003b6e9  mov     [rsp+1B0h+var_150], r13
0x14003b6ee  mov     [rsp+1B0h+var_148], 63h ; 'c'
0x14003b6f6  mov     [rsp+1B0h+var_144], 4
0x14003b6fe  mov     [rsp+1B0h+var_140], r14d
0x14003b703  mov     [rbp+0B0h+var_C0], 1000000h
0x14003b70a  xor     edx, edx; Val
0x14003b70c  lea     r8d, [rax+78h]; Size
0x14003b710  lea     rcx, [rsp+1B0h+pv]; void *
0x14003b715  call    memset_0
0x14003b71a  lea     r8, aDestroycomregd_1; "DestroyComRegDBWriter could not be load"...
0x14003b721  lea     rdx, [rsp+1B0h+var_160]
0x14003b726  lea     rcx, [rbp+0B0h+var_B0]
0x14003b72a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003b72f  jmp     loc_14003B800
0x14003b734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b739  mov     ebx, eax
0x14003b73b  mov     [rbp+0B0h+var_A8], eax
0x14003b73e  test    eax, eax
0x14003b740  jns     short loc_14003B795
0x14003b742  mov     [rsp+1B0h+var_160], r15
0x14003b747  mov     [rsp+1B0h+var_158], r12
0x14003b74c  mov     [rsp+1B0h+var_150], r13
0x14003b751  mov     [rsp+1B0h+var_148], 69h ; 'i'
0x14003b759  mov     [rsp+1B0h+var_144], 4
0x14003b761  mov     [rsp+1B0h+var_140], r14d
0x14003b766  mov     [rbp+0B0h+var_C0], 1000000h
0x14003b76d  xor     edx, edx; Val
0x14003b76f  lea     r8d, [rdx+78h]; Size
0x14003b773  lea     rcx, [rsp+1B0h+pv]; void *
0x14003b778  call    memset_0
0x14003b77d  mov     r9d, ebx
0x14003b780  lea     r8, aDestroycomregd_0; "DestroyComRegDBWriter failed with hr 0x"...
0x14003b787  lea     rdx, [rsp+1B0h+var_160]
0x14003b78c  lea     rcx, [rbp+0B0h+var_B0]
0x14003b790  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003b795  mov     [rdi+18h], sil
0x14003b799  jmp     short loc_14003B800
0x14003b79b  mov     [rsp+1B0h+var_160], r15
0x14003b7a0  mov     [rsp+1B0h+var_158], r12
0x14003b7a5  mov     [rsp+1B0h+var_150], r13
0x14003b7aa  mov     [rsp+1B0h+var_148], 5Bh ; '['
0x14003b7b2  mov     [rsp+1B0h+var_144], 4
0x14003b7ba  mov     [rsp+1B0h+var_140], r14d
0x14003b7bf  mov     [rbp+0B0h+var_C0], 1000000h
0x14003b7c6  xor     edx, edx; Val
0x14003b7c8  lea     r8d, [rdx+78h]; Size
0x14003b7cc  lea     rcx, [rsp+1B0h+pv]; void *
0x14003b7d1  call    memset_0
0x14003b7d6  lea     rax, aFalse; "FALSE"
0x14003b7dd  lea     r9, aTrue; "TRUE"
0x14003b7e4  test    bl, bl
0x14003b7e6  cmovz   r9, rax
0x14003b7ea  lea     r8, aTheComWriterWa; "The COM+ writer was not initialized on "...
0x14003b7f1  lea     rdx, [rsp+1B0h+var_160]
0x14003b7f6  lea     rcx, [rbp+0B0h+var_B0]
0x14003b7fa  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003b7ff  nop
0x14003b800  lea     rcx, [rbp+0B0h+var_B0]; this
0x14003b804  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003b809  add     rsp, 178h
0x14003b810  pop     r15
0x14003b812  pop     r14
0x14003b814  pop     r13
0x14003b816  pop     r12
0x14003b818  pop     rdi
0x14003b819  pop     rsi
0x14003b81a  pop     rbx
0x14003b81b  pop     rbp
0x14003b81c  retn
```
