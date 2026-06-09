# CWcnEapSession::StartDisconnect(void)

- ea: `0x180047ea0`
- end: `0x180047f85`
- name: `?StartDisconnect@CWcnEapSession@@UEAAXXZ`
- size: `229`
- prototype: `void __fastcall(CWcnEapSession *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001e22`
- `0x18003d6e8`
- `0x18003dbb4`
- `0x180047ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047ebf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047ebf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047f3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047f3f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180047f7e`

## pseudocode

```c
void __fastcall CWcnEapSession::StartDisconnect(CWcnEapSession *this)
{
  __int64 v1; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  CWcnEapSession ***v4; // r14
  CWcnEapSession **v5; // rdx
  CWcnEapSession **v6; // rbx
  CWcnEapSession **v7; // rax
  CWcnEapSession **v8; // rax
  size_t v9; // rdi
  CWcnMessageSinkSession *v10; // rcx

  v1 = *((_QWORD *)this + 19);
  v3 = (struct _RTL_CRITICAL_SECTION *)(v1 + 232);
  EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 232));
  v4 = *(CWcnEapSession ****)(v1 + 224);
  v5 = v4[1];
  v6 = *v4;
  if ( *v4 != v5 )
  {
    while ( 1 )
    {
      v7 = v6 + 1;
      if ( *v6 == this )
        break;
      ++v6;
      if ( v7 == v5 )
        goto LABEL_9;
    }
    while ( v7 != v5 )
    {
      if ( *v7 != this )
        *v6++ = *v7;
      ++v7;
    }
  }
LABEL_9:
  v8 = *v4;
  if ( v6 != *v4 || v5 != v4[1] )
  {
    if ( v6 == v5 )
      goto LABEL_14;
    v9 = v4[1] - v5;
    memmove_0(v6, v5, v9 * 8);
    v8 = &v6[v9];
  }
  v4[1] = v8;
LABEL_14:
  LeaveCriticalSection(v3);
  v10 = (CWcnMessageSinkSession *)*((_QWORD *)this + 18);
  if ( v10 )
  {
    CWcnMessageSinkSession::EndSessionAndPreventMoreMessages(v10);
    CWcnMessageSinkSession::Release(*((CWcnMessageSinkSession **)this + 18));
    *((_QWORD *)this + 18) = 0;
  }
  SubmitThreadpoolWork(*((PTP_WORK *)this + 20));
}

```

## disassembly

```asm
0x180047ea0  push    rbx
0x180047ea2  push    rbp
0x180047ea3  push    rsi
0x180047ea4  push    rdi
0x180047ea5  push    r14
0x180047ea7  sub     rsp, 20h
0x180047eab  mov     rbx, [rcx+98h]
0x180047eb2  mov     rsi, rcx
0x180047eb5  lea     rbp, [rbx+0E8h]
0x180047ebc  mov     rcx, rbp; lpCriticalSection
0x180047ebf  call    cs:__imp_EnterCriticalSection
0x180047ec5  mov     r14, [rbx+0E0h]
0x180047ecc  mov     rdx, [r14+8]; Src
0x180047ed0  mov     rbx, [r14]
0x180047ed3  cmp     rbx, rdx
0x180047ed6  jz      short loc_180047F03
0x180047ed8  lea     rax, [rbx+8]
0x180047edc  cmp     [rbx], rsi
0x180047edf  jz      short loc_180047EFE
0x180047ee1  mov     rbx, rax
0x180047ee4  cmp     rax, rdx
0x180047ee7  jnz     short loc_180047ED8
0x180047ee9  jmp     short loc_180047F03
0x180047eeb  mov     rcx, [rax]
0x180047eee  cmp     rcx, rsi
0x180047ef1  jz      short loc_180047EFA
0x180047ef3  mov     [rbx], rcx
0x180047ef6  add     rbx, 8
0x180047efa  add     rax, 8
0x180047efe  cmp     rax, rdx
0x180047f01  jnz     short loc_180047EEB
0x180047f03  mov     rax, [r14]
0x180047f06  cmp     rbx, rax
0x180047f09  jnz     short loc_180047F11
0x180047f0b  cmp     rdx, [r14+8]
0x180047f0f  jz      short loc_180047F38
0x180047f11  cmp     rbx, rdx
0x180047f14  jz      short loc_180047F3C
0x180047f16  mov     rax, [r14+8]
0x180047f1a  mov     rcx, rbx; void *
0x180047f1d  sub     rax, rdx
0x180047f20  sar     rax, 3
0x180047f24  lea     rdi, ds:0[rax*8]
0x180047f2c  mov     r8, rdi; Size
0x180047f2f  call    memmove_0
0x180047f34  lea     rax, [rdi+rbx]
0x180047f38  mov     [r14+8], rax
0x180047f3c  mov     rcx, rbp; lpCriticalSection
0x180047f3f  call    cs:__imp_LeaveCriticalSection
0x180047f45  mov     rcx, [rsi+90h]; this
0x180047f4c  test    rcx, rcx
0x180047f4f  jz      short loc_180047F6D
0x180047f51  call    ?EndSessionAndPreventMoreMessages@CWcnMessageSinkSession@@QEAAXXZ; CWcnMessageSinkSession::EndSessionAndPreventMoreMessages(void)
0x180047f56  mov     rcx, [rsi+90h]; this
0x180047f5d  call    ?Release@CWcnMessageSinkSession@@QEAAXXZ; CWcnMessageSinkSession::Release(void)
0x180047f62  mov     qword ptr [rsi+90h], 0
0x180047f6d  mov     rcx, [rsi+0A0h]
0x180047f74  add     rsp, 20h
0x180047f78  pop     r14
0x180047f7a  pop     rdi
0x180047f7b  pop     rsi
0x180047f7c  pop     rbp
0x180047f7d  pop     rbx
0x180047f7e  jmp     cs:__imp_SubmitThreadpoolWork
```
