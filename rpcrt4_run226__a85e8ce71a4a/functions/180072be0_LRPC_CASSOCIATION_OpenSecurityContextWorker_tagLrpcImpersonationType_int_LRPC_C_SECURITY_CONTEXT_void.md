# LRPC_CASSOCIATION::OpenSecurityContextWorker(tagLrpcImpersonationType,int,LRPC_C_SECURITY_CONTEXT *,void *)

- ea: `0x180072be0`
- end: `0x180072e2a`
- name: `?OpenSecurityContextWorker@LRPC_CASSOCIATION@@QEAAJW4tagLrpcImpersonationType@@HPEAVLRPC_C_SECURITY_CONTEXT@@PEAX@Z`
- size: `586`
- prototype: `__int64 __fastcall(__int64, int, char, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028d70`
- `0x18002b9a0`
- `0x180072ab0`

## callees

- `0x1800274e0`
- `0x1800283bc`
- `0x180072be0`
- `0x180072e30`

## import_xrefs

- `ntdll!NtAlpcCreateSecurityContext` at `0x180072ce7`
- `ntdll!NtAlpcCreateSecurityContext` at `0x180072ce7`
- `ntdll!NtImpersonateAnonymousToken` at `0x180072d6e`
- `ntdll!NtImpersonateAnonymousToken` at `0x180072d6e`
- `ntdll!NtOpenThreadToken` at `0x180072c23`
- `ntdll!NtOpenThreadToken` at `0x180072c23`
- `ntdll!NtSetInformationThread` at `0x180072c7a`
- `ntdll!NtSetInformationThread` at `0x180072c7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072c0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072c65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072d65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072c0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072c65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072d65`

## pseudocode

```c
__int64 __fastcall LRPC_CASSOCIATION::OpenSecurityContextWorker(__int64 a1, int a2, char a3, __int64 a4, __int64 a5)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v10; // eax
  __int64 v11; // rax
  unsigned int v12; // edi
  int v13; // ebx
  HANDLE v14; // rax
  NTSTATUS v15; // eax
  int SecurityContext; // eax
  __int64 v17; // rcx
  unsigned __int16 v19; // r8
  HANDLE v20; // rax
  unsigned int v21; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  __int64 ThreadInformation; // [rsp+38h] [rbp-28h] BYREF
  int v24; // [rsp+40h] [rbp-20h] BYREF
  int v25; // [rsp+48h] [rbp-18h]

  TokenHandle = 0;
  ThreadInformation = 0;
  CurrentThread = GetCurrentThread();
  v10 = NtOpenThreadToken(CurrentThread, 0xCu, 1u, &TokenHandle);
  switch ( v10 )
  {
    case -1073741790:
      v21 = 5;
      goto LABEL_30;
    case -1073741700:
      TokenHandle = (void *)4294967293LL;
      break;
    case -1073741658:
      TokenHandle = (void *)4294967294LL;
      break;
    default:
      if ( v10 )
      {
        v21 = 14;
LABEL_30:
        v25 = v10;
        TokenHandle = 0;
        v24 = 3;
        RpcpErrorAddRecord(2u, v21, 0x460u, 1, (struct tagParam *)&v24);
        return v21;
      }
      break;
  }
  v11 = a5;
  v12 = 0;
  v13 = 5;
  if ( a5 == 4294967293LL )
  {
    v11 = 0;
  }
  else if ( a5 == 4294967294LL )
  {
    v20 = GetCurrentThread();
    v15 = NtImpersonateAnonymousToken(v20);
    goto LABEL_7;
  }
  ThreadInformation = v11;
  v14 = GetCurrentThread();
  v15 = NtSetInformationThread(v14, ThreadImpersonationToken, &ThreadInformation, 8u);
LABEL_7:
  if ( v15 < 0 )
  {
    v24 = 3;
    if ( v15 == -1073741790 )
    {
      v25 = -1073741790;
      v19 = 541;
    }
    else
    {
      v13 = 14;
      v25 = v15;
      v19 = 542;
    }
    v12 = v13;
    RpcpErrorAddRecord(2u, v13, v19, 1, (struct tagParam *)&v24);
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)(a4 + 8) + 16LL) = 0;
    **(_DWORD **)(a4 + 8) = 0x20000;
    *(_DWORD *)(a4 + 52) = a2 - 1;
    *(_BYTE *)(a4 + 56) = 0;
    *(_BYTE *)(a4 + 57) = a3;
    if ( dword_1800F9624 )
      LogEventToEtw(
        0x4Cu,
        0x43u,
        *(_QWORD *)(a1 + 136) | 1LL,
        *(_QWORD *)(*(_QWORD *)(a4 + 8) + 16LL),
        **(unsigned int **)(a4 + 8));
    SecurityContext = NtAlpcCreateSecurityContext(*(_QWORD *)(a1 + 136), 0, *(_QWORD *)(a4 + 8));
    **(_DWORD **)(a4 + 8) = 0;
    if ( SecurityContext < 0 )
    {
      if ( SecurityContext == -1073741790 || (v12 = 14, SecurityContext == -1073741659) )
        v12 = 5;
      v25 = SecurityContext;
      v24 = 3;
      RpcpErrorAddRecord(2u, v12, 0x21Cu, 1, (struct tagParam *)&v24);
      v17 = 0;
    }
    else
    {
      v17 = *(_QWORD *)(*(_QWORD *)(a4 + 8) + 16LL);
    }
    *(_QWORD *)a4 = v17;
  }
  RestoreOldThreadToken(TokenHandle);
  return v12;
}

```

## disassembly

```asm
0x180072be0  push    rbp
0x180072be2  push    rbx
0x180072be3  push    rsi
0x180072be4  push    rdi
0x180072be5  push    r13
0x180072be7  push    r14
0x180072be9  push    r15
0x180072beb  mov     rbp, rsp
0x180072bee  sub     rsp, 60h
0x180072bf2  mov     rsi, r9
0x180072bf5  mov     [rbp+TokenHandle], 0
0x180072bfd  mov     r15d, r8d
0x180072c00  mov     [rbp+ThreadInformation], 0
0x180072c08  mov     r13d, edx
0x180072c0b  mov     r14, rcx
0x180072c0e  call    cs:__imp_GetCurrentThread
0x180072c14  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180072c18  mov     r8b, 1; OpenAsSelf
0x180072c1b  mov     rcx, rax; ThreadHandle
0x180072c1e  mov     edx, 0Ch; DesiredAccess
0x180072c23  call    cs:__imp_NtOpenThreadToken
0x180072c29  cmp     eax, 0C0000022h
0x180072c2e  jz      loc_180072DF0
0x180072c34  mov     edx, 0FFFFFFFEh
0x180072c39  mov     ecx, 0FFFFFFFDh
0x180072c3e  cmp     eax, 0C000007Ch
0x180072c43  jnz     loc_180072D89
0x180072c49  mov     [rbp+TokenHandle], rcx
0x180072c4d  mov     rax, [rbp+arg_20]
0x180072c51  xor     edi, edi
0x180072c53  lea     ebx, [rdi+5]
0x180072c56  cmp     rax, rcx
0x180072c59  jnz     loc_180072D5C
0x180072c5f  xor     eax, eax
0x180072c61  mov     [rbp+ThreadInformation], rax
0x180072c65  call    cs:__imp_GetCurrentThread
0x180072c6b  mov     r9d, 8; ThreadInformationLength
0x180072c71  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180072c75  mov     rcx, rax; ThreadHandle
0x180072c78  mov     edx, ebx; ThreadInformationClass
0x180072c7a  call    cs:__imp_NtSetInformationThread
0x180072c80  test    eax, eax
0x180072c82  js      loc_180072D24
0x180072c88  mov     rax, [rsi+8]
0x180072c8c  mov     qword ptr [rax+10h], 0
0x180072c94  mov     rax, [rsi+8]
0x180072c98  mov     dword ptr [rax], 20000h
0x180072c9e  lea     eax, [r13-1]
0x180072ca2  mov     [rsi+34h], eax
0x180072ca5  mov     byte ptr [rsi+38h], 0
0x180072ca9  mov     [rsi+39h], r15b
0x180072cad  cmp     cs:dword_1800F9624, 0
0x180072cb4  jz      short loc_180072CDA
0x180072cb6  mov     r9, [rsi+8]
0x180072cba  mov     dl, 43h ; 'C'; unsigned __int8
0x180072cbc  mov     r8, [r14+88h]
0x180072cc3  mov     cl, 4Ch ; 'L'; unsigned __int8
0x180072cc5  or      r8, 1; __int64
0x180072cc9  mov     eax, [r9]
0x180072ccc  mov     r9, [r9+10h]; __int64
0x180072cd0  mov     [rsp+60h+var_40], rax; __int64
0x180072cd5  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x180072cda  mov     r8, [rsi+8]
0x180072cde  xor     edx, edx
0x180072ce0  mov     rcx, [r14+88h]
0x180072ce7  call    cs:__imp_NtAlpcCreateSecurityContext
0x180072ced  mov     rcx, [rsi+8]
0x180072cf1  mov     dword ptr [rcx], 0
0x180072cf7  test    eax, eax
0x180072cf9  js      loc_180072DA8
0x180072cff  mov     rax, [rsi+8]
0x180072d03  mov     rcx, [rax+10h]
0x180072d07  mov     [rsi], rcx
0x180072d0a  mov     rcx, [rbp+TokenHandle]; void *
0x180072d0e  call    ?RestoreOldThreadToken@@YAXPEAX@Z; RestoreOldThreadToken(void *)
0x180072d13  mov     eax, edi
0x180072d15  add     rsp, 60h
0x180072d19  pop     r15
0x180072d1b  pop     r14
0x180072d1d  pop     r13
0x180072d1f  pop     rdi
0x180072d20  pop     rsi
0x180072d21  pop     rbx
0x180072d22  pop     rbp
0x180072d23  retn
0x180072d24  mov     ecx, 0C0000022h
0x180072d29  mov     [rbp+var_20], 3
0x180072d30  mov     r9d, 1; int
0x180072d36  cmp     eax, ecx
0x180072d38  jnz     short loc_180072D79
0x180072d3a  mov     [rbp+var_18], ecx
0x180072d3d  mov     r8d, 21Dh; unsigned __int16
0x180072d43  lea     rax, [rbp+var_20]
0x180072d47  mov     edx, ebx; int
0x180072d49  mov     ecx, 2; unsigned int
0x180072d4e  mov     [rsp+60h+var_40], rax; struct tagParam *
0x180072d53  mov     edi, ebx
0x180072d55  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180072d5a  jmp     short loc_180072D0A
0x180072d5c  cmp     rax, rdx
0x180072d5f  jnz     loc_180072C61
0x180072d65  call    cs:__imp_GetCurrentThread
0x180072d6b  mov     rcx, rax; Thread
0x180072d6e  call    cs:__imp_NtImpersonateAnonymousToken
0x180072d74  jmp     loc_180072C80
0x180072d79  mov     ebx, 0Eh
0x180072d7e  mov     [rbp+var_18], eax
0x180072d81  mov     r8d, 21Eh
0x180072d87  jmp     short loc_180072D43
0x180072d89  cmp     eax, 0C00000A6h
0x180072d8e  jz      short loc_180072D9F
0x180072d90  test    eax, eax
0x180072d92  jz      loc_180072C4D
0x180072d98  mov     ebx, 0Eh
0x180072d9d  jmp     short loc_180072DF5
0x180072d9f  mov     [rbp+TokenHandle], rdx
0x180072da3  jmp     loc_180072C4D
0x180072da8  mov     ecx, 0C0000022h
0x180072dad  cmp     eax, ecx
0x180072daf  jz      short loc_180072DBD
0x180072db1  mov     edi, 0Eh
0x180072db6  cmp     eax, 0C00000A5h
0x180072dbb  jnz     short loc_180072DBF
0x180072dbd  mov     edi, ebx
0x180072dbf  mov     r9d, 1; int
0x180072dc5  mov     [rbp+var_18], eax
0x180072dc8  lea     rax, [rbp+var_20]
0x180072dcc  mov     [rbp+var_20], 3
0x180072dd3  mov     r8d, 21Ch; unsigned __int16
0x180072dd9  mov     [rsp+60h+var_40], rax; struct tagParam *
0x180072dde  mov     edx, edi; int
0x180072de0  lea     ecx, [r9+1]; unsigned int
0x180072de4  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180072de9  xor     ecx, ecx
0x180072deb  jmp     loc_180072D07
0x180072df0  mov     ebx, 5
0x180072df5  xor     ecx, ecx
0x180072df7  mov     [rbp+var_18], eax
0x180072dfa  mov     [rbp+TokenHandle], rcx
0x180072dfe  lea     rax, [rbp+var_20]
0x180072e02  mov     r8d, 460h; unsigned __int16
0x180072e08  mov     [rbp+var_20], 3
0x180072e0f  mov     edx, ebx; int
0x180072e11  mov     [rsp+60h+var_40], rax; struct tagParam *
0x180072e16  lea     r9d, [rcx+1]; int
0x180072e1a  lea     ecx, [r9+1]; unsigned int
0x180072e1e  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180072e23  mov     edi, ebx
0x180072e25  jmp     loc_180072D13
```
