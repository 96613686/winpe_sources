# CSdCatalog::_OpenLockFile(ulong)

- ea: `0x1800bab44`
- end: `0x1800bae8e`
- name: `?_OpenLockFile@CSdCatalog@@AEAAJK@Z`
- size: `842`
- prototype: `int(CSdCatalog *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800b6d80`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x180089b20`
- `0x180092d48`
- `0x1800935fc`
- `0x18009ea34`
- `0x18009f560`
- `0x1800ba378`
- `0x1800bab44`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x1800bac7e`
- `KERNEL32!GetSystemDirectoryW` at `0x1800bac7e`
- `KERNEL32!LocalFree` at `0x1800bae3d`
- `KERNEL32!LocalFree` at `0x1800bae3d`
- `KERNEL32!CreateFileW` at `0x1800badc0`
- `KERNEL32!CreateFileW` at `0x1800badc0`
- `KERNEL32!GetLastError` at `0x1800badff`
- `KERNEL32!GetLastError` at `0x1800badff`
- `KERNEL32!GetVolumePathNameW` at `0x1800bacbd`
- `KERNEL32!GetVolumePathNameW` at `0x1800bacbd`
- `KERNEL32!CloseHandle` at `0x1800bad84`
- `KERNEL32!CloseHandle` at `0x1800bade0`
- `KERNEL32!CloseHandle` at `0x1800bad84`
- `KERNEL32!CloseHandle` at `0x1800bade0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bac34`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bac34`

## string_xrefs

- `0x1800bab7d`: `CSdCatalog::_OpenLockFile`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&CatalogPath, "CSdCatalog::_OpenLockFile", 0x4EFu, 1u);
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
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
0x1800bab44  mov     [rsp-8+arg_10], rbx
0x1800bab49  push    rbp
0x1800bab4a  push    rsi
0x1800bab4b  push    rdi
0x1800bab4c  lea     rbp, [rsp-4F0h]
0x1800bab54  sub     rsp, 5F0h
0x1800bab5b  mov     rax, cs:__security_cookie
0x1800bab62  xor     rax, rsp
0x1800bab65  mov     [rbp+500h+var_20], rax
0x1800bab6c  mov     edi, edx
0x1800bab6e  mov     rbx, rcx
0x1800bab71  mov     r9d, 1; unsigned __int16
0x1800bab77  mov     r8d, 4EFh; unsigned __int16
0x1800bab7d  lea     rdx, aCsdcatalogOpen_1; "CSdCatalog::_OpenLockFile"
0x1800bab84  lea     rcx, [rsp+600h+var_598]; this
0x1800bab89  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800bab8e  lea     rax, qword_1800EE510
0x1800bab95  mov     [rbp+500h+lpFileName], rax
0x1800bab99  xor     esi, esi
0x1800bab9b  mov     [rbp+500h+var_538], rsi
0x1800bab9f  mov     [rbp+500h+Buffer], si
0x1800baba3  xor     edx, edx; Val
0x1800baba5  mov     r8d, 206h; Size
0x1800babab  lea     rcx, [rbp+500h+var_4BE]; void *
0x1800babaf  call    memset_0
0x1800babb4  mov     [rbp+500h+var_2B0], si
0x1800babbb  xor     edx, edx; Val
0x1800babbd  mov     r8d, 286h; Size
0x1800babc3  lea     rcx, [rbp+500h+var_2AE]; void *
0x1800babca  call    memset_0
0x1800babcf  mov     [rbp+500h+szVolumePathName], si
0x1800babd3  xor     edx, edx; Val
0x1800babd5  lea     r8d, [rsi+62h]; Size
0x1800babd9  lea     rcx, [rbp+500h+var_52E]; void *
0x1800babdd  call    memset_0
0x1800babe2  xorps   xmm0, xmm0
0x1800babe5  xor     eax, eax
0x1800babe7  movups  xmmword ptr [rbp+500h+SecurityAttributes.nLength], xmm0
0x1800babeb  mov     qword ptr [rbp+500h+SecurityAttributes.bInheritHandle], rax
0x1800babef  mov     [rsp+600h+SecurityDescriptor], rsi
0x1800babf4  mov     [rbp+500h+SecurityDescriptorSize], esi
0x1800babf7  lea     rdx, [rbp+500h+var_2B0]; unsigned __int16 *
0x1800babfe  call    ?_GetCatalogPath@CSdCatalog@@AEAAJPEAGK@Z; CSdCatalog::_GetCatalogPath(ushort *,ulong)
0x1800bac03  mov     [rsp+600h+var_598], eax
0x1800bac07  test    eax, eax
0x1800bac09  mov     eax, 4F9h
0x1800bac0e  jns     short loc_1800BAC1A
0x1800bac10  mov     word ptr [rsp+600h+var_594+2], ax
0x1800bac15  jmp     loc_1800BAE33
0x1800bac1a  mov     word ptr [rsp+600h+var_594], ax
0x1800bac1f  lea     r9, [rbp+500h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800bac23  lea     r8, [rsp+600h+SecurityDescriptor]; SecurityDescriptor
0x1800bac28  mov     edx, 1; StringSDRevision
0x1800bac2d  lea     rcx, c_wszSVISubDirSecurity; "D:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)"
0x1800bac34  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800bac3b  nop     dword ptr [rax+rax+00h]
0x1800bac40  test    eax, eax
0x1800bac42  jnz     short loc_1800BAC54
0x1800bac44  call    GetLastFailureAsHRESULT
0x1800bac49  mov     [rsp+600h+var_598], eax
0x1800bac4d  mov     eax, 4FEh
0x1800bac52  jmp     short loc_1800BAC10
0x1800bac54  mov     [rsp+600h+var_598], esi
0x1800bac58  mov     eax, 4FEh
0x1800bac5d  mov     word ptr [rsp+600h+var_594], ax
0x1800bac62  mov     [rbp+500h+SecurityAttributes.bInheritHandle], esi
0x1800bac65  mov     rax, [rsp+600h+SecurityDescriptor]
0x1800bac6a  mov     [rbp+500h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800bac6e  mov     [rbp+500h+SecurityAttributes.nLength], 18h
0x1800bac75  mov     edx, 104h; uSize
0x1800bac7a  lea     rcx, [rbp+500h+Buffer]; lpBuffer
0x1800bac7e  call    cs:__imp_GetSystemDirectoryW
0x1800bac85  nop     dword ptr [rax+rax+00h]
0x1800bac8a  test    eax, eax
0x1800bac8c  jnz     short loc_1800BACA1
0x1800bac8e  call    GetLastFailureAsHRESULT
0x1800bac93  mov     [rsp+600h+var_598], eax
0x1800bac97  mov     eax, 506h
0x1800bac9c  jmp     loc_1800BAC10
0x1800baca1  mov     [rsp+600h+var_598], esi
0x1800baca5  mov     eax, 506h
0x1800bacaa  mov     word ptr [rsp+600h+var_594], ax
0x1800bacaf  mov     r8d, 32h ; '2'; cchBufferLength
0x1800bacb5  lea     rdx, [rbp+500h+szVolumePathName]; lpszVolumePathName
0x1800bacb9  lea     rcx, [rbp+500h+Buffer]; lpszFileName
0x1800bacbd  call    cs:__imp_GetVolumePathNameW
0x1800bacc4  nop     dword ptr [rax+rax+00h]
0x1800bacc9  test    eax, eax
0x1800baccb  jnz     short loc_1800BACE0
0x1800baccd  call    GetLastFailureAsHRESULT
0x1800bacd2  mov     [rsp+600h+var_598], eax
0x1800bacd6  mov     eax, 507h
0x1800bacdb  jmp     loc_1800BAC10
0x1800bace0  mov     [rsp+600h+var_598], esi
0x1800bace4  mov     eax, 507h
0x1800bace9  mov     word ptr [rsp+600h+var_594], ax
0x1800bacee  lea     rcx, [rbp+500h+szVolumePathName]; unsigned __int16 *
0x1800bacf2  call    ?SxCreateSVI@@YAJPEBG@Z; SxCreateSVI(ushort const *)
0x1800bacf7  mov     [rsp+600h+var_598], eax
0x1800bacfb  test    eax, eax
0x1800bacfd  mov     eax, 508h
0x1800bad02  js      loc_1800BAC10
0x1800bad08  mov     word ptr [rsp+600h+var_594], ax
0x1800bad0d  xor     r9d, r9d; int
0x1800bad10  xor     r8d, r8d; int
0x1800bad13  lea     rdx, [rbp+500h+SecurityAttributes]; lpSecurityAttributes
0x1800bad17  lea     rcx, [rbp+500h+var_2B0]; unsigned __int16 *
0x1800bad1e  call    ?EnsureDirectoryExists@@YAJPEBGPEBU_SECURITY_ATTRIBUTES@@HH@Z; EnsureDirectoryExists(ushort const *,_SECURITY_ATTRIBUTES const *,int,int)
0x1800bad23  mov     [rsp+600h+var_598], eax
0x1800bad27  test    eax, eax
0x1800bad29  mov     eax, 50Dh
0x1800bad2e  js      loc_1800BAC10
0x1800bad34  mov     word ptr [rsp+600h+var_594], ax
0x1800bad39  mov     qword ptr [rsp+600h+dwFlagsAndAttributes], rsi; unsigned __int16 *
0x1800bad3e  mov     qword ptr [rsp+600h+dwCreationDisposition], rsi; unsigned __int16 *
0x1800bad43  xor     r9d, r9d; unsigned __int16 *
0x1800bad46  lea     r8, c_wszGCLockName; "GlobalCatalogLock.dat"
0x1800bad4d  lea     rdx, [rbp+500h+var_2B0]; unsigned __int16 *
0x1800bad54  lea     rcx, [rbp+500h+lpFileName]; this
0x1800bad58  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800bad5d  mov     [rsp+600h+var_598], eax
0x1800bad61  test    eax, eax
0x1800bad63  mov     eax, 512h
0x1800bad68  js      loc_1800BAC10
0x1800bad6e  mov     word ptr [rsp+600h+var_594], ax
0x1800bad73  mov     rcx, [rbx+98h]; hObject
0x1800bad7a  lea     rax, [rcx-1]
0x1800bad7e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800bad82  ja      short loc_1800BAD9B
0x1800bad84  call    cs:__imp_CloseHandle
0x1800bad8b  nop     dword ptr [rax+rax+00h]
0x1800bad90  mov     qword ptr [rbx+98h], 0FFFFFFFFFFFFFFFFh
0x1800bad9b  mov     [rsp+600h+hTemplateFile], rsi; hTemplateFile
0x1800bada0  mov     [rsp+600h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800bada8  mov     [rsp+600h+dwCreationDisposition], 4; dwCreationDisposition
0x1800badb0  lea     r9, [rbp+500h+SecurityAttributes]; lpSecurityAttributes
0x1800badb4  mov     r8d, edi; dwShareMode
0x1800badb7  mov     edx, 80000000h; dwDesiredAccess
0x1800badbc  mov     rcx, [rbp+500h+lpFileName]; lpFileName
0x1800badc0  call    cs:__imp_CreateFileW
0x1800badc7  nop     dword ptr [rax+rax+00h]
0x1800badcc  mov     rdi, rax
0x1800badcf  mov     rcx, [rbx+98h]; hObject
0x1800badd6  lea     rdx, [rcx-1]
0x1800badda  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800badde  ja      short loc_1800BADEC
0x1800bade0  call    cs:__imp_CloseHandle
0x1800bade7  nop     dword ptr [rax+rax+00h]
0x1800badec  mov     [rbx+98h], rdi
0x1800badf3  lea     rax, [rdi+1]
0x1800badf7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800badfd  jnz     short loc_1800BAE33
0x1800badff  call    cs:__imp_GetLastError
0x1800bae06  nop     dword ptr [rax+rax+00h]
0x1800bae0b  cmp     eax, 20h ; ' '
0x1800bae0e  jz      short loc_1800BAE23
0x1800bae10  call    GetLastFailureAsHRESULT
0x1800bae15  mov     [rsp+600h+var_598], eax
0x1800bae19  mov     eax, 525h
0x1800bae1e  jmp     loc_1800BAC10
0x1800bae23  mov     [rsp+600h+var_594], 5260525h
0x1800bae2b  mov     [rsp+600h+var_598], 810000F7h
0x1800bae33  mov     rcx, [rsp+600h+SecurityDescriptor]; hMem
0x1800bae38  test    rcx, rcx
0x1800bae3b  jz      short loc_1800BAE52
0x1800bae3d  call    cs:__imp_LocalFree
0x1800bae44  nop     dword ptr [rax+rax+00h]
0x1800bae49  mov     [rsp+600h+SecurityDescriptor], rsi
0x1800bae4e  mov     [rbp+500h+SecurityAttributes.lpSecurityDescriptor], rsi
0x1800bae52  mov     ebx, [rsp+600h+var_598]
0x1800bae56  lea     rcx, [rbp+500h+lpFileName]; this
0x1800bae5a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800bae5f  lea     rcx, [rsp+600h+var_598]; this
0x1800bae64  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800bae69  mov     eax, ebx
0x1800bae6b  mov     rcx, [rbp+500h+var_20]
0x1800bae72  xor     rcx, rsp; StackCookie
0x1800bae75  call    __security_check_cookie
0x1800bae7a  mov     rbx, [rsp+600h+arg_10]
0x1800bae82  add     rsp, 5F0h
0x1800bae89  pop     rdi
0x1800bae8a  pop     rsi
0x1800bae8b  pop     rbp
0x1800bae8c  retn
```
