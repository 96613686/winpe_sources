# AclHelper::UpdateFileAcl(void *,ushort const *,bool,ulong,_ACCESS_MODE)

- ea: `0x18004ba9c`
- end: `0x18004bd1c`
- name: `?UpdateFileAcl@AclHelper@@YAXPEAXPEBG_NKW4_ACCESS_MODE@@@Z`
- size: `640`
- prototype: `void __usercall(AclHelper *__hidden this@<rcx>, LPCWSTR lpFileName@<rdx>, const unsigned __int16 *@<r8>, bool@<r9b>, unsigned int, enum _ACCESS_MODE)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004a43c`
- `0x18004a688`
- `0x18004aa68`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x180006660`
- `0x18000d0ec`
- `0x180022d10`
- `0x180049bc4`
- `0x180049c60`
- `0x18004a3b0`
- `0x18004b9d0`
- `0x18004ba9c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bcb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bcb9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004baf7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004baf7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc9f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18004bc40`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18004bc40`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18004bb63`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18004bb63`

## string_xrefs

- `0x18004bce3`: `onecore\vm\compute\dll\lib\inc\AclHelper.h`
- `0x18004bcf5`: `onecore\vm\compute\dll\lib\inc\AclHelper.h`
- `0x18004bd0a`: `onecore\vm\compute\dll\lib\inc\AclHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall AclHelper::UpdateFileAcl(
        AclHelper *this,
        LPCWSTR lpFileName,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  char v6; // di
  char *FileW; // rbx
  const char *v9; // r9
  DWORD SecurityInfo; // eax
  const struct _ACL *Dacl; // rax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // edi
  DWORD v14; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-81h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-81h]
  HLOCAL hMem[2]; // [rsp+50h] [rbp-51h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-41h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-21h] BYREF
  PACL pDacl[2]; // [rsp+A0h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor[2]; // [rsp+B0h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v6 = (char)a3;
  FileW = (char *)CreateFileW(lpFileName, 0x60000u, 3u, 0, 3u, ((unsigned __int8)a3 << 25) | 0x80u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\inc\\AclHelper.h",
      v9);
  *(_OWORD *)ppSecurityDescriptor = 0;
  SecurityInfo = GetSecurityInfo(FileW, SE_FILE_OBJECT, 4u, 0, 0, 0, 0, ppSecurityDescriptor);
  if ( SecurityInfo )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\inc\\AclHelper.h",
      (const char *)SecurityInfo,
      dwCreationDisposition);
  *(_OWORD *)pDacl = 0;
  Dacl = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)ppSecurityDescriptor);
  Vml::VmDacl::VmDacl((Vml::VmDacl *)pDacl, Dacl);
  memset_0(hMem, 0, 0x50u);
  Vml::VmSid::VmSid((Vml::VmSid *)hMem, v12);
  if ( a5 == 1 )
  {
    v13 = v6 != 0 ? 3 : 0;
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, this, a4, v13, GRANT_ACCESS);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, hMem[0], a4, v13, GRANT_ACCESS);
  }
  else
  {
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, this, 0, 0, REVOKE_ACCESS);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, hMem[0], 0, 0, REVOKE_ACCESS);
  }
  v14 = SetSecurityInfo(FileW, SE_FILE_OBJECT, 4u, 0, 0, pDacl[0], 0);
  if ( v14 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\inc\\AclHelper.h",
      (const char *)v14,
      dwCreationDispositiona);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  std::wstring::~wstring(v19);
  std::wstring::~wstring(v18);
  if ( pDacl[0] )
    LocalFree(pDacl[0]);
  if ( ppSecurityDescriptor[0] )
    LocalFree(ppSecurityDescriptor[0]);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
}

```

## disassembly

```asm
0x18004ba9c  push    rbp
0x18004ba9e  push    rbx
0x18004ba9f  push    rsi
0x18004baa0  push    rdi
0x18004baa1  push    r14
0x18004baa3  lea     rbp, [rsp-2Fh]
0x18004baa8  sub     rsp, 0D0h
0x18004baaf  mov     rax, cs:__security_cookie
0x18004bab6  xor     rax, rsp
0x18004bab9  mov     [rbp+4Fh+var_30], rax
0x18004babd  mov     r14d, r9d
0x18004bac0  movzx   edi, r8b
0x18004bac4  mov     r10, rdx
0x18004bac7  mov     rsi, rcx
0x18004baca  mov     eax, edi
0x18004bacc  shl     eax, 19h
0x18004bacf  bts     eax, 7
0x18004bad3  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18004badc  mov     [rsp+0F0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18004bae0  mov     eax, 3
0x18004bae5  mov     [rsp+0F0h+dwCreationDisposition], eax; dwCreationDisposition
0x18004bae9  xor     r9d, r9d; lpSecurityAttributes
0x18004baec  mov     r8d, eax; dwShareMode
0x18004baef  mov     edx, 60000h; dwDesiredAccess
0x18004baf4  mov     rcx, r10; lpFileName
0x18004baf7  call    cs:__imp_CreateFileW
0x18004bafe  nop     dword ptr [rax+rax+00h]
0x18004bb03  mov     rbx, rax
0x18004bb06  mov     [rbp+4Fh+var_B0], rax
0x18004bb0a  inc     rax
0x18004bb0d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004bb13  setz    al
0x18004bb16  mov     rcx, [rbp+57h]; this
0x18004bb1a  test    al, al
0x18004bb1c  jnz     loc_18004BCF5
0x18004bb22  xorps   xmm0, xmm0
0x18004bb25  movups  xmmword ptr [rbp+4Fh+var_40], xmm0
0x18004bb29  mov     [rbp+4Fh+var_40], 0
0x18004bb31  lea     rax, [rbp+4Fh+var_40]
0x18004bb35  mov     [rsp+0F0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18004bb3a  mov     [rsp+0F0h+hTemplateFile], 0; ppSacl
0x18004bb43  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], 0; ppDacl
0x18004bb4c  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; unsigned int
0x18004bb55  xor     r9d, r9d; ppsidOwner
0x18004bb58  lea     edx, [r9+1]; ObjectType
0x18004bb5c  lea     r8d, [r9+4]; SecurityInfo
0x18004bb60  mov     rcx, rbx; handle
0x18004bb63  call    cs:__imp_GetSecurityInfo
0x18004bb6a  nop     dword ptr [rax+rax+00h]
0x18004bb6f  mov     rcx, [rbp+57h]; this
0x18004bb73  test    eax, eax
0x18004bb75  jnz     loc_18004BD07
0x18004bb7b  xorps   xmm0, xmm0
0x18004bb7e  movups  xmmword ptr [rbp+4Fh+pDacl], xmm0
0x18004bb82  lea     rcx, [rbp+4Fh+var_40]; this
0x18004bb86  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x18004bb8b  mov     rdx, rax; struct _ACL *
0x18004bb8e  lea     rcx, [rbp+4Fh+pDacl]; this
0x18004bb92  call    ??0VmDacl@Vml@@QEAA@PEBU_ACL@@@Z; Vml::VmDacl::VmDacl(_ACL const *)
0x18004bb97  nop
0x18004bb98  xor     edx, edx; Val
0x18004bb9a  lea     r8d, [rdx+50h]; Size
0x18004bb9e  lea     rcx, [rbp+4Fh+hMem]; void *
0x18004bba2  call    memset_0
0x18004bba7  lea     rcx, [rbp+4Fh+hMem]; this
0x18004bbab  call    ??0VmSid@Vml@@QEAA@PEBG@Z; Vml::VmSid::VmSid(ushort const *)
0x18004bbb0  nop
0x18004bbb1  mov     rdx, rsi; void *
0x18004bbb4  lea     rcx, [rbp+4Fh+pDacl]; this
0x18004bbb8  cmp     [rbp+4Fh+arg_20], 1
0x18004bbbc  jnz     short loc_18004BBE9
0x18004bbbe  neg     dil
0x18004bbc1  sbb     edi, edi
0x18004bbc3  and     edi, 3
0x18004bbc6  mov     [rsp+0F0h+dwCreationDisposition], 1; enum _ACCESS_MODE
0x18004bbce  mov     r9d, edi; unsigned int
0x18004bbd1  mov     r8d, r14d; unsigned int
0x18004bbd4  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x18004bbd9  mov     [rsp+0F0h+dwCreationDisposition], 1
0x18004bbe1  mov     r9d, edi
0x18004bbe4  mov     r8d, r14d
0x18004bbe7  jmp     short loc_18004BC0A
0x18004bbe9  mov     [rsp+0F0h+dwCreationDisposition], 4; enum _ACCESS_MODE
0x18004bbf1  xor     r9d, r9d; unsigned int
0x18004bbf4  xor     r8d, r8d; unsigned int
0x18004bbf7  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x18004bbfc  mov     [rsp+0F0h+dwCreationDisposition], 4; enum _ACCESS_MODE
0x18004bc04  xor     r9d, r9d; unsigned int
0x18004bc07  xor     r8d, r8d; unsigned int
0x18004bc0a  mov     rdx, [rbp+4Fh+hMem]; void *
0x18004bc0e  lea     rcx, [rbp+4Fh+pDacl]; this
0x18004bc12  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x18004bc17  mov     rax, [rbp+4Fh+pDacl]
0x18004bc1b  mov     [rsp+0F0h+hTemplateFile], 0; pSacl
0x18004bc24  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; pDacl
0x18004bc29  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; unsigned int
0x18004bc32  xor     r9d, r9d; psidOwner
0x18004bc35  lea     edx, [r9+1]; ObjectType
0x18004bc39  lea     r8d, [r9+4]; SecurityInfo
0x18004bc3d  mov     rcx, rbx; handle
0x18004bc40  call    cs:__imp_SetSecurityInfo
0x18004bc47  nop     dword ptr [rax+rax+00h]
0x18004bc4c  mov     rcx, [rbp+57h]; this
0x18004bc50  test    eax, eax
0x18004bc52  jnz     loc_18004BCE0
0x18004bc58  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18004bc5c  test    rcx, rcx
0x18004bc5f  jz      short loc_18004BC6D
0x18004bc61  call    cs:__imp_LocalFree
0x18004bc68  nop     dword ptr [rax+rax+00h]
0x18004bc6d  lea     rcx, [rbp+4Fh+var_70]
0x18004bc71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004bc76  lea     rcx, [rbp+4Fh+var_90]
0x18004bc7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004bc7f  nop
0x18004bc80  mov     rcx, [rbp+4Fh+pDacl]; hMem
0x18004bc84  test    rcx, rcx
0x18004bc87  jz      short loc_18004BC96
0x18004bc89  call    cs:__imp_LocalFree
0x18004bc90  nop     dword ptr [rax+rax+00h]
0x18004bc95  nop
0x18004bc96  mov     rcx, [rbp+4Fh+var_40]; hMem
0x18004bc9a  test    rcx, rcx
0x18004bc9d  jz      short loc_18004BCAC
0x18004bc9f  call    cs:__imp_LocalFree
0x18004bca6  nop     dword ptr [rax+rax+00h]
0x18004bcab  nop
0x18004bcac  lea     rax, [rbx-1]
0x18004bcb0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004bcb4  ja      short loc_18004BCC5
0x18004bcb6  mov     rcx, rbx; hObject
0x18004bcb9  call    cs:__imp_CloseHandle
0x18004bcc0  nop     dword ptr [rax+rax+00h]
0x18004bcc5  mov     rcx, [rbp+4Fh+var_30]
0x18004bcc9  xor     rcx, rsp; StackCookie
0x18004bccc  call    __security_check_cookie
0x18004bcd1  add     rsp, 0D0h
0x18004bcd8  pop     r14
0x18004bcda  pop     rdi
0x18004bcdb  pop     rsi
0x18004bcdc  pop     rbx
0x18004bcdd  pop     rbp
0x18004bcde  retn
0x18004bce0  mov     r9d, eax; char *
0x18004bce3  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\dll\\lib\\inc\\Ac"...
0x18004bcea  mov     edx, 47h ; 'G'; void *
0x18004bcef  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004bcf5  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\dll\\lib\\inc\\Ac"...
0x18004bcfc  mov     edx, 24h ; '$'; void *
0x18004bd01  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004bd07  mov     r9d, eax; char *
0x18004bd0a  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\dll\\lib\\inc\\Ac"...
0x18004bd11  mov     edx, 2Fh ; '/'; void *
0x18004bd16  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
