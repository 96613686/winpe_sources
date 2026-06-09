# SxCreateDirectoryUnderSVI(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18000e554`
- end: `0x18000e7e4`
- name: `?SxCreateDirectoryUnderSVI@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `656`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, struct _TOKEN_PRIVILEGES *, unsigned __int16)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000bdd0`
- `0x18000bf70`

## callees

- `0x180003e5c`
- `0x18000d348`
- `0x18000d43c`
- `0x18000e3b8`
- `0x18000e554`
- `0x18000e7ec`
- `0x18000ea60`
- `0x18000ef70`
- `0x18000f154`
- `0x18000f2cc`
- `0x180014ec8`
- `0x180015760`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000e7ae`
- `KERNEL32!CloseHandle` at `0x18000e7ae`
- `KERNEL32!GetFileAttributesW` at `0x18000e63c`
- `KERNEL32!GetFileAttributesW` at `0x18000e63c`
- `KERNEL32!DeleteFileW` at `0x18000e6ca`
- `KERNEL32!DeleteFileW` at `0x18000e6ca`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000e786`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000e786`
- `ole32!CoTaskMemFree` at `0x18000e790`
- `ole32!CoTaskMemFree` at `0x18000e790`

## string_xrefs

- `0x18000e5af`: `SxCreateDirectoryUnderSVI`
- `0x18000e70e`: `::DeleteFile( strDir )`

## pseudocode

```c
__int64 __fastcall SxCreateDirectoryUnderSVI(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        struct _TOKEN_PRIVILEGES *a3,
        unsigned __int16 a4)
{
  char *v5; // rbx
  int SVI; // edi
  __int16 v7; // ax
  const WCHAR *v8; // r15
  unsigned int v9; // ecx
  DWORD FileAttributesW; // r12d
  int v11; // eax
  bool v12; // sf
  struct _SECURITY_ATTRIBUTES *v13; // rdx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+40h] [rbp-40h] BYREF
  __int16 v17; // [rsp+44h] [rbp-3Ch]
  __int16 v18; // [rsp+46h] [rbp-3Ah]
  HANDLE TokenHandle; // [rsp+B8h] [rbp+38h] BYREF
  PTOKEN_PRIVILEGES NewState; // [rsp+C0h] [rbp+40h] BYREF

  NewState = a3;
  TokenHandle = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, a3, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "SxCreateDirectoryUnderSVI", 0x68Eu, a4);
  v5 = 0;
  lpFileName[1] = 0;
  NewState = 0;
  lpFileName[0] = (LPCWSTR)qword_18001A620;
  TokenHandle = 0;
  if ( !a1 )
  {
    SVI = -2147024809;
    v16 = -2147024809;
    v18 = 1685;
    goto LABEL_28;
  }
  v16 = 0;
  v17 = 1686;
  SVI = CBsString::Append((CBsString *)lpFileName, a1, L"System Volume Information\\SPP");
  v16 = SVI;
  v7 = 1688;
  if ( SVI < 0 )
  {
LABEL_7:
    v18 = v7;
    goto LABEL_23;
  }
  v8 = lpFileName[0];
  v17 = 1688;
  FileAttributesW = GetFileAttributesW(lpFileName[0]);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    v11 = SxOpenThreadOrProcessToken(v9, &TokenHandle);
    v5 = (char *)TokenHandle;
    SVI = v11;
    v16 = v11;
    v12 = v11 < 0;
    v7 = 1706;
    if ( v12 )
      goto LABEL_7;
    v17 = 1706;
    SVI = SxEnableBackupRestorePrivs(TokenHandle, &NewState);
    v16 = SVI;
    v7 = 1714;
    if ( SVI < 0 )
      goto LABEL_7;
    v17 = 1714;
    SVI = SxCreateSVI(a1);
    v16 = SVI;
    v7 = 1721;
    if ( SVI < 0 )
      goto LABEL_7;
    v17 = 1721;
    if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
    {
      if ( !DeleteFileW(v8) )
      {
        SVI = GetLastFailureAsHRESULT();
        v16 = SVI;
        v18 = 1730;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids,
            (unsigned int)"::DeleteFile( strDir )",
            (__int64)v8,
            SVI);
          SVI = v16;
        }
        goto LABEL_23;
      }
      v16 = 0;
      v17 = 1730;
    }
    SVI = SxCreateDirectory(v8, v13);
    v16 = SVI;
    v7 = 1733;
    if ( SVI < 0 )
      goto LABEL_7;
  }
  else
  {
    SVI = 0;
    v7 = 1696;
    v16 = 0;
  }
  v17 = v7;
LABEL_23:
  if ( NewState && (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    AdjustTokenPrivileges(v5, 0, NewState, 0, 0, 0);
    CoTaskMemFree(NewState);
    SVI = v16;
    NewState = 0;
  }
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
LABEL_28:
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)SVI;
}

```

## disassembly

```asm
0x18000e554  mov     rax, rsp
0x18000e557  mov     [rax+8], rbx
0x18000e55b  mov     [rax+20h], rsi
0x18000e55f  mov     [rax+18h], r8
0x18000e563  mov     [rax+10h], rdx
0x18000e567  push    rbp
0x18000e568  push    rdi
0x18000e569  push    r12
0x18000e56b  push    r14
0x18000e56d  push    r15
0x18000e56f  mov     rbp, rsp
0x18000e572  sub     rsp, 80h
0x18000e579  mov     r14, rcx
0x18000e57c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e583  lea     rax, WPP_GLOBAL_Control
0x18000e58a  cmp     rcx, rax
0x18000e58d  jz      short loc_18000E5A9
0x18000e58f  test    dword ptr [rcx+1Ch], 20000000h
0x18000e596  jz      short loc_18000E5A9
0x18000e598  mov     rcx, [rcx+10h]
0x18000e59c  mov     edx, 32h ; '2'
0x18000e5a1  mov     r9, r14
0x18000e5a4  call    WPP_SF_q
0x18000e5a9  mov     r8d, 68Eh; unsigned __int16
0x18000e5af  lea     rdx, aSxcreatedirect; "SxCreateDirectoryUnderSVI"
0x18000e5b6  lea     rcx, [rbp+var_40]; this
0x18000e5ba  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e5bf  xor     ebx, ebx
0x18000e5c1  mov     [rbp+var_48], 0
0x18000e5c9  mov     [rbp+NewState], 0
0x18000e5d1  lea     rax, qword_18001A620
0x18000e5d8  mov     [rbp+lpFileName], rax
0x18000e5dc  mov     [rbp+TokenHandle], rbx
0x18000e5e0  test    r14, r14
0x18000e5e3  jnz     short loc_18000E5FB
0x18000e5e5  mov     edi, 80070057h
0x18000e5ea  mov     eax, 695h
0x18000e5ef  mov     [rbp+var_40], edi
0x18000e5f2  mov     [rbp+var_3A], ax
0x18000e5f6  jmp     loc_18000E7B4
0x18000e5fb  mov     eax, 696h
0x18000e600  mov     [rbp+var_40], ebx
0x18000e603  mov     [rbp+var_3C], ax
0x18000e607  lea     r8, aSystemVolumeIn_2; "System Volume Information\\SPP"
0x18000e60e  mov     rdx, r14; unsigned __int16 *
0x18000e611  lea     rcx, [rbp+lpFileName]; this
0x18000e615  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x18000e61a  mov     edi, eax
0x18000e61c  mov     [rbp+var_40], eax
0x18000e61f  test    eax, eax
0x18000e621  mov     eax, 698h
0x18000e626  jns     short loc_18000E631
0x18000e628  mov     [rbp+var_3A], ax
0x18000e62c  jmp     loc_18000E759
0x18000e631  mov     r15, [rbp+lpFileName]
0x18000e635  mov     rcx, r15; lpFileName
0x18000e638  mov     [rbp+var_3C], ax
0x18000e63c  call    cs:__imp_GetFileAttributesW
0x18000e642  mov     esi, eax
0x18000e644  mov     r12d, eax
0x18000e647  and     esi, 10h
0x18000e64a  cmp     eax, 0FFFFFFFFh
0x18000e64d  jz      short loc_18000E662
0x18000e64f  test    esi, esi
0x18000e651  jz      short loc_18000E662
0x18000e653  xor     edi, edi
0x18000e655  mov     eax, 6A0h
0x18000e65a  mov     [rbp+var_40], edi
0x18000e65d  jmp     loc_18000E755
0x18000e662  lea     rdx, [rbp+TokenHandle]; void **
0x18000e666  call    ?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z; SxOpenThreadOrProcessToken(ulong,void * *)
0x18000e66b  mov     rbx, [rbp+TokenHandle]
0x18000e66f  mov     edi, eax
0x18000e671  mov     [rbp+var_40], eax
0x18000e674  test    eax, eax
0x18000e676  mov     eax, 6AAh
0x18000e67b  js      short loc_18000E628
0x18000e67d  lea     rdx, [rbp+NewState]; struct _TOKEN_PRIVILEGES **
0x18000e681  mov     [rbp+var_3C], ax
0x18000e685  mov     rcx, rbx; TokenHandle
0x18000e688  call    ?SxEnableBackupRestorePrivs@@YAJPEAXPEAPEAU_TOKEN_PRIVILEGES@@@Z; SxEnableBackupRestorePrivs(void *,_TOKEN_PRIVILEGES * *)
0x18000e68d  mov     edi, eax
0x18000e68f  mov     [rbp+var_40], eax
0x18000e692  test    eax, eax
0x18000e694  mov     eax, 6B2h
0x18000e699  js      short loc_18000E628
0x18000e69b  mov     rcx, r14; unsigned __int16 *
0x18000e69e  mov     [rbp+var_3C], ax
0x18000e6a2  call    ?SxCreateSVI@@YAJPEBG@Z; SxCreateSVI(ushort const *)
0x18000e6a7  mov     edi, eax
0x18000e6a9  mov     [rbp+var_40], eax
0x18000e6ac  test    eax, eax
0x18000e6ae  mov     eax, 6B9h
0x18000e6b3  js      loc_18000E628
0x18000e6b9  mov     [rbp+var_3C], ax
0x18000e6bd  cmp     r12d, 0FFFFFFFFh
0x18000e6c1  jz      short loc_18000E73B
0x18000e6c3  test    esi, esi
0x18000e6c5  jnz     short loc_18000E73B
0x18000e6c7  mov     rcx, r15; lpFileName
0x18000e6ca  call    cs:__imp_DeleteFileW
0x18000e6d0  test    eax, eax
0x18000e6d2  jnz     short loc_18000E72B
0x18000e6d4  call    GetLastFailureAsHRESULT
0x18000e6d9  mov     edi, eax
0x18000e6db  mov     [rbp+var_40], eax
0x18000e6de  mov     eax, 6C2h
0x18000e6e3  mov     [rbp+var_3A], ax
0x18000e6e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6ee  lea     rax, WPP_GLOBAL_Control
0x18000e6f5  cmp     rcx, rax
0x18000e6f8  jz      short loc_18000E759
0x18000e6fa  test    dword ptr [rcx+1Ch], 2000000h
0x18000e701  jz      short loc_18000E759
0x18000e703  mov     rcx, [rcx+10h]
0x18000e707  lea     edx, [rsi+33h]
0x18000e70a  mov     dword ptr [rsp+80h+ReturnLength], edi
0x18000e70e  lea     r9, aDeletefileStrd; "::DeleteFile( strDir )"
0x18000e715  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18000e71c  mov     [rsp+80h+PreviousState], r15
0x18000e721  call    WPP_SF_sSd
0x18000e726  mov     edi, [rbp+var_40]
0x18000e729  jmp     short loc_18000E759
0x18000e72b  mov     eax, 6C2h
0x18000e730  mov     [rbp+var_40], 0
0x18000e737  mov     [rbp+var_3C], ax
0x18000e73b  mov     rcx, r15; lpFileName
0x18000e73e  call    ?SxCreateDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; SxCreateDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000e743  mov     edi, eax
0x18000e745  mov     [rbp+var_40], eax
0x18000e748  test    eax, eax
0x18000e74a  mov     eax, 6C5h
0x18000e74f  js      loc_18000E628
0x18000e755  mov     [rbp+var_3C], ax
0x18000e759  mov     r8, [rbp+NewState]; NewState
0x18000e75d  test    r8, r8
0x18000e760  jz      short loc_18000E7A1
0x18000e762  lea     rax, [rbx-1]
0x18000e766  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e76a  ja      short loc_18000E7A1
0x18000e76c  mov     [rsp+80h+ReturnLength], 0; ReturnLength
0x18000e775  xor     r9d, r9d; BufferLength
0x18000e778  xor     edx, edx; DisableAllPrivileges
0x18000e77a  mov     [rsp+80h+PreviousState], 0; PreviousState
0x18000e783  mov     rcx, rbx; TokenHandle
0x18000e786  call    cs:__imp_AdjustTokenPrivileges
0x18000e78c  mov     rcx, [rbp+NewState]; pv
0x18000e790  call    cs:__imp_CoTaskMemFree
0x18000e796  mov     edi, [rbp+var_40]
0x18000e799  mov     [rbp+NewState], 0
0x18000e7a1  lea     rcx, [rbx-1]
0x18000e7a5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000e7a9  ja      short loc_18000E7B4
0x18000e7ab  mov     rcx, rbx; hObject
0x18000e7ae  call    cs:__imp_CloseHandle
0x18000e7b4  lea     rcx, [rbp+lpFileName]; this
0x18000e7b8  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000e7bd  lea     rcx, [rbp+var_40]; this
0x18000e7c1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e7c6  lea     r11, [rsp+80h+var_s0]
0x18000e7ce  mov     eax, edi
0x18000e7d0  mov     rbx, [r11+30h]
0x18000e7d4  mov     rsi, [r11+48h]
0x18000e7d8  mov     rsp, r11
0x18000e7db  pop     r15
0x18000e7dd  pop     r14
0x18000e7df  pop     r12
0x18000e7e1  pop     rdi
0x18000e7e2  pop     rbp
0x18000e7e3  retn
```
