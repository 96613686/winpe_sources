# RemoveFileFromAutoRecoverFolder(ushort const *)

- ea: `0x18002c310`
- end: `0x18002c984`
- name: `?RemoveFileFromAutoRecoverFolder@@YAJPEBG@Z`
- size: `1652`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000a290`
- `0x18000fa30`
- `0x18000ff54`
- `0x18001016c`
- `0x180011db4`
- `0x180011e40`
- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x18001e990`
- `0x1800298f0`
- `0x18002a1f0`
- `0x18002c310`
- `0x18002c98c`
- `0x18002c9f4`
- `0x1800378f8`
- `0x1800434d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c86b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c93b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c86b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c93b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c85d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c85d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c525`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c57d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c525`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c57d`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18002c838`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18002c8eb`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18002c931`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18002c838`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18002c8eb`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18002c931`

## string_xrefs

- `0x18002c444`: `Working Directory`
- `0x18002c4cc`: `Working Directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RemoveFileFromAutoRecoverFolder(const unsigned __int16 *a1)
{
  __int64 v2; // rax
  unsigned __int64 v3; // rdi
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // r15
  int v7; // eax
  int v8; // r8d
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  int v13; // r8d
  __int64 v14; // rbx
  int Value; // eax
  unsigned int v16; // edi
  void *v17; // rax
  int v18; // r8d
  const WCHAR *v19; // rsi
  signed int v20; // eax
  bool v21; // cc
  DWORD v22; // eax
  __int64 v23; // r14
  void *v24; // rax
  unsigned __int16 *v25; // rdi
  int v26; // eax
  unsigned int v27; // esi
  int v28; // eax
  const unsigned __int16 *v29; // rbx
  __int64 v30; // rax
  void *v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rdx
  int v34; // eax
  int v35; // eax
  WowSettings *v36; // rcx
  __int64 v37; // rdx
  WowSettings *v38; // rcx
  signed int LastError; // eax
  WowSettings *v40; // rcx
  LPWSTR lpDst; // [rsp+30h] [rbp-30h] BYREF
  __int64 v42; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v43[8]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v44; // [rsp+48h] [rbp-18h]
  PVOID OlValue; // [rsp+50h] [rbp-10h] BYREF
  int v46; // [rsp+58h] [rbp-8h]
  int v47; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v48; // [rsp+B0h] [rbp+50h] BYREF
  LPCWSTR lpSrc; // [rsp+B8h] [rbp+58h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  v3 = v2 + 1;
  v4 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v2 + 1, 2u));
  v5 = v4;
  if ( !v4 )
    return 2147749894LL;
  std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(v43, v4);
  CWbemTime::CWbemTime((CWbemTime *)&lpDst);
  v7 = StringCchCopyW(v5, v3, a1);
  v9 = v7;
  if ( v7 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v7);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_98;
    }
    v11 = 13;
    goto LABEL_55;
  }
  if ( CWbemInstallObject::m_bOffline )
  {
    v29 = CWbemInstallObject::m_pwszAutoRecoverPath;
    v30 = -1;
    do
      ++v30;
    while ( CWbemInstallObject::m_pwszAutoRecoverPath[v30] );
    v23 = v30 + 38;
    v31 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v30 + 38, 2u));
    std::unique_ptr<unsigned short [0]>::reset(&lpDst, v31);
    v25 = lpDst;
    if ( lpDst )
    {
      v32 = StringCchPrintfW(lpDst, v23, L"%ls\\", v29);
      v9 = v32;
      if ( v32 < 0 )
      {
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v32);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_98;
        }
        v11 = 15;
LABEL_55:
        WPP_SF_D(v10[2], v11, &WPP_ee0346ed31b93840a3824ae448285ccd_Traceguids, v9);
        goto LABEL_98;
      }
LABEL_40:
      lpSrc = 0;
      v28 = ComposeName((PUCHAR)v5, (unsigned __int16 **)&lpSrc);
      v9 = v28;
      if ( v28 < 0 )
      {
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v28);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_98;
        }
        v11 = 16;
        goto LABEL_55;
      }
      std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&lpSrc, lpSrc);
      v34 = StringCchCatW(v25, v23, v33);
      v9 = v34;
      if ( v34 < 0 )
      {
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v34);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_ee0346ed31b93840a3824ae448285ccd_Traceguids, v9);
        }
LABEL_61:
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
        goto LABEL_98;
      }
      OlValue = 0;
      v46 = 0;
      v35 = WowSettings::Wow64DisableWow64FsRedirection(&OlValue);
      v9 = v35;
      if ( v35 >= 0 )
      {
        if ( DeleteFileW(v25) )
        {
          if ( (int)WowSettings::EnsureWowFunctions(v38) >= 0 && WowSettings::s_bIsWow64 && v46 )
          {
            if ( Wow64RevertWow64FsRedirection(OlValue) )
            {
              OlValue = 0;
              v46 = 0;
            }
            else
            {
              GetLastError();
            }
          }
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
          v9 = 0;
          goto LABEL_98;
        }
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( v9 == -2147024894 )
        {
          if ( (int)WowSettings::EnsureWowFunctions(v40) >= 0 && WowSettings::s_bIsWow64 && v46 )
          {
            if ( Wow64RevertWow64FsRedirection(OlValue) )
            {
              OlValue = 0;
              v46 = 0;
            }
            else
            {
              GetLastError();
            }
          }
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
          v9 = 1;
          goto LABEL_98;
        }
        if ( (v9 & 0x80000000) != 0 )
          CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v9);
        v36 = (WowSettings *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_68;
        }
        v37 = 19;
      }
      else
      {
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v35);
        v36 = (WowSettings *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_68:
          if ( (int)WowSettings::EnsureWowFunctions(v36) >= 0 && WowSettings::s_bIsWow64 && v46 )
          {
            if ( Wow64RevertWow64FsRedirection(OlValue) )
            {
              OlValue = 0;
              v46 = 0;
            }
            else
            {
              GetLastError();
            }
          }
          goto LABEL_61;
        }
        v37 = 18;
      }
      WPP_SF_D(*((_QWORD *)v36 + 2), v37, &WPP_ee0346ed31b93840a3824ae448285ccd_Traceguids, v9);
      goto LABEL_68;
    }
LABEL_46:
    v9 = -2147217402;
    goto LABEL_98;
  }
  v42 = 0;
  v12 = DLRegOpenKeyExW(-2147483646, (unsigned int)L"Software\\Microsoft\\WBEM\\CIMOM", v8, 131353, (__int64)&v42);
  if ( v12 )
  {
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v9 = v12;
    goto LABEL_98;
  }
  v14 = v42;
  v44 = v42;
  v47 = 0;
  v48 = 0;
  Value = DLRegQueryValueExW(v42, (unsigned int)L"Working Directory", v13, (unsigned int)&v47, 0, (__int64)&v48);
  v16 = Value;
  if ( !Value )
  {
    if ( !v48 || v47 != 2 )
      goto LABEL_28;
    v17 = CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned __int64)v48 >> 1, 2u));
    std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&lpSrc, v17);
    v19 = lpSrc;
    if ( lpSrc )
    {
      v20 = DLRegQueryValueExW(
              v42,
              (unsigned int)L"Working Directory",
              v18,
              (unsigned int)&v47,
              (__int64)lpSrc,
              (__int64)&v48);
      v16 = v20;
      v21 = v20 <= 0;
      if ( v20 )
      {
LABEL_23:
        if ( !v21 )
          v16 = (unsigned __int16)v20 | 0x80070000;
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
        goto LABEL_18;
      }
      if ( v47 != 2 )
      {
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
LABEL_28:
        DLRegCloseKey(v14);
        v9 = -2147023881;
        goto LABEL_98;
      }
      v22 = ExpandEnvironmentStringsW(v19, 0, 0);
      if ( !v22 )
      {
LABEL_30:
        v20 = GetLastError();
        v16 = v20;
        v21 = v20 <= 0;
        goto LABEL_23;
      }
      v23 = v22 + 51LL;
      v24 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v23, 2u));
      std::unique_ptr<unsigned short [0]>::reset(&lpDst, v24);
      v25 = lpDst;
      if ( lpDst )
      {
        if ( !ExpandEnvironmentStringsW(v19, lpDst, v23) )
          goto LABEL_30;
        v26 = StringCchCatW(v25, v23, L"\\AutoRecover\\");
        v27 = v26;
        if ( v26 < 0 )
        {
          CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v26);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ee0346ed31b93840a3824ae448285ccd_Traceguids, v27);
          }
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
          DLRegCloseKey(v14);
          v9 = v27;
          goto LABEL_98;
        }
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
        DLRegCloseKey(v14);
        goto LABEL_40;
      }
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
    DLRegCloseKey(v14);
    goto LABEL_46;
  }
  if ( Value > 0 )
    v16 = (unsigned __int16)Value | 0x80070000;
LABEL_18:
  DLRegCloseKey(v14);
  v9 = v16;
LABEL_98:
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpDst);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v43);
  return v9;
}

```

## disassembly

```asm
0x18002c310  mov     [rsp-38h+arg_0], rbx
0x18002c315  push    rbp
0x18002c316  push    rsi
0x18002c317  push    rdi
0x18002c318  push    r12
0x18002c31a  push    r13
0x18002c31c  push    r14
0x18002c31e  push    r15
0x18002c320  mov     rbp, rsp
0x18002c323  sub     rsp, 60h
0x18002c327  mov     rbx, rcx
0x18002c32a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002c32e  mov     rax, rsi
0x18002c331  xor     r12d, r12d
0x18002c334  inc     rax
0x18002c337  cmp     [rcx+rax*2], r12w
0x18002c33c  jnz     short loc_18002C334
0x18002c33e  lea     rdi, [rax+1]
0x18002c342  mov     r13d, 2
0x18002c348  mov     eax, r13d
0x18002c34b  mul     rdi
0x18002c34e  cmovb   rax, rsi
0x18002c352  mov     rcx, rax; unsigned __int64
0x18002c355  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002c35a  mov     r15, rax
0x18002c35d  test    rax, rax
0x18002c360  jnz     short loc_18002C36C
0x18002c362  mov     eax, 80041006h
0x18002c367  jmp     loc_18002C96C
0x18002c36c  mov     rdx, r15
0x18002c36f  lea     rcx, [rbp+var_20]
0x18002c373  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18002c378  nop
0x18002c379  lea     rcx, [rbp+lpDst]; this
0x18002c37d  call    ??0CWbemTime@@QEAA@XZ; CWbemTime::CWbemTime(void)
0x18002c382  nop
0x18002c383  mov     r8, rbx; unsigned __int16 *
0x18002c386  mov     rdx, rdi; unsigned __int64
0x18002c389  mov     rcx, r15; unsigned __int16 *
0x18002c38c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c391  mov     ebx, eax
0x18002c393  test    eax, eax
0x18002c395  jns     short loc_18002C3DA
0x18002c397  mov     edx, eax; int
0x18002c399  lea     rcx, unk_18006A9C0; this
0x18002c3a0  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002c3a5  lea     rax, WPP_GLOBAL_Control
0x18002c3ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3b3  cmp     rcx, rax
0x18002c3b6  jz      loc_18002C957
0x18002c3bc  test    byte ptr [rcx+1Ch], 1
0x18002c3c0  jz      loc_18002C957
0x18002c3c6  cmp     [rcx+19h], r13b
0x18002c3ca  jb      loc_18002C957
0x18002c3d0  mov     edx, 0Dh
0x18002c3d5  jmp     loc_18002C725
0x18002c3da  cmp     cs:?m_bOffline@CWbemInstallObject@@0_NA, r12b; bool CWbemInstallObject::m_bOffline
0x18002c3e1  jnz     loc_18002C689
0x18002c3e7  mov     [rbp+var_28], r12
0x18002c3eb  lea     rax, [rbp+var_28]
0x18002c3ef  mov     [rsp+60h+var_40], rax
0x18002c3f4  mov     r9d, 20119h
0x18002c3fa  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WBEM\\CIMOM"
0x18002c401  mov     rcx, 0FFFFFFFF80000002h
0x18002c408  call    DLRegOpenKeyExW
0x18002c40d  test    eax, eax
0x18002c40f  jz      short loc_18002C422
0x18002c411  jle     short loc_18002C41B
0x18002c413  movzx   eax, ax
0x18002c416  or      eax, 80070000h
0x18002c41b  mov     ebx, eax
0x18002c41d  jmp     loc_18002C957
0x18002c422  mov     rbx, [rbp+var_28]
0x18002c426  mov     [rbp+var_18], rbx
0x18002c42a  mov     [rbp+arg_8], r12d
0x18002c42e  mov     [rbp+arg_10], r12d
0x18002c432  lea     rax, [rbp+arg_10]
0x18002c436  mov     [rsp+60h+var_38], rax
0x18002c43b  mov     [rsp+60h+var_40], r12
0x18002c440  lea     r9, [rbp+arg_8]
0x18002c444  lea     rdx, aWorkingDirecto; "Working Directory"
0x18002c44b  mov     rcx, [rbp+var_28]
0x18002c44f  call    DLRegQueryValueExW
0x18002c454  mov     edi, eax
0x18002c456  test    eax, eax
0x18002c458  jz      short loc_18002C474
0x18002c45a  jle     short loc_18002C465
0x18002c45c  movzx   edi, ax
0x18002c45f  or      edi, 80070000h
0x18002c465  mov     rcx, rbx
0x18002c468  call    DLRegCloseKey
0x18002c46d  mov     ebx, edi
0x18002c46f  jmp     loc_18002C957
0x18002c474  mov     eax, [rbp+arg_10]
0x18002c477  test    eax, eax
0x18002c479  jz      loc_18002C50B
0x18002c47f  cmp     [rbp+arg_8], r13d
0x18002c483  jnz     loc_18002C50B
0x18002c489  mov     ecx, eax
0x18002c48b  shr     rcx, 1
0x18002c48e  mov     rax, r13
0x18002c491  mul     rcx
0x18002c494  cmovb   rax, rsi
0x18002c498  mov     rcx, rax; unsigned __int64
0x18002c49b  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002c4a0  mov     rdx, rax
0x18002c4a3  lea     rcx, [rbp+lpSrc]
0x18002c4a7  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18002c4ac  nop
0x18002c4ad  mov     rsi, [rbp+lpSrc]
0x18002c4b1  test    rsi, rsi
0x18002c4b4  jz      loc_18002C66D
0x18002c4ba  lea     rax, [rbp+arg_10]
0x18002c4be  mov     [rsp+60h+var_38], rax
0x18002c4c3  mov     [rsp+60h+var_40], rsi
0x18002c4c8  lea     r9, [rbp+arg_8]
0x18002c4cc  lea     rdx, aWorkingDirecto; "Working Directory"
0x18002c4d3  mov     rcx, [rbp+var_28]
0x18002c4d7  call    DLRegQueryValueExW
0x18002c4dc  mov     edi, eax
0x18002c4de  test    eax, eax
0x18002c4e0  jz      short loc_18002C4FB
0x18002c4e2  jle     short loc_18002C4ED
0x18002c4e4  movzx   edi, ax
0x18002c4e7  or      edi, 80070000h
0x18002c4ed  lea     rcx, [rbp+lpSrc]
0x18002c4f1  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18002c4f6  jmp     loc_18002C465
0x18002c4fb  cmp     [rbp+arg_8], r13d
0x18002c4ff  jz      short loc_18002C51D
0x18002c501  lea     rcx, [rbp+lpSrc]
0x18002c505  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18002c50a  nop
0x18002c50b  mov     rcx, rbx
0x18002c50e  call    DLRegCloseKey
0x18002c513  mov     ebx, 800703F7h
0x18002c518  jmp     loc_18002C957
0x18002c51d  xor     r8d, r8d; nSize
0x18002c520  xor     edx, edx; lpDst
0x18002c522  mov     rcx, rsi; lpSrc
0x18002c525  call    cs:__imp_ExpandEnvironmentStringsW
0x18002c52b  test    eax, eax
0x18002c52d  jnz     short loc_18002C53B
0x18002c52f  call    cs:__imp_GetLastError
0x18002c535  mov     edi, eax
0x18002c537  test    eax, eax
0x18002c539  jmp     short loc_18002C4E2
0x18002c53b  mov     r14d, eax
0x18002c53e  add     r14, 33h ; '3'
0x18002c542  mov     rax, r13
0x18002c545  mul     r14
0x18002c548  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c54f  cmovb   rax, rcx
0x18002c553  mov     rcx, rax; unsigned __int64
0x18002c556  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002c55b  mov     rdx, rax
0x18002c55e  lea     rcx, [rbp+lpDst]
0x18002c562  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort [0]>::reset(ushort *)
0x18002c567  mov     rdi, [rbp+lpDst]
0x18002c56b  test    rdi, rdi
0x18002c56e  jz      loc_18002C66D
0x18002c574  mov     r8d, r14d; nSize
0x18002c577  mov     rdx, rdi; lpDst
0x18002c57a  mov     rcx, rsi; lpSrc
0x18002c57d  call    cs:__imp_ExpandEnvironmentStringsW
0x18002c583  test    eax, eax
0x18002c585  jz      short loc_18002C52F
0x18002c587  lea     r8, aAutorecover; "\\AutoRecover\\"
0x18002c58e  mov     rdx, r14; unsigned __int64
0x18002c591  mov     rcx, rdi; unsigned __int16 *
0x18002c594  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c599  mov     esi, eax
0x18002c59b  test    eax, eax
0x18002c59d  jns     short loc_18002C5FE
0x18002c59f  mov     edx, eax; int
0x18002c5a1  lea     rcx, unk_18006A9C0; this
0x18002c5a8  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002c5ad  lea     rax, WPP_GLOBAL_Control
0x18002c5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5bb  cmp     rcx, rax
0x18002c5be  jz      short loc_18002C5E5
0x18002c5c0  test    byte ptr [rcx+1Ch], 1
0x18002c5c4  jz      short loc_18002C5E5
0x18002c5c6  cmp     [rcx+19h], r13b
0x18002c5ca  jb      short loc_18002C5E5
0x18002c5cc  mov     edx, 0Eh
0x18002c5d1  mov     r9d, esi
0x18002c5d4  lea     r8, WPP_ee0346ed31b93840a3824ae448285ccd_Traceguids
0x18002c5db  mov     rcx, [rcx+10h]
0x18002c5df  call    WPP_SF_D
0x18002c5e4  nop
0x18002c5e5  lea     rcx, [rbp+lpSrc]
0x18002c5e9  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18002c5ee  nop
0x18002c5ef  mov     rcx, rbx
0x18002c5f2  call    DLRegCloseKey
0x18002c5f7  mov     ebx, esi
0x18002c5f9  jmp     loc_18002C957
0x18002c5fe  lea     rcx, [rbp+lpSrc]
0x18002c602  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18002c607  nop
0x18002c608  mov     rcx, rbx
0x18002c60b  call    DLRegCloseKey
0x18002c610  mov     [rbp+lpSrc], r12
0x18002c614  lea     rdx, [rbp+lpSrc]; unsigned __int16 **
0x18002c618  mov     rcx, r15; pbInput
0x18002c61b  call    ?ComposeName@@YAJPEAGPEAPEAG@Z; ComposeName(ushort *,ushort * *)
0x18002c620  mov     ebx, eax
0x18002c622  test    eax, eax
0x18002c624  jns     loc_18002C73D
0x18002c62a  mov     edx, eax; int
0x18002c62c  lea     rcx, unk_18006A9C0; this
0x18002c633  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002c638  lea     rax, WPP_GLOBAL_Control
0x18002c63f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c646  cmp     rcx, rax
0x18002c649  jz      loc_18002C957
0x18002c64f  test    byte ptr [rcx+1Ch], 1
0x18002c653  jz      loc_18002C957
0x18002c659  cmp     [rcx+19h], r13b
0x18002c65d  jb      loc_18002C957
0x18002c663  mov     edx, 10h
0x18002c668  jmp     loc_18002C725
0x18002c66d  lea     rcx, [rbp+lpSrc]
0x18002c671  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18002c676  nop
0x18002c677  mov     rcx, rbx
0x18002c67a  call    DLRegCloseKey
0x18002c67f  mov     ebx, 80041006h
0x18002c684  jmp     loc_18002C957
0x18002c689  mov     rbx, cs:?m_pwszAutoRecoverPath@CWbemInstallObject@@0PEBGEB; ushort const * const CWbemInstallObject::m_pwszAutoRecoverPath
0x18002c690  mov     rax, rsi
0x18002c693  inc     rax
0x18002c696  cmp     [rbx+rax*2], r12w
0x18002c69b  jnz     short loc_18002C693
0x18002c69d  lea     r14, [rax+26h]
0x18002c6a1  mov     rax, r13
0x18002c6a4  mul     r14
0x18002c6a7  cmovb   rax, rsi
0x18002c6ab  mov     rcx, rax; unsigned __int64
0x18002c6ae  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002c6b3  mov     rdx, rax
0x18002c6b6  lea     rcx, [rbp+lpDst]
0x18002c6ba  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort [0]>::reset(ushort *)
0x18002c6bf  mov     rdi, [rbp+lpDst]
0x18002c6c3  test    rdi, rdi
0x18002c6c6  jz      short loc_18002C67F
0x18002c6c8  mov     r9, rbx
0x18002c6cb  lea     r8, aLs; "%ls\\"
0x18002c6d2  mov     rdx, r14; unsigned __int64
0x18002c6d5  mov     rcx, rdi; unsigned __int16 *
0x18002c6d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c6dd  mov     ebx, eax
0x18002c6df  test    eax, eax
0x18002c6e1  jns     loc_18002C610
0x18002c6e7  mov     edx, eax; int
0x18002c6e9  lea     rcx, unk_18006A9C0; this
0x18002c6f0  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002c6f5  lea     rax, WPP_GLOBAL_Control
0x18002c6fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c703  cmp     rcx, rax
0x18002c706  jz      loc_18002C957
0x18002c70c  test    byte ptr [rcx+1Ch], 1
0x18002c710  jz      loc_18002C957
0x18002c716  cmp     [rcx+19h], r13b
0x18002c71a  jb      loc_18002C957
0x18002c720  mov     edx, 0Fh
0x18002c725  mov     r9d, ebx
0x18002c728  lea     r8, WPP_ee0346ed31b93840a3824ae448285ccd_Traceguids
0x18002c72f  mov     rcx, [rcx+10h]
0x18002c733  call    WPP_SF_D
0x18002c738  jmp     loc_18002C957
0x18002c73d  mov     rdx, [rbp+lpSrc]
0x18002c741  lea     rcx, [rbp+lpSrc]
0x18002c745  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18002c74a  nop
0x18002c74b  mov     r8, rdx; unsigned __int16 *
0x18002c74e  mov     rdx, r14; unsigned __int64
0x18002c751  mov     rcx, rdi; unsigned __int16 *
0x18002c754  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c759  mov     ebx, eax
0x18002c75b  test    eax, eax
0x18002c75d  jns     short loc_18002C7B3
0x18002c75f  mov     edx, eax; int
0x18002c761  lea     rcx, unk_18006A9C0; this
0x18002c768  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002c76d  lea     rax, WPP_GLOBAL_Control
0x18002c774  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c77b  cmp     rcx, rax
0x18002c77e  jz      short loc_18002C7A5
0x18002c780  test    byte ptr [rcx+1Ch], 1
0x18002c784  jz      short loc_18002C7A5
0x18002c786  cmp     [rcx+19h], r13b
0x18002c78a  jb      short loc_18002C7A5
0x18002c78c  mov     edx, 11h
0x18002c791  mov     r9d, ebx
0x18002c794  lea     r8, WPP_ee0346ed31b93840a3824ae448285ccd_Traceguids
0x18002c79b  mov     rcx, [rcx+10h]
0x18002c79f  call    WPP_SF_D
0x18002c7a4  nop
  ... truncated ...
```
