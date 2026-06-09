# CSdCatalog::_CreateGlobalCatalog(ushort *,ulong)

- ea: `0x1800b4064`
- end: `0x1800b43b9`
- name: `?_CreateGlobalCatalog@CSdCatalog@@AEAAJPEAGK@Z`
- size: `853`
- prototype: `int(CSdCatalog *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800b5e90`

## callees

- `0x1800059d0`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180086220`
- `0x18008ed84`
- `0x18008f5d0`
- `0x1800b4064`
- `0x1800b4980`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x1800b418e`
- `KERNEL32!GetSystemDirectoryW` at `0x1800b418e`
- `KERNEL32!LocalFree` at `0x1800b4350`
- `KERNEL32!LocalFree` at `0x1800b4350`
- `KERNEL32!CreateFileW` at `0x1800b4316`
- `KERNEL32!CreateFileW` at `0x1800b4316`
- `KERNEL32!GetVolumePathNameW` at `0x1800b41ca`
- `KERNEL32!GetVolumePathNameW` at `0x1800b41ca`
- `KERNEL32!CloseHandle` at `0x1800b4376`
- `KERNEL32!CloseHandle` at `0x1800b4376`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b4144`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b4144`
- `ole32!CoCreateGuid` at `0x1800b4247`
- `ole32!CoCreateGuid` at `0x1800b4247`

## string_xrefs

- `0x1800b42ae`: `GlobalCatalogTemp.wbcat`
- `0x1800b409c`: `CSdCatalog::_CreateGlobalCatalog`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CSdCatalog::_CreateGlobalCatalog", 2441, 1);
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
0x1800b4064  push    rbp
0x1800b4066  push    rbx
0x1800b4067  push    rsi
0x1800b4068  push    rdi
0x1800b4069  push    r14
0x1800b406b  push    r15
0x1800b406d  lea     rbp, [rsp-518h]
0x1800b4075  sub     rsp, 618h
0x1800b407c  mov     rax, cs:__security_cookie
0x1800b4083  xor     rax, rsp
0x1800b4086  mov     [rbp+540h+var_40], rax
0x1800b408d  mov     r15, rdx
0x1800b4090  mov     r9d, 1; unsigned __int16
0x1800b4096  mov     r8d, 989h; unsigned __int16
0x1800b409c  lea     rdx, aCsdcatalogCrea_0; "CSdCatalog::_CreateGlobalCatalog"
0x1800b40a3  lea     rcx, [rbp+540h+var_5B8]; this
0x1800b40a7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800b40ac  xor     eax, eax
0x1800b40ae  mov     [rbp+540h+Buffer], ax
0x1800b40b2  xor     edx, edx; Val
0x1800b40b4  mov     r8d, 206h; Size
0x1800b40ba  lea     rcx, [rbp+540h+var_4DE]; void *
0x1800b40be  call    memset_0
0x1800b40c3  xor     eax, eax
0x1800b40c5  mov     [rbp+540h+szVolumePathName], ax
0x1800b40c9  xor     edx, edx; Val
0x1800b40cb  lea     r8d, [rax+62h]; Size
0x1800b40cf  lea     rcx, [rbp+540h+var_54E]; void *
0x1800b40d3  call    memset_0
0x1800b40d8  xorps   xmm0, xmm0
0x1800b40db  xor     eax, eax
0x1800b40dd  movups  xmmword ptr [rbp+540h+SecurityAttributes.nLength], xmm0
0x1800b40e1  mov     qword ptr [rbp+540h+SecurityAttributes.bInheritHandle], rax
0x1800b40e5  mov     [rbp+540h+SecurityDescriptor], rax
0x1800b40e9  mov     [rbp+540h+SecurityDescriptorSize], eax
0x1800b40ec  movups  xmmword ptr [rbp+540h+pguid.Data1], xmm0
0x1800b40f0  test    r15, r15
0x1800b40f3  jz      loc_1800B437E
0x1800b40f9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b40fd  mov     [rbp+540h+var_5B8], eax
0x1800b4100  mov     eax, 993h
0x1800b4105  mov     [rbp+540h+var_5B4], ax
0x1800b4109  lea     rdx, [rbp+540h+var_2D0]; unsigned __int16 *
0x1800b4110  call    ?_GetCatalogPath@CSdCatalog@@AEAAJPEAGK@Z; CSdCatalog::_GetCatalogPath(ushort *,ulong)
0x1800b4115  mov     edi, eax
0x1800b4117  mov     [rbp+540h+var_5B8], eax
0x1800b411a  test    eax, eax
0x1800b411c  mov     eax, 995h
0x1800b4121  jns     short loc_1800B412C
0x1800b4123  mov     [rbp+540h+var_5B2], ax
0x1800b4127  jmp     loc_1800B4347
0x1800b412c  mov     [rbp+540h+var_5B4], ax
0x1800b4130  lea     r9, [rbp+540h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800b4134  lea     r8, [rbp+540h+SecurityDescriptor]; SecurityDescriptor
0x1800b4138  mov     edx, 1; StringSDRevision
0x1800b413d  lea     rcx, c_wszSVISubDirSecurity; "D:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)"
0x1800b4144  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800b414a  test    eax, eax
0x1800b414c  jnz     short loc_1800B415F
0x1800b414e  call    GetLastFailureAsHRESULT
0x1800b4153  mov     edi, eax
0x1800b4155  mov     [rbp+540h+var_5B8], eax
0x1800b4158  mov     eax, 998h
0x1800b415d  jmp     short loc_1800B4123
0x1800b415f  mov     [rbp+540h+var_5B8], 0
0x1800b4166  mov     eax, 998h
0x1800b416b  mov     [rbp+540h+var_5B4], ax
0x1800b416f  mov     [rbp+540h+SecurityAttributes.bInheritHandle], 0
0x1800b4176  mov     rax, [rbp+540h+SecurityDescriptor]
0x1800b417a  mov     [rbp+540h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800b417e  mov     [rbp+540h+SecurityAttributes.nLength], 18h
0x1800b4185  mov     edx, 104h; uSize
0x1800b418a  lea     rcx, [rbp+540h+Buffer]; lpBuffer
0x1800b418e  call    cs:__imp_GetSystemDirectoryW
0x1800b4194  test    eax, eax
0x1800b4196  jnz     short loc_1800B41AC
0x1800b4198  call    GetLastFailureAsHRESULT
0x1800b419d  mov     edi, eax
0x1800b419f  mov     [rbp+540h+var_5B8], eax
0x1800b41a2  mov     eax, 99Eh
0x1800b41a7  jmp     loc_1800B4123
0x1800b41ac  mov     [rbp+540h+var_5B8], 0
0x1800b41b3  mov     eax, 99Eh
0x1800b41b8  mov     [rbp+540h+var_5B4], ax
0x1800b41bc  mov     r8d, 32h ; '2'; cchBufferLength
0x1800b41c2  lea     rdx, [rbp+540h+szVolumePathName]; lpszVolumePathName
0x1800b41c6  lea     rcx, [rbp+540h+Buffer]; lpszFileName
0x1800b41ca  call    cs:__imp_GetVolumePathNameW
0x1800b41d0  test    eax, eax
0x1800b41d2  jnz     short loc_1800B41E8
0x1800b41d4  call    GetLastFailureAsHRESULT
0x1800b41d9  mov     edi, eax
0x1800b41db  mov     [rbp+540h+var_5B8], eax
0x1800b41de  mov     eax, 99Fh
0x1800b41e3  jmp     loc_1800B4123
0x1800b41e8  mov     [rbp+540h+var_5B8], 0
0x1800b41ef  mov     eax, 99Fh
0x1800b41f4  mov     [rbp+540h+var_5B4], ax
0x1800b41f8  lea     rcx, [rbp+540h+szVolumePathName]; unsigned __int16 *
0x1800b41fc  call    ?SxCreateSVI@@YAJPEBG@Z; SxCreateSVI(ushort const *)
0x1800b4201  mov     edi, eax
0x1800b4203  mov     [rbp+540h+var_5B8], eax
0x1800b4206  test    eax, eax
0x1800b4208  mov     eax, 9A0h
0x1800b420d  js      loc_1800B4123
0x1800b4213  mov     [rbp+540h+var_5B4], ax
0x1800b4217  xor     r9d, r9d; int
0x1800b421a  xor     r8d, r8d; int
0x1800b421d  lea     rdx, [rbp+540h+SecurityAttributes]; lpSecurityAttributes
0x1800b4221  lea     rcx, [rbp+540h+var_2D0]; unsigned __int16 *
0x1800b4228  call    ?EnsureDirectoryExists@@YAJPEBGPEBU_SECURITY_ATTRIBUTES@@HH@Z; EnsureDirectoryExists(ushort const *,_SECURITY_ATTRIBUTES const *,int,int)
0x1800b422d  mov     edi, eax
0x1800b422f  mov     [rbp+540h+var_5B8], eax
0x1800b4232  test    eax, eax
0x1800b4234  mov     eax, 9A3h
0x1800b4239  js      loc_1800B4123
0x1800b423f  mov     [rbp+540h+var_5B4], ax
0x1800b4243  lea     rcx, [rbp+540h+pguid]; pguid
0x1800b4247  call    cs:__imp_CoCreateGuid
0x1800b424d  movzx   eax, [rbp+540h+pguid.Data4+7]
0x1800b4251  movzx   ecx, [rbp+540h+pguid.Data4+6]
0x1800b4255  movzx   edx, [rbp+540h+pguid.Data4+5]
0x1800b4259  movzx   r8d, [rbp+540h+pguid.Data4+4]
0x1800b425e  movzx   r9d, [rbp+540h+pguid.Data4+3]
0x1800b4263  movzx   r10d, [rbp+540h+pguid.Data4+2]
0x1800b4268  movzx   r11d, [rbp+540h+pguid.Data4+1]
0x1800b426d  movzx   edi, [rbp+540h+pguid.Data4]
0x1800b4271  movzx   esi, [rbp+540h+pguid.Data3]
0x1800b4275  movzx   r14d, [rbp+540h+pguid.Data2]
0x1800b427a  mov     [rsp+640h+var_5C8], eax
0x1800b427e  mov     [rsp+640h+var_5D0], ecx
0x1800b4282  mov     [rsp+640h+var_5D8], edx
0x1800b4286  mov     [rsp+640h+var_5E0], r8d
0x1800b428b  mov     [rsp+640h+var_5E8], r9d
0x1800b4290  mov     [rsp+640h+var_5F0], r10d
0x1800b4295  mov     [rsp+640h+var_5F8], r11d
0x1800b429a  mov     [rsp+640h+var_600], edi
0x1800b429e  mov     [rsp+640h+var_608], esi
0x1800b42a2  mov     dword ptr [rsp+640h+hTemplateFile], r14d
0x1800b42a7  mov     eax, [rbp+540h+pguid.Data1]
0x1800b42aa  mov     [rsp+640h+dwFlagsAndAttributes], eax
0x1800b42ae  lea     rax, aGlobalcatalogt; "GlobalCatalogTemp.wbcat"
0x1800b42b5  mov     qword ptr [rsp+640h+dwCreationDisposition], rax
0x1800b42ba  lea     r9, [rbp+540h+var_2D0]
0x1800b42c1  lea     r8, aSS8x4x4x2x2x2x; "%s\\%s{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x"...
0x1800b42c8  mov     edx, 144h; unsigned __int64
0x1800b42cd  mov     rcx, r15; unsigned __int16 *
0x1800b42d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b42d5  mov     edi, eax
0x1800b42d7  mov     [rbp+540h+var_5B8], eax
0x1800b42da  test    eax, eax
0x1800b42dc  mov     eax, 9A9h
0x1800b42e1  js      loc_1800B4123
0x1800b42e7  mov     [rbp+540h+var_5B4], ax
0x1800b42eb  mov     [rsp+640h+hTemplateFile], 0; hTemplateFile
0x1800b42f4  mov     [rsp+640h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b42fc  mov     [rsp+640h+dwCreationDisposition], 1; dwCreationDisposition
0x1800b4304  lea     r9, [rbp+540h+SecurityAttributes]; lpSecurityAttributes
0x1800b4308  mov     edx, 0C0000000h; dwDesiredAccess
0x1800b430d  mov     r8d, 3; dwShareMode
0x1800b4313  mov     rcx, r15; lpFileName
0x1800b4316  call    cs:__imp_CreateFileW
0x1800b431c  mov     rbx, rax
0x1800b431f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b4323  jnz     short loc_1800B4339
0x1800b4325  call    GetLastFailureAsHRESULT
0x1800b432a  mov     edi, eax
0x1800b432c  mov     [rbp+540h+var_5B8], eax
0x1800b432f  mov     eax, 9ADh
0x1800b4334  jmp     loc_1800B4123
0x1800b4339  xor     edi, edi
0x1800b433b  mov     [rbp+540h+var_5B8], edi
0x1800b433e  mov     eax, 9ADh
0x1800b4343  mov     [rbp+540h+var_5B4], ax
0x1800b4347  mov     rcx, [rbp+540h+SecurityDescriptor]; hMem
0x1800b434b  test    rcx, rcx
0x1800b434e  jz      short loc_1800B4369
0x1800b4350  call    cs:__imp_LocalFree
0x1800b4356  mov     [rbp+540h+SecurityDescriptor], 0
0x1800b435e  mov     [rbp+540h+SecurityAttributes.lpSecurityDescriptor], 0
0x1800b4366  mov     edi, [rbp+540h+var_5B8]
0x1800b4369  lea     rax, [rbx-1]
0x1800b436d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b4371  ja      short loc_1800B438F
0x1800b4373  mov     rcx, rbx; hObject
0x1800b4376  call    cs:__imp_CloseHandle
0x1800b437c  jmp     short loc_1800B438F
0x1800b437e  mov     edi, 80070057h
0x1800b4383  mov     [rbp+540h+var_5B8], edi
0x1800b4386  mov     eax, 993h
0x1800b438b  mov     [rbp+540h+var_5B2], ax
0x1800b438f  lea     rcx, [rbp+540h+var_5B8]; this
0x1800b4393  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800b4398  mov     eax, edi
0x1800b439a  mov     rcx, [rbp+540h+var_40]
0x1800b43a1  xor     rcx, rsp; StackCookie
0x1800b43a4  call    __security_check_cookie
0x1800b43a9  add     rsp, 618h
0x1800b43b0  pop     r15
0x1800b43b2  pop     r14
0x1800b43b4  pop     rdi
0x1800b43b5  pop     rsi
0x1800b43b6  pop     rbx
0x1800b43b7  pop     rbp
0x1800b43b8  retn
```
