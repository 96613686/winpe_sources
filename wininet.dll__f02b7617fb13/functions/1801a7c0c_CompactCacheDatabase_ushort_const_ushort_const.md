# CompactCacheDatabase(ushort const *,ushort const *)

- ea: `0x1801a7c0c`
- end: `0x1801a7e8f`
- name: `?CompactCacheDatabase@@YAJPEBG0@Z`
- size: `643`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800b18d4`

## callees

- `0x1800204f8`
- `0x180025910`
- `0x1800701d0`
- `0x18007ec9c`
- `0x1800afe20`
- `0x1800b098c`
- `0x180136748`
- `0x18014a7a0`
- `0x1801a7c0c`
- `0x1801e1790`
- `0x1801e21a0`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1801a7e44`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1801a7e44`
- `ESENT!JetDetachDatabaseW` at `0x1801a7e1e`
- `ESENT!JetDetachDatabaseW` at `0x1801a7e82`
- `ESENT!JetDetachDatabaseW` at `0x1801a7e1e`
- `ESENT!JetDetachDatabaseW` at `0x1801a7e82`
- `ESENT!JetAttachDatabaseW` at `0x1801a7dca`
- `ESENT!JetAttachDatabaseW` at `0x1801a7dca`
- `ESENT!JetBeginSessionA` at `0x1801a7da4`
- `ESENT!JetBeginSessionA` at `0x1801a7da4`
- `ESENT!JetTerm2` at `0x1801a7cd3`
- `ESENT!JetTerm2` at `0x1801a7cd3`
- `ESENT!JetEndSession` at `0x1801a7cbb`
- `ESENT!JetEndSession` at `0x1801a7cbb`
- `ESENT!JetCompactW` at `0x1801a7e02`
- `ESENT!JetCompactW` at `0x1801a7e02`

## string_xrefs

- `0x1801a7c8a`: `TempCompact.dat`

## pseudocode

```c
__int64 __fastcall CompactCacheDatabase(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int CacheDatabaseJetInstance; // eax
  signed int v5; // ebx
  unsigned int v6; // edi
  const unsigned __int16 *v8; // rdx
  JET_ERR v9; // eax
  JET_ERR v10; // eax
  JET_ERR v11; // eax
  JET_ERR v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int LastError; // eax
  JET_CONVERT_W *pconvert; // [rsp+20h] [rbp-29h]
  const unsigned __int16 *grbit; // [rsp+28h] [rbp-21h]
  const unsigned __int16 *v18; // [rsp+30h] [rbp-19h]
  const unsigned __int16 *v19; // [rsp+38h] [rbp-11h]
  const unsigned __int16 *v20; // [rsp+40h] [rbp-9h]
  const unsigned __int16 *v21; // [rsp+48h] [rbp-1h]
  const unsigned __int16 *v22; // [rsp+50h] [rbp+7h]
  JET_PCWSTR szDatabaseDest; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v24; // [rsp+70h] [rbp+27h]
  JET_SESID sesid; // [rsp+78h] [rbp+2Fh] BYREF
  JET_INSTANCE instance; // [rsp+80h] [rbp+37h] BYREF

  instance = -1;
  sesid = -1;
  szDatabaseDest = &Data;
  v24 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_SS(1036, 41, (unsigned int)WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, (_DWORD)a1, (__int64)a2);
  CacheDatabaseJetInstance = CWxString::SetPath(
                               (CWxString *)&szDatabaseDest,
                               a1,
                               L"TempCompact.dat",
                               0,
                               (const unsigned __int16 *)pconvert,
                               grbit,
                               v18,
                               v19,
                               v20,
                               v21,
                               v22);
  v5 = CacheDatabaseJetInstance;
  if ( CacheDatabaseJetInstance < 0 )
    goto LABEL_4;
  CacheDatabaseJetInstance = WxDeleteFile(szDatabaseDest);
  v5 = CacheDatabaseJetInstance;
  if ( CacheDatabaseJetInstance < 0 )
    goto LABEL_4;
  CacheDatabaseJetInstance = VerifyAdequateDiskSpace(a1);
  v5 = CacheDatabaseJetInstance;
  if ( CacheDatabaseJetInstance < 0 )
    goto LABEL_4;
  CacheDatabaseJetInstance = CreateCacheDatabaseJetInstance(a1, v8, 1, (unsigned __int16 *)&instance);
  v5 = CacheDatabaseJetInstance;
  if ( CacheDatabaseJetInstance < 0 )
    goto LABEL_4;
  v9 = JetBeginSessionA(instance, &sesid, 0, 0);
  CacheDatabaseJetInstance = HRESULTFromJET_ERR(v9, 0);
  v5 = CacheDatabaseJetInstance;
  if ( CacheDatabaseJetInstance < 0 )
    goto LABEL_4;
  v10 = JetAttachDatabaseW(sesid, a2, 1u);
  CacheDatabaseJetInstance = HRESULTFromJET_ERR(v10, 0);
  v5 = CacheDatabaseJetInstance;
  if ( CacheDatabaseJetInstance < 0 )
    goto LABEL_4;
  v11 = JetCompactW(sesid, a2, szDatabaseDest, 0, 0, 0);
  v5 = HRESULTFromJET_ERR(v11, 0);
  if ( v5 < 0 )
  {
    JetDetachDatabaseW(sesid, a2);
    v6 = v5;
    goto LABEL_5;
  }
  v12 = JetDetachDatabaseW(sesid, a2);
  CacheDatabaseJetInstance = HRESULTFromJET_ERR(v12, 0);
  v5 = CacheDatabaseJetInstance;
  if ( CacheDatabaseJetInstance < 0 )
  {
LABEL_4:
    v6 = CacheDatabaseJetInstance;
    goto LABEL_5;
  }
  if ( MoveFileExW(szDatabaseDest, a2, 1u) )
  {
    v5 = 0;
    v6 = 0;
  }
  else
  {
    LastError = WxGetLastError(v14, v13);
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147418113;
    v6 = v5;
  }
LABEL_5:
  if ( sesid != -1 )
  {
    JetEndSession(sesid, 0);
    sesid = -1;
  }
  if ( instance != -1 )
  {
    JetTerm2(instance, 1u);
    instance = -1;
  }
  if ( (_DWORD)v24 )
    WxDeleteFile(szDatabaseDest);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 42, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, (unsigned int)v5);
  CWxString::_Release((CWxString *)&szDatabaseDest);
  return v6;
}

```

## disassembly

```asm
0x1801a7c0c  mov     [rsp-8+arg_10], rbx
0x1801a7c11  mov     [rsp-8+arg_18], rsi
0x1801a7c16  push    rbp
0x1801a7c17  push    rdi
0x1801a7c18  push    r12
0x1801a7c1a  lea     rbp, [rsp-47h]
0x1801a7c1f  sub     rsp, 90h
0x1801a7c26  mov     rax, cs:__security_cookie
0x1801a7c2d  xor     rax, rsp
0x1801a7c30  mov     [rbp+57h+var_18], rax
0x1801a7c34  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801a7c38  mov     [rbp+57h+var_3C], 0
0x1801a7c3f  lea     rax, Data
0x1801a7c46  mov     [rbp+57h+instance], r12
0x1801a7c4a  mov     [rbp+57h+sesid], r12
0x1801a7c4e  mov     rdi, rdx
0x1801a7c51  mov     [rbp+57h+szDatabaseDest], rax
0x1801a7c55  mov     rsi, rcx
0x1801a7c58  mov     [rbp+57h+var_30], 0
0x1801a7c60  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a7c67  jz      short loc_1801A7C87
0x1801a7c69  lea     edx, [r12+2Ah]
0x1801a7c6e  mov     [rsp+0A0h+pconvert], rdi; unsigned __int16 *
0x1801a7c73  mov     ecx, 40Ch
0x1801a7c78  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1801a7c7f  mov     r9, rsi
0x1801a7c82  call    WPP_SF_SS
0x1801a7c87  xor     r9d, r9d; unsigned __int16 *
0x1801a7c8a  lea     r8, aTempcompactDat
0x1801a7c91  mov     rdx, rsi; unsigned __int16 *
0x1801a7c94  lea     rcx, [rbp+57h+szDatabaseDest]; this
0x1801a7c98  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z
0x1801a7c9d  mov     ebx, eax
0x1801a7c9f  test    eax, eax
0x1801a7ca1  jns     loc_1801A7D3D
0x1801a7ca7  mov     [rbp+57h+var_3C], 35Dh
0x1801a7cae  mov     edi, eax
0x1801a7cb0  mov     rcx, [rbp+57h+sesid]; sesid
0x1801a7cb4  cmp     rcx, r12
0x1801a7cb7  jz      short loc_1801A7CC5
0x1801a7cb9  xor     edx, edx; grbit
0x1801a7cbb  call    cs:__imp_JetEndSession
0x1801a7cc1  mov     [rbp+57h+sesid], r12
0x1801a7cc5  mov     rcx, [rbp+57h+instance]; instance
0x1801a7cc9  cmp     rcx, r12
0x1801a7ccc  jz      short loc_1801A7CDD
0x1801a7cce  mov     edx, 1; grbit
0x1801a7cd3  call    cs:__imp_JetTerm2
0x1801a7cd9  mov     [rbp+57h+instance], r12
0x1801a7cdd  cmp     dword ptr [rbp+57h+var_30], 0
0x1801a7ce1  jz      short loc_1801A7CEC
0x1801a7ce3  mov     rcx, [rbp+57h+szDatabaseDest]; lpPathName
0x1801a7ce7  call    ?WxDeleteFile@@YAJPEBG@Z
0x1801a7cec  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a7cf3  jz      short loc_1801A7D0E
0x1801a7cf5  mov     edx, 2Ah ; '*'
0x1801a7cfa  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1801a7d01  mov     ecx, 40Ch
0x1801a7d06  mov     r9d, ebx
0x1801a7d09  call    WPP_SF_d
0x1801a7d0e  lea     rcx, [rbp+57h+szDatabaseDest]; this
0x1801a7d12  call    ?_Release@CWxString@@AEAAXXZ
0x1801a7d17  mov     eax, edi
0x1801a7d19  mov     rcx, [rbp+57h+var_18]
0x1801a7d1d  xor     rcx, rsp; StackCookie
0x1801a7d20  call    __security_check_cookie
0x1801a7d25  lea     r11, [rsp+0A0h+var_10]
0x1801a7d2d  mov     rbx, [r11+30h]
0x1801a7d31  mov     rsi, [r11+38h]
0x1801a7d35  mov     rsp, r11
0x1801a7d38  pop     r12
0x1801a7d3a  pop     rdi
0x1801a7d3b  pop     rbp
0x1801a7d3c  retn
0x1801a7d3d  mov     rcx, [rbp+57h+szDatabaseDest]; lpPathName
0x1801a7d41  call    ?WxDeleteFile@@YAJPEBG@Z
0x1801a7d46  mov     ebx, eax
0x1801a7d48  test    eax, eax
0x1801a7d4a  jns     short loc_1801A7D58
0x1801a7d4c  mov     [rbp+57h+var_3C], 35Eh
0x1801a7d53  jmp     loc_1801A7CAE
0x1801a7d58  mov     rcx, rsi; lpDirectoryName
0x1801a7d5b  call    ?VerifyAdequateDiskSpace@@YAJPEBG@Z
0x1801a7d60  mov     ebx, eax
0x1801a7d62  test    eax, eax
0x1801a7d64  jns     short loc_1801A7D72
0x1801a7d66  mov     [rbp+57h+var_3C], 360h
0x1801a7d6d  jmp     loc_1801A7CAE
0x1801a7d72  lea     r9, [rbp+57h+instance]; unsigned __int64 *
0x1801a7d76  mov     r8d, 1; int
0x1801a7d7c  mov     rcx, rsi; unsigned __int16 *
0x1801a7d7f  call    ?CreateCacheDatabaseJetInstance@@YAJPEBG0HPEA_K@Z
0x1801a7d84  mov     ebx, eax
0x1801a7d86  test    eax, eax
0x1801a7d88  jns     short loc_1801A7D96
0x1801a7d8a  mov     [rbp+57h+var_3C], 362h
0x1801a7d91  jmp     loc_1801A7CAE
0x1801a7d96  mov     rcx, [rbp+57h+instance]; instance
0x1801a7d9a  lea     rdx, [rbp+57h+sesid]; psesid
0x1801a7d9e  xor     r9d, r9d; szPassword
0x1801a7da1  xor     r8d, r8d; szUserName
0x1801a7da4  call    cs:__imp_JetBeginSessionA
0x1801a7daa  mov     ecx, eax; int
0x1801a7dac  xor     edx, edx; int
0x1801a7dae  call    ?HRESULTFromJET_ERR@@YAJJH@Z
0x1801a7db3  mov     ebx, eax
0x1801a7db5  test    eax, eax
0x1801a7db7  js      loc_1801A7CAE
0x1801a7dbd  mov     rcx, [rbp+57h+sesid]; sesid
0x1801a7dc1  mov     r8d, 1; grbit
0x1801a7dc7  mov     rdx, rdi; szFilename
0x1801a7dca  call    cs:__imp_JetAttachDatabaseW
0x1801a7dd0  mov     ecx, eax; int
0x1801a7dd2  xor     edx, edx; int
0x1801a7dd4  call    ?HRESULTFromJET_ERR@@YAJJH@Z
0x1801a7dd9  mov     ebx, eax
0x1801a7ddb  test    eax, eax
0x1801a7ddd  js      loc_1801A7CAE
0x1801a7de3  mov     r8, [rbp+57h+szDatabaseDest]; szDatabaseDest
0x1801a7de7  xor     r9d, r9d; pfnStatus
0x1801a7dea  mov     rcx, [rbp+57h+sesid]; sesid
0x1801a7dee  mov     rdx, rdi; szDatabaseSrc
0x1801a7df1  mov     dword ptr [rsp+0A0h+grbit], 0; grbit
0x1801a7df9  mov     [rsp+0A0h+pconvert], 0; pconvert
0x1801a7e02  call    cs:__imp_JetCompactW
0x1801a7e08  mov     ecx, eax; int
0x1801a7e0a  xor     edx, edx; int
0x1801a7e0c  call    ?HRESULTFromJET_ERR@@YAJJH@Z
0x1801a7e11  mov     rcx, [rbp+57h+sesid]; sesid
0x1801a7e15  mov     ebx, eax
0x1801a7e17  mov     rdx, rdi; szFilename
0x1801a7e1a  test    eax, eax
0x1801a7e1c  js      short loc_1801A7E82
0x1801a7e1e  call    cs:__imp_JetDetachDatabaseW
0x1801a7e24  mov     ecx, eax; int
0x1801a7e26  xor     edx, edx; int
0x1801a7e28  call    ?HRESULTFromJET_ERR@@YAJJH@Z
0x1801a7e2d  mov     ebx, eax
0x1801a7e2f  test    eax, eax
0x1801a7e31  js      loc_1801A7CAE
0x1801a7e37  mov     rcx, [rbp+57h+szDatabaseDest]; lpExistingFileName
0x1801a7e3b  mov     r8d, 1; dwFlags
0x1801a7e41  mov     rdx, rdi; lpNewFileName
0x1801a7e44  call    cs:__imp_MoveFileExW
0x1801a7e4a  test    eax, eax
0x1801a7e4c  jnz     short loc_1801A7E79
0x1801a7e4e  call    WxGetLastError
0x1801a7e53  mov     ebx, eax
0x1801a7e55  test    eax, eax
0x1801a7e57  jle     short loc_1801A7E62
0x1801a7e59  movzx   ebx, ax
0x1801a7e5c  or      ebx, 80070000h
0x1801a7e62  test    ebx, ebx
0x1801a7e64  js      short loc_1801A7E6B
0x1801a7e66  mov     ebx, 8000FFFFh
0x1801a7e6b  mov     edi, ebx
0x1801a7e6d  mov     [rbp+57h+var_3C], 36Dh
0x1801a7e74  jmp     loc_1801A7CB0
0x1801a7e79  xor     ebx, ebx
0x1801a7e7b  xor     edi, edi
0x1801a7e7d  jmp     loc_1801A7CB0
0x1801a7e82  call    cs:__imp_JetDetachDatabaseW
0x1801a7e88  mov     edi, ebx
0x1801a7e8a  jmp     loc_1801A7CB0
```
