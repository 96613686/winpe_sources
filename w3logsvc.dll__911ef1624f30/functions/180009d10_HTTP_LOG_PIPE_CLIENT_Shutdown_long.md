# HTTP_LOG_PIPE_CLIENT::Shutdown(long)

- ea: `0x180009d10`
- end: `0x180009f3e`
- name: `?Shutdown@HTTP_LOG_PIPE_CLIENT@@QEAAXJ@Z`
- size: `558`
- prototype: `void __fastcall(HTTP_LOG_PIPE_CLIENT *__hidden this, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180008dac`
- `0x18000b6f0`
- `0x18000cf20`

## callees

- `0x180001048`
- `0x1800062c4`
- `0x180008cf4`
- `0x180009d10`
- `0x18000e9a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009e2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009e2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009dd9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009dd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009eff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009eff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009d9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009d9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009db0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009db0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009dbd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009dbd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180009eeb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180009eeb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180009ede`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180009ede`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180009ece`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180009ece`
- `iisutil!?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ` at `0x180009eac`
- `iisutil!?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ` at `0x180009eac`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180009f0b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180009f0b`

## pseudocode

```c
void __fastcall HTTP_LOG_PIPE_CLIENT::Shutdown(HTTP_LOG_PIPE_CLIENT *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  BOOL v5; // ebx
  HTTP_LOG_PENDING_CONTEXT *v6; // rbx
  HTTP_LOG_PENDING_CONTEXT *v7; // rsi
  HTTP_LOG_PENDING_CONTEXT **v8; // rax
  __int64 i; // rbx
  __int64 v10; // rcx
  IPM2_MESSAGE_PIPE *v11; // rcx
  struct _TP_WAIT *v12; // rcx
  _QWORD v13[5]; // [rsp+20h] [rbp-68h] BYREF
  int v14; // [rsp+48h] [rbp-40h]
  __int16 v15; // [rsp+4Ch] [rbp-3Ch]

  v13[0] = 0;
  v13[4] = v13;
  v14 = 32;
  v15 = 256;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 80352);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 80352));
  if ( !*((_DWORD *)this + 39) || a2 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 27);
    v6 = (HTTP_LOG_PENDING_CONTEXT *)*((_QWORD *)this + 25);
    if ( v6 != (HTTP_LOG_PIPE_CLIENT *)((char *)this + 200) )
    {
      do
      {
        v7 = *(HTTP_LOG_PENDING_CONTEXT **)v6;
        if ( *(HTTP_LOG_PENDING_CONTEXT **)(*(_QWORD *)v6 + 8LL) != v6
          || (v8 = (HTTP_LOG_PENDING_CONTEXT **)*((_QWORD *)v6 + 1), *v8 != v6) )
        {
          __fastfail(3u);
        }
        *v8 = v7;
        *((_QWORD *)v7 + 1) = v8;
        HTTP_LOG_PENDING_CONTEXT::~HTTP_LOG_PENDING_CONTEXT(v6);
        operator delete(v6);
        v6 = v7;
      }
      while ( v7 != (HTTP_LOG_PIPE_CLIENT *)((char *)this + 200) );
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 27);
  }
  else
  {
    while ( *((_DWORD *)this + 39) )
    {
      AcquireSRWLockShared((PSRWLOCK)this + 27);
      v5 = *((_QWORD *)this + 25) == (_QWORD)this + 200;
      ReleaseSRWLockShared((PSRWLOCK)this + 27);
      if ( v5 )
        break;
      Sleep(0x64u);
    }
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 20086); i = (unsigned int)(i + 1) )
  {
    v10 = *((_QWORD *)this + i + 43);
    if ( v10 )
    {
      *(_QWORD *)(v10 + 816) = 0;
      LOG_WRITER::Write(*(RTL_SRWLOCK **)(v10 + 1184), (struct HTTP_LOG_CONTEXT *)v10);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + i + 43) + 8LL))(*((_QWORD *)this + i + 43));
      *((_QWORD *)this + i + 43) = 0;
    }
  }
  *((_DWORD *)this + 20086) = 0;
  *((_DWORD *)this + 39) = 0;
  v11 = (IPM2_MESSAGE_PIPE *)*((_QWORD *)this + 42);
  if ( v11 )
  {
    IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe(v11);
    *((_QWORD *)this + 42) = 0;
  }
  v12 = (struct _TP_WAIT *)*((_QWORD *)this + 22);
  if ( v12 )
  {
    SetThreadpoolWait(v12, 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 22), 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 22));
    *((_QWORD *)this + 22) = 0;
  }
  LeaveCriticalSection(v4);
  BUFFER::~BUFFER((BUFFER *)v13);
}

```

## disassembly

```asm
0x180009d10  mov     r11, rsp
0x180009d13  mov     [r11+10h], rbx
0x180009d17  mov     [r11+18h], rbp
0x180009d1b  push    rsi
0x180009d1c  push    rdi
0x180009d1d  push    r13
0x180009d1f  push    r14
0x180009d21  push    r15
0x180009d23  sub     rsp, 60h
0x180009d27  mov     rax, cs:__security_cookie
0x180009d2e  xor     rax, rsp
0x180009d31  mov     [rsp+88h+var_38], rax
0x180009d36  mov     ebx, edx
0x180009d38  mov     rdi, rcx
0x180009d3b  mov     qword ptr [r11-68h], 0
0x180009d43  lea     rax, [r11-68h]
0x180009d47  mov     [r11-48h], rax
0x180009d4b  mov     [rsp+88h+var_40], 20h ; ' '
0x180009d53  mov     [rsp+88h+var_3C], 100h
0x180009d5a  mov     r13d, 1
0x180009d60  lea     r15, [rcx+139E0h]
0x180009d67  mov     rcx, r15; lpCriticalSection
0x180009d6a  call    cs:__imp_EnterCriticalSection
0x180009d70  mov     eax, [rdi+9Ch]
0x180009d76  test    eax, eax
0x180009d78  jz      short loc_180009DCF
0x180009d7a  test    ebx, ebx
0x180009d7c  jnz     short loc_180009DCF
0x180009d7e  mov     eax, [rdi+9Ch]
0x180009d84  test    eax, eax
0x180009d86  jz      loc_180009E30
0x180009d8c  lea     rsi, [rdi+0D8h]
0x180009d93  lea     rbp, [rdi+0C8h]
0x180009d9a  xor     ebx, ebx
0x180009d9c  mov     rcx, rsi; SRWLock
0x180009d9f  call    cs:__imp_AcquireSRWLockShared
0x180009da5  cmp     [rbp+0], rbp
0x180009da9  cmovz   ebx, r13d
0x180009dad  mov     rcx, rsi; SRWLock
0x180009db0  call    cs:__imp_ReleaseSRWLockShared
0x180009db6  test    ebx, ebx
0x180009db8  jnz     short loc_180009E30
0x180009dba  lea     ecx, [rbx+64h]; dwMilliseconds
0x180009dbd  call    cs:__imp_Sleep
0x180009dc3  mov     eax, [rdi+9Ch]
0x180009dc9  test    eax, eax
0x180009dcb  jnz     short loc_180009D9A
0x180009dcd  jmp     short loc_180009E30
0x180009dcf  lea     rbp, [rdi+0D8h]
0x180009dd6  mov     rcx, rbp; SRWLock
0x180009dd9  call    cs:__imp_AcquireSRWLockExclusive
0x180009ddf  lea     r14, [rdi+0C8h]
0x180009de6  mov     rbx, [r14]
0x180009de9  cmp     rbx, r14
0x180009dec  jz      short loc_180009E27
0x180009dee  mov     rsi, [rbx]
0x180009df1  cmp     [rsi+8], rbx
0x180009df5  jnz     loc_180009F37
0x180009dfb  mov     rax, [rbx+8]
0x180009dff  cmp     [rax], rbx
0x180009e02  jnz     loc_180009F37
0x180009e08  mov     [rax], rsi
0x180009e0b  mov     [rsi+8], rax
0x180009e0f  mov     rcx, rbx; this
0x180009e12  call    ??1HTTP_LOG_PENDING_CONTEXT@@QEAA@XZ; HTTP_LOG_PENDING_CONTEXT::~HTTP_LOG_PENDING_CONTEXT(void)
0x180009e17  mov     rcx, rbx; Block
0x180009e1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009e1f  mov     rbx, rsi
0x180009e22  cmp     rsi, r14
0x180009e25  jnz     short loc_180009DEE
0x180009e27  mov     rcx, rbp; SRWLock
0x180009e2a  call    cs:__imp_ReleaseSRWLockExclusive
0x180009e30  xor     ebx, ebx
0x180009e32  cmp     [rdi+139D8h], ebx
0x180009e38  jbe     short loc_180009E8C
0x180009e3a  mov     rcx, [rdi+rbx*8+158h]
0x180009e42  test    rcx, rcx
0x180009e45  jz      short loc_180009E81
0x180009e47  mov     qword ptr [rcx+330h], 0
0x180009e52  mov     rdx, rcx; struct HTTP_LOG_CONTEXT *
0x180009e55  mov     rcx, [rcx+4A0h]; this
0x180009e5c  call    ?Write@LOG_WRITER@@QEAAJPEAVHTTP_LOG_CONTEXT@@@Z; LOG_WRITER::Write(HTTP_LOG_CONTEXT *)
0x180009e61  mov     rcx, [rdi+rbx*8+158h]
0x180009e69  mov     rax, [rcx]
0x180009e6c  mov     rax, [rax+8]
0x180009e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e75  mov     qword ptr [rdi+rbx*8+158h], 0
0x180009e81  add     ebx, r13d
0x180009e84  cmp     ebx, [rdi+139D8h]
0x180009e8a  jb      short loc_180009E3A
0x180009e8c  mov     dword ptr [rdi+139D8h], 0
0x180009e96  mov     dword ptr [rdi+9Ch], 0
0x180009ea0  mov     rcx, [rdi+150h]
0x180009ea7  test    rcx, rcx
0x180009eaa  jz      short loc_180009EBD
0x180009eac  call    cs:__imp_?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ; IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe(void)
0x180009eb2  mov     qword ptr [rdi+150h], 0
0x180009ebd  mov     rcx, [rdi+0B0h]; pwa
0x180009ec4  test    rcx, rcx
0x180009ec7  jz      short loc_180009EFC
0x180009ec9  xor     r8d, r8d; pftTimeout
0x180009ecc  xor     edx, edx; h
0x180009ece  call    cs:__imp_SetThreadpoolWait
0x180009ed4  mov     edx, r13d; fCancelPendingCallbacks
0x180009ed7  mov     rcx, [rdi+0B0h]; pwa
0x180009ede  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180009ee4  mov     rcx, [rdi+0B0h]; pwa
0x180009eeb  call    cs:__imp_CloseThreadpoolWait
0x180009ef1  mov     qword ptr [rdi+0B0h], 0
0x180009efc  mov     rcx, r15; lpCriticalSection
0x180009eff  call    cs:__imp_LeaveCriticalSection
0x180009f05  nop
0x180009f06  lea     rcx, [rsp+88h+var_68]
0x180009f0b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180009f11  mov     rcx, [rsp+88h+var_38]
0x180009f16  xor     rcx, rsp; StackCookie
0x180009f19  call    __security_check_cookie
0x180009f1e  lea     r11, [rsp+88h+var_28]
0x180009f23  mov     rbx, [r11+38h]
0x180009f27  mov     rbp, [r11+40h]
0x180009f2b  mov     rsp, r11
0x180009f2e  pop     r15
0x180009f30  pop     r14
0x180009f32  pop     r13
0x180009f34  pop     rdi
0x180009f35  pop     rsi
0x180009f36  retn
0x180009f37  mov     ecx, 3
0x180009f3c  int     29h; Win8: RtlFailFast(ecx)
```
