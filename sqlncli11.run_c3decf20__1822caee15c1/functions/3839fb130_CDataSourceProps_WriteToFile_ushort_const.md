# CDataSourceProps::WriteToFile(ushort const *)

- ea: `0x3839fb130`
- end: `0x3839fb494`
- name: `?WriteToFile@CDataSourceProps@@QEAAJPEBG@Z`
- size: `868`
- prototype: `int(CDataSourceProps *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x3839f42e0`

## callees

- `0x3838434c0`
- `0x38387c820`
- `0x38388bbe0`
- `0x38391aed0`
- `0x3839faaf0`
- `0x3839fabe0`
- `0x3839fb130`
- `0x383a98984`
- `0x383a98b58`

## import_xrefs

- `MSVCR100!_wcsicmp` at `0x3839fb29b`
- `MSVCR100!_wcsicmp` at `0x3839fb29b`
- `KERNEL32!GetLastError` at `0x3839fb367`
- `KERNEL32!GetLastError` at `0x3839fb3a6`
- `KERNEL32!GetLastError` at `0x3839fb367`
- `KERNEL32!GetLastError` at `0x3839fb3a6`
- `KERNEL32!WritePrivateProfileStringW` at `0x3839fb321`
- `KERNEL32!WritePrivateProfileStringW` at `0x3839fb321`
- `KERNEL32!DeleteFileW` at `0x3839fb35d`
- `KERNEL32!DeleteFileW` at `0x3839fb35d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDataSourceProps::WriteToFile(CDataSourceProps *this, wchar_t *a2)
{
  int FullFileName; // ebx
  const char *v4; // r8
  __int64 v5; // r9
  __int64 v6; // r15
  __int64 v7; // r14
  bool v8; // zf
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // r12
  int *v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // r8
  const WCHAR *v15; // r8
  __int64 v16; // r8
  DWORD LastError; // ecx
  unsigned __int64 v18; // rdx
  int v20; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  _BYTE v25[48]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v26; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+88h] [rbp-78h]
  __int64 v28; // [rsp+90h] [rbp-70h]
  int v29; // [rsp+98h] [rbp-68h]
  int v30; // [rsp+9Ch] [rbp-64h]
  int v31; // [rsp+A0h] [rbp-60h]
  int v32; // [rsp+A4h] [rbp-5Ch]
  WCHAR FileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v24 = -2;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = -1;
  v30 = 0;
  v31 = -1;
  v32 = 0;
  v21 = 0;
  v22 = 0;
  lpFileName = 0;
  if ( (int)CDataSourceProps::GetConnectInfo(this, (struct tagOLEDB_DLGSTRUCT *)v25) < 0 )
  {
    FullFileName = -2147467259;
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B43328[0], 3124265, off_383B49128[0], 2147500037LL);
    goto LABEL_47;
  }
  FullFileName = GetFullFileName(a2, FileName);
  if ( FullFileName < 0 )
    goto LABEL_47;
  FullFileName = CEXAutoBackupFile::BackupFile((CEXAutoBackupFile *)&v21, FileName);
  if ( FullFileName < 0 )
  {
    FullFileName = -2147467259;
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    {
      v20 = 3065;
      bidTraceW(off_383B43328[0], 3138601, off_383B49128[0], 2147500037LL);
    }
    goto LABEL_39;
  }
  v6 = v27;
  v7 = v28;
  if ( (*(_BYTE *)(v27 + 312) & 1) == 0
    || (v8 = _wcsicmp((const wchar_t *)(*(_QWORD *)(v28 + 32) + *(_QWORD *)(v27 + 320)), L"Yes") == 0, v9 = 1, !v8) )
  {
    v9 = 0;
  }
  v10 = 0;
  v11 = v9;
  v12 = &dword_383913374;
  do
  {
    v13 = *(unsigned __int16 *)v12;
    v14 = v6 + 24 * v13;
    if ( (*(_WORD *)v14 & 2) == 0 && (*(_WORD *)v14 & 4) == 0 )
    {
      v15 = 0;
      goto LABEL_24;
    }
    if ( (_WORD)v13 == 2 )
    {
      if ( !v11 )
      {
        v15 = 0;
        goto LABEL_24;
      }
      v16 = *(_QWORD *)(v6 + 56);
    }
    else
    {
      v16 = *(_QWORD *)(v14 + 8);
    }
    v15 = (const WCHAR *)(*(_QWORD *)(v7 + 32) + v16);
LABEL_24:
    if ( !WritePrivateProfileStringW(L"SQLNCLI", (LPCWSTR)&g_rgLookup[54 * *(unsigned __int16 *)v12], v15, FileName) )
    {
      LastError = GetLastError();
      if ( (bidGblFlags & 2) != 0 )
      {
        FullFileName = RemapError(LastError);
        v18 = 3191817;
        if ( (FullFileName || (bidGblFlags & 0x40) != 0) && off_383B49128[0] )
        {
          if ( FullFileName < 0 )
            v18 = 3191849;
          v20 = v18 >> 10;
          bidTraceW(off_383B43328[0], v18, off_383B49128[0], (unsigned int)FullFileName);
        }
      }
      else
      {
        FullFileName = RemapError(LastError);
      }
      goto LABEL_39;
    }
    ++v10;
    v12 = (int *)((char *)v12 + 6);
    v5 = 2;
    v4 = L"Server";
  }
  while ( v10 < 0x1A );
  if ( !lpFileName )
    goto LABEL_42;
  if ( v22 )
  {
    if ( !DeleteFileW(lpFileName) )
      GetLastError();
    ((void (__fastcall *)(struct IMalloc *, LPCWSTR))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, lpFileName);
    lpFileName = 0;
    ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v22);
    v22 = 0;
    goto LABEL_42;
  }
LABEL_39:
  if ( lpFileName && v22 )
    CEXAutoBackupFile::RestoreFile((CEXAutoBackupFile *)&v21);
LABEL_42:
  if ( lpFileName && v22 )
    CEXAutoBackupFile::RestoreFile((CEXAutoBackupFile *)&v21);
  if ( v21 )
    ((void (__fastcall *)(struct IMalloc *, __int64, const char *, __int64, int))g_pMO->lpVtbl->Free)(
      g_pMO,
      v21,
      v4,
      v5,
      v20);
LABEL_47:
  CDlgATTRs::Uninitialize((CDlgATTRs *)&v26);
  return (unsigned int)FullFileName;
}

```

## disassembly

```asm
0x3839fb130  push    rbp
0x3839fb132  push    rsi
0x3839fb133  push    rdi
0x3839fb134  push    r12
0x3839fb136  push    r13
0x3839fb138  push    r14
0x3839fb13a  push    r15
0x3839fb13c  lea     rbp, [rsp-5D0h]
0x3839fb144  sub     rsp, 6D0h
0x3839fb14b  mov     [rsp+700h+var_6B8], 0FFFFFFFFFFFFFFFEh
0x3839fb154  mov     [rsp+700h+arg_10], rbx
0x3839fb15c  mov     rax, cs:__security_cookie
0x3839fb163  xor     rax, rsp
0x3839fb166  mov     [rbp+600h+var_40], rax
0x3839fb16d  mov     rbx, rdx
0x3839fb170  xor     r13d, r13d
0x3839fb173  mov     [rbp+600h+var_680], r13w
0x3839fb178  mov     [rbp+600h+var_678], r13
0x3839fb17c  mov     [rbp+600h+var_670], r13
0x3839fb180  mov     [rbp+600h+var_668], 0FFFFFFFFh
0x3839fb187  mov     [rbp+600h+var_664], r13d
0x3839fb18b  mov     [rbp+600h+var_660], 0FFFFFFFFh
0x3839fb192  mov     [rbp+600h+var_65C], r13d
0x3839fb196  mov     [rsp+700h+var_6D0], r13
0x3839fb19b  mov     [rsp+700h+var_6C8], r13
0x3839fb1a0  mov     [rsp+700h+lpFileName], r13
0x3839fb1a5  lea     rdx, [rsp+700h+var_6B0]; struct tagOLEDB_DLGSTRUCT *
0x3839fb1aa  call    ?GetConnectInfo@CDataSourceProps@@QEAAJPEAUtagOLEDB_DLGSTRUCT@@@Z; CDataSourceProps::GetConnectInfo(tagOLEDB_DLGSTRUCT *)
0x3839fb1af  test    eax, eax
0x3839fb1b1  jns     short loc_3839FB1F6
0x3839fb1b3  mov     ebx, 80004005h
0x3839fb1b8  test    byte ptr cs:_bidGblFlags, 2
0x3839fb1bf  jz      short loc_3839FB1F1
0x3839fb1c1  mov     rcx, cs:off_383B43328; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fb1c8  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fb1cf  test    rax, rax
0x3839fb1d2  jz      short loc_3839FB1F1
0x3839fb1d4  mov     [rsp+700h+var_6E0], 0BEBh
0x3839fb1dc  mov     r9d, ebx
0x3839fb1df  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fb1e6  mov     edx, 2FAC29h
0x3839fb1eb  call    _bidTraceW
0x3839fb1f0  nop
0x3839fb1f1  jmp     loc_3839FB45F
0x3839fb1f6  mov     r8d, 40000000h
0x3839fb1fc  lea     rdx, [rbp+600h+FileName]; lpFileName
0x3839fb203  mov     rcx, rbx; Path
0x3839fb206  call    GetFullFileName
0x3839fb20b  mov     ebx, eax
0x3839fb20d  test    eax, eax
0x3839fb20f  jns     short loc_3839FB216
0x3839fb211  jmp     loc_3839FB45F
0x3839fb216  lea     rdx, [rbp+600h+FileName]; unsigned __int16 *
0x3839fb21d  lea     rcx, [rsp+700h+var_6D0]; this
0x3839fb222  call    ?BackupFile@CEXAutoBackupFile@@QEAAJPEBG@Z; CEXAutoBackupFile::BackupFile(ushort const *)
0x3839fb227  mov     ebx, eax
0x3839fb229  test    eax, eax
0x3839fb22b  jns     short loc_3839FB277
0x3839fb22d  mov     ebx, 80004005h
0x3839fb232  test    byte ptr cs:_bidGblFlags, 2
0x3839fb239  jz      loc_3839FB411
0x3839fb23f  mov     rcx, cs:off_383B43328; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fb246  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fb24d  test    rax, rax
0x3839fb250  jz      loc_3839FB411
0x3839fb256  mov     [rsp+700h+var_6E0], 0BF9h
0x3839fb25e  mov     r9d, ebx
0x3839fb261  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fb268  mov     edx, 2FE429h
0x3839fb26d  call    _bidTraceW
0x3839fb272  jmp     loc_3839FB411
0x3839fb277  mov     r15, [rbp+600h+var_678]
0x3839fb27b  mov     r14, [rbp+600h+var_670]
0x3839fb27f  test    byte ptr [r15+138h], 1
0x3839fb287  jz      short loc_3839FB2AA
0x3839fb289  mov     rcx, [r15+140h]
0x3839fb290  add     rcx, [r14+20h]; String1
0x3839fb294  lea     rdx, aYes_0; "Yes"
0x3839fb29b  call    cs:__imp__wcsicmp
0x3839fb2a1  test    eax, eax
0x3839fb2a3  mov     eax, 1
0x3839fb2a8  jz      short loc_3839FB2AD
0x3839fb2aa  mov     eax, r13d
0x3839fb2ad  mov     edi, r13d
0x3839fb2b0  movsxd  r12, eax
0x3839fb2b3  lea     rsi, dword_383913374
0x3839fb2ba  lea     r8, ?g_rgLookup@@3QBUtagKeyLookup@@B; "Server"
0x3839fb2c1  mov     r9d, 2
0x3839fb2c7  nop     word ptr [rax+rax+00000000h]
0x3839fb2d0  movzx   ecx, word ptr [rsi]
0x3839fb2d3  mov     edx, ecx
0x3839fb2d5  imul    rdx, 36h ; '6'
0x3839fb2d9  add     rdx, r8; lpKeyName
0x3839fb2dc  lea     rax, [rcx+rcx*2]
0x3839fb2e0  lea     r8, [r15+rax*8]
0x3839fb2e4  movzx   eax, word ptr [r8]
0x3839fb2e8  test    al, 2
0x3839fb2ea  jnz     short loc_3839FB2F5
0x3839fb2ec  test    al, 4
0x3839fb2ee  jnz     short loc_3839FB2F5
0x3839fb2f0  mov     r8, r13
0x3839fb2f3  jmp     short loc_3839FB313
0x3839fb2f5  cmp     r9w, cx
0x3839fb2f9  jnz     short loc_3839FB30B
0x3839fb2fb  test    r12, r12
0x3839fb2fe  jnz     short loc_3839FB305
0x3839fb300  mov     r8, r13
0x3839fb303  jmp     short loc_3839FB313
0x3839fb305  mov     r8, [r15+38h]
0x3839fb309  jmp     short loc_3839FB30F
0x3839fb30b  mov     r8, [r8+8]
0x3839fb30f  add     r8, [r14+20h]; lpString
0x3839fb313  lea     r9, [rbp+600h+FileName]; lpFileName
0x3839fb31a  lea     rcx, AppName; "SQLNCLI"
0x3839fb321  call    cs:__imp_WritePrivateProfileStringW
0x3839fb327  test    eax, eax
0x3839fb329  jz      short loc_3839FB3A6
0x3839fb32b  inc     edi
0x3839fb32d  add     rsi, 6
0x3839fb331  cmp     edi, 1Ah
0x3839fb334  mov     r9d, 2
0x3839fb33a  lea     r8, ?g_rgLookup@@3QBUtagKeyLookup@@B; "Server"
0x3839fb341  jb      short loc_3839FB2D0
0x3839fb343  mov     rcx, [rsp+700h+lpFileName]; lpFileName
0x3839fb348  test    rcx, rcx
0x3839fb34b  jz      loc_3839FB42C
0x3839fb351  cmp     [rsp+700h+var_6C8], 0
0x3839fb357  jz      loc_3839FB411
0x3839fb35d  call    cs:__imp_DeleteFileW
0x3839fb363  test    eax, eax
0x3839fb365  jnz     short loc_3839FB36D
0x3839fb367  call    cs:__imp_GetLastError
0x3839fb36d  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3839fb374  mov     rax, [rcx]
0x3839fb377  mov     rdx, [rsp+700h+lpFileName]
0x3839fb37c  call    qword ptr [rax+80h]
0x3839fb382  mov     [rsp+700h+lpFileName], r13
0x3839fb387  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3839fb38e  mov     rax, [rcx]
0x3839fb391  mov     rdx, [rsp+700h+var_6C8]
0x3839fb396  call    qword ptr [rax+80h]
0x3839fb39c  mov     [rsp+700h+var_6C8], r13
0x3839fb3a1  jmp     loc_3839FB42C
0x3839fb3a6  call    cs:__imp_GetLastError
0x3839fb3ac  mov     ecx, eax; unsigned int
0x3839fb3ae  test    byte ptr cs:_bidGblFlags, 2
0x3839fb3b5  jz      short loc_3839FB40A
0x3839fb3b7  call    ?RemapError@@YAJK@Z; RemapError(ulong)
0x3839fb3bc  mov     ebx, eax
0x3839fb3be  mov     edx, 30B409h
0x3839fb3c3  mov     rcx, cs:off_383B43328; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fb3ca  test    eax, eax
0x3839fb3cc  jnz     short loc_3839FB3D7
0x3839fb3ce  test    byte ptr cs:_bidGblFlags, 40h
0x3839fb3d5  jz      short loc_3839FB411
0x3839fb3d7  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fb3de  test    rax, rax
0x3839fb3e1  jz      short loc_3839FB411
0x3839fb3e3  mov     eax, 30B429h
0x3839fb3e8  test    ebx, ebx
0x3839fb3ea  cmovs   rdx, rax
0x3839fb3ee  mov     rax, rdx
0x3839fb3f1  shr     rax, 0Ah
0x3839fb3f5  mov     [rsp+700h+var_6E0], eax
0x3839fb3f9  mov     r9d, ebx
0x3839fb3fc  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fb403  call    _bidTraceW
0x3839fb408  jmp     short loc_3839FB411
0x3839fb40a  call    ?RemapError@@YAJK@Z; RemapError(ulong)
0x3839fb40f  mov     ebx, eax
0x3839fb411  cmp     [rsp+700h+lpFileName], 0
0x3839fb417  jz      short loc_3839FB42C
0x3839fb419  cmp     [rsp+700h+var_6C8], 0
0x3839fb41f  jz      short loc_3839FB42C
0x3839fb421  lea     rcx, [rsp+700h+var_6D0]; this
0x3839fb426  call    ?RestoreFile@CEXAutoBackupFile@@QEAAJXZ; CEXAutoBackupFile::RestoreFile(void)
0x3839fb42b  nop
0x3839fb42c  cmp     [rsp+700h+lpFileName], 0
0x3839fb432  jz      short loc_3839FB447
0x3839fb434  cmp     [rsp+700h+var_6C8], 0
0x3839fb43a  jz      short loc_3839FB447
0x3839fb43c  lea     rcx, [rsp+700h+var_6D0]; this
0x3839fb441  call    ?RestoreFile@CEXAutoBackupFile@@QEAAJXZ; CEXAutoBackupFile::RestoreFile(void)
0x3839fb446  nop
0x3839fb447  mov     rdx, [rsp+700h+var_6D0]
0x3839fb44c  test    rdx, rdx
0x3839fb44f  jz      short loc_3839FB45F
0x3839fb451  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3839fb458  mov     rax, [rcx]
0x3839fb45b  call    qword ptr [rax+28h]
0x3839fb45e  nop
0x3839fb45f  lea     rcx, [rbp+600h+var_680]; this
0x3839fb463  call    ?Uninitialize@CDlgATTRs@@QEAAXXZ; CDlgATTRs::Uninitialize(void)
0x3839fb468  mov     eax, ebx
0x3839fb46a  mov     rcx, [rbp+600h+var_40]
0x3839fb471  xor     rcx, rsp; StackCookie
0x3839fb474  call    __security_check_cookie
0x3839fb479  mov     rbx, [rsp+700h+arg_10]
0x3839fb481  add     rsp, 6D0h
0x3839fb488  pop     r15
0x3839fb48a  pop     r14
0x3839fb48c  pop     r13
0x3839fb48e  pop     r12
0x3839fb490  pop     rdi
0x3839fb491  pop     rsi
0x3839fb492  pop     rbp
0x3839fb493  retn
```
