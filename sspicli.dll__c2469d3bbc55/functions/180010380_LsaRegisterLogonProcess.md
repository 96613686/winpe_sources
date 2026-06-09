# LsaRegisterLogonProcess

- ea: `0x180010380`
- end: `0x1800104da`
- name: `LsaRegisterLogonProcess`
- size: `346`
- prototype: `NTSTATUS __stdcall(PLSA_STRING LogonProcessName, PHANDLE LsaHandle, PLSA_OPERATIONAL_MODE SecurityMode)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b940`
- `0x180010380`
- `0x180022047`
- `0x18002205f`
- `0x180022190`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180010471`
- `ntdll!NtWaitForSingleObject` at `0x180010471`
- `ntdll!NtClose` at `0x18001047e`
- `ntdll!NtClose` at `0x18001047e`
- `ntdll!RtlInitUnicodeString` at `0x1800103fd`
- `ntdll!RtlInitUnicodeString` at `0x1800103fd`
- `ntdll!NtOpenEvent` at `0x18001043a`
- `ntdll!NtOpenEvent` at `0x18001043a`

## string_xrefs

- `0x1800103f1`: `\SECURITY\LSA_AUTHENTICATION_INITIALIZED`

## pseudocode

```c
NTSTATUS __stdcall LsaRegisterLogonProcess(
        PLSA_STRING LogonProcessName,
        PHANDLE LsaHandle,
        PLSA_OPERATIONAL_MODE SecurityMode)
{
  NTSTATUS result; // eax
  int v7; // ebx
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE EventHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v12[128]; // [rsp+80h] [rbp-80h] BYREF

  EventHandle = 0;
  DestinationString = 0;
  v8 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(v12, 0, sizeof(v12));
  if ( LogonProcessName->Length > 0x7Fu )
    return -1073741562;
  RtlInitUnicodeString(&DestinationString, L"\\SECURITY\\LSA_AUTHENTICATION_INITIALIZED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes);
  if ( result >= 0 )
  {
    v7 = NtWaitForSingleObject(EventHandle, 1u, 0);
    NtClose(EventHandle);
    if ( v7 < 0 )
    {
      return v7;
    }
    else
    {
      if ( LogonProcessName->Length )
        memcpy_0(v12, LogonProcessName->Buffer, LogonProcessName->Length);
      result = CreateRpcConnection((__int64)v12, 0, (__int64)LsaHandle, (__int64)&v8, (__int64)SecurityMode);
      if ( result == -1073741727 )
        return -1073741759;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010380  mov     [rsp-8+arg_18], rbx
0x180010385  push    rbp
0x180010386  push    rsi
0x180010387  push    rdi
0x180010388  push    r14
0x18001038a  push    r15
0x18001038c  lea     rbp, [rsp-10h]
0x180010391  sub     rsp, 110h
0x180010398  mov     rax, cs:__security_cookie
0x18001039f  xor     rax, rsp
0x1800103a2  mov     [rbp+30h+var_30], rax
0x1800103a6  xorps   xmm1, xmm1
0x1800103a9  mov     r14, r8
0x1800103ac  mov     rsi, rdx
0x1800103af  mov     rdi, rcx
0x1800103b2  xorps   xmm0, xmm0
0x1800103b5  lea     rcx, [rbp+30h+var_B0]; void *
0x1800103b9  xor     r15d, r15d
0x1800103bc  xor     edx, edx; Val
0x1800103be  mov     r8d, 80h; Size
0x1800103c4  mov     [rsp+130h+EventHandle], r15
0x1800103c9  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x1800103ce  mov     [rsp+130h+var_100], r15d
0x1800103d3  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm1
0x1800103d8  movups  xmmword ptr [rsp+130h+ObjectAttributes.ObjectName], xmm1
0x1800103dd  movups  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800103e2  call    memset_0
0x1800103e7  cmp     word ptr [rdi], 7Fh
0x1800103eb  ja      loc_1800104C9
0x1800103f1  lea     rdx, aSecurityLsaAut; "\\SECURITY\\LSA_AUTHENTICATION_INITIALI"...
0x1800103f8  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x1800103fd  call    cs:__imp_RtlInitUnicodeString
0x180010403  lea     rax, [rsp+130h+DestinationString]
0x180010408  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x180010410  xorps   xmm0, xmm0
0x180010413  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x180010418  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x18001041d  mov     [rsp+130h+ObjectAttributes.RootDirectory], r15
0x180010422  mov     edx, 100000h; DesiredAccess
0x180010427  mov     [rsp+130h+ObjectAttributes.Attributes], 40h ; '@'
0x18001042f  lea     rcx, [rsp+130h+EventHandle]; EventHandle
0x180010434  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001043a  call    cs:__imp_NtOpenEvent
0x180010440  test    eax, eax
0x180010442  jns     short loc_180010467
0x180010444  mov     rcx, [rbp+30h+var_30]
0x180010448  xor     rcx, rsp; StackCookie
0x18001044b  call    __security_check_cookie
0x180010450  mov     rbx, [rsp+130h+arg_18]
0x180010458  add     rsp, 110h
0x18001045f  pop     r15
0x180010461  pop     r14
0x180010463  pop     rdi
0x180010464  pop     rsi
0x180010465  pop     rbp
0x180010466  retn
0x180010467  mov     rcx, [rsp+130h+EventHandle]; Handle
0x18001046c  xor     r8d, r8d; Timeout
0x18001046f  mov     dl, 1; Alertable
0x180010471  call    cs:__imp_NtWaitForSingleObject
0x180010477  mov     rcx, [rsp+130h+EventHandle]; Handle
0x18001047c  mov     ebx, eax
0x18001047e  call    cs:__imp_NtClose
0x180010484  test    ebx, ebx
0x180010486  js      short loc_1800104D3
0x180010488  cmp     [rdi], r15w
0x18001048c  jbe     short loc_18001049F
0x18001048e  movzx   r8d, word ptr [rdi]; Size
0x180010492  lea     rcx, [rbp+30h+var_B0]; void *
0x180010496  mov     rdx, [rdi+8]; Src
0x18001049a  call    memcpy_0
0x18001049f  lea     r9, [rsp+130h+var_100]
0x1800104a4  mov     [rsp+130h+var_110], r14
0x1800104a9  mov     r8, rsi
0x1800104ac  lea     rcx, [rbp+30h+var_B0]
0x1800104b0  xor     edx, edx
0x1800104b2  call    CreateRpcConnection
0x1800104b7  cmp     eax, 0C0000061h
0x1800104bc  mov     ecx, 0C0000041h
0x1800104c1  cmovz   eax, ecx
0x1800104c4  jmp     loc_180010444
0x1800104c9  mov     eax, 0C0000106h
0x1800104ce  jmp     loc_180010444
0x1800104d3  mov     eax, ebx
0x1800104d5  jmp     loc_180010444
```
