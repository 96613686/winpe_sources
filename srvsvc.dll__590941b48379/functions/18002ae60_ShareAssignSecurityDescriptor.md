# ShareAssignSecurityDescriptor

- ea: `0x18002ae60`
- end: `0x18002afef`
- name: `ShareAssignSecurityDescriptor`
- size: `399`
- prototype: `ULONG __fastcall(__int16 *Src, PSECURITY_DESCRIPTOR *NewDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003f60`
- `0x180029884`

## callees

- `0x18002ae60`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002aeac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002aedd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002af17`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002af54`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002afb2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002aeac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002aedd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002af17`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002af54`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002afb2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aebd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aebd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002afcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002afcd`
- `ntdll!RtlNewSecurityObjectEx` at `0x18002af8a`
- `ntdll!RtlNewSecurityObjectEx` at `0x18002af8a`
- `ntdll!RtlNtStatusToDosError` at `0x18002afd5`
- `ntdll!RtlNtStatusToDosError` at `0x18002afd5`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002ae92`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002ae92`
- `ntdll!NtOpenThreadToken` at `0x18002af34`
- `ntdll!NtOpenThreadToken` at `0x18002af34`
- `ntdll!NtClose` at `0x18002af9e`
- `ntdll!NtClose` at `0x18002af9e`
- `RPCRT4!RpcImpersonateClient` at `0x18002aeff`
- `RPCRT4!RpcImpersonateClient` at `0x18002aeff`
- `RPCRT4!RpcRevertToSelf` at `0x18002af40`
- `RPCRT4!RpcRevertToSelf` at `0x18002af40`

## pseudocode

```c
ULONG __fastcall ShareAssignSecurityDescriptor(__int16 *Src, PSECURITY_DESCRIPTOR *NewDescriptor)
{
  ULONG v5; // eax
  SIZE_T v6; // rdi
  size_t v7; // r14
  HLOCAL v8; // rdi
  RPC_STATUS v9; // eax
  NTSTATUS v10; // esi
  NTSTATUS v11; // esi
  void *TokenHandle; // [rsp+80h] [rbp+18h] BYREF

  TokenHandle = 0;
  if ( Src[1] >= 0 )
    return 87;
  v5 = RtlLengthSecurityDescriptor(Src);
  v6 = v5;
  if ( v5 < 0x14 )
    RaiseException(0xC000000D, 0, 0, 0);
  v7 = v6;
  v8 = LocalAlloc(0x40u, v6);
  if ( !v8 )
    RaiseException(0xC000009A, 0, 0, 0);
  memcpy_0(v8, Src, v7);
  *((_DWORD *)v8 + 3) = 0;
  *((_WORD *)v8 + 1) &= 0x900Cu;
  v9 = RpcImpersonateClient(0);
  if ( v9 < 0 )
    RaiseException(v9, 0, 0, 0);
  v10 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  RpcRevertToSelf();
  if ( v10 < 0 )
    RaiseException(v10, 0, 0, 0);
  v11 = RtlNewSecurityObjectEx(0, v8, NewDescriptor, 0, 0, 0x10u, TokenHandle, &SrvShareFileGenericMapping);
  NtClose(TokenHandle);
  if ( v11 < 0 )
    RaiseException(v11, 0, 0, 0);
  if ( v8 )
    LocalFree(v8);
  return RtlNtStatusToDosError(v11);
}

```

## disassembly

```asm
0x18002ae60  mov     rax, rsp
0x18002ae63  mov     [rax+8], rbx
0x18002ae67  mov     [rax+10h], rsi
0x18002ae6b  push    rdi
0x18002ae6c  push    r14
0x18002ae6e  push    r15
0x18002ae70  sub     rsp, 50h
0x18002ae74  mov     r15, rdx
0x18002ae77  mov     rsi, rcx
0x18002ae7a  xor     ebx, ebx
0x18002ae7c  mov     [rax+18h], rbx
0x18002ae80  mov     [rax-20h], rbx
0x18002ae84  cmp     [rcx+2], bx
0x18002ae88  jl      short loc_18002AE92
0x18002ae8a  lea     eax, [rbx+57h]
0x18002ae8d  jmp     loc_18002AFDB
0x18002ae92  call    cs:__imp_RtlLengthSecurityDescriptor
0x18002ae98  mov     edi, eax
0x18002ae9a  cmp     eax, 14h
0x18002ae9d  jnb     short loc_18002AEB2
0x18002ae9f  xor     r9d, r9d; lpArguments
0x18002aea2  xor     r8d, r8d; nNumberOfArguments
0x18002aea5  xor     edx, edx; dwExceptionFlags
0x18002aea7  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002aeac  call    cs:__imp_RaiseException
0x18002aeb2  mov     r14, rdi
0x18002aeb5  mov     rdx, rdi; uBytes
0x18002aeb8  mov     ecx, 40h ; '@'; uFlags
0x18002aebd  call    cs:__imp_LocalAlloc
0x18002aec3  mov     rdi, rax
0x18002aec6  mov     [rsp+68h+var_20], rax
0x18002aecb  test    rax, rax
0x18002aece  jnz     short loc_18002AEE3
0x18002aed0  xor     r9d, r9d; lpArguments
0x18002aed3  xor     r8d, r8d; nNumberOfArguments
0x18002aed6  xor     edx, edx; dwExceptionFlags
0x18002aed8  mov     ecx, 0C000009Ah; dwExceptionCode
0x18002aedd  call    cs:__imp_RaiseException
0x18002aee3  mov     r8, r14; Size
0x18002aee6  mov     rdx, rsi; Src
0x18002aee9  mov     rcx, rdi; void *
0x18002aeec  call    memcpy_0
0x18002aef1  mov     [rdi+0Ch], ebx
0x18002aef4  mov     eax, 900Ch
0x18002aef9  and     [rdi+2], ax
0x18002aefd  xor     ecx, ecx; BindingHandle
0x18002aeff  call    cs:__imp_RpcImpersonateClient
0x18002af05  mov     [rsp+68h+var_28], eax
0x18002af09  test    eax, eax
0x18002af0b  jns     short loc_18002AF1D
0x18002af0d  xor     r9d, r9d; lpArguments
0x18002af10  xor     r8d, r8d; nNumberOfArguments
0x18002af13  xor     edx, edx; dwExceptionFlags
0x18002af15  mov     ecx, eax; dwExceptionCode
0x18002af17  call    cs:__imp_RaiseException
0x18002af1d  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x18002af25  mov     r8b, 1; OpenAsSelf
0x18002af28  mov     edx, 8; DesiredAccess
0x18002af2d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002af34  call    cs:__imp_NtOpenThreadToken
0x18002af3a  mov     esi, eax
0x18002af3c  mov     [rsp+68h+var_28], eax
0x18002af40  call    cs:__imp_RpcRevertToSelf
0x18002af46  test    esi, esi
0x18002af48  jns     short loc_18002AF5A
0x18002af4a  xor     r9d, r9d; lpArguments
0x18002af4d  xor     r8d, r8d; nNumberOfArguments
0x18002af50  xor     edx, edx; dwExceptionFlags
0x18002af52  mov     ecx, esi; dwExceptionCode
0x18002af54  call    cs:__imp_RaiseException
0x18002af5a  lea     rax, SrvShareFileGenericMapping
0x18002af61  mov     [rsp+68h+GenericMapping], rax; GenericMapping
0x18002af66  mov     rax, [rsp+68h+TokenHandle]
0x18002af6e  mov     [rsp+68h+Token], rax; Token
0x18002af73  mov     [rsp+68h+AutoInheritFlags], 10h; AutoInheritFlags
0x18002af7b  mov     [rsp+68h+IsDirectoryObject], bl; IsDirectoryObject
0x18002af7f  xor     r9d, r9d; ObjectType
0x18002af82  mov     r8, r15; NewDescriptor
0x18002af85  mov     rdx, rdi; CreatorDescriptor
0x18002af88  xor     ecx, ecx; ParentDescriptor
0x18002af8a  call    cs:__imp_RtlNewSecurityObjectEx
0x18002af90  mov     esi, eax
0x18002af92  mov     [rsp+68h+var_28], eax
0x18002af96  mov     rcx, [rsp+68h+TokenHandle]; Handle
0x18002af9e  call    cs:__imp_NtClose
0x18002afa4  test    esi, esi
0x18002afa6  jns     short loc_18002AFB8
0x18002afa8  xor     r9d, r9d; lpArguments
0x18002afab  xor     r8d, r8d; nNumberOfArguments
0x18002afae  xor     edx, edx; dwExceptionFlags
0x18002afb0  mov     ecx, esi; dwExceptionCode
0x18002afb2  call    cs:__imp_RaiseException
0x18002afb8  jmp     short loc_18002AFC5
0x18002afba  mov     esi, eax
0x18002afbc  mov     [rsp+68h+var_28], eax
0x18002afc0  mov     rdi, [rsp+68h+var_20]
0x18002afc5  test    rdi, rdi
0x18002afc8  jz      short loc_18002AFD3
0x18002afca  mov     rcx, rdi; hMem
0x18002afcd  call    cs:__imp_LocalFree
0x18002afd3  mov     ecx, esi; Status
0x18002afd5  call    cs:__imp_RtlNtStatusToDosError
0x18002afdb  mov     rbx, [rsp+68h+arg_0]
0x18002afe0  mov     rsi, [rsp+68h+arg_8]
0x18002afe5  add     rsp, 50h
0x18002afe9  pop     r15
0x18002afeb  pop     r14
0x18002afed  pop     rdi
0x18002afee  retn
```
