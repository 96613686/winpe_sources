# CScriptedDiag::Initialize(ushort *,IUnknown *,ushort *)

- ea: `0x18000cf00`
- end: `0x18000d635`
- name: `?Initialize@CScriptedDiag@@UEAAJPEAGPEAUIUnknown@@0@Z`
- size: `1845`
- prototype: `__int64 __fastcall(Settings **this, unsigned __int16 *, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180001264`
- `0x1800012a4`
- `0x1800026a0`
- `0x180004518`
- `0x180005d60`
- `0x18000a5b4`
- `0x18000a650`
- `0x18000b1c0`
- `0x18000bef0`
- `0x18000cf00`
- `0x18000dad4`
- `0x1800101cc`
- `0x1800130d0`
- `0x180013128`
- `0x1800131a8`
- `0x18001e75c`
- `0x18001ea08`
- `0x180020f6c`
- `0x180021914`
- `0x180026fa0`
- `0x1800280f8`
- `0x1800286a4`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18000cfa2`
- `KERNEL32!GetTickCount64` at `0x18000d515`
- `KERNEL32!GetTickCount64` at `0x18000cfa2`
- `KERNEL32!GetTickCount64` at `0x18000d515`

## string_xrefs

- `0x18000d587`: `PackagePath`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::Initialize(
        Settings **this,
        unsigned __int16 *a2,
        struct IUnknown *a3,
        unsigned __int16 *a4)
{
  struct IXMLDOMDocument2 *v5; // r12
  Reporter *v6; // rdi
  _QWORD *v7; // rsi
  struct IXMLDOMDocument2 *v8; // r13
  int LongPath; // eax
  CScriptedDiag *v10; // rcx
  __int64 v11; // r8
  int v12; // ebx
  int v13; // r8d
  int v14; // r9d
  const WCHAR *v15; // r14
  char v16; // al
  char *v17; // rax
  Settings *v18; // r14
  __int64 v19; // rbx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // r14d
  __int64 v23; // rcx
  char v24; // al
  LPCWSTR v25; // rdi
  void *v26; // r14
  __int64 v27; // rcx
  __int64 v28; // r8
  ULONGLONG TickCount64; // rax
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // r8
  int v34; // [rsp+90h] [rbp-E8h]
  int v35; // [rsp+94h] [rbp-E4h] BYREF
  unsigned int v36; // [rsp+98h] [rbp-E0h] BYREF
  void *Block; // [rsp+A0h] [rbp-D8h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-D0h] BYREF
  unsigned __int16 *v39; // [rsp+B0h] [rbp-C8h] BYREF
  LPCWSTR lpszShortPath; // [rsp+B8h] [rbp-C0h]
  int v41; // [rsp+C0h] [rbp-B8h] BYREF
  struct IXMLDOMDocument2 *v42; // [rsp+C8h] [rbp-B0h] BYREF
  struct IXMLDOMDocument2 *v43; // [rsp+D0h] [rbp-A8h] BYREF
  unsigned __int16 *v44; // [rsp+D8h] [rbp-A0h] BYREF
  struct IXMLDOMNodeList *v45; // [rsp+E0h] [rbp-98h] BYREF
  OLECHAR *psz; // [rsp+E8h] [rbp-90h]
  struct IUnknown *v47; // [rsp+F0h] [rbp-88h]
  _QWORD v48[2]; // [rsp+F8h] [rbp-80h] BYREF
  ULONGLONG v49[2]; // [rsp+108h] [rbp-70h] BYREF
  _BYTE v50[16]; // [rsp+118h] [rbp-60h] BYREF
  _QWORD *v51; // [rsp+128h] [rbp-50h]
  __int64 v52; // [rsp+130h] [rbp-48h]

  psz = a4;
  v47 = a3;
  lpszShortPath = a2;
  v5 = 0;
  v43 = 0;
  v6 = 0;
  LODWORD(v48[0]) = 0;
  v41 = 1;
  v7 = 0;
  v38 = 0;
  v8 = 0;
  v42 = 0;
  v36 = 0;
  v45 = 0;
  Block = 0;
  v34 = 0;
  v35 = 0;
  v44 = 0;
  v39 = 0;
  v49[0] = GetTickCount64();
  LongPath = CScriptedDiag::CheckAndSetState(this, v48, 1, 1);
  v12 = LongPath;
  if ( LongPath < 0 )
  {
    v13 = 136;
LABEL_3:
    v14 = LongPath;
LABEL_62:
    SdpDebugTrace(1u, L"CScriptedDiag::Initialize", v13, v14);
    if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 4) != 0 )
    {
      LODWORD(v48[0]) = v12;
      v51 = v48;
      v52 = 4;
      McGenEventWrite_EventWriteTransfer(v27, SCRIPTED_DIAGNOSTICS_EVENT_ERROR, v28, 2, v50);
    }
    v26 = Block;
    goto LABEL_65;
  }
  v15 = lpszShortPath;
  if ( !lpszShortPath )
  {
    v14 = -2147024809;
    v13 = 142;
LABEL_61:
    v12 = v14;
    goto LABEL_62;
  }
  if ( !this[3] )
  {
    v12 = -2147467261;
    v13 = 143;
LABEL_8:
    v14 = v12;
    goto LABEL_62;
  }
  v16 = Microsoft_Windows_Diagnosis_ScriptedEnableBits;
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 0x10) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(v10, SCRIPTED_DIAGNOSTICS_EVENT_PERF_INITIALIZE_START, v11, 1, v48);
    v16 = Microsoft_Windows_Diagnosis_ScriptedEnableBits;
  }
  if ( (v16 & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(v10, SCRIPTED_DIAGNOSTICS_EVENT_INITIALIZE_START, lpszShortPath);
  LongPath = CScriptedDiag::CheckGroupPolicy(v10, &v35);
  v12 = LongPath;
  if ( LongPath < 0 )
  {
    v13 = 153;
    goto LABEL_3;
  }
  if ( !v35 )
  {
    v12 = -2143551226;
    v13 = 157;
    goto LABEL_8;
  }
  v48[0] = operator new(0x18u);
  v7 = (_QWORD *)v48[0];
  if ( !v48[0] )
  {
    v7 = 0;
    v13 = 165;
    goto LABEL_60;
  }
  *(_DWORD *)(v48[0] + 8LL) = 1;
  *v7 = &CScriptedDiagInteraction::`vftable';
  v7[2] = 0;
  _InterlockedIncrement(&g_Count);
  v7[2] = this;
  LongPath = (*(__int64 (__fastcall **)(_QWORD *, GUID *, char *))*v7)(
               v7,
               &IID_IScriptedDiagnosticInteraction,
               (char *)this + 40);
  v12 = LongPath;
  if ( LongPath < 0 )
  {
    v13 = 172;
    goto LABEL_3;
  }
  LongPath = SdpGetLongPath(v15, &v39);
  v12 = LongPath;
  if ( LongPath < 0 )
  {
    v13 = 175;
    goto LABEL_3;
  }
  LongPath = SdpGetLocale(v39, &v44);
  v12 = LongPath;
  if ( LongPath < 0 )
  {
    v13 = 178;
    goto LABEL_3;
  }
  if ( v44 )
  {
    LongPath = Settings::set_Locale(this[3], v44);
    v12 = LongPath;
    if ( LongPath < 0 )
    {
      v13 = 182;
      goto LABEL_3;
    }
  }
  LongPath = CScriptedDiag::SecurePackage((CScriptedDiag *)this, v39);
  v12 = LongPath;
  if ( LongPath < 0 )
  {
    v13 = 186;
    goto LABEL_3;
  }
  v17 = (char *)operator new(0x48u);
  v48[0] = v17;
  v6 = (Reporter *)v17;
  if ( !v17 )
  {
    v6 = 0;
    v13 = 193;
LABEL_60:
    v14 = -2147024882;
    goto LABEL_61;
  }
  *((_QWORD *)v17 + 6) = 0;
  *((_QWORD *)v17 + 7) = 0;
  *((_QWORD *)v17 + 8) = 0;
  *(_OWORD *)(v17 + 24) = 0;
  *((_QWORD *)v17 + 5) = 0;
  *(_OWORD *)v17 = 0;
  *((_QWORD *)v17 + 2) = 0;
  LongPath = Reporter::Initialize((Reporter *)v17, this[3]);
  v12 = LongPath;
  if ( LongPath < 0 )
  {
    v13 = 196;
    goto LABEL_3;
  }
  *((_QWORD *)this[3] + 9) = v6;
  v6 = 0;
  if ( v47 )
  {
    LongPath = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v47->lpVtbl->QueryInterface)(
                 v47,
                 &IID_IScriptedDiagnosticClient,
                 &v38);
    v12 = LongPath;
    if ( LongPath < 0 )
    {
      v13 = 210;
      goto LABEL_3;
    }
  }
  v18 = this[3];
  v19 = v38;
  v20 = *((_QWORD *)v18 + 10);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  *((_QWORD *)v18 + 10) = v19;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
  if ( psz )
  {
    LongPath = SdpXmlCreate(psz, &v42);
    v8 = v42;
    v12 = LongPath;
    if ( LongPath < 0 )
    {
      v13 = 225;
      goto LABEL_3;
    }
  }
  LongPath = CScriptedDiag::GetPackageXml((CScriptedDiag *)this, &v43);
  v5 = v43;
  v12 = LongPath;
  if ( LongPath < 0 )
  {
    v13 = 229;
    goto LABEL_3;
  }
  v21 = CScriptedDiag::InitializePackage((CScriptedDiag *)this, v43, v8);
  v34 = v21;
  v22 = v21;
  if ( v21 < 0 )
  {
    v12 = v21;
    v13 = 238;
    v14 = v21;
    goto LABEL_62;
  }
  if ( v8 )
  {
    LongPath = SdpXmlGetChildNodes(v8, 0, &v45, &v36);
    v12 = LongPath;
    if ( LongPath < 0 )
    {
      v13 = 247;
      goto LABEL_3;
    }
    if ( v36 )
    {
      v14 = -2147024809;
      v13 = 251;
      goto LABEL_61;
    }
  }
  LongPath = Settings::get_PackageId(this[3], (unsigned __int16 **)&Block);
  v12 = LongPath;
  if ( LongPath < 0 )
  {
    v13 = 256;
    goto LABEL_3;
  }
  *((_DWORD *)this + 12) |= 0x40u;
  v24 = Microsoft_Windows_Diagnosis_ScriptedEnableBits;
  v25 = lpszShortPath;
  v34 = v22;
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 2) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v23, SCRIPTED_DIAGNOSTICS_EVENT_INITIALIZE_END, lpszShortPath);
    v24 = Microsoft_Windows_Diagnosis_ScriptedEnableBits;
  }
  v26 = Block;
  if ( (v24 & 1) != 0 )
    McTemplateU0zz_EventWriteTransfer(v23, SCRIPTED_DIAGNOSTICS_EVENT_PACKAGE_INFO, v25, Block);
  v6 = 0;
LABEL_65:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v6 )
  {
    Reporter::~Reporter(v6);
    operator delete(v6);
  }
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v8->lpVtbl->Release)(v8);
  if ( v45 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v45->lpVtbl->Release)(v45);
  if ( v26 )
    operator delete(v26);
  if ( v44 )
    operator delete(v44);
  if ( v39 )
    operator delete(v39);
  TickCount64 = GetTickCount64();
  v30 = SdpRecordMethodCall(
          this[3],
          L"Initialize",
          TickCount64 - v49[0],
          v12,
          3u,
          L"PackagePath",
          8,
          1,
          lpszShortPath,
          L"Client",
          13,
          1,
          v47,
          L"Answer",
          8,
          1,
          psz);
  if ( v12 >= 0 )
  {
    if ( v30 >= 0 )
    {
      if ( v34 == 3932421 )
        v12 = 3932421;
    }
    else
    {
      v12 = v30;
    }
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(v31, SCRIPTED_DIAGNOSTICS_EVENT_PERF_INITIALIZE_STOP, v32, 1, v49);
  CScriptedDiag::ExitUpdateState(this, (unsigned int)v12, 0, &v41);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000cf00  mov     r11, rsp
0x18000cf03  push    rbx
0x18000cf04  push    rsi
0x18000cf05  push    rdi
0x18000cf06  push    r12
0x18000cf08  push    r13
0x18000cf0a  push    r14
0x18000cf0c  push    r15
0x18000cf0e  sub     rsp, 140h
0x18000cf15  mov     rax, cs:__security_cookie
0x18000cf1c  xor     rax, rsp
0x18000cf1f  mov     [rsp+178h+var_40], rax
0x18000cf27  xor     eax, eax
0x18000cf29  mov     [rsp+178h+psz], r9
0x18000cf31  mov     [rsp+178h+var_88], r8
0x18000cf39  mov     r15, rcx
0x18000cf3c  mov     [rsp+178h+lpszShortPath], rdx
0x18000cf44  mov     r12d, eax
0x18000cf47  mov     [r11-0A8h], rax
0x18000cf4e  mov     edi, eax
0x18000cf50  lea     ebx, [rax+1]
0x18000cf53  mov     [r11-80h], eax
0x18000cf57  mov     [rsp+178h+var_B8], ebx
0x18000cf5e  mov     esi, eax
0x18000cf60  mov     [r11-0D0h], rax
0x18000cf67  mov     r13d, eax
0x18000cf6a  mov     [r11-0B0h], rax
0x18000cf71  mov     [rsp+178h+var_E0], eax
0x18000cf78  mov     [r11-98h], rax
0x18000cf7f  mov     [r11-0D8h], rax
0x18000cf86  mov     [rsp+178h+var_E8], eax
0x18000cf8d  mov     [rsp+178h+var_E4], eax
0x18000cf94  mov     [r11-0A0h], rax
0x18000cf9b  mov     [r11-0C8h], rax
0x18000cfa2  call    cs:__imp_GetTickCount64
0x18000cfa8  mov     r9d, ebx
0x18000cfab  lea     rdx, [rsp+178h+var_80]
0x18000cfb3  mov     r8d, ebx
0x18000cfb6  mov     [rsp+178h+var_70], rax
0x18000cfbe  mov     rcx, r15
0x18000cfc1  call    ?CheckAndSetState@CScriptedDiag@@AEAAJPEAW4SDIAG_ENGINE_STATE@Settings@@KW423@@Z; CScriptedDiag::CheckAndSetState(Settings::SDIAG_ENGINE_STATE *,ulong,Settings::SDIAG_ENGINE_STATE)
0x18000cfc6  mov     ebx, eax
0x18000cfc8  test    eax, eax
0x18000cfca  jns     short loc_18000CFDA
0x18000cfcc  mov     r8d, 88h
0x18000cfd2  mov     r9d, eax
0x18000cfd5  jmp     loc_18000D3D4
0x18000cfda  mov     r14, [rsp+178h+lpszShortPath]
0x18000cfe2  test    r14, r14
0x18000cfe5  jnz     short loc_18000CFF8
0x18000cfe7  mov     r9d, 80070057h
0x18000cfed  mov     r8d, 8Eh
0x18000cff3  jmp     loc_18000D3D1
0x18000cff8  cmp     [r15+18h], rsi
0x18000cffc  jnz     short loc_18000D011
0x18000cffe  mov     ebx, 80004003h
0x18000d003  mov     r8d, 8Fh
0x18000d009  mov     r9d, ebx
0x18000d00c  jmp     loc_18000D3D4
0x18000d011  mov     eax, cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits
0x18000d017  test    al, 10h
0x18000d019  jz      short loc_18000D040
0x18000d01b  lea     rax, [rsp+178h+var_80]
0x18000d023  mov     r9d, 1
0x18000d029  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_PERF_INITIALIZE_START
0x18000d030  mov     qword ptr [rsp+178h+var_158], rax
0x18000d035  call    McGenEventWrite_EventWriteTransfer
0x18000d03a  mov     eax, cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits
0x18000d040  test    al, 2
0x18000d042  jz      short loc_18000D053
0x18000d044  mov     r8, r14
0x18000d047  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_INITIALIZE_START
0x18000d04e  call    McTemplateU0z_EventWriteTransfer
0x18000d053  lea     rdx, [rsp+178h+var_E4]; int *
0x18000d05b  call    ?CheckGroupPolicy@CScriptedDiag@@AEAAJPEAH@Z; CScriptedDiag::CheckGroupPolicy(int *)
0x18000d060  mov     ebx, eax
0x18000d062  test    eax, eax
0x18000d064  jns     short loc_18000D071
0x18000d066  mov     r8d, 99h
0x18000d06c  jmp     loc_18000CFD2
0x18000d071  cmp     [rsp+178h+var_E4], esi
0x18000d078  jnz     short loc_18000D087
0x18000d07a  mov     ebx, 803C0106h
0x18000d07f  mov     r8d, 9Dh
0x18000d085  jmp     short loc_18000D009
0x18000d087  mov     ecx, 18h; Size
0x18000d08c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d091  mov     [rsp+178h+var_80], rax
0x18000d099  mov     rsi, rax
0x18000d09c  test    rax, rax
0x18000d09f  jz      loc_18000D3C3
0x18000d0a5  lea     rax, ??_7CScriptedDiagInteraction@@6B@; const CScriptedDiagInteraction::`vftable'
0x18000d0ac  mov     dword ptr [rsi+8], 1
0x18000d0b3  mov     [rsi], rax
0x18000d0b6  mov     [rsi+10h], rdi
0x18000d0ba  lock inc cs:?g_Count@@3JA; long g_Count
0x18000d0c1  test    rsi, rsi
0x18000d0c4  jz      loc_18000D3C5
0x18000d0ca  mov     [rsi+10h], r15
0x18000d0ce  mov     rax, [rsi]
0x18000d0d1  lea     r8, [r15+28h]
0x18000d0d5  lea     rdx, IID_IScriptedDiagnosticInteraction
0x18000d0dc  mov     rcx, rsi
0x18000d0df  mov     rax, [rax]
0x18000d0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0e7  mov     ebx, eax
0x18000d0e9  test    eax, eax
0x18000d0eb  jns     short loc_18000D0F8
0x18000d0ed  mov     r8d, 0ACh
0x18000d0f3  jmp     loc_18000CFD2
0x18000d0f8  lea     rdx, [rsp+178h+var_C8]; unsigned __int16 **
0x18000d100  mov     rcx, r14; lpszShortPath
0x18000d103  call    ?SdpGetLongPath@@YAJPEBGPEAPEAG@Z; SdpGetLongPath(ushort const *,ushort * *)
0x18000d108  mov     ebx, eax
0x18000d10a  test    eax, eax
0x18000d10c  jns     short loc_18000D119
0x18000d10e  mov     r8d, 0AFh
0x18000d114  jmp     loc_18000CFD2
0x18000d119  mov     rcx, [rsp+178h+var_C8]; unsigned __int16 *
0x18000d121  lea     rdx, [rsp+178h+var_A0]; unsigned __int16 **
0x18000d129  call    ?SdpGetLocale@@YAJPEAGPEAPEAG@Z; SdpGetLocale(ushort *,ushort * *)
0x18000d12e  mov     ebx, eax
0x18000d130  test    eax, eax
0x18000d132  jns     short loc_18000D13F
0x18000d134  mov     r8d, 0B2h
0x18000d13a  jmp     loc_18000CFD2
0x18000d13f  mov     r14, [rsp+178h+var_A0]
0x18000d147  test    r14, r14
0x18000d14a  jz      short loc_18000D169
0x18000d14c  mov     rcx, [r15+18h]; this
0x18000d150  mov     rdx, r14; unsigned __int16 *
0x18000d153  call    ?set_Locale@Settings@@QEAAJPEBG@Z; Settings::set_Locale(ushort const *)
0x18000d158  mov     ebx, eax
0x18000d15a  test    eax, eax
0x18000d15c  jns     short loc_18000D169
0x18000d15e  mov     r8d, 0B6h
0x18000d164  jmp     loc_18000CFD2
0x18000d169  mov     rdx, [rsp+178h+var_C8]; unsigned __int16 *
0x18000d171  mov     rcx, r15; this
0x18000d174  call    ?SecurePackage@CScriptedDiag@@AEAAJPEBG@Z; CScriptedDiag::SecurePackage(ushort const *)
0x18000d179  mov     ebx, eax
0x18000d17b  test    eax, eax
0x18000d17d  jns     short loc_18000D18A
0x18000d17f  mov     r8d, 0BAh
0x18000d185  jmp     loc_18000CFD2
0x18000d18a  mov     ecx, 48h ; 'H'; Size
0x18000d18f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d194  mov     [rsp+178h+var_80], rax
0x18000d19c  mov     rdi, rax
0x18000d19f  test    rax, rax
0x18000d1a2  jz      loc_18000D3B9
0x18000d1a8  mov     [rax+30h], r12
0x18000d1ac  xorps   xmm0, xmm0
0x18000d1af  mov     [rax+38h], r12
0x18000d1b3  xorps   xmm1, xmm1
0x18000d1b6  mov     [rax+40h], r12
0x18000d1ba  xor     eax, eax
0x18000d1bc  movups  xmmword ptr [rdi+18h], xmm0
0x18000d1c0  mov     [rdi+28h], rax
0x18000d1c4  movups  xmmword ptr [rdi], xmm1
0x18000d1c7  mov     [rdi+10h], rax
0x18000d1cb  test    rdi, rdi
0x18000d1ce  jz      loc_18000D3BB
0x18000d1d4  mov     rdx, [r15+18h]; struct Settings *
0x18000d1d8  mov     rcx, rdi; this
0x18000d1db  call    ?Initialize@Reporter@@QEAAJPEAVSettings@@@Z; Reporter::Initialize(Settings *)
0x18000d1e0  mov     ebx, eax
0x18000d1e2  test    eax, eax
0x18000d1e4  jns     short loc_18000D1F1
0x18000d1e6  mov     r8d, 0C4h
0x18000d1ec  jmp     loc_18000CFD2
0x18000d1f1  mov     rax, [r15+18h]
0x18000d1f5  mov     [rax+48h], rdi
0x18000d1f9  mov     rcx, [rsp+178h+var_88]
0x18000d201  xor     edi, edi
0x18000d203  test    rcx, rcx
0x18000d206  jz      short loc_18000D233
0x18000d208  mov     rax, [rcx]
0x18000d20b  lea     r8, [rsp+178h+var_D0]
0x18000d213  lea     rdx, IID_IScriptedDiagnosticClient
0x18000d21a  mov     rax, [rax]
0x18000d21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d222  mov     ebx, eax
0x18000d224  test    eax, eax
0x18000d226  jns     short loc_18000D233
0x18000d228  mov     r8d, 0D2h
0x18000d22e  jmp     loc_18000CFD2
0x18000d233  mov     r14, [r15+18h]
0x18000d237  mov     rbx, [rsp+178h+var_D0]
0x18000d23f  mov     rcx, [r14+50h]
0x18000d243  test    rcx, rcx
0x18000d246  jz      short loc_18000D254
0x18000d248  mov     rax, [rcx]
0x18000d24b  mov     rax, [rax+10h]
0x18000d24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d254  mov     [r14+50h], rbx
0x18000d258  test    rbx, rbx
0x18000d25b  jz      short loc_18000D26C
0x18000d25d  mov     rax, [rbx]
0x18000d260  mov     rcx, rbx
0x18000d263  mov     rax, [rax+8]
0x18000d267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d26c  mov     rax, [rsp+178h+psz]
0x18000d274  test    rax, rax
0x18000d277  jz      short loc_18000D2A2
0x18000d279  lea     rdx, [rsp+178h+var_B0]; struct IXMLDOMDocument2 **
0x18000d281  mov     rcx, rax; psz
0x18000d284  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18000d289  mov     r13, [rsp+178h+var_B0]
0x18000d291  mov     ebx, eax
0x18000d293  test    eax, eax
0x18000d295  jns     short loc_18000D2A2
0x18000d297  mov     r8d, 0E1h
0x18000d29d  jmp     loc_18000CFD2
0x18000d2a2  lea     rdx, [rsp+178h+var_A8]; struct IXMLDOMDocument2 **
0x18000d2aa  mov     rcx, r15; this
0x18000d2ad  call    ?GetPackageXml@CScriptedDiag@@AEAAJPEAPEAUIXMLDOMDocument2@@@Z; CScriptedDiag::GetPackageXml(IXMLDOMDocument2 * *)
0x18000d2b2  mov     r12, [rsp+178h+var_A8]
0x18000d2ba  mov     ebx, eax
0x18000d2bc  test    eax, eax
0x18000d2be  jns     short loc_18000D2CB
0x18000d2c0  mov     r8d, 0E5h
0x18000d2c6  jmp     loc_18000CFD2
0x18000d2cb  mov     r8, r13; struct IXMLDOMDocument2 *
0x18000d2ce  mov     rdx, r12; struct IXMLDOMDocument2 *
0x18000d2d1  mov     rcx, r15; this
0x18000d2d4  call    ?InitializePackage@CScriptedDiag@@AEAAJPEAUIXMLDOMDocument2@@0@Z; CScriptedDiag::InitializePackage(IXMLDOMDocument2 *,IXMLDOMDocument2 *)
0x18000d2d9  mov     [rsp+178h+var_E8], eax
0x18000d2e0  mov     r14d, eax
0x18000d2e3  test    eax, eax
0x18000d2e5  jns     short loc_18000D2F7
0x18000d2e7  mov     ebx, eax
0x18000d2e9  mov     r8d, 0EEh
0x18000d2ef  mov     r9d, eax
0x18000d2f2  jmp     loc_18000D3D4
0x18000d2f7  test    r13, r13
0x18000d2fa  jz      short loc_18000D341
0x18000d2fc  lea     r9, [rsp+178h+var_E0]; unsigned int *
0x18000d304  xor     edx, edx; struct IXMLDOMNode *
0x18000d306  lea     r8, [rsp+178h+var_98]; struct IXMLDOMNodeList **
0x18000d30e  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000d311  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18000d316  mov     ebx, eax
0x18000d318  test    eax, eax
0x18000d31a  jns     short loc_18000D327
0x18000d31c  mov     r8d, 0F7h
0x18000d322  jmp     loc_18000CFD2
0x18000d327  cmp     [rsp+178h+var_E0], edi
0x18000d32e  jbe     short loc_18000D341
0x18000d330  mov     r9d, 80070057h
0x18000d336  mov     r8d, 0FBh
0x18000d33c  jmp     loc_18000D3D1
0x18000d341  mov     rcx, [r15+18h]; this
0x18000d345  lea     rdx, [rsp+178h+Block]; unsigned __int16 **
0x18000d34d  call    ?get_PackageId@Settings@@QEAAJPEAPEAG@Z; Settings::get_PackageId(ushort * *)
0x18000d352  mov     ebx, eax
0x18000d354  test    eax, eax
0x18000d356  jns     short loc_18000D363
0x18000d358  mov     r8d, 100h
0x18000d35e  jmp     loc_18000CFD2
0x18000d363  or      dword ptr [r15+30h], 40h
0x18000d368  mov     eax, cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits
0x18000d36e  mov     rdi, [rsp+178h+lpszShortPath]
0x18000d376  mov     [rsp+178h+var_E8], r14d
0x18000d37e  test    al, 2
0x18000d380  jz      short loc_18000D397
0x18000d382  mov     r8, rdi
0x18000d385  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_INITIALIZE_END
0x18000d38c  call    McTemplateU0z_EventWriteTransfer
0x18000d391  mov     eax, cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits
0x18000d397  mov     r14, [rsp+178h+Block]
0x18000d39f  test    al, 1
0x18000d3a1  jz      short loc_18000D3B5
0x18000d3a3  mov     r9, r14
0x18000d3a6  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_PACKAGE_INFO
0x18000d3ad  mov     r8, rdi
0x18000d3b0  call    McTemplateU0zz_EventWriteTransfer
0x18000d3b5  xor     edi, edi
0x18000d3b7  jmp     short loc_18000D438
0x18000d3b9  xor     edi, edi
0x18000d3bb  mov     r8d, 0C1h
0x18000d3c1  jmp     short loc_18000D3CB
0x18000d3c3  xor     esi, esi
0x18000d3c5  mov     r8d, 0A5h; int
0x18000d3cb  mov     r9d, 8007000Eh; int
0x18000d3d1  mov     ebx, r9d
0x18000d3d4  lea     rdx, aCscripteddiagI_2; "CScriptedDiag::Initialize"
0x18000d3db  mov     ecx, 1; Level
0x18000d3e0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000d3e5  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 4
0x18000d3ec  jz      short loc_18000D430
0x18000d3ee  lea     rax, [rsp+178h+var_80]
0x18000d3f6  mov     dword ptr [rsp+178h+var_80], ebx
0x18000d3fd  mov     [rsp+178h+var_50], rax
0x18000d405  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_ERROR
0x18000d40c  lea     rax, [rsp+178h+var_60]
0x18000d414  mov     [rsp+178h+var_48], 4
0x18000d420  mov     r9d, 2
0x18000d426  mov     qword ptr [rsp+178h+var_158], rax
0x18000d42b  call    McGenEventWrite_EventWriteTransfer
  ... truncated ...
```
