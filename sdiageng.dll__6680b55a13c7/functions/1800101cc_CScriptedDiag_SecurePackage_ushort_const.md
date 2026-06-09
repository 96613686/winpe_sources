# CScriptedDiag::SecurePackage(ushort const *)

- ea: `0x1800101cc`
- end: `0x180010669`
- name: `?SecurePackage@CScriptedDiag@@AEAAJPEBG@Z`
- size: `1181`
- prototype: `__int64 __fastcall(CScriptedDiag *this, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000cf00`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x18000a86c`
- `0x18000c3fc`
- `0x1800101cc`
- `0x1800114dc`
- `0x180011888`
- `0x180011ba4`
- `0x1800130d0`
- `0x180026dec`
- `0x180026fa0`
- `0x18002708c`
- `0x18002758c`
- `0x180027aa0`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800103ad`
- `KERNEL32!GetLastError` at `0x18001051e`
- `KERNEL32!GetLastError` at `0x1800103ad`
- `KERNEL32!GetLastError` at `0x18001051e`
- `KERNEL32!CreateDirectoryW` at `0x1800103a3`
- `KERNEL32!CreateDirectoryW` at `0x180010514`
- `KERNEL32!CreateDirectoryW` at `0x1800103a3`
- `KERNEL32!CreateDirectoryW` at `0x180010514`
- `KERNEL32!LocalFree` at `0x180010639`
- `KERNEL32!LocalFree` at `0x180010639`

## string_xrefs

- `0x180010401`: `Settings::set_PackagePath`
- `0x180010438`: `Settings::set_PackagePath`
- `0x180010554`: `Settings::set_ResultPath`
- `0x180010588`: `Settings::set_ResultPath`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::SecurePackage(CScriptedDiag *this, const unsigned __int16 *a2, __int64 a3)
{
  unsigned __int16 *v3; // r12
  WCHAR *v4; // rdi
  unsigned __int16 *v5; // r15
  signed int v8; // ebx
  int v9; // r8d
  int FullPath; // eax
  WCHAR *v11; // rcx
  __int64 v12; // r8
  int v13; // ebx
  int v14; // r8d
  int v15; // r14d
  int IsSubDirectory; // eax
  int v17; // r9d
  __int64 v18; // rdx
  CScriptedDiag *v19; // rcx
  int TempPackagePath; // eax
  CScriptedDiag *v21; // rcx
  int v22; // eax
  unsigned int v23; // ecx
  int v24; // eax
  signed int LastError; // eax
  int v26; // eax
  int v27; // r14d
  __int64 v28; // rbx
  int v29; // eax
  WCHAR *v30; // rcx
  void *v31; // rcx
  int v32; // eax
  int v33; // eax
  int v34; // eax
  signed int v35; // eax
  __int64 v36; // rsi
  int v37; // eax
  void *v38; // rcx
  void *Block; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR lpPathName; // [rsp+38h] [rbp-48h] BYREF
  LPCWSTR v42; // [rsp+40h] [rbp-40h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v44[16]; // [rsp+60h] [rbp-20h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = 0;
  Block = 0;
  lpPathName = 0;
  v42 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(this, SCRIPTED_DIAGNOSTICS_EVENT_PERF_TRUST_START, a3, 1, v44);
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = 1325;
LABEL_63:
    v17 = v8;
    goto LABEL_64;
  }
  if ( !*((_QWORD *)this + 3) )
  {
    v8 = -2147467261;
    v9 = 1327;
    goto LABEL_63;
  }
  FullPath = SdpGetFullPath(a2, (unsigned __int16 **)&Block, 0);
  v8 = FullPath;
  if ( FullPath < 0 )
  {
    SdpDebugTrace(1u, L"CScriptedDiag::SecurePackage", 1330, FullPath);
    v3 = (unsigned __int16 *)Block;
    goto LABEL_65;
  }
  v3 = (unsigned __int16 *)Block;
  LODWORD(Block) = 0;
  if ( !v3 )
  {
    v13 = -2147024809;
    v14 = 1679;
    v15 = -2147024809;
LABEL_13:
    SdpDebugTrace(1u, L"CScriptedDiag::IsInboxPackage", v14, v13);
    v17 = v15;
    v9 = 1333;
    v8 = v15;
LABEL_64:
    SdpDebugTrace(1u, L"CScriptedDiag::SecurePackage", v9, v17);
    goto LABEL_65;
  }
  IsSubDirectory = SdpIsSubDirectory(L"%SystemRoot%\\Diagnostics", v3, (int *)&Block);
  v15 = IsSubDirectory;
  if ( IsSubDirectory < 0 )
  {
    v14 = 1683;
    v13 = IsSubDirectory;
    goto LABEL_13;
  }
  v18 = *((_QWORD *)this + 3);
  v19 = (CScriptedDiag *)*(unsigned int *)(v18 + 56);
  LODWORD(v19) = (unsigned int)v19 | 0x200;
  if ( !(_DWORD)Block )
    v19 = (CScriptedDiag *)(*(_DWORD *)(v18 + 56) & 0xFFFFFDFF);
  *(_DWORD *)(v18 + 56) = (_DWORD)v19;
  TempPackagePath = CScriptedDiag::GetTempPackagePath(v19, (unsigned __int16 **)&lpPathName);
  v8 = TempPackagePath;
  if ( TempPackagePath < 0 )
  {
    SdpDebugTrace(1u, L"CScriptedDiag::SecurePackage", 1339, TempPackagePath);
    v4 = (WCHAR *)lpPathName;
    goto LABEL_65;
  }
  v4 = (WCHAR *)lpPathName;
  v22 = CScriptedDiag::ValidatePackagePath(v21, lpPathName);
  v8 = v22;
  if ( v22 < 0 )
  {
    v17 = v22;
    v9 = 1342;
    goto LABEL_64;
  }
  v24 = SdpCreateSecurityDescriptor(v23, &SecurityAttributes);
  v8 = v24;
  if ( v24 < 0 )
  {
    v17 = v24;
    v9 = 1345;
    goto LABEL_64;
  }
  if ( !CreateDirectoryW(v4, &SecurityAttributes) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = 1348;
      goto LABEL_63;
    }
  }
  v26 = CScriptedDiag::CopyPackage(this, v3, v4);
  v8 = v26;
  if ( v26 < 0 )
  {
    v17 = v26;
    v9 = 1351;
    goto LABEL_64;
  }
  lpPathName = 0;
  if ( !v4 )
  {
    v27 = -2147024809;
    SdpDebugTrace(1u, L"Settings::set_PackagePath", 139, -2147024809);
LABEL_39:
    v8 = v27;
    v17 = v27;
    v9 = 1354;
    goto LABEL_64;
  }
  v28 = *((_QWORD *)this + 3);
  v29 = SdpStrCpy((unsigned __int16 **)&lpPathName, v4);
  v27 = v29;
  if ( v29 >= 0 )
  {
    v31 = *(void **)(v28 + 8);
    if ( v31 )
      operator delete(v31);
    v30 = 0;
    *(_QWORD *)(v28 + 8) = lpPathName;
  }
  else
  {
    SdpDebugTrace(1u, L"Settings::set_PackagePath", 142, v29);
    v30 = (WCHAR *)lpPathName;
  }
  if ( v30 )
    operator delete(v30);
  if ( v27 < 0 )
    goto LABEL_39;
  if ( (_DWORD)Block )
  {
    *((_DWORD *)this + 12) |= 2u;
    v32 = CScriptedDiag::VerifyInboxPackageTrust(this, v4);
    v8 = v32;
    if ( v32 < 0 )
    {
      v17 = v32;
      v9 = 1364;
      goto LABEL_64;
    }
  }
  else
  {
    v33 = CScriptedDiag::VerifyPackageTrust(this, v4);
    v8 = v33;
    if ( v33 < 0 )
    {
      v17 = v33;
      v9 = 1368;
      goto LABEL_64;
    }
  }
  v34 = SdpBuildPath(v4, L"result", (unsigned __int16 **)&v42);
  v8 = v34;
  if ( v34 < 0 )
  {
    SdpDebugTrace(1u, L"CScriptedDiag::SecurePackage", 1372, v34);
    v5 = (unsigned __int16 *)v42;
    goto LABEL_65;
  }
  v5 = (unsigned __int16 *)v42;
  if ( !CreateDirectoryW(v42, 0) )
  {
    v35 = GetLastError();
    v8 = v35;
    if ( v35 > 0 )
      v8 = (unsigned __int16)v35 | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = 1375;
      goto LABEL_63;
    }
  }
  v42 = 0;
  if ( !v5 )
  {
    v8 = -2147024809;
    SdpDebugTrace(1u, L"Settings::set_ResultPath", 322, -2147024809);
LABEL_62:
    v9 = 1378;
    goto LABEL_63;
  }
  v36 = *((_QWORD *)this + 3);
  v37 = SdpStrCpy((unsigned __int16 **)&v42, v5);
  v8 = v37;
  if ( v37 >= 0 )
  {
    v38 = *(void **)(v36 + 24);
    if ( v38 )
      operator delete(v38);
    v11 = 0;
    *(_QWORD *)(v36 + 24) = v42;
  }
  else
  {
    SdpDebugTrace(1u, L"Settings::set_ResultPath", 325, v37);
    v11 = (WCHAR *)v42;
  }
  if ( v11 )
    operator delete(v11);
  if ( v8 < 0 )
    goto LABEL_62;
LABEL_65:
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(v11, SCRIPTED_DIAGNOSTICS_EVENT_PERF_TRUST_STOP, v12, 1, v44);
  if ( v3 )
    operator delete(v3);
  if ( v4 )
    operator delete(v4);
  if ( v5 )
    operator delete(v5);
  if ( SecurityAttributes.lpSecurityDescriptor )
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800101cc  mov     [rsp-28h+arg_10], rbx
0x1800101d1  mov     [rsp-28h+arg_18], rsi
0x1800101d6  push    rbp
0x1800101d7  push    rdi
0x1800101d8  push    r12
0x1800101da  push    r14
0x1800101dc  push    r15
0x1800101de  mov     rbp, rsp
0x1800101e1  sub     rsp, 80h
0x1800101e8  mov     rax, cs:__security_cookie
0x1800101ef  xor     rax, rsp
0x1800101f2  mov     [rbp+var_10], rax
0x1800101f6  xor     r12d, r12d
0x1800101f9  xor     edi, edi
0x1800101fb  xor     r15d, r15d
0x1800101fe  mov     [rbp+Block], r12
0x180010202  xor     eax, eax
0x180010204  mov     [rbp+lpPathName], rdi
0x180010208  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 10h
0x18001020f  xorps   xmm0, xmm0
0x180010212  mov     rbx, rdx
0x180010215  mov     [rbp+var_40], r15
0x180010219  mov     rsi, rcx
0x18001021c  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x180010220  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x180010224  jz      short loc_180010240
0x180010226  lea     rax, [rbp+var_20]
0x18001022a  lea     r9d, [r12+1]
0x18001022f  mov     [rsp+80h+var_60], rax
0x180010234  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_PERF_TRUST_START
0x18001023b  call    McGenEventWrite_EventWriteTransfer
0x180010240  xor     eax, eax
0x180010242  xorps   xmm0, xmm0
0x180010245  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x180010249  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x18001024d  test    rbx, rbx
0x180010250  jnz     short loc_180010262
0x180010252  mov     ebx, 80070057h
0x180010257  mov     r8d, 52Dh
0x18001025d  jmp     loc_1800105D1
0x180010262  cmp     [rsi+18h], rax
0x180010266  jnz     short loc_180010278
0x180010268  mov     ebx, 80004003h
0x18001026d  mov     r8d, 52Fh
0x180010273  jmp     loc_1800105D1
0x180010278  xor     r8d, r8d; unsigned __int16 **
0x18001027b  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18001027f  mov     rcx, rbx; unsigned __int16 *
0x180010282  call    ?SdpGetFullPath@@YAJPEBGPEAPEAG1@Z; SdpGetFullPath(ushort const *,ushort * *,ushort * *)
0x180010287  mov     ebx, eax
0x180010289  test    eax, eax
0x18001028b  jns     short loc_1800102B0
0x18001028d  mov     r9d, eax; int
0x180010290  lea     rdx, aCscripteddiagS; "CScriptedDiag::SecurePackage"
0x180010297  mov     r8d, 532h; int
0x18001029d  mov     ecx, 1; Level
0x1800102a2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800102a7  mov     r12, [rbp+Block]
0x1800102ab  jmp     loc_1800105E5
0x1800102b0  mov     r12, [rbp+Block]
0x1800102b4  mov     dword ptr [rbp+Block], edi
0x1800102b7  test    r12, r12
0x1800102ba  jnz     short loc_1800102CC
0x1800102bc  mov     ebx, 80070057h
0x1800102c1  mov     r8d, 68Fh
0x1800102c7  mov     r14d, ebx
0x1800102ca  jmp     short loc_1800102EE
0x1800102cc  lea     r8, [rbp+Block]; int *
0x1800102d0  mov     rdx, r12; unsigned __int16 *
0x1800102d3  lea     rcx, aSystemrootDiag; "%SystemRoot%\\Diagnostics"
0x1800102da  call    ?SdpIsSubDirectory@@YAJPEBG0PEAH@Z; SdpIsSubDirectory(ushort const *,ushort const *,int *)
0x1800102df  mov     r14d, eax
0x1800102e2  test    eax, eax
0x1800102e4  jns     short loc_180010313
0x1800102e6  mov     r8d, 693h; int
0x1800102ec  mov     ebx, eax
0x1800102ee  lea     rdx, aCscripteddiagI; "CScriptedDiag::IsInboxPackage"
0x1800102f5  mov     ecx, 1; Level
0x1800102fa  mov     r9d, ebx; int
0x1800102fd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180010302  mov     r9d, r14d
0x180010305  mov     r8d, 535h
0x18001030b  mov     ebx, r14d
0x18001030e  jmp     loc_1800105D4
0x180010313  mov     rdx, [rsi+18h]
0x180010317  mov     ecx, [rdx+38h]
0x18001031a  mov     eax, ecx
0x18001031c  btr     eax, 9
0x180010320  bts     ecx, 9
0x180010324  cmp     dword ptr [rbp+Block], edi
0x180010327  cmovz   ecx, eax; this
0x18001032a  mov     [rdx+38h], ecx
0x18001032d  lea     rdx, [rbp+lpPathName]; unsigned __int16 **
0x180010331  call    ?GetTempPackagePath@CScriptedDiag@@AEAAJPEAPEAG@Z; CScriptedDiag::GetTempPackagePath(ushort * *)
0x180010336  mov     ebx, eax
0x180010338  test    eax, eax
0x18001033a  jns     short loc_18001035F
0x18001033c  mov     r9d, eax; int
0x18001033f  lea     rdx, aCscripteddiagS; "CScriptedDiag::SecurePackage"
0x180010346  mov     r8d, 53Bh; int
0x18001034c  mov     ecx, 1; Level
0x180010351  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180010356  mov     rdi, [rbp+lpPathName]
0x18001035a  jmp     loc_1800105E5
0x18001035f  mov     rdi, [rbp+lpPathName]
0x180010363  mov     rdx, rdi; unsigned __int16 *
0x180010366  call    ?ValidatePackagePath@CScriptedDiag@@AEAAJPEBG@Z; CScriptedDiag::ValidatePackagePath(ushort const *)
0x18001036b  mov     ebx, eax
0x18001036d  test    eax, eax
0x18001036f  jns     short loc_18001037F
0x180010371  mov     r9d, eax
0x180010374  mov     r8d, 53Eh
0x18001037a  jmp     loc_1800105D4
0x18001037f  lea     rdx, [rbp+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x180010383  call    ?SdpCreateSecurityDescriptor@@YAJKPEAU_SECURITY_ATTRIBUTES@@@Z; SdpCreateSecurityDescriptor(ulong,_SECURITY_ATTRIBUTES *)
0x180010388  mov     ebx, eax
0x18001038a  test    eax, eax
0x18001038c  jns     short loc_18001039C
0x18001038e  mov     r9d, eax
0x180010391  mov     r8d, 541h
0x180010397  jmp     loc_1800105D4
0x18001039c  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x1800103a0  mov     rcx, rdi; lpPathName
0x1800103a3  call    cs:__imp_CreateDirectoryW
0x1800103a9  test    eax, eax
0x1800103ab  jnz     short loc_1800103D1
0x1800103ad  call    cs:__imp_GetLastError
0x1800103b3  mov     ebx, eax
0x1800103b5  test    eax, eax
0x1800103b7  jle     short loc_1800103C2
0x1800103b9  movzx   ebx, ax
0x1800103bc  or      ebx, 80070000h
0x1800103c2  test    ebx, ebx
0x1800103c4  jns     short loc_1800103D1
0x1800103c6  mov     r8d, 544h
0x1800103cc  jmp     loc_1800105D1
0x1800103d1  mov     r8, rdi; unsigned __int16 *
0x1800103d4  mov     rdx, r12; unsigned __int16 *
0x1800103d7  mov     rcx, rsi; this
0x1800103da  call    ?CopyPackage@CScriptedDiag@@AEAAJPEBG0@Z; CScriptedDiag::CopyPackage(ushort const *,ushort const *)
0x1800103df  mov     ebx, eax
0x1800103e1  test    eax, eax
0x1800103e3  jns     short loc_1800103F3
0x1800103e5  mov     r9d, eax
0x1800103e8  mov     r8d, 547h
0x1800103ee  jmp     loc_1800105D4
0x1800103f3  mov     [rbp+lpPathName], r15
0x1800103f7  test    rdi, rdi
0x1800103fa  jnz     short loc_18001041E
0x1800103fc  mov     ebx, 80070057h
0x180010401  lea     rdx, aSettingsSetPac; "Settings::set_PackagePath"
0x180010408  mov     r9d, ebx; int
0x18001040b  lea     ecx, [rdi+1]; Level
0x18001040e  mov     r8d, 8Bh; int
0x180010414  mov     r14d, ebx
0x180010417  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001041c  jmp     short loc_18001047C
0x18001041e  mov     rbx, [rsi+18h]
0x180010422  lea     rcx, [rbp+lpPathName]; unsigned __int16 **
0x180010426  mov     rdx, rdi; unsigned __int16 *
0x180010429  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18001042e  mov     r14d, eax
0x180010431  test    eax, eax
0x180010433  jns     short loc_180010455
0x180010435  mov     r9d, eax; int
0x180010438  lea     rdx, aSettingsSetPac; "Settings::set_PackagePath"
0x18001043f  mov     r8d, 8Eh; int
0x180010445  mov     ecx, 1; Level
0x18001044a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001044f  mov     rcx, [rbp+lpPathName]
0x180010453  jmp     short loc_18001046D
0x180010455  mov     rcx, [rbx+8]; Block
0x180010459  test    rcx, rcx
0x18001045c  jz      short loc_180010463
0x18001045e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010463  mov     rax, [rbp+lpPathName]
0x180010467  xor     ecx, ecx; Block
0x180010469  mov     [rbx+8], rax
0x18001046d  test    rcx, rcx
0x180010470  jz      short loc_180010477
0x180010472  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010477  test    r14d, r14d
0x18001047a  jns     short loc_18001048D
0x18001047c  mov     ebx, r14d
0x18001047f  mov     r9d, r14d
0x180010482  mov     r8d, 54Ah
0x180010488  jmp     loc_1800105D4
0x18001048d  mov     rdx, rdi; unsigned __int16 *
0x180010490  mov     rcx, rsi; this
0x180010493  cmp     dword ptr [rbp+Block], r15d
0x180010497  jz      short loc_1800104B6
0x180010499  or      dword ptr [rsi+30h], 2
0x18001049d  call    ?VerifyInboxPackageTrust@CScriptedDiag@@AEAAJPEBG@Z; CScriptedDiag::VerifyInboxPackageTrust(ushort const *)
0x1800104a2  mov     ebx, eax
0x1800104a4  test    eax, eax
0x1800104a6  jns     short loc_1800104CF
0x1800104a8  mov     r9d, eax
0x1800104ab  mov     r8d, 554h
0x1800104b1  jmp     loc_1800105D4
0x1800104b6  call    ?VerifyPackageTrust@CScriptedDiag@@AEAAJPEBG@Z; CScriptedDiag::VerifyPackageTrust(ushort const *)
0x1800104bb  mov     ebx, eax
0x1800104bd  test    eax, eax
0x1800104bf  jns     short loc_1800104CF
0x1800104c1  mov     r9d, eax
0x1800104c4  mov     r8d, 558h
0x1800104ca  jmp     loc_1800105D4
0x1800104cf  lea     r8, [rbp+var_40]; unsigned __int16 **
0x1800104d3  mov     rcx, rdi; unsigned __int16 *
0x1800104d6  lea     rdx, aResult_0; "result"
0x1800104dd  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x1800104e2  mov     ebx, eax
0x1800104e4  test    eax, eax
0x1800104e6  jns     short loc_18001050B
0x1800104e8  mov     r9d, eax; int
0x1800104eb  lea     rdx, aCscripteddiagS; "CScriptedDiag::SecurePackage"
0x1800104f2  mov     r8d, 55Ch; int
0x1800104f8  mov     ecx, 1; Level
0x1800104fd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180010502  mov     r15, [rbp+var_40]
0x180010506  jmp     loc_1800105E5
0x18001050b  mov     r15, [rbp+var_40]
0x18001050f  xor     edx, edx; lpSecurityAttributes
0x180010511  mov     rcx, r15; lpPathName
0x180010514  call    cs:__imp_CreateDirectoryW
0x18001051a  test    eax, eax
0x18001051c  jnz     short loc_180010542
0x18001051e  call    cs:__imp_GetLastError
0x180010524  mov     ebx, eax
0x180010526  test    eax, eax
0x180010528  jle     short loc_180010533
0x18001052a  movzx   ebx, ax
0x18001052d  or      ebx, 80070000h
0x180010533  test    ebx, ebx
0x180010535  jns     short loc_180010542
0x180010537  mov     r8d, 55Fh
0x18001053d  jmp     loc_1800105D1
0x180010542  mov     [rbp+var_40], 0
0x18001054a  test    r15, r15
0x18001054d  jnz     short loc_18001056F
0x18001054f  mov     ebx, 80070057h
0x180010554  lea     rdx, aSettingsSetRes; "Settings::set_ResultPath"
0x18001055b  mov     r9d, ebx; int
0x18001055e  lea     ecx, [r15+1]; Level
0x180010562  mov     r8d, 142h; int
0x180010568  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001056d  jmp     short loc_1800105CB
0x18001056f  mov     rsi, [rsi+18h]
0x180010573  lea     rcx, [rbp+var_40]; unsigned __int16 **
0x180010577  mov     rdx, r15; unsigned __int16 *
0x18001057a  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18001057f  mov     ebx, eax
0x180010581  test    eax, eax
0x180010583  jns     short loc_1800105A5
0x180010585  mov     r9d, eax; int
0x180010588  lea     rdx, aSettingsSetRes; "Settings::set_ResultPath"
0x18001058f  mov     r8d, 145h; int
0x180010595  mov     ecx, 1; Level
0x18001059a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001059f  mov     rcx, [rbp+var_40]
0x1800105a3  jmp     short loc_1800105BD
0x1800105a5  mov     rcx, [rsi+18h]; Block
0x1800105a9  test    rcx, rcx
0x1800105ac  jz      short loc_1800105B3
0x1800105ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800105b3  mov     rax, [rbp+var_40]
0x1800105b7  xor     ecx, ecx; Block
0x1800105b9  mov     [rsi+18h], rax
0x1800105bd  test    rcx, rcx
0x1800105c0  jz      short loc_1800105C7
0x1800105c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800105c7  test    ebx, ebx
0x1800105c9  jns     short loc_1800105E5
0x1800105cb  mov     r8d, 562h; int
0x1800105d1  mov     r9d, ebx; int
0x1800105d4  lea     rdx, aCscripteddiagS; "CScriptedDiag::SecurePackage"
0x1800105db  mov     ecx, 1; Level
0x1800105e0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800105e5  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 10h
0x1800105ec  jz      short loc_180010609
0x1800105ee  lea     rax, [rbp+var_20]
0x1800105f2  mov     r9d, 1
0x1800105f8  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_PERF_TRUST_STOP
0x1800105ff  mov     [rsp+80h+var_60], rax
0x180010604  call    McGenEventWrite_EventWriteTransfer
0x180010609  test    r12, r12
0x18001060c  jz      short loc_180010616
0x18001060e  mov     rcx, r12; Block
0x180010611  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010616  test    rdi, rdi
0x180010619  jz      short loc_180010623
0x18001061b  mov     rcx, rdi; Block
0x18001061e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010623  test    r15, r15
0x180010626  jz      short loc_180010630
0x180010628  mov     rcx, r15; Block
0x18001062b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010630  mov     rcx, [rbp+SecurityAttributes.lpSecurityDescriptor]; hMem
0x180010634  test    rcx, rcx
0x180010637  jz      short loc_18001063F
0x180010639  call    cs:__imp_LocalFree
  ... truncated ...
```
