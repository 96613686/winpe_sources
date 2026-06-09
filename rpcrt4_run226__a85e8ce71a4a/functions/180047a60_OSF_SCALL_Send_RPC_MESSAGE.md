# OSF_SCALL::Send(_RPC_MESSAGE *)

- ea: `0x180047a60`
- end: `0x180047ea2`
- name: `?Send@OSF_SCALL@@UEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `1090`
- prototype: `__int64 __fastcall(OSF_SCALL *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800474f4`
- `0x1800af120`

## callees

- `0x180025280`
- `0x180046d74`
- `0x180047a60`
- `0x180047ea8`
- `0x180047f28`
- `0x180061948`
- `0x18006203c`
- `0x1800637cc`
- `0x1800a3fd4`
- `0x1800b03bc`
- `0x1800ca031`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180047b55`
- `ntdll!RtlLeaveCriticalSection` at `0x180047be8`
- `ntdll!RtlLeaveCriticalSection` at `0x180047c46`
- `ntdll!RtlLeaveCriticalSection` at `0x180047e24`
- `ntdll!RtlLeaveCriticalSection` at `0x180047b55`
- `ntdll!RtlLeaveCriticalSection` at `0x180047be8`
- `ntdll!RtlLeaveCriticalSection` at `0x180047c46`
- `ntdll!RtlLeaveCriticalSection` at `0x180047e24`
- `ntdll!RtlEnterCriticalSection` at `0x180047aec`
- `ntdll!RtlEnterCriticalSection` at `0x180047aec`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180047d1a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180047d1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180047d12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180047d12`

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
  ULONG_PTR v15; // rax
  unsigned int v16; // eax
  unsigned int v18; // eax
  unsigned int BufferLength; // eax
  DWORD CurrentProcessId; // ebx
  unsigned int CommandLineW; // eax
  ULONG_PTR SpinCount; // rax
  char *Buffer; // rax
  ULONG_PTR v24; // rcx
  size_t Size; // [rsp+20h] [rbp-78h]
  char *v26; // [rsp+30h] [rbp-68h]
  void *v27; // [rsp+38h] [rbp-60h] BYREF
  HANDLE *v28; // [rsp+40h] [rbp-58h]
  __int128 v29; // [rsp+48h] [rbp-50h] BYREF

  v2 = 0;
  v3 = HIDWORD(this[11].SpinCount) - LODWORD(this[8].OwningThread);
  p_LockSemaphore = &this->LockSemaphore;
  v26 = 0;
  v6 = v3 - 24;
  v27 = 0;
  v7 = (a2->RpcFlags & 0x2000) == 0;
  LODWORD(v9) = 0;
  v28 = p_LockSemaphore;
  BufferDo = 0;
  if ( v7 )
  {
    this[11].LockSemaphore = a2->Buffer;
    v28 = p_LockSemaphore;
  }
  else
  {
    v29 = 0;
    if ( !*p_LockSemaphore )
    {
      p_LockSemaphore = (HANDLE *)*((_QWORD *)this[7].LockSemaphore + 4);
      if ( p_LockSemaphore[35] )
      {
        v29 = *(_OWORD *)((*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *))&this->DebugInfo[6].Type)(this) + 84);
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
            (__int64)&v29);
        }
        I_RpcBCacheFree((char *)a2->Buffer - 24);
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
          BufferDo = OSF_SCALL::GetBufferDo(
                       (OSF_SCALL *)p_LockSemaphore,
                       (const void **)&v27,
                       BufferLength % v6,
                       0,
                       Size);
          Buffer = (char *)a2->Buffer;
          if ( BufferDo )
          {
            I_RpcBCacheFree(Buffer - 24);
            v24 = this[7].SpinCount;
            if ( v24 && (*(_DWORD *)(*(_QWORD *)v24 + 56LL) & 2) != 0 )
              a2->Buffer = 0;
            return BufferDo;
          }
          a2->BufferLength -= v9;
          v26 = (char *)v27;
          memcpy_0(v27, &Buffer[a2->BufferLength], v9);
        }
      }
    }
  }
  v11 = 0;
  LODWORD(v27) = 0;
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
      LODWORD(v27) = 1;
      if ( this[8].DebugInfo == LockSemaphore && this[8].LockCount <= v6 )
      {
        v14 = v26;
      }
      else
      {
        v14 = v26;
        if ( (_DWORD)v9 )
        {
          a2->Buffer = v26;
          v18 = v9;
        }
        else
        {
          a2->Buffer = 0;
          v18 = 0;
        }
        a2->BufferLength = v18;
        v2 = 1;
        HIDWORD(this[14].SpinCount) = v18;
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
      v14 = v26;
      goto LABEL_24;
    }
    if ( *v28 || this[15].RecursionCount < 4 )
      break;
    LODWORD(this[17].DebugInfo) = 1;
    RtlLeaveCriticalSection(this + 12);
    EVENT::Wait((EVENT *)&this[17].LockSemaphore, -1);
    v12 = this + 12;
    if ( LODWORD(this->SpinCount) )
    {
      BufferDo = this->SpinCount;
      v2 = 1;
      v14 = v26;
      goto LABEL_10;
    }
  }
  v14 = v26;
  if ( (unsigned int)QUEUE::PutOnQueue((QUEUE *)&this[15], a2->Buffer, a2->BufferLength) )
  {
    BufferDo = 14;
  }
  else
  {
    if ( (_DWORD)v9 )
    {
      a2->Buffer = v26;
      v16 = v9;
    }
    else
    {
      a2->Buffer = 0;
      v16 = 0;
    }
    a2->BufferLength = v16;
    HIDWORD(this[14].SpinCount) = v16;
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
        I_RpcBCacheFree((char *)a2->Buffer - 24);
        v15 = this[7].SpinCount;
        if ( v15 )
        {
          if ( (*(_DWORD *)(*(_QWORD *)v15 + 56LL) & 2) != 0 )
            a2->Buffer = 0;
        }
      }
      goto LABEL_27;
    }
LABEL_11:
    I_RpcBCacheFree(v14 - 24);
    goto LABEL_12;
  }
LABEL_25:
  if ( v11 )
    BufferDo = v11;
LABEL_27:
  if ( !(_DWORD)v27 )
    return BufferDo;
LABEL_28:
  (*(void (__fastcall **)(struct _RTL_CRITICAL_SECTION *))&this->DebugInfo->EntryCount)(this);
  return BufferDo;
}

```

## disassembly

```asm
0x180047a60  mov     [rsp+arg_10], rbx
0x180047a65  push    rbp
0x180047a66  push    rsi
0x180047a67  push    rdi
0x180047a68  push    r12
0x180047a6a  push    r13
0x180047a6c  push    r14
0x180047a6e  push    r15
0x180047a70  sub     rsp, 60h
0x180047a74  mov     rax, cs:__security_cookie
0x180047a7b  xor     rax, rsp
0x180047a7e  mov     [rsp+98h+var_40], rax
0x180047a83  mov     r13d, [rcx+1DCh]
0x180047a8a  xor     r15d, r15d
0x180047a8d  sub     r13d, [rcx+150h]
0x180047a94  mov     rdi, rcx
0x180047a97  add     rcx, 18h
0x180047a9b  mov     [rsp+98h+var_68], r15
0x180047aa0  add     r13d, 0FFFFFFE8h
0x180047aa4  mov     [rsp+98h+var_60], r15
0x180047aa9  test    dword ptr [rdx+48h], 2000h
0x180047ab0  mov     rsi, rdx
0x180047ab3  mov     ebp, r15d
0x180047ab6  mov     [rsp+98h+var_58], rcx
0x180047abb  mov     ebx, r15d
0x180047abe  jnz     loc_180047CCC
0x180047ac4  mov     rax, [rdx+10h]
0x180047ac8  mov     [rdi+1D0h], rax
0x180047acf  mov     [rsp+98h+var_58], rcx
0x180047ad4  mov     r12d, r15d
0x180047ad7  mov     dword ptr [rsp+98h+var_60], r15d
0x180047adc  lea     rax, [rdi+1E0h]
0x180047ae3  mov     r14d, 1
0x180047ae9  mov     rcx, rax; CriticalSection
0x180047aec  call    cs:__imp_RtlEnterCriticalSection
0x180047af2  xor     ecx, ecx
0x180047af4  cmp     [rdi+140h], rcx
0x180047afb  jnz     loc_180047C36
0x180047b01  mov     [rdi+14Ch], ecx
0x180047b07  mov     rcx, rdi; this
0x180047b0a  mov     rax, [rsi+10h]
0x180047b0e  mov     [rdi+140h], rax
0x180047b15  mov     eax, [rsi+18h]
0x180047b18  mov     [rdi+148h], eax
0x180047b1e  call    ?SetSendBufferSizeIfNecessary@OSF_SCALL@@QEAAXXZ; OSF_SCALL::SetSendBufferSizeIfNecessary(void)
0x180047b23  mov     rax, [rdi+1D0h]
0x180047b2a  mov     dword ptr [rsp+98h+var_60], r14d
0x180047b2f  cmp     [rdi+140h], rax
0x180047b36  jnz     loc_180047C59
0x180047b3c  cmp     [rdi+148h], r13d
0x180047b43  ja      loc_180047C59
0x180047b49  mov     r13, [rsp+98h+var_68]
0x180047b4e  lea     rcx, [rdi+1E0h]; CriticalSection
0x180047b55  call    cs:__imp_RtlLeaveCriticalSection
0x180047b5b  mov     rcx, rdi; this
0x180047b5e  call    ?SendNextFragment@OSF_SCALL@@QEAAJXZ; OSF_SCALL::SendNextFragment(void)
0x180047b63  mov     ebx, eax
0x180047b65  test    eax, eax
0x180047b67  jz      short loc_180047BB2
0x180047b69  test    r15d, r15d
0x180047b6c  jnz     loc_180047E85
0x180047b72  test    ebp, ebp
0x180047b74  jz      short loc_180047B7F
0x180047b76  lea     rcx, [r13-18h]; void *
0x180047b7a  call    I_RpcBCacheFree
0x180047b7f  test    r15d, r15d
0x180047b82  jz      short loc_180047BF9
0x180047b84  mov     rcx, [rsi+10h]
0x180047b88  sub     rcx, 18h; void *
0x180047b8c  call    I_RpcBCacheFree
0x180047b91  mov     rax, [rdi+138h]
0x180047b98  test    rax, rax
0x180047b9b  jz      short loc_180047BF9
0x180047b9d  mov     rax, [rax]
0x180047ba0  mov     ecx, [rax+38h]
0x180047ba3  test    cl, 2
0x180047ba6  jz      short loc_180047BF9
0x180047ba8  mov     qword ptr [rsi+10h], 0
0x180047bb0  jmp     short loc_180047BF9
0x180047bb2  test    r15d, r15d
0x180047bb5  jz      short loc_180047C00
0x180047bb7  test    ebp, ebp
0x180047bb9  jz      short loc_180047BEE
0x180047bbb  test    ebx, ebx
0x180047bbd  jnz     short loc_180047B76
0x180047bbf  mov     r12d, 779h
0x180047bc5  jmp     short loc_180047BF2
0x180047bc7  mov     [rsi+10h], r13
0x180047bcb  mov     eax, ebp
0x180047bcd  mov     [rsi+18h], eax
0x180047bd0  test    ebp, ebp
0x180047bd2  mov     [rdi+254h], eax
0x180047bd8  mov     eax, 779h
0x180047bdd  cmovnz  r12d, eax
0x180047be1  lea     rcx, [rdi+1E0h]; CriticalSection
0x180047be8  call    cs:__imp_RtlLeaveCriticalSection
0x180047bee  test    ebx, ebx
0x180047bf0  jnz     short loc_180047B72
0x180047bf2  test    r12d, r12d
0x180047bf5  cmovnz  ebx, r12d
0x180047bf9  cmp     dword ptr [rsp+98h+var_60], 0
0x180047bfe  jz      short loc_180047C0F
0x180047c00  mov     rax, [rdi]
0x180047c03  mov     rcx, rdi
0x180047c06  mov     rax, [rax+20h]
0x180047c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c0f  mov     eax, ebx
0x180047c11  mov     rcx, [rsp+98h+var_40]
0x180047c16  xor     rcx, rsp; StackCookie
0x180047c19  call    __security_check_cookie
0x180047c1e  mov     rbx, [rsp+98h+arg_10]
0x180047c26  add     rsp, 60h
0x180047c2a  pop     r15
0x180047c2c  pop     r14
0x180047c2e  pop     r13
0x180047c30  pop     r12
0x180047c32  pop     rdi
0x180047c33  pop     rsi
0x180047c34  pop     rbp
0x180047c35  retn
0x180047c36  cmp     [rdi+20h], ecx
0x180047c39  jz      loc_180047E03
0x180047c3f  lea     rcx, [rdi+1E0h]; CriticalSection
0x180047c46  call    cs:__imp_RtlLeaveCriticalSection
0x180047c4c  mov     ebx, [rdi+20h]
0x180047c4f  mov     r15d, r14d
0x180047c52  mov     r13, [rsp+98h+var_68]
0x180047c57  jmp     short loc_180047BEE
0x180047c59  mov     r13, [rsp+98h+var_68]
0x180047c5e  test    ebp, ebp
0x180047c60  jz      short loc_180047C79
0x180047c62  mov     [rsi+10h], r13
0x180047c66  mov     eax, ebp
0x180047c68  mov     [rsi+18h], eax
0x180047c6b  mov     r15d, r14d
0x180047c6e  mov     [rdi+254h], eax
0x180047c74  jmp     loc_180047B4E
0x180047c79  mov     [rsi+10h], r12
0x180047c7d  xor     eax, eax
0x180047c7f  jmp     short loc_180047C68
0x180047c81  mov     rax, [rdi+130h]
0x180047c88  mov     rcx, [rax+20h]; this
0x180047c8c  cmp     [rcx+118h], r15
0x180047c93  jnz     short loc_180047CDB
0x180047c95  mov     eax, [rdi+2E0h]
0x180047c9b  test    al, 10h
0x180047c9d  jnz     loc_180047AD4
0x180047ca3  mov     eax, [rdx+18h]
0x180047ca6  cmp     eax, r13d
0x180047ca9  jnb     loc_180047D7A
0x180047caf  mov     eax, 779h
0x180047cb4  jmp     loc_180047C11
0x180047cb9  test    ebp, ebp
0x180047cbb  jnz     loc_180047BC7
0x180047cc1  mov     [rsi+10h], r12
0x180047cc5  xor     eax, eax
0x180047cc7  jmp     loc_180047BCD
0x180047ccc  xorps   xmm0, xmm0
0x180047ccf  movups  [rsp+98h+var_50], xmm0
0x180047cd4  cmp     [rcx], r15
0x180047cd7  jnz     short loc_180047C95
0x180047cd9  jmp     short loc_180047C81
0x180047cdb  mov     rax, [rdi]
0x180047cde  mov     rcx, rdi
0x180047ce1  mov     rax, [rax+120h]
0x180047ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ced  mov     ecx, 2; unsigned int
0x180047cf2  movups  xmm0, xmmword ptr [rax+54h]
0x180047cf6  movdqu  [rsp+98h+var_50], xmm0
0x180047cfc  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x180047d01  test    eax, eax
0x180047d03  jnz     short loc_180047D48
0x180047d05  lea     r14d, [rax+1]
0x180047d09  test    cs:Microsoft_Windows_RPC_EventsEnableBits, r14b
0x180047d10  jz      short loc_180047D48
0x180047d12  call    cs:__imp_GetCurrentProcessId
0x180047d18  mov     ebx, eax
0x180047d1a  call    cs:__imp_GetCommandLineW
0x180047d20  lea     rcx, [rsp+98h+var_50]
0x180047d25  mov     r9d, ebx
0x180047d28  mov     [rsp+98h+var_70], rcx
0x180047d2d  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x180047d34  lea     rcx, aNcacnHttp; "ncacn_http"
0x180047d3b  mov     r8, rax
0x180047d3e  mov     [rsp+98h+Size], rcx
0x180047d43  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x180047d48  mov     rcx, [rsi+10h]
0x180047d4c  sub     rcx, 18h; void *
0x180047d50  call    I_RpcBCacheFree
0x180047d55  mov     rax, [rdi+138h]
0x180047d5c  test    rax, rax
0x180047d5f  jz      short loc_180047D70
0x180047d61  mov     rax, [rax]
0x180047d64  mov     ecx, [rax+38h]
0x180047d67  test    cl, 2
0x180047d6a  jz      short loc_180047D70
0x180047d6c  mov     [rsi+10h], r15
0x180047d70  mov     eax, 6E4h
0x180047d75  jmp     loc_180047C11
0x180047d7a  jbe     loc_180047AD4
0x180047d80  xor     edx, edx
0x180047d82  div     r13d
0x180047d85  movsxd  rbp, edx
0x180047d88  test    edx, edx
0x180047d8a  jz      loc_180047AD4
0x180047d90  xor     r9d, r9d; int
0x180047d93  mov     dword ptr [rsp+98h+Size], r15d; Size
0x180047d98  mov     r8d, ebp; unsigned int
0x180047d9b  lea     rdx, [rsp+98h+var_60]; void **
0x180047da0  call    ?GetBufferDo@OSF_SCALL@@QEAAJPEAPEAXIHIK@Z; OSF_SCALL::GetBufferDo(void * *,uint,int,uint,ulong)
0x180047da5  mov     ebx, eax
0x180047da7  mov     rax, [rsi+10h]
0x180047dab  test    ebx, ebx
0x180047dad  jz      short loc_180047DE0
0x180047daf  lea     rcx, [rax-18h]; void *
0x180047db3  call    I_RpcBCacheFree
0x180047db8  mov     rcx, [rdi+138h]
0x180047dbf  test    rcx, rcx
0x180047dc2  jz      loc_180047C0F
0x180047dc8  mov     rcx, [rcx]
0x180047dcb  mov     edx, [rcx+38h]
0x180047dce  test    dl, 2
0x180047dd1  jz      loc_180047C0F
0x180047dd7  mov     [rsi+10h], r15
0x180047ddb  jmp     loc_180047C0F
0x180047de0  sub     [rsi+18h], ebp
0x180047de3  mov     r8, rbp; Size
0x180047de6  mov     edx, [rsi+18h]
0x180047de9  add     rdx, rax; Src
0x180047dec  mov     rax, [rsp+98h+var_60]
0x180047df1  mov     rcx, rax; void *
0x180047df4  mov     [rsp+98h+var_68], rax
0x180047df9  call    memcpy_0
0x180047dfe  jmp     loc_180047AD4
0x180047e03  mov     rax, [rsp+98h+var_58]
0x180047e08  cmp     [rax], rcx
0x180047e0b  jnz     short loc_180047E5A
0x180047e0d  cmp     dword ptr [rdi+264h], 4
0x180047e14  jl      short loc_180047E5A
0x180047e16  lea     rcx, [rdi+1E0h]; CriticalSection
0x180047e1d  mov     [rdi+2A8h], r14d
0x180047e24  call    cs:__imp_RtlLeaveCriticalSection
0x180047e2a  lea     rcx, [rdi+2C0h]; this
0x180047e31  or      edx, 0FFFFFFFFh; int
0x180047e34  call    ?Wait@EVENT@@QEAAHJ@Z; EVENT::Wait(long)
0x180047e39  lea     rax, [rdi+1E0h]
0x180047e40  cmp     [rdi+20h], r12d
0x180047e44  jz      loc_180047AE9
0x180047e4a  mov     ebx, [rdi+20h]
0x180047e4d  mov     r15d, r14d
0x180047e50  mov     r13, [rsp+98h+var_68]
0x180047e55  jmp     loc_180047B72
0x180047e5a  mov     r8d, [rsi+18h]; unsigned int
0x180047e5e  lea     rcx, [rdi+258h]; this
0x180047e65  mov     rdx, [rsi+10h]; void *
0x180047e69  call    ?PutOnQueue@QUEUE@@QEAAHPEAXI@Z; QUEUE::PutOnQueue(void *,uint)
0x180047e6e  mov     r13, [rsp+98h+var_68]
0x180047e73  test    eax, eax
0x180047e75  jz      loc_180047CB9
0x180047e7b  mov     ebx, 0Eh
0x180047e80  jmp     loc_180047BE1
0x180047e85  mov     rax, [rdi+140h]
0x180047e8c  xor     r8d, r8d; int
0x180047e8f  mov     edx, ebx; int
0x180047e91  mov     [rsi+10h], rax
0x180047e95  mov     rcx, rdi; this
0x180047e98  call    ?CleanupCallAndSendFault@OSF_SCALL@@QEAAXJH@Z; OSF_SCALL::CleanupCallAndSendFault(long,int)
0x180047e9d  jmp     loc_180047BB7
```
