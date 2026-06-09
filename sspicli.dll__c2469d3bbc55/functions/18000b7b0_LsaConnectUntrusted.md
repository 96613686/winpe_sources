# LsaConnectUntrusted

- ea: `0x18000b7b0`
- end: `0x18000b93a`
- name: `LsaConnectUntrusted`
- size: `394`
- prototype: `NTSTATUS __stdcall(PHANDLE LsaHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b104`
- `0x1800197b0`

## callees

- `0x18000b7b0`
- `0x18000b940`

## import_xrefs

- `ntdll!NtOpenThreadTokenEx` at `0x18000b8bf`
- `ntdll!NtOpenThreadTokenEx` at `0x18000b8bf`
- `ntdll!NtWaitForSingleObject` at `0x18000b840`
- `ntdll!NtWaitForSingleObject` at `0x18000b840`
- `ntdll!NtClose` at `0x18000b84c`
- `ntdll!NtClose` at `0x18000b92f`
- `ntdll!NtClose` at `0x18000b84c`
- `ntdll!NtClose` at `0x18000b92f`
- `ntdll!RtlInitUnicodeString` at `0x18000b7f6`
- `ntdll!RtlInitUnicodeString` at `0x18000b7f6`
- `ntdll!NtOpenEvent` at `0x18000b82b`
- `ntdll!NtOpenEvent` at `0x18000b8fa`
- `ntdll!NtOpenEvent` at `0x18000b82b`
- `ntdll!NtOpenEvent` at `0x18000b8fa`
- `ntdll!NtSetInformationThread` at `0x18000b8e1`
- `ntdll!NtSetInformationThread` at `0x18000b925`
- `ntdll!NtSetInformationThread` at `0x18000b8e1`
- `ntdll!NtSetInformationThread` at `0x18000b925`

## string_xrefs

- `0x18000b7c5`: `\SECURITY\LSA_AUTHENTICATION_INITIALIZED`

## pseudocode

```c
NTSTATUS __stdcall LsaConnectUntrusted(PHANDLE LsaHandle)
{
  NTSTATUS v2; // eax
  NTSTATUS RpcConnection; // ebx
  HANDLE EventHandle; // [rsp+30h] [rbp-50h] BYREF
  __int64 ThreadInformation; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int v9; // [rsp+A8h] [rbp+28h] BYREF
  int v10; // [rsp+B0h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp+38h] BYREF

  EventHandle = 0;
  Handle = 0;
  DestinationString = 0;
  v10 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\SECURITY\\LSA_AUTHENTICATION_INITIALIZED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes);
  RpcConnection = v2;
  if ( v2 >= 0 )
    goto LABEL_2;
  ThreadInformation = 0;
  if ( v2 == -1073741659 || v2 == -1073741790 )
  {
    RpcConnection = NtOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000Cu, 1u, 0, &Handle);
    if ( RpcConnection >= 0 )
    {
      RpcConnection = NtSetInformationThread(
                        (HANDLE)0xFFFFFFFFFFFFFFFELL,
                        ThreadImpersonationToken,
                        &ThreadInformation,
                        8u);
      if ( RpcConnection < 0 )
      {
LABEL_13:
        NtClose(Handle);
        return RpcConnection;
      }
      RpcConnection = NtOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes);
      if ( RpcConnection >= 0 )
      {
LABEL_2:
        RpcConnection = NtWaitForSingleObject(EventHandle, 1u, 0);
        NtClose(EventHandle);
        if ( RpcConnection >= 0 )
          RpcConnection = CreateRpcConnection(0, 0, (__int64)LsaHandle, (__int64)&v10, (__int64)&v9);
      }
    }
  }
  if ( Handle )
  {
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &Handle, 8u);
    goto LABEL_13;
  }
  return RpcConnection;
}

```

## disassembly

```asm
0x18000b7b0  mov     [rsp-18h+arg_0], rbx
0x18000b7b5  push    rbp
0x18000b7b6  push    rsi
0x18000b7b7  push    rdi
0x18000b7b8  mov     rbp, rsp
0x18000b7bb  sub     rsp, 80h
0x18000b7c2  xorps   xmm1, xmm1
0x18000b7c5  lea     rdx, aSecurityLsaAut; "\\SECURITY\\LSA_AUTHENTICATION_INITIALI"...
0x18000b7cc  xor     esi, esi
0x18000b7ce  mov     rdi, rcx
0x18000b7d1  xorps   xmm0, xmm0
0x18000b7d4  mov     [rbp+EventHandle], rsi
0x18000b7d8  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000b7dc  mov     [rbp+Handle], rsi
0x18000b7e0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000b7e4  mov     [rbp+arg_10], esi
0x18000b7e7  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x18000b7eb  mov     [rbp+arg_8], esi
0x18000b7ee  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x18000b7f2  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x18000b7f6  call    cs:__imp_RtlInitUnicodeString
0x18000b7fc  lea     rax, [rbp+DestinationString]
0x18000b800  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000b807  xorps   xmm0, xmm0
0x18000b80a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000b80e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000b812  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18000b816  mov     edx, 100000h; DesiredAccess
0x18000b81b  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000b822  lea     rcx, [rbp+EventHandle]; EventHandle
0x18000b826  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b82b  call    cs:__imp_NtOpenEvent
0x18000b831  mov     ebx, eax
0x18000b833  test    eax, eax
0x18000b835  js      short loc_18000B892
0x18000b837  mov     rcx, [rbp+EventHandle]; Handle
0x18000b83b  xor     r8d, r8d; Timeout
0x18000b83e  mov     dl, 1; Alertable
0x18000b840  call    cs:__imp_NtWaitForSingleObject
0x18000b846  mov     rcx, [rbp+EventHandle]; Handle
0x18000b84a  mov     ebx, eax
0x18000b84c  call    cs:__imp_NtClose
0x18000b852  test    ebx, ebx
0x18000b854  jns     short loc_18000B875
0x18000b856  cmp     [rbp+Handle], rsi
0x18000b85a  jnz     loc_18000B90F
0x18000b860  mov     eax, ebx
0x18000b862  mov     rbx, [rsp+80h+arg_0]
0x18000b86a  add     rsp, 80h
0x18000b871  pop     rdi
0x18000b872  pop     rsi
0x18000b873  pop     rbp
0x18000b874  retn
0x18000b875  lea     rax, [rbp+arg_8]
0x18000b879  mov     r8, rdi
0x18000b87c  lea     r9, [rbp+arg_10]
0x18000b880  mov     [rsp+80h+TokenHandle], rax
0x18000b885  xor     edx, edx
0x18000b887  xor     ecx, ecx
0x18000b889  call    CreateRpcConnection
0x18000b88e  mov     ebx, eax
0x18000b890  jmp     short loc_18000B856
0x18000b892  mov     [rbp+ThreadInformation], rsi
0x18000b896  cmp     eax, 0C00000A5h
0x18000b89b  jz      short loc_18000B8A4
0x18000b89d  cmp     eax, 0C0000022h
0x18000b8a2  jnz     short loc_18000B856
0x18000b8a4  lea     rax, [rbp+Handle]
0x18000b8a8  xor     r9d, r9d; HandleAttributes
0x18000b8ab  mov     r8b, 1; OpenAsSelf
0x18000b8ae  mov     [rsp+80h+TokenHandle], rax; TokenHandle
0x18000b8b3  mov     edx, 2000Ch; DesiredAccess
0x18000b8b8  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000b8bf  call    cs:__imp_NtOpenThreadTokenEx
0x18000b8c5  mov     ebx, eax
0x18000b8c7  test    eax, eax
0x18000b8c9  js      short loc_18000B856
0x18000b8cb  mov     r9d, 8; ThreadInformationLength
0x18000b8d1  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18000b8d5  mov     edx, 5; ThreadInformationClass
0x18000b8da  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000b8e1  call    cs:__imp_NtSetInformationThread
0x18000b8e7  mov     ebx, eax
0x18000b8e9  test    eax, eax
0x18000b8eb  js      short loc_18000B92B
0x18000b8ed  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000b8f1  mov     edx, 100000h; DesiredAccess
0x18000b8f6  lea     rcx, [rbp+EventHandle]; EventHandle
0x18000b8fa  call    cs:__imp_NtOpenEvent
0x18000b900  mov     ebx, eax
0x18000b902  test    eax, eax
0x18000b904  js      loc_18000B856
0x18000b90a  jmp     loc_18000B837
0x18000b90f  mov     r9d, 8; ThreadInformationLength
0x18000b915  lea     r8, [rbp+Handle]; ThreadInformation
0x18000b919  mov     edx, 5; ThreadInformationClass
0x18000b91e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000b925  call    cs:__imp_NtSetInformationThread
0x18000b92b  mov     rcx, [rbp+Handle]; Handle
0x18000b92f  call    cs:__imp_NtClose
0x18000b935  jmp     loc_18000B860
```
