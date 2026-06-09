# CSdBackupImpl::_EnsureAutoRunIcon(ushort const *,CBsString *)

- ea: `0x18001a0bc`
- end: `0x18001a36e`
- name: `?_EnsureAutoRunIcon@CSdBackupImpl@@AEAAJPEBGPEAVCBsString@@@Z`
- size: `690`
- prototype: `int(CSdBackupImpl *__hidden this, const unsigned __int16 *, struct CBsString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180021400`

## callees

- `0x18001a0bc`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009a24c`
- `0x18009a378`
- `0x18009ae34`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001a281`
- `KERNEL32!CreateFileW` at `0x18001a281`
- `KERNEL32!GetLastError` at `0x18001a295`
- `KERNEL32!GetLastError` at `0x18001a295`
- `KERNEL32!CloseHandle` at `0x18001a349`
- `KERNEL32!CloseHandle` at `0x18001a349`
- `KERNEL32!FindResourceW` at `0x18001a15b`
- `KERNEL32!FindResourceW` at `0x18001a15b`
- `KERNEL32!LoadResource` at `0x18001a191`
- `KERNEL32!LoadResource` at `0x18001a191`
- `KERNEL32!LockResource` at `0x18001a1c0`
- `KERNEL32!LockResource` at `0x18001a1c0`
- `KERNEL32!SizeofResource` at `0x18001a1f9`
- `KERNEL32!SizeofResource` at `0x18001a1f9`
- `KERNEL32!WriteFile` at `0x18001a2e3`
- `KERNEL32!WriteFile` at `0x18001a2e3`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_EnsureAutoRunIcon(
        CSdBackupImpl *this,
        const unsigned __int16 *a2,
        struct CBsString *a3)
{
  __int64 FileW; // rbx
  __int16 v6; // ax
  signed int LastFailureAsHRESULT; // edi
  __int64 v8; // rcx
  HRSRC ResourceW; // rdi
  HGLOBAL Resource; // rcx
  __int64 v11; // rcx
  const void *v12; // r15
  __int64 v13; // rcx
  DWORD v14; // r12d
  signed int LastError; // eax
  __int64 v16; // rcx
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-69h]
  const unsigned __int16 *v19; // [rsp+38h] [rbp-61h]
  const unsigned __int16 *v20; // [rsp+40h] [rbp-59h]
  const unsigned __int16 *v21; // [rsp+48h] [rbp-51h]
  const unsigned __int16 *v22; // [rsp+50h] [rbp-49h]
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-39h] BYREF
  int v24; // [rsp+70h] [rbp-29h] BYREF
  __int16 v25; // [rsp+74h] [rbp-25h]
  __int16 v26; // [rsp+76h] [rbp-23h]
  CSdBackupImpl *NumberOfBytesWritten; // [rsp+100h] [rbp+67h] BYREF

  NumberOfBytesWritten = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v24, "CSdBackupImpl::_EnsureAutoRunIcon", 4298, 1);
  FileW = -1;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  LODWORD(NumberOfBytesWritten) = 0;
  v6 = 4308;
  if ( !a2 || (v25 = 4308, v6 = 4309, !a3) )
  {
    LastFailureAsHRESULT = -2147024809;
    v24 = -2147024809;
LABEL_3:
    v26 = v6;
    goto LABEL_25;
  }
  v24 = 0;
  v25 = 4309;
  ResourceW = FindResourceW(hInstance, L"IDI_RESTOREICON", L"ICONBINARY");
  if ( !ResourceW )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v24 = LastFailureAsHRESULT;
    v6 = 4316;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 4316;
  Resource = LoadResource(hInstance, ResourceW);
  if ( !Resource )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(0);
    v24 = LastFailureAsHRESULT;
    v6 = 4319;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 4319;
  v12 = LockResource(Resource);
  if ( !v12 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
    v24 = LastFailureAsHRESULT;
    v6 = 4322;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 4322;
  v14 = SizeofResource(hInstance, ResourceW);
  if ( !v14 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
    v24 = LastFailureAsHRESULT;
    v6 = 4325;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 4325;
  LastFailureAsHRESULT = CBsString::SetPath(
                           (CBsString *)lpFileName,
                           a2,
                           L"restore.ico",
                           0,
                           0,
                           0,
                           hTemplateFile,
                           v19,
                           v20,
                           v21,
                           v22);
  v24 = LastFailureAsHRESULT;
  v6 = 4327;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v25 = 4327;
  FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 0, 0, 1u, 0x80u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    LastFailureAsHRESULT = LastError;
    if ( LastError == 80 )
    {
      v24 = 0;
      v6 = 4343;
      LastFailureAsHRESULT = 0;
      goto LABEL_24;
    }
    if ( LastError > 0 )
      LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
    v24 = LastFailureAsHRESULT;
    v6 = 4345;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v25 = 4345;
  }
  if ( !WriteFile((HANDLE)FileW, v12, v14, (LPDWORD)&NumberOfBytesWritten, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v16);
    v24 = LastFailureAsHRESULT;
    v6 = 4352;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 4352;
  LastFailureAsHRESULT = CBsString::Set(a3, L"restore.ico");
  v24 = LastFailureAsHRESULT;
  v6 = 4358;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
LABEL_24:
  v25 = v6;
LABEL_25:
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v24);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001a0bc  mov     [rsp-8+NumberOfBytesWritten], rcx
0x18001a0c1  push    rbp
0x18001a0c2  push    rbx
0x18001a0c3  push    rsi
0x18001a0c4  push    rdi
0x18001a0c5  push    r12
0x18001a0c7  push    r13
0x18001a0c9  push    r14
0x18001a0cb  push    r15
0x18001a0cd  lea     rbp, [rsp-1Fh]
0x18001a0d2  sub     rsp, 0B8h
0x18001a0d9  mov     rsi, r8
0x18001a0dc  mov     r14, rdx
0x18001a0df  mov     r9d, 1; unsigned __int16
0x18001a0e5  mov     r8d, 10CAh; unsigned __int16
0x18001a0eb  lea     rdx, aCsdbackupimplE_0; "CSdBackupImpl::_EnsureAutoRunIcon"
0x18001a0f2  lea     rcx, [rbp+57h+var_80]; this
0x18001a0f6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001a0fb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001a0ff  lea     rax, qword_1800E8530
0x18001a106  mov     [rbp+57h+lpFileName], rax
0x18001a10a  xor     r13d, r13d
0x18001a10d  mov     [rbp+57h+var_88], r13
0x18001a111  mov     dword ptr [rbp+57h+NumberOfBytesWritten], r13d
0x18001a115  mov     eax, 10D4h
0x18001a11a  test    r14, r14
0x18001a11d  jnz     short loc_18001A130
0x18001a11f  mov     edi, 80070057h
0x18001a124  mov     [rbp+57h+var_80], edi
0x18001a127  mov     [rbp+57h+var_7A], ax
0x18001a12b  jmp     loc_18001A333
0x18001a130  mov     [rbp+57h+var_7C], ax
0x18001a134  mov     eax, 10D5h
0x18001a139  test    rsi, rsi
0x18001a13c  jz      short loc_18001A11F
0x18001a13e  mov     [rbp+57h+var_80], r13d
0x18001a142  mov     [rbp+57h+var_7C], ax
0x18001a146  lea     r8, Type; "ICONBINARY"
0x18001a14d  lea     rdx, Name; "IDI_RESTOREICON"
0x18001a154  mov     rcx, cs:hInstance; hModule
0x18001a15b  call    cs:__imp_FindResourceW
0x18001a161  mov     rdi, rax
0x18001a164  test    rax, rax
0x18001a167  jnz     short loc_18001A17A
0x18001a169  call    GetLastFailureAsHRESULT
0x18001a16e  mov     edi, eax
0x18001a170  mov     [rbp+57h+var_80], eax
0x18001a173  mov     eax, 10DCh
0x18001a178  jmp     short loc_18001A127
0x18001a17a  mov     [rbp+57h+var_80], r13d
0x18001a17e  mov     eax, 10DCh
0x18001a183  mov     [rbp+57h+var_7C], ax
0x18001a187  mov     rdx, rdi; hResInfo
0x18001a18a  mov     rcx, cs:hInstance; hModule
0x18001a191  call    cs:__imp_LoadResource
0x18001a197  mov     rcx, rax; hResData
0x18001a19a  test    rax, rax
0x18001a19d  jnz     short loc_18001A1B3
0x18001a19f  call    GetLastFailureAsHRESULT
0x18001a1a4  mov     edi, eax
0x18001a1a6  mov     [rbp+57h+var_80], eax
0x18001a1a9  mov     eax, 10DFh
0x18001a1ae  jmp     loc_18001A127
0x18001a1b3  mov     [rbp+57h+var_80], r13d
0x18001a1b7  mov     eax, 10DFh
0x18001a1bc  mov     [rbp+57h+var_7C], ax
0x18001a1c0  call    cs:__imp_LockResource
0x18001a1c6  mov     r15, rax
0x18001a1c9  test    rax, rax
0x18001a1cc  jnz     short loc_18001A1E2
0x18001a1ce  call    GetLastFailureAsHRESULT
0x18001a1d3  mov     edi, eax
0x18001a1d5  mov     [rbp+57h+var_80], eax
0x18001a1d8  mov     eax, 10E2h
0x18001a1dd  jmp     loc_18001A127
0x18001a1e2  mov     [rbp+57h+var_80], r13d
0x18001a1e6  mov     eax, 10E2h
0x18001a1eb  mov     [rbp+57h+var_7C], ax
0x18001a1ef  mov     rdx, rdi; hResInfo
0x18001a1f2  mov     rcx, cs:hInstance; hModule
0x18001a1f9  call    cs:__imp_SizeofResource
0x18001a1ff  mov     r12d, eax
0x18001a202  test    eax, eax
0x18001a204  jnz     short loc_18001A21A
0x18001a206  call    GetLastFailureAsHRESULT
0x18001a20b  mov     edi, eax
0x18001a20d  mov     [rbp+57h+var_80], eax
0x18001a210  mov     eax, 10E5h
0x18001a215  jmp     loc_18001A127
0x18001a21a  mov     [rbp+57h+var_80], r13d
0x18001a21e  mov     eax, 10E5h
0x18001a223  mov     [rbp+57h+var_7C], ax
0x18001a227  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x18001a22c  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r13; unsigned __int16 *
0x18001a231  xor     r9d, r9d; unsigned __int16 *
0x18001a234  lea     r8, aRestoreIco; "restore.ico"
0x18001a23b  mov     rdx, r14; unsigned __int16 *
0x18001a23e  lea     rcx, [rbp+57h+lpFileName]; this
0x18001a242  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001a247  mov     edi, eax
0x18001a249  mov     [rbp+57h+var_80], eax
0x18001a24c  test    eax, eax
0x18001a24e  mov     eax, 10E7h
0x18001a253  js      loc_18001A127
0x18001a259  mov     [rbp+57h+var_7C], ax
0x18001a25d  mov     [rsp+0F0h+hTemplateFile], r13; hTemplateFile
0x18001a262  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001a26a  mov     [rsp+0F0h+dwCreationDisposition], 1; dwCreationDisposition
0x18001a272  xor     r9d, r9d; lpSecurityAttributes
0x18001a275  xor     r8d, r8d; dwShareMode
0x18001a278  mov     edx, 0C0000000h; dwDesiredAccess
0x18001a27d  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18001a281  call    cs:__imp_CreateFileW
0x18001a287  mov     rbx, rax
0x18001a28a  inc     rax
0x18001a28d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001a293  jnz     short loc_18001A2D1
0x18001a295  call    cs:__imp_GetLastError
0x18001a29b  mov     edi, eax
0x18001a29d  cmp     eax, 50h ; 'P'
0x18001a2a0  jnz     short loc_18001A2B0
0x18001a2a2  mov     [rbp+57h+var_80], r13d
0x18001a2a6  mov     eax, 10F7h
0x18001a2ab  mov     edi, r13d
0x18001a2ae  jmp     short loc_18001A32F
0x18001a2b0  test    eax, eax
0x18001a2b2  jle     short loc_18001A2BD
0x18001a2b4  movzx   edi, ax
0x18001a2b7  or      edi, 80070000h
0x18001a2bd  mov     [rbp+57h+var_80], edi
0x18001a2c0  mov     eax, 10F9h
0x18001a2c5  test    edi, edi
0x18001a2c7  js      loc_18001A127
0x18001a2cd  mov     [rbp+57h+var_7C], ax
0x18001a2d1  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r13; lpOverlapped
0x18001a2d6  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001a2da  mov     r8d, r12d; nNumberOfBytesToWrite
0x18001a2dd  mov     rdx, r15; lpBuffer
0x18001a2e0  mov     rcx, rbx; hFile
0x18001a2e3  call    cs:__imp_WriteFile
0x18001a2e9  test    eax, eax
0x18001a2eb  jnz     short loc_18001A301
0x18001a2ed  call    GetLastFailureAsHRESULT
0x18001a2f2  mov     edi, eax
0x18001a2f4  mov     [rbp+57h+var_80], eax
0x18001a2f7  mov     eax, 1100h
0x18001a2fc  jmp     loc_18001A127
0x18001a301  mov     [rbp+57h+var_80], r13d
0x18001a305  mov     eax, 1100h
0x18001a30a  mov     [rbp+57h+var_7C], ax
0x18001a30e  lea     rdx, aRestoreIco; "restore.ico"
0x18001a315  mov     rcx, rsi; this
0x18001a318  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001a31d  mov     edi, eax
0x18001a31f  mov     [rbp+57h+var_80], eax
0x18001a322  test    eax, eax
0x18001a324  mov     eax, 1106h
0x18001a329  js      loc_18001A127
0x18001a32f  mov     [rbp+57h+var_7C], ax
0x18001a333  lea     rcx, [rbp+57h+lpFileName]; this
0x18001a337  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001a33c  lea     rdx, [rbx-1]
0x18001a340  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001a344  ja      short loc_18001A34F
0x18001a346  mov     rcx, rbx; hObject
0x18001a349  call    cs:__imp_CloseHandle
0x18001a34f  lea     rcx, [rbp+57h+var_80]; this
0x18001a353  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001a358  mov     eax, edi
0x18001a35a  add     rsp, 0B8h
0x18001a361  pop     r15
0x18001a363  pop     r14
0x18001a365  pop     r13
0x18001a367  pop     r12
0x18001a369  pop     rdi
0x18001a36a  pop     rsi
0x18001a36b  pop     rbx
0x18001a36c  pop     rbp
0x18001a36d  retn
```
