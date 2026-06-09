# CSelectiveWipe::LoadEfsWrtLibrary(void)

- ea: `0x1800b9988`
- end: `0x1800b9c5a`
- name: `?LoadEfsWrtLibrary@CSelectiveWipe@@CAJXZ`
- size: `722`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b86ec`
- `0x1800b8f94`
- `0x1800b9108`
- `0x1800b95f8`
- `0x1800b9ed0`

## callees

- `0x180007b9c`
- `0x180007e10`
- `0x180008b60`
- `0x180011314`
- `0x1800b9988`
- `0x1800bcb0c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800b9ad5`
- `KERNEL32!GetProcAddress` at `0x1800b9b3d`
- `KERNEL32!GetProcAddress` at `0x1800b9ba8`
- `KERNEL32!GetProcAddress` at `0x1800b9ad5`
- `KERNEL32!GetProcAddress` at `0x1800b9b3d`
- `KERNEL32!GetProcAddress` at `0x1800b9ba8`
- `KERNEL32!LoadLibraryExW` at `0x1800b9a60`
- `KERNEL32!LoadLibraryExW` at `0x1800b9a60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b9c3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b9c3e`

## string_xrefs

- `0x1800b9a53`: `efswrt.dll`

## pseudocode

```c
__int64 CSelectiveWipe::LoadEfsWrtLibrary(void)
{
  _BYTE *v0; // rax
  char v1; // cl
  HMODULE v2; // r8
  int LastFailureAsHRESULT; // ebx
  __int16 v4; // ax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  char v7; // [rsp+28h] [rbp-30h]
  int v8; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+34h] [rbp-24h]
  char v10; // [rsp+38h] [rbp-20h]
  const char *v11; // [rsp+40h] [rbp-18h]
  __int64 v12; // [rsp+48h] [rbp-10h]

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
      v0 = WPP_GLOBAL_Control;
    }
  }
  if ( (v0[68] & 0x20) != 0 && v0[65] >= 6u )
  {
    v1 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v1 = 0;
LABEL_9:
  v10 = v1;
  v11 = "CSelectiveWipe::LoadEfsWrtLibrary";
  v8 = 0;
  v9 = 71;
  v12 = 0;
  CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
    &lpCriticalSection,
    &CSelectiveWipe::m_cs);
  if ( CSelectiveWipe::m_hEfsWrtDll )
  {
    LastFailureAsHRESULT = v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
    }
    CSelectiveWipe::m_hEfsWrtDll = LoadLibraryExW(L"efswrt.dll", 0, 0x800u);
    v2 = CSelectiveWipe::m_hEfsWrtDll;
    if ( !CSelectiveWipe::m_hEfsWrtDll )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v8 = LastFailureAsHRESULT;
      v4 = 79;
LABEL_16:
      HIWORD(v9) = v4;
      goto LABEL_44;
    }
    v8 = 0;
    LOWORD(v9) = 79;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
      v2 = CSelectiveWipe::m_hEfsWrtDll;
    }
    CSelectiveWipe::pfncEnterpriseDataProtect = (int (*)(const unsigned __int16 *, const unsigned __int16 *, enum Windows::Security::EnterpriseData::FileProtectionStatus *))GetProcAddress(v2, "EnterpriseDataProtect");
    if ( !CSelectiveWipe::pfncEnterpriseDataProtect )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v8 = LastFailureAsHRESULT;
      v4 = 83;
      goto LABEL_16;
    }
    v8 = 0;
    LOWORD(v9) = 83;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
    }
    CSelectiveWipe::pfncEnterpriseDataGetStatus = (int (*)(const unsigned __int16 *, enum Windows::Security::EnterpriseData::FileProtectionStatus *))GetProcAddress(CSelectiveWipe::m_hEfsWrtDll, "EnterpriseDataGetStatus");
    if ( !CSelectiveWipe::pfncEnterpriseDataGetStatus )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v8 = LastFailureAsHRESULT;
      v4 = 87;
      goto LABEL_16;
    }
    v8 = 0;
    LOWORD(v9) = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
    }
    CSelectiveWipe::pfncUnprotectFile = (int (*)(const unsigned __int16 *, const struct FILE_UNPROTECT_OPTIONS *))GetProcAddress(CSelectiveWipe::m_hEfsWrtDll, "UnprotectFile");
    if ( !CSelectiveWipe::pfncUnprotectFile )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v8 = LastFailureAsHRESULT;
      v4 = 91;
      goto LABEL_16;
    }
    LastFailureAsHRESULT = 0;
    v8 = 0;
    LOWORD(v9) = 91;
  }
  if ( !CSelectiveWipe::m_spEdpMethods )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
    }
    LastFailureAsHRESULT = CEdpMethods::CreateInstance(&CSelectiveWipe::m_spEdpMethods);
    v8 = LastFailureAsHRESULT;
    v4 = 97;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_16;
    LOWORD(v9) = 97;
  }
LABEL_44:
  if ( v7 )
    LeaveCriticalSection(lpCriticalSection);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v8);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800b9988  push    rbp
0x1800b998a  push    rbx
0x1800b998b  push    r12
0x1800b998d  push    r15
0x1800b998f  mov     rbp, rsp
0x1800b9992  sub     rsp, 58h
0x1800b9996  mov     rax, cs:WPP_GLOBAL_Control
0x1800b999d  lea     r15, WPP_GLOBAL_Control
0x1800b99a4  lea     r12, WPP_8f615fdb2b0232236e798df82271f47a_Traceguids
0x1800b99ab  cmp     rax, r15
0x1800b99ae  jz      short loc_1800B99D4
0x1800b99b0  test    byte ptr [rax+44h], 20h
0x1800b99b4  jz      short loc_1800B99E4
0x1800b99b6  cmp     byte ptr [rax+41h], 6
0x1800b99ba  jb      short loc_1800B99D4
0x1800b99bc  mov     rcx, [rax+38h]
0x1800b99c0  mov     edx, 0Ah
0x1800b99c5  mov     r8, r12
0x1800b99c8  call    WPP_SF_
0x1800b99cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800b99d4  test    byte ptr [rax+44h], 20h
0x1800b99d8  jz      short loc_1800B99E4
0x1800b99da  cmp     byte ptr [rax+41h], 6
0x1800b99de  jb      short loc_1800B99E4
0x1800b99e0  mov     cl, 1
0x1800b99e2  jmp     short loc_1800B99E6
0x1800b99e4  xor     cl, cl
0x1800b99e6  mov     [rbp+var_20], cl
0x1800b99e9  lea     rax, aCselectivewipe_9; "CSelectiveWipe::LoadEfsWrtLibrary"
0x1800b99f0  lea     rcx, [rbp+lpCriticalSection]
0x1800b99f4  mov     [rbp+var_18], rax
0x1800b99f8  lea     rdx, ?m_cs@CSelectiveWipe@@0VCEcsCriticalSection@@A; CEcsCriticalSection CSelectiveWipe::m_cs
0x1800b99ff  mov     [rbp+var_28], 0
0x1800b9a06  mov     [rbp+var_24], 47h ; 'G'
0x1800b9a0d  mov     [rbp+var_10], 0
0x1800b9a15  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x1800b9a1a  cmp     cs:?m_hEfsWrtDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CSelectiveWipe::m_hEfsWrtDll
0x1800b9a22  jnz     loc_1800B9BDC
0x1800b9a28  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9a2f  cmp     rcx, r15
0x1800b9a32  jz      short loc_1800B9A51
0x1800b9a34  test    byte ptr [rcx+44h], 20h
0x1800b9a38  jz      short loc_1800B9A51
0x1800b9a3a  cmp     byte ptr [rcx+41h], 4
0x1800b9a3e  jb      short loc_1800B9A51
0x1800b9a40  mov     rcx, [rcx+38h]
0x1800b9a44  mov     edx, 0Bh
0x1800b9a49  mov     r8, r12
0x1800b9a4c  call    WPP_SF_
0x1800b9a51  xor     edx, edx; hFile
0x1800b9a53  lea     rcx, aEfswrtDll; "efswrt.dll"
0x1800b9a5a  mov     r8d, 800h; dwFlags
0x1800b9a60  call    cs:__imp_LoadLibraryExW
0x1800b9a66  mov     cs:?m_hEfsWrtDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CSelectiveWipe::m_hEfsWrtDll
0x1800b9a6d  mov     r8, rax
0x1800b9a70  test    rax, rax
0x1800b9a73  jnz     short loc_1800B9A8D
0x1800b9a75  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800b9a7a  mov     ebx, eax
0x1800b9a7c  mov     [rbp+var_28], eax
0x1800b9a7f  mov     eax, 4Fh ; 'O'
0x1800b9a84  mov     word ptr [rbp+var_24+2], ax
0x1800b9a88  jmp     loc_1800B9C34
0x1800b9a8d  mov     eax, 4Fh ; 'O'
0x1800b9a92  mov     [rbp+var_28], 0
0x1800b9a99  mov     word ptr [rbp+var_24], ax
0x1800b9a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9aa4  cmp     rcx, r15
0x1800b9aa7  jz      short loc_1800B9ACB
0x1800b9aa9  test    byte ptr [rcx+44h], 20h
0x1800b9aad  jz      short loc_1800B9ACB
0x1800b9aaf  cmp     byte ptr [rcx+41h], 4
0x1800b9ab3  jb      short loc_1800B9ACB
0x1800b9ab5  mov     rcx, [rcx+38h]
0x1800b9ab9  lea     edx, [rax-43h]
0x1800b9abc  mov     r8, r12
0x1800b9abf  call    WPP_SF_
0x1800b9ac4  mov     r8, cs:?m_hEfsWrtDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CSelectiveWipe::m_hEfsWrtDll
0x1800b9acb  lea     rdx, aEnterprisedata_0; "EnterpriseDataProtect"
0x1800b9ad2  mov     rcx, r8; hModule
0x1800b9ad5  call    cs:__imp_GetProcAddress
0x1800b9adb  mov     cs:?pfncEnterpriseDataProtect@CSelectiveWipe@@0P6AJPEBG0PEAW4FileProtectionStatus@EnterpriseData@Security@Windows@@@ZEA, rax; long (*CSelectiveWipe::pfncEnterpriseDataProtect)(ushort const *,ushort const *,Windows::Security::EnterpriseData::FileProtectionStatus *)
0x1800b9ae2  test    rax, rax
0x1800b9ae5  jnz     short loc_1800B9AF8
0x1800b9ae7  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800b9aec  mov     ebx, eax
0x1800b9aee  mov     [rbp+var_28], eax
0x1800b9af1  mov     eax, 53h ; 'S'
0x1800b9af6  jmp     short loc_1800B9A84
0x1800b9af8  mov     eax, 53h ; 'S'
0x1800b9afd  mov     [rbp+var_28], 0
0x1800b9b04  mov     word ptr [rbp+var_24], ax
0x1800b9b08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9b0f  cmp     rcx, r15
0x1800b9b12  jz      short loc_1800B9B2F
0x1800b9b14  test    byte ptr [rcx+44h], 20h
0x1800b9b18  jz      short loc_1800B9B2F
0x1800b9b1a  cmp     byte ptr [rcx+41h], 4
0x1800b9b1e  jb      short loc_1800B9B2F
0x1800b9b20  mov     rcx, [rcx+38h]
0x1800b9b24  lea     edx, [rax-46h]
0x1800b9b27  mov     r8, r12
0x1800b9b2a  call    WPP_SF_
0x1800b9b2f  mov     rcx, cs:?m_hEfsWrtDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA; hModule
0x1800b9b36  lea     rdx, aEnterprisedata; "EnterpriseDataGetStatus"
0x1800b9b3d  call    cs:__imp_GetProcAddress
0x1800b9b43  mov     cs:?pfncEnterpriseDataGetStatus@CSelectiveWipe@@0P6AJPEBGPEAW4FileProtectionStatus@EnterpriseData@Security@Windows@@@ZEA, rax; long (*CSelectiveWipe::pfncEnterpriseDataGetStatus)(ushort const *,Windows::Security::EnterpriseData::FileProtectionStatus *)
0x1800b9b4a  test    rax, rax
0x1800b9b4d  jnz     short loc_1800B9B63
0x1800b9b4f  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800b9b54  mov     ebx, eax
0x1800b9b56  mov     [rbp+var_28], eax
0x1800b9b59  mov     eax, 57h ; 'W'
0x1800b9b5e  jmp     loc_1800B9A84
0x1800b9b63  mov     eax, 57h ; 'W'
0x1800b9b68  mov     [rbp+var_28], 0
0x1800b9b6f  mov     word ptr [rbp+var_24], ax
0x1800b9b73  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9b7a  cmp     rcx, r15
0x1800b9b7d  jz      short loc_1800B9B9A
0x1800b9b7f  test    byte ptr [rcx+44h], 20h
0x1800b9b83  jz      short loc_1800B9B9A
0x1800b9b85  cmp     byte ptr [rcx+41h], 4
0x1800b9b89  jb      short loc_1800B9B9A
0x1800b9b8b  mov     rcx, [rcx+38h]
0x1800b9b8f  lea     edx, [rax-49h]
0x1800b9b92  mov     r8, r12
0x1800b9b95  call    WPP_SF_
0x1800b9b9a  mov     rcx, cs:?m_hEfsWrtDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA; hModule
0x1800b9ba1  lea     rdx, aUnprotectfile; "UnprotectFile"
0x1800b9ba8  call    cs:__imp_GetProcAddress
0x1800b9bae  mov     cs:?pfncUnprotectFile@CSelectiveWipe@@0P6AJPEBGPEBUFILE_UNPROTECT_OPTIONS@@@ZEA, rax; long (*CSelectiveWipe::pfncUnprotectFile)(ushort const *,FILE_UNPROTECT_OPTIONS const *)
0x1800b9bb5  test    rax, rax
0x1800b9bb8  jnz     short loc_1800B9BCE
0x1800b9bba  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800b9bbf  mov     ebx, eax
0x1800b9bc1  mov     [rbp+var_28], eax
0x1800b9bc4  mov     eax, 5Bh ; '['
0x1800b9bc9  jmp     loc_1800B9A84
0x1800b9bce  xor     ebx, ebx
0x1800b9bd0  mov     [rbp+var_28], ebx
0x1800b9bd3  lea     eax, [rbx+5Bh]
0x1800b9bd6  mov     word ptr [rbp+var_24], ax
0x1800b9bda  jmp     short loc_1800B9BDF
0x1800b9bdc  mov     ebx, [rbp+var_28]
0x1800b9bdf  cmp     cs:?m_spEdpMethods@CSelectiveWipe@@0V?$CComPtr@UIEdpMethods@@@ATL@@A, 0; ATL::CComPtr<IEdpMethods> CSelectiveWipe::m_spEdpMethods
0x1800b9be7  jnz     short loc_1800B9C34
0x1800b9be9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9bf0  cmp     rcx, r15
0x1800b9bf3  jz      short loc_1800B9C12
0x1800b9bf5  test    byte ptr [rcx+44h], 20h
0x1800b9bf9  jz      short loc_1800B9C12
0x1800b9bfb  cmp     byte ptr [rcx+41h], 4
0x1800b9bff  jb      short loc_1800B9C12
0x1800b9c01  mov     rcx, [rcx+38h]
0x1800b9c05  mov     edx, 0Fh
0x1800b9c0a  mov     r8, r12
0x1800b9c0d  call    WPP_SF_
0x1800b9c12  lea     rcx, ?m_spEdpMethods@CSelectiveWipe@@0V?$CComPtr@UIEdpMethods@@@ATL@@A; struct IEdpMethods **
0x1800b9c19  call    ?CreateInstance@CEdpMethods@@SAJPEAPEAUIEdpMethods@@@Z; CEdpMethods::CreateInstance(IEdpMethods * *)
0x1800b9c1e  mov     ebx, eax
0x1800b9c20  mov     [rbp+var_28], eax
0x1800b9c23  test    eax, eax
0x1800b9c25  mov     eax, 61h ; 'a'
0x1800b9c2a  js      loc_1800B9A84
0x1800b9c30  mov     word ptr [rbp+var_24], ax
0x1800b9c34  cmp     [rbp+var_30], 0
0x1800b9c38  jz      short loc_1800B9C44
0x1800b9c3a  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800b9c3e  call    cs:__imp_LeaveCriticalSection
0x1800b9c44  lea     rcx, [rbp+var_28]; this
0x1800b9c48  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800b9c4d  mov     eax, ebx
0x1800b9c4f  add     rsp, 58h
0x1800b9c53  pop     r15
0x1800b9c55  pop     r12
0x1800b9c57  pop     rbx
0x1800b9c58  pop     rbp
0x1800b9c59  retn
```
