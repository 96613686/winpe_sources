# CSdCatalog::_OpenLockFile(ulong)

- ea: `0x1800b512c`
- end: `0x1800b5445`
- name: `?_OpenLockFile@CSdCatalog@@AEAAJK@Z`
- size: `793`
- prototype: `int(CSdCatalog *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800b1410`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x180086220`
- `0x18008ed84`
- `0x18008f5d0`
- `0x18009a378`
- `0x18009ae34`
- `0x1800b4980`
- `0x1800b512c`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x1800b5260`
- `KERNEL32!GetSystemDirectoryW` at `0x1800b5260`
- `KERNEL32!LocalFree` at `0x1800b53fb`
- `KERNEL32!LocalFree` at `0x1800b53fb`
- `KERNEL32!CreateFileW` at `0x1800b5390`
- `KERNEL32!CreateFileW` at `0x1800b5390`
- `KERNEL32!GetLastError` at `0x1800b53c3`
- `KERNEL32!GetLastError` at `0x1800b53c3`
- `KERNEL32!GetVolumePathNameW` at `0x1800b5299`
- `KERNEL32!GetVolumePathNameW` at `0x1800b5299`
- `KERNEL32!CloseHandle` at `0x1800b535a`
- `KERNEL32!CloseHandle` at `0x1800b53aa`
- `KERNEL32!CloseHandle` at `0x1800b535a`
- `KERNEL32!CloseHandle` at `0x1800b53aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b521c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b521c`

## string_xrefs

- `0x1800b5165`: `CSdCatalog::_OpenLockFile`

## pseudocode

```c
__int64 __fastcall CSdCatalog::_OpenLockFile(CSdCatalog *this, DWORD a2)
{
  CSdCatalog *v4; // rcx
  unsigned int v5; // r8d
  __int16 v6; // ax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  char *v10; // rcx
  HANDLE v11; // rdi
  char *v12; // rcx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v17; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v18; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v19; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v20; // [rsp+50h] [rbp-B0h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  int CatalogPath; // [rsp+68h] [rbp-98h] BYREF
  int v23; // [rsp+6Ch] [rbp-94h]
  ULONG SecurityDescriptorSize; // [rsp+A0h] [rbp-60h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR szVolumePathName; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v28[110]; // [rsp+D2h] [rbp-2Eh] BYREF
  WCHAR Buffer; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v30[526]; // [rsp+142h] [rbp+42h] BYREF
  unsigned __int16 v31; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v32[654]; // [rsp+352h] [rbp+252h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&CatalogPath, "CSdCatalog::_OpenLockFile", 1263, 1);
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  Buffer = 0;
  memset_0(v30, 0, 0x206u);
  v31 = 0;
  memset_0(v32, 0, 0x286u);
  szVolumePathName = 0;
  memset_0(v28, 0, 0x62u);
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  CatalogPath = CSdCatalog::_GetCatalogPath(v4, &v31, v5);
  v6 = 1273;
  if ( CatalogPath < 0 )
    goto LABEL_2;
  LOWORD(v23) = 1273;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
  {
    CatalogPath = GetLastFailureAsHRESULT(v7);
    v6 = 1278;
LABEL_2:
    HIWORD(v23) = v6;
    goto LABEL_20;
  }
  CatalogPath = 0;
  LOWORD(v23) = 1278;
  SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.nLength = 24;
  if ( !GetSystemDirectoryW(&Buffer, 0x104u) )
  {
    CatalogPath = GetLastFailureAsHRESULT(v8);
    v6 = 1286;
    goto LABEL_2;
  }
  CatalogPath = 0;
  LOWORD(v23) = 1286;
  if ( !GetVolumePathNameW(&Buffer, &szVolumePathName, 0x32u) )
  {
    CatalogPath = GetLastFailureAsHRESULT(v9);
    v6 = 1287;
    goto LABEL_2;
  }
  CatalogPath = 0;
  LOWORD(v23) = 1287;
  CatalogPath = SxCreateSVI(&szVolumePathName);
  v6 = 1288;
  if ( CatalogPath < 0 )
    goto LABEL_2;
  LOWORD(v23) = 1288;
  CatalogPath = EnsureDirectoryExists(&v31, &SecurityAttributes, 0, 0);
  v6 = 1293;
  if ( CatalogPath < 0 )
    goto LABEL_2;
  LOWORD(v23) = 1293;
  CatalogPath = CBsString::SetPath(
                  (CBsString *)lpFileName,
                  &v31,
                  L"GlobalCatalogLock.dat",
                  0,
                  0,
                  0,
                  hTemplateFile,
                  v17,
                  v18,
                  v19,
                  v20);
  v6 = 1298;
  if ( CatalogPath < 0 )
    goto LABEL_2;
  LOWORD(v23) = 1298;
  v10 = (char *)*((_QWORD *)this + 19);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v10);
    *((_QWORD *)this + 19) = -1;
  }
  v11 = CreateFileW(lpFileName[0], 0x80000000, a2, &SecurityAttributes, 4u, 0x80u, 0);
  v12 = (char *)*((_QWORD *)this + 19);
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v12);
  *((_QWORD *)this + 19) = v11;
  if ( (((unsigned __int64)v11 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( GetLastError() != 32 )
    {
      CatalogPath = GetLastFailureAsHRESULT(v13);
      v6 = 1317;
      goto LABEL_2;
    }
    v23 = 86377765;
    CatalogPath = -2130706185;
  }
LABEL_20:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
    SecurityAttributes.lpSecurityDescriptor = 0;
  }
  v14 = CatalogPath;
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&CatalogPath);
  return v14;
}

```

## disassembly

```asm
0x1800b512c  mov     [rsp-8+arg_10], rbx
0x1800b5131  push    rbp
0x1800b5132  push    rsi
0x1800b5133  push    rdi
0x1800b5134  lea     rbp, [rsp-4F0h]
0x1800b513c  sub     rsp, 5F0h
0x1800b5143  mov     rax, cs:__security_cookie
0x1800b514a  xor     rax, rsp
0x1800b514d  mov     [rbp+500h+var_20], rax
0x1800b5154  mov     edi, edx
0x1800b5156  mov     rbx, rcx
0x1800b5159  mov     r9d, 1; unsigned __int16
0x1800b515f  mov     r8d, 4EFh; unsigned __int16
0x1800b5165  lea     rdx, aCsdcatalogOpen_1; "CSdCatalog::_OpenLockFile"
0x1800b516c  lea     rcx, [rsp+600h+var_598]; this
0x1800b5171  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800b5176  lea     rax, qword_1800E8530
0x1800b517d  mov     [rbp+500h+lpFileName], rax
0x1800b5181  xor     esi, esi
0x1800b5183  mov     [rbp+500h+var_538], rsi
0x1800b5187  mov     [rbp+500h+Buffer], si
0x1800b518b  xor     edx, edx; Val
0x1800b518d  mov     r8d, 206h; Size
0x1800b5193  lea     rcx, [rbp+500h+var_4BE]; void *
0x1800b5197  call    memset_0
0x1800b519c  mov     [rbp+500h+var_2B0], si
0x1800b51a3  xor     edx, edx; Val
0x1800b51a5  mov     r8d, 286h; Size
0x1800b51ab  lea     rcx, [rbp+500h+var_2AE]; void *
0x1800b51b2  call    memset_0
0x1800b51b7  mov     [rbp+500h+szVolumePathName], si
0x1800b51bb  xor     edx, edx; Val
0x1800b51bd  lea     r8d, [rsi+62h]; Size
0x1800b51c1  lea     rcx, [rbp+500h+var_52E]; void *
0x1800b51c5  call    memset_0
0x1800b51ca  xorps   xmm0, xmm0
0x1800b51cd  xor     eax, eax
0x1800b51cf  movups  xmmword ptr [rbp+500h+SecurityAttributes.nLength], xmm0
0x1800b51d3  mov     qword ptr [rbp+500h+SecurityAttributes.bInheritHandle], rax
0x1800b51d7  mov     [rsp+600h+SecurityDescriptor], rsi
0x1800b51dc  mov     [rbp+500h+SecurityDescriptorSize], esi
0x1800b51df  lea     rdx, [rbp+500h+var_2B0]; unsigned __int16 *
0x1800b51e6  call    ?_GetCatalogPath@CSdCatalog@@AEAAJPEAGK@Z; CSdCatalog::_GetCatalogPath(ushort *,ulong)
0x1800b51eb  mov     [rsp+600h+var_598], eax
0x1800b51ef  test    eax, eax
0x1800b51f1  mov     eax, 4F9h
0x1800b51f6  jns     short loc_1800B5202
0x1800b51f8  mov     word ptr [rsp+600h+var_594+2], ax
0x1800b51fd  jmp     loc_1800B53F1
0x1800b5202  mov     word ptr [rsp+600h+var_594], ax
0x1800b5207  lea     r9, [rbp+500h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800b520b  lea     r8, [rsp+600h+SecurityDescriptor]; SecurityDescriptor
0x1800b5210  mov     edx, 1; StringSDRevision
0x1800b5215  lea     rcx, c_wszSVISubDirSecurity; "D:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)"
0x1800b521c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800b5222  test    eax, eax
0x1800b5224  jnz     short loc_1800B5236
0x1800b5226  call    GetLastFailureAsHRESULT
0x1800b522b  mov     [rsp+600h+var_598], eax
0x1800b522f  mov     eax, 4FEh
0x1800b5234  jmp     short loc_1800B51F8
0x1800b5236  mov     [rsp+600h+var_598], esi
0x1800b523a  mov     eax, 4FEh
0x1800b523f  mov     word ptr [rsp+600h+var_594], ax
0x1800b5244  mov     [rbp+500h+SecurityAttributes.bInheritHandle], esi
0x1800b5247  mov     rax, [rsp+600h+SecurityDescriptor]
0x1800b524c  mov     [rbp+500h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800b5250  mov     [rbp+500h+SecurityAttributes.nLength], 18h
0x1800b5257  mov     edx, 104h; uSize
0x1800b525c  lea     rcx, [rbp+500h+Buffer]; lpBuffer
0x1800b5260  call    cs:__imp_GetSystemDirectoryW
0x1800b5266  test    eax, eax
0x1800b5268  jnz     short loc_1800B527D
0x1800b526a  call    GetLastFailureAsHRESULT
0x1800b526f  mov     [rsp+600h+var_598], eax
0x1800b5273  mov     eax, 506h
0x1800b5278  jmp     loc_1800B51F8
0x1800b527d  mov     [rsp+600h+var_598], esi
0x1800b5281  mov     eax, 506h
0x1800b5286  mov     word ptr [rsp+600h+var_594], ax
0x1800b528b  mov     r8d, 32h ; '2'; cchBufferLength
0x1800b5291  lea     rdx, [rbp+500h+szVolumePathName]; lpszVolumePathName
0x1800b5295  lea     rcx, [rbp+500h+Buffer]; lpszFileName
0x1800b5299  call    cs:__imp_GetVolumePathNameW
0x1800b529f  test    eax, eax
0x1800b52a1  jnz     short loc_1800B52B6
0x1800b52a3  call    GetLastFailureAsHRESULT
0x1800b52a8  mov     [rsp+600h+var_598], eax
0x1800b52ac  mov     eax, 507h
0x1800b52b1  jmp     loc_1800B51F8
0x1800b52b6  mov     [rsp+600h+var_598], esi
0x1800b52ba  mov     eax, 507h
0x1800b52bf  mov     word ptr [rsp+600h+var_594], ax
0x1800b52c4  lea     rcx, [rbp+500h+szVolumePathName]; unsigned __int16 *
0x1800b52c8  call    ?SxCreateSVI@@YAJPEBG@Z; SxCreateSVI(ushort const *)
0x1800b52cd  mov     [rsp+600h+var_598], eax
0x1800b52d1  test    eax, eax
0x1800b52d3  mov     eax, 508h
0x1800b52d8  js      loc_1800B51F8
0x1800b52de  mov     word ptr [rsp+600h+var_594], ax
0x1800b52e3  xor     r9d, r9d; int
0x1800b52e6  xor     r8d, r8d; int
0x1800b52e9  lea     rdx, [rbp+500h+SecurityAttributes]; lpSecurityAttributes
0x1800b52ed  lea     rcx, [rbp+500h+var_2B0]; unsigned __int16 *
0x1800b52f4  call    ?EnsureDirectoryExists@@YAJPEBGPEBU_SECURITY_ATTRIBUTES@@HH@Z; EnsureDirectoryExists(ushort const *,_SECURITY_ATTRIBUTES const *,int,int)
0x1800b52f9  mov     [rsp+600h+var_598], eax
0x1800b52fd  test    eax, eax
0x1800b52ff  mov     eax, 50Dh
0x1800b5304  js      loc_1800B51F8
0x1800b530a  mov     word ptr [rsp+600h+var_594], ax
0x1800b530f  mov     qword ptr [rsp+600h+dwFlagsAndAttributes], rsi; unsigned __int16 *
0x1800b5314  mov     qword ptr [rsp+600h+dwCreationDisposition], rsi; unsigned __int16 *
0x1800b5319  xor     r9d, r9d; unsigned __int16 *
0x1800b531c  lea     r8, c_wszGCLockName; "GlobalCatalogLock.dat"
0x1800b5323  lea     rdx, [rbp+500h+var_2B0]; unsigned __int16 *
0x1800b532a  lea     rcx, [rbp+500h+lpFileName]; this
0x1800b532e  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800b5333  mov     [rsp+600h+var_598], eax
0x1800b5337  test    eax, eax
0x1800b5339  mov     eax, 512h
0x1800b533e  js      loc_1800B51F8
0x1800b5344  mov     word ptr [rsp+600h+var_594], ax
0x1800b5349  mov     rcx, [rbx+98h]; hObject
0x1800b5350  lea     rax, [rcx-1]
0x1800b5354  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b5358  ja      short loc_1800B536B
0x1800b535a  call    cs:__imp_CloseHandle
0x1800b5360  mov     qword ptr [rbx+98h], 0FFFFFFFFFFFFFFFFh
0x1800b536b  mov     [rsp+600h+hTemplateFile], rsi; hTemplateFile
0x1800b5370  mov     [rsp+600h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b5378  mov     [rsp+600h+dwCreationDisposition], 4; dwCreationDisposition
0x1800b5380  lea     r9, [rbp+500h+SecurityAttributes]; lpSecurityAttributes
0x1800b5384  mov     r8d, edi; dwShareMode
0x1800b5387  mov     edx, 80000000h; dwDesiredAccess
0x1800b538c  mov     rcx, [rbp+500h+lpFileName]; lpFileName
0x1800b5390  call    cs:__imp_CreateFileW
0x1800b5396  mov     rdi, rax
0x1800b5399  mov     rcx, [rbx+98h]; hObject
0x1800b53a0  lea     rdx, [rcx-1]
0x1800b53a4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800b53a8  ja      short loc_1800B53B0
0x1800b53aa  call    cs:__imp_CloseHandle
0x1800b53b0  mov     [rbx+98h], rdi
0x1800b53b7  lea     rax, [rdi+1]
0x1800b53bb  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b53c1  jnz     short loc_1800B53F1
0x1800b53c3  call    cs:__imp_GetLastError
0x1800b53c9  cmp     eax, 20h ; ' '
0x1800b53cc  jz      short loc_1800B53E1
0x1800b53ce  call    GetLastFailureAsHRESULT
0x1800b53d3  mov     [rsp+600h+var_598], eax
0x1800b53d7  mov     eax, 525h
0x1800b53dc  jmp     loc_1800B51F8
0x1800b53e1  mov     [rsp+600h+var_594], 5260525h
0x1800b53e9  mov     [rsp+600h+var_598], 810000F7h
0x1800b53f1  mov     rcx, [rsp+600h+SecurityDescriptor]; hMem
0x1800b53f6  test    rcx, rcx
0x1800b53f9  jz      short loc_1800B540A
0x1800b53fb  call    cs:__imp_LocalFree
0x1800b5401  mov     [rsp+600h+SecurityDescriptor], rsi
0x1800b5406  mov     [rbp+500h+SecurityAttributes.lpSecurityDescriptor], rsi
0x1800b540a  mov     ebx, [rsp+600h+var_598]
0x1800b540e  lea     rcx, [rbp+500h+lpFileName]; this
0x1800b5412  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800b5417  lea     rcx, [rsp+600h+var_598]; this
0x1800b541c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800b5421  mov     eax, ebx
0x1800b5423  mov     rcx, [rbp+500h+var_20]
0x1800b542a  xor     rcx, rsp; StackCookie
0x1800b542d  call    __security_check_cookie
0x1800b5432  mov     rbx, [rsp+600h+arg_10]
0x1800b543a  add     rsp, 5F0h
0x1800b5441  pop     rdi
0x1800b5442  pop     rsi
0x1800b5443  pop     rbp
0x1800b5444  retn
```
