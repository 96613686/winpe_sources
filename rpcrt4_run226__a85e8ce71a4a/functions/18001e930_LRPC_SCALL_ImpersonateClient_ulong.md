# LRPC_SCALL::ImpersonateClient(ulong)

- ea: `0x18001e930`
- end: `0x18001eb99`
- name: `?ImpersonateClient@LRPC_SCALL@@UEAAJK@Z`
- size: `617`
- prototype: `__int64 __fastcall(LRPC_SCALL *this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007d050`
- `0x1800a81d0`

## callees

- `0x18001d750`
- `0x18001e930`
- `0x1800281b0`
- `0x1800283bc`
- `0x18008a244`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18001eab6`
- `ntdll!NtSetInformationThread` at `0x18001eae9`
- `ntdll!NtSetInformationThread` at `0x18001eab6`
- `ntdll!NtSetInformationThread` at `0x18001eae9`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18001e98e`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18001e9de`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18001e98e`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18001e9de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ea9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001eace`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ea9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001eace`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::ImpersonateClient(LRPC_SCALL *this, int a2)
{
  struct THREAD *v4; // rax
  int v5; // ebx
  int v6; // eax
  unsigned int v7; // ebx
  struct THREAD *v8; // rax
  bool v10; // zf
  bool v11; // zf
  __int64 v12; // rsi
  __int64 v13; // rsi
  HANDLE v14; // rax
  HANDLE CurrentThread; // rax
  int v16; // ebx
  _DWORD v17[10]; // [rsp+30h] [rbp-28h] BYREF

  v4 = ThreadSelf();
  if ( !v4 )
    return 14;
  *((_QWORD *)v4 + 5) = -1;
  if ( !*((_QWORD *)this + 74) )
  {
    v5 = a2 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
      {
        v7 = 1764;
        goto LABEL_8;
      }
      v6 = NtAlpcImpersonateClientOfPort(*(_QWORD *)(*((_QWORD *)this + 38) + 48LL), *((_QWORD *)this + 55), 1);
      if ( !v6 )
        goto LABEL_6;
      v10 = v6 == -1073741670;
      if ( v6 > -1073741670 )
      {
        if ( v6 == -1073741281 || v6 == -1073740030 )
          goto LABEL_23;
        v11 = v6 == -1073740029;
LABEL_22:
        if ( v11 )
        {
LABEL_23:
          v7 = 1765;
          goto LABEL_24;
        }
LABEL_15:
        v7 = 5;
LABEL_24:
        v17[2] = v6;
        v17[0] = 3;
        RpcpErrorAddRecord(2u, v7, 0x4BAu, 1, (struct tagParam *)v17);
        goto LABEL_7;
      }
    }
    else
    {
      v6 = NtAlpcImpersonateClientOfPort(*(_QWORD *)(*((_QWORD *)this + 38) + 48LL), *((_QWORD *)this + 55), 0);
      if ( !v6 )
      {
LABEL_6:
        v7 = 0;
        goto LABEL_7;
      }
      v10 = v6 == -1073741670;
      if ( v6 > -1073741670 )
      {
        if ( v6 != -1073741659 && (v6 == -1073741281 || v6 == -1073740030 || v6 == -1073740029) )
          goto LABEL_23;
        goto LABEL_15;
      }
    }
    if ( v10 )
    {
      v7 = 1721;
      goto LABEL_24;
    }
    switch ( v6 )
    {
      case -1073741813:
        goto LABEL_23;
      case -1073741801:
        v7 = 14;
        goto LABEL_24;
      case -1073741790:
        goto LABEL_23;
    }
    v11 = v6 == -1073741769;
    goto LABEL_22;
  }
  v12 = *((_QWORD *)this + 74);
  if ( (*((_DWORD *)this + 58) & 0x40) != 0 )
  {
    CurrentThread = GetCurrentThread();
    NtSetInformationThread(CurrentThread, ThreadImpersonationToken, (PVOID)(v12 + 216), 8u);
    return 0;
  }
  else
  {
    v13 = *(_QWORD *)(v12 + 24);
    if ( !*(_DWORD *)(v13 + 148) )
    {
      v16 = a2 - 1;
      if ( v16 )
      {
        if ( v16 != 1 )
        {
          v7 = 1764;
          goto LABEL_8;
        }
        v7 = LRPC_SASSOCIATION::ImpersonateClientEx(
               *((LRPC_SASSOCIATION **)this + 38),
               *((struct _PORT_MESSAGE **)this + 55));
      }
      else
      {
        v7 = LRPC_SASSOCIATION::ImpersonateClient(
               *((LRPC_SASSOCIATION **)this + 38),
               *((struct _PORT_MESSAGE **)this + 55));
      }
LABEL_7:
      if ( !v7 )
        return v7;
LABEL_8:
      v8 = ThreadSelf();
      if ( v8 )
      {
        if ( *((_QWORD *)v8 + 5) )
          *((_QWORD *)v8 + 5) = 0;
      }
      return v7;
    }
    v14 = GetCurrentThread();
    NtSetInformationThread(v14, ThreadImpersonationToken, (PVOID)(v13 + 160), 8u);
    return 0;
  }
}

```

## disassembly

```asm
0x18001e930  mov     [rsp+arg_8], rbx
0x18001e935  push    rdi
0x18001e936  sub     rsp, 50h
0x18001e93a  mov     ebx, edx
0x18001e93c  mov     rdi, rcx
0x18001e93f  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18001e944  test    rax, rax
0x18001e947  jz      loc_18001EB8F
0x18001e94d  mov     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x18001e955  cmp     qword ptr [rdi+250h], 0
0x18001e95d  mov     [rsp+58h+arg_0], rsi
0x18001e962  jnz     loc_18001EA7B
0x18001e968  sub     ebx, 1
0x18001e96b  jz      short loc_18001E9C9
0x18001e96d  cmp     ebx, 1
0x18001e970  jnz     loc_18001EB22
0x18001e976  mov     rcx, [rdi+130h]
0x18001e97d  mov     r8d, 1
0x18001e983  mov     rdx, [rdi+1B8h]
0x18001e98a  mov     rcx, [rcx+30h]
0x18001e98e  call    cs:__imp_NtAlpcImpersonateClientOfPort
0x18001e994  test    eax, eax
0x18001e996  jnz     short loc_18001EA01
0x18001e998  xor     ebx, ebx
0x18001e99a  test    ebx, ebx
0x18001e99c  jz      short loc_18001E9B7
0x18001e99e  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18001e9a3  test    rax, rax
0x18001e9a6  jz      short loc_18001E9B7
0x18001e9a8  cmp     qword ptr [rax+28h], 0
0x18001e9ad  jz      short loc_18001E9B7
0x18001e9af  mov     qword ptr [rax+28h], 0
0x18001e9b7  mov     rsi, [rsp+58h+arg_0]
0x18001e9bc  mov     eax, ebx
0x18001e9be  mov     rbx, [rsp+58h+arg_8]
0x18001e9c3  add     rsp, 50h
0x18001e9c7  pop     rdi
0x18001e9c8  retn
0x18001e9c9  mov     rcx, [rdi+130h]
0x18001e9d0  xor     r8d, r8d
0x18001e9d3  mov     rdx, [rdi+1B8h]
0x18001e9da  mov     rcx, [rcx+30h]
0x18001e9de  call    cs:__imp_NtAlpcImpersonateClientOfPort
0x18001e9e4  test    eax, eax
0x18001e9e6  jz      short loc_18001E998
0x18001e9e8  cmp     eax, 0C000009Ah
0x18001e9ed  jle     short loc_18001EA08
0x18001e9ef  cmp     eax, 0C00000A5h
0x18001e9f4  jnz     loc_18001EB69
0x18001e9fa  mov     ebx, 5
0x18001e9ff  jmp     short loc_18001EA33
0x18001ea01  cmp     eax, 0C000009Ah
0x18001ea06  jg      short loc_18001EA66
0x18001ea08  jz      loc_18001EB5F
0x18001ea0e  cmp     eax, 0C000000Bh
0x18001ea13  jz      short loc_18001EA2E
0x18001ea15  cmp     eax, 0C0000017h
0x18001ea1a  jz      loc_18001EB55
0x18001ea20  cmp     eax, 0C0000022h
0x18001ea25  jz      short loc_18001EA2E
0x18001ea27  cmp     eax, 0C0000037h
0x18001ea2c  jnz     short loc_18001E9FA
0x18001ea2e  mov     ebx, 6E5h
0x18001ea33  mov     [rsp+58h+var_20], eax
0x18001ea37  mov     r9d, 1; int
0x18001ea3d  lea     rax, [rsp+58h+var_28]
0x18001ea42  mov     [rsp+58h+var_28], 3
0x18001ea4a  mov     r8d, 4BAh; unsigned __int16
0x18001ea50  mov     [rsp+58h+var_38], rax; struct tagParam *
0x18001ea55  mov     edx, ebx; int
0x18001ea57  mov     ecx, 2; unsigned int
0x18001ea5c  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18001ea61  jmp     loc_18001E99A
0x18001ea66  cmp     eax, 0C000021Fh
0x18001ea6b  jz      short loc_18001EA2E
0x18001ea6d  cmp     eax, 0C0000702h
0x18001ea72  jz      short loc_18001EA2E
0x18001ea74  cmp     eax, 0C0000703h
0x18001ea79  jmp     short loc_18001EA2C
0x18001ea7b  mov     eax, [rdi+0E8h]
0x18001ea81  mov     rsi, [rdi+250h]
0x18001ea88  test    al, 40h
0x18001ea8a  jnz     short loc_18001EACE
0x18001ea8c  mov     rsi, [rsi+18h]
0x18001ea90  cmp     dword ptr [rsi+94h], 0
0x18001ea97  jz      short loc_18001EB03
0x18001ea99  xor     ebx, ebx
0x18001ea9b  call    cs:__imp_GetCurrentThread
0x18001eaa1  lea     r8, [rsi+0A0h]; ThreadInformation
0x18001eaa8  mov     edx, 5; ThreadInformationClass
0x18001eaad  mov     rcx, rax; ThreadHandle
0x18001eab0  mov     r9d, 8; ThreadInformationLength
0x18001eab6  call    cs:__imp_NtSetInformationThread
0x18001eabc  mov     rsi, [rsp+58h+arg_0]
0x18001eac1  mov     eax, ebx
0x18001eac3  mov     rbx, [rsp+58h+arg_8]
0x18001eac8  add     rsp, 50h
0x18001eacc  pop     rdi
0x18001eacd  retn
0x18001eace  call    cs:__imp_GetCurrentThread
0x18001ead4  lea     r8, [rsi+0D8h]; ThreadInformation
0x18001eadb  mov     edx, 5; ThreadInformationClass
0x18001eae0  mov     rcx, rax; ThreadHandle
0x18001eae3  mov     r9d, 8; ThreadInformationLength
0x18001eae9  call    cs:__imp_NtSetInformationThread
0x18001eaef  mov     rsi, [rsp+58h+arg_0]
0x18001eaf4  xor     ebx, ebx
0x18001eaf6  mov     eax, ebx
0x18001eaf8  mov     rbx, [rsp+58h+arg_8]
0x18001eafd  add     rsp, 50h
0x18001eb01  pop     rdi
0x18001eb02  retn
0x18001eb03  sub     ebx, 1
0x18001eb06  jnz     short loc_18001EB2C
0x18001eb08  mov     rdx, [rdi+1B8h]; struct _PORT_MESSAGE *
0x18001eb0f  mov     rcx, [rdi+130h]; this
0x18001eb16  call    ?ImpersonateClient@LRPC_SASSOCIATION@@QEAAJPEAU_PORT_MESSAGE@@@Z; LRPC_SASSOCIATION::ImpersonateClient(_PORT_MESSAGE *)
0x18001eb1b  mov     ebx, eax
0x18001eb1d  jmp     loc_18001E99A
0x18001eb22  mov     ebx, 6E4h
0x18001eb27  jmp     loc_18001E99E
0x18001eb2c  cmp     ebx, 1
0x18001eb2f  jz      short loc_18001EB3B
0x18001eb31  mov     ebx, 6E4h
0x18001eb36  jmp     loc_18001E99E
0x18001eb3b  mov     rdx, [rdi+1B8h]; struct _PORT_MESSAGE *
0x18001eb42  mov     rcx, [rdi+130h]; this
0x18001eb49  call    ?ImpersonateClientEx@LRPC_SASSOCIATION@@QEAAJPEAU_PORT_MESSAGE@@@Z; LRPC_SASSOCIATION::ImpersonateClientEx(_PORT_MESSAGE *)
0x18001eb4e  mov     ebx, eax
0x18001eb50  jmp     loc_18001E99A
0x18001eb55  mov     ebx, 0Eh
0x18001eb5a  jmp     loc_18001EA33
0x18001eb5f  mov     ebx, 6B9h
0x18001eb64  jmp     loc_18001EA33
0x18001eb69  cmp     eax, 0C000021Fh
0x18001eb6e  jz      loc_18001EA2E
0x18001eb74  cmp     eax, 0C0000702h
0x18001eb79  jz      loc_18001EA2E
0x18001eb7f  cmp     eax, 0C0000703h
0x18001eb84  jnz     loc_18001E9FA
0x18001eb8a  jmp     loc_18001EA2E
0x18001eb8f  mov     eax, 0Eh
0x18001eb94  jmp     loc_18001E9BE
```
