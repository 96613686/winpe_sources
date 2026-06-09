# CAutoDestListParser::_EnsureStorage(void)

- ea: `0x180165de0`
- end: `0x1801666af`
- name: `?_EnsureStorage@CAutoDestListParser@@IEAAJXZ`
- size: `2255`
- prototype: `__int64 __fastcall(CAutoDestListParser *__hidden this)`
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180070040`
- `0x1801657dc`
- `0x180165ac0`
- `0x180165bc8`
- `0x180165cd0`
- `0x180167920`

## callees

- `0x18001c7ec`
- `0x18001d7a0`
- `0x180038f50`
- `0x180083c94`
- `0x180165de0`
- `0x18033e6cc`
- `0x18033ee40`
- `0x1803b243c`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801662db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801662db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180165f03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801662bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180165f03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801662bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180165ec7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180165f88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180166030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801660e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801662cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016631b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801663ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180166459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801664d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180166520`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016659d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801665e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016665c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180165ec7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180165f88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180166030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801660e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801662cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016631b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801663ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180166459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801664d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180166520`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016659d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801665e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016665c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180165e85`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801662a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180165e85`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801662a3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180166277`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180166277`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x180165ff7`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x18016641c`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x180165ff7`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x18016641c`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180166227`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180166227`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CAutoDestListParser::_EnsureStorage(CAutoDestListParser *this)
{
  IStorage **v2; // r15
  int v3; // eax
  DWORD v4; // r13d
  DWORD v5; // r12d
  int v6; // eax
  unsigned int v7; // ebx
  __int64 FileW; // rdi
  const char *v10; // r9
  unsigned int LastError; // ebx
  int v12; // eax
  int v13; // eax
  unsigned int v14; // ebx
  ILockBytes *v15; // rcx
  IStorage *v16; // rcx
  DWORD v17; // edx
  HRESULT v18; // eax
  ILockBytes *v19; // rcx
  IStorage *v20; // rbx
  HRESULT (__stdcall *QueryInterface)(IStorage *, const IID *const, void **); // r15
  __int64 v22; // rcx
  int v23; // eax
  ILockBytes *v24; // rcx
  ILockBytes *v25; // rax
  ILockBytes *v26; // rbx
  IStorage *v27; // rcx
  DWORD v28; // r8d
  HRESULT v29; // eax
  unsigned int v30; // ebx
  ILockBytes *v31; // rcx
  const char *v32; // r9
  char *v33; // r13
  DWORD v34; // ebx
  int v35; // eax
  ILockBytes *v36; // rcx
  IStorage *v37; // rcx
  DWORD v38; // edx
  HRESULT DocfileOnILockBytes; // eax
  ILockBytes *v40; // rcx
  ILockBytes *v41; // rcx
  ILockBytes *v42; // rcx
  int v43; // eax
  ILockBytes *v44; // rcx
  ILockBytes *v45; // rcx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-48h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-48h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-48h]
  ILockBytes *plkbyt; // [rsp+40h] [rbp-28h] BYREF
  HANDLE hObject[2]; // [rsp+48h] [rbp-20h] BYREF
  char v51; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v2 = (IStorage **)((char *)this + 32);
  if ( *((_QWORD *)this + 4) )
    return 1;
  v3 = *((_DWORD *)this + 41);
  v4 = -1073741824;
  if ( v3 != 1 )
    v4 = 0x80000000;
  v5 = (v3 == 1) + 3;
  v6 = CAutoDestListParser::ReadWriteLock::AcquireLock((CAutoDestListParser *)((char *)this + 48));
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
      (const char *)(unsigned int)v6,
      dwCreationDisposition);
    return v7;
  }
  hObject[1] = this;
  v51 = 1;
  plkbyt = 0;
  FileW = (__int64)CreateFileW(*((LPCWSTR *)this + 1), v4, 3u, 0, v5, 0, 0);
  hObject[0] = (HANDLE)FileW;
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2CE,
                  (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
                  v10);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle((HANDLE)FileW);
    CAutoDestListParser::ReadWriteLock::ReleaseLock((CAutoDestListParser *)((char *)this + 48));
    return LastError;
  }
  if ( GetLastError() == 183 || (v12 = *((_DWORD *)this + 41)) == 0 )
  {
    v25 = (ILockBytes *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v26 = v25;
    if ( !v25 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
        (const char *)0x8007000ELL,
        dwCreationDispositiona);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E5,
        (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
        (const char *)0x8007000ELL,
        dwCreationDispositionb);
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)FileW);
      CAutoDestListParser::ReadWriteLock::ReleaseLock((CAutoDestListParser *)((char *)this + 48));
      return 2147942414LL;
    }
    *(_OWORD *)&v25->lpVtbl = 0;
    *(_OWORD *)&v25[2].lpVtbl = 0;
    HIDWORD(v25[1].lpVtbl) = 1;
    v25->lpVtbl = (struct ILockBytesVtbl *)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILockBytes>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v26->lpVtbl = (struct ILockBytesVtbl *)&CFileLockBytes::`vftable';
    v26[2].lpVtbl = (struct ILockBytesVtbl *)-1LL;
    v26[3].lpVtbl = 0;
    if ( &v26[2] != (ILockBytes *)hObject )
    {
      v26[2].lpVtbl = (struct ILockBytesVtbl *)FileW;
      FileW = -1;
      hObject[0] = (HANDLE)-1LL;
    }
    plkbyt = v26;
    ((void (__fastcall *)(ILockBytes *))v26->lpVtbl->AddRef)(v26);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ILockBytes>::Release(v26);
    v27 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      ((void (__fastcall *)(IStorage *))v27->lpVtbl->Release)(v27);
    }
    v28 = 4194368;
    if ( *((_DWORD *)this + 41) )
      v28 = 4194338;
    v29 = StgOpenStorageOnILockBytes(plkbyt, 0, v28, 0, 0, v2);
    v30 = v29;
    if ( (v29 == -2147286775 || v29 == -2147286960) && *((_DWORD *)this + 41) == 1 )
    {
      v31 = plkbyt;
      if ( plkbyt )
      {
        plkbyt = 0;
        ((void (__fastcall *)(ILockBytes *))v31->lpVtbl->Release)(v31);
      }
      DeleteFileW(*((LPCWSTR *)this + 1));
      v33 = (char *)CreateFileW(*((LPCWSTR *)this + 1), v4, 3u, 0, v5, 0, 0);
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v34 = GetLastError();
        CloseHandle((HANDLE)FileW);
        SetLastError(v34);
      }
      hObject[0] = v33;
      if ( ((unsigned __int64)(v33 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        v35 = CFileLockBytes::Create(hObject, &plkbyt);
        v14 = v35;
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F8,
            (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
            (const char *)(unsigned int)v35,
            dwCreationDispositiona);
          if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(hObject[0]);
          v36 = plkbyt;
          if ( plkbyt )
          {
            plkbyt = 0;
            ((void (__fastcall *)(ILockBytes *))v36->lpVtbl->Release)(v36);
          }
          goto LABEL_94;
        }
        v37 = *v2;
        if ( *v2 )
        {
          *v2 = 0;
          ((void (__fastcall *)(IStorage *))v37->lpVtbl->Release)(v37);
        }
        v38 = 4198464;
        if ( *((_DWORD *)this + 41) )
          v38 = 4198434;
        DocfileOnILockBytes = StgCreateDocfileOnILockBytes(plkbyt, v38, 0, v2);
        v14 = DocfileOnILockBytes;
        if ( DocfileOnILockBytes < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F9,
            (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
            (const char *)(unsigned int)DocfileOnILockBytes,
            dwCreationDispositiona);
          if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(hObject[0]);
          v40 = plkbyt;
          if ( plkbyt )
          {
            plkbyt = 0;
            ((void (__fastcall *)(ILockBytes *))v40->lpVtbl->Release)(v40);
          }
          goto LABEL_94;
        }
LABEL_29:
        FileW = (__int64)hObject[0];
        goto LABEL_30;
      }
      v30 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2EF,
              (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
              v32);
      if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v33);
    }
    else
    {
      if ( v29 >= 0 )
        goto LABEL_30;
      if ( v29 == -2147287007 || v29 == -2147286775 || v29 == -2147286960 )
      {
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle((HANDLE)FileW);
        v42 = plkbyt;
        if ( plkbyt )
        {
          plkbyt = 0;
          ((void (__fastcall *)(ILockBytes *))v42->lpVtbl->Release)(v42);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2FF,
          (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
          (const char *)(unsigned int)v29,
          dwCreationDispositiona);
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle((HANDLE)FileW);
        v41 = plkbyt;
        if ( plkbyt )
        {
          plkbyt = 0;
          ((void (__fastcall *)(ILockBytes *))v41->lpVtbl->Release)(v41);
        }
      }
    }
    CAutoDestListParser::ReadWriteLock::ReleaseLock((CAutoDestListParser *)((char *)this + 48));
    return v30;
  }
  if ( v12 == 1 )
  {
    v13 = CFileLockBytes::Create(hObject, &plkbyt);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x303,
        (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
        (const char *)(unsigned int)v13,
        dwCreationDispositiona);
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject[0]);
      v15 = plkbyt;
      if ( plkbyt )
      {
        plkbyt = 0;
        ((void (__fastcall *)(ILockBytes *))v15->lpVtbl->Release)(v15);
      }
LABEL_94:
      CAutoDestListParser::ReadWriteLock::ReleaseLock((CAutoDestListParser *)((char *)this + 48));
      return v14;
    }
    v16 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      ((void (__fastcall *)(IStorage *))v16->lpVtbl->Release)(v16);
    }
    v17 = 4198464;
    if ( *((_DWORD *)this + 41) )
      v17 = 4198434;
    v18 = StgCreateDocfileOnILockBytes(plkbyt, v17, 0, v2);
    v14 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x304,
        (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
        (const char *)(unsigned int)v18,
        dwCreationDispositiona);
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject[0]);
      v19 = plkbyt;
      if ( plkbyt )
      {
        plkbyt = 0;
        ((void (__fastcall *)(ILockBytes *))v19->lpVtbl->Release)(v19);
      }
      goto LABEL_94;
    }
    goto LABEL_29;
  }
LABEL_30:
  if ( *((_DWORD *)this + 41) == 1 )
  {
    v20 = *v2;
    QueryInterface = (*v2)->lpVtbl->QueryInterface;
    v22 = *((_QWORD *)this + 5);
    if ( v22 )
    {
      *((_QWORD *)this + 5) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = ((__int64 (__fastcall *)(IStorage *, GUID *, char *))QueryInterface)(
            v20,
            &GUID_0e6d4d92_6738_11cf_9608_00aa00680db4,
            (char *)this + 40);
    v14 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x309,
        (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
        (const char *)(unsigned int)v23,
        dwCreationDispositiona);
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)FileW);
      v24 = plkbyt;
      if ( plkbyt )
      {
        plkbyt = 0;
        ((void (__fastcall *)(ILockBytes *))v24->lpVtbl->Release)(v24);
      }
      goto LABEL_94;
    }
    v43 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 24LL))(
            *((_QWORD *)this + 5),
            0xFFFFFFFFLL);
    v14 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x313,
        (unsigned int)"onecoreuap\\shell\\SrcPkg\\ShellDataLayer\\AutomaticDestinationList\\src\\AutoDestListParser.cpp",
        (const char *)(unsigned int)v43,
        dwCreationDispositiona);
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)FileW);
      v44 = plkbyt;
      if ( plkbyt )
      {
        plkbyt = 0;
        ((void (__fastcall *)(ILockBytes *))v44->lpVtbl->Release)(v44);
      }
      goto LABEL_94;
    }
  }
  v51 = 0;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  v45 = plkbyt;
  if ( plkbyt )
  {
    plkbyt = 0;
    ((void (__fastcall *)(ILockBytes *))v45->lpVtbl->Release)(v45);
  }
  return 0;
}

```

## disassembly

```asm
0x180165de0  push    rbp
0x180165de2  push    rbx
0x180165de3  push    rsi
0x180165de4  push    rdi
0x180165de5  push    r12
0x180165de7  push    r13
0x180165de9  push    r14
0x180165deb  push    r15
0x180165ded  mov     rbp, rsp
0x180165df0  sub     rsp, 68h
0x180165df4  mov     r14, rcx
0x180165df7  lea     r15, [rcx+20h]
0x180165dfb  cmp     qword ptr [r15], 0
0x180165dff  jnz     loc_180166698
0x180165e05  mov     eax, [rcx+0A4h]
0x180165e0b  mov     ecx, 80000000h
0x180165e10  mov     r13d, 0C0000000h
0x180165e16  cmp     eax, 1
0x180165e19  cmovnz  r13d, ecx
0x180165e1d  xor     edi, edi
0x180165e1f  mov     r12d, edi
0x180165e22  cmp     eax, 1
0x180165e25  setz    r12b
0x180165e29  add     r12d, 3
0x180165e2d  lea     rcx, [r14+30h]; this
0x180165e31  call    ?AcquireLock@ReadWriteLock@CAutoDestListParser@@QEAAJXZ; CAutoDestListParser::ReadWriteLock::AcquireLock(void)
0x180165e36  mov     ebx, eax
0x180165e38  test    eax, eax
0x180165e3a  jns     short loc_180165E5B
0x180165e3c  mov     rcx, [rbp+40h]; this
0x180165e40  mov     r9d, eax; char *
0x180165e43  lea     r8, aOnecoreuapShel_80; "onecoreuap\\shell\\SrcPkg\\ShellDataLay"...
0x180165e4a  mov     edx, 2C1h; void *
0x180165e4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165e54  mov     eax, ebx
0x180165e56  jmp     loc_18016669D
0x180165e5b  mov     [rbp+var_18], r14
0x180165e5f  mov     [rbp+var_10], 1
0x180165e63  mov     [rbp+plkbyt], rdi
0x180165e67  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x180165e6c  mov     [rsp+68h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180165e70  mov     [rsp+68h+dwCreationDisposition], r12d; int
0x180165e75  xor     r9d, r9d; lpSecurityAttributes
0x180165e78  mov     r8d, 3; dwShareMode
0x180165e7e  mov     edx, r13d; dwDesiredAccess
0x180165e81  mov     rcx, [r14+8]; lpFileName
0x180165e85  call    cs:__imp_CreateFileW
0x180165e8c  nop     dword ptr [rax+rax+00h]
0x180165e91  mov     rdi, rax
0x180165e94  mov     [rbp+hObject], rax
0x180165e98  inc     rax
0x180165e9b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180165ea1  jnz     short loc_180165F03
0x180165ea3  mov     rcx, [rbp+40h]; this
0x180165ea7  lea     r8, aOnecoreuapShel_80; "onecoreuap\\shell\\SrcPkg\\ShellDataLay"...
0x180165eae  mov     edx, 2CEh; void *
0x180165eb3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180165eb8  mov     ebx, eax
0x180165eba  lea     rdx, [rdi-1]
0x180165ebe  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180165ec2  ja      short loc_180165ED4
0x180165ec4  mov     rcx, rdi; hObject
0x180165ec7  call    cs:__imp_CloseHandle
0x180165ece  nop     dword ptr [rax+rax+00h]
0x180165ed3  nop
0x180165ed4  mov     rcx, [rbp+plkbyt]
0x180165ed8  test    rcx, rcx
0x180165edb  jz      short loc_180165EF2
0x180165edd  mov     [rbp+plkbyt], 0
0x180165ee5  mov     rax, [rcx]
0x180165ee8  mov     rax, [rax+10h]
0x180165eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165ef1  nop
0x180165ef2  lea     rcx, [r14+30h]; this
0x180165ef6  call    ?ReleaseLock@ReadWriteLock@CAutoDestListParser@@QEAAXXZ; CAutoDestListParser::ReadWriteLock::ReleaseLock(void)
0x180165efb  nop
0x180165efc  mov     eax, ebx
0x180165efe  jmp     loc_18016669D
0x180165f03  call    cs:__imp_GetLastError
0x180165f0a  nop     dword ptr [rax+rax+00h]
0x180165f0f  cmp     eax, 0B7h
0x180165f14  jz      loc_18016611E
0x180165f1a  mov     eax, [r14+0A4h]
0x180165f21  test    eax, eax
0x180165f23  jz      loc_18016611E
0x180165f29  cmp     eax, 1
0x180165f2c  jnz     loc_18016606C
0x180165f32  mov     rcx, [rbp+plkbyt]
0x180165f36  xor     edi, edi
0x180165f38  test    rcx, rcx
0x180165f3b  jz      short loc_180165F4E
0x180165f3d  mov     [rbp+plkbyt], rdi
0x180165f41  mov     rax, [rcx]
0x180165f44  mov     rax, [rax+10h]
0x180165f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165f4d  nop
0x180165f4e  lea     rdx, [rbp+plkbyt]
0x180165f52  lea     rcx, [rbp+hObject]
0x180165f56  call    ?Create@CFileLockBytes@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAPEAUILockBytes@@@Z; CFileLockBytes::Create(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ILockBytes * *)
0x180165f5b  mov     ebx, eax
0x180165f5d  test    eax, eax
0x180165f5f  jns     short loc_180165FC0
0x180165f61  mov     rcx, [rbp+40h]; this
0x180165f65  mov     r9d, eax; char *
0x180165f68  lea     r8, aOnecoreuapShel_80; "onecoreuap\\shell\\SrcPkg\\ShellDataLay"...
0x180165f6f  mov     edx, 303h; void *
0x180165f74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165f79  nop
0x180165f7a  mov     rcx, [rbp+hObject]; hObject
0x180165f7e  lea     rdx, [rcx-1]
0x180165f82  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180165f86  ja      short loc_180165F95
0x180165f88  call    cs:__imp_CloseHandle
0x180165f8f  nop     dword ptr [rax+rax+00h]
0x180165f94  nop
0x180165f95  mov     rcx, [rbp+plkbyt]
0x180165f99  test    rcx, rcx
0x180165f9c  jz      short loc_180165FAF
0x180165f9e  mov     [rbp+plkbyt], rdi
0x180165fa2  mov     rax, [rcx]
0x180165fa5  mov     rax, [rax+10h]
0x180165fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165fae  nop
0x180165faf  lea     rcx, [r14+30h]; this
0x180165fb3  call    ?ReleaseLock@ReadWriteLock@CAutoDestListParser@@QEAAXXZ; CAutoDestListParser::ReadWriteLock::ReleaseLock(void)
0x180165fb8  nop
0x180165fb9  mov     eax, ebx
0x180165fbb  jmp     loc_18016669D
0x180165fc0  mov     rcx, [r15]
0x180165fc3  test    rcx, rcx
0x180165fc6  jz      short loc_180165FD8
0x180165fc8  mov     [r15], rdi
0x180165fcb  mov     rax, [rcx]
0x180165fce  mov     rax, [rax+10h]
0x180165fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165fd7  nop
0x180165fd8  mov     edx, 401040h
0x180165fdd  mov     eax, 401022h
0x180165fe2  cmp     dword ptr [r14+0A4h], 0
0x180165fea  cmovnz  edx, eax; grfMode
0x180165fed  mov     r9, r15; ppstgOpen
0x180165ff0  xor     r8d, r8d; reserved
0x180165ff3  mov     rcx, [rbp+plkbyt]; plkbyt
0x180165ff7  call    cs:__imp_StgCreateDocfileOnILockBytes
0x180165ffe  nop     dword ptr [rax+rax+00h]
0x180166003  mov     ebx, eax
0x180166005  test    eax, eax
0x180166007  jns     short loc_180166068
0x180166009  mov     rcx, [rbp+40h]; this
0x18016600d  mov     r9d, eax; char *
0x180166010  lea     r8, aOnecoreuapShel_80; "onecoreuap\\shell\\SrcPkg\\ShellDataLay"...
0x180166017  mov     edx, 304h; void *
0x18016601c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180166021  nop
0x180166022  mov     rcx, [rbp+hObject]; hObject
0x180166026  lea     rdx, [rcx-1]
0x18016602a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18016602e  ja      short loc_18016603D
0x180166030  call    cs:__imp_CloseHandle
0x180166037  nop     dword ptr [rax+rax+00h]
0x18016603c  nop
0x18016603d  mov     rcx, [rbp+plkbyt]
0x180166041  test    rcx, rcx
0x180166044  jz      short loc_180166057
0x180166046  mov     [rbp+plkbyt], rdi
0x18016604a  mov     rax, [rcx]
0x18016604d  mov     rax, [rax+10h]
0x180166051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166056  nop
0x180166057  lea     rcx, [r14+30h]; this
0x18016605b  call    ?ReleaseLock@ReadWriteLock@CAutoDestListParser@@QEAAXXZ; CAutoDestListParser::ReadWriteLock::ReleaseLock(void)
0x180166060  nop
0x180166061  mov     eax, ebx
0x180166063  jmp     loc_18016669D
0x180166068  mov     rdi, [rbp+hObject]
0x18016606c  cmp     dword ptr [r14+0A4h], 1
0x180166074  jnz     loc_1801665D5
0x18016607a  mov     rbx, [r15]
0x18016607d  mov     rax, [rbx]
0x180166080  mov     r15, [rax]
0x180166083  mov     rcx, [r14+28h]
0x180166087  xor     r12d, r12d
0x18016608a  test    rcx, rcx
0x18016608d  jz      short loc_1801660A0
0x18016608f  mov     [r14+28h], r12
0x180166093  mov     rdx, [rcx]
0x180166096  mov     rax, [rdx+10h]
0x18016609a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016609f  nop
0x1801660a0  lea     r8, [r14+28h]
0x1801660a4  lea     rdx, _GUID_0e6d4d92_6738_11cf_9608_00aa00680db4
0x1801660ab  mov     rcx, rbx
0x1801660ae  mov     rax, r15
0x1801660b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801660b6  mov     ebx, eax
0x1801660b8  test    eax, eax
0x1801660ba  jns     loc_18016655C
0x1801660c0  mov     rcx, [rbp+40h]; this
0x1801660c4  mov     r9d, eax; char *
0x1801660c7  lea     r8, aOnecoreuapShel_80; "onecoreuap\\shell\\SrcPkg\\ShellDataLay"...
0x1801660ce  mov     edx, 309h; void *
0x1801660d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801660d8  nop
0x1801660d9  lea     rcx, [rdi-1]
0x1801660dd  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801660e1  ja      short loc_1801660F3
0x1801660e3  mov     rcx, rdi; hObject
0x1801660e6  call    cs:__imp_CloseHandle
0x1801660ed  nop     dword ptr [rax+rax+00h]
0x1801660f2  nop
0x1801660f3  mov     rcx, [rbp+plkbyt]
0x1801660f7  test    rcx, rcx
0x1801660fa  jz      short loc_18016610D
0x1801660fc  mov     [rbp+plkbyt], r12
0x180166100  mov     rax, [rcx]
0x180166103  mov     rax, [rax+10h]
0x180166107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016610c  nop
0x18016610d  lea     rcx, [r14+30h]; this
0x180166111  call    ?ReleaseLock@ReadWriteLock@CAutoDestListParser@@QEAAXXZ; CAutoDestListParser::ReadWriteLock::ReleaseLock(void)
0x180166116  nop
0x180166117  mov     eax, ebx
0x180166119  jmp     loc_18016669D
0x18016611e  mov     rcx, [rbp+plkbyt]
0x180166122  test    rcx, rcx
0x180166125  jz      short loc_18016613C
0x180166127  mov     [rbp+plkbyt], 0
0x18016612f  mov     rax, [rcx]
0x180166132  mov     rax, [rax+10h]
0x180166136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016613b  nop
0x18016613c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180166143  mov     ecx, 20h ; ' '; unsigned __int64
0x180166148  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18016614d  mov     rbx, rax
0x180166150  test    rax, rax
0x180166153  jz      loc_180166618
0x180166159  xorps   xmm0, xmm0
0x18016615c  movups  xmmword ptr [rax], xmm0
0x18016615f  movups  xmmword ptr [rax+10h], xmm0
0x180166163  mov     dword ptr [rax+0Ch], 1
0x18016616a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UILockBytes@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILockBytes>::`vftable'
0x180166171  mov     [rbx], rax
0x180166174  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18016617b  test    rcx, rcx
0x18016617e  jz      short loc_18016618D
0x180166180  mov     rax, [rcx]
0x180166183  mov     rax, [rax+8]
0x180166187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016618c  nop
0x18016618d  lea     rax, ??_7CFileLockBytes@@6B@; const CFileLockBytes::`vftable'
0x180166194  mov     [rbx], rax
0x180166197  lea     rax, [rbx+10h]
0x18016619b  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1801661a2  mov     qword ptr [rbx+18h], 0
0x1801661aa  lea     rcx, [rbp+hObject]
0x1801661ae  cmp     rax, rcx
0x1801661b1  jz      short loc_1801661C1
0x1801661b3  mov     [rax], rdi
0x1801661b6  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1801661bd  mov     [rbp+hObject], rdi
0x1801661c1  mov     [rbp+plkbyt], rbx
0x1801661c5  mov     rax, [rbx]
0x1801661c8  mov     rcx, rbx
0x1801661cb  mov     rax, [rax+8]
0x1801661cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801661d4  nop
0x1801661d5  mov     rcx, rbx
0x1801661d8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UILockBytes@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ILockBytes>::Release(void)
0x1801661dd  nop
0x1801661de  mov     rcx, [r15]
0x1801661e1  test    rcx, rcx
0x1801661e4  jz      short loc_1801661FA
0x1801661e6  mov     qword ptr [r15], 0
0x1801661ed  mov     rax, [rcx]
0x1801661f0  mov     rax, [rax+10h]
0x1801661f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801661f9  nop
0x1801661fa  mov     eax, 400022h
0x1801661ff  mov     r8d, 400040h
0x180166205  cmp     dword ptr [r14+0A4h], 0
0x18016620d  cmovnz  r8d, eax; grfMode
0x180166211  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r15; ppstgOpen
0x180166216  mov     [rsp+68h+dwCreationDisposition], 0; int
0x18016621e  xor     r9d, r9d; snbExclude
0x180166221  xor     edx, edx; pstgPriority
0x180166223  mov     rcx, [rbp+plkbyt]; plkbyt
0x180166227  call    cs:__imp_StgOpenStorageOnILockBytes
0x18016622e  nop     dword ptr [rax+rax+00h]
0x180166233  mov     ebx, eax
0x180166235  cmp     eax, 80030109h
0x18016623a  jz      short loc_180166247
0x18016623c  cmp     eax, 80030050h
0x180166241  jnz     loc_180166491
0x180166247  cmp     dword ptr [r14+0A4h], 1
0x18016624f  jnz     loc_180166491
0x180166255  mov     rcx, [rbp+plkbyt]
0x180166259  test    rcx, rcx
0x18016625c  jz      short loc_180166273
0x18016625e  mov     [rbp+plkbyt], 0
  ... truncated ...
```
