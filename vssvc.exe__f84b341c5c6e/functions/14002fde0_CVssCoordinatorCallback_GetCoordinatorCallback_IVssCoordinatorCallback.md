# CVssCoordinatorCallback::GetCoordinatorCallback(IVssCoordinatorCallback * *)

- ea: `0x14002fde0`
- end: `0x14003021f`
- name: `?GetCoordinatorCallback@CVssCoordinatorCallback@@QEAAXPEAPEAUIVssCoordinatorCallback@@@Z`
- size: `1087`
- prototype: `void __fastcall(CVssCoordinatorCallback *__hidden this, struct IVssCoordinatorCallback **)`
- caller_count: `5`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002e580`
- `0x14002f950`
- `0x140054e30`
- `0x140055590`
- `0x1400a85f0`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015e38`
- `0x14002fde0`
- `0x140032fcc`
- `0x1400330fc`
- `0x140049ec4`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002fe8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002fe8b`
- `VssTrace!__imp_VssTraceMessage` at `0x14002ff53`
- `VssTrace!__imp_VssTraceMessage` at `0x14002ff53`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002fed2`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002fed2`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002fec4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002fec4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x14003010d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x14003010d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002ff6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002ff6c`

## string_xrefs

- `0x14002ffd9`: `Illegal callback call during Delayed Post Snapshot`
- `0x1400300cb`: `QI to IVssWriterCallback failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssCoordinatorCallback::GetCoordinatorCallback(CVssCoordinatorCallback *this, IUnknown **a2)
{
  int v4; // eax
  __int64 v5; // rcx
  int v6; // ebx
  __int64 i; // rbx
  void *v8; // rcx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, IUnknown **); // rcx
  signed int v10; // ebx
  CVssDebugInfo *v11; // rax
  HRESULT v12; // eax
  DWORD v13; // ebx
  CVssDebugInfo *v14; // rax
  signed int v15; // ebx
  __int64 dwAuthnLevel; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v17; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v18; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+6Ch] [rbp-94h]
  int v22; // [rsp+70h] [rbp-90h]
  LPVOID pv[15]; // [rsp+78h] [rbp-88h] BYREF
  int v24; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v25; // [rsp+100h] [rbp+0h] BYREF
  signed int v26; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v27; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v28; // [rsp+118h] [rbp+18h]
  unsigned int v29; // [rsp+120h] [rbp+20h]
  int v30; // [rsp+124h] [rbp+24h]
  const wchar_t *v31; // [rsp+128h] [rbp+28h]
  unsigned int v32; // [rsp+130h] [rbp+30h]
  DWORD TickCount; // [rsp+134h] [rbp+34h]
  int v34; // [rsp+138h] [rbp+38h]
  __int128 v35; // [rsp+140h] [rbp+40h]
  __int128 v36; // [rsp+150h] [rbp+50h]
  __int64 v37; // [rsp+160h] [rbp+60h]
  _BYTE v38[240]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v39; // [rsp+270h] [rbp+170h] BYREF

  v17 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
  v18 = L"CVssCoordinatorCallback::GetCoordinatorCallback";
  v19 = L"CORCALBC";
  v20 = 105;
  v21 = 1;
  v22 = 255;
  v24 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v26 = 0;
  v31 = L"CVssCoordinatorCallback::GetCoordinatorCallback";
  v27 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
  v28 = L"CORCALBC";
  v29 = 105;
  v30 = 1;
  TickCount = GetTickCount();
  v34 = 255;
  v25 = 0xFFFFFFFF00000000uLL;
  v37 = 0;
  v35 = 0;
  v36 = 0;
  v39 = 0;
  if ( (int)VssGetTracingContextPerThread(&v39) < 0 )
  {
    v5 = v37;
  }
  else
  {
    v4 = VssSetTracingContextPerThread(&v25);
    v5 = v37;
    if ( v4 >= 0 )
      v5 = v39;
    v37 = v5;
  }
  if ( v5 )
    v32 = *(_DWORD *)(v5 + 48) + 1;
  else
    v32 = 0;
  v6 = 160;
  if ( v34 != 255 )
    v6 = v34;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v25) )
    VssTraceMessage(v27, v28, v29, v32, v30, v31, L"ENTER", v6, 0);
  if ( HIBYTE(v24) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v8 = pv[i];
      if ( v8 )
      {
        CoTaskMemFree(v8);
        pv[i] = 0;
      }
    }
  }
  *a2 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, IUnknown **))*((_QWORD *)this + 9);
  if ( !v9 )
  {
    v17 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
    v18 = L"CVssCoordinatorCallback::GetCoordinatorCallback";
    v19 = L"CORCALBC";
    v20 = 117;
    v21 = 1;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::TranslateGenericError(
      &v25,
      &v17,
      2147549183LL,
      L"Illegal callback call during Delayed Post Snapshot");
  }
  v10 = (**v9)(v9, &GUID_6a36e2b7_7cf8_48b7_8d9f_d4f96fa413a8, a2);
  v26 = v10;
  if ( v10 < 0 )
  {
    v17 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
    v18 = L"CVssCoordinatorCallback::GetCoordinatorCallback";
    v19 = L"CORCALBC";
    v20 = 123;
    v21 = 1;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    v11 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v17, (CVssDebugInfo *)v38, v10);
    CVssFunctionTracer::LogError((__int64)&v25, 0x2002u, (__int64)v11, 1u);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v17);
    v17 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
    v18 = L"CVssCoordinatorCallback::GetCoordinatorCallback";
    v19 = L"CORCALBC";
    v20 = 124;
    v21 = 1;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::Throw(&v25, &v17, 2147754754LL, L"QI to IVssWriterCallback failed");
  }
  v12 = CoSetProxyBlanket(*a2, 0xFFFFFFFF, 0xFFFFFFFF, 0, 6u, 2u, 0, 0);
  v13 = v12;
  v26 = v12;
  if ( v12 < 0 && v12 != -2147467262 )
  {
    v17 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
    v18 = L"CVssCoordinatorCallback::GetCoordinatorCallback";
    v19 = L"CORCALBC";
    v20 = 144;
    v21 = 1;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    v14 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v17, (CVssDebugInfo *)v38, v13);
    CVssFunctionTracer::LogError((__int64)&v25, 0x300Fu, (__int64)v14, 1u);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v17);
    v15 = v26;
    v17 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
    v18 = L"CVssCoordinatorCallback::GetCoordinatorCallback";
    v19 = L"CORCALBC";
    v20 = 147;
    v21 = 1;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    LODWORD(dwAuthnLevel) = v15;
    CVssFunctionTracer::Throw(
      &v25,
      &v17,
      2147754754LL,
      L"Call to CoSetProxyBlanket failed.  hr = 0x%08lx",
      dwAuthnLevel);
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v25);
}

```

## disassembly

```asm
0x14002fde0  push    rbp
0x14002fde2  push    rbx
0x14002fde3  push    rsi
0x14002fde4  push    rdi
0x14002fde5  push    r12
0x14002fde7  push    r13
0x14002fde9  push    r14
0x14002fdeb  push    r15
0x14002fded  lea     rbp, [rsp-128h]
0x14002fdf5  sub     rsp, 228h
0x14002fdfc  mov     rdi, rdx
0x14002fdff  mov     rsi, rcx
0x14002fe02  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14002fe09  mov     [rsp+260h+var_210], rax
0x14002fe0e  lea     rax, aCvsscoordinato_27; "CVssCoordinatorCallback::GetCoordinator"...
0x14002fe15  mov     [rsp+260h+var_208], rax
0x14002fe1a  lea     rax, aCorcalbc; "CORCALBC"
0x14002fe21  mov     [rsp+260h+var_200], rax
0x14002fe26  mov     [rsp+260h+var_1F8], 69h ; 'i'
0x14002fe2e  mov     r15d, 1
0x14002fe34  mov     [rsp+260h+var_1F4], r15d
0x14002fe39  mov     r12d, 0FFh
0x14002fe3f  mov     [rsp+260h+var_1F0], r12d
0x14002fe44  xor     r14d, r14d
0x14002fe47  mov     [rbp+160h+var_170], 1000000h
0x14002fe4e  xor     edx, edx; Val
0x14002fe50  lea     r8d, [r15+77h]; Size
0x14002fe54  lea     rcx, [rsp+260h+pv]; void *
0x14002fe59  call    memset_0
0x14002fe5e  mov     [rbp+160h+var_158], r14d
0x14002fe62  mov     rax, [rsp+260h+var_208]
0x14002fe67  mov     [rbp+160h+var_138], rax
0x14002fe6b  mov     rax, [rsp+260h+var_210]
0x14002fe70  mov     [rbp+160h+var_150], rax
0x14002fe74  mov     rax, [rsp+260h+var_200]
0x14002fe79  mov     [rbp+160h+var_148], rax
0x14002fe7d  mov     eax, [rsp+260h+var_1F8]
0x14002fe81  mov     [rbp+160h+var_140], eax
0x14002fe84  mov     eax, [rsp+260h+var_1F4]
0x14002fe88  mov     [rbp+160h+var_13C], eax
0x14002fe8b  call    cs:__imp_GetTickCount
0x14002fe91  mov     [rbp+160h+var_12C], eax
0x14002fe94  or      r13d, 0FFFFFFFFh
0x14002fe98  mov     [rbp+160h+var_15C], r13d
0x14002fe9c  mov     eax, [rsp+260h+var_1F0]
0x14002fea0  mov     [rbp+160h+var_128], eax
0x14002fea3  mov     [rbp+160h+var_160], r14d
0x14002fea7  mov     [rbp+160h+var_100], r14
0x14002feab  xorps   xmm0, xmm0
0x14002feae  movups  [rbp+160h+var_120], xmm0
0x14002feb2  movups  [rbp+160h+var_110], xmm0
0x14002feb6  mov     [rbp+160h+arg_0], r14
0x14002febd  lea     rcx, [rbp+160h+arg_0]
0x14002fec4  call    cs:__imp_VssGetTracingContextPerThread
0x14002feca  test    eax, eax
0x14002fecc  js      short loc_14002FEEC
0x14002fece  lea     rcx, [rbp+160h+var_160]
0x14002fed2  call    cs:__imp_VssSetTracingContextPerThread
0x14002fed8  mov     rcx, [rbp+160h+var_100]
0x14002fedc  test    eax, eax
0x14002fede  cmovns  rcx, [rbp+160h+arg_0]
0x14002fee6  mov     [rbp+160h+var_100], rcx
0x14002feea  jmp     short loc_14002FEF0
0x14002feec  mov     rcx, [rbp+160h+var_100]
0x14002fef0  test    rcx, rcx
0x14002fef3  jz      short loc_14002FF00
0x14002fef5  mov     eax, [rcx+30h]
0x14002fef8  add     eax, r15d
0x14002fefb  mov     [rbp+160h+var_130], eax
0x14002fefe  jmp     short loc_14002FF04
0x14002ff00  mov     [rbp+160h+var_130], r14d
0x14002ff04  mov     ebx, 0A0h
0x14002ff09  cmp     [rbp+160h+var_128], r12d
0x14002ff0d  cmovnz  ebx, [rbp+160h+var_128]
0x14002ff11  lea     rcx, [rbp+160h+var_160]; this
0x14002ff15  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14002ff1a  test    eax, eax
0x14002ff1c  jz      short loc_14002FF59
0x14002ff1e  mov     [rsp+260h+var_220], r14
0x14002ff23  mov     [rsp+260h+dwCapabilities], ebx
0x14002ff27  lea     rax, aEnter; "ENTER"
0x14002ff2e  mov     [rsp+260h+pAuthInfo], rax
0x14002ff33  mov     rax, [rbp+160h+var_138]
0x14002ff37  mov     qword ptr [rsp+260h+dwImpLevel], rax
0x14002ff3c  mov     eax, [rbp+160h+var_13C]
0x14002ff3f  mov     dword ptr [rsp+260h+dwAuthnLevel], eax
0x14002ff43  mov     r9d, [rbp+160h+var_130]
0x14002ff47  mov     r8d, [rbp+160h+var_140]
0x14002ff4b  mov     rdx, [rbp+160h+var_148]
0x14002ff4f  mov     rcx, [rbp+160h+var_150]
0x14002ff53  call    cs:__imp_VssTraceMessage
0x14002ff59  cmp     byte ptr [rbp+160h+var_170+3], r14b
0x14002ff5d  jz      short loc_14002FF80
0x14002ff5f  mov     rbx, r14
0x14002ff62  mov     rcx, [rsp+rbx*8+260h+pv]; pv
0x14002ff67  test    rcx, rcx
0x14002ff6a  jz      short loc_14002FF77
0x14002ff6c  call    cs:__imp_CoTaskMemFree
0x14002ff72  mov     [rsp+rbx*8+260h+pv], r14
0x14002ff77  add     rbx, r15
0x14002ff7a  cmp     rbx, 0Fh
0x14002ff7e  jnz     short loc_14002FF62
0x14002ff80  mov     [rdi], r14
0x14002ff83  mov     rcx, [rsi+48h]
0x14002ff87  test    rcx, rcx
0x14002ff8a  jnz     short loc_14002FFF5
0x14002ff8c  lea     rdi, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14002ff93  mov     [rsp+260h+var_210], rdi
0x14002ff98  lea     rsi, aCvsscoordinato_27; "CVssCoordinatorCallback::GetCoordinator"...
0x14002ff9f  mov     [rsp+260h+var_208], rsi
0x14002ffa4  lea     r13, aCorcalbc; "CORCALBC"
0x14002ffab  mov     [rsp+260h+var_200], r13
0x14002ffb0  mov     [rsp+260h+var_1F8], 75h ; 'u'
0x14002ffb8  mov     [rsp+260h+var_1F4], r15d
0x14002ffbd  mov     [rsp+260h+var_1F0], r12d
0x14002ffc2  mov     [rbp+160h+var_170], 1000000h
0x14002ffc9  xor     edx, edx; Val
0x14002ffcb  lea     r8d, [rcx+78h]; Size
0x14002ffcf  lea     rcx, [rsp+260h+pv]; void *
0x14002ffd4  call    memset_0
0x14002ffd9  lea     r9, aIllegalCallbac; "Illegal callback call during Delayed Po"...
0x14002ffe0  mov     r8d, 8000FFFFh
0x14002ffe6  lea     rdx, [rsp+260h+var_210]
0x14002ffeb  lea     rcx, [rbp+160h+var_160]
0x14002ffef  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14002fff5  mov     rax, [rcx]
0x14002fff8  mov     r8, rdi
0x14002fffb  lea     rdx, _GUID_6a36e2b7_7cf8_48b7_8d9f_d4f96fa413a8
0x140030002  mov     rax, [rax]
0x140030005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003000a  mov     ebx, eax
0x14003000c  mov     [rbp+160h+var_158], eax
0x14003000f  test    eax, eax
0x140030011  jns     loc_1400300E7
0x140030017  lea     rdi, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14003001e  mov     [rsp+260h+var_210], rdi
0x140030023  lea     rsi, aCvsscoordinato_27; "CVssCoordinatorCallback::GetCoordinator"...
0x14003002a  mov     [rsp+260h+var_208], rsi
0x14003002f  lea     r13, aCorcalbc; "CORCALBC"
0x140030036  mov     [rsp+260h+var_200], r13
0x14003003b  mov     [rsp+260h+var_1F8], 7Bh ; '{'
0x140030043  mov     [rsp+260h+var_1F4], r15d
0x140030048  mov     [rsp+260h+var_1F0], r12d
0x14003004d  mov     [rbp+160h+var_170], 1000000h
0x140030054  xor     edx, edx; Val
0x140030056  lea     r8d, [rdx+78h]; Size
0x14003005a  lea     rcx, [rsp+260h+pv]; void *
0x14003005f  call    memset_0
0x140030064  mov     r8d, ebx; dwMessageId
0x140030067  lea     rdx, [rbp+160h+var_F0]; this
0x14003006b  lea     rcx, [rsp+260h+var_210]; struct CVssDebugInfo *
0x140030070  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x140030075  mov     r9d, r15d
0x140030078  mov     r8, rax
0x14003007b  mov     edx, 2002h
0x140030080  lea     rcx, [rbp+160h+var_160]
0x140030084  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x140030089  lea     rcx, [rsp+260h+var_210]; this
0x14003008e  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140030093  mov     [rsp+260h+var_210], rdi
0x140030098  mov     [rsp+260h+var_208], rsi
0x14003009d  mov     [rsp+260h+var_200], r13
0x1400300a2  mov     [rsp+260h+var_1F8], 7Ch ; '|'
0x1400300aa  mov     [rsp+260h+var_1F4], r15d
0x1400300af  mov     [rsp+260h+var_1F0], r12d
0x1400300b4  mov     [rbp+160h+var_170], 1000000h
0x1400300bb  xor     edx, edx; Val
0x1400300bd  lea     r8d, [rdx+78h]; Size
0x1400300c1  lea     rcx, [rsp+260h+pv]; void *
0x1400300c6  call    memset_0
0x1400300cb  lea     r9, aQiToIvsswriter; "QI to IVssWriterCallback failed"
0x1400300d2  mov     r8d, 80042302h
0x1400300d8  lea     rdx, [rsp+260h+var_210]
0x1400300dd  lea     rcx, [rbp+160h+var_160]
0x1400300e1  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400300e7  mov     [rsp+260h+dwCapabilities], r14d; dwCapabilities
0x1400300ec  mov     [rsp+260h+pAuthInfo], r14; pAuthInfo
0x1400300f1  mov     [rsp+260h+dwImpLevel], 2; dwImpLevel
0x1400300f9  mov     dword ptr [rsp+260h+dwAuthnLevel], 6; dwAuthnLevel
0x140030101  xor     r9d, r9d; pServerPrincName
0x140030104  mov     r8d, r13d; dwAuthzSvc
0x140030107  mov     edx, r13d; dwAuthnSvc
0x14003010a  mov     rcx, [rdi]; pProxy
0x14003010d  call    cs:__imp_CoSetProxyBlanket
0x140030113  mov     ebx, eax
0x140030115  mov     [rbp+160h+var_158], eax
0x140030118  test    eax, eax
0x14003011a  jns     loc_140030202
0x140030120  cmp     eax, 80004002h
0x140030125  jz      loc_140030202
0x14003012b  lea     rdi, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x140030132  mov     [rsp+260h+var_210], rdi
0x140030137  lea     rsi, aCvsscoordinato_27; "CVssCoordinatorCallback::GetCoordinator"...
0x14003013e  mov     [rsp+260h+var_208], rsi
0x140030143  lea     r13, aCorcalbc; "CORCALBC"
0x14003014a  mov     [rsp+260h+var_200], r13
0x14003014f  mov     [rsp+260h+var_1F8], 90h
0x140030157  mov     [rsp+260h+var_1F4], r15d
0x14003015c  mov     [rsp+260h+var_1F0], r12d
0x140030161  mov     [rbp+160h+var_170], 1000000h
0x140030168  xor     edx, edx; Val
0x14003016a  lea     r8d, [rdx+78h]; Size
0x14003016e  lea     rcx, [rsp+260h+pv]; void *
0x140030173  call    memset_0
0x140030178  mov     r8d, ebx; dwMessageId
0x14003017b  lea     rdx, [rbp+160h+var_F0]; this
0x14003017f  lea     rcx, [rsp+260h+var_210]; struct CVssDebugInfo *
0x140030184  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x140030189  mov     r9d, r15d
0x14003018c  mov     r8, rax
0x14003018f  mov     edx, 300Fh
0x140030194  lea     rcx, [rbp+160h+var_160]
0x140030198  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x14003019d  lea     rcx, [rsp+260h+var_210]; this
0x1400301a2  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x1400301a7  mov     ebx, [rbp+160h+var_158]
0x1400301aa  mov     [rsp+260h+var_210], rdi
0x1400301af  mov     [rsp+260h+var_208], rsi
0x1400301b4  mov     [rsp+260h+var_200], r13
0x1400301b9  mov     [rsp+260h+var_1F8], 93h
0x1400301c1  mov     [rsp+260h+var_1F4], r15d
0x1400301c6  mov     [rsp+260h+var_1F0], r12d
0x1400301cb  mov     [rbp+160h+var_170], 1000000h
0x1400301d2  xor     edx, edx; Val
0x1400301d4  lea     r8d, [rdx+78h]; Size
0x1400301d8  lea     rcx, [rsp+260h+pv]; void *
0x1400301dd  call    memset_0
0x1400301e2  mov     dword ptr [rsp+260h+dwAuthnLevel], ebx
0x1400301e6  lea     r9, aCallToCosetpro; "Call to CoSetProxyBlanket failed.  hr ="...
0x1400301ed  mov     r8d, 80042302h
0x1400301f3  lea     rdx, [rsp+260h+var_210]
0x1400301f8  lea     rcx, [rbp+160h+var_160]
0x1400301fc  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140030202  lea     rcx, [rbp+160h+var_160]; this
0x140030206  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003020b  add     rsp, 228h
0x140030212  pop     r15
0x140030214  pop     r14
0x140030216  pop     r13
0x140030218  pop     r12
0x14003021a  pop     rdi
0x14003021b  pop     rsi
0x14003021c  pop     rbx
0x14003021d  pop     rbp
0x14003021e  retn
```
