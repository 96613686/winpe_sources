# LRPC_CASSOCIATION::OpenSecurityContextWorker(tagLrpcImpersonationType,int,LRPC_C_SECURITY_CONTEXT *,void *)

- ea: `0x180071ad0`
- end: `0x180071d45`
- name: `?OpenSecurityContextWorker@LRPC_CASSOCIATION@@QEAAJW4tagLrpcImpersonationType@@HPEAVLRPC_C_SECURITY_CONTEXT@@PEAX@Z`
- size: `629`
- prototype: `__int64 __fastcall(__int64, int, char, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029fc0`
- `0x18002cc94`
- `0x1800719a0`

## callees

- `0x180028670`
- `0x1800295d8`
- `0x180071ad0`
- `0x180071d4c`

## import_xrefs

- `ntdll!NtAlpcCreateSecurityContext` at `0x180071bef`
- `ntdll!NtAlpcCreateSecurityContext` at `0x180071bef`
- `ntdll!NtImpersonateAnonymousToken` at `0x180071c83`
- `ntdll!NtImpersonateAnonymousToken` at `0x180071c83`
- `ntdll!NtOpenThreadToken` at `0x180071b19`
- `ntdll!NtOpenThreadToken` at `0x180071b19`
- `ntdll!NtSetInformationThread` at `0x180071b7c`
- `ntdll!NtSetInformationThread` at `0x180071b7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071afe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071b61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071c74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071afe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071b61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071c74`

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
    if ( dword_1800FE624 )
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
0x180071ad0  push    rbp
0x180071ad2  push    rbx
0x180071ad3  push    rsi
0x180071ad4  push    rdi
0x180071ad5  push    r13
0x180071ad7  push    r14
0x180071ad9  push    r15
0x180071adb  mov     rbp, rsp
0x180071ade  sub     rsp, 60h
0x180071ae2  mov     rsi, r9
0x180071ae5  mov     [rbp+TokenHandle], 0
0x180071aed  mov     r15d, r8d
0x180071af0  mov     [rbp+ThreadInformation], 0
0x180071af8  mov     r13d, edx
0x180071afb  mov     r14, rcx
0x180071afe  call    cs:__imp_GetCurrentThread
0x180071b05  nop     dword ptr [rax+rax+00h]
0x180071b0a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180071b0e  mov     r8b, 1; OpenAsSelf
0x180071b11  mov     rcx, rax; ThreadHandle
0x180071b14  mov     edx, 0Ch; DesiredAccess
0x180071b19  call    cs:__imp_NtOpenThreadToken
0x180071b20  nop     dword ptr [rax+rax+00h]
0x180071b25  cmp     eax, 0C0000022h
0x180071b2a  jz      loc_180071D0B
0x180071b30  mov     edx, 0FFFFFFFEh
0x180071b35  mov     ecx, 0FFFFFFFDh
0x180071b3a  cmp     eax, 0C000007Ch
0x180071b3f  jnz     loc_180071CA4
0x180071b45  mov     [rbp+TokenHandle], rcx
0x180071b49  mov     rax, [rbp+arg_20]
0x180071b4d  xor     edi, edi
0x180071b4f  lea     ebx, [rdi+5]
0x180071b52  cmp     rax, rcx
0x180071b55  jnz     loc_180071C6B
0x180071b5b  xor     eax, eax
0x180071b5d  mov     [rbp+ThreadInformation], rax
0x180071b61  call    cs:__imp_GetCurrentThread
0x180071b68  nop     dword ptr [rax+rax+00h]
0x180071b6d  mov     r9d, 8; ThreadInformationLength
0x180071b73  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180071b77  mov     rcx, rax; ThreadHandle
0x180071b7a  mov     edx, ebx; ThreadInformationClass
0x180071b7c  call    cs:__imp_NtSetInformationThread
0x180071b83  nop     dword ptr [rax+rax+00h]
0x180071b88  test    eax, eax
0x180071b8a  js      loc_180071C33
0x180071b90  mov     rax, [rsi+8]
0x180071b94  mov     qword ptr [rax+10h], 0
0x180071b9c  mov     rax, [rsi+8]
0x180071ba0  mov     dword ptr [rax], 20000h
0x180071ba6  lea     eax, [r13-1]
0x180071baa  mov     [rsi+34h], eax
0x180071bad  mov     byte ptr [rsi+38h], 0
0x180071bb1  mov     [rsi+39h], r15b
0x180071bb5  cmp     cs:dword_1800FE624, 0
0x180071bbc  jz      short loc_180071BE2
0x180071bbe  mov     r9, [rsi+8]
0x180071bc2  mov     dl, 43h ; 'C'; unsigned __int8
0x180071bc4  mov     r8, [r14+88h]
0x180071bcb  mov     cl, 4Ch ; 'L'; unsigned __int8
0x180071bcd  or      r8, 1; __int64
0x180071bd1  mov     eax, [r9]
0x180071bd4  mov     r9, [r9+10h]; __int64
0x180071bd8  mov     [rsp+60h+var_40], rax; __int64
0x180071bdd  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x180071be2  mov     r8, [rsi+8]
0x180071be6  xor     edx, edx
0x180071be8  mov     rcx, [r14+88h]
0x180071bef  call    cs:__imp_NtAlpcCreateSecurityContext
0x180071bf6  nop     dword ptr [rax+rax+00h]
0x180071bfb  mov     rcx, [rsi+8]
0x180071bff  mov     dword ptr [rcx], 0
0x180071c05  test    eax, eax
0x180071c07  js      loc_180071CC3
0x180071c0d  mov     rax, [rsi+8]
0x180071c11  mov     rcx, [rax+10h]
0x180071c15  mov     [rsi], rcx
0x180071c18  mov     rcx, [rbp+TokenHandle]; void *
0x180071c1c  call    ?RestoreOldThreadToken@@YAXPEAX@Z; RestoreOldThreadToken(void *)
0x180071c21  mov     eax, edi
0x180071c23  add     rsp, 60h
0x180071c27  pop     r15
0x180071c29  pop     r14
0x180071c2b  pop     r13
0x180071c2d  pop     rdi
0x180071c2e  pop     rsi
0x180071c2f  pop     rbx
0x180071c30  pop     rbp
0x180071c31  retn
0x180071c33  mov     ecx, 0C0000022h
0x180071c38  mov     [rbp+var_20], 3
0x180071c3f  mov     r9d, 1; int
0x180071c45  cmp     eax, ecx
0x180071c47  jnz     short loc_180071C94
0x180071c49  mov     [rbp+var_18], ecx
0x180071c4c  mov     r8d, 21Dh; unsigned __int16
0x180071c52  lea     rax, [rbp+var_20]
0x180071c56  mov     edx, ebx; int
0x180071c58  mov     ecx, 2; unsigned int
0x180071c5d  mov     [rsp+60h+var_40], rax; struct tagParam *
0x180071c62  mov     edi, ebx
0x180071c64  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180071c69  jmp     short loc_180071C18
0x180071c6b  cmp     rax, rdx
0x180071c6e  jnz     loc_180071B5D
0x180071c74  call    cs:__imp_GetCurrentThread
0x180071c7b  nop     dword ptr [rax+rax+00h]
0x180071c80  mov     rcx, rax; Thread
0x180071c83  call    cs:__imp_NtImpersonateAnonymousToken
0x180071c8a  nop     dword ptr [rax+rax+00h]
0x180071c8f  jmp     loc_180071B88
0x180071c94  mov     ebx, 0Eh
0x180071c99  mov     [rbp+var_18], eax
0x180071c9c  mov     r8d, 21Eh
0x180071ca2  jmp     short loc_180071C52
0x180071ca4  cmp     eax, 0C00000A6h
0x180071ca9  jz      short loc_180071CBA
0x180071cab  test    eax, eax
0x180071cad  jz      loc_180071B49
0x180071cb3  mov     ebx, 0Eh
0x180071cb8  jmp     short loc_180071D10
0x180071cba  mov     [rbp+TokenHandle], rdx
0x180071cbe  jmp     loc_180071B49
0x180071cc3  mov     ecx, 0C0000022h
0x180071cc8  cmp     eax, ecx
0x180071cca  jz      short loc_180071CD8
0x180071ccc  mov     edi, 0Eh
0x180071cd1  cmp     eax, 0C00000A5h
0x180071cd6  jnz     short loc_180071CDA
0x180071cd8  mov     edi, ebx
0x180071cda  mov     r9d, 1; int
0x180071ce0  mov     [rbp+var_18], eax
0x180071ce3  lea     rax, [rbp+var_20]
0x180071ce7  mov     [rbp+var_20], 3
0x180071cee  mov     r8d, 21Ch; unsigned __int16
0x180071cf4  mov     [rsp+60h+var_40], rax; struct tagParam *
0x180071cf9  mov     edx, edi; int
0x180071cfb  lea     ecx, [r9+1]; unsigned int
0x180071cff  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180071d04  xor     ecx, ecx
0x180071d06  jmp     loc_180071C15
0x180071d0b  mov     ebx, 5
0x180071d10  xor     ecx, ecx
0x180071d12  mov     [rbp+var_18], eax
0x180071d15  mov     [rbp+TokenHandle], rcx
0x180071d19  lea     rax, [rbp+var_20]
0x180071d1d  mov     r8d, 460h; unsigned __int16
0x180071d23  mov     [rbp+var_20], 3
0x180071d2a  mov     edx, ebx; int
0x180071d2c  mov     [rsp+60h+var_40], rax; struct tagParam *
0x180071d31  lea     r9d, [rcx+1]; int
0x180071d35  lea     ecx, [r9+1]; unsigned int
0x180071d39  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180071d3e  mov     edi, ebx
0x180071d40  jmp     loc_180071C21
```
