# CSdRestoreImpl::_RestoreDirectoryTempAttribute(ushort const *)

- ea: `0x18002e68c`
- end: `0x18002e8c2`
- name: `?_RestoreDirectoryTempAttribute@CSdRestoreImpl@@AEAAJPEBG@Z`
- size: `566`
- prototype: `int(CSdRestoreImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18002dbbc`

## callees

- `0x18002e68c`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18008f660`
- `0x18009a20c`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18002e84b`
- `ntdll!NtSetInformationFile` at `0x18002e84b`
- `KERNEL32!CreateFileW` at `0x18002e7f0`
- `KERNEL32!CreateFileW` at `0x18002e7f0`
- `KERNEL32!CloseHandle` at `0x18002e873`
- `KERNEL32!CloseHandle` at `0x18002e898`
- `KERNEL32!CloseHandle` at `0x18002e873`
- `KERNEL32!CloseHandle` at `0x18002e898`
- `ole32!StringFromGUID2` at `0x18002e774`
- `ole32!StringFromGUID2` at `0x18002e774`
- `ole32!CoCreateGuid` at `0x18002e74c`
- `ole32!CoCreateGuid` at `0x18002e74c`

## string_xrefs

- `0x18002e6ba`: `CSdRestoreImpl::_RestoreDirectoryTempAttribute`

## pseudocode

```c
__int64 __fastcall CSdRestoreImpl::_RestoreDirectoryTempAttribute(CSdRestoreImpl *this, const unsigned __int16 *a2)
{
  __int64 FileW; // rbx
  HRESULT LastFailureAsHRESULT; // edi
  __int16 v5; // ax
  bool v6; // zf
  __int64 v7; // rcx
  unsigned int v8; // eax
  HRESULT v10; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v11; // [rsp+44h] [rbp-BCh]
  __int16 v12; // [rsp+46h] [rbp-BAh]
  LPCWSTR lpFileName[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-78h] BYREF
  GUID pguid; // [rsp+98h] [rbp-68h] BYREF
  int FileInformation; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v17; // [rsp+ACh] [rbp-54h]
  __int128 v18; // [rsp+BCh] [rbp-44h]
  int v19; // [rsp+CCh] [rbp-34h]
  OLECHAR sz; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v21[78]; // [rsp+D2h] [rbp-2Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v10,
    "CSdRestoreImpl::_RestoreDirectoryTempAttribute",
    4636,
    1);
  pguid = 0;
  sz = 0;
  memset_0(v21, 0, sizeof(v21));
  FileW = -1;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v5 = 4644;
LABEL_3:
    v10 = LastFailureAsHRESULT;
LABEL_4:
    v12 = v5;
    goto LABEL_13;
  }
  v10 = 0;
  v11 = 4644;
  LastFailureAsHRESULT = CoCreateGuid(&pguid);
  v10 = LastFailureAsHRESULT;
  v5 = 4647;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_4;
  v11 = 4647;
  v6 = StringFromGUID2(&pguid, &sz, 40) == 0;
  v5 = 4650;
  if ( v6 )
  {
    LastFailureAsHRESULT = -2130706378;
    goto LABEL_3;
  }
  v10 = 0;
  v11 = 4650;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)lpFileName, a2, L":", &sz);
  v10 = LastFailureAsHRESULT;
  v5 = 4651;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_4;
  v11 = 4651;
  FileW = (__int64)CreateFileW(lpFileName[0], 0xC0010000, 0, 0, 1u, 0x4000000u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v10 = LastFailureAsHRESULT;
    v5 = 4655;
    goto LABEL_4;
  }
  v10 = 0;
  v11 = 4655;
  HIDWORD(v18) = 256;
  v8 = NtSetInformationFile((HANDLE)FileW, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v8);
  v10 = LastFailureAsHRESULT;
  v5 = 4659;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_4;
  v11 = 4659;
  CloseHandle((HANDLE)FileW);
  FileW = -1;
  LastFailureAsHRESULT = v10;
LABEL_13:
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002e68c  push    rbp
0x18002e68e  push    rbx
0x18002e68f  push    rsi
0x18002e690  push    rdi
0x18002e691  lea     rbp, [rsp-38h]
0x18002e696  sub     rsp, 138h
0x18002e69d  mov     rax, cs:__security_cookie
0x18002e6a4  xor     rax, rsp
0x18002e6a7  mov     [rbp+50h+var_30], rax
0x18002e6ab  mov     rsi, rdx
0x18002e6ae  mov     r9d, 1; unsigned __int16
0x18002e6b4  mov     r8d, 121Ch; unsigned __int16
0x18002e6ba  lea     rdx, aCsdrestoreimpl_23; "CSdRestoreImpl::_RestoreDirectoryTempAt"...
0x18002e6c1  lea     rcx, [rsp+150h+var_110]; this
0x18002e6c6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002e6cb  xorps   xmm0, xmm0
0x18002e6ce  movups  xmmword ptr [rbp+50h+pguid.Data1], xmm0
0x18002e6d2  xor     eax, eax
0x18002e6d4  mov     [rbp+50h+sz], ax
0x18002e6d8  xor     edx, edx; Val
0x18002e6da  lea     r8d, [rax+4Eh]; Size
0x18002e6de  lea     rcx, [rbp+50h+var_7E]; void *
0x18002e6e2  call    memset_0
0x18002e6e7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e6eb  lea     rax, qword_1800E8530
0x18002e6f2  mov     [rsp+150h+lpFileName], rax
0x18002e6f7  mov     [rbp+50h+var_D0], 0
0x18002e6ff  xorps   xmm0, xmm0
0x18002e702  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x18002e706  mov     [rbp+50h+FileInformation], 0
0x18002e70d  xorps   xmm1, xmm1
0x18002e710  xor     eax, eax
0x18002e712  movups  [rbp+50h+var_A4], xmm1
0x18002e716  movups  [rbp+50h+var_94], xmm1
0x18002e71a  mov     [rbp+50h+var_84], eax
0x18002e71d  test    rsi, rsi
0x18002e720  jnz     short loc_18002E73A
0x18002e722  mov     edi, 80070057h
0x18002e727  mov     eax, 1224h
0x18002e72c  mov     [rsp+150h+var_110], edi
0x18002e730  mov     [rsp+150h+var_10A], ax
0x18002e735  jmp     loc_18002E881
0x18002e73a  mov     [rsp+150h+var_110], eax
0x18002e73e  mov     eax, 1224h
0x18002e743  mov     [rsp+150h+var_10C], ax
0x18002e748  lea     rcx, [rbp+50h+pguid]; pguid
0x18002e74c  call    cs:__imp_CoCreateGuid
0x18002e752  mov     edi, eax
0x18002e754  mov     [rsp+150h+var_110], eax
0x18002e758  test    eax, eax
0x18002e75a  mov     eax, 1227h
0x18002e75f  js      short loc_18002E730
0x18002e761  mov     [rsp+150h+var_10C], ax
0x18002e766  mov     r8d, 28h ; '('; cchMax
0x18002e76c  lea     rdx, [rbp+50h+sz]; lpsz
0x18002e770  lea     rcx, [rbp+50h+pguid]; rguid
0x18002e774  call    cs:__imp_StringFromGUID2
0x18002e77a  test    eax, eax
0x18002e77c  mov     eax, 122Ah
0x18002e781  jnz     short loc_18002E78A
0x18002e783  mov     edi, 81000036h
0x18002e788  jmp     short loc_18002E72C
0x18002e78a  mov     [rsp+150h+var_110], 0
0x18002e792  mov     [rsp+150h+var_10C], ax
0x18002e797  lea     r9, [rbp+50h+sz]; unsigned __int16 *
0x18002e79b  lea     r8, asc_1800DC494; ":"
0x18002e7a2  mov     rdx, rsi; unsigned __int16 *
0x18002e7a5  lea     rcx, [rsp+150h+lpFileName]; this
0x18002e7aa  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x18002e7af  mov     edi, eax
0x18002e7b1  mov     [rsp+150h+var_110], eax
0x18002e7b5  test    eax, eax
0x18002e7b7  mov     eax, 122Bh
0x18002e7bc  js      loc_18002E730
0x18002e7c2  mov     [rsp+150h+var_10C], ax
0x18002e7c7  mov     [rsp+150h+hTemplateFile], 0; hTemplateFile
0x18002e7d0  mov     [rsp+150h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x18002e7d8  mov     [rsp+150h+dwCreationDisposition], 1; dwCreationDisposition
0x18002e7e0  xor     r9d, r9d; lpSecurityAttributes
0x18002e7e3  xor     r8d, r8d; dwShareMode
0x18002e7e6  mov     edx, 0C0010000h; dwDesiredAccess
0x18002e7eb  mov     rcx, [rsp+150h+lpFileName]; lpFileName
0x18002e7f0  call    cs:__imp_CreateFileW
0x18002e7f6  mov     rbx, rax
0x18002e7f9  inc     rax
0x18002e7fc  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e802  jnz     short loc_18002E819
0x18002e804  call    GetLastFailureAsHRESULT
0x18002e809  mov     edi, eax
0x18002e80b  mov     [rsp+150h+var_110], eax
0x18002e80f  mov     eax, 122Fh
0x18002e814  jmp     loc_18002E730
0x18002e819  mov     [rsp+150h+var_110], 0
0x18002e821  mov     eax, 122Fh
0x18002e826  mov     [rsp+150h+var_10C], ax
0x18002e82b  mov     dword ptr [rbp+50h+var_94+0Ch], 100h
0x18002e832  mov     [rsp+150h+dwCreationDisposition], 4; FileInformationClass
0x18002e83a  mov     r9d, 28h ; '('; Length
0x18002e840  lea     r8, [rbp+50h+FileInformation]; FileInformation
0x18002e844  lea     rdx, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x18002e848  mov     rcx, rbx; FileHandle
0x18002e84b  call    cs:__imp_NtSetInformationFile
0x18002e851  mov     ecx, eax
0x18002e853  call    HRESULTFromNTSTATUS
0x18002e858  mov     edi, eax
0x18002e85a  mov     [rsp+150h+var_110], eax
0x18002e85e  test    eax, eax
0x18002e860  mov     eax, 1233h
0x18002e865  js      loc_18002E730
0x18002e86b  mov     [rsp+150h+var_10C], ax
0x18002e870  mov     rcx, rbx; hObject
0x18002e873  call    cs:__imp_CloseHandle
0x18002e879  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e87d  mov     edi, [rsp+150h+var_110]
0x18002e881  lea     rcx, [rsp+150h+lpFileName]; this
0x18002e886  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002e88b  lea     rcx, [rbx-1]
0x18002e88f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002e893  ja      short loc_18002E89E
0x18002e895  mov     rcx, rbx; hObject
0x18002e898  call    cs:__imp_CloseHandle
0x18002e89e  lea     rcx, [rsp+150h+var_110]; this
0x18002e8a3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002e8a8  mov     eax, edi
0x18002e8aa  mov     rcx, [rbp+50h+var_30]
0x18002e8ae  xor     rcx, rsp; StackCookie
0x18002e8b1  call    __security_check_cookie
0x18002e8b6  add     rsp, 138h
0x18002e8bd  pop     rdi
0x18002e8be  pop     rsi
0x18002e8bf  pop     rbx
0x18002e8c0  pop     rbp
0x18002e8c1  retn
```
