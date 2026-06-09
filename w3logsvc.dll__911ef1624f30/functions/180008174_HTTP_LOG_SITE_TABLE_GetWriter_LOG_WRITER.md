# HTTP_LOG_SITE_TABLE::GetWriter(LOG_WRITER * *)

- ea: `0x180008174`
- end: `0x180008227`
- name: `?GetWriter@HTTP_LOG_SITE_TABLE@@QEAAJPEAPEAVLOG_WRITER@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(HTTP_LOG_SITE_TABLE *__hidden this, struct LOG_WRITER **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a57c`

## callees

- `0x180001008`
- `0x180002094`
- `0x1800057a0`
- `0x180008174`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800081ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800081f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800081ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800081f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000819d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000819d`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_TABLE::GetWriter(HTTP_LOG_SITE_TABLE *this, struct LOG_WRITER **a2)
{
  RTL_SRWLOCK *v4; // rdi
  LOG_WRITER *v5; // rax

  if ( *((_QWORD *)this + 135) )
    goto LABEL_9;
  v4 = (RTL_SRWLOCK *)((char *)this + 1096);
  AcquireSRWLockExclusive((PSRWLOCK)this + 137);
  if ( *((_QWORD *)this + 135) )
    goto LABEL_8;
  v5 = (LOG_WRITER *)operator new(0x2D8u);
  if ( v5 )
    v5 = LOG_WRITER::LOG_WRITER(v5);
  *((_QWORD *)this + 135) = v5;
  if ( v5 )
  {
    if ( (int)LOG_WRITER::Initialize(v5, *((const struct HTTP_LOG_FILE_CONFIG_CONTEXT **)this + 136)) >= 0 )
    {
LABEL_8:
      ReleaseSRWLockExclusive(v4);
LABEL_9:
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 135) + 672LL));
      *a2 = (struct LOG_WRITER *)*((_QWORD *)this + 135);
      return 0;
    }
  }
  ReleaseSRWLockExclusive(v4);
  return 0;
}

```

## disassembly

```asm
0x180008174  mov     [rsp+arg_8], rbx
0x180008179  mov     [rsp+arg_10], rsi
0x18000817e  push    rdi
0x18000817f  sub     rsp, 20h
0x180008183  mov     rsi, rdx
0x180008186  mov     rbx, rcx
0x180008189  cmp     qword ptr [rcx+438h], 0
0x180008191  jnz     short loc_1800081FD
0x180008193  lea     rdi, [rcx+448h]
0x18000819a  mov     rcx, rdi; SRWLock
0x18000819d  call    cs:__imp_AcquireSRWLockExclusive
0x1800081a3  cmp     qword ptr [rbx+438h], 0
0x1800081ab  jnz     short loc_1800081F4
0x1800081ad  mov     ecx, 2D8h; Size
0x1800081b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800081b7  mov     [rsp+28h+arg_0], rax
0x1800081bc  test    rax, rax
0x1800081bf  jz      short loc_1800081CA
0x1800081c1  mov     rcx, rax; this
0x1800081c4  call    ??0LOG_WRITER@@QEAA@XZ; LOG_WRITER::LOG_WRITER(void)
0x1800081c9  nop
0x1800081ca  mov     [rbx+438h], rax
0x1800081d1  test    rax, rax
0x1800081d4  jz      short loc_1800081E9
0x1800081d6  mov     rdx, [rbx+440h]; struct HTTP_LOG_FILE_CONFIG_CONTEXT *
0x1800081dd  mov     rcx, rax; this
0x1800081e0  call    ?Initialize@LOG_WRITER@@QEAAJPEBVHTTP_LOG_FILE_CONFIG_CONTEXT@@@Z; LOG_WRITER::Initialize(HTTP_LOG_FILE_CONFIG_CONTEXT const *)
0x1800081e5  test    eax, eax
0x1800081e7  jns     short loc_1800081F4
0x1800081e9  mov     rcx, rdi; SRWLock
0x1800081ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800081f2  jmp     short loc_180008215
0x1800081f4  mov     rcx, rdi; SRWLock
0x1800081f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800081fd  mov     rax, [rbx+438h]
0x180008204  lock inc dword ptr [rax+2A0h]
0x18000820b  mov     rax, [rbx+438h]
0x180008212  mov     [rsi], rax
0x180008215  xor     eax, eax
0x180008217  mov     rbx, [rsp+28h+arg_8]
0x18000821c  mov     rsi, [rsp+28h+arg_10]
0x180008221  add     rsp, 20h
0x180008225  pop     rdi
0x180008226  retn
```
