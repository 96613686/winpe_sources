# CEngine::UserLexiconExists(void)

- ea: `0x1800b14d8`
- end: `0x1800b15ab`
- name: `?UserLexiconExists@CEngine@@QEAA_NXZ`
- size: `211`
- prototype: `bool __fastcall(CEngine *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800b04a4`

## callees

- `0x180002db8`
- `0x1800061d0`
- `0x1800b13a0`
- `0x1800b14d8`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b1575`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b1575`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1581`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CEngine::UserLexiconExists(CEngine *this)
{
  bool v1; // bl
  char *FileW; // rbx
  LPCWSTR lpFileName; // [rsp+50h] [rbp+8h] BYREF
  struct ISpObjectToken *v5; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  v5 = 0;
  lpFileName = 0;
  if ( !(unsigned int)SpGetTokenFromId(
                        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Speech_OneCore\\CurrentUserLexicon",
                        &v5)
    && !((unsigned int (__fastcall *)(struct ISpObjectToken *, GUID *, const wchar_t *, _QWORD, _DWORD, LPCWSTR *))v5->lpVtbl->GetStorageFileName)(
          v5,
          &CLSID_SpUnCompressedLexicon,
          L"Datafile",
          0,
          0,
          &lpFileName)
    && lpFileName )
  {
    FileW = (char *)CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
    CloseHandle(FileW);
    v1 = FileW + 1 != 0;
  }
  CSpDynamicString::_free((LPVOID *)&lpFileName);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v5);
  return v1;
}

```

## disassembly

```asm
0x1800b14d8  mov     rax, rsp
0x1800b14db  mov     [rax+8], rcx
0x1800b14df  push    rbx
0x1800b14e0  sub     rsp, 40h
0x1800b14e4  xor     bl, bl
0x1800b14e6  mov     qword ptr [rax+10h], 0
0x1800b14ee  mov     qword ptr [rax+8], 0
0x1800b14f6  lea     rdx, [rax+10h]; struct ISpObjectToken **
0x1800b14fa  lea     rcx, aHkeyCurrentUse; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x1800b1501  call    ?SpGetTokenFromId@@YAJPEBGPEAPEAUISpObjectToken@@H@Z; SpGetTokenFromId(ushort const *,ISpObjectToken * *,int)
0x1800b1506  test    eax, eax
0x1800b1508  jnz     loc_1800B158E
0x1800b150e  mov     rcx, [rsp+48h+arg_8]
0x1800b1513  mov     rax, [rcx]
0x1800b1516  lea     rdx, [rsp+48h+lpFileName]
0x1800b151b  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], rdx
0x1800b1520  mov     [rsp+48h+dwCreationDisposition], 0
0x1800b1528  xor     r9d, r9d
0x1800b152b  lea     r8, aDatafile_0; "Datafile"
0x1800b1532  lea     rdx, CLSID_SpUnCompressedLexicon
0x1800b1539  mov     rax, [rax+98h]
0x1800b1540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1545  test    eax, eax
0x1800b1547  jnz     short loc_1800B158E
0x1800b1549  mov     rcx, [rsp+48h+lpFileName]; lpFileName
0x1800b154e  test    rcx, rcx
0x1800b1551  jz      short loc_1800B158E
0x1800b1553  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800b155c  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b1564  lea     r8d, [rax+3]; dwShareMode
0x1800b1568  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800b156d  xor     r9d, r9d; lpSecurityAttributes
0x1800b1570  mov     edx, 80000000h; dwDesiredAccess
0x1800b1575  call    cs:__imp_CreateFileW
0x1800b157b  mov     rbx, rax
0x1800b157e  mov     rcx, rax; hObject
0x1800b1581  call    cs:__imp_CloseHandle
0x1800b1587  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b158b  setnz   bl
0x1800b158e  lea     rcx, [rsp+48h+lpFileName]; this
0x1800b1593  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x1800b1598  nop
0x1800b1599  lea     rcx, [rsp+48h+arg_8]
0x1800b159e  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800b15a3  mov     al, bl
0x1800b15a5  add     rsp, 40h
0x1800b15a9  pop     rbx
0x1800b15aa  retn
```
