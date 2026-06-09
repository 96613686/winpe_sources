# CVssDiag::Initialize(ushort const *)

- ea: `0x140027cb0`
- end: `0x140028193`
- name: `?Initialize@CVssDiag@@QEAAXPEBG@Z`
- size: `1251`
- prototype: `void __fastcall(CVssDiag *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400272d8`
- `0x140027420`
- `0x1400281a0`
- `0x14004a93c`
- `0x1400a92e8`
- `0x1400cb914`

## callees

- `0x140009b50`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140014650`
- `0x140027690`
- `0x140027cb0`
- `0x140049ec4`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140027d7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140027d7d`
- `VssTrace!__imp_VssTraceMessage` at `0x140027e86`
- `VssTrace!__imp_VssTraceMessage` at `0x140027e86`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140027ddf`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140027ddf`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140027dd0`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140027dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027ea6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027ff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400280e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027ea6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027ff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400280e9`

## string_xrefs

- `0x140027cd1`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140028044`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140027f5c`: `SYSTEM\CurrentControlSet\Services\VSS\Diag`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall CVssDiag::Initialize(CVssDiag *this, const unsigned __int16 *a2)
{
  int v4; // eax
  __int64 v5; // rcx
  int v6; // ebx
  __int64 i; // rbx
  void *v8; // rcx
  char v9; // r9
  char Value; // al
  unsigned __int16 *v11; // rbx
  unsigned __int16 *v12; // rax
  int v13; // ecx
  int v14; // edx
  unsigned __int64 v15; // [rsp+50h] [rbp-168h] BYREF
  int v16; // [rsp+58h] [rbp-160h]
  const unsigned __int16 *v17; // [rsp+60h] [rbp-158h]
  const unsigned __int16 *v18; // [rsp+68h] [rbp-150h]
  unsigned int v19; // [rsp+70h] [rbp-148h]
  int v20; // [rsp+74h] [rbp-144h]
  const unsigned __int16 *v21; // [rsp+78h] [rbp-140h]
  unsigned int v22; // [rsp+80h] [rbp-138h]
  DWORD TickCount; // [rsp+84h] [rbp-134h]
  int v24; // [rsp+88h] [rbp-130h]
  __int128 v25; // [rsp+90h] [rbp-128h]
  __int128 v26; // [rsp+A0h] [rbp-118h]
  __int64 v27; // [rsp+B0h] [rbp-108h]
  const unsigned __int16 *v28; // [rsp+C0h] [rbp-F8h] BYREF
  const unsigned __int16 *v29; // [rsp+C8h] [rbp-F0h]
  const unsigned __int16 *v30; // [rsp+D0h] [rbp-E8h]
  int v31; // [rsp+D8h] [rbp-E0h]
  int v32; // [rsp+DCh] [rbp-DCh]
  int v33; // [rsp+E0h] [rbp-D8h]
  LPVOID pv[15]; // [rsp+E8h] [rbp-D0h] BYREF
  int v35; // [rsp+160h] [rbp-58h]
  void **v36; // [rsp+168h] [rbp-50h]
  unsigned __int16 *v37; // [rsp+170h] [rbp-48h] BYREF
  __int64 v38; // [rsp+1C8h] [rbp+10h] BYREF

  v28 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v29 = L"CVssDiag::Initialize";
  v30 = L"REGREGSC";
  v31 = 1253;
  v32 = 11;
  v33 = 255;
  v35 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v16 = 0;
  v21 = L"CVssDiag::Initialize";
  v17 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v18 = L"REGREGSC";
  v19 = 1253;
  v20 = 11;
  TickCount = GetTickCount();
  v24 = 255;
  v15 = 0xFFFFFFFF00000000uLL;
  v27 = 0;
  v25 = 0;
  v26 = 0;
  v38 = 0;
  if ( (int)VssGetTracingContextPerThread(&v38) < 0 )
  {
    v5 = v27;
  }
  else
  {
    v4 = VssSetTracingContextPerThread(&v15);
    v5 = v27;
    if ( v4 >= 0 )
      v5 = v38;
    v27 = v5;
  }
  if ( v5 )
    v22 = *(_DWORD *)(v5 + 48) + 1;
  else
    v22 = 0;
  v6 = 160;
  if ( v24 != 255 )
    v6 = v24;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v15) )
    VssTraceMessage(v17, v18, v19, v22, v20, v21, L"ENTER", v6, 0);
  if ( HIBYTE(v35) )
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
  v28 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v29 = L"CVssDiag::Initialize";
  v30 = L"REGREGSC";
  v31 = 1257;
  v32 = 11;
  v33 = 255;
  v35 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  CVssFunctionTracer::Trace(&v15, &v28, L"Parameters %s", a2);
  if ( !a2 || !*a2 )
  {
    v28 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v29 = L"CVssDiag::Initialize";
    v30 = L"REGREGSC";
    v31 = 1262;
    v32 = 11;
    v33 = 255;
    v35 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::TranslateGenericError(&v15, &v28, 2147549183LL, L" NULL or empty parameter");
  }
  if ( !*((_BYTE *)this + 32) )
  {
    if ( !CVssRegistryKey::Open((REGSAM *)this, HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Diag") )
      CVssRegistryKey::Create(this, HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Diag");
    v36 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    v37 = 0;
    Value = CVssRegistryKey::GetValue((HKEY *)this, &byte_1400F9C88, (BYTE **)&v37, v9);
    v11 = v37;
    if ( !Value || !v37 )
      goto LABEL_40;
    v12 = v37;
    do
    {
      v13 = *(unsigned __int16 *)((char *)v12 + (char *)L"Disabled" - (char *)v37);
      v14 = *v12 - v13;
      if ( v14 )
        break;
      ++v12;
    }
    while ( v13 );
    if ( !v14 )
    {
      CoTaskMemFree(v37);
    }
    else
    {
LABEL_40:
      if ( !CVssRegistryKey::Open(
              (REGSAM *)this,
              HKEY_LOCAL_MACHINE,
              L"%s\\%s",
              L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Diag",
              a2) )
        CVssRegistryKey::Create(
          this,
          HKEY_LOCAL_MACHINE,
          L"%s\\%s",
          L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Diag",
          a2);
      v28 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v29 = L"CVssDiag::Initialize";
      v30 = L"REGREGSC";
      v31 = 1285;
      v32 = 11;
      v33 = 255;
      v35 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      CVssFunctionTracer::Trace(&v15, &v28, L"Diagnose enabled for (%s)", a2);
      if ( this != (CVssDiag *)-40LL )
        memset_0((char *)this + 40, 0, 0x50u);
      *((_BYTE *)this + 32) = 1;
      if ( v11 )
        CoTaskMemFree(v11);
    }
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v15);
}

```

## disassembly

```asm
0x140027cb0  mov     r11, rsp
0x140027cb3  mov     [r11+8], rbx
0x140027cb7  mov     [r11+18h], rsi
0x140027cbb  push    rdi
0x140027cbc  push    r12
0x140027cbe  push    r13
0x140027cc0  push    r14
0x140027cc2  push    r15
0x140027cc4  sub     rsp, 190h
0x140027ccb  mov     rsi, rdx
0x140027cce  mov     rdi, rcx
0x140027cd1  lea     r15, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x140027cd8  mov     [r11-0F8h], r15
0x140027cdf  lea     r12, aCvssdiagInitia; "CVssDiag::Initialize"
0x140027ce6  mov     [r11-0F0h], r12
0x140027ced  lea     rax, aRegregsc; "REGREGSC"
0x140027cf4  mov     [r11-0E8h], rax
0x140027cfb  mov     [rsp+1B8h+var_E0], 4E5h
0x140027d06  mov     [rsp+1B8h+var_DC], 0Bh
0x140027d11  mov     r13d, 0FFh
0x140027d17  mov     [r11-0D8h], r13d
0x140027d1e  xor     r14d, r14d
0x140027d21  mov     dword ptr [r11-58h], 1000000h
0x140027d29  xor     edx, edx; Val
0x140027d2b  lea     r8d, [r14+78h]; Size
0x140027d2f  lea     rcx, [r11-0D0h]; void *
0x140027d36  call    memset_0
0x140027d3b  mov     [rsp+1B8h+var_160], r14d
0x140027d40  mov     rax, [rsp+1B8h+var_F0]
0x140027d48  mov     [rsp+1B8h+var_140], rax
0x140027d4d  mov     rax, [rsp+1B8h+var_F8]
0x140027d55  mov     [rsp+1B8h+var_158], rax
0x140027d5a  mov     rax, [rsp+1B8h+var_E8]
0x140027d62  mov     [rsp+1B8h+var_150], rax
0x140027d67  mov     eax, [rsp+1B8h+var_E0]
0x140027d6e  mov     [rsp+1B8h+var_148], eax
0x140027d72  mov     eax, [rsp+1B8h+var_DC]
0x140027d79  mov     [rsp+1B8h+var_144], eax
0x140027d7d  call    cs:__imp_GetTickCount
0x140027d83  mov     [rsp+1B8h+var_134], eax
0x140027d8a  mov     [rsp+1B8h+var_164], 0FFFFFFFFh
0x140027d92  mov     eax, [rsp+1B8h+var_D8]
0x140027d99  mov     [rsp+1B8h+var_130], eax
0x140027da0  mov     [rsp+1B8h+var_168], r14d
0x140027da5  mov     [rsp+1B8h+var_108], r14
0x140027dad  xorps   xmm0, xmm0
0x140027db0  movups  [rsp+1B8h+var_128], xmm0
0x140027db8  movups  [rsp+1B8h+var_118], xmm0
0x140027dc0  mov     [rsp+1B8h+arg_8], r14
0x140027dc8  lea     rcx, [rsp+1B8h+arg_8]
0x140027dd0  call    cs:__imp_VssGetTracingContextPerThread
0x140027dd6  test    eax, eax
0x140027dd8  js      short loc_140027E02
0x140027dda  lea     rcx, [rsp+1B8h+var_168]
0x140027ddf  call    cs:__imp_VssSetTracingContextPerThread
0x140027de5  mov     rcx, [rsp+1B8h+var_108]
0x140027ded  test    eax, eax
0x140027def  cmovns  rcx, [rsp+1B8h+arg_8]
0x140027df8  mov     [rsp+1B8h+var_108], rcx
0x140027e00  jmp     short loc_140027E0A
0x140027e02  mov     rcx, [rsp+1B8h+var_108]
0x140027e0a  test    rcx, rcx
0x140027e0d  jz      short loc_140027E1D
0x140027e0f  mov     eax, [rcx+30h]
0x140027e12  inc     eax
0x140027e14  mov     [rsp+1B8h+var_138], eax
0x140027e1b  jmp     short loc_140027E25
0x140027e1d  mov     [rsp+1B8h+var_138], r14d
0x140027e25  mov     ebx, 0A0h
0x140027e2a  cmp     [rsp+1B8h+var_130], r13d
0x140027e32  cmovnz  ebx, [rsp+1B8h+var_130]
0x140027e3a  lea     rcx, [rsp+1B8h+var_168]; this
0x140027e3f  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140027e44  test    eax, eax
0x140027e46  jz      short loc_140027E8C
0x140027e48  mov     [rsp+1B8h+var_178], r14
0x140027e4d  mov     [rsp+1B8h+var_180], ebx
0x140027e51  lea     rax, aEnter; "ENTER"
0x140027e58  mov     [rsp+1B8h+var_188], rax
0x140027e5d  mov     rax, [rsp+1B8h+var_140]
0x140027e62  mov     [rsp+1B8h+var_190], rax
0x140027e67  mov     eax, [rsp+1B8h+var_144]
0x140027e6b  mov     dword ptr [rsp+1B8h+var_198], eax
0x140027e6f  mov     r9d, [rsp+1B8h+var_138]
0x140027e77  mov     r8d, [rsp+1B8h+var_148]
0x140027e7c  mov     rdx, [rsp+1B8h+var_150]
0x140027e81  mov     rcx, [rsp+1B8h+var_158]
0x140027e86  call    cs:__imp_VssTraceMessage
0x140027e8c  cmp     [rsp+1B8h+var_55], r14b
0x140027e94  jz      short loc_140027EBD
0x140027e96  mov     rbx, r14
0x140027e99  mov     rcx, [rsp+rbx*8+1B8h+pv]; pv
0x140027ea1  test    rcx, rcx
0x140027ea4  jz      short loc_140027EB4
0x140027ea6  call    cs:__imp_CoTaskMemFree
0x140027eac  mov     [rsp+rbx*8+1B8h+pv], r14
0x140027eb4  inc     rbx
0x140027eb7  cmp     rbx, 0Fh
0x140027ebb  jnz     short loc_140027E99
0x140027ebd  mov     [rsp+1B8h+var_F8], r15
0x140027ec5  mov     [rsp+1B8h+var_F0], r12
0x140027ecd  lea     rbx, aRegregsc; "REGREGSC"
0x140027ed4  mov     [rsp+1B8h+var_E8], rbx
0x140027edc  mov     [rsp+1B8h+var_E0], 4E9h
0x140027ee7  mov     [rsp+1B8h+var_DC], 0Bh
0x140027ef2  mov     [rsp+1B8h+var_D8], r13d
0x140027efa  mov     dword ptr [rsp+160h], 1000000h
0x140027f05  xor     edx, edx; Val
0x140027f07  lea     r8d, [rdx+78h]; Size
0x140027f0b  lea     rcx, [rsp+1B8h+pv]; void *
0x140027f13  call    memset_0
0x140027f18  mov     r9, rsi
0x140027f1b  lea     r8, aParametersS; "Parameters %s"
0x140027f22  lea     rdx, [rsp+1B8h+var_F8]
0x140027f2a  lea     rcx, [rsp+1B8h+var_168]
0x140027f2f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140027f34  test    rsi, rsi
0x140027f37  jz      loc_1400280F2
0x140027f3d  cmp     [rsi], r14w
0x140027f41  jz      loc_1400280F2
0x140027f47  cmp     [rdi+20h], r14b
0x140027f4b  jz      short loc_140027F5C
0x140027f4d  lea     rcx, [rsp+1B8h+var_168]; this
0x140027f52  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140027f57  jmp     loc_140028176
0x140027f5c  lea     r15, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x140027f63  mov     r8, r15; unsigned __int16 *
0x140027f66  mov     r12, 0FFFFFFFF80000002h
0x140027f6d  mov     rdx, r12; HKEY
0x140027f70  mov     rcx, rdi; this
0x140027f73  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x140027f78  test    al, al
0x140027f7a  jnz     short loc_140027F8A
0x140027f7c  mov     r8, r15; unsigned __int16 *
0x140027f7f  mov     rdx, r12; HKEY
0x140027f82  mov     rcx, rdi; this
0x140027f85  call    ?Create@CVssRegistryKey@@QEAAXPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Create(HKEY__ *,ushort const *,...)
0x140027f8a  lea     rax, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x140027f91  mov     [rsp+1B8h+var_50], rax
0x140027f99  mov     [rsp+1B8h+var_48], r14
0x140027fa1  lea     r8, [rsp+1B8h+var_48]; unsigned __int16 **
0x140027fa9  lea     rdx, byte_1400F9C88; unsigned __int16 *
0x140027fb0  mov     rcx, rdi; this
0x140027fb3  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAPEAG_N@Z; CVssRegistryKey::GetValue(ushort const *,ushort * &,bool)
0x140027fb8  mov     rbx, [rsp+1B8h+var_48]
0x140027fc0  test    al, al
0x140027fc2  jz      short loc_14002800C
0x140027fc4  test    rbx, rbx
0x140027fc7  jz      short loc_14002800C
0x140027fc9  mov     rax, rbx
0x140027fcc  lea     r8, aDisabled; "Disabled"
0x140027fd3  sub     r8, rbx
0x140027fd6  movzx   edx, word ptr [rax]
0x140027fd9  movzx   ecx, word ptr [rax+r8]
0x140027fde  sub     edx, ecx
0x140027fe0  jnz     short loc_140027FEA
0x140027fe2  add     rax, 2
0x140027fe6  test    ecx, ecx
0x140027fe8  jnz     short loc_140027FD6
0x140027fea  test    edx, edx
0x140027fec  jnz     short loc_14002800C
0x140027fee  test    rbx, rbx
0x140027ff1  jz      short loc_140027FFD
0x140027ff3  mov     rcx, rbx; pv
0x140027ff6  call    cs:__imp_CoTaskMemFree
0x140027ffc  nop
0x140027ffd  lea     rcx, [rsp+1B8h+var_168]; this
0x140028002  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140028007  jmp     loc_140028176
0x14002800c  mov     [rsp+1B8h+var_198], rsi
0x140028011  mov     r9, r15
0x140028014  lea     r8, aSS; "%s\\%s"
0x14002801b  mov     rdx, r12; HKEY
0x14002801e  mov     rcx, rdi; this
0x140028021  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x140028026  test    al, al
0x140028028  jnz     short loc_140028044
0x14002802a  mov     [rsp+1B8h+var_198], rsi
0x14002802f  mov     r9, r15
0x140028032  lea     r8, aSS; "%s\\%s"
0x140028039  mov     rdx, r12; HKEY
0x14002803c  mov     rcx, rdi; this
0x14002803f  call    ?Create@CVssRegistryKey@@QEAAXPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Create(HKEY__ *,ushort const *,...)
0x140028044  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14002804b  mov     [rsp+1B8h+var_F8], rax
0x140028053  lea     rax, aCvssdiagInitia; "CVssDiag::Initialize"
0x14002805a  mov     [rsp+1B8h+var_F0], rax
0x140028062  lea     rax, aRegregsc; "REGREGSC"
0x140028069  mov     [rsp+1B8h+var_E8], rax
0x140028071  mov     [rsp+1B8h+var_E0], 505h
0x14002807c  mov     [rsp+1B8h+var_DC], 0Bh
0x140028087  mov     [rsp+1B8h+var_D8], r13d
0x14002808f  mov     dword ptr [rsp+160h], 1000000h
0x14002809a  xor     edx, edx; Val
0x14002809c  lea     r8d, [rdx+78h]; Size
0x1400280a0  lea     rcx, [rsp+1B8h+pv]; void *
0x1400280a8  call    memset_0
0x1400280ad  mov     r9, rsi
0x1400280b0  lea     r8, aDiagnoseEnable; "Diagnose enabled for (%s)"
0x1400280b7  lea     rdx, [rsp+1B8h+var_F8]
0x1400280bf  lea     rcx, [rsp+1B8h+var_168]
0x1400280c4  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400280c9  lea     rcx, [rdi+28h]; void *
0x1400280cd  test    rcx, rcx
0x1400280d0  jz      short loc_1400280DD
0x1400280d2  xor     edx, edx; Val
0x1400280d4  lea     r8d, [rdx+50h]; Size
0x1400280d8  call    memset_0
0x1400280dd  mov     byte ptr [rdi+20h], 1
0x1400280e1  test    rbx, rbx
0x1400280e4  jz      short loc_1400280F0
0x1400280e6  mov     rcx, rbx; pv
0x1400280e9  call    cs:__imp_CoTaskMemFree
0x1400280ef  nop
0x1400280f0  jmp     short loc_14002816C
0x1400280f2  mov     [rsp+1B8h+var_F8], r15
0x1400280fa  mov     [rsp+1B8h+var_F0], r12
0x140028102  mov     [rsp+1B8h+var_E8], rbx
0x14002810a  mov     [rsp+1B8h+var_E0], 4EEh
0x140028115  mov     [rsp+1B8h+var_DC], 0Bh
0x140028120  mov     [rsp+1B8h+var_D8], r13d
0x140028128  mov     dword ptr [rsp+160h], 1000000h
0x140028133  xor     edx, edx; Val
0x140028135  lea     r8d, [rdx+78h]; Size
0x140028139  lea     rcx, [rsp+1B8h+pv]; void *
0x140028141  call    memset_0
0x140028146  lea     r9, aNullOrEmptyPar; " NULL or empty parameter"
0x14002814d  mov     r8d, 8000FFFFh
0x140028153  lea     rdx, [rsp+1B8h+var_F8]
0x14002815b  lea     rcx, [rsp+1B8h+var_168]
0x140028160  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140028166  jmp     short loc_14002816C
0x140028168  jmp     short loc_14002816C
0x14002816a  jmp     short $+2
0x14002816c  lea     rcx, [rsp+1B8h+var_168]; this
0x140028171  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140028176  lea     r11, [rsp+1B8h+var_28]
0x14002817e  mov     rbx, [r11+30h]
0x140028182  mov     rsi, [r11+40h]
0x140028186  mov     rsp, r11
0x140028189  pop     r15
0x14002818b  pop     r14
0x14002818d  pop     r13
0x14002818f  pop     r12
0x140028191  pop     rdi
0x140028192  retn
```
