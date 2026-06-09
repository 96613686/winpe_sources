# LOG_WRITER::Write(HTTP_LOG_CONTEXT *)

- ea: `0x1800062c4`
- end: `0x1800063b3`
- name: `?Write@LOG_WRITER@@QEAAJPEAVHTTP_LOG_CONTEXT@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct HTTP_LOG_CONTEXT *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180008cf4`
- `0x180009d10`
- `0x18000a2f8`
- `0x18000a57c`

## callees

- `0x180003718`
- `0x180006148`
- `0x1800062c4`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000632d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000632d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000637a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000637a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006386`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006386`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006310`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006310`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000635c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000635c`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::Write(RTL_SRWLOCK *this, struct HTTP_LOG_CONTEXT *a2)
{
  int LogString; // ebx
  _BYTE v6[48]; // [rsp+20h] [rbp-458h] BYREF
  int v7; // [rsp+50h] [rbp-428h]
  unsigned __int16 v8[512]; // [rsp+60h] [rbp-418h] BYREF

  memset_0(v8, 0, sizeof(v8));
  STRU::STRU((STRU *)v6, v8, 0x200u);
  if ( a2 )
  {
    AcquireSRWLockShared(this + 90);
    LogString = LOG_WRITER::CreateLogString((LOG_WRITER *)this, a2, (struct STRU *)v6);
    if ( LogString >= 0 )
    {
      if ( v7 )
      {
        LogString = STRU::Append((STRU *)v6, L"\r\n");
        if ( LogString >= 0 )
          LogString = LOG_WRITER::Write((struct _RTL_CRITICAL_SECTION *)this, (struct STRU *)v6);
      }
    }
    ReleaseSRWLockShared(this + 90);
  }
  else
  {
    LogString = -2147024809;
  }
  STRU::~STRU((STRU *)v6);
  return (unsigned int)LogString;
}

```

## disassembly

```asm
0x1800062c4  mov     [rsp+arg_10], rbx
0x1800062c9  mov     [rsp+arg_18], rsi
0x1800062ce  push    rdi
0x1800062cf  sub     rsp, 470h
0x1800062d6  mov     rax, cs:__security_cookie
0x1800062dd  xor     rax, rsp
0x1800062e0  mov     [rsp+478h+var_18], rax
0x1800062e8  mov     rbx, rdx
0x1800062eb  mov     rdi, rcx
0x1800062ee  xor     edx, edx; Val
0x1800062f0  mov     r8d, 400h; Size
0x1800062f6  lea     rcx, [rsp+478h+var_418]; void *
0x1800062fb  call    memset_0
0x180006300  mov     r8d, 200h
0x180006306  lea     rdx, [rsp+478h+var_418]
0x18000630b  lea     rcx, [rsp+478h+var_458]
0x180006310  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180006316  nop
0x180006317  test    rbx, rbx
0x18000631a  jnz     short loc_180006323
0x18000631c  mov     ebx, 80070057h
0x180006321  jmp     short loc_180006381
0x180006323  lea     rsi, [rdi+2D0h]
0x18000632a  mov     rcx, rsi; SRWLock
0x18000632d  call    cs:__imp_AcquireSRWLockShared
0x180006333  lea     r8, [rsp+478h+var_458]; struct STRU *
0x180006338  mov     rdx, rbx; struct HTTP_LOG_CONTEXT *
0x18000633b  mov     rcx, rdi; this
0x18000633e  call    ?CreateLogString@LOG_WRITER@@AEAAJPEAVHTTP_LOG_CONTEXT@@PEAVSTRU@@@Z; LOG_WRITER::CreateLogString(HTTP_LOG_CONTEXT *,STRU *)
0x180006343  mov     ebx, eax
0x180006345  test    eax, eax
0x180006347  js      short loc_180006377
0x180006349  cmp     [rsp+478h+var_428], 0
0x18000634e  jbe     short loc_180006377
0x180006350  lea     rdx, asc_1800120D0; "\r\n"
0x180006357  lea     rcx, [rsp+478h+var_458]
0x18000635c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180006362  mov     ebx, eax
0x180006364  test    eax, eax
0x180006366  js      short loc_180006377
0x180006368  lea     rdx, [rsp+478h+var_458]; struct STRU *
0x18000636d  mov     rcx, rdi; this
0x180006370  call    ?Write@LOG_WRITER@@AEAAJPEAVSTRU@@@Z; LOG_WRITER::Write(STRU *)
0x180006375  mov     ebx, eax
0x180006377  mov     rcx, rsi; SRWLock
0x18000637a  call    cs:__imp_ReleaseSRWLockShared
0x180006380  nop
0x180006381  lea     rcx, [rsp+478h+var_458]
0x180006386  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000638c  mov     eax, ebx
0x18000638e  mov     rcx, [rsp+478h+var_18]
0x180006396  xor     rcx, rsp; StackCookie
0x180006399  call    __security_check_cookie
0x18000639e  lea     r11, [rsp+478h+var_8]
0x1800063a6  mov     rbx, [r11+20h]
0x1800063aa  mov     rsi, [r11+28h]
0x1800063ae  mov     rsp, r11
0x1800063b1  pop     rdi
0x1800063b2  retn
```
