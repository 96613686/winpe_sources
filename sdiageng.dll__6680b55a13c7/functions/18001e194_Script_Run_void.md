# Script::Run(void)

- ea: `0x18001e194`
- end: `0x18001e53f`
- name: `?Run@Script@@QEAAJXZ`
- size: `939`
- prototype: `__int64 __fastcall(const OLECHAR **this, __int64, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ae2c`
- `0x18001b3b8`
- `0x18001c110`

## callees

- `0x180005590`
- `0x1800130d0`
- `0x18001d544`
- `0x18001e194`
- `0x18001e65c`
- `0x18002146c`
- `0x180026fa0`
- `0x18002744c`
- `0x1800280f8`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18001e1f8`
- `KERNEL32!GetTickCount64` at `0x18001e40a`
- `KERNEL32!GetTickCount64` at `0x18001e1f8`
- `KERNEL32!GetTickCount64` at `0x18001e40a`
- `ole32!CoAllowSetForegroundWindow` at `0x18001e396`
- `ole32!CoAllowSetForegroundWindow` at `0x18001e396`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e30e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e30e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e4e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e4e9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001e2e2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001e2f0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001e4f8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001e506`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001e2e2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001e2f0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001e4f8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001e506`

## string_xrefs

- `0x18001e21e`: `<?xml version="1.0" encoding="utf-8"?><DetailedInformation/>`
- `0x18001e41a`: `Script::UpdateReport`
- `0x18001e48f`: `Script::UpdateReport`

## pseudocode

```c
__int64 __fastcall Script::Run(const OLECHAR **this, __int64 a2, __int64 a3)
{
  SAFEARRAY *v3; // rsi
  OLECHAR *v5; // r12
  struct tagSAFEARRAY *v6; // r15
  SAFEARRAY *v7; // r13
  IUnknown *v8; // r14
  int v9; // ebx
  int v10; // r8d
  int v11; // r9d
  int IsAdmin; // eax
  const OLECHAR *v13; // rcx
  int v14; // eax
  SAFEARRAY *v15; // rcx
  int Host; // eax
  HRESULT v17; // eax
  unsigned __int16 *v18; // rsi
  ULONGLONG TickCount64; // rax
  int v20; // esi
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // eax
  IUnknown *v24; // r15
  int v25; // r8d
  struct tagSAFEARRAY *v27; // [rsp+30h] [rbp-48h] BYREF
  SAFEARRAY *psa; // [rsp+38h] [rbp-40h] BYREF
  IUnknown *pUnk; // [rsp+40h] [rbp-38h] BYREF
  SAFEARRAY *v30; // [rsp+48h] [rbp-30h]
  _QWORD v31[2]; // [rsp+50h] [rbp-28h] BYREF

  v3 = 0;
  v5 = 0;
  v6 = 0;
  v30 = 0;
  v7 = 0;
  pUnk = 0;
  v8 = 0;
  LODWORD(v27) = 0;
  psa = 0;
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(this, SCRIPTED_DIAGNOSTICS_EVENT_PERF_SCRIPT_START, a3, 1, v31);
  v31[0] = GetTickCount64();
  if ( !*this )
  {
    v9 = -2147467261;
    v10 = 133;
    v11 = -2147467261;
LABEL_37:
    SdpDebugTrace(1u, L"Script::Run", v10, v11);
    goto LABEL_38;
  }
  IsAdmin = SdpXmlCreate(
              (OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><DetailedInformation/>",
              (struct IXMLDOMDocument2 **)&psa);
  v9 = IsAdmin;
  if ( IsAdmin < 0 )
  {
    v10 = 136;
LABEL_36:
    v11 = IsAdmin;
    goto LABEL_37;
  }
  v13 = this[6];
  if ( v13 )
    (*(void (__fastcall **)(const OLECHAR *))(*(_QWORD *)v13 + 16LL))(v13);
  this[6] = &psa->cDims;
  IsAdmin = SdpIsAdmin((int *)&v27);
  v9 = IsAdmin;
  if ( IsAdmin < 0 )
  {
    v10 = 143;
    goto LABEL_36;
  }
  if ( *((_DWORD *)this + 4) && !(_DWORD)v27 )
  {
    v9 = 1;
    goto LABEL_38;
  }
  if ( this[3] )
  {
    v27 = 0;
    psa = 0;
    v14 = SdpParamSetToSafeArrays((struct _SDIAG_PARAMSET *)(this + 3), &v27, &psa);
    v9 = v14;
    if ( v14 >= 0 )
    {
      v6 = v27;
      v15 = 0;
      v7 = psa;
      v30 = v27;
    }
    else
    {
      SdpDebugTrace(1u, L"Script::PrepareParameters", 577, v14);
      v15 = v27;
      v3 = psa;
    }
    if ( v15 )
      SafeArrayDestroy(v15);
    if ( v3 )
      SafeArrayDestroy(v3);
    if ( v9 < 0 )
    {
      v11 = v9;
      v10 = 152;
      goto LABEL_37;
    }
  }
  v5 = SysAllocString(this[1]);
  if ( !v5 )
  {
    v9 = -2147024882;
    v10 = 156;
    v11 = -2147024882;
    goto LABEL_37;
  }
  if ( *((_DWORD *)this + 10) )
    *((_DWORD *)*this + 14) |= 0x40u;
  if ( _InterlockedExchange((volatile __int32 *)*this + 15, *((_DWORD *)*this + 15)) )
  {
    v9 = -2143551232;
    v10 = 176;
    v11 = -2143551232;
    goto LABEL_37;
  }
  Host = Settings::get_Host((Settings *)*this, (struct IScriptedDiagnosticHost **)&pUnk);
  v9 = Host;
  if ( Host < 0 )
  {
    SdpDebugTrace(1u, L"Script::Run", 180, Host);
    v8 = pUnk;
    goto LABEL_38;
  }
  v8 = pUnk;
  v17 = CoAllowSetForegroundWindow(pUnk, 0);
  if ( v17 < 0 )
    SdpDebugTrace(2u, L"Script::Run", 183, v17);
  IsAdmin = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, struct tagSAFEARRAY *, SAFEARRAY *))v8->lpVtbl[1].AddRef)(
              v8,
              v5,
              v6,
              v7);
  v9 = IsAdmin;
  if ( IsAdmin < 0 )
  {
    v10 = 186;
    goto LABEL_36;
  }
LABEL_38:
  if ( *this )
    *((_DWORD *)*this + 14) &= ~0x40u;
  v18 = (unsigned __int16 *)this[1];
  pUnk = 0;
  TickCount64 = GetTickCount64();
  if ( !v18 )
  {
    v20 = -2147024809;
    SdpDebugTrace(1u, L"Script::UpdateReport", 232, -2147024809);
    goto LABEL_49;
  }
  v23 = Script::BuildReportScriptXml(
          (Script *)this,
          v18,
          v6,
          v7,
          TickCount64 - v31[0],
          (struct IXMLDOMDocument2 **)&pUnk);
  v24 = pUnk;
  v20 = v23;
  if ( v23 >= 0 )
  {
    v23 = Reporter::AddXmlToReport(*((_QWORD *)*this + 9), pUnk, 2);
    v20 = v23;
    if ( v23 >= 0 )
      goto LABEL_47;
    v25 = 255;
  }
  else
  {
    v25 = 244;
  }
  SdpDebugTrace(1u, L"Script::UpdateReport", v25, v23);
LABEL_47:
  if ( v24 )
    ((void (__fastcall *)(IUnknown *))v24->lpVtbl->Release)(v24);
LABEL_49:
  if ( v9 >= 0 && v20 < 0 )
    v9 = v20;
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(v21, SCRIPTED_DIAGNOSTICS_EVENT_PERF_SCRIPT_STOP, v22, 1, v31);
  if ( v5 )
    SysFreeString(v5);
  if ( v30 )
    SafeArrayDestroy(v30);
  if ( v7 )
    SafeArrayDestroy(v7);
  if ( v8 )
    ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001e194  push    rbp
0x18001e196  push    rbx
0x18001e197  push    rsi
0x18001e198  push    rdi
0x18001e199  push    r12
0x18001e19b  push    r13
0x18001e19d  push    r14
0x18001e19f  push    r15
0x18001e1a1  mov     rbp, rsp
0x18001e1a4  sub     rsp, 78h
0x18001e1a8  mov     rax, cs:__security_cookie
0x18001e1af  xor     rax, rsp
0x18001e1b2  mov     [rbp+var_18], rax
0x18001e1b6  xor     esi, esi
0x18001e1b8  mov     rdi, rcx
0x18001e1bb  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 10h
0x18001e1c2  mov     r12d, esi
0x18001e1c5  mov     r15d, esi
0x18001e1c8  mov     [rbp+var_30], rsi
0x18001e1cc  mov     r13d, esi
0x18001e1cf  mov     [rbp+pUnk], rsi
0x18001e1d3  mov     r14d, esi
0x18001e1d6  mov     dword ptr [rbp+var_48], esi
0x18001e1d9  mov     [rbp+psa], rsi
0x18001e1dd  jz      short loc_18001E1F8
0x18001e1df  lea     rax, [rbp+var_28]
0x18001e1e3  lea     r9d, [rsi+1]
0x18001e1e7  mov     [rsp+78h+var_58], rax
0x18001e1ec  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_PERF_SCRIPT_START
0x18001e1f3  call    McGenEventWrite_EventWriteTransfer
0x18001e1f8  call    cs:__imp_GetTickCount64
0x18001e1fe  mov     [rbp+var_28], rax
0x18001e202  cmp     [rdi], rsi
0x18001e205  jnz     short loc_18001E21A
0x18001e207  mov     ebx, 80004003h
0x18001e20c  mov     r8d, 85h
0x18001e212  mov     r9d, ebx
0x18001e215  jmp     loc_18001E3E1
0x18001e21a  lea     rdx, [rbp+psa]; struct IXMLDOMDocument2 **
0x18001e21e  lea     rcx, aXmlVersion10En_20; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001e225  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18001e22a  mov     ebx, eax
0x18001e22c  test    eax, eax
0x18001e22e  jns     short loc_18001E23B
0x18001e230  mov     r8d, 88h
0x18001e236  jmp     loc_18001E3DE
0x18001e23b  mov     rcx, [rdi+30h]
0x18001e23f  test    rcx, rcx
0x18001e242  jz      short loc_18001E250
0x18001e244  mov     rax, [rcx]
0x18001e247  mov     rax, [rax+10h]
0x18001e24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e250  mov     rax, [rbp+psa]
0x18001e254  lea     rcx, [rbp+var_48]; int *
0x18001e258  mov     [rdi+30h], rax
0x18001e25c  call    ?SdpIsAdmin@@YAJPEAH@Z; SdpIsAdmin(int *)
0x18001e261  mov     ebx, eax
0x18001e263  test    eax, eax
0x18001e265  jns     short loc_18001E272
0x18001e267  mov     r8d, 8Fh
0x18001e26d  jmp     loc_18001E3DE
0x18001e272  cmp     [rdi+10h], esi
0x18001e275  jz      short loc_18001E286
0x18001e277  cmp     dword ptr [rbp+var_48], esi
0x18001e27a  jnz     short loc_18001E286
0x18001e27c  mov     ebx, 1
0x18001e281  jmp     loc_18001E3F2
0x18001e286  lea     rcx, [rdi+18h]; struct _SDIAG_PARAMSET *
0x18001e28a  cmp     [rcx], rsi
0x18001e28d  jz      short loc_18001E30A
0x18001e28f  lea     r8, [rbp+psa]; struct tagSAFEARRAY **
0x18001e293  mov     [rbp+var_48], rsi
0x18001e297  lea     rdx, [rbp+var_48]; struct tagSAFEARRAY **
0x18001e29b  mov     [rbp+psa], rsi
0x18001e29f  call    ?SdpParamSetToSafeArrays@@YAJPEAU_SDIAG_PARAMSET@@PEAPEAUtagSAFEARRAY@@1@Z; SdpParamSetToSafeArrays(_SDIAG_PARAMSET *,tagSAFEARRAY * *,tagSAFEARRAY * *)
0x18001e2a4  mov     ebx, eax
0x18001e2a6  test    eax, eax
0x18001e2a8  jns     short loc_18001E2CE
0x18001e2aa  mov     r9d, eax; int
0x18001e2ad  lea     rdx, aScriptPreparep; "Script::PrepareParameters"
0x18001e2b4  mov     r8d, 241h; int
0x18001e2ba  mov     ecx, 1; Level
0x18001e2bf  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e2c4  mov     rcx, [rbp+var_48]
0x18001e2c8  mov     rsi, [rbp+psa]
0x18001e2cc  jmp     short loc_18001E2DD
0x18001e2ce  mov     r15, [rbp+var_48]
0x18001e2d2  mov     rcx, rsi; psa
0x18001e2d5  mov     r13, [rbp+psa]
0x18001e2d9  mov     [rbp+var_30], r15
0x18001e2dd  test    rcx, rcx
0x18001e2e0  jz      short loc_18001E2E8
0x18001e2e2  call    cs:__imp_SafeArrayDestroy
0x18001e2e8  test    rsi, rsi
0x18001e2eb  jz      short loc_18001E2F6
0x18001e2ed  mov     rcx, rsi; psa
0x18001e2f0  call    cs:__imp_SafeArrayDestroy
0x18001e2f6  xor     esi, esi
0x18001e2f8  test    ebx, ebx
0x18001e2fa  jns     short loc_18001E30A
0x18001e2fc  mov     r9d, ebx
0x18001e2ff  mov     r8d, 98h
0x18001e305  jmp     loc_18001E3E1
0x18001e30a  mov     rcx, [rdi+8]; psz
0x18001e30e  call    cs:__imp_SysAllocString
0x18001e314  mov     r12, rax
0x18001e317  test    rax, rax
0x18001e31a  jnz     short loc_18001E32F
0x18001e31c  mov     ebx, 8007000Eh
0x18001e321  mov     r8d, 9Ch
0x18001e327  mov     r9d, ebx
0x18001e32a  jmp     loc_18001E3E1
0x18001e32f  cmp     [rdi+28h], esi
0x18001e332  jz      short loc_18001E33B
0x18001e334  mov     rax, [rdi]
0x18001e337  or      dword ptr [rax+38h], 40h
0x18001e33b  mov     rax, [rdi]
0x18001e33e  mov     ecx, [rax+3Ch]
0x18001e341  xchg    ecx, [rax+3Ch]
0x18001e344  test    ecx, ecx
0x18001e346  jz      short loc_18001E35B
0x18001e348  mov     ebx, 803C0100h
0x18001e34d  mov     r8d, 0B0h
0x18001e353  mov     r9d, ebx
0x18001e356  jmp     loc_18001E3E1
0x18001e35b  mov     rcx, [rdi]; this
0x18001e35e  lea     rdx, [rbp+pUnk]; struct IScriptedDiagnosticHost **
0x18001e362  call    ?get_Host@Settings@@QEAAJPEAPEAUIScriptedDiagnosticHost@@@Z; Settings::get_Host(IScriptedDiagnosticHost * *)
0x18001e367  mov     ebx, eax
0x18001e369  test    eax, eax
0x18001e36b  jns     short loc_18001E38D
0x18001e36d  mov     r9d, eax; int
0x18001e370  lea     rdx, aScriptRun; "Script::Run"
0x18001e377  mov     r8d, 0B4h; int
0x18001e37d  mov     ecx, 1; Level
0x18001e382  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e387  mov     r14, [rbp+pUnk]
0x18001e38b  jmp     short loc_18001E3F2
0x18001e38d  mov     r14, [rbp+pUnk]
0x18001e391  xor     edx, edx; lpvReserved
0x18001e393  mov     rcx, r14; pUnk
0x18001e396  call    cs:__imp_CoAllowSetForegroundWindow
0x18001e39c  test    eax, eax
0x18001e39e  jns     short loc_18001E3BA
0x18001e3a0  mov     r9d, eax; int
0x18001e3a3  lea     rdx, aScriptRun; "Script::Run"
0x18001e3aa  mov     r8d, 0B7h; int
0x18001e3b0  mov     ecx, 2; Level
0x18001e3b5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e3ba  mov     rax, [r14]
0x18001e3bd  mov     r9, r13
0x18001e3c0  mov     r8, r15
0x18001e3c3  mov     rdx, r12
0x18001e3c6  mov     rcx, r14
0x18001e3c9  mov     rax, [rax+20h]
0x18001e3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3d2  mov     ebx, eax
0x18001e3d4  test    eax, eax
0x18001e3d6  jns     short loc_18001E3F2
0x18001e3d8  mov     r8d, 0BAh; int
0x18001e3de  mov     r9d, eax; int
0x18001e3e1  lea     rdx, aScriptRun; "Script::Run"
0x18001e3e8  mov     ecx, 1; Level
0x18001e3ed  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e3f2  mov     rax, [rdi]
0x18001e3f5  test    rax, rax
0x18001e3f8  jz      short loc_18001E3FE
0x18001e3fa  and     dword ptr [rax+38h], 0FFFFFFBFh
0x18001e3fe  mov     rsi, [rdi+8]
0x18001e402  mov     [rbp+pUnk], 0
0x18001e40a  call    cs:__imp_GetTickCount64
0x18001e410  test    rsi, rsi
0x18001e413  jnz     short loc_18001E436
0x18001e415  mov     esi, 80070057h
0x18001e41a  lea     rdx, aScriptUpdatere; "Script::UpdateReport"
0x18001e421  mov     r9d, esi; int
0x18001e424  mov     r8d, 0E8h; int
0x18001e42a  mov     ecx, 1; Level
0x18001e42f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e434  jmp     short loc_18001E4B4
0x18001e436  sub     rax, [rbp+var_28]
0x18001e43a  lea     rcx, [rbp+pUnk]
0x18001e43e  mov     [rsp+78h+var_50], rcx; struct IXMLDOMDocument2 **
0x18001e443  mov     r9, r13; struct tagSAFEARRAY *
0x18001e446  mov     rcx, rdi; this
0x18001e449  mov     [rsp+78h+var_58], rax; unsigned __int64
0x18001e44e  mov     r8, r15; struct tagSAFEARRAY *
0x18001e451  mov     rdx, rsi; unsigned __int16 *
0x18001e454  call    ?BuildReportScriptXml@Script@@AEAAJPEAGPEAUtagSAFEARRAY@@1_KPEAPEAUIXMLDOMDocument2@@@Z; Script::BuildReportScriptXml(ushort *,tagSAFEARRAY *,tagSAFEARRAY *,unsigned __int64,IXMLDOMDocument2 * *)
0x18001e459  mov     r15, [rbp+pUnk]
0x18001e45d  mov     esi, eax
0x18001e45f  test    eax, eax
0x18001e461  jns     short loc_18001E46B
0x18001e463  mov     r8d, 0F4h
0x18001e469  jmp     short loc_18001E48C
0x18001e46b  mov     rcx, [rdi]
0x18001e46e  mov     r8d, 2
0x18001e474  mov     rdx, r15
0x18001e477  mov     rcx, [rcx+48h]
0x18001e47b  call    ?AddXmlToReport@Reporter@@QEAAJPEAUIXMLDOMDocument2@@W4_REPORT_AREA@1@@Z; Reporter::AddXmlToReport(IXMLDOMDocument2 *,Reporter::_REPORT_AREA)
0x18001e480  mov     esi, eax
0x18001e482  test    eax, eax
0x18001e484  jns     short loc_18001E4A0
0x18001e486  mov     r8d, 0FFh; int
0x18001e48c  mov     r9d, eax; int
0x18001e48f  lea     rdx, aScriptUpdatere; "Script::UpdateReport"
0x18001e496  mov     ecx, 1; Level
0x18001e49b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e4a0  test    r15, r15
0x18001e4a3  jz      short loc_18001E4B4
0x18001e4a5  mov     rax, [r15]
0x18001e4a8  mov     rcx, r15
0x18001e4ab  mov     rax, [rax+10h]
0x18001e4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4b4  test    ebx, ebx
0x18001e4b6  js      short loc_18001E4BD
0x18001e4b8  test    esi, esi
0x18001e4ba  cmovs   ebx, esi
0x18001e4bd  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 10h
0x18001e4c4  jz      short loc_18001E4E1
0x18001e4c6  lea     rax, [rbp+var_28]
0x18001e4ca  mov     r9d, 1
0x18001e4d0  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_PERF_SCRIPT_STOP
0x18001e4d7  mov     [rsp+78h+var_58], rax
0x18001e4dc  call    McGenEventWrite_EventWriteTransfer
0x18001e4e1  test    r12, r12
0x18001e4e4  jz      short loc_18001E4EF
0x18001e4e6  mov     rcx, r12; bstrString
0x18001e4e9  call    cs:__imp_SysFreeString
0x18001e4ef  mov     rcx, [rbp+var_30]; psa
0x18001e4f3  test    rcx, rcx
0x18001e4f6  jz      short loc_18001E4FE
0x18001e4f8  call    cs:__imp_SafeArrayDestroy
0x18001e4fe  test    r13, r13
0x18001e501  jz      short loc_18001E50C
0x18001e503  mov     rcx, r13; psa
0x18001e506  call    cs:__imp_SafeArrayDestroy
0x18001e50c  test    r14, r14
0x18001e50f  jz      short loc_18001E520
0x18001e511  mov     rax, [r14]
0x18001e514  mov     rcx, r14
0x18001e517  mov     rax, [rax+10h]
0x18001e51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e520  mov     eax, ebx
0x18001e522  mov     rcx, [rbp+var_18]
0x18001e526  xor     rcx, rsp; StackCookie
0x18001e529  call    __security_check_cookie
0x18001e52e  add     rsp, 78h
0x18001e532  pop     r15
0x18001e534  pop     r14
0x18001e536  pop     r13
0x18001e538  pop     r12
0x18001e53a  pop     rdi
0x18001e53b  pop     rsi
0x18001e53c  pop     rbx
0x18001e53d  pop     rbp
0x18001e53e  retn
```
