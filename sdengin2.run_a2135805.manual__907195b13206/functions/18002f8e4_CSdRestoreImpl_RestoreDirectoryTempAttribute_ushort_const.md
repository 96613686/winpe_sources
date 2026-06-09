# CSdRestoreImpl::_RestoreDirectoryTempAttribute(ushort const *)

- ea: `0x18002f8e4`
- end: `0x18002fb3f`
- name: `?_RestoreDirectoryTempAttribute@CSdRestoreImpl@@AEAAJPEBG@Z`
- size: `603`
- prototype: `int(CSdRestoreImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18002ed94`

## callees

- `0x18002f8e4`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180093698`
- `0x18009e8c4`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18002fab5`
- `ntdll!NtSetInformationFile` at `0x18002fab5`
- `KERNEL32!CreateFileW` at `0x18002fa54`
- `KERNEL32!CreateFileW` at `0x18002fa54`
- `KERNEL32!CloseHandle` at `0x18002fae3`
- `KERNEL32!CloseHandle` at `0x18002fb0e`
- `KERNEL32!CloseHandle` at `0x18002fae3`
- `KERNEL32!CloseHandle` at `0x18002fb0e`
- `ole32!StringFromGUID2` at `0x18002f9d2`
- `ole32!StringFromGUID2` at `0x18002f9d2`
- `ole32!CoCreateGuid` at `0x18002f9a4`
- `ole32!CoCreateGuid` at `0x18002f9a4`

## string_xrefs

- `0x18002f912`: `CSdRestoreImpl::_RestoreDirectoryTempAttribute`

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
    0x121Cu,
    1u);
  pguid = 0;
  sz = 0;
  memset_0(v21, 0, sizeof(v21));
  FileW = -1;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
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
0x18002f8e4  push    rbp
0x18002f8e6  push    rbx
0x18002f8e7  push    rsi
0x18002f8e8  push    rdi
0x18002f8e9  lea     rbp, [rsp-38h]
0x18002f8ee  sub     rsp, 138h
0x18002f8f5  mov     rax, cs:__security_cookie
0x18002f8fc  xor     rax, rsp
0x18002f8ff  mov     [rbp+50h+var_30], rax
0x18002f903  mov     rsi, rdx
0x18002f906  mov     r9d, 1; unsigned __int16
0x18002f90c  mov     r8d, 121Ch; unsigned __int16
0x18002f912  lea     rdx, aCsdrestoreimpl_23; "CSdRestoreImpl::_RestoreDirectoryTempAt"...
0x18002f919  lea     rcx, [rsp+150h+var_110]; this
0x18002f91e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002f923  xorps   xmm0, xmm0
0x18002f926  movups  xmmword ptr [rbp+50h+pguid.Data1], xmm0
0x18002f92a  xor     eax, eax
0x18002f92c  mov     [rbp+50h+sz], ax
0x18002f930  xor     edx, edx; Val
0x18002f932  lea     r8d, [rax+4Eh]; Size
0x18002f936  lea     rcx, [rbp+50h+var_7E]; void *
0x18002f93a  call    memset_0
0x18002f93f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f943  lea     rax, qword_1800EE510
0x18002f94a  mov     [rsp+150h+lpFileName], rax
0x18002f94f  mov     [rbp+50h+var_D0], 0
0x18002f957  xorps   xmm0, xmm0
0x18002f95a  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x18002f95e  mov     [rbp+50h+FileInformation], 0
0x18002f965  xorps   xmm1, xmm1
0x18002f968  xor     eax, eax
0x18002f96a  movups  [rbp+50h+var_A4], xmm1
0x18002f96e  movups  [rbp+50h+var_94], xmm1
0x18002f972  mov     [rbp+50h+var_84], eax
0x18002f975  test    rsi, rsi
0x18002f978  jnz     short loc_18002F992
0x18002f97a  mov     edi, 80070057h
0x18002f97f  mov     eax, 1224h
0x18002f984  mov     [rsp+150h+var_110], edi
0x18002f988  mov     [rsp+150h+var_10A], ax
0x18002f98d  jmp     loc_18002FAF7
0x18002f992  mov     [rsp+150h+var_110], eax
0x18002f996  mov     eax, 1224h
0x18002f99b  mov     [rsp+150h+var_10C], ax
0x18002f9a0  lea     rcx, [rbp+50h+pguid]; pguid
0x18002f9a4  call    cs:__imp_CoCreateGuid
0x18002f9ab  nop     dword ptr [rax+rax+00h]
0x18002f9b0  mov     edi, eax
0x18002f9b2  mov     [rsp+150h+var_110], eax
0x18002f9b6  test    eax, eax
0x18002f9b8  mov     eax, 1227h
0x18002f9bd  js      short loc_18002F988
0x18002f9bf  mov     [rsp+150h+var_10C], ax
0x18002f9c4  mov     r8d, 28h ; '('; cchMax
0x18002f9ca  lea     rdx, [rbp+50h+sz]; lpsz
0x18002f9ce  lea     rcx, [rbp+50h+pguid]; rguid
0x18002f9d2  call    cs:__imp_StringFromGUID2
0x18002f9d9  nop     dword ptr [rax+rax+00h]
0x18002f9de  test    eax, eax
0x18002f9e0  mov     eax, 122Ah
0x18002f9e5  jnz     short loc_18002F9EE
0x18002f9e7  mov     edi, 81000036h
0x18002f9ec  jmp     short loc_18002F984
0x18002f9ee  mov     [rsp+150h+var_110], 0
0x18002f9f6  mov     [rsp+150h+var_10C], ax
0x18002f9fb  lea     r9, [rbp+50h+sz]; unsigned __int16 *
0x18002f9ff  lea     r8, asc_1800E2474; ":"
0x18002fa06  mov     rdx, rsi; unsigned __int16 *
0x18002fa09  lea     rcx, [rsp+150h+lpFileName]; this
0x18002fa0e  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x18002fa13  mov     edi, eax
0x18002fa15  mov     [rsp+150h+var_110], eax
0x18002fa19  test    eax, eax
0x18002fa1b  mov     eax, 122Bh
0x18002fa20  js      loc_18002F988
0x18002fa26  mov     [rsp+150h+var_10C], ax
0x18002fa2b  mov     [rsp+150h+hTemplateFile], 0; hTemplateFile
0x18002fa34  mov     [rsp+150h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x18002fa3c  mov     [rsp+150h+dwCreationDisposition], 1; dwCreationDisposition
0x18002fa44  xor     r9d, r9d; lpSecurityAttributes
0x18002fa47  xor     r8d, r8d; dwShareMode
0x18002fa4a  mov     edx, 0C0010000h; dwDesiredAccess
0x18002fa4f  mov     rcx, [rsp+150h+lpFileName]; lpFileName
0x18002fa54  call    cs:__imp_CreateFileW
0x18002fa5b  nop     dword ptr [rax+rax+00h]
0x18002fa60  mov     rbx, rax
0x18002fa63  inc     rax
0x18002fa66  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002fa6c  jnz     short loc_18002FA83
0x18002fa6e  call    GetLastFailureAsHRESULT
0x18002fa73  mov     edi, eax
0x18002fa75  mov     [rsp+150h+var_110], eax
0x18002fa79  mov     eax, 122Fh
0x18002fa7e  jmp     loc_18002F988
0x18002fa83  mov     [rsp+150h+var_110], 0
0x18002fa8b  mov     eax, 122Fh
0x18002fa90  mov     [rsp+150h+var_10C], ax
0x18002fa95  mov     dword ptr [rbp+50h+var_94+0Ch], 100h
0x18002fa9c  mov     [rsp+150h+dwCreationDisposition], 4; FileInformationClass
0x18002faa4  mov     r9d, 28h ; '('; Length
0x18002faaa  lea     r8, [rbp+50h+FileInformation]; FileInformation
0x18002faae  lea     rdx, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x18002fab2  mov     rcx, rbx; FileHandle
0x18002fab5  call    cs:__imp_NtSetInformationFile
0x18002fabc  nop     dword ptr [rax+rax+00h]
0x18002fac1  mov     ecx, eax
0x18002fac3  call    HRESULTFromNTSTATUS
0x18002fac8  mov     edi, eax
0x18002faca  mov     [rsp+150h+var_110], eax
0x18002face  test    eax, eax
0x18002fad0  mov     eax, 1233h
0x18002fad5  js      loc_18002F988
0x18002fadb  mov     [rsp+150h+var_10C], ax
0x18002fae0  mov     rcx, rbx; hObject
0x18002fae3  call    cs:__imp_CloseHandle
0x18002faea  nop     dword ptr [rax+rax+00h]
0x18002faef  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002faf3  mov     edi, [rsp+150h+var_110]
0x18002faf7  lea     rcx, [rsp+150h+lpFileName]; this
0x18002fafc  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002fb01  lea     rcx, [rbx-1]
0x18002fb05  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002fb09  ja      short loc_18002FB1A
0x18002fb0b  mov     rcx, rbx; hObject
0x18002fb0e  call    cs:__imp_CloseHandle
0x18002fb15  nop     dword ptr [rax+rax+00h]
0x18002fb1a  lea     rcx, [rsp+150h+var_110]; this
0x18002fb1f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002fb24  mov     eax, edi
0x18002fb26  mov     rcx, [rbp+50h+var_30]
0x18002fb2a  xor     rcx, rsp; StackCookie
0x18002fb2d  call    __security_check_cookie
0x18002fb32  add     rsp, 138h
0x18002fb39  pop     rdi
0x18002fb3a  pop     rsi
0x18002fb3b  pop     rbx
0x18002fb3c  pop     rbp
0x18002fb3d  retn
```
