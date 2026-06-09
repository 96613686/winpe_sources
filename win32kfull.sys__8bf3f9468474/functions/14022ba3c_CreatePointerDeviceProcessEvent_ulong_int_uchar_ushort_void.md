# CreatePointerDeviceProcessEvent(ulong,int,uchar,ushort *,void * *)

- ea: `0x14022ba3c`
- end: `0x14022bd7e`
- name: `?CreatePointerDeviceProcessEvent@@YAHKHEPEAGPEAPEAX@Z`
- size: `834`
- prototype: `__int64 __usercall@<rax>(ACCESS_MASK AccessMask@<ecx>, int@<edx>, unsigned __int8@<r8b>, unsigned __int16 *@<r9>, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14022b9cc`

## callees

- `0x140077cc8`
- `0x14022ba3c`
- `0x14022bf60`
- `0x14022bf98`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x14022bd67`
- `ntoskrnl!ZwCreateEvent` at `0x14022bd67`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14022bca6`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14022bca6`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14022bc8a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14022bc8a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14022bc50`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14022bc6f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14022bc50`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14022bc6f`
- `ntoskrnl!RtlCreateAcl` at `0x14022bc28`
- `ntoskrnl!RtlCreateAcl` at `0x14022bc28`
- `ntoskrnl!RtlLengthSid` at `0x14022bbd0`
- `ntoskrnl!RtlLengthSid` at `0x14022bbe1`
- `ntoskrnl!RtlLengthSid` at `0x14022bbd0`
- `ntoskrnl!RtlLengthSid` at `0x14022bbe1`
- `ntoskrnl!RtlInitializeSid` at `0x14022bb3c`
- `ntoskrnl!RtlInitializeSid` at `0x14022bbb9`
- `ntoskrnl!RtlInitializeSid` at `0x14022bb3c`
- `ntoskrnl!RtlInitializeSid` at `0x14022bbb9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14022bb20`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14022bba0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14022bb20`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14022bba0`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14022bac2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14022bb77`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14022bac2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14022bb77`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022bd0f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022bd0f`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14022bad7`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14022bb87`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14022bad7`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14022bb87`
- `win32kbase!Win32AllocPoolZInit` at `0x14022bc00`
- `win32kbase!Win32AllocPoolZInit` at `0x14022bc00`
- `win32kbase!Win32FreePool` at `0x14022bb4f`
- `win32kbase!Win32FreePool` at `0x14022bb63`
- `win32kbase!Win32FreePool` at `0x14022bcc2`
- `win32kbase!Win32FreePool` at `0x14022bb4f`
- `win32kbase!Win32FreePool` at `0x14022bb63`
- `win32kbase!Win32FreePool` at `0x14022bcc2`

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
0x14022ba3c  mov     [rsp-8+arg_8], rbx
0x14022ba41  push    rbp
0x14022ba42  push    rsi
0x14022ba43  push    rdi
0x14022ba44  push    r12
0x14022ba46  push    r13
0x14022ba48  push    r14
0x14022ba4a  push    r15
0x14022ba4c  lea     rbp, [rsp-1B0h]
0x14022ba54  sub     rsp, 2B0h
0x14022ba5b  mov     rax, cs:__security_cookie
0x14022ba62  xor     rax, rsp
0x14022ba65  mov     [rbp+1E0h+var_40], rax
0x14022ba6c  mov     rax, [rbp+1E0h+arg_20]
0x14022ba73  xorps   xmm0, xmm0
0x14022ba76  xor     r12d, r12d
0x14022ba79  mov     [rsp+2E0h+var_2A8], r9
0x14022ba7e  mov     r13d, ecx
0x14022ba81  mov     [rsp+2E0h+var_2B0], r8b
0x14022ba86  mov     [rsp+2E0h+var_2AC], edx
0x14022ba8a  mov     edi, r12d
0x14022ba8d  mov     [rsp+2E0h+EventHandle], rax
0x14022ba92  lea     r14d, [r12+1]
0x14022ba97  mov     dword ptr [rbp+1E0h+IdentifierAuthority.Value], r12d
0x14022ba9b  mov     ecx, r14d; SubAuthorityCount
0x14022ba9e  mov     word ptr [rbp+1E0h+IdentifierAuthority.Value+4], 500h
0x14022baa4  mov     dword ptr [rbp+1E0h+var_250.Value], r12d
0x14022baa8  mov     word ptr [rbp+1E0h+var_250.Value+4], 100h
0x14022baae  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x14022bab3  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x14022bab8  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14022babd  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm0
0x14022bac2  call    cs:__imp_RtlLengthRequiredSid
0x14022bac9  nop     dword ptr [rax+rax+00h]
0x14022bace  mov     esi, 65737355h
0x14022bad3  mov     ecx, eax
0x14022bad5  mov     edx, esi
0x14022bad7  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x14022bade  nop     dword ptr [rax+rax+00h]
0x14022bae3  mov     r15, rax
0x14022bae6  test    rax, rax
0x14022bae9  jnz     short loc_14022BB18
0x14022baeb  mov     eax, edi
0x14022baed  mov     rcx, [rbp+1E0h+var_40]
0x14022baf4  xor     rcx, rsp; StackCookie
0x14022baf7  call    __security_check_cookie
0x14022bafc  mov     rbx, [rsp+2E0h+arg_8]
0x14022bb04  add     rsp, 2B0h
0x14022bb0b  pop     r15
0x14022bb0d  pop     r14
0x14022bb0f  pop     r13
0x14022bb11  pop     r12
0x14022bb13  pop     rdi
0x14022bb14  pop     rsi
0x14022bb15  pop     rbp
0x14022bb16  retn
0x14022bb18  xor     edx, edx; SubAuthority
0x14022bb1a  mov     rcx, r15; Sid
0x14022bb1d  mov     rbx, r12
0x14022bb20  call    cs:__imp_RtlSubAuthoritySid
0x14022bb27  nop     dword ptr [rax+rax+00h]
0x14022bb2c  mov     r8b, r14b; SubAuthorityCount
0x14022bb2f  lea     rdx, [rbp+1E0h+IdentifierAuthority]; IdentifierAuthority
0x14022bb33  mov     rcx, r15; Sid
0x14022bb36  mov     dword ptr [rax], 12h
0x14022bb3c  call    cs:__imp_RtlInitializeSid
0x14022bb43  nop     dword ptr [rax+rax+00h]
0x14022bb48  test    eax, eax
0x14022bb4a  jns     short loc_14022BB74
0x14022bb4c  mov     rcx, r15
0x14022bb4f  call    cs:__imp_Win32FreePool
0x14022bb56  nop     dword ptr [rax+rax+00h]
0x14022bb5b  test    rbx, rbx
0x14022bb5e  jz      short loc_14022BAEB
0x14022bb60  mov     rcx, rbx
0x14022bb63  call    cs:__imp_Win32FreePool
0x14022bb6a  nop     dword ptr [rax+rax+00h]
0x14022bb6f  jmp     loc_14022BAEB
0x14022bb74  mov     ecx, r14d; SubAuthorityCount
0x14022bb77  call    cs:__imp_RtlLengthRequiredSid
0x14022bb7e  nop     dword ptr [rax+rax+00h]
0x14022bb83  mov     ecx, eax
0x14022bb85  mov     edx, esi
0x14022bb87  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x14022bb8e  nop     dword ptr [rax+rax+00h]
0x14022bb93  mov     rsi, rax
0x14022bb96  test    rax, rax
0x14022bb99  jz      short loc_14022BB4C
0x14022bb9b  xor     edx, edx; SubAuthority
0x14022bb9d  mov     rcx, rax; Sid
0x14022bba0  call    cs:__imp_RtlSubAuthoritySid
0x14022bba7  nop     dword ptr [rax+rax+00h]
0x14022bbac  mov     r8b, r14b; SubAuthorityCount
0x14022bbaf  lea     rdx, [rbp+1E0h+var_250]; IdentifierAuthority
0x14022bbb3  mov     rcx, rsi; Sid
0x14022bbb6  mov     [rax], r12d
0x14022bbb9  call    cs:__imp_RtlInitializeSid
0x14022bbc0  nop     dword ptr [rax+rax+00h]
0x14022bbc5  test    eax, eax
0x14022bbc7  js      loc_14022BCBF
0x14022bbcd  mov     rcx, r15; Sid
0x14022bbd0  call    cs:__imp_RtlLengthSid
0x14022bbd7  nop     dword ptr [rax+rax+00h]
0x14022bbdc  mov     rcx, rsi; Sid
0x14022bbdf  mov     ebx, eax
0x14022bbe1  call    cs:__imp_RtlLengthSid
0x14022bbe8  nop     dword ptr [rax+rax+00h]
0x14022bbed  mov     edx, 78707355h
0x14022bbf2  lea     r12d, [rax+28h]
0x14022bbf6  add     r12d, ebx
0x14022bbf9  mov     ecx, r12d
0x14022bbfc  add     rcx, 28h ; '('
0x14022bc00  call    cs:__imp_Win32AllocPoolZInit
0x14022bc07  nop     dword ptr [rax+rax+00h]
0x14022bc0c  mov     rbx, rax
0x14022bc0f  test    rax, rax
0x14022bc12  jz      loc_14022BCBF
0x14022bc18  lea     r14, [rax+28h]
0x14022bc1c  mov     r8d, 2; AclRevision
0x14022bc22  mov     rcx, r14; Acl
0x14022bc25  mov     edx, r12d; AclLength
0x14022bc28  call    cs:__imp_RtlCreateAcl
0x14022bc2f  nop     dword ptr [rax+rax+00h]
0x14022bc34  xor     r12d, r12d
0x14022bc37  test    eax, eax
0x14022bc39  js      loc_14022BCBF
0x14022bc3f  mov     r8d, r13d; AccessMask
0x14022bc42  mov     r9, rsi; Sid
0x14022bc45  lea     r13d, [r12+2]
0x14022bc4a  mov     rcx, r14; Acl
0x14022bc4d  mov     edx, r13d; AceRevision
0x14022bc50  call    cs:__imp_RtlAddAccessAllowedAce
0x14022bc57  nop     dword ptr [rax+rax+00h]
0x14022bc5c  test    eax, eax
0x14022bc5e  js      short loc_14022BCBF
0x14022bc60  mov     r9, r15; Sid
0x14022bc63  mov     r8d, 1F0003h; AccessMask
0x14022bc69  mov     edx, r13d; AceRevision
0x14022bc6c  mov     rcx, r14; Acl
0x14022bc6f  call    cs:__imp_RtlAddAccessAllowedAce
0x14022bc76  nop     dword ptr [rax+rax+00h]
0x14022bc7b  test    eax, eax
0x14022bc7d  js      short loc_14022BCBF
0x14022bc7f  lea     r13d, [r12+1]
0x14022bc84  mov     rcx, rbx; SecurityDescriptor
0x14022bc87  mov     edx, r13d; Revision
0x14022bc8a  call    cs:__imp_RtlCreateSecurityDescriptor
0x14022bc91  nop     dword ptr [rax+rax+00h]
0x14022bc96  test    eax, eax
0x14022bc98  js      short loc_14022BCBF
0x14022bc9a  xor     r9d, r9d; DaclDefaulted
0x14022bc9d  mov     r8, r14; Dacl
0x14022bca0  mov     dl, r13b; DaclPresent
0x14022bca3  mov     rcx, rbx; SecurityDescriptor
0x14022bca6  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14022bcad  nop     dword ptr [rax+rax+00h]
0x14022bcb2  test    eax, eax
0x14022bcb4  js      short loc_14022BCBF
0x14022bcb6  call    IsCurrentSessionHostServiceSession
0x14022bcbb  test    eax, eax
0x14022bcbd  jz      short loc_14022BCD3
0x14022bcbf  mov     rcx, rsi
0x14022bcc2  call    cs:__imp_Win32FreePool
0x14022bcc9  nop     dword ptr [rax+rax+00h]
0x14022bcce  jmp     loc_14022BB4C
0x14022bcd3  call    W32GetCurrentWin32kSessionId
0x14022bcd8  mov     rcx, [rsp+2E0h+var_2A8]
0x14022bcdd  lea     r9, aSessions; "\\Sessions"
0x14022bce4  mov     [rsp+2E0h+var_2B8], rcx
0x14022bce9  lea     r8, aWsLdBasenamedo; "%ws\\%ld\\BaseNamedObjects\\%ws"
0x14022bcf0  lea     rcx, [rbp+1E0h+SourceString]; unsigned __int16 *
0x14022bcf4  mov     dword ptr [rsp+2E0h+InitialState], eax
0x14022bcf8  mov     edx, 100h; unsigned __int64
0x14022bcfd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14022bd02  test    eax, eax
0x14022bd04  js      short loc_14022BCBF
0x14022bd06  lea     rdx, [rbp+1E0h+SourceString]; SourceString
0x14022bd0a  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x14022bd0f  call    cs:__imp_RtlInitUnicodeString
0x14022bd16  nop     dword ptr [rax+rax+00h]
0x14022bd1b  cmp     [rsp+2E0h+var_2AC], r12d
0x14022bd20  lea     rax, [rsp+2E0h+DestinationString]
0x14022bd25  mov     rcx, [rsp+2E0h+EventHandle]; EventHandle
0x14022bd2a  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x14022bd2f  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x14022bd34  mov     r9d, r12d
0x14022bd37  mov     al, [rsp+2E0h+var_2B0]
0x14022bd3b  setz    r9b; EventType
0x14022bd3f  mov     edx, 1F0003h; DesiredAccess
0x14022bd44  mov     [rsp+2E0h+InitialState], al; InitialState
0x14022bd48  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x14022bd50  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r12
0x14022bd55  mov     [rsp+2E0h+ObjectAttributes.Attributes], 0C0h
0x14022bd5d  mov     [rsp+2E0h+ObjectAttributes.SecurityDescriptor], rbx
0x14022bd62  mov     [rsp+2E0h+ObjectAttributes.SecurityQualityOfService], r12
0x14022bd67  call    cs:__imp_ZwCreateEvent
0x14022bd6e  nop     dword ptr [rax+rax+00h]
0x14022bd73  test    eax, eax
0x14022bd75  cmovns  edi, r13d
0x14022bd79  jmp     loc_14022BCBF
```
