# SampRtlWellKnownPrivilegeCheck

- ea: `0x18001cc00`
- end: `0x18001ce3e`
- name: `SampRtlWellKnownPrivilegeCheck`
- size: `574`
- prototype: `__int64 __fastcall(char, int, struct _CLIENT_ID *)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180022188`
- `0x180025fe4`
- `0x180053408`
- `0x180056510`
- `0x180056c30`
- `0x1800573f0`
- `0x180061124`

## callees

- `0x18001cc00`
- `0x18001cfa0`
- `0x18001d0d0`
- `0x180027e24`
- `0x18002cd80`

## import_xrefs

- `ntdll!NtPrivilegedServiceAuditAlarm` at `0x18001cd83`
- `ntdll!NtPrivilegedServiceAuditAlarm` at `0x18001cd83`
- `ntdll!NtPrivilegeCheck` at `0x18001cd5e`
- `ntdll!NtPrivilegeCheck` at `0x18001cd5e`
- `ntdll!NtOpenProcessToken` at `0x18001cd27`
- `ntdll!NtOpenProcessToken` at `0x18001cd27`
- `ntdll!NtOpenThreadToken` at `0x18001ccf9`
- `ntdll!NtOpenThreadToken` at `0x18001ccf9`
- `ntdll!NtOpenThread` at `0x18001cccc`
- `ntdll!NtOpenThread` at `0x18001cccc`
- `ntdll!NtOpenProcess` at `0x18001cc9c`
- `ntdll!NtOpenProcess` at `0x18001cc9c`
- `ntdll!NtClose` at `0x18001cdb0`
- `ntdll!NtClose` at `0x18001cdc3`
- `ntdll!NtClose` at `0x18001cde2`
- `ntdll!NtClose` at `0x18001cdb0`
- `ntdll!NtClose` at `0x18001cdc3`
- `ntdll!NtClose` at `0x18001cde2`

## pseudocode

```c
__int64 __fastcall SampRtlWellKnownPrivilegeCheck(char a1, int a2, struct _CLIENT_ID *a3)
{
  LUID v3; // rsi
  NTSTATUS v5; // ebx
  __int64 v6; // rcx
  NTSTATUS v7; // eax
  unsigned __int8 Result[8]; // [rsp+30h] [rbp-39h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v11; // [rsp+40h] [rbp-29h] BYREF
  void *ProcessHandle; // [rsp+48h] [rbp-21h] BYREF
  void *ThreadHandle; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-11h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+88h] [rbp+1Fh] BYREF

  v3 = (LUID)a2;
  Result[0] = 0;
  ThreadHandle = 0;
  ProcessHandle = 0;
  TokenHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v11 = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  if ( !a1 || (v5 = SampImpersonateClient(&v11), v5 >= 0) )
  {
    if ( !a3 )
      goto LABEL_11;
    if ( a3->UniqueProcess == (HANDLE)-1LL )
    {
      ProcessHandle = (void *)-1LL;
    }
    else
    {
      v5 = NtOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, a3);
      if ( v5 < 0 )
        goto LABEL_20;
    }
    if ( a3->UniqueThread == (HANDLE)-2LL )
    {
LABEL_11:
      v6 = -2;
      ThreadHandle = (void *)-2LL;
    }
    else
    {
      v5 = NtOpenThread(&ThreadHandle, 0x40u, &ObjectAttributes, a3);
      if ( v5 < 0 )
        goto LABEL_20;
      v6 = (__int64)ThreadHandle;
    }
    v7 = NtOpenThreadToken((HANDLE)v6, 8u, 1u, &TokenHandle);
    v5 = v7;
    if ( v7 < 0 )
    {
      if ( v7 != -1073741700 )
        goto LABEL_20;
      if ( !ProcessHandle )
      {
        v5 = -1073741811;
        goto LABEL_20;
      }
      v5 = NtOpenProcessToken(ProcessHandle, 8u, &TokenHandle);
      if ( v5 < 0 )
        goto LABEL_20;
    }
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.Privilege[0].Luid = v3;
    RequiredPrivileges.Privilege[0].Attributes = 0;
    v5 = NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result);
    if ( v5 >= 0 )
    {
      NtPrivilegedServiceAuditAlarm(&SampSamSubsystem, &SampSamSubsystem, TokenHandle, &RequiredPrivileges, Result[0]);
      if ( !Result[0] )
        v5 = -1073741727;
    }
  }
LABEL_20:
  SampRevertToSelf(v11);
  if ( a3 && a3->UniqueProcess != (HANDLE)-1LL && ProcessHandle )
  {
    NtClose(ProcessHandle);
    ProcessHandle = 0;
  }
  if ( TokenHandle )
  {
    NtClose(TokenHandle);
    TokenHandle = 0;
  }
  if ( a3 && a3->UniqueThread != (HANDLE)-2LL && ThreadHandle )
  {
    NtClose(ThreadHandle);
    ThreadHandle = 0;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 147, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)v5, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001cc00  mov     [rsp-8+arg_0], rbx
0x18001cc05  mov     [rsp-8+arg_8], rsi
0x18001cc0a  push    rbp
0x18001cc0b  push    rdi
0x18001cc0c  push    r14
0x18001cc0e  lea     rbp, [rsp-47h]
0x18001cc13  sub     rsp, 0B0h
0x18001cc1a  mov     rax, cs:__security_cookie
0x18001cc21  xor     rax, rsp
0x18001cc24  mov     [rbp+57h+var_20], rax
0x18001cc28  xor     r14d, r14d
0x18001cc2b  movsxd  rsi, edx
0x18001cc2e  xor     eax, eax
0x18001cc30  mov     [rbp+57h+Result], r14b
0x18001cc34  mov     [rbp+57h+ThreadHandle], r14
0x18001cc38  xorps   xmm0, xmm0
0x18001cc3b  mov     [rbp+57h+ProcessHandle], r14
0x18001cc3f  mov     rdi, r8
0x18001cc42  mov     [rbp+57h+TokenHandle], r14
0x18001cc46  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001cc4e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r14
0x18001cc52  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x18001cc55  mov     [rbp+57h+var_80], r14d
0x18001cc59  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x18001cc5d  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x18001cc61  movups  xmmword ptr [rbp+57h+RequiredPrivileges.PrivilegeCount], xmm0
0x18001cc65  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001cc6a  test    cl, cl
0x18001cc6c  jz      short loc_18001CC81
0x18001cc6e  lea     rcx, [rbp+57h+var_80]
0x18001cc72  call    SampImpersonateClient
0x18001cc77  mov     ebx, eax
0x18001cc79  test    eax, eax
0x18001cc7b  js      loc_18001CD94
0x18001cc81  test    rdi, rdi
0x18001cc84  jz      short loc_18001CCE2
0x18001cc86  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18001cc8a  jz      short loc_18001CCAD
0x18001cc8c  mov     r9, rdi; ClientId
0x18001cc8f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001cc93  mov     edx, 400h; DesiredAccess
0x18001cc98  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x18001cc9c  call    cs:__imp_NtOpenProcess
0x18001cca2  mov     ebx, eax
0x18001cca4  test    eax, eax
0x18001cca6  jns     short loc_18001CCB5
0x18001cca8  jmp     loc_18001CD94
0x18001ccad  mov     [rbp+57h+ProcessHandle], 0FFFFFFFFFFFFFFFFh
0x18001ccb5  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFEh
0x18001ccba  jz      short loc_18001CCE2
0x18001ccbc  mov     r9, rdi; ClientId
0x18001ccbf  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001ccc3  mov     edx, 40h ; '@'; DesiredAccess
0x18001ccc8  lea     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x18001cccc  call    cs:__imp_NtOpenThread
0x18001ccd2  mov     ebx, eax
0x18001ccd4  test    eax, eax
0x18001ccd6  js      loc_18001CD94
0x18001ccdc  mov     rcx, [rbp+57h+ThreadHandle]
0x18001cce0  jmp     short loc_18001CCED
0x18001cce2  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18001cce9  mov     [rbp+57h+ThreadHandle], rcx
0x18001cced  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001ccf1  mov     r8b, 1; OpenAsSelf
0x18001ccf4  mov     edx, 8; DesiredAccess
0x18001ccf9  call    cs:__imp_NtOpenThreadToken
0x18001ccff  mov     ebx, eax
0x18001cd01  test    eax, eax
0x18001cd03  jns     short loc_18001CD33
0x18001cd05  cmp     eax, 0C000007Ch
0x18001cd0a  jnz     loc_18001CD94
0x18001cd10  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x18001cd14  test    rcx, rcx
0x18001cd17  jnz     short loc_18001CD1E
0x18001cd19  lea     ebx, [rax-6Fh]
0x18001cd1c  jmp     short loc_18001CD94
0x18001cd1e  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001cd22  mov     edx, 8; DesiredAccess
0x18001cd27  call    cs:__imp_NtOpenProcessToken
0x18001cd2d  mov     ebx, eax
0x18001cd2f  test    eax, eax
0x18001cd31  js      short loc_18001CD94
0x18001cd33  mov     rcx, rsi
0x18001cd36  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], 1
0x18001cd3d  shr     rcx, 20h
0x18001cd41  lea     r8, [rbp+57h+Result]; Result
0x18001cd45  mov     [rbp+57h+RequiredPrivileges.Privilege.Luid.HighPart], ecx
0x18001cd48  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x18001cd4c  mov     rcx, [rbp+57h+TokenHandle]; ClientToken
0x18001cd50  mov     [rbp+57h+RequiredPrivileges.Control], 1
0x18001cd57  mov     [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], esi
0x18001cd5a  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], r14d
0x18001cd5e  call    cs:__imp_NtPrivilegeCheck
0x18001cd64  mov     ebx, eax
0x18001cd66  test    eax, eax
0x18001cd68  js      short loc_18001CD94
0x18001cd6a  mov     al, [rbp+57h+Result]
0x18001cd6d  lea     rcx, ?SampSamSubsystem@@3U_UNICODE_STRING@@A; SubsystemName
0x18001cd74  mov     r8, [rbp+57h+TokenHandle]; ClientToken
0x18001cd78  lea     r9, [rbp+57h+RequiredPrivileges]; Privileges
0x18001cd7c  mov     rdx, rcx; ServiceName
0x18001cd7f  mov     [rsp+0C0h+AccessGranted], al; AccessGranted
0x18001cd83  call    cs:__imp_NtPrivilegedServiceAuditAlarm
0x18001cd89  cmp     [rbp+57h+Result], r14b
0x18001cd8d  jnz     short loc_18001CD94
0x18001cd8f  mov     ebx, 0C0000061h
0x18001cd94  mov     ecx, [rbp+57h+var_80]
0x18001cd97  call    SampRevertToSelf
0x18001cd9c  test    rdi, rdi
0x18001cd9f  jz      short loc_18001CDBA
0x18001cda1  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18001cda5  jz      short loc_18001CDBA
0x18001cda7  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x18001cdab  test    rcx, rcx
0x18001cdae  jz      short loc_18001CDBA
0x18001cdb0  call    cs:__imp_NtClose
0x18001cdb6  mov     [rbp+57h+ProcessHandle], r14
0x18001cdba  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18001cdbe  test    rcx, rcx
0x18001cdc1  jz      short loc_18001CDCD
0x18001cdc3  call    cs:__imp_NtClose
0x18001cdc9  mov     [rbp+57h+TokenHandle], r14
0x18001cdcd  test    rdi, rdi
0x18001cdd0  jz      short loc_18001CDEC
0x18001cdd2  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFEh
0x18001cdd7  jz      short loc_18001CDEC
0x18001cdd9  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x18001cddd  test    rcx, rcx
0x18001cde0  jz      short loc_18001CDEC
0x18001cde2  call    cs:__imp_NtClose
0x18001cde8  mov     [rbp+57h+ThreadHandle], r14
0x18001cdec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdf3  test    dword ptr [rcx+44h], 20000h
0x18001cdfa  jz      short loc_18001CE18
0x18001cdfc  mov     rcx, [rcx+38h]
0x18001ce00  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x18001ce07  mov     edx, 93h
0x18001ce0c  mov     dword ptr [rsp+0C0h+AccessGranted], ebx
0x18001ce10  mov     r9d, ebx
0x18001ce13  call    WPP_SF_Dd
0x18001ce18  mov     eax, ebx
0x18001ce1a  mov     rcx, [rbp+57h+var_20]
0x18001ce1e  xor     rcx, rsp; StackCookie
0x18001ce21  call    __security_check_cookie
0x18001ce26  lea     r11, [rsp+0C0h+var_10]
0x18001ce2e  mov     rbx, [r11+20h]
0x18001ce32  mov     rsi, [r11+28h]
0x18001ce36  mov     rsp, r11
0x18001ce39  pop     r14
0x18001ce3b  pop     rdi
0x18001ce3c  pop     rbp
0x18001ce3d  retn
```
