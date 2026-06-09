# RpcServer::CreateRegistrationPath(ushort const *,JobSecurity &,void *)

- ea: `0x18001fe44`
- end: `0x180020106`
- name: `?CreateRegistrationPath@RpcServer@@AEAAJPEBGAEAVJobSecurity@@PEAX@Z`
- size: `706`
- prototype: `int(RpcServer *__hidden this, const unsigned __int16 *, struct JobSecurity *, void *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001fa60`
- `0x180047ee0`

## callees

- `0x18000cc40`
- `0x18001fe10`
- `0x18001fe44`
- `0x180020350`
- `0x1800204e0`
- `0x1800206a0`
- `0x18002123c`
- `0x1800213d8`
- `0x180021418`
- `0x180022d80`
- `0x180040af0`
- `0x180042200`
- `0x18004f898`
- `0x1800529a0`
- `0x18005491c`
- `0x18006e65c`

## import_xrefs

- `msvcrt!wcschr` at `0x18001fe91`
- `msvcrt!wcschr` at `0x18001fec2`
- `msvcrt!wcschr` at `0x18001fed7`
- `msvcrt!wcschr` at `0x18001fe91`
- `msvcrt!wcschr` at `0x18001fec2`
- `msvcrt!wcschr` at `0x18001fed7`
- `msvcrt!wcsrchr` at `0x18001fea7`
- `msvcrt!wcsrchr` at `0x18001fea7`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ff1e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ff1e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800200bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800200bf`
- `RPCRT4!RpcRevertToSelf` at `0x180020099`
- `RPCRT4!RpcRevertToSelf` at `0x1800200f7`
- `RPCRT4!RpcRevertToSelf` at `0x180020099`
- `RPCRT4!RpcRevertToSelf` at `0x1800200f7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001ff7a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001ff7a`

## string_xrefs

- `0x18002006e`: `RpcServer::CreateRegistrationPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RpcServer::CreateRegistrationPath(
        RpcServer *this,
        const unsigned __int16 *a2,
        struct JobSecurity *a3,
        void *a4)
{
  JobStore *v5; // r15
  wchar_t *v6; // rbx
  char v7; // r13
  wchar_t *v8; // rax
  wchar_t *v9; // rax
  OLECHAR *v10; // r14
  int v11; // eax
  int XmlFileSystemPath; // esi
  WCHAR *v13; // rdi
  int v14; // edx
  char v15; // di
  struct _SECURITY_DESCRIPTOR *v16; // rdx
  LPCWSTR pszPath; // [rsp+30h] [rbp-30h] BYREF
  wchar_t *v19; // [rsp+38h] [rbp-28h]
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+40h] [rbp-20h] BYREF
  int v21; // [rsp+48h] [rbp-18h]
  _QWORD v22[2]; // [rsp+50h] [rbp-10h] BYREF
  char v23; // [rsp+A0h] [rbp+40h]
  int v24; // [rsp+A8h] [rbp+48h] BYREF
  HANDLE ClientToken; // [rsp+B8h] [rbp+58h]

  ClientToken = a4;
  v5 = JobStore::m_pCommonStore;
  if ( a2 )
  {
    v6 = SysAllocString(a2);
    v19 = v6;
    if ( !v6 )
      ATL::PrivateAtlThrow(0x8007000E);
  }
  else
  {
    v6 = 0;
    v19 = 0;
  }
  v7 = 0;
  v23 = 0;
  v22[0] = v6;
  wcschr(v6, 0);
  v8 = wcsrchr(v6, 0x5Cu);
  if ( v8 )
    *v8 = 0;
  v22[1] = wcschr(v6, 0);
  v9 = wcschr(v6, 0x5Cu);
  if ( v9 )
    *v9 = 0;
  v10 = v6;
  while ( 1 )
  {
    v11 = JobStore::RegJobSecurityQuery(v5, v10, a3);
    XmlFileSystemPath = v11;
    if ( v11 == -2147023728 || (unsigned int)(v11 + 2147024894) <= 1 )
    {
      v7 = 1;
    }
    else if ( v11 < 0 )
    {
      goto LABEL_35;
    }
    v13 = 0;
    pszPath = 0;
    if ( JobStore::GetUseXmlStore(v5) )
    {
      XmlFileSystemPath = JobStore::GetXmlFileSystemPath(v5, v10, &pszPath);
      v13 = (WCHAR *)pszPath;
      if ( XmlFileSystemPath >= 0 && !PathFileExistsW(pszPath) )
        XmlFileSystemPath = -2147024893;
    }
    else
    {
      XmlFileSystemPath = 0;
    }
    operator delete(v13);
    if ( tsched::IsErrorNotFound((tsched *)(unsigned int)XmlFileSystemPath, v14) )
    {
      v15 = 1;
      v23 = 1;
    }
    else
    {
      if ( XmlFileSystemPath < 0 )
        goto LABEL_35;
      v15 = v23;
    }
    if ( v7 )
    {
      XmlFileSystemPath = JobAccessCheck(ClientToken, *(PSECURITY_DESCRIPTOR *)a3, 4u);
      if ( XmlFileSystemPath < 0 )
        goto LABEL_35;
      NewDescriptor = 0;
      tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(&NewDescriptor, 0);
      v21 = 0;
      XmlFileSystemPath = JobStore::GenerateJobSecurity(v5, v10, 0, 1u, ClientToken, &NewDescriptor);
      if ( XmlFileSystemPath < 0
        || (XmlFileSystemPath = JobStore::RegFolderEntryCreate(v5, v10, (const struct JobSecurity *)&NewDescriptor),
            XmlFileSystemPath < 0) )
      {
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&NewDescriptor);
        goto LABEL_35;
      }
      v21 = 0;
      v16 = (struct _SECURITY_DESCRIPTOR *)NewDescriptor;
      NewDescriptor = 0;
      JobSecurity::Attach(a3, v16);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&NewDescriptor);
    }
    if ( v15 )
      break;
LABEL_33:
    v10 = JobPathWrapper::CursorToChild((JobPathWrapper *)v22);
    if ( !v10 )
    {
      XmlFileSystemPath = 0;
      goto LABEL_35;
    }
  }
  RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v24, L"RpcServer::CreateRegistrationPath", 1);
  XmlFileSystemPath = JobStore::CreateXmlFolder(v5, v10, 0);
  if ( XmlFileSystemPath >= 0 )
  {
    if ( v24 )
      RpcRevertToSelf();
    goto LABEL_33;
  }
  if ( v24 )
    RpcRevertToSelf();
LABEL_35:
  SysFreeString(v6);
  return (unsigned int)XmlFileSystemPath;
}

```

## disassembly

```asm
0x18001fe44  mov     [rsp-38h+arg_10], rbx
0x18001fe49  mov     [rsp-38h+ClientToken], r9
0x18001fe4e  mov     [rsp-38h+arg_0], rcx
0x18001fe53  push    rbp
0x18001fe54  push    rsi
0x18001fe55  push    rdi
0x18001fe56  push    r12
0x18001fe58  push    r13
0x18001fe5a  push    r14
0x18001fe5c  push    r15
0x18001fe5e  mov     rbp, rsp
0x18001fe61  sub     rsp, 60h
0x18001fe65  mov     r12, r8
0x18001fe68  mov     r15, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18001fe6f  test    rdx, rdx
0x18001fe72  jnz     loc_18001FF1B
0x18001fe78  xor     ebx, ebx
0x18001fe7a  mov     [rbp+var_28], rbx
0x18001fe7e  xor     r13b, r13b
0x18001fe81  xor     dil, dil
0x18001fe84  mov     byte ptr [rbp+arg_0], dil
0x18001fe88  mov     [rbp+var_10], rbx
0x18001fe8c  xor     edx, edx; Ch
0x18001fe8e  mov     rcx, rbx; Str
0x18001fe91  call    cs:__imp_wcschr
0x18001fe98  nop     dword ptr [rax+rax+00h]
0x18001fe9d  mov     edi, 5Ch ; '\'
0x18001fea2  mov     edx, edi; Ch
0x18001fea4  mov     rcx, rbx; Str
0x18001fea7  call    cs:__imp_wcsrchr
0x18001feae  nop     dword ptr [rax+rax+00h]
0x18001feb3  test    rax, rax
0x18001feb6  jz      short loc_18001FEBD
0x18001feb8  xor     ecx, ecx
0x18001feba  mov     [rax], cx
0x18001febd  xor     edx, edx; Ch
0x18001febf  mov     rcx, rbx; Str
0x18001fec2  call    cs:__imp_wcschr
0x18001fec9  nop     dword ptr [rax+rax+00h]
0x18001fece  mov     [rbp+var_8], rax
0x18001fed2  mov     edx, edi; Ch
0x18001fed4  mov     rcx, rbx; Str
0x18001fed7  call    cs:__imp_wcschr
0x18001fede  nop     dword ptr [rax+rax+00h]
0x18001fee3  test    rax, rax
0x18001fee6  jz      short loc_18001FEED
0x18001fee8  xor     ecx, ecx
0x18001feea  mov     [rax], cx
0x18001feed  mov     r14, rbx
0x18001fef0  mov     r8, r12; struct JobSecurity *
0x18001fef3  mov     rdx, r14; unsigned __int16 *
0x18001fef6  mov     rcx, r15; this
0x18001fef9  call    ?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z; JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)
0x18001fefe  mov     esi, eax
0x18001ff00  cmp     eax, 80070490h
0x18001ff05  jz      short loc_18001FF45
0x18001ff07  lea     ecx, [rax+7FF8FFFEh]
0x18001ff0d  cmp     ecx, 1
0x18001ff10  jbe     short loc_18001FF45
0x18001ff12  test    eax, eax
0x18001ff14  jns     short loc_18001FF48
0x18001ff16  jmp     loc_1800200BC
0x18001ff1b  mov     rcx, rdx; psz
0x18001ff1e  call    cs:__imp_SysAllocString
0x18001ff25  nop     dword ptr [rax+rax+00h]
0x18001ff2a  mov     rbx, rax
0x18001ff2d  mov     [rbp+var_28], rax
0x18001ff31  test    rax, rax
0x18001ff34  jnz     loc_18001FE7E
0x18001ff3a  mov     ecx, 8007000Eh; unsigned int
0x18001ff3f  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18001ff45  mov     r13b, 1
0x18001ff48  xor     edi, edi
0x18001ff4a  mov     [rbp+pszPath], rdi
0x18001ff4e  mov     rcx, r15; this
0x18001ff51  call    ?GetUseXmlStore@JobStore@@QEBAEXZ; JobStore::GetUseXmlStore(void)
0x18001ff56  test    al, al
0x18001ff58  jnz     short loc_18001FF5E
0x18001ff5a  xor     esi, esi
0x18001ff5c  jmp     short loc_18001FF90
0x18001ff5e  lea     r8, [rbp+pszPath]
0x18001ff62  mov     rdx, r14
0x18001ff65  mov     rcx, r15
0x18001ff68  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x18001ff6d  mov     esi, eax
0x18001ff6f  mov     rdi, [rbp+pszPath]
0x18001ff73  test    eax, eax
0x18001ff75  js      short loc_18001FF90
0x18001ff77  mov     rcx, rdi; pszPath
0x18001ff7a  call    cs:__imp_PathFileExistsW
0x18001ff81  nop     dword ptr [rax+rax+00h]
0x18001ff86  mov     ecx, 80070003h
0x18001ff8b  test    eax, eax
0x18001ff8d  cmovz   esi, ecx
0x18001ff90  mov     rcx, rdi; void *
0x18001ff93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ff98  mov     ecx, esi; this
0x18001ff9a  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18001ff9f  test    al, al
0x18001ffa1  jz      short loc_18001FFAC
0x18001ffa3  mov     dil, 1
0x18001ffa6  mov     byte ptr [rbp+arg_0], dil
0x18001ffaa  jmp     short loc_18001FFB8
0x18001ffac  test    esi, esi
0x18001ffae  js      loc_1800200BC
0x18001ffb4  mov     dil, byte ptr [rbp+arg_0]
0x18001ffb8  test    r13b, r13b
0x18001ffbb  jz      loc_180020063
0x18001ffc1  mov     r8d, 4; DesiredAccess
0x18001ffc7  mov     rdx, [r12]; pSecurityDescriptor
0x18001ffcb  mov     rcx, [rbp+ClientToken]; ClientToken
0x18001ffcf  call    ?JobAccessCheck@@YAJPEAX0K@Z; JobAccessCheck(void *,void *,ulong)
0x18001ffd4  mov     esi, eax
0x18001ffd6  test    eax, eax
0x18001ffd8  js      loc_1800200BC
0x18001ffde  mov     [rbp+var_20], 0
0x18001ffe6  xor     edx, edx
0x18001ffe8  lea     rcx, [rbp+var_20]
0x18001ffec  call    ?Attach@?$AutoLocalPtr@U_SECURITY_DESCRIPTOR@@@tsched@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(_SECURITY_DESCRIPTOR *)
0x18001fff1  mov     [rbp+var_18], 0
0x18001fff8  lea     rax, [rbp+var_20]
0x18001fffc  mov     [rsp+60h+NewDescriptor], rax; NewDescriptor
0x180020001  mov     rax, [rbp+ClientToken]
0x180020005  mov     [rsp+60h+var_40], rax; HANDLE
0x18002000a  mov     r9b, 1; IsDirectoryObject
0x18002000d  xor     r8d, r8d; StringSecurityDescriptor
0x180020010  mov     rdx, r14; unsigned __int16 *
0x180020013  mov     rcx, r15; this
0x180020016  call    ?GenerateJobSecurity@JobStore@@QEBAJPEBG0EPEAXAEAVJobSecurity@@@Z; JobStore::GenerateJobSecurity(ushort const *,ushort const *,uchar,void *,JobSecurity &)
0x18002001b  mov     esi, eax
0x18002001d  test    eax, eax
0x18002001f  js      loc_1800200E6
0x180020025  lea     r8, [rbp+var_20]; struct JobSecurity *
0x180020029  mov     rdx, r14; unsigned __int16 *
0x18002002c  mov     rcx, r15; this
0x18002002f  call    ?RegFolderEntryCreate@JobStore@@QEBAJPEBGAEBVJobSecurity@@@Z; JobStore::RegFolderEntryCreate(ushort const *,JobSecurity const &)
0x180020034  mov     esi, eax
0x180020036  test    eax, eax
0x180020038  js      loc_1800200E6
0x18002003e  mov     [rbp+var_18], 0
0x180020045  mov     rdx, [rbp+var_20]; struct _SECURITY_DESCRIPTOR *
0x180020049  mov     [rbp+var_20], 0
0x180020051  mov     rcx, r12; this
0x180020054  call    ?Attach@JobSecurity@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; JobSecurity::Attach(_SECURITY_DESCRIPTOR *)
0x180020059  nop
0x18002005a  lea     rcx, [rbp+var_20]
0x18002005e  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180020063  test    dil, dil
0x180020066  jz      short loc_1800200A5
0x180020068  mov     r8d, 1; int
0x18002006e  lea     rdx, aRpcserverCreat_0; "RpcServer::CreateRegistrationPath"
0x180020075  lea     rcx, [rbp+arg_8]; this
0x180020079  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x18002007e  nop
0x18002007f  xor     r8d, r8d; unsigned __int16 *
0x180020082  mov     rdx, r14; unsigned __int16 *
0x180020085  mov     rcx, r15; this
0x180020088  call    ?CreateXmlFolder@JobStore@@QEAAJPEBG0@Z; JobStore::CreateXmlFolder(ushort const *,ushort const *)
0x18002008d  mov     esi, eax
0x18002008f  test    eax, eax
0x180020091  js      short loc_1800200F1
0x180020093  cmp     [rbp+arg_8], 0
0x180020097  jz      short loc_1800200A5
0x180020099  call    cs:__imp_RpcRevertToSelf
0x1800200a0  nop     dword ptr [rax+rax+00h]
0x1800200a5  lea     rcx, [rbp+var_10]; this
0x1800200a9  call    ?CursorToChild@JobPathWrapper@@QEAAPEAGXZ; JobPathWrapper::CursorToChild(void)
0x1800200ae  mov     r14, rax
0x1800200b1  test    rax, rax
0x1800200b4  jnz     loc_18001FEF0
0x1800200ba  xor     esi, esi
0x1800200bc  mov     rcx, rbx; bstrString
0x1800200bf  call    cs:__imp_SysFreeString
0x1800200c6  nop     dword ptr [rax+rax+00h]
0x1800200cb  mov     eax, esi
0x1800200cd  mov     rbx, [rsp+60h+arg_10]
0x1800200d5  add     rsp, 60h
0x1800200d9  pop     r15
0x1800200db  pop     r14
0x1800200dd  pop     r13
0x1800200df  pop     r12
0x1800200e1  pop     rdi
0x1800200e2  pop     rsi
0x1800200e3  pop     rbp
0x1800200e4  retn
0x1800200e6  lea     rcx, [rbp+var_20]
0x1800200ea  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800200ef  jmp     short loc_1800200BC
0x1800200f1  cmp     [rbp+arg_8], 0
0x1800200f5  jz      short loc_1800200BC
0x1800200f7  call    cs:__imp_RpcRevertToSelf
0x1800200fe  nop     dword ptr [rax+rax+00h]
0x180020103  jmp     short loc_1800200BC
```
