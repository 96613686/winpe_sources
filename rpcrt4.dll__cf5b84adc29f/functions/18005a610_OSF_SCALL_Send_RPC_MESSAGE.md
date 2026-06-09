# OSF_SCALL::Send(_RPC_MESSAGE *)

- ea: `0x18005a610`
- end: `0x18005aa81`
- name: `?Send@OSF_SCALL@@UEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `1137`
- prototype: `__int64 __fastcall(OSF_SCALL *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005a098`
- `0x1800b2e30`

## callees

- `0x180026500`
- `0x180034eb4`
- `0x1800591e4`
- `0x18005a610`
- `0x18005aa88`
- `0x18005ab0c`
- `0x180066718`
- `0x180068818`
- `0x1800a72e0`
- `0x1800b411c`
- `0x1800cec91`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18005a70b`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a7a4`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a80d`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a9fd`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a70b`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a7a4`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a80d`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a9fd`
- `ntdll!RtlEnterCriticalSection` at `0x18005a69c`
- `ntdll!RtlEnterCriticalSection` at `0x18005a69c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18005a8ed`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18005a8ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005a8df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005a8df`

## pseudocode

```c
__int64 __fastcall OSF_SCALL::Send(struct _RTL_CRITICAL_SECTION *this, struct _RPC_MESSAGE *a2)
{
  int v2; // r15d
  int v3; // r13d
  HANDLE *p_LockSemaphore; // rcx
  unsigned int v6; // r13d
  bool v7; // zf
  size_t v9; // rbp
  unsigned int BufferDo; // ebx
  int v11; // r12d
  struct _RTL_CRITICAL_SECTION *v12; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *LockSemaphore; // rax
  char *v14; // r13
  __int64 v15; // rdx
  int v16; // r8d
  ULONG_PTR v17; // rax
  unsigned int v18; // eax
  unsigned int v20; // eax
  unsigned int BufferLength; // eax
  __int64 v22; // rdx
  int v23; // r8d
  DWORD CurrentProcessId; // ebx
  unsigned int CommandLineW; // eax
  ULONG_PTR SpinCount; // rax
  __int64 v27; // rdx
  int v28; // r8d
  char *Buffer; // rax
  ULONG_PTR v30; // rcx
  size_t Size; // [rsp+20h] [rbp-78h]
  unsigned int v32; // [rsp+28h] [rbp-70h]
  char *v33; // [rsp+30h] [rbp-68h]
  void *v34; // [rsp+38h] [rbp-60h] BYREF
  HANDLE *v35; // [rsp+40h] [rbp-58h]
  __int128 v36; // [rsp+48h] [rbp-50h] BYREF

  v2 = 0;
  v3 = HIDWORD(this[11].SpinCount) - LODWORD(this[8].OwningThread);
  p_LockSemaphore = &this->LockSemaphore;
  v33 = 0;
  v6 = v3 - 24;
  v34 = 0;
  v7 = (a2->RpcFlags & 0x2000) == 0;
  LODWORD(v9) = 0;
  v35 = p_LockSemaphore;
  BufferDo = 0;
  if ( v7 )
  {
    this[11].LockSemaphore = a2->Buffer;
    v35 = p_LockSemaphore;
  }
  else
  {
    v36 = 0;
    if ( !*p_LockSemaphore )
    {
      p_LockSemaphore = (HANDLE *)*((_QWORD *)this[7].LockSemaphore + 4);
      if ( p_LockSemaphore[35] )
      {
        v36 = *(_OWORD *)((*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *))&this->DebugInfo[6].Type)(this) + 84);
        if ( !(unsigned int)ShouldSkipLogging(2u) && (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
        {
          CurrentProcessId = GetCurrentProcessId();
          CommandLineW = (unsigned int)GetCommandLineW();
          McTemplateU0zdzj_EtwEventWriteTransfer(
            (unsigned int)L"ncacn_http",
            (unsigned int)RPC_EVENTLOG_SYNC_PIPE_USE_ERR,
            CommandLineW,
            CurrentProcessId,
            (__int64)L"ncacn_http",
            (__int64)&v36);
        }
        I_RpcBCacheFree((BCACHE *)((char *)a2->Buffer - 24), v22, v23);
        SpinCount = this[7].SpinCount;
        if ( SpinCount && (*(_DWORD *)(*(_QWORD *)SpinCount + 56LL) & 2) != 0 )
          a2->Buffer = 0;
        return 1764;
      }
    }
    if ( ((__int64)this[18].OwningThread & 0x10) == 0 )
    {
      BufferLength = a2->BufferLength;
      if ( BufferLength < v6 )
        return 1913;
      if ( BufferLength > v6 )
      {
        v9 = (int)(BufferLength % v6);
        if ( BufferLength % v6 )
        {
          LODWORD(Size) = 0;
          BufferDo = OSF_SCALL::GetBufferDo((OSF_SCALL *)p_LockSemaphore, &v34, BufferLength % v6, 0, Size, v32);
          Buffer = (char *)a2->Buffer;
          if ( BufferDo )
          {
            I_RpcBCacheFree((BCACHE *)(Buffer - 24), v27, v28);
            v30 = this[7].SpinCount;
            if ( v30 && (*(_DWORD *)(*(_QWORD *)v30 + 56LL) & 2) != 0 )
              a2->Buffer = 0;
            return BufferDo;
          }
          a2->BufferLength -= v9;
          v33 = (char *)v34;
          memcpy_0(v34, &Buffer[a2->BufferLength], v9);
        }
      }
    }
  }
  v11 = 0;
  LODWORD(v34) = 0;
  v12 = this + 12;
  while ( 1 )
  {
    RtlEnterCriticalSection(v12);
    if ( !this[8].DebugInfo )
    {
      this[8].RecursionCount = 0;
      this[8].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)a2->Buffer;
      this[8].LockCount = a2->BufferLength;
      OSF_SCALL::SetSendBufferSizeIfNecessary((OSF_SCALL *)this);
      LockSemaphore = (struct _RTL_CRITICAL_SECTION_DEBUG *)this[11].LockSemaphore;
      LODWORD(v34) = 1;
      if ( this[8].DebugInfo == LockSemaphore && this[8].LockCount <= v6 )
      {
        v14 = v33;
      }
      else
      {
        v14 = v33;
        if ( (_DWORD)v9 )
        {
          a2->Buffer = v33;
          v20 = v9;
        }
        else
        {
          a2->Buffer = 0;
          v20 = 0;
        }
        a2->BufferLength = v20;
        v2 = 1;
        HIDWORD(this[14].SpinCount) = v20;
      }
      RtlLeaveCriticalSection(this + 12);
      BufferDo = OSF_SCALL::SendNextFragment((OSF_SCALL *)this);
      if ( BufferDo )
      {
        if ( !v2 )
          goto LABEL_10;
        a2->Buffer = this[8].DebugInfo;
        OSF_SCALL::CleanupCallAndSendFault((OSF_SCALL *)this, BufferDo, 0);
      }
      else if ( !v2 )
      {
        goto LABEL_28;
      }
      if ( !(_DWORD)v9 )
        goto LABEL_24;
      if ( !BufferDo )
      {
        v11 = 1913;
        goto LABEL_25;
      }
      goto LABEL_11;
    }
    if ( LODWORD(this->SpinCount) )
    {
      RtlLeaveCriticalSection(this + 12);
      BufferDo = this->SpinCount;
      v2 = 1;
      v14 = v33;
      goto LABEL_24;
    }
    if ( *v35 || this[15].RecursionCount < 4 )
      break;
    LODWORD(this[17].DebugInfo) = 1;
    RtlLeaveCriticalSection(this + 12);
    EVENT::Wait((EVENT *)&this[17].LockSemaphore, -1);
    v12 = this + 12;
    if ( LODWORD(this->SpinCount) )
    {
      BufferDo = this->SpinCount;
      v2 = 1;
      v14 = v33;
      goto LABEL_10;
    }
  }
  v14 = v33;
  if ( (unsigned int)QUEUE::PutOnQueue((QUEUE *)&this[15], a2->Buffer, a2->BufferLength) )
  {
    BufferDo = 14;
  }
  else
  {
    if ( (_DWORD)v9 )
    {
      a2->Buffer = v33;
      v18 = v9;
    }
    else
    {
      a2->Buffer = 0;
      v18 = 0;
    }
    a2->BufferLength = v18;
    HIDWORD(this[14].SpinCount) = v18;
    if ( (_DWORD)v9 )
      v11 = 1913;
  }
  RtlLeaveCriticalSection(this + 12);
LABEL_24:
  if ( BufferDo )
  {
LABEL_10:
    if ( !(_DWORD)v9 )
    {
LABEL_12:
      if ( v2 )
      {
        I_RpcBCacheFree((BCACHE *)((char *)a2->Buffer - 24), v15, v16);
        v17 = this[7].SpinCount;
        if ( v17 )
        {
          if ( (*(_DWORD *)(*(_QWORD *)v17 + 56LL) & 2) != 0 )
            a2->Buffer = 0;
        }
      }
      goto LABEL_27;
    }
LABEL_11:
    I_RpcBCacheFree((BCACHE *)(v14 - 24), v15, v16);
    goto LABEL_12;
  }
LABEL_25:
  if ( v11 )
    BufferDo = v11;
LABEL_27:
  if ( !(_DWORD)v34 )
    return BufferDo;
LABEL_28:
  (*(void (__fastcall **)(struct _RTL_CRITICAL_SECTION *))&this->DebugInfo->EntryCount)(this);
  return BufferDo;
}

```

## disassembly

```asm
0x18005a610  mov     [rsp+arg_10], rbx
0x18005a615  push    rbp
0x18005a616  push    rsi
0x18005a617  push    rdi
0x18005a618  push    r12
0x18005a61a  push    r13
0x18005a61c  push    r14
0x18005a61e  push    r15
0x18005a620  sub     rsp, 60h
0x18005a624  mov     rax, cs:__security_cookie
0x18005a62b  xor     rax, rsp
0x18005a62e  mov     [rsp+98h+var_40], rax
0x18005a633  mov     r13d, [rcx+1DCh]
0x18005a63a  xor     r15d, r15d
0x18005a63d  sub     r13d, [rcx+150h]
0x18005a644  mov     rdi, rcx
0x18005a647  add     rcx, 18h
0x18005a64b  mov     [rsp+98h+var_68], r15
0x18005a650  add     r13d, 0FFFFFFE8h
0x18005a654  mov     [rsp+98h+var_60], r15
0x18005a659  test    dword ptr [rdx+48h], 2000h
0x18005a660  mov     rsi, rdx
0x18005a663  mov     ebp, r15d
0x18005a666  mov     [rsp+98h+var_58], rcx
0x18005a66b  mov     ebx, r15d
0x18005a66e  jnz     loc_18005A899
0x18005a674  mov     rax, [rdx+10h]
0x18005a678  mov     [rdi+1D0h], rax
0x18005a67f  mov     [rsp+98h+var_58], rcx
0x18005a684  mov     r12d, r15d
0x18005a687  mov     dword ptr [rsp+98h+var_60], r15d
0x18005a68c  lea     rax, [rdi+1E0h]
0x18005a693  mov     r14d, 1
0x18005a699  mov     rcx, rax; CriticalSection
0x18005a69c  call    cs:__imp_RtlEnterCriticalSection
0x18005a6a3  nop     dword ptr [rax+rax+00h]
0x18005a6a8  xor     ecx, ecx
0x18005a6aa  cmp     [rdi+140h], rcx
0x18005a6b1  jnz     loc_18005A7FD
0x18005a6b7  mov     [rdi+14Ch], ecx
0x18005a6bd  mov     rcx, rdi; this
0x18005a6c0  mov     rax, [rsi+10h]
0x18005a6c4  mov     [rdi+140h], rax
0x18005a6cb  mov     eax, [rsi+18h]
0x18005a6ce  mov     [rdi+148h], eax
0x18005a6d4  call    ?SetSendBufferSizeIfNecessary@OSF_SCALL@@QEAAXXZ; OSF_SCALL::SetSendBufferSizeIfNecessary(void)
0x18005a6d9  mov     rax, [rdi+1D0h]
0x18005a6e0  mov     dword ptr [rsp+98h+var_60], r14d
0x18005a6e5  cmp     [rdi+140h], rax
0x18005a6ec  jnz     loc_18005A826
0x18005a6f2  cmp     [rdi+148h], r13d
0x18005a6f9  ja      loc_18005A826
0x18005a6ff  mov     r13, [rsp+98h+var_68]
0x18005a704  lea     rcx, [rdi+1E0h]; CriticalSection
0x18005a70b  call    cs:__imp_RtlLeaveCriticalSection
0x18005a712  nop     dword ptr [rax+rax+00h]
0x18005a717  mov     rcx, rdi; this
0x18005a71a  call    ?SendNextFragment@OSF_SCALL@@QEAAJXZ; OSF_SCALL::SendNextFragment(void)
0x18005a71f  mov     ebx, eax
0x18005a721  test    eax, eax
0x18005a723  jz      short loc_18005A76E
0x18005a725  test    r15d, r15d
0x18005a728  jnz     loc_18005AA64
0x18005a72e  test    ebp, ebp
0x18005a730  jz      short loc_18005A73B
0x18005a732  lea     rcx, [r13-18h]; void *
0x18005a736  call    I_RpcBCacheFree
0x18005a73b  test    r15d, r15d
0x18005a73e  jz      short loc_18005A7BF
0x18005a740  mov     rcx, [rsi+10h]
0x18005a744  sub     rcx, 18h; void *
0x18005a748  call    I_RpcBCacheFree
0x18005a74d  mov     rax, [rdi+138h]
0x18005a754  test    rax, rax
0x18005a757  jz      short loc_18005A7BF
0x18005a759  mov     rax, [rax]
0x18005a75c  mov     ecx, [rax+38h]
0x18005a75f  test    cl, 2
0x18005a762  jz      short loc_18005A7BF
0x18005a764  mov     qword ptr [rsi+10h], 0
0x18005a76c  jmp     short loc_18005A7BF
0x18005a76e  test    r15d, r15d
0x18005a771  jz      short loc_18005A7C6
0x18005a773  test    ebp, ebp
0x18005a775  jz      short loc_18005A7B0
0x18005a777  test    ebx, ebx
0x18005a779  jnz     short loc_18005A732
0x18005a77b  mov     r12d, 779h
0x18005a781  jmp     short loc_18005A7B8
0x18005a783  mov     [rsi+10h], r13
0x18005a787  mov     eax, ebp
0x18005a789  mov     [rsi+18h], eax
0x18005a78c  test    ebp, ebp
0x18005a78e  mov     [rdi+254h], eax
0x18005a794  mov     eax, 779h
0x18005a799  cmovnz  r12d, eax
0x18005a79d  lea     rcx, [rdi+1E0h]; CriticalSection
0x18005a7a4  call    cs:__imp_RtlLeaveCriticalSection
0x18005a7ab  nop     dword ptr [rax+rax+00h]
0x18005a7b0  test    ebx, ebx
0x18005a7b2  jnz     loc_18005A72E
0x18005a7b8  test    r12d, r12d
0x18005a7bb  cmovnz  ebx, r12d
0x18005a7bf  cmp     dword ptr [rsp+98h+var_60], 0
0x18005a7c4  jz      short loc_18005A7D5
0x18005a7c6  mov     rax, [rdi]
0x18005a7c9  mov     rcx, rdi
0x18005a7cc  mov     rax, [rax+20h]
0x18005a7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a7d5  mov     eax, ebx
0x18005a7d7  mov     rcx, [rsp+98h+var_40]
0x18005a7dc  xor     rcx, rsp; StackCookie
0x18005a7df  call    __security_check_cookie
0x18005a7e4  mov     rbx, [rsp+98h+arg_10]
0x18005a7ec  add     rsp, 60h
0x18005a7f0  pop     r15
0x18005a7f2  pop     r14
0x18005a7f4  pop     r13
0x18005a7f6  pop     r12
0x18005a7f8  pop     rdi
0x18005a7f9  pop     rsi
0x18005a7fa  pop     rbp
0x18005a7fb  retn
0x18005a7fd  cmp     [rdi+20h], ecx
0x18005a800  jz      loc_18005A9DC
0x18005a806  lea     rcx, [rdi+1E0h]; CriticalSection
0x18005a80d  call    cs:__imp_RtlLeaveCriticalSection
0x18005a814  nop     dword ptr [rax+rax+00h]
0x18005a819  mov     ebx, [rdi+20h]
0x18005a81c  mov     r15d, r14d
0x18005a81f  mov     r13, [rsp+98h+var_68]
0x18005a824  jmp     short loc_18005A7B0
0x18005a826  mov     r13, [rsp+98h+var_68]
0x18005a82b  test    ebp, ebp
0x18005a82d  jz      short loc_18005A846
0x18005a82f  mov     [rsi+10h], r13
0x18005a833  mov     eax, ebp
0x18005a835  mov     [rsi+18h], eax
0x18005a838  mov     r15d, r14d
0x18005a83b  mov     [rdi+254h], eax
0x18005a841  jmp     loc_18005A704
0x18005a846  mov     [rsi+10h], r12
0x18005a84a  xor     eax, eax
0x18005a84c  jmp     short loc_18005A835
0x18005a84e  mov     rax, [rdi+130h]
0x18005a855  mov     rcx, [rax+20h]; this
0x18005a859  cmp     [rcx+118h], r15
0x18005a860  jnz     short loc_18005A8A8
0x18005a862  mov     eax, [rdi+2E0h]
0x18005a868  test    al, 10h
0x18005a86a  jnz     loc_18005A684
0x18005a870  mov     eax, [rdx+18h]
0x18005a873  cmp     eax, r13d
0x18005a876  jnb     loc_18005A953
0x18005a87c  mov     eax, 779h
0x18005a881  jmp     loc_18005A7D7
0x18005a886  test    ebp, ebp
0x18005a888  jnz     loc_18005A783
0x18005a88e  mov     [rsi+10h], r12
0x18005a892  xor     eax, eax
0x18005a894  jmp     loc_18005A789
0x18005a899  xorps   xmm0, xmm0
0x18005a89c  movups  [rsp+98h+var_50], xmm0
0x18005a8a1  cmp     [rcx], r15
0x18005a8a4  jnz     short loc_18005A862
0x18005a8a6  jmp     short loc_18005A84E
0x18005a8a8  mov     rax, [rdi]
0x18005a8ab  mov     rcx, rdi
0x18005a8ae  mov     rax, [rax+120h]
0x18005a8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8ba  mov     ecx, 2; unsigned int
0x18005a8bf  movups  xmm0, xmmword ptr [rax+54h]
0x18005a8c3  movdqu  [rsp+98h+var_50], xmm0
0x18005a8c9  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x18005a8ce  test    eax, eax
0x18005a8d0  jnz     short loc_18005A921
0x18005a8d2  lea     r14d, [rax+1]
0x18005a8d6  test    cs:Microsoft_Windows_RPC_EventsEnableBits, r14b
0x18005a8dd  jz      short loc_18005A921
0x18005a8df  call    cs:__imp_GetCurrentProcessId
0x18005a8e6  nop     dword ptr [rax+rax+00h]
0x18005a8eb  mov     ebx, eax
0x18005a8ed  call    cs:__imp_GetCommandLineW
0x18005a8f4  nop     dword ptr [rax+rax+00h]
0x18005a8f9  lea     rcx, [rsp+98h+var_50]
0x18005a8fe  mov     r9d, ebx
0x18005a901  mov     [rsp+98h+var_70], rcx
0x18005a906  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x18005a90d  lea     rcx, aNcacnHttp; "ncacn_http"
0x18005a914  mov     r8, rax
0x18005a917  mov     [rsp+98h+Size], rcx
0x18005a91c  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x18005a921  mov     rcx, [rsi+10h]
0x18005a925  sub     rcx, 18h; void *
0x18005a929  call    I_RpcBCacheFree
0x18005a92e  mov     rax, [rdi+138h]
0x18005a935  test    rax, rax
0x18005a938  jz      short loc_18005A949
0x18005a93a  mov     rax, [rax]
0x18005a93d  mov     ecx, [rax+38h]
0x18005a940  test    cl, 2
0x18005a943  jz      short loc_18005A949
0x18005a945  mov     [rsi+10h], r15
0x18005a949  mov     eax, 6E4h
0x18005a94e  jmp     loc_18005A7D7
0x18005a953  jbe     loc_18005A684
0x18005a959  xor     edx, edx
0x18005a95b  div     r13d
0x18005a95e  movsxd  rbp, edx
0x18005a961  test    edx, edx
0x18005a963  jz      loc_18005A684
0x18005a969  xor     r9d, r9d; int
0x18005a96c  mov     dword ptr [rsp+98h+Size], r15d; Size
0x18005a971  mov     r8d, ebp; unsigned int
0x18005a974  lea     rdx, [rsp+98h+var_60]; void **
0x18005a979  call    ?GetBufferDo@OSF_SCALL@@QEAAJPEAPEAXIHIK@Z; OSF_SCALL::GetBufferDo(void * *,uint,int,uint,ulong)
0x18005a97e  mov     ebx, eax
0x18005a980  mov     rax, [rsi+10h]
0x18005a984  test    ebx, ebx
0x18005a986  jz      short loc_18005A9B9
0x18005a988  lea     rcx, [rax-18h]; void *
0x18005a98c  call    I_RpcBCacheFree
0x18005a991  mov     rcx, [rdi+138h]
0x18005a998  test    rcx, rcx
0x18005a99b  jz      loc_18005A7D5
0x18005a9a1  mov     rcx, [rcx]
0x18005a9a4  mov     edx, [rcx+38h]
0x18005a9a7  test    dl, 2
0x18005a9aa  jz      loc_18005A7D5
0x18005a9b0  mov     [rsi+10h], r15
0x18005a9b4  jmp     loc_18005A7D5
0x18005a9b9  sub     [rsi+18h], ebp
0x18005a9bc  mov     r8, rbp; Size
0x18005a9bf  mov     edx, [rsi+18h]
0x18005a9c2  add     rdx, rax; Src
0x18005a9c5  mov     rax, [rsp+98h+var_60]
0x18005a9ca  mov     rcx, rax; void *
0x18005a9cd  mov     [rsp+98h+var_68], rax
0x18005a9d2  call    memcpy_0
0x18005a9d7  jmp     loc_18005A684
0x18005a9dc  mov     rax, [rsp+98h+var_58]
0x18005a9e1  cmp     [rax], rcx
0x18005a9e4  jnz     short loc_18005AA39
0x18005a9e6  cmp     dword ptr [rdi+264h], 4
0x18005a9ed  jl      short loc_18005AA39
0x18005a9ef  lea     rcx, [rdi+1E0h]; CriticalSection
0x18005a9f6  mov     [rdi+2A8h], r14d
0x18005a9fd  call    cs:__imp_RtlLeaveCriticalSection
0x18005aa04  nop     dword ptr [rax+rax+00h]
0x18005aa09  lea     rcx, [rdi+2C0h]; this
0x18005aa10  or      edx, 0FFFFFFFFh; int
0x18005aa13  call    ?Wait@EVENT@@QEAAHJ@Z; EVENT::Wait(long)
0x18005aa18  lea     rax, [rdi+1E0h]
0x18005aa1f  cmp     [rdi+20h], r12d
0x18005aa23  jz      loc_18005A699
0x18005aa29  mov     ebx, [rdi+20h]
0x18005aa2c  mov     r15d, r14d
0x18005aa2f  mov     r13, [rsp+98h+var_68]
0x18005aa34  jmp     loc_18005A72E
0x18005aa39  mov     r8d, [rsi+18h]; unsigned int
0x18005aa3d  lea     rcx, [rdi+258h]; this
0x18005aa44  mov     rdx, [rsi+10h]; void *
0x18005aa48  call    ?PutOnQueue@QUEUE@@QEAAHPEAXI@Z; QUEUE::PutOnQueue(void *,uint)
0x18005aa4d  mov     r13, [rsp+98h+var_68]
0x18005aa52  test    eax, eax
0x18005aa54  jz      loc_18005A886
0x18005aa5a  mov     ebx, 0Eh
0x18005aa5f  jmp     loc_18005A79D
0x18005aa64  mov     rax, [rdi+140h]
0x18005aa6b  xor     r8d, r8d; int
0x18005aa6e  mov     edx, ebx; int
0x18005aa70  mov     [rsi+10h], rax
0x18005aa74  mov     rcx, rdi; this
0x18005aa77  call    ?CleanupCallAndSendFault@OSF_SCALL@@QEAAXJH@Z; OSF_SCALL::CleanupCallAndSendFault(long,int)
0x18005aa7c  jmp     loc_18005A773
```
