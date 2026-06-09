# JobStore::InitKnownTreeFolder(ushort const *,ushort const *)

- ea: `0x18006c5b8`
- end: `0x18006c837`
- name: `?InitKnownTreeFolder@JobStore@@AEAAJPEBG0@Z`
- size: `639`
- prototype: `__int64 __fastcall(JobStore *__hidden this, const unsigned __int16 *, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006c234`

## callees

- `0x18000dc30`
- `0x18001a260`
- `0x180021300`
- `0x180025040`
- `0x1800265c4`
- `0x180027ee0`
- `0x1800290f0`
- `0x180037e10`
- `0x18003f380`
- `0x180040900`
- `0x18004a5d8`
- `0x180051ce0`
- `0x180052584`
- `0x18006c5b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006c7e2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006c7e2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006c77e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006c77e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006c6b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006c6b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006c5f5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006c7a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006c5f5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006c7a3`

## string_xrefs

- `0x18006c632`: `TaskCache\Tree`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall JobStore::InitKnownTreeFolder(HKEY *this, unsigned __int16 *a2, LPCWSTR StringSecurityDescriptor)
{
  int v6; // edx
  tsched *v7; // rcx
  signed int XmlFileSystemPath; // edi
  const unsigned __int16 *v9; // rdx
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  WCHAR *v12; // rcx
  WCHAR *v13; // rbx
  DWORD FileAttributesW; // eax
  int v15; // edx
  tsched *v16; // rcx
  LPCWSTR lpFileName; // [rsp+50h] [rbp-19h] BYREF
  const WCHAR **v19; // [rsp+58h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR v22; // [rsp+70h] [rbp+7h] BYREF
  int v23; // [rsp+78h] [rbp+Fh]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp+17h] BYREF
  struct _SECURITY_ATTRIBUTES v25; // [rsp+98h] [rbp+2Fh] BYREF
  DWORD dwDisposition; // [rsp+E8h] [rbp+7Fh] BYREF

  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:P(A;OICI;KRSD;;;BA)(A;OICI;KA;;;SY)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    dwDisposition = 0;
    phkResult = 0;
    _bstr_t::_bstr_t((_bstr_t *)&v19, L"TaskCache\\Tree");
    if ( !tsched::IsRoot((tsched *)a2, v9) )
    {
      _bstr_t::_bstr_t((_bstr_t *)&lpFileName, a2);
      _bstr_t::operator+=(&v19, &lpFileName);
      _bstr_t::~_bstr_t((_bstr_t *)&lpFileName);
    }
    if ( v19 )
      v10 = *v19;
    else
      v10 = 0;
    v11 = RegCreateKeyExW(this[2], v10, 0, 0, 0, 0xF003Fu, &SecurityAttributes, &phkResult, &dwDisposition);
    XmlFileSystemPath = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        XmlFileSystemPath = (unsigned __int16)v11 | 0x80070000;
      goto LABEL_11;
    }
    if ( dwDisposition == 1 )
    {
      v22 = 0;
      tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(&v22, 0);
      v23 = 0;
      XmlFileSystemPath = JobSecurity::SetSddl(&v22, StringSecurityDescriptor);
      if ( XmlFileSystemPath < 0
        || (XmlFileSystemPath = JobSecurity::StreamOut((JobSecurity *)&v22, phkResult), XmlFileSystemPath < 0) )
      {
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v22);
LABEL_11:
        _bstr_t::~_bstr_t((_bstr_t *)&v19);
        wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
        goto LABEL_29;
      }
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v22);
    }
    if ( JobStore::GetUseXmlStore((JobStore *)this) )
    {
      lpFileName = 0;
      XmlFileSystemPath = JobStore::GetXmlFileSystemPath(this, a2, &lpFileName);
      if ( XmlFileSystemPath < 0 )
      {
        v12 = (WCHAR *)lpFileName;
LABEL_20:
        operator delete(v12);
        goto LABEL_11;
      }
      v13 = (WCHAR *)lpFileName;
      FileAttributesW = GetFileAttributesW(lpFileName);
      if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
      {
        lpFileName = 0;
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                StringSecurityDescriptor,
                1u,
                (PSECURITY_DESCRIPTOR *)&lpFileName,
                0)
          || (*(_QWORD *)&v25.nLength = 24,
              v25.lpSecurityDescriptor = (LPVOID)lpFileName,
              *(_QWORD *)&v25.bInheritHandle = 0,
              !CreateDirectoryW(v13, &v25)) )
        {
          XmlFileSystemPath = tsched::GetLastHrError(v16, v15);
          tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&lpFileName);
          v12 = v13;
          goto LABEL_20;
        }
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&lpFileName);
      }
      operator delete(v13);
    }
    _bstr_t::~_bstr_t((_bstr_t *)&v19);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    XmlFileSystemPath = 0;
    goto LABEL_29;
  }
  XmlFileSystemPath = tsched::GetLastHrError(v7, v6);
LABEL_29:
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
  return (unsigned int)XmlFileSystemPath;
}

```

## disassembly

```asm
0x18006c5b8  mov     [rsp-8+arg_0], rbx
0x18006c5bd  mov     [rsp-8+arg_8], rsi
0x18006c5c2  push    rbp
0x18006c5c3  push    rdi
0x18006c5c4  push    r14
0x18006c5c6  lea     rbp, [rsp-47h]
0x18006c5cb  sub     rsp, 0B0h
0x18006c5d2  mov     r14, r8
0x18006c5d5  mov     rbx, rdx
0x18006c5d8  mov     rsi, rcx
0x18006c5db  mov     [rbp+57h+SecurityDescriptor], 0
0x18006c5e3  xor     r9d, r9d; SecurityDescriptorSize
0x18006c5e6  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006c5ea  lea     edx, [r9+1]; StringSDRevision
0x18006c5ee  lea     rcx, aDPAOiciKrsdBaA; "D:P(A;OICI;KRSD;;;BA)(A;OICI;KA;;;SY)"
0x18006c5f5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18006c5fb  test    eax, eax
0x18006c5fd  jnz     short loc_18006C60B
0x18006c5ff  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006c604  mov     edi, eax
0x18006c606  jmp     loc_18006C814
0x18006c60b  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18006c613  mov     rax, [rbp+57h+SecurityDescriptor]
0x18006c617  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18006c61b  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x18006c623  mov     [rbp+57h+dwDisposition], 0
0x18006c62a  mov     [rbp+57h+var_60], 0
0x18006c632  lea     rdx, aTaskcacheTree; "TaskCache\\Tree"
0x18006c639  lea     rcx, [rbp+57h+var_68]; this
0x18006c63d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006c642  nop
0x18006c643  mov     rcx, rbx; this
0x18006c646  call    ?IsRoot@tsched@@YA_NPEBG@Z; tsched::IsRoot(ushort const *)
0x18006c64b  test    al, al
0x18006c64d  jnz     short loc_18006C673
0x18006c64f  mov     rdx, rbx; unsigned __int16 *
0x18006c652  lea     rcx, [rbp+57h+lpFileName]; this
0x18006c656  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006c65b  nop
0x18006c65c  lea     rdx, [rbp+57h+lpFileName]
0x18006c660  lea     rcx, [rbp+57h+var_68]
0x18006c664  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18006c669  nop
0x18006c66a  lea     rcx, [rbp+57h+lpFileName]; this
0x18006c66e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18006c673  mov     rax, [rbp+57h+var_68]
0x18006c677  test    rax, rax
0x18006c67a  jz      short loc_18006C681
0x18006c67c  mov     rdx, [rax]
0x18006c67f  jmp     short loc_18006C683
0x18006c681  xor     edx, edx; lpSubKey
0x18006c683  lea     rax, [rbp+57h+dwDisposition]
0x18006c687  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18006c68c  lea     rax, [rbp+57h+var_60]
0x18006c690  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18006c695  lea     rax, [rbp+57h+SecurityAttributes]
0x18006c699  mov     [rsp+0C0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18006c69e  mov     [rsp+0C0h+samDesired], 0F003Fh; samDesired
0x18006c6a6  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x18006c6ae  xor     r9d, r9d; lpClass
0x18006c6b1  xor     r8d, r8d; Reserved
0x18006c6b4  mov     rcx, [rsi+10h]; hKey
0x18006c6b8  call    cs:__imp_RegCreateKeyExW
0x18006c6be  mov     edi, eax
0x18006c6c0  test    eax, eax
0x18006c6c2  jz      short loc_18006C6E7
0x18006c6c4  jle     short loc_18006C6CF
0x18006c6c6  movzx   edi, ax
0x18006c6c9  or      edi, 80070000h
0x18006c6cf  lea     rcx, [rbp+57h+var_68]; this
0x18006c6d3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18006c6d8  nop
0x18006c6d9  lea     rcx, [rbp+57h+var_60]; this
0x18006c6dd  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18006c6e2  jmp     loc_18006C814
0x18006c6e7  cmp     [rbp+57h+dwDisposition], 1
0x18006c6eb  jnz     short loc_18006C73C
0x18006c6ed  mov     [rbp+57h+var_50], 0
0x18006c6f5  xor     edx, edx
0x18006c6f7  lea     rcx, [rbp+57h+var_50]
0x18006c6fb  call    ?Attach@?$AutoLocalPtr@U_SECURITY_DESCRIPTOR@@@tsched@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(_SECURITY_DESCRIPTOR *)
0x18006c700  mov     [rbp+57h+var_48], 0
0x18006c707  mov     rdx, r14; StringSecurityDescriptor
0x18006c70a  lea     rcx, [rbp+57h+var_50]; SecurityDescriptor
0x18006c70e  call    ?SetSddl@JobSecurity@@QEAAJPEBG@Z; JobSecurity::SetSddl(ushort const *)
0x18006c713  mov     edi, eax
0x18006c715  lea     rcx, [rbp+57h+var_50]; this
0x18006c719  test    eax, eax
0x18006c71b  jns     short loc_18006C724
0x18006c71d  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18006c722  jmp     short loc_18006C6CF
0x18006c724  mov     rdx, [rbp+57h+var_60]; HKEY
0x18006c728  call    ?StreamOut@JobSecurity@@QEBAJPEAUHKEY__@@@Z; JobSecurity::StreamOut(HKEY__ *)
0x18006c72d  mov     edi, eax
0x18006c72f  lea     rcx, [rbp+57h+var_50]
0x18006c733  test    eax, eax
0x18006c735  js      short loc_18006C71D
0x18006c737  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18006c73c  mov     rcx, rsi; this
0x18006c73f  call    ?GetUseXmlStore@JobStore@@QEBAEXZ; JobStore::GetUseXmlStore(void)
0x18006c744  test    al, al
0x18006c746  jz      loc_18006C7FF
0x18006c74c  mov     [rbp+57h+lpFileName], 0
0x18006c754  lea     r8, [rbp+57h+lpFileName]
0x18006c758  mov     rdx, rbx
0x18006c75b  mov     rcx, rsi
0x18006c75e  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x18006c763  mov     edi, eax
0x18006c765  test    eax, eax
0x18006c767  jns     short loc_18006C777
0x18006c769  mov     rcx, [rbp+57h+lpFileName]; void *
0x18006c76d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c772  jmp     loc_18006C6CF
0x18006c777  mov     rbx, [rbp+57h+lpFileName]
0x18006c77b  mov     rcx, rbx; lpFileName
0x18006c77e  call    cs:__imp_GetFileAttributesW
0x18006c784  cmp     eax, 0FFFFFFFFh
0x18006c787  jz      short loc_18006C78D
0x18006c789  test    al, 10h
0x18006c78b  jnz     short loc_18006C7F6
0x18006c78d  mov     [rbp+57h+lpFileName], 0
0x18006c795  xor     r9d, r9d; SecurityDescriptorSize
0x18006c798  lea     r8, [rbp+57h+lpFileName]; SecurityDescriptor
0x18006c79c  lea     edx, [r9+1]; StringSDRevision
0x18006c7a0  mov     rcx, r14; StringSecurityDescriptor
0x18006c7a3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18006c7a9  test    eax, eax
0x18006c7ab  jnz     short loc_18006C7C3
0x18006c7ad  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006c7b2  mov     edi, eax
0x18006c7b4  lea     rcx, [rbp+57h+lpFileName]
0x18006c7b8  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18006c7bd  nop
0x18006c7be  mov     rcx, rbx
0x18006c7c1  jmp     short loc_18006C76D
0x18006c7c3  mov     qword ptr [rbp+57h+var_28.nLength], 18h
0x18006c7cb  mov     rax, [rbp+57h+lpFileName]
0x18006c7cf  mov     [rbp+57h+var_28.lpSecurityDescriptor], rax
0x18006c7d3  mov     qword ptr [rbp+57h+var_28.bInheritHandle], 0
0x18006c7db  lea     rdx, [rbp+57h+var_28]; lpSecurityAttributes
0x18006c7df  mov     rcx, rbx; lpPathName
0x18006c7e2  call    cs:__imp_CreateDirectoryW
0x18006c7e8  test    eax, eax
0x18006c7ea  jz      short loc_18006C7AD
0x18006c7ec  lea     rcx, [rbp+57h+lpFileName]
0x18006c7f0  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18006c7f5  nop
0x18006c7f6  mov     rcx, rbx; void *
0x18006c7f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c7fe  nop
0x18006c7ff  lea     rcx, [rbp+57h+var_68]; this
0x18006c803  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18006c808  nop
0x18006c809  lea     rcx, [rbp+57h+var_60]; this
0x18006c80d  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18006c812  xor     edi, edi
0x18006c814  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18006c818  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18006c81d  mov     eax, edi
0x18006c81f  lea     r11, [rsp+0C0h+var_10]
0x18006c827  mov     rbx, [r11+20h]
0x18006c82b  mov     rsi, [r11+28h]
0x18006c82f  mov     rsp, r11
0x18006c832  pop     r14
0x18006c834  pop     rdi
0x18006c835  pop     rbp
0x18006c836  retn
```
