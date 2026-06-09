# CSdCatalog::_CreateGlobalCatalog(ushort *,ulong)

- ea: `0x1800b9a24`
- end: `0x1800b9da4`
- name: `?_CreateGlobalCatalog@CSdCatalog@@AEAAJPEAGK@Z`
- size: `896`
- prototype: `int(CSdCatalog *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800bb8ec`

## callees

- `0x180005b70`
- `0x180072e08`
- `0x180072f14`
- `0x180089b20`
- `0x180092d48`
- `0x1800935fc`
- `0x1800b9a24`
- `0x1800ba378`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x1800b9b54`
- `KERNEL32!GetSystemDirectoryW` at `0x1800b9b54`
- `KERNEL32!LocalFree` at `0x1800b9d2e`
- `KERNEL32!LocalFree` at `0x1800b9d2e`
- `KERNEL32!CreateFileW` at `0x1800b9cee`
- `KERNEL32!CreateFileW` at `0x1800b9cee`
- `KERNEL32!GetVolumePathNameW` at `0x1800b9b96`
- `KERNEL32!GetVolumePathNameW` at `0x1800b9b96`
- `KERNEL32!CloseHandle` at `0x1800b9d5a`
- `KERNEL32!CloseHandle` at `0x1800b9d5a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b9b04`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b9b04`
- `ole32!CoCreateGuid` at `0x1800b9c19`
- `ole32!CoCreateGuid` at `0x1800b9c19`

## string_xrefs

- `0x1800b9c86`: `GlobalCatalogTemp.wbcat`
- `0x1800b9a5c`: `CSdCatalog::_CreateGlobalCatalog`

## pseudocode

```c
__int64 __fastcall CSdCatalog::_CreateGlobalCatalog(CSdCatalog *this, unsigned __int16 *a2)
{
  CSdCatalog *v3; // rcx
  unsigned int v4; // r8d
  __int64 v5; // rbx
  int CatalogPath; // edi
  __int16 v7; // ax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  int v14; // [rsp+88h] [rbp-78h] BYREF
  __int16 v15; // [rsp+8Ch] [rbp-74h]
  __int16 v16; // [rsp+8Eh] [rbp-72h]
  ULONG SecurityDescriptorSize; // [rsp+C0h] [rbp-40h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+C8h] [rbp-38h] BYREF
  GUID pguid; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR szVolumePathName; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v21[110]; // [rsp+F2h] [rbp-Eh] BYREF
  WCHAR Buffer; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v23[526]; // [rsp+162h] [rbp+62h] BYREF
  unsigned __int16 v24[328]; // [rsp+370h] [rbp+270h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CSdCatalog::_CreateGlobalCatalog", 0x989u, 1u);
  Buffer = 0;
  memset_0(v23, 0, 0x206u);
  szVolumePathName = 0;
  memset_0(v21, 0, 0x62u);
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  pguid = 0;
  if ( !a2 )
  {
    CatalogPath = -2147024809;
    v14 = -2147024809;
    v16 = 2451;
    goto LABEL_21;
  }
  v5 = -1;
  v14 = 0;
  v15 = 2451;
  CatalogPath = CSdCatalog::_GetCatalogPath(v3, v24, v4);
  v14 = CatalogPath;
  v7 = 2453;
  if ( CatalogPath >= 0 )
  {
    v15 = 2453;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)",
           1u,
           &SecurityDescriptor,
           &SecurityDescriptorSize) )
    {
      v14 = 0;
      v15 = 2456;
      SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
      SecurityAttributes.nLength = 24;
      if ( GetSystemDirectoryW(&Buffer, 0x104u) )
      {
        v14 = 0;
        v15 = 2462;
        if ( GetVolumePathNameW(&Buffer, &szVolumePathName, 0x32u) )
        {
          v14 = 0;
          v15 = 2463;
          CatalogPath = SxCreateSVI(&szVolumePathName);
          v14 = CatalogPath;
          v7 = 2464;
          if ( CatalogPath >= 0 )
          {
            v15 = 2464;
            CatalogPath = EnsureDirectoryExists(v24, &SecurityAttributes, 0, 0);
            v14 = CatalogPath;
            v7 = 2467;
            if ( CatalogPath >= 0 )
            {
              v15 = 2467;
              CoCreateGuid(&pguid);
              CatalogPath = StringCchPrintfW(
                              a2,
                              0x144u,
                              L"%s\\%s{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
                              v24,
                              L"GlobalCatalogTemp.wbcat",
                              pguid.Data1,
                              pguid.Data2,
                              pguid.Data3,
                              pguid.Data4[0],
                              pguid.Data4[1],
                              pguid.Data4[2],
                              pguid.Data4[3],
                              pguid.Data4[4],
                              pguid.Data4[5],
                              pguid.Data4[6],
                              pguid.Data4[7]);
              v14 = CatalogPath;
              v7 = 2473;
              if ( CatalogPath >= 0 )
              {
                v15 = 2473;
                v5 = (__int64)CreateFileW(a2, 0xC0000000, 3u, &SecurityAttributes, 1u, 0x80u, 0);
                if ( v5 != -1 )
                {
                  CatalogPath = 0;
                  v14 = 0;
                  v15 = 2477;
                  goto LABEL_16;
                }
                CatalogPath = GetLastFailureAsHRESULT(v11);
                v14 = CatalogPath;
                v7 = 2477;
              }
            }
          }
        }
        else
        {
          CatalogPath = GetLastFailureAsHRESULT(v10);
          v14 = CatalogPath;
          v7 = 2463;
        }
      }
      else
      {
        CatalogPath = GetLastFailureAsHRESULT(v9);
        v14 = CatalogPath;
        v7 = 2462;
      }
    }
    else
    {
      CatalogPath = GetLastFailureAsHRESULT(v8);
      v14 = CatalogPath;
      v7 = 2456;
    }
  }
  v16 = v7;
LABEL_16:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
    SecurityAttributes.lpSecurityDescriptor = 0;
    CatalogPath = v14;
  }
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v5);
LABEL_21:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return (unsigned int)CatalogPath;
}

```

## disassembly

```asm
0x1800b9a24  push    rbp
0x1800b9a26  push    rbx
0x1800b9a27  push    rsi
0x1800b9a28  push    rdi
0x1800b9a29  push    r14
0x1800b9a2b  push    r15
0x1800b9a2d  lea     rbp, [rsp-518h]
0x1800b9a35  sub     rsp, 618h
0x1800b9a3c  mov     rax, cs:__security_cookie
0x1800b9a43  xor     rax, rsp
0x1800b9a46  mov     [rbp+540h+var_40], rax
0x1800b9a4d  mov     r15, rdx
0x1800b9a50  mov     r9d, 1; unsigned __int16
0x1800b9a56  mov     r8d, 989h; unsigned __int16
0x1800b9a5c  lea     rdx, aCsdcatalogCrea_0; "CSdCatalog::_CreateGlobalCatalog"
0x1800b9a63  lea     rcx, [rbp+540h+var_5B8]; this
0x1800b9a67  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800b9a6c  xor     eax, eax
0x1800b9a6e  mov     [rbp+540h+Buffer], ax
0x1800b9a72  xor     edx, edx; Val
0x1800b9a74  mov     r8d, 206h; Size
0x1800b9a7a  lea     rcx, [rbp+540h+var_4DE]; void *
0x1800b9a7e  call    memset_0
0x1800b9a83  xor     eax, eax
0x1800b9a85  mov     [rbp+540h+szVolumePathName], ax
0x1800b9a89  xor     edx, edx; Val
0x1800b9a8b  lea     r8d, [rax+62h]; Size
0x1800b9a8f  lea     rcx, [rbp+540h+var_54E]; void *
0x1800b9a93  call    memset_0
0x1800b9a98  xorps   xmm0, xmm0
0x1800b9a9b  xor     eax, eax
0x1800b9a9d  movups  xmmword ptr [rbp+540h+SecurityAttributes.nLength], xmm0
0x1800b9aa1  mov     qword ptr [rbp+540h+SecurityAttributes.bInheritHandle], rax
0x1800b9aa5  mov     [rbp+540h+SecurityDescriptor], rax
0x1800b9aa9  mov     [rbp+540h+SecurityDescriptorSize], eax
0x1800b9aac  movups  xmmword ptr [rbp+540h+pguid.Data1], xmm0
0x1800b9ab0  test    r15, r15
0x1800b9ab3  jz      loc_1800B9D68
0x1800b9ab9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9abd  mov     [rbp+540h+var_5B8], eax
0x1800b9ac0  mov     eax, 993h
0x1800b9ac5  mov     [rbp+540h+var_5B4], ax
0x1800b9ac9  lea     rdx, [rbp+540h+var_2D0]; unsigned __int16 *
0x1800b9ad0  call    ?_GetCatalogPath@CSdCatalog@@AEAAJPEAGK@Z; CSdCatalog::_GetCatalogPath(ushort *,ulong)
0x1800b9ad5  mov     edi, eax
0x1800b9ad7  mov     [rbp+540h+var_5B8], eax
0x1800b9ada  test    eax, eax
0x1800b9adc  mov     eax, 995h
0x1800b9ae1  jns     short loc_1800B9AEC
0x1800b9ae3  mov     [rbp+540h+var_5B2], ax
0x1800b9ae7  jmp     loc_1800B9D25
0x1800b9aec  mov     [rbp+540h+var_5B4], ax
0x1800b9af0  lea     r9, [rbp+540h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800b9af4  lea     r8, [rbp+540h+SecurityDescriptor]; SecurityDescriptor
0x1800b9af8  mov     edx, 1; StringSDRevision
0x1800b9afd  lea     rcx, c_wszSVISubDirSecurity; "D:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)"
0x1800b9b04  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800b9b0b  nop     dword ptr [rax+rax+00h]
0x1800b9b10  test    eax, eax
0x1800b9b12  jnz     short loc_1800B9B25
0x1800b9b14  call    GetLastFailureAsHRESULT
0x1800b9b19  mov     edi, eax
0x1800b9b1b  mov     [rbp+540h+var_5B8], eax
0x1800b9b1e  mov     eax, 998h
0x1800b9b23  jmp     short loc_1800B9AE3
0x1800b9b25  mov     [rbp+540h+var_5B8], 0
0x1800b9b2c  mov     eax, 998h
0x1800b9b31  mov     [rbp+540h+var_5B4], ax
0x1800b9b35  mov     [rbp+540h+SecurityAttributes.bInheritHandle], 0
0x1800b9b3c  mov     rax, [rbp+540h+SecurityDescriptor]
0x1800b9b40  mov     [rbp+540h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800b9b44  mov     [rbp+540h+SecurityAttributes.nLength], 18h
0x1800b9b4b  mov     edx, 104h; uSize
0x1800b9b50  lea     rcx, [rbp+540h+Buffer]; lpBuffer
0x1800b9b54  call    cs:__imp_GetSystemDirectoryW
0x1800b9b5b  nop     dword ptr [rax+rax+00h]
0x1800b9b60  test    eax, eax
0x1800b9b62  jnz     short loc_1800B9B78
0x1800b9b64  call    GetLastFailureAsHRESULT
0x1800b9b69  mov     edi, eax
0x1800b9b6b  mov     [rbp+540h+var_5B8], eax
0x1800b9b6e  mov     eax, 99Eh
0x1800b9b73  jmp     loc_1800B9AE3
0x1800b9b78  mov     [rbp+540h+var_5B8], 0
0x1800b9b7f  mov     eax, 99Eh
0x1800b9b84  mov     [rbp+540h+var_5B4], ax
0x1800b9b88  mov     r8d, 32h ; '2'; cchBufferLength
0x1800b9b8e  lea     rdx, [rbp+540h+szVolumePathName]; lpszVolumePathName
0x1800b9b92  lea     rcx, [rbp+540h+Buffer]; lpszFileName
0x1800b9b96  call    cs:__imp_GetVolumePathNameW
0x1800b9b9d  nop     dword ptr [rax+rax+00h]
0x1800b9ba2  test    eax, eax
0x1800b9ba4  jnz     short loc_1800B9BBA
0x1800b9ba6  call    GetLastFailureAsHRESULT
0x1800b9bab  mov     edi, eax
0x1800b9bad  mov     [rbp+540h+var_5B8], eax
0x1800b9bb0  mov     eax, 99Fh
0x1800b9bb5  jmp     loc_1800B9AE3
0x1800b9bba  mov     [rbp+540h+var_5B8], 0
0x1800b9bc1  mov     eax, 99Fh
0x1800b9bc6  mov     [rbp+540h+var_5B4], ax
0x1800b9bca  lea     rcx, [rbp+540h+szVolumePathName]; unsigned __int16 *
0x1800b9bce  call    ?SxCreateSVI@@YAJPEBG@Z; SxCreateSVI(ushort const *)
0x1800b9bd3  mov     edi, eax
0x1800b9bd5  mov     [rbp+540h+var_5B8], eax
0x1800b9bd8  test    eax, eax
0x1800b9bda  mov     eax, 9A0h
0x1800b9bdf  js      loc_1800B9AE3
0x1800b9be5  mov     [rbp+540h+var_5B4], ax
0x1800b9be9  xor     r9d, r9d; int
0x1800b9bec  xor     r8d, r8d; int
0x1800b9bef  lea     rdx, [rbp+540h+SecurityAttributes]; lpSecurityAttributes
0x1800b9bf3  lea     rcx, [rbp+540h+var_2D0]; unsigned __int16 *
0x1800b9bfa  call    ?EnsureDirectoryExists@@YAJPEBGPEBU_SECURITY_ATTRIBUTES@@HH@Z; EnsureDirectoryExists(ushort const *,_SECURITY_ATTRIBUTES const *,int,int)
0x1800b9bff  mov     edi, eax
0x1800b9c01  mov     [rbp+540h+var_5B8], eax
0x1800b9c04  test    eax, eax
0x1800b9c06  mov     eax, 9A3h
0x1800b9c0b  js      loc_1800B9AE3
0x1800b9c11  mov     [rbp+540h+var_5B4], ax
0x1800b9c15  lea     rcx, [rbp+540h+pguid]; pguid
0x1800b9c19  call    cs:__imp_CoCreateGuid
0x1800b9c20  nop     dword ptr [rax+rax+00h]
0x1800b9c25  movzx   eax, [rbp+540h+pguid.Data4+7]
0x1800b9c29  movzx   ecx, [rbp+540h+pguid.Data4+6]
0x1800b9c2d  movzx   edx, [rbp+540h+pguid.Data4+5]
0x1800b9c31  movzx   r8d, [rbp+540h+pguid.Data4+4]
0x1800b9c36  movzx   r9d, [rbp+540h+pguid.Data4+3]
0x1800b9c3b  movzx   r10d, [rbp+540h+pguid.Data4+2]
0x1800b9c40  movzx   r11d, [rbp+540h+pguid.Data4+1]
0x1800b9c45  movzx   edi, [rbp+540h+pguid.Data4]
0x1800b9c49  movzx   esi, [rbp+540h+pguid.Data3]
0x1800b9c4d  movzx   r14d, [rbp+540h+pguid.Data2]
0x1800b9c52  mov     [rsp+640h+var_5C8], eax
0x1800b9c56  mov     [rsp+640h+var_5D0], ecx
0x1800b9c5a  mov     [rsp+640h+var_5D8], edx
0x1800b9c5e  mov     [rsp+640h+var_5E0], r8d
0x1800b9c63  mov     [rsp+640h+var_5E8], r9d
0x1800b9c68  mov     [rsp+640h+var_5F0], r10d
0x1800b9c6d  mov     [rsp+640h+var_5F8], r11d
0x1800b9c72  mov     [rsp+640h+var_600], edi
0x1800b9c76  mov     [rsp+640h+var_608], esi
0x1800b9c7a  mov     dword ptr [rsp+640h+hTemplateFile], r14d
0x1800b9c7f  mov     eax, [rbp+540h+pguid.Data1]
0x1800b9c82  mov     [rsp+640h+dwFlagsAndAttributes], eax
0x1800b9c86  lea     rax, aGlobalcatalogt; "GlobalCatalogTemp.wbcat"
0x1800b9c8d  mov     qword ptr [rsp+640h+dwCreationDisposition], rax
0x1800b9c92  lea     r9, [rbp+540h+var_2D0]
0x1800b9c99  lea     r8, aSS8x4x4x2x2x2x; "%s\\%s{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x"...
0x1800b9ca0  mov     edx, 144h; unsigned __int64
0x1800b9ca5  mov     rcx, r15; unsigned __int16 *
0x1800b9ca8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b9cad  mov     edi, eax
0x1800b9caf  mov     [rbp+540h+var_5B8], eax
0x1800b9cb2  test    eax, eax
0x1800b9cb4  mov     eax, 9A9h
0x1800b9cb9  js      loc_1800B9AE3
0x1800b9cbf  mov     [rbp+540h+var_5B4], ax
0x1800b9cc3  mov     [rsp+640h+hTemplateFile], 0; hTemplateFile
0x1800b9ccc  mov     [rsp+640h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b9cd4  mov     [rsp+640h+dwCreationDisposition], 1; dwCreationDisposition
0x1800b9cdc  lea     r9, [rbp+540h+SecurityAttributes]; lpSecurityAttributes
0x1800b9ce0  mov     edx, 0C0000000h; dwDesiredAccess
0x1800b9ce5  mov     r8d, 3; dwShareMode
0x1800b9ceb  mov     rcx, r15; lpFileName
0x1800b9cee  call    cs:__imp_CreateFileW
0x1800b9cf5  nop     dword ptr [rax+rax+00h]
0x1800b9cfa  mov     rbx, rax
0x1800b9cfd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b9d01  jnz     short loc_1800B9D17
0x1800b9d03  call    GetLastFailureAsHRESULT
0x1800b9d08  mov     edi, eax
0x1800b9d0a  mov     [rbp+540h+var_5B8], eax
0x1800b9d0d  mov     eax, 9ADh
0x1800b9d12  jmp     loc_1800B9AE3
0x1800b9d17  xor     edi, edi
0x1800b9d19  mov     [rbp+540h+var_5B8], edi
0x1800b9d1c  mov     eax, 9ADh
0x1800b9d21  mov     [rbp+540h+var_5B4], ax
0x1800b9d25  mov     rcx, [rbp+540h+SecurityDescriptor]; hMem
0x1800b9d29  test    rcx, rcx
0x1800b9d2c  jz      short loc_1800B9D4D
0x1800b9d2e  call    cs:__imp_LocalFree
0x1800b9d35  nop     dword ptr [rax+rax+00h]
0x1800b9d3a  mov     [rbp+540h+SecurityDescriptor], 0
0x1800b9d42  mov     [rbp+540h+SecurityAttributes.lpSecurityDescriptor], 0
0x1800b9d4a  mov     edi, [rbp+540h+var_5B8]
0x1800b9d4d  lea     rax, [rbx-1]
0x1800b9d51  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b9d55  ja      short loc_1800B9D79
0x1800b9d57  mov     rcx, rbx; hObject
0x1800b9d5a  call    cs:__imp_CloseHandle
0x1800b9d61  nop     dword ptr [rax+rax+00h]
0x1800b9d66  jmp     short loc_1800B9D79
0x1800b9d68  mov     edi, 80070057h
0x1800b9d6d  mov     [rbp+540h+var_5B8], edi
0x1800b9d70  mov     eax, 993h
0x1800b9d75  mov     [rbp+540h+var_5B2], ax
0x1800b9d79  lea     rcx, [rbp+540h+var_5B8]; this
0x1800b9d7d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800b9d82  mov     eax, edi
0x1800b9d84  mov     rcx, [rbp+540h+var_40]
0x1800b9d8b  xor     rcx, rsp; StackCookie
0x1800b9d8e  call    __security_check_cookie
0x1800b9d93  add     rsp, 618h
0x1800b9d9a  pop     r15
0x1800b9d9c  pop     r14
0x1800b9d9e  pop     rdi
0x1800b9d9f  pop     rsi
0x1800b9da0  pop     rbx
0x1800b9da1  pop     rbp
0x1800b9da2  retn
```
