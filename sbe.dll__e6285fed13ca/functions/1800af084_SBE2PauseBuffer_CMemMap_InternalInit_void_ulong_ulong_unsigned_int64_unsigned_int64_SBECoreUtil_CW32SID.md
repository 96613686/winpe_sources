# SBE2PauseBuffer::CMemMap::InternalInit(void *,ulong,ulong,unsigned __int64,unsigned __int64,SBECoreUtil::CW32SID *)

- ea: `0x1800af084`
- end: `0x1800af38d`
- name: `?InternalInit@CMemMap@SBE2PauseBuffer@@AEAAJPEAXKK_K1PEAVCW32SID@SBECoreUtil@@@Z`
- size: `777`
- prototype: `__int64 __usercall@<rax>(SBE2PauseBuffer::CMemMap *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int64, unsigned __int64, struct SBECoreUtil::CW32SID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800ae0d0`
- `0x1800ae5d4`

## callees

- `0x1800017a0`
- `0x180002e68`
- `0x18002573c`
- `0x180057140`
- `0x18005ff10`
- `0x1800af084`
- `0x1800af394`
- `0x1800af3c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800af1af`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800af1af`
- `KERNEL32!CloseHandle` at `0x1800af2d6`
- `KERNEL32!CloseHandle` at `0x1800af2d6`
- `KERNEL32!GetLastError` at `0x1800af20d`
- `KERNEL32!GetLastError` at `0x1800af288`
- `KERNEL32!GetLastError` at `0x1800af35b`
- `KERNEL32!GetLastError` at `0x1800af20d`
- `KERNEL32!GetLastError` at `0x1800af288`
- `KERNEL32!GetLastError` at `0x1800af35b`
- `KERNEL32!OpenFileMappingW` at `0x1800af1f8`
- `KERNEL32!OpenFileMappingW` at `0x1800af2c8`
- `KERNEL32!OpenFileMappingW` at `0x1800af1f8`
- `KERNEL32!OpenFileMappingW` at `0x1800af2c8`
- `KERNEL32!MapViewOfFile` at `0x1800af276`
- `KERNEL32!MapViewOfFile` at `0x1800af276`
- `KERNEL32!CreateFileMappingW` at `0x1800af342`
- `KERNEL32!CreateFileMappingW` at `0x1800af342`

## string_xrefs

- `0x1800af374`: `%s(%d) : CreateFileMapping() error on %s: GetLastError () = %u`
- `0x1800af2f5`: `%s(%d) : CREATE_NEW and mapping for %s already exists`
- `0x1800af226`: `%s(%d) : OpenFileMapping() error on %s: GetLastError () = %u`

## pseudocode

```c
__int64 __fastcall SBE2PauseBuffer::CMemMap::InternalInit(
        wchar_t *this,
        void *a2,
        unsigned int a3,
        int a4,
        unsigned __int64 dwFileOffsetLow,
        unsigned __int64 a6,
        struct SBECoreUtil::CW32SID *a7)
{
  signed int v10; // edi
  unsigned int *v11; // r14
  SBE2PauseBuffer::CMemMap *v12; // rcx
  unsigned int v13; // eax
  enum _ACCESS_MODE v14; // r8d
  SBECoreUtil::CSBESecurityObject *v15; // r10
  __int64 v16; // rax
  __int64 v17; // rbx
  SBE2PauseBuffer::CMemMap *v18; // rcx
  int v19; // edx
  const WCHAR *lpName; // r14
  int v21; // eax
  int v22; // r15d
  int v23; // r15d
  DWORD v24; // eax
  HANDLE v25; // rax
  SBE2PauseBuffer::CMemMap *v26; // rcx
  signed int LastError; // eax
  DWORD v28; // r15d
  DWORD v29; // eax
  HANDLE v30; // r10
  LPVOID v31; // rax
  signed int v32; // eax
  DWORD v34; // eax
  HANDLE v35; // rax
  struct _SECURITY_ATTRIBUTES *v36; // rdx
  HANDLE FileMappingW; // rax
  signed int v38; // eax
  SIZE_T dwNumberOfBytesToMap; // [rsp+20h] [rbp-38h]
  SIZE_T dwNumberOfBytesToMapa; // [rsp+20h] [rbp-38h]
  unsigned int *v41; // [rsp+30h] [rbp-28h]
  _QWORD v42[3]; // [rsp+40h] [rbp-18h] BYREF

  v42[0] = 0;
  SAL2::Release<SAL2::CSALResidentNVP *>(v42);
  if ( ((a6 - dwFileOffsetLow) & 0xFFFFFFFF00000000uLL) != 0 )
    goto LABEL_2;
  v11 = (unsigned int *)a7;
  v10 = 0;
  *((_QWORD *)this + 67) = a6 - dwFileOffsetLow;
  LODWORD(a6) = 0;
  if ( v11 )
  {
    if ( operator new(0x48u) )
    {
      v13 = SBE2PauseBuffer::CMemMap::MapProtectToAccessRights(v12, a3);
      v16 = SBECoreUtil::CSBESecurityObject::CSBESecurityObject(
              v15,
              (struct SBECoreUtil::CW32SID *)v11,
              v14,
              v13,
              (enum _ACCESS_MODE)dwNumberOfBytesToMap,
              v13,
              (unsigned int *)&a6);
      v10 = a6;
      v17 = v16;
    }
    else
    {
      v17 = 0;
    }
    SAL2::Release<SAL2::CSALResidentNVP *>(v42);
    v42[0] = v17;
    if ( !v17 )
    {
      v10 = -2147024882;
      goto LABEL_36;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
    if ( v10 )
    {
      if ( v10 <= 0 )
        goto LABEL_36;
      v10 = (unsigned __int16)v10;
LABEL_35:
      v10 |= 0x80070000;
      goto LABEL_36;
    }
    v18 = (SBE2PauseBuffer::CMemMap *)v11[6];
    v19 = (_DWORD)v18 - 1;
    if ( !(_DWORD)v18 )
      v19 = 0;
    if ( v19 )
    {
      v10 = 0;
LABEL_15:
      lpName = this;
      goto LABEL_23;
    }
  }
  else
  {
    v17 = v42[0];
  }
  a6 = 0;
  v21 = StringCchLengthW(this, 0x104u, &a6);
  v10 = v21;
  if ( v21 < 0 || a6 < 7 )
  {
    lpName = 0;
    if ( v21 < 0 )
      goto LABEL_36;
  }
  else
  {
    if ( wcsstr(this, L"Global\\") != this )
      goto LABEL_15;
    lpName = this + 7;
  }
LABEL_23:
  v22 = a4 - 1;
  if ( v22 )
  {
    v23 = v22 - 1;
    if ( v23 )
    {
      if ( v23 != 1 )
      {
LABEL_2:
        v10 = -2147024809;
        goto LABEL_36;
      }
      v24 = SBE2PauseBuffer::CMemMap::MapProtectToMapAccess(v18, a3);
      v25 = OpenFileMappingW(v24, 0, lpName);
      *((_QWORD *)this + 65) = v25;
      if ( !v25 )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        LODWORD(v41) = LastError;
        LODWORD(dwNumberOfBytesToMap) = 1628;
        CSbeFileLog::LogEvent(
          0x10u,
          1u,
          L"%s(%d) : OpenFileMapping() error on %s: GetLastError () = %u",
          L"multimedia\\dshow\\filters\\sbe\\pausebuffer\\sbexp.cpp",
          dwNumberOfBytesToMap,
          lpName,
          v41);
        goto LABEL_36;
      }
      v28 = dwFileOffsetLow;
      goto LABEL_32;
    }
  }
  else
  {
    v34 = SBE2PauseBuffer::CMemMap::MapProtectToMapAccess(v18, a3);
    v35 = OpenFileMappingW(v34, 0, lpName);
    if ( v35 )
    {
      CloseHandle(v35);
      LODWORD(dwNumberOfBytesToMap) = 1648;
      v10 = -2147024713;
      CSbeFileLog::LogEvent(
        0x10u,
        1u,
        L"%s(%d) : CREATE_NEW and mapping for %s already exists",
        L"multimedia\\dshow\\filters\\sbe\\pausebuffer\\sbexp.cpp",
        dwNumberOfBytesToMap,
        lpName);
      goto LABEL_36;
    }
  }
  v28 = dwFileOffsetLow;
  if ( v17 )
    v36 = *(struct _SECURITY_ATTRIBUTES **)(v17 + 56);
  else
    v36 = 0;
  FileMappingW = CreateFileMappingW(
                   a2,
                   v36,
                   a3,
                   (dwFileOffsetLow + *((_QWORD *)this + 67)) >> 32,
                   (int)dwFileOffsetLow + *((_DWORD *)this + 134),
                   lpName);
  *((_QWORD *)this + 65) = FileMappingW;
  if ( !FileMappingW )
  {
    v38 = GetLastError();
    v10 = v38;
    if ( v38 > 0 )
      v10 = (unsigned __int16)v38 | 0x80070000;
    LODWORD(v41) = v38;
    LODWORD(dwNumberOfBytesToMapa) = 1678;
    CSbeFileLog::LogEvent(
      0x10u,
      1u,
      L"%s(%d) : CreateFileMapping() error on %s: GetLastError () = %u",
      L"multimedia\\dshow\\filters\\sbe\\pausebuffer\\sbexp.cpp",
      dwNumberOfBytesToMapa,
      lpName,
      v41);
    goto LABEL_36;
  }
LABEL_32:
  v29 = SBE2PauseBuffer::CMemMap::MapProtectToMapAccess(v26, a3);
  v31 = MapViewOfFile(v30, v29, HIDWORD(dwFileOffsetLow), v28, *((_QWORD *)this + 67));
  *((_QWORD *)this + 66) = v31;
  if ( !v31 )
  {
    v32 = GetLastError();
    v10 = v32;
    if ( v32 > 0 )
    {
      v10 = (unsigned __int16)v32;
      goto LABEL_35;
    }
  }
LABEL_36:
  SAL2::Release<SAL2::CSALResidentNVP *>(v42);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800af084  mov     [rsp-40h+hFile], rdx
0x1800af089  push    rbp
0x1800af08a  push    rbx
0x1800af08b  push    rsi
0x1800af08c  push    rdi
0x1800af08d  push    r12
0x1800af08f  push    r13
0x1800af091  push    r14
0x1800af093  push    r15
0x1800af095  mov     rbp, rsp
0x1800af098  sub     rsp, 58h
0x1800af09c  mov     rsi, rcx
0x1800af09f  mov     [rbp+var_18], 0
0x1800af0a7  lea     rcx, [rbp+var_18]
0x1800af0ab  mov     r15d, r9d
0x1800af0ae  mov     r13d, r8d
0x1800af0b1  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800af0b6  mov     rax, [rbp+arg_28]
0x1800af0ba  mov     rcx, 0FFFFFFFF00000000h
0x1800af0c4  mov     r12, qword ptr [rbp+dwFileOffsetLow]
0x1800af0c8  sub     rax, r12
0x1800af0cb  test    rcx, rax
0x1800af0ce  jz      short loc_1800AF0DA
0x1800af0d0  mov     edi, 80070057h
0x1800af0d5  jmp     loc_1800AF29D
0x1800af0da  mov     r14, [rbp+arg_30]
0x1800af0de  xor     edi, edi
0x1800af0e0  mov     [rsi+218h], rax
0x1800af0e7  mov     dword ptr [rbp+arg_28], edi
0x1800af0ea  test    r14, r14
0x1800af0ed  jz      loc_1800AF17B
0x1800af0f3  lea     ecx, [rdi+48h]; Size
0x1800af0f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800af0fb  mov     r10, rax
0x1800af0fe  test    rax, rax
0x1800af101  jz      short loc_1800AF12E
0x1800af103  mov     edx, r13d; unsigned int
0x1800af106  call    ?MapProtectToAccessRights@CMemMap@SBE2PauseBuffer@@AEAAKK@Z; SBE2PauseBuffer::CMemMap::MapProtectToAccessRights(ulong)
0x1800af10b  lea     rcx, [rbp+arg_28]
0x1800af10f  mov     r9d, eax; unsigned int
0x1800af112  mov     [rsp+58h+var_28], rcx; unsigned int *
0x1800af117  mov     rdx, r14; struct SBECoreUtil::CW32SID *
0x1800af11a  mov     rcx, r10; this
0x1800af11d  mov     dword ptr [rsp+58h+lpName], eax; unsigned int
0x1800af121  call    ??0CSBESecurityObject@SBECoreUtil@@QEAA@PEAVCW32SID@1@W4_ACCESS_MODE@@K1KPEAK@Z; SBECoreUtil::CSBESecurityObject::CSBESecurityObject(SBECoreUtil::CW32SID *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,ulong *)
0x1800af126  mov     edi, dword ptr [rbp+arg_28]
0x1800af129  mov     rbx, rax
0x1800af12c  jmp     short loc_1800AF130
0x1800af12e  xor     ebx, ebx
0x1800af130  lea     rcx, [rbp+var_18]
0x1800af134  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800af139  mov     [rbp+var_18], rbx
0x1800af13d  test    rbx, rbx
0x1800af140  jz      short loc_1800AF171
0x1800af142  lock inc dword ptr [rbx+8]
0x1800af146  test    edi, edi
0x1800af148  jz      short loc_1800AF158
0x1800af14a  jle     loc_1800AF29D
0x1800af150  movzx   edi, di
0x1800af153  jmp     loc_1800AF297
0x1800af158  mov     ecx, [r14+18h]
0x1800af15c  xor     eax, eax
0x1800af15e  test    ecx, ecx
0x1800af160  lea     edx, [rcx-1]
0x1800af163  cmovz   edx, eax
0x1800af166  test    edx, edx
0x1800af168  jz      short loc_1800AF17F
0x1800af16a  xor     edi, edi
0x1800af16c  mov     r14, rsi
0x1800af16f  jmp     short loc_1800AF1CB
0x1800af171  mov     edi, 8007000Eh
0x1800af176  jmp     loc_1800AF29D
0x1800af17b  mov     rbx, [rbp+var_18]
0x1800af17f  lea     r8, [rbp+arg_28]; unsigned __int64 *
0x1800af183  mov     [rbp+arg_28], 0
0x1800af18b  mov     edx, 104h; unsigned __int64
0x1800af190  mov     rcx, rsi; unsigned __int16 *
0x1800af193  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800af198  mov     edi, eax
0x1800af19a  test    eax, eax
0x1800af19c  js      short loc_1800AF1C0
0x1800af19e  cmp     [rbp+arg_28], 7
0x1800af1a3  jb      short loc_1800AF1C0
0x1800af1a5  lea     rdx, aGlobal_0; "Global\\"
0x1800af1ac  mov     rcx, rsi; Str
0x1800af1af  call    cs:__imp_wcsstr
0x1800af1b5  cmp     rax, rsi
0x1800af1b8  jnz     short loc_1800AF16C
0x1800af1ba  lea     r14, [rsi+0Eh]
0x1800af1be  jmp     short loc_1800AF1CB
0x1800af1c0  xor     r14d, r14d
0x1800af1c3  test    eax, eax
0x1800af1c5  js      loc_1800AF29D
0x1800af1cb  sub     r15d, 1
0x1800af1cf  jz      loc_1800AF2B9
0x1800af1d5  sub     r15d, 1
0x1800af1d9  jz      loc_1800AF30B
0x1800af1df  cmp     r15d, 1
0x1800af1e3  jnz     loc_1800AF0D0
0x1800af1e9  mov     edx, r13d; unsigned int
0x1800af1ec  call    ?MapProtectToMapAccess@CMemMap@SBE2PauseBuffer@@AEAAKK@Z; SBE2PauseBuffer::CMemMap::MapProtectToMapAccess(ulong)
0x1800af1f1  mov     ecx, eax; dwDesiredAccess
0x1800af1f3  mov     r8, r14; lpName
0x1800af1f6  xor     edx, edx; bInheritHandle
0x1800af1f8  call    cs:__imp_OpenFileMappingW
0x1800af1fe  mov     [rsi+208h], rax
0x1800af205  mov     r10, rax
0x1800af208  test    rax, rax
0x1800af20b  jnz     short loc_1800AF250
0x1800af20d  call    cs:__imp_GetLastError
0x1800af213  mov     edi, eax
0x1800af215  test    eax, eax
0x1800af217  jle     short loc_1800AF222
0x1800af219  movzx   edi, ax
0x1800af21c  or      edi, 80070000h
0x1800af222  mov     dword ptr [rsp+58h+var_28], eax
0x1800af226  lea     r8, aSDOpenfilemapp; "%s(%d) : OpenFileMapping() error on %s:"...
0x1800af22d  mov     [rsp+58h+lpName], r14
0x1800af232  mov     dword ptr [rsp+58h+dwNumberOfBytesToMap], 65Ch
0x1800af23a  mov     edx, 1; unsigned __int8
0x1800af23f  lea     r9, aMultimediaDsho_5; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800af246  lea     ecx, [rdx+0Fh]; unsigned int
0x1800af249  call    ?LogEvent@CSbeFileLog@@SAJKEPEBGZZ; CSbeFileLog::LogEvent(ulong,uchar,ushort const *,...)
0x1800af24e  jmp     short loc_1800AF29D
0x1800af250  mov     r15d, r12d
0x1800af253  mov     edx, r13d; unsigned int
0x1800af256  shr     r12, 20h
0x1800af25a  call    ?MapProtectToMapAccess@CMemMap@SBE2PauseBuffer@@AEAAKK@Z; SBE2PauseBuffer::CMemMap::MapProtectToMapAccess(ulong)
0x1800af25f  mov     edx, eax; dwDesiredAccess
0x1800af261  mov     r9d, r15d; dwFileOffsetLow
0x1800af264  mov     rax, [rsi+218h]
0x1800af26b  mov     r8d, r12d; dwFileOffsetHigh
0x1800af26e  mov     rcx, r10; hFileMappingObject
0x1800af271  mov     [rsp+58h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x1800af276  call    cs:__imp_MapViewOfFile
0x1800af27c  mov     [rsi+210h], rax
0x1800af283  test    rax, rax
0x1800af286  jnz     short loc_1800AF29D
0x1800af288  call    cs:__imp_GetLastError
0x1800af28e  mov     edi, eax
0x1800af290  test    eax, eax
0x1800af292  jle     short loc_1800AF29D
0x1800af294  movzx   edi, ax
0x1800af297  or      edi, 80070000h
0x1800af29d  lea     rcx, [rbp+var_18]
0x1800af2a1  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800af2a6  mov     eax, edi
0x1800af2a8  add     rsp, 58h
0x1800af2ac  pop     r15
0x1800af2ae  pop     r14
0x1800af2b0  pop     r13
0x1800af2b2  pop     r12
0x1800af2b4  pop     rdi
0x1800af2b5  pop     rsi
0x1800af2b6  pop     rbx
0x1800af2b7  pop     rbp
0x1800af2b8  retn
0x1800af2b9  mov     edx, r13d; unsigned int
0x1800af2bc  call    ?MapProtectToMapAccess@CMemMap@SBE2PauseBuffer@@AEAAKK@Z; SBE2PauseBuffer::CMemMap::MapProtectToMapAccess(ulong)
0x1800af2c1  mov     ecx, eax; dwDesiredAccess
0x1800af2c3  mov     r8, r14; lpName
0x1800af2c6  xor     edx, edx; bInheritHandle
0x1800af2c8  call    cs:__imp_OpenFileMappingW
0x1800af2ce  test    rax, rax
0x1800af2d1  jz      short loc_1800AF30B
0x1800af2d3  mov     rcx, rax; hObject
0x1800af2d6  call    cs:__imp_CloseHandle
0x1800af2dc  mov     edx, 1; unsigned __int8
0x1800af2e1  mov     [rsp+58h+lpName], r14
0x1800af2e6  lea     r9, aMultimediaDsho_5; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800af2ed  mov     dword ptr [rsp+58h+dwNumberOfBytesToMap], 670h
0x1800af2f5  lea     r8, aSDCreateNewAnd; "%s(%d) : CREATE_NEW and mapping for %s "...
0x1800af2fc  mov     edi, 800700B7h
0x1800af301  lea     ecx, [rdx+0Fh]; unsigned int
0x1800af304  call    ?LogEvent@CSbeFileLog@@SAJKEPEBGZZ; CSbeFileLog::LogEvent(ulong,uchar,ushort const *,...)
0x1800af309  jmp     short loc_1800AF29D
0x1800af30b  mov     r9, [rsi+218h]
0x1800af312  mov     r15d, r12d
0x1800af315  mov     ecx, [rsi+218h]
0x1800af31b  add     r9, r12
0x1800af31e  shr     r9, 20h; dwMaximumSizeHigh
0x1800af322  add     ecx, r12d
0x1800af325  test    rbx, rbx
0x1800af328  jz      short loc_1800AF330
0x1800af32a  mov     rdx, [rbx+38h]
0x1800af32e  jmp     short loc_1800AF332
0x1800af330  xor     edx, edx; lpFileMappingAttributes
0x1800af332  mov     [rsp+58h+lpName], r14; lpName
0x1800af337  mov     r8d, r13d; flProtect
0x1800af33a  mov     dword ptr [rsp+58h+dwNumberOfBytesToMap], ecx; dwMaximumSizeLow
0x1800af33e  mov     rcx, [rbp+hFile]; hFile
0x1800af342  call    cs:__imp_CreateFileMappingW
0x1800af348  mov     [rsi+208h], rax
0x1800af34f  mov     r10, rax
0x1800af352  test    rax, rax
0x1800af355  jnz     loc_1800AF253
0x1800af35b  call    cs:__imp_GetLastError
0x1800af361  mov     edi, eax
0x1800af363  test    eax, eax
0x1800af365  jle     short loc_1800AF370
0x1800af367  movzx   edi, ax
0x1800af36a  or      edi, 80070000h
0x1800af370  mov     dword ptr [rsp+58h+var_28], eax
0x1800af374  lea     r8, aSDCreatefilema; "%s(%d) : CreateFileMapping() error on %"...
0x1800af37b  mov     [rsp+58h+lpName], r14
0x1800af380  mov     dword ptr [rsp+58h+dwNumberOfBytesToMap], 68Eh
0x1800af388  jmp     loc_1800AF23A
```
