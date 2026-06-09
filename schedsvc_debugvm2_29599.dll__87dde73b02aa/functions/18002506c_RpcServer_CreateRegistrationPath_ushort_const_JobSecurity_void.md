# RpcServer::CreateRegistrationPath(ushort const *,JobSecurity &,void *)

- ea: `0x18002506c`
- end: `0x180025306`
- name: `?CreateRegistrationPath@RpcServer@@AEAAJPEBGAEAVJobSecurity@@PEAX@Z`
- size: `666`
- prototype: `int(RpcServer *__hidden this, const unsigned __int16 *, struct JobSecurity *, void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024ce0`
- `0x180045df0`

## callees

- `0x180025040`
- `0x18002506c`
- `0x180025550`
- `0x1800256d0`
- `0x180025870`
- `0x18002643c`
- `0x1800265c4`
- `0x1800265fc`
- `0x180027ee0`
- `0x18003f380`
- `0x180040590`
- `0x18004d50c`
- `0x1800504b4`
- `0x180052320`
- `0x18006b14c`

## import_xrefs

- `msvcrt!wcschr` at `0x1800250b9`
- `msvcrt!wcschr` at `0x1800250de`
- `msvcrt!wcschr` at `0x1800250ed`
- `msvcrt!wcschr` at `0x1800250b9`
- `msvcrt!wcschr` at `0x1800250de`
- `msvcrt!wcschr` at `0x1800250ed`
- `msvcrt!wcsrchr` at `0x1800250c9`
- `msvcrt!wcsrchr` at `0x1800250c9`
- `OLEAUT32!__imp_SysAllocString` at `0x18002512e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002512e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800251a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800251a5`
- `RPCRT4!RpcRevertToSelf` at `0x1800252ac`
- `RPCRT4!RpcRevertToSelf` at `0x1800252fd`
- `RPCRT4!RpcRevertToSelf` at `0x1800252ac`
- `RPCRT4!RpcRevertToSelf` at `0x1800252fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180025184`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180025184`

## string_xrefs

- `0x180025281`: `RpcServer::CreateRegistrationPath`

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
  int XmlFileSystemPath; // edi
  WCHAR *v13; // rsi
  int v14; // edx
  char v15; // si
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
      goto LABEL_37;
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
    if ( v13 )
      HeapFree(g_PrivateHeap, 0, v13);
    if ( tsched::IsErrorNotFound((tsched *)(unsigned int)XmlFileSystemPath, v14) )
    {
      v15 = 1;
      v23 = 1;
    }
    else
    {
      if ( XmlFileSystemPath < 0 )
        goto LABEL_37;
      v15 = v23;
    }
    if ( v7 )
    {
      XmlFileSystemPath = JobAccessCheck(ClientToken, *(PSECURITY_DESCRIPTOR *)a3, 4u);
      if ( XmlFileSystemPath < 0 )
        goto LABEL_37;
      NewDescriptor = 0;
      tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(&NewDescriptor, 0);
      v21 = 0;
      XmlFileSystemPath = JobStore::GenerateJobSecurity(v5, v10, 0, 1u, ClientToken, &NewDescriptor);
      if ( XmlFileSystemPath < 0
        || (XmlFileSystemPath = JobStore::RegFolderEntryCreate(v5, v10, (const struct JobSecurity *)&NewDescriptor),
            XmlFileSystemPath < 0) )
      {
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&NewDescriptor);
        goto LABEL_37;
      }
      v21 = 0;
      v16 = (struct _SECURITY_DESCRIPTOR *)NewDescriptor;
      NewDescriptor = 0;
      JobSecurity::Attach(a3, v16);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&NewDescriptor);
    }
    if ( v15 )
      break;
LABEL_35:
    v10 = JobPathWrapper::CursorToChild((JobPathWrapper *)v22);
    if ( !v10 )
    {
      XmlFileSystemPath = 0;
      goto LABEL_37;
    }
  }
  RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v24, L"RpcServer::CreateRegistrationPath", 1);
  XmlFileSystemPath = JobStore::CreateXmlFolder(v5, v10, 0);
  if ( XmlFileSystemPath >= 0 )
  {
    if ( v24 )
      RpcRevertToSelf();
    goto LABEL_35;
  }
  if ( v24 )
    RpcRevertToSelf();
LABEL_37:
  SysFreeString(v6);
  return (unsigned int)XmlFileSystemPath;
}

```

## disassembly

```asm
0x18002506c  mov     [rsp-38h+arg_10], rbx
0x180025071  mov     [rsp-38h+ClientToken], r9
0x180025076  mov     [rsp-38h+arg_0], rcx
0x18002507b  push    rbp
0x18002507c  push    rsi
0x18002507d  push    rdi
0x18002507e  push    r12
0x180025080  push    r13
0x180025082  push    r14
0x180025084  push    r15
0x180025086  mov     rbp, rsp
0x180025089  sub     rsp, 60h
0x18002508d  mov     r12, r8
0x180025090  mov     r15, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x180025097  test    rdx, rdx
0x18002509a  jnz     loc_18002512B
0x1800250a0  xor     ebx, ebx
0x1800250a2  mov     [rbp+var_28], rbx
0x1800250a6  xor     r13b, r13b
0x1800250a9  xor     sil, sil
0x1800250ac  mov     byte ptr [rbp+arg_0], sil
0x1800250b0  mov     [rbp+var_10], rbx
0x1800250b4  xor     edx, edx; Ch
0x1800250b6  mov     rcx, rbx; Str
0x1800250b9  call    cs:__imp_wcschr
0x1800250bf  mov     edi, 5Ch ; '\'
0x1800250c4  mov     edx, edi; Ch
0x1800250c6  mov     rcx, rbx; Str
0x1800250c9  call    cs:__imp_wcsrchr
0x1800250cf  test    rax, rax
0x1800250d2  jz      short loc_1800250D9
0x1800250d4  xor     ecx, ecx
0x1800250d6  mov     [rax], cx
0x1800250d9  xor     edx, edx; Ch
0x1800250db  mov     rcx, rbx; Str
0x1800250de  call    cs:__imp_wcschr
0x1800250e4  mov     [rbp+var_8], rax
0x1800250e8  mov     edx, edi; Ch
0x1800250ea  mov     rcx, rbx; Str
0x1800250ed  call    cs:__imp_wcschr
0x1800250f3  test    rax, rax
0x1800250f6  jz      short loc_1800250FD
0x1800250f8  xor     ecx, ecx
0x1800250fa  mov     [rax], cx
0x1800250fd  mov     r14, rbx
0x180025100  mov     r8, r12; struct JobSecurity *
0x180025103  mov     rdx, r14; unsigned __int16 *
0x180025106  mov     rcx, r15; this
0x180025109  call    ?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z; JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)
0x18002510e  mov     edi, eax
0x180025110  cmp     eax, 80070490h
0x180025115  jz      short loc_18002514F
0x180025117  lea     ecx, [rax+7FF8FFFEh]
0x18002511d  cmp     ecx, 1
0x180025120  jbe     short loc_18002514F
0x180025122  test    eax, eax
0x180025124  jns     short loc_180025152
0x180025126  jmp     loc_1800252C9
0x18002512b  mov     rcx, rdx; psz
0x18002512e  call    cs:__imp_SysAllocString
0x180025134  mov     rbx, rax
0x180025137  mov     [rbp+var_28], rax
0x18002513b  test    rax, rax
0x18002513e  jnz     loc_1800250A6
0x180025144  mov     ecx, 8007000Eh; unsigned int
0x180025149  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002514f  mov     r13b, 1
0x180025152  xor     esi, esi
0x180025154  mov     [rbp+pszPath], rsi
0x180025158  mov     rcx, r15; this
0x18002515b  call    ?GetUseXmlStore@JobStore@@QEBAEXZ; JobStore::GetUseXmlStore(void)
0x180025160  test    al, al
0x180025162  jnz     short loc_180025168
0x180025164  xor     edi, edi
0x180025166  jmp     short loc_180025194
0x180025168  lea     r8, [rbp+pszPath]
0x18002516c  mov     rdx, r14
0x18002516f  mov     rcx, r15
0x180025172  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180025177  mov     edi, eax
0x180025179  mov     rsi, [rbp+pszPath]
0x18002517d  test    eax, eax
0x18002517f  js      short loc_180025194
0x180025181  mov     rcx, rsi; pszPath
0x180025184  call    cs:__imp_PathFileExistsW
0x18002518a  mov     ecx, 80070003h
0x18002518f  test    eax, eax
0x180025191  cmovz   edi, ecx
0x180025194  test    rsi, rsi
0x180025197  jz      short loc_1800251AB
0x180025199  mov     r8, rsi; lpMem
0x18002519c  xor     edx, edx; dwFlags
0x18002519e  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800251a5  call    cs:__imp_HeapFree
0x1800251ab  mov     ecx, edi; this
0x1800251ad  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x1800251b2  test    al, al
0x1800251b4  jz      short loc_1800251BF
0x1800251b6  mov     sil, 1
0x1800251b9  mov     byte ptr [rbp+arg_0], sil
0x1800251bd  jmp     short loc_1800251CB
0x1800251bf  test    edi, edi
0x1800251c1  js      loc_1800252C9
0x1800251c7  mov     sil, byte ptr [rbp+arg_0]
0x1800251cb  test    r13b, r13b
0x1800251ce  jz      loc_180025276
0x1800251d4  mov     r8d, 4; DesiredAccess
0x1800251da  mov     rdx, [r12]; pSecurityDescriptor
0x1800251de  mov     rcx, [rbp+ClientToken]; ClientToken
0x1800251e2  call    ?JobAccessCheck@@YAJPEAX0K@Z; JobAccessCheck(void *,void *,ulong)
0x1800251e7  mov     edi, eax
0x1800251e9  test    eax, eax
0x1800251eb  js      loc_1800252C9
0x1800251f1  mov     [rbp+var_20], 0
0x1800251f9  xor     edx, edx
0x1800251fb  lea     rcx, [rbp+var_20]
0x1800251ff  call    ?Attach@?$AutoLocalPtr@U_SECURITY_DESCRIPTOR@@@tsched@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(_SECURITY_DESCRIPTOR *)
0x180025204  mov     [rbp+var_18], 0
0x18002520b  lea     rax, [rbp+var_20]
0x18002520f  mov     [rsp+60h+NewDescriptor], rax; NewDescriptor
0x180025214  mov     rax, [rbp+ClientToken]
0x180025218  mov     [rsp+60h+var_40], rax; HANDLE
0x18002521d  mov     r9b, 1; IsDirectoryObject
0x180025220  xor     r8d, r8d; StringSecurityDescriptor
0x180025223  mov     rdx, r14; unsigned __int16 *
0x180025226  mov     rcx, r15; this
0x180025229  call    ?GenerateJobSecurity@JobStore@@QEBAJPEBG0EPEAXAEAVJobSecurity@@@Z; JobStore::GenerateJobSecurity(ushort const *,ushort const *,uchar,void *,JobSecurity &)
0x18002522e  mov     edi, eax
0x180025230  test    eax, eax
0x180025232  js      loc_1800252EC
0x180025238  lea     r8, [rbp+var_20]; struct JobSecurity *
0x18002523c  mov     rdx, r14; unsigned __int16 *
0x18002523f  mov     rcx, r15; this
0x180025242  call    ?RegFolderEntryCreate@JobStore@@QEBAJPEBGAEBVJobSecurity@@@Z; JobStore::RegFolderEntryCreate(ushort const *,JobSecurity const &)
0x180025247  mov     edi, eax
0x180025249  test    eax, eax
0x18002524b  js      loc_1800252EC
0x180025251  mov     [rbp+var_18], 0
0x180025258  mov     rdx, [rbp+var_20]; struct _SECURITY_DESCRIPTOR *
0x18002525c  mov     [rbp+var_20], 0
0x180025264  mov     rcx, r12; this
0x180025267  call    ?Attach@JobSecurity@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; JobSecurity::Attach(_SECURITY_DESCRIPTOR *)
0x18002526c  nop
0x18002526d  lea     rcx, [rbp+var_20]
0x180025271  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180025276  test    sil, sil
0x180025279  jz      short loc_1800252B2
0x18002527b  mov     r8d, 1; int
0x180025281  lea     rdx, aRpcserverCreat_0; "RpcServer::CreateRegistrationPath"
0x180025288  lea     rcx, [rbp+arg_8]; this
0x18002528c  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x180025291  nop
0x180025292  xor     r8d, r8d; unsigned __int16 *
0x180025295  mov     rdx, r14; unsigned __int16 *
0x180025298  mov     rcx, r15; this
0x18002529b  call    ?CreateXmlFolder@JobStore@@QEAAJPEBG0@Z; JobStore::CreateXmlFolder(ushort const *,ushort const *)
0x1800252a0  mov     edi, eax
0x1800252a2  test    eax, eax
0x1800252a4  js      short loc_1800252F7
0x1800252a6  cmp     [rbp+arg_8], 0
0x1800252aa  jz      short loc_1800252B2
0x1800252ac  call    cs:__imp_RpcRevertToSelf
0x1800252b2  lea     rcx, [rbp+var_10]; this
0x1800252b6  call    ?CursorToChild@JobPathWrapper@@QEAAPEAGXZ; JobPathWrapper::CursorToChild(void)
0x1800252bb  mov     r14, rax
0x1800252be  test    rax, rax
0x1800252c1  jnz     loc_180025100
0x1800252c7  xor     edi, edi
0x1800252c9  mov     rcx, rbx; bstrString
0x1800252cc  call    cs:__imp_SysFreeString
0x1800252d2  mov     eax, edi
0x1800252d4  mov     rbx, [rsp+60h+arg_10]
0x1800252dc  add     rsp, 60h
0x1800252e0  pop     r15
0x1800252e2  pop     r14
0x1800252e4  pop     r13
0x1800252e6  pop     r12
0x1800252e8  pop     rdi
0x1800252e9  pop     rsi
0x1800252ea  pop     rbp
0x1800252eb  retn
0x1800252ec  lea     rcx, [rbp+var_20]
0x1800252f0  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800252f5  jmp     short loc_1800252C9
0x1800252f7  cmp     [rbp+arg_8], 0
0x1800252fb  jz      short loc_1800252C9
0x1800252fd  call    cs:__imp_RpcRevertToSelf
0x180025303  jmp     short loc_1800252C9
```
