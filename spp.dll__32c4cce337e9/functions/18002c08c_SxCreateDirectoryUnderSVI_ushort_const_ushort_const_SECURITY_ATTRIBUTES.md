# SxCreateDirectoryUnderSVI(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18002c08c`
- end: `0x18002c31b`
- name: `?SxCreateDirectoryUnderSVI@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014c48`

## callees

- `0x1800216c8`
- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002bee4`
- `0x18002c08c`
- `0x18002c324`
- `0x18002c5a4`
- `0x18002d408`
- `0x18002d6e8`
- `0x18003530c`
- `0x180035b00`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002c2e6`
- `KERNEL32!CloseHandle` at `0x18002c2e6`
- `KERNEL32!DeleteFileW` at `0x18002c209`
- `KERNEL32!DeleteFileW` at `0x18002c209`
- `KERNEL32!GetFileAttributesW` at `0x18002c17b`
- `KERNEL32!GetFileAttributesW` at `0x18002c17b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2cc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002c2c2`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002c2c2`

## string_xrefs

- `0x18002c0e9`: `SxCreateDirectoryUnderSVI`
- `0x18002c24d`: `::DeleteFile( strDir )`

## pseudocode

```c
__int64 __fastcall SxCreateDirectoryUnderSVI(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  __int16 v6; // ax
  char *v7; // rbx
  int SVI; // edi
  __int16 v9; // ax
  const WCHAR *v10; // r15
  __int64 v11; // rcx
  DWORD FileAttributesW; // r12d
  int v13; // eax
  bool v14; // sf
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-50h] BYREF
  int v20; // [rsp+40h] [rbp-40h] BYREF
  __int16 v21; // [rsp+44h] [rbp-3Ch]
  __int16 v22; // [rsp+46h] [rbp-3Ah]
  PTOKEN_PRIVILEGES NewState; // [rsp+C0h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+D8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "SxCreateDirectoryUnderSVI", 1678, 1);
  lpFileName[0] = &FileName;
  v6 = 1685;
  lpFileName[1] = 0;
  v7 = 0;
  NewState = 0;
  TokenHandle = 0;
  if ( !a1 || (v21 = 1685, v6 = 1686, !a2) )
  {
    SVI = -2147024809;
    v22 = v6;
    v20 = -2147024809;
    goto LABEL_29;
  }
  v20 = 0;
  v21 = 1686;
  SVI = CBsString::Set((CBsString *)lpFileName, a1, a2);
  v20 = SVI;
  v9 = 1688;
  if ( SVI < 0 )
  {
LABEL_8:
    v22 = v9;
    goto LABEL_24;
  }
  v10 = lpFileName[0];
  v21 = 1688;
  FileAttributesW = GetFileAttributesW(lpFileName[0]);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    v13 = SxOpenThreadOrProcessToken(v11, &TokenHandle);
    v7 = (char *)TokenHandle;
    SVI = v13;
    v20 = v13;
    v14 = v13 < 0;
    v9 = 1706;
    if ( v14 )
      goto LABEL_8;
    v21 = 1706;
    SVI = SxEnableBackupRestorePrivs(TokenHandle, &NewState);
    v20 = SVI;
    v9 = 1714;
    if ( SVI < 0 )
      goto LABEL_8;
    v21 = 1714;
    SVI = SxCreateSVI(a1);
    v20 = SVI;
    v9 = 1721;
    if ( SVI < 0 )
      goto LABEL_8;
    v21 = 1721;
    if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
    {
      if ( !DeleteFileW(v10) )
      {
        SVI = GetLastFailureAsHRESULT(v15);
        v20 = SVI;
        v22 = 1730;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)&WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids,
            (unsigned int)"::DeleteFile( strDir )",
            (__int64)v10,
            SVI);
          SVI = v20;
        }
        goto LABEL_24;
      }
      v20 = 0;
      v21 = 1730;
    }
    SVI = SxCreateDirectory(v10, lpSecurityAttributes);
    v20 = SVI;
    v9 = 1733;
    if ( SVI < 0 )
      goto LABEL_8;
  }
  else
  {
    SVI = 0;
    v9 = 1696;
    v20 = 0;
  }
  v21 = v9;
LABEL_24:
  if ( NewState && (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    AdjustTokenPrivileges(v7, 0, NewState, 0, 0, 0);
    CoTaskMemFree(NewState);
    NewState = 0;
    SVI = v20;
  }
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
LABEL_29:
  CBsString::_Release((unsigned __int16 **)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20, v16, v17);
  return (unsigned int)SVI;
}

```

## disassembly

```asm
0x18002c08c  mov     [rsp-38h+arg_8], rbx
0x18002c091  push    rbp
0x18002c092  push    rsi
0x18002c093  push    rdi
0x18002c094  push    r12
0x18002c096  push    r13
0x18002c098  push    r14
0x18002c09a  push    r15
0x18002c09c  mov     rbp, rsp
0x18002c09f  sub     rsp, 80h
0x18002c0a6  mov     r13, r8
0x18002c0a9  mov     rdi, rdx
0x18002c0ac  mov     r14, rcx
0x18002c0af  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0b6  lea     rax, WPP_GLOBAL_Control
0x18002c0bd  cmp     rcx, rax
0x18002c0c0  jz      short loc_18002C0E3
0x18002c0c2  test    dword ptr [rcx+1Ch], 20000000h
0x18002c0c9  jz      short loc_18002C0E3
0x18002c0cb  mov     rcx, [rcx+10h]
0x18002c0cf  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002c0d6  mov     edx, 32h ; '2'
0x18002c0db  mov     r9, r14
0x18002c0de  call    WPP_SF_q
0x18002c0e3  mov     r9d, 1; unsigned __int16
0x18002c0e9  lea     rdx, aSxcreatedirect; "SxCreateDirectoryUnderSVI"
0x18002c0f0  mov     r8d, 68Eh; unsigned __int16
0x18002c0f6  lea     rcx, [rbp+var_40]; this
0x18002c0fa  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002c0ff  xor     ecx, ecx
0x18002c101  lea     rax, FileName
0x18002c108  mov     [rbp+lpFileName], rax
0x18002c10c  mov     eax, 695h
0x18002c111  mov     [rbp+var_48], rcx
0x18002c115  mov     ebx, ecx
0x18002c117  mov     [rbp+NewState], rcx
0x18002c11b  mov     [rbp+TokenHandle], rcx
0x18002c11f  test    r14, r14
0x18002c122  jnz     short loc_18002C135
0x18002c124  mov     edi, 80070057h
0x18002c129  mov     [rbp+var_3A], ax
0x18002c12d  mov     [rbp+var_40], edi
0x18002c130  jmp     loc_18002C2EC
0x18002c135  mov     [rbp+var_3C], ax
0x18002c139  mov     eax, 696h
0x18002c13e  test    rdi, rdi
0x18002c141  jz      short loc_18002C124
0x18002c143  mov     [rbp+var_40], ecx
0x18002c146  mov     r8, rdi; unsigned __int16 *
0x18002c149  lea     rcx, [rbp+lpFileName]; this
0x18002c14d  mov     [rbp+var_3C], ax
0x18002c151  mov     rdx, r14; unsigned __int16 *
0x18002c154  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x18002c159  mov     edi, eax
0x18002c15b  mov     [rbp+var_40], eax
0x18002c15e  test    eax, eax
0x18002c160  mov     eax, 698h
0x18002c165  jns     short loc_18002C170
0x18002c167  mov     [rbp+var_3A], ax
0x18002c16b  jmp     loc_18002C29B
0x18002c170  mov     r15, [rbp+lpFileName]
0x18002c174  mov     rcx, r15; lpFileName
0x18002c177  mov     [rbp+var_3C], ax
0x18002c17b  call    cs:__imp_GetFileAttributesW
0x18002c181  mov     esi, eax
0x18002c183  mov     r12d, eax
0x18002c186  and     esi, 10h
0x18002c189  cmp     eax, 0FFFFFFFFh
0x18002c18c  jz      short loc_18002C1A1
0x18002c18e  test    esi, esi
0x18002c190  jz      short loc_18002C1A1
0x18002c192  xor     edi, edi
0x18002c194  mov     eax, 6A0h
0x18002c199  mov     [rbp+var_40], edi
0x18002c19c  jmp     loc_18002C297
0x18002c1a1  lea     rdx, [rbp+TokenHandle]; void **
0x18002c1a5  call    ?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z; SxOpenThreadOrProcessToken(ulong,void * *)
0x18002c1aa  mov     rbx, [rbp+TokenHandle]
0x18002c1ae  mov     edi, eax
0x18002c1b0  mov     [rbp+var_40], eax
0x18002c1b3  test    eax, eax
0x18002c1b5  mov     eax, 6AAh
0x18002c1ba  js      short loc_18002C167
0x18002c1bc  lea     rdx, [rbp+NewState]; struct _TOKEN_PRIVILEGES **
0x18002c1c0  mov     [rbp+var_3C], ax
0x18002c1c4  mov     rcx, rbx; TokenHandle
0x18002c1c7  call    ?SxEnableBackupRestorePrivs@@YAJPEAXPEAPEAU_TOKEN_PRIVILEGES@@@Z; SxEnableBackupRestorePrivs(void *,_TOKEN_PRIVILEGES * *)
0x18002c1cc  mov     edi, eax
0x18002c1ce  mov     [rbp+var_40], eax
0x18002c1d1  test    eax, eax
0x18002c1d3  mov     eax, 6B2h
0x18002c1d8  js      short loc_18002C167
0x18002c1da  mov     rcx, r14; unsigned __int16 *
0x18002c1dd  mov     [rbp+var_3C], ax
0x18002c1e1  call    ?SxCreateSVI@@YAJPEBG@Z; SxCreateSVI(ushort const *)
0x18002c1e6  mov     edi, eax
0x18002c1e8  mov     [rbp+var_40], eax
0x18002c1eb  test    eax, eax
0x18002c1ed  mov     eax, 6B9h
0x18002c1f2  js      loc_18002C167
0x18002c1f8  mov     [rbp+var_3C], ax
0x18002c1fc  cmp     r12d, 0FFFFFFFFh
0x18002c200  jz      short loc_18002C27A
0x18002c202  test    esi, esi
0x18002c204  jnz     short loc_18002C27A
0x18002c206  mov     rcx, r15; lpFileName
0x18002c209  call    cs:__imp_DeleteFileW
0x18002c20f  test    eax, eax
0x18002c211  jnz     short loc_18002C26A
0x18002c213  call    GetLastFailureAsHRESULT
0x18002c218  mov     edi, eax
0x18002c21a  mov     [rbp+var_40], eax
0x18002c21d  mov     eax, 6C2h
0x18002c222  mov     [rbp+var_3A], ax
0x18002c226  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c22d  lea     rax, WPP_GLOBAL_Control
0x18002c234  cmp     rcx, rax
0x18002c237  jz      short loc_18002C29B
0x18002c239  test    dword ptr [rcx+1Ch], 2000000h
0x18002c240  jz      short loc_18002C29B
0x18002c242  mov     rcx, [rcx+10h]
0x18002c246  lea     edx, [rsi+33h]
0x18002c249  mov     dword ptr [rsp+80h+ReturnLength], edi
0x18002c24d  lea     r9, aDeletefileStrd; "::DeleteFile( strDir )"
0x18002c254  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002c25b  mov     [rsp+80h+PreviousState], r15
0x18002c260  call    WPP_SF_sSd
0x18002c265  mov     edi, [rbp+var_40]
0x18002c268  jmp     short loc_18002C29B
0x18002c26a  mov     eax, 6C2h
0x18002c26f  mov     [rbp+var_40], 0
0x18002c276  mov     [rbp+var_3C], ax
0x18002c27a  mov     rdx, r13; lpSecurityAttributes
0x18002c27d  mov     rcx, r15; lpFileName
0x18002c280  call    ?SxCreateDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; SxCreateDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18002c285  mov     edi, eax
0x18002c287  mov     [rbp+var_40], eax
0x18002c28a  test    eax, eax
0x18002c28c  mov     eax, 6C5h
0x18002c291  js      loc_18002C167
0x18002c297  mov     [rbp+var_3C], ax
0x18002c29b  mov     r8, [rbp+NewState]; NewState
0x18002c29f  test    r8, r8
0x18002c2a2  jz      short loc_18002C2D9
0x18002c2a4  lea     rax, [rbx-1]
0x18002c2a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c2ac  ja      short loc_18002C2D9
0x18002c2ae  xor     edi, edi
0x18002c2b0  xor     r9d, r9d; BufferLength
0x18002c2b3  mov     [rsp+80h+ReturnLength], rdi; ReturnLength
0x18002c2b8  xor     edx, edx; DisableAllPrivileges
0x18002c2ba  mov     rcx, rbx; TokenHandle
0x18002c2bd  mov     [rsp+80h+PreviousState], rdi; PreviousState
0x18002c2c2  call    cs:__imp_AdjustTokenPrivileges
0x18002c2c8  mov     rcx, [rbp+NewState]; pv
0x18002c2cc  call    cs:__imp_CoTaskMemFree
0x18002c2d2  mov     [rbp+NewState], rdi
0x18002c2d6  mov     edi, [rbp+var_40]
0x18002c2d9  lea     rcx, [rbx-1]
0x18002c2dd  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002c2e1  ja      short loc_18002C2EC
0x18002c2e3  mov     rcx, rbx; hObject
0x18002c2e6  call    cs:__imp_CloseHandle
0x18002c2ec  lea     rcx, [rbp+lpFileName]; this
0x18002c2f0  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002c2f5  lea     rcx, [rbp+var_40]; this
0x18002c2f9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002c2fe  mov     rbx, [rsp+80h+arg_8]
0x18002c306  mov     eax, edi
0x18002c308  add     rsp, 80h
0x18002c30f  pop     r15
0x18002c311  pop     r14
0x18002c313  pop     r13
0x18002c315  pop     r12
0x18002c317  pop     rdi
0x18002c318  pop     rsi
0x18002c319  pop     rbp
0x18002c31a  retn
```
