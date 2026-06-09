# CreatePointerDeviceProcessEvent(ulong,int,uchar,ushort *,void * *)

- ea: `0x14022ca2c`
- end: `0x14022cd6e`
- name: `?CreatePointerDeviceProcessEvent@@YAHKHEPEAGPEAPEAX@Z`
- size: `834`
- prototype: `_BOOL8 __fastcall(ACCESS_MASK AccessMask, int, BOOLEAN, unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14022c9bc`

## callees

- `0x1400a4a38`
- `0x14022ca2c`
- `0x14022cf50`
- `0x14022cf88`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x14022cd57`
- `ntoskrnl!ZwCreateEvent` at `0x14022cd57`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14022cc96`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14022cc96`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14022cc7a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14022cc7a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14022cc40`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14022cc5f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14022cc40`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14022cc5f`
- `ntoskrnl!RtlCreateAcl` at `0x14022cc18`
- `ntoskrnl!RtlCreateAcl` at `0x14022cc18`
- `ntoskrnl!RtlLengthSid` at `0x14022cbc0`
- `ntoskrnl!RtlLengthSid` at `0x14022cbd1`
- `ntoskrnl!RtlLengthSid` at `0x14022cbc0`
- `ntoskrnl!RtlLengthSid` at `0x14022cbd1`
- `ntoskrnl!RtlInitializeSid` at `0x14022cb2c`
- `ntoskrnl!RtlInitializeSid` at `0x14022cba9`
- `ntoskrnl!RtlInitializeSid` at `0x14022cb2c`
- `ntoskrnl!RtlInitializeSid` at `0x14022cba9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14022cb10`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14022cb90`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14022cb10`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14022cb90`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14022cab2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14022cb67`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14022cab2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14022cb67`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022ccff`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022ccff`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14022cac7`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14022cb77`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14022cac7`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14022cb77`
- `win32kbase!Win32AllocPoolZInit` at `0x14022cbf0`
- `win32kbase!Win32AllocPoolZInit` at `0x14022cbf0`
- `win32kbase!Win32FreePool` at `0x14022cb3f`
- `win32kbase!Win32FreePool` at `0x14022cb53`
- `win32kbase!Win32FreePool` at `0x14022ccb2`
- `win32kbase!Win32FreePool` at `0x14022cb3f`
- `win32kbase!Win32FreePool` at `0x14022cb53`
- `win32kbase!Win32FreePool` at `0x14022ccb2`

## pseudocode

```c
_BOOL8 __fastcall CreatePointerDeviceProcessEvent(
        ACCESS_MASK AccessMask,
        int a2,
        BOOLEAN a3,
        unsigned __int16 *a4,
        void **a5)
{
  BOOL v6; // edi
  ULONG v7; // eax
  void *v8; // rax
  void *v9; // r15
  struct _ACL *v11; // rbx
  ULONG v12; // eax
  void *v13; // rax
  void *v14; // rsi
  ULONG v15; // ebx
  ULONG v16; // r12d
  struct _ACL *v17; // rax
  struct _ACL *v18; // r14
  BOOLEAN InitialState[4]; // [rsp+20h] [rbp-E0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+88h] [rbp-78h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v26; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SourceString[256]; // [rsp+A0h] [rbp-60h] BYREF

  v6 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v26.Value = 0;
  *(_WORD *)&v26.Value[4] = 256;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v7 = RtlLengthRequiredSid(1u);
  v8 = (void *)Win32AllocPoolWithQuotaZInit(v7, 1702064981);
  v9 = v8;
  if ( v8 )
  {
    v11 = 0;
    *RtlSubAuthoritySid(v8, 0) = 18;
    if ( RtlInitializeSid(v9, &IdentifierAuthority, 1u) >= 0 )
    {
      v12 = RtlLengthRequiredSid(1u);
      v13 = (void *)Win32AllocPoolWithQuotaZInit(v12, 1702064981);
      v14 = v13;
      if ( v13 )
      {
        *RtlSubAuthoritySid(v13, 0) = 0;
        if ( RtlInitializeSid(v14, &v26, 1u) >= 0 )
        {
          v15 = RtlLengthSid(v9);
          v16 = v15 + RtlLengthSid(v14) + 40;
          v17 = (struct _ACL *)Win32AllocPoolZInit(v16 + 40LL, 2020635477);
          v11 = v17;
          if ( v17 )
          {
            v18 = v17 + 5;
            if ( RtlCreateAcl(v17 + 5, v16, 2u) >= 0
              && RtlAddAccessAllowedAce(v18, 2u, AccessMask, v14) >= 0
              && RtlAddAccessAllowedAce(v18, 2u, 0x1F0003u, v9) >= 0
              && RtlCreateSecurityDescriptor(v11, 1u) >= 0
              && RtlSetDaclSecurityDescriptor(v11, 1u, v18, 0) >= 0
              && !(unsigned int)IsCurrentSessionHostServiceSession() )
            {
              *(_DWORD *)InitialState = W32GetCurrentWin32kSessionId();
              if ( (int)StringCchPrintfW(
                          SourceString,
                          0x100u,
                          L"%ws\\%ld\\BaseNamedObjects\\%ws",
                          L"\\Sessions",
                          *(_DWORD *)InitialState,
                          a4) >= 0 )
              {
                RtlInitUnicodeString(&DestinationString, SourceString);
                ObjectAttributes.ObjectName = &DestinationString;
                ObjectAttributes.Length = 48;
                ObjectAttributes.RootDirectory = 0;
                ObjectAttributes.Attributes = 192;
                ObjectAttributes.SecurityDescriptor = v11;
                ObjectAttributes.SecurityQualityOfService = 0;
                v6 = ZwCreateEvent(a5, 0x1F0003u, &ObjectAttributes, (EVENT_TYPE)(a2 == 0), a3) >= 0;
              }
            }
          }
        }
        Win32FreePool(v14);
      }
    }
    Win32FreePool(v9);
    if ( v11 )
      Win32FreePool(v11);
  }
  return v6;
}

```

## disassembly

```asm
0x14022ca2c  mov     [rsp-8+arg_8], rbx
0x14022ca31  push    rbp
0x14022ca32  push    rsi
0x14022ca33  push    rdi
0x14022ca34  push    r12
0x14022ca36  push    r13
0x14022ca38  push    r14
0x14022ca3a  push    r15
0x14022ca3c  lea     rbp, [rsp-1B0h]
0x14022ca44  sub     rsp, 2B0h
0x14022ca4b  mov     rax, cs:__security_cookie
0x14022ca52  xor     rax, rsp
0x14022ca55  mov     [rbp+1E0h+var_40], rax
0x14022ca5c  mov     rax, [rbp+1E0h+arg_20]
0x14022ca63  xorps   xmm0, xmm0
0x14022ca66  xor     r12d, r12d
0x14022ca69  mov     [rsp+2E0h+var_2A8], r9
0x14022ca6e  mov     r13d, ecx
0x14022ca71  mov     [rsp+2E0h+var_2B0], r8b
0x14022ca76  mov     [rsp+2E0h+var_2AC], edx
0x14022ca7a  mov     edi, r12d
0x14022ca7d  mov     [rsp+2E0h+EventHandle], rax
0x14022ca82  lea     r14d, [r12+1]
0x14022ca87  mov     dword ptr [rbp+1E0h+IdentifierAuthority.Value], r12d
0x14022ca8b  mov     ecx, r14d; SubAuthorityCount
0x14022ca8e  mov     word ptr [rbp+1E0h+IdentifierAuthority.Value+4], 500h
0x14022ca94  mov     dword ptr [rbp+1E0h+var_250.Value], r12d
0x14022ca98  mov     word ptr [rbp+1E0h+var_250.Value+4], 100h
0x14022ca9e  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x14022caa3  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x14022caa8  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14022caad  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm0
0x14022cab2  call    cs:__imp_RtlLengthRequiredSid
0x14022cab9  nop     dword ptr [rax+rax+00h]
0x14022cabe  mov     esi, 65737355h
0x14022cac3  mov     ecx, eax
0x14022cac5  mov     edx, esi
0x14022cac7  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x14022cace  nop     dword ptr [rax+rax+00h]
0x14022cad3  mov     r15, rax
0x14022cad6  test    rax, rax
0x14022cad9  jnz     short loc_14022CB08
0x14022cadb  mov     eax, edi
0x14022cadd  mov     rcx, [rbp+1E0h+var_40]
0x14022cae4  xor     rcx, rsp; StackCookie
0x14022cae7  call    __security_check_cookie
0x14022caec  mov     rbx, [rsp+2E0h+arg_8]
0x14022caf4  add     rsp, 2B0h
0x14022cafb  pop     r15
0x14022cafd  pop     r14
0x14022caff  pop     r13
0x14022cb01  pop     r12
0x14022cb03  pop     rdi
0x14022cb04  pop     rsi
0x14022cb05  pop     rbp
0x14022cb06  retn
0x14022cb08  xor     edx, edx; SubAuthority
0x14022cb0a  mov     rcx, r15; Sid
0x14022cb0d  mov     rbx, r12
0x14022cb10  call    cs:__imp_RtlSubAuthoritySid
0x14022cb17  nop     dword ptr [rax+rax+00h]
0x14022cb1c  mov     r8b, r14b; SubAuthorityCount
0x14022cb1f  lea     rdx, [rbp+1E0h+IdentifierAuthority]; IdentifierAuthority
0x14022cb23  mov     rcx, r15; Sid
0x14022cb26  mov     dword ptr [rax], 12h
0x14022cb2c  call    cs:__imp_RtlInitializeSid
0x14022cb33  nop     dword ptr [rax+rax+00h]
0x14022cb38  test    eax, eax
0x14022cb3a  jns     short loc_14022CB64
0x14022cb3c  mov     rcx, r15
0x14022cb3f  call    cs:__imp_Win32FreePool
0x14022cb46  nop     dword ptr [rax+rax+00h]
0x14022cb4b  test    rbx, rbx
0x14022cb4e  jz      short loc_14022CADB
0x14022cb50  mov     rcx, rbx
0x14022cb53  call    cs:__imp_Win32FreePool
0x14022cb5a  nop     dword ptr [rax+rax+00h]
0x14022cb5f  jmp     loc_14022CADB
0x14022cb64  mov     ecx, r14d; SubAuthorityCount
0x14022cb67  call    cs:__imp_RtlLengthRequiredSid
0x14022cb6e  nop     dword ptr [rax+rax+00h]
0x14022cb73  mov     ecx, eax
0x14022cb75  mov     edx, esi
0x14022cb77  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x14022cb7e  nop     dword ptr [rax+rax+00h]
0x14022cb83  mov     rsi, rax
0x14022cb86  test    rax, rax
0x14022cb89  jz      short loc_14022CB3C
0x14022cb8b  xor     edx, edx; SubAuthority
0x14022cb8d  mov     rcx, rax; Sid
0x14022cb90  call    cs:__imp_RtlSubAuthoritySid
0x14022cb97  nop     dword ptr [rax+rax+00h]
0x14022cb9c  mov     r8b, r14b; SubAuthorityCount
0x14022cb9f  lea     rdx, [rbp+1E0h+var_250]; IdentifierAuthority
0x14022cba3  mov     rcx, rsi; Sid
0x14022cba6  mov     [rax], r12d
0x14022cba9  call    cs:__imp_RtlInitializeSid
0x14022cbb0  nop     dword ptr [rax+rax+00h]
0x14022cbb5  test    eax, eax
0x14022cbb7  js      loc_14022CCAF
0x14022cbbd  mov     rcx, r15; Sid
0x14022cbc0  call    cs:__imp_RtlLengthSid
0x14022cbc7  nop     dword ptr [rax+rax+00h]
0x14022cbcc  mov     rcx, rsi; Sid
0x14022cbcf  mov     ebx, eax
0x14022cbd1  call    cs:__imp_RtlLengthSid
0x14022cbd8  nop     dword ptr [rax+rax+00h]
0x14022cbdd  mov     edx, 78707355h
0x14022cbe2  lea     r12d, [rax+28h]
0x14022cbe6  add     r12d, ebx
0x14022cbe9  mov     ecx, r12d
0x14022cbec  add     rcx, 28h ; '('
0x14022cbf0  call    cs:__imp_Win32AllocPoolZInit
0x14022cbf7  nop     dword ptr [rax+rax+00h]
0x14022cbfc  mov     rbx, rax
0x14022cbff  test    rax, rax
0x14022cc02  jz      loc_14022CCAF
0x14022cc08  lea     r14, [rax+28h]
0x14022cc0c  mov     r8d, 2; AclRevision
0x14022cc12  mov     rcx, r14; Acl
0x14022cc15  mov     edx, r12d; AclLength
0x14022cc18  call    cs:__imp_RtlCreateAcl
0x14022cc1f  nop     dword ptr [rax+rax+00h]
0x14022cc24  xor     r12d, r12d
0x14022cc27  test    eax, eax
0x14022cc29  js      loc_14022CCAF
0x14022cc2f  mov     r8d, r13d; AccessMask
0x14022cc32  mov     r9, rsi; Sid
0x14022cc35  lea     r13d, [r12+2]
0x14022cc3a  mov     rcx, r14; Acl
0x14022cc3d  mov     edx, r13d; AceRevision
0x14022cc40  call    cs:__imp_RtlAddAccessAllowedAce
0x14022cc47  nop     dword ptr [rax+rax+00h]
0x14022cc4c  test    eax, eax
0x14022cc4e  js      short loc_14022CCAF
0x14022cc50  mov     r9, r15; Sid
0x14022cc53  mov     r8d, 1F0003h; AccessMask
0x14022cc59  mov     edx, r13d; AceRevision
0x14022cc5c  mov     rcx, r14; Acl
0x14022cc5f  call    cs:__imp_RtlAddAccessAllowedAce
0x14022cc66  nop     dword ptr [rax+rax+00h]
0x14022cc6b  test    eax, eax
0x14022cc6d  js      short loc_14022CCAF
0x14022cc6f  lea     r13d, [r12+1]
0x14022cc74  mov     rcx, rbx; SecurityDescriptor
0x14022cc77  mov     edx, r13d; Revision
0x14022cc7a  call    cs:__imp_RtlCreateSecurityDescriptor
0x14022cc81  nop     dword ptr [rax+rax+00h]
0x14022cc86  test    eax, eax
0x14022cc88  js      short loc_14022CCAF
0x14022cc8a  xor     r9d, r9d; DaclDefaulted
0x14022cc8d  mov     r8, r14; Dacl
0x14022cc90  mov     dl, r13b; DaclPresent
0x14022cc93  mov     rcx, rbx; SecurityDescriptor
0x14022cc96  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14022cc9d  nop     dword ptr [rax+rax+00h]
0x14022cca2  test    eax, eax
0x14022cca4  js      short loc_14022CCAF
0x14022cca6  call    IsCurrentSessionHostServiceSession
0x14022ccab  test    eax, eax
0x14022ccad  jz      short loc_14022CCC3
0x14022ccaf  mov     rcx, rsi
0x14022ccb2  call    cs:__imp_Win32FreePool
0x14022ccb9  nop     dword ptr [rax+rax+00h]
0x14022ccbe  jmp     loc_14022CB3C
0x14022ccc3  call    W32GetCurrentWin32kSessionId
0x14022ccc8  mov     rcx, [rsp+2E0h+var_2A8]
0x14022cccd  lea     r9, aSessions; "\\Sessions"
0x14022ccd4  mov     [rsp+2E0h+var_2B8], rcx
0x14022ccd9  lea     r8, aWsLdBasenamedo; "%ws\\%ld\\BaseNamedObjects\\%ws"
0x14022cce0  lea     rcx, [rbp+1E0h+SourceString]; unsigned __int16 *
0x14022cce4  mov     dword ptr [rsp+2E0h+InitialState], eax
0x14022cce8  mov     edx, 100h; unsigned __int64
0x14022cced  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14022ccf2  test    eax, eax
0x14022ccf4  js      short loc_14022CCAF
0x14022ccf6  lea     rdx, [rbp+1E0h+SourceString]; SourceString
0x14022ccfa  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x14022ccff  call    cs:__imp_RtlInitUnicodeString
0x14022cd06  nop     dword ptr [rax+rax+00h]
0x14022cd0b  cmp     [rsp+2E0h+var_2AC], r12d
0x14022cd10  lea     rax, [rsp+2E0h+DestinationString]
0x14022cd15  mov     rcx, [rsp+2E0h+EventHandle]; EventHandle
0x14022cd1a  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x14022cd1f  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x14022cd24  mov     r9d, r12d
0x14022cd27  mov     al, [rsp+2E0h+var_2B0]
0x14022cd2b  setz    r9b; EventType
0x14022cd2f  mov     edx, 1F0003h; DesiredAccess
0x14022cd34  mov     [rsp+2E0h+InitialState], al; InitialState
0x14022cd38  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x14022cd40  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r12
0x14022cd45  mov     [rsp+2E0h+ObjectAttributes.Attributes], 0C0h
0x14022cd4d  mov     [rsp+2E0h+ObjectAttributes.SecurityDescriptor], rbx
0x14022cd52  mov     [rsp+2E0h+ObjectAttributes.SecurityQualityOfService], r12
0x14022cd57  call    cs:__imp_ZwCreateEvent
0x14022cd5e  nop     dword ptr [rax+rax+00h]
0x14022cd63  test    eax, eax
0x14022cd65  cmovns  edi, r13d
0x14022cd69  jmp     loc_14022CCAF
```
