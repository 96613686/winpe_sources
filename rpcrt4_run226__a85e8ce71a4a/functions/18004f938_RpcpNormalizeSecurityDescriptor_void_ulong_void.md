# RpcpNormalizeSecurityDescriptor(void *,ulong,void * *)

- ea: `0x18004f938`
- end: `0x18004fc08`
- name: `?RpcpNormalizeSecurityDescriptor@@YAJPEAXKPEAPEAX@Z`
- size: `720`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR CreatorDescriptor, ULONG AutoInheritFlags, void **)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002e0f0`
- `0x18004f690`
- `0x180067778`
- `0x180091480`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18002d420`
- `0x18004f938`
- `0x18004fc10`
- `0x180050500`
- `0x1800ca140`

## import_xrefs

- `ntdll!RtlDeleteSecurityObject` at `0x18004fb6e`
- `ntdll!RtlDeleteSecurityObject` at `0x18004fb6e`
- `ntdll!RtlNewSecurityObjectEx` at `0x18004fb14`
- `ntdll!RtlNewSecurityObjectEx` at `0x18004fb14`
- `ntdll!NtQuerySecurityObject` at `0x18004fa7b`
- `ntdll!NtQuerySecurityObject` at `0x18004fab9`
- `ntdll!NtQuerySecurityObject` at `0x18004fa7b`
- `ntdll!NtQuerySecurityObject` at `0x18004fab9`
- `ntdll!NtOpenDirectoryObject` at `0x18004fa53`
- `ntdll!NtOpenDirectoryObject` at `0x18004fa53`
- `ntdll!wcsstr` at `0x18004f9c3`
- `ntdll!wcsstr` at `0x18004f9c3`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18004f9dd`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18004f9dd`
- `ntdll!RtlFreeUnicodeString` at `0x18004fbf3`
- `ntdll!RtlFreeUnicodeString` at `0x18004fbf3`
- `ntdll!RtlInitUnicodeString` at `0x18004fa19`
- `ntdll!RtlInitUnicodeString` at `0x18004fa19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fb99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fb99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fb41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fb5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fb41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fb5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fba6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fba6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004fadd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004fadd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004fac7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004fac7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004fbb8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004fbb8`

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
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF
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
0x18004f938  mov     [rsp-8+arg_18], rbx
0x18004f93d  push    rbp
0x18004f93e  push    rsi
0x18004f93f  push    rdi
0x18004f940  push    r14
0x18004f942  push    r15
0x18004f944  lea     rbp, [rsp-37h]
0x18004f949  sub     rsp, 0D0h
0x18004f950  mov     rax, cs:__security_cookie
0x18004f957  xor     rax, rsp
0x18004f95a  mov     [rbp+57h+var_30], rax
0x18004f95e  xor     edi, edi
0x18004f960  mov     [rbp+57h+FileHandle], 0
0x18004f968  xorps   xmm1, xmm1
0x18004f96b  mov     [rbp+57h+NewDescriptor], rdi
0x18004f96f  xorps   xmm0, xmm0
0x18004f972  mov     [rbp+57h+TokenHandle], rdi
0x18004f976  mov     eax, 20001h
0x18004f97b  mov     [rbp+57h+Length], edi
0x18004f97e  mov     r15d, edx
0x18004f981  mov     [rbp+57h+var_40.GenericRead], eax
0x18004f984  mov     r14, rcx
0x18004f987  mov     [rbp+57h+var_40.GenericWrite], eax
0x18004f98a  lea     rsi, Src
0x18004f991  mov     [rbp+57h+var_40.GenericExecute], 20000h
0x18004f998  mov     rcx, rsi; Str
0x18004f99b  mov     [rbp+57h+var_40.GenericAll], 1F0001h
0x18004f9a2  lea     rdx, aRpcControl; "\\RPC Control\\"
0x18004f9a9  mov     [r8], rdi
0x18004f9ac  mov     rbx, r8
0x18004f9af  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18004f9b3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18004f9b7  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18004f9bb  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18004f9bf  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x18004f9c3  call    cs:__imp_wcsstr
0x18004f9c9  test    rax, rax
0x18004f9cc  jnz     loc_18004FBD0
0x18004f9d2  lea     r9, [rbp+57h+UnicodeString]
0x18004f9d6  xor     r8d, r8d
0x18004f9d9  xor     edx, edx
0x18004f9db  xor     ecx, ecx
0x18004f9dd  call    cs:__imp_RtlGetAppContainerNamedObjectPath
0x18004f9e3  test    eax, eax
0x18004f9e5  js      short loc_18004F9F4
0x18004f9e7  mov     rcx, [rbp+57h+UnicodeString.Buffer]; Src
0x18004f9eb  test    rcx, rcx
0x18004f9ee  jnz     loc_18004FBDD
0x18004f9f4  mov     r8, rsi; unsigned __int16 *
0x18004f9f7  lea     rdx, aRpcControl; "\\RPC Control\\"
0x18004f9fe  mov     rcx, rsi; Src
0x18004fa01  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x18004fa06  mov     rsi, rax
0x18004fa09  test    rsi, rsi
0x18004fa0c  jz      loc_18004FBFE
0x18004fa12  mov     rdx, rsi; SourceString
0x18004fa15  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004fa19  call    cs:__imp_RtlInitUnicodeString
0x18004fa1f  mov     eax, 0FFFEh
0x18004fa24  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18004fa2b  add     [rbp+57h+DestinationString.Length], ax
0x18004fa2f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18004fa33  lea     rax, [rbp+57h+DestinationString]
0x18004fa37  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x18004fa3b  xorps   xmm0, xmm0
0x18004fa3e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18004fa42  mov     edx, 20001h; DesiredAccess
0x18004fa47  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x18004fa4a  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18004fa4e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004fa53  call    cs:__imp_NtOpenDirectoryObject
0x18004fa59  test    eax, eax
0x18004fa5b  js      loc_18004FBC6
0x18004fa61  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18004fa65  lea     rax, [rbp+57h+Length]
0x18004fa69  xor     r9d, r9d; Length
0x18004fa6c  mov     [rbp+57h+Length], edi
0x18004fa6f  xor     r8d, r8d; SecurityDescriptor
0x18004fa72  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x18004fa77  lea     edx, [r9+17h]; SecurityInformation
0x18004fa7b  call    cs:__imp_NtQuerySecurityObject
0x18004fa81  cmp     eax, 0C0000023h
0x18004fa86  jnz     loc_18004FBC6
0x18004fa8c  mov     ecx, [rbp+57h+Length]; dwBytes
0x18004fa8f  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18004fa94  mov     rdi, rax
0x18004fa97  test    rax, rax
0x18004fa9a  jz      loc_18004FBC6
0x18004faa0  mov     r9d, [rbp+57h+Length]; Length
0x18004faa4  lea     rax, [rbp+57h+Length]
0x18004faa8  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18004faac  mov     r8, rdi; SecurityDescriptor
0x18004faaf  mov     edx, 17h; SecurityInformation
0x18004fab4  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x18004fab9  call    cs:__imp_NtQuerySecurityObject
0x18004fabf  test    eax, eax
0x18004fac1  js      loc_18004FBC6
0x18004fac7  call    cs:__imp_GetCurrentThread
0x18004facd  mov     edx, 8; DesiredAccess
0x18004fad2  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18004fad6  mov     rcx, rax; ThreadHandle
0x18004fad9  lea     r8d, [rdx-7]; OpenAsSelf
0x18004fadd  call    cs:__imp_OpenThreadToken
0x18004fae3  test    eax, eax
0x18004fae5  jz      loc_18004FB99
0x18004faeb  lea     rax, [rbp+57h+var_40]
0x18004faef  xor     r9d, r9d; ObjectType
0x18004faf2  mov     [rsp+0F0h+GenericMapping], rax; GenericMapping
0x18004faf7  lea     r8, [rbp+57h+NewDescriptor]; NewDescriptor
0x18004fafb  mov     rax, [rbp+57h+TokenHandle]
0x18004faff  mov     rdx, r14; CreatorDescriptor
0x18004fb02  mov     [rsp+0F0h+Token], rax; Token
0x18004fb07  mov     rcx, rdi; ParentDescriptor
0x18004fb0a  mov     [rsp+0F0h+AutoInheritFlags], r15d; AutoInheritFlags
0x18004fb0f  mov     byte ptr [rsp+0F0h+LengthNeeded], 0; IsDirectoryObject
0x18004fb14  call    cs:__imp_RtlNewSecurityObjectEx
0x18004fb1a  test    eax, eax
0x18004fb1c  js      loc_18004FBC6
0x18004fb22  mov     rcx, [rbp+57h+NewDescriptor]; Src
0x18004fb26  mov     rdx, rbx; void **
0x18004fb29  call    ?RpcpCopySecurityDescriptor@@YAJPEAXPEAPEAX@Z; RpcpCopySecurityDescriptor(void *,void * *)
0x18004fb2e  mov     ebx, eax
0x18004fb30  mov     rcx, rsi; lpMem
0x18004fb33  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004fb38  mov     rcx, [rbp+57h+FileHandle]; hObject
0x18004fb3c  test    rcx, rcx
0x18004fb3f  jz      short loc_18004FB47
0x18004fb41  call    cs:__imp_CloseHandle
0x18004fb47  test    rdi, rdi
0x18004fb4a  jz      short loc_18004FB54
0x18004fb4c  mov     rcx, rdi; lpMem
0x18004fb4f  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004fb54  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18004fb58  test    rcx, rcx
0x18004fb5b  jz      short loc_18004FB63
0x18004fb5d  call    cs:__imp_CloseHandle
0x18004fb63  cmp     [rbp+57h+NewDescriptor], 0
0x18004fb68  jz      short loc_18004FB74
0x18004fb6a  lea     rcx, [rbp+57h+NewDescriptor]; ObjectDescriptor
0x18004fb6e  call    cs:__imp_RtlDeleteSecurityObject
0x18004fb74  mov     eax, ebx
0x18004fb76  mov     rcx, [rbp+57h+var_30]
0x18004fb7a  xor     rcx, rsp; StackCookie
0x18004fb7d  call    __security_check_cookie
0x18004fb82  mov     rbx, [rsp+0F0h+arg_18]
0x18004fb8a  add     rsp, 0D0h
0x18004fb91  pop     r15
0x18004fb93  pop     r14
0x18004fb95  pop     rdi
0x18004fb96  pop     rsi
0x18004fb97  pop     rbp
0x18004fb98  retn
0x18004fb99  call    cs:__imp_GetLastError
0x18004fb9f  cmp     eax, 3F0h
0x18004fba4  jnz     short loc_18004FBC6
0x18004fba6  call    cs:__imp_GetCurrentProcess
0x18004fbac  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18004fbb0  mov     edx, 8; DesiredAccess
0x18004fbb5  mov     rcx, rax; ProcessHandle
0x18004fbb8  call    cs:__imp_OpenProcessToken
0x18004fbbe  test    eax, eax
0x18004fbc0  jnz     loc_18004FAEB
0x18004fbc6  mov     ebx, 0Eh
0x18004fbcb  jmp     loc_18004FB30
0x18004fbd0  mov     rcx, rsi; Src
0x18004fbd3  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x18004fbd8  jmp     loc_18004FA06
0x18004fbdd  mov     r8, rsi; unsigned __int16 *
0x18004fbe0  lea     rdx, aRpcControl; "\\RPC Control\\"
0x18004fbe7  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x18004fbec  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18004fbf0  mov     rsi, rax
0x18004fbf3  call    cs:__imp_RtlFreeUnicodeString
0x18004fbf9  jmp     loc_18004FA09
0x18004fbfe  mov     ebx, 0Eh
0x18004fc03  jmp     loc_18004FB38
```
