# RpcpNormalizeSecurityDescriptor(void *,ulong,void * *)

- ea: `0x180010244`
- end: `0x180010575`
- name: `?RpcpNormalizeSecurityDescriptor@@YAJPEAXKPEAPEAX@Z`
- size: `817`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR CreatorDescriptor, ULONG AutoInheritFlags, void **)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007ae0`
- `0x18000ff90`
- `0x18002f480`
- `0x180095a30`

## callees

- `0x180010244`
- `0x18001057c`
- `0x180010f10`
- `0x180023020`
- `0x180023a40`
- `0x18002e750`
- `0x1800ceda0`

## import_xrefs

- `ntdll!RtlDeleteSecurityObject` at `0x1800104bc`
- `ntdll!RtlDeleteSecurityObject` at `0x1800104bc`
- `ntdll!RtlNewSecurityObjectEx` at `0x180010450`
- `ntdll!RtlNewSecurityObjectEx` at `0x180010450`
- `ntdll!NtQuerySecurityObject` at `0x18001039f`
- `ntdll!NtQuerySecurityObject` at `0x1800103e3`
- `ntdll!NtQuerySecurityObject` at `0x18001039f`
- `ntdll!NtQuerySecurityObject` at `0x1800103e3`
- `ntdll!NtOpenDirectoryObject` at `0x180010371`
- `ntdll!NtOpenDirectoryObject` at `0x180010371`
- `ntdll!wcsstr` at `0x1800102cf`
- `ntdll!wcsstr` at `0x1800102cf`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x1800102ef`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x1800102ef`
- `ntdll!RtlFreeUnicodeString` at `0x18001055a`
- `ntdll!RtlFreeUnicodeString` at `0x18001055a`
- `ntdll!RtlInitUnicodeString` at `0x180010331`
- `ntdll!RtlInitUnicodeString` at `0x180010331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010483`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800104a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010483`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800104a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010501`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010413`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800103f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800103f7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010519`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010519`

## pseudocode

```c
__int64 __fastcall RpcpNormalizeSecurityDescriptor(
        PSECURITY_DESCRIPTOR CreatorDescriptor,
        ULONG AutoInheritFlags,
        void **a3)
{
  void *v3; // rdi
  unsigned __int16 *v7; // rax
  WCHAR *v8; // rsi
  HANDLE CurrentThread; // rax
  unsigned int v10; // ebx
  HANDLE CurrentProcess; // rax
  ULONG Length; // [rsp+40h] [rbp-59h] BYREF
  void *FileHandle; // [rsp+48h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-49h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+58h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-29h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+B0h] [rbp+17h] BYREF

  v3 = 0;
  FileHandle = 0;
  NewDescriptor = 0;
  TokenHandle = 0;
  Length = 0;
  GenericMapping.GenericRead = 131073;
  GenericMapping.GenericWrite = 131073;
  GenericMapping.GenericExecute = 0x20000;
  GenericMapping.GenericAll = 2031617;
  *a3 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  UnicodeString = 0;
  if ( wcsstr(&Src, L"\\RPC Control\\") )
  {
    v7 = DuplicateString(&Src);
    goto LABEL_5;
  }
  if ( (int)RtlGetAppContainerNamedObjectPath(0, 0, 0, &UnicodeString) < 0 || !UnicodeString.Buffer )
  {
    v7 = DuplicateString3(&Src, L"\\RPC Control\\", &Src);
LABEL_5:
    v8 = v7;
    goto LABEL_6;
  }
  v8 = DuplicateString3(UnicodeString.Buffer, L"\\RPC Control\\", &Src);
  RtlFreeUnicodeString(&UnicodeString);
LABEL_6:
  if ( v8 )
  {
    RtlInitUnicodeString(&DestinationString, v8);
    ObjectAttributes.Length = 48;
    DestinationString.Length -= 2;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenDirectoryObject(&FileHandle, 0x20001u, &ObjectAttributes) >= 0
      && (Length = 0, NtQuerySecurityObject(FileHandle, 0x17u, 0, 0, &Length) == -1073741789)
      && (v3 = AllocWrapper(Length)) != 0
      && NtQuerySecurityObject(FileHandle, 0x17u, v3, Length, &Length) >= 0
      && ((CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle))
       || GetLastError() == 1008
       && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)))
      && RtlNewSecurityObjectEx(
           v3,
           CreatorDescriptor,
           &NewDescriptor,
           0,
           0,
           AutoInheritFlags,
           TokenHandle,
           &GenericMapping) >= 0 )
    {
      v10 = RpcpCopySecurityDescriptor(NewDescriptor, a3);
    }
    else
    {
      v10 = 14;
    }
    FreeWrapper(v8);
  }
  else
  {
    v10 = 14;
  }
  if ( FileHandle )
    CloseHandle(FileHandle);
  if ( v3 )
    FreeWrapper(v3);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( NewDescriptor )
    RtlDeleteSecurityObject(&NewDescriptor);
  return v10;
}

```

## disassembly

```asm
0x180010244  mov     [rsp-8+arg_18], rbx
0x180010249  push    rbp
0x18001024a  push    rsi
0x18001024b  push    rdi
0x18001024c  push    r14
0x18001024e  push    r15
0x180010250  lea     rbp, [rsp-37h]
0x180010255  sub     rsp, 0D0h
0x18001025c  mov     rax, cs:__security_cookie
0x180010263  xor     rax, rsp
0x180010266  mov     [rbp+57h+var_30], rax
0x18001026a  xor     edi, edi
0x18001026c  mov     [rbp+57h+FileHandle], 0
0x180010274  xorps   xmm1, xmm1
0x180010277  mov     [rbp+57h+NewDescriptor], rdi
0x18001027b  xorps   xmm0, xmm0
0x18001027e  mov     [rbp+57h+TokenHandle], rdi
0x180010282  mov     eax, 20001h
0x180010287  mov     [rbp+57h+Length], edi
0x18001028a  mov     r15d, edx
0x18001028d  mov     [rbp+57h+var_40.GenericRead], eax
0x180010290  mov     r14, rcx
0x180010293  mov     [rbp+57h+var_40.GenericWrite], eax
0x180010296  lea     rsi, Src
0x18001029d  mov     [rbp+57h+var_40.GenericExecute], 20000h
0x1800102a4  mov     rcx, rsi; Str
0x1800102a7  mov     [rbp+57h+var_40.GenericAll], 1F0001h
0x1800102ae  lea     rdx, aRpcControl; "\\RPC Control\\"
0x1800102b5  mov     [r8], rdi
0x1800102b8  mov     rbx, r8
0x1800102bb  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800102bf  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800102c3  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800102c7  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800102cb  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x1800102cf  call    cs:__imp_wcsstr
0x1800102d6  nop     dword ptr [rax+rax+00h]
0x1800102db  test    rax, rax
0x1800102de  jnz     loc_180010537
0x1800102e4  lea     r9, [rbp+57h+UnicodeString]
0x1800102e8  xor     r8d, r8d
0x1800102eb  xor     edx, edx
0x1800102ed  xor     ecx, ecx
0x1800102ef  call    cs:__imp_RtlGetAppContainerNamedObjectPath
0x1800102f6  nop     dword ptr [rax+rax+00h]
0x1800102fb  test    eax, eax
0x1800102fd  js      short loc_18001030C
0x1800102ff  mov     rcx, [rbp+57h+UnicodeString.Buffer]; Src
0x180010303  test    rcx, rcx
0x180010306  jnz     loc_180010544
0x18001030c  mov     r8, rsi; unsigned __int16 *
0x18001030f  lea     rdx, aRpcControl; "\\RPC Control\\"
0x180010316  mov     rcx, rsi; Src
0x180010319  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x18001031e  mov     rsi, rax
0x180010321  test    rsi, rsi
0x180010324  jz      loc_18001056B
0x18001032a  mov     rdx, rsi; SourceString
0x18001032d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180010331  call    cs:__imp_RtlInitUnicodeString
0x180010338  nop     dword ptr [rax+rax+00h]
0x18001033d  mov     eax, 0FFFEh
0x180010342  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180010349  add     [rbp+57h+DestinationString.Length], ax
0x18001034d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180010351  lea     rax, [rbp+57h+DestinationString]
0x180010355  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180010359  xorps   xmm0, xmm0
0x18001035c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180010360  mov     edx, 20001h; DesiredAccess
0x180010365  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x180010368  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18001036c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180010371  call    cs:__imp_NtOpenDirectoryObject
0x180010378  nop     dword ptr [rax+rax+00h]
0x18001037d  test    eax, eax
0x18001037f  js      loc_18001052D
0x180010385  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180010389  lea     rax, [rbp+57h+Length]
0x18001038d  xor     r9d, r9d; Length
0x180010390  mov     [rbp+57h+Length], edi
0x180010393  xor     r8d, r8d; SecurityDescriptor
0x180010396  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x18001039b  lea     edx, [r9+17h]; SecurityInformation
0x18001039f  call    cs:__imp_NtQuerySecurityObject
0x1800103a6  nop     dword ptr [rax+rax+00h]
0x1800103ab  cmp     eax, 0C0000023h
0x1800103b0  jnz     loc_18001052D
0x1800103b6  mov     ecx, [rbp+57h+Length]; dwBytes
0x1800103b9  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800103be  mov     rdi, rax
0x1800103c1  test    rax, rax
0x1800103c4  jz      loc_18001052D
0x1800103ca  mov     r9d, [rbp+57h+Length]; Length
0x1800103ce  lea     rax, [rbp+57h+Length]
0x1800103d2  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800103d6  mov     r8, rdi; SecurityDescriptor
0x1800103d9  mov     edx, 17h; SecurityInformation
0x1800103de  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x1800103e3  call    cs:__imp_NtQuerySecurityObject
0x1800103ea  nop     dword ptr [rax+rax+00h]
0x1800103ef  test    eax, eax
0x1800103f1  js      loc_18001052D
0x1800103f7  call    cs:__imp_GetCurrentThread
0x1800103fe  nop     dword ptr [rax+rax+00h]
0x180010403  mov     edx, 8; DesiredAccess
0x180010408  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001040c  mov     rcx, rax; ThreadHandle
0x18001040f  lea     r8d, [rdx-7]; OpenAsSelf
0x180010413  call    cs:__imp_OpenThreadToken
0x18001041a  nop     dword ptr [rax+rax+00h]
0x18001041f  test    eax, eax
0x180010421  jz      loc_1800104EE
0x180010427  lea     rax, [rbp+57h+var_40]
0x18001042b  xor     r9d, r9d; ObjectType
0x18001042e  mov     [rsp+0F0h+GenericMapping], rax; GenericMapping
0x180010433  lea     r8, [rbp+57h+NewDescriptor]; NewDescriptor
0x180010437  mov     rax, [rbp+57h+TokenHandle]
0x18001043b  mov     rdx, r14; CreatorDescriptor
0x18001043e  mov     [rsp+0F0h+Token], rax; Token
0x180010443  mov     rcx, rdi; ParentDescriptor
0x180010446  mov     [rsp+0F0h+AutoInheritFlags], r15d; AutoInheritFlags
0x18001044b  mov     byte ptr [rsp+0F0h+LengthNeeded], 0; IsDirectoryObject
0x180010450  call    cs:__imp_RtlNewSecurityObjectEx
0x180010457  nop     dword ptr [rax+rax+00h]
0x18001045c  test    eax, eax
0x18001045e  js      loc_18001052D
0x180010464  mov     rcx, [rbp+57h+NewDescriptor]; Src
0x180010468  mov     rdx, rbx; void **
0x18001046b  call    ?RpcpCopySecurityDescriptor@@YAJPEAXPEAPEAX@Z; RpcpCopySecurityDescriptor(void *,void * *)
0x180010470  mov     ebx, eax
0x180010472  mov     rcx, rsi; lpMem
0x180010475  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18001047a  mov     rcx, [rbp+57h+FileHandle]; hObject
0x18001047e  test    rcx, rcx
0x180010481  jz      short loc_18001048F
0x180010483  call    cs:__imp_CloseHandle
0x18001048a  nop     dword ptr [rax+rax+00h]
0x18001048f  test    rdi, rdi
0x180010492  jz      short loc_18001049C
0x180010494  mov     rcx, rdi; lpMem
0x180010497  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18001049c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800104a0  test    rcx, rcx
0x1800104a3  jz      short loc_1800104B1
0x1800104a5  call    cs:__imp_CloseHandle
0x1800104ac  nop     dword ptr [rax+rax+00h]
0x1800104b1  cmp     [rbp+57h+NewDescriptor], 0
0x1800104b6  jz      short loc_1800104C8
0x1800104b8  lea     rcx, [rbp+57h+NewDescriptor]; ObjectDescriptor
0x1800104bc  call    cs:__imp_RtlDeleteSecurityObject
0x1800104c3  nop     dword ptr [rax+rax+00h]
0x1800104c8  mov     eax, ebx
0x1800104ca  mov     rcx, [rbp+57h+var_30]
0x1800104ce  xor     rcx, rsp; StackCookie
0x1800104d1  call    __security_check_cookie
0x1800104d6  mov     rbx, [rsp+0F0h+arg_18]
0x1800104de  add     rsp, 0D0h
0x1800104e5  pop     r15
0x1800104e7  pop     r14
0x1800104e9  pop     rdi
0x1800104ea  pop     rsi
0x1800104eb  pop     rbp
0x1800104ec  retn
0x1800104ee  call    cs:__imp_GetLastError
0x1800104f5  nop     dword ptr [rax+rax+00h]
0x1800104fa  cmp     eax, 3F0h
0x1800104ff  jnz     short loc_18001052D
0x180010501  call    cs:__imp_GetCurrentProcess
0x180010508  nop     dword ptr [rax+rax+00h]
0x18001050d  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180010511  mov     edx, 8; DesiredAccess
0x180010516  mov     rcx, rax; ProcessHandle
0x180010519  call    cs:__imp_OpenProcessToken
0x180010520  nop     dword ptr [rax+rax+00h]
0x180010525  test    eax, eax
0x180010527  jnz     loc_180010427
0x18001052d  mov     ebx, 0Eh
0x180010532  jmp     loc_180010472
0x180010537  mov     rcx, rsi; Src
0x18001053a  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x18001053f  jmp     loc_18001031E
0x180010544  mov     r8, rsi; unsigned __int16 *
0x180010547  lea     rdx, aRpcControl; "\\RPC Control\\"
0x18001054e  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x180010553  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180010557  mov     rsi, rax
0x18001055a  call    cs:__imp_RtlFreeUnicodeString
0x180010561  nop     dword ptr [rax+rax+00h]
0x180010566  jmp     loc_180010321
0x18001056b  mov     ebx, 0Eh
0x180010570  jmp     loc_18001047A
```
