# CWcnWfdClientSession::StartDisconnect(void)

- ea: `0x18004cc60`
- end: `0x18004cd45`
- name: `?StartDisconnect@CWcnWfdClientSession@@UEAAXXZ`
- size: `229`
- prototype: `void __fastcall(CWcnWfdClientSession *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001e22`
- `0x18003d6e8`
- `0x18003dbb4`
- `0x18004cc60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cc7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cc7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ccff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ccff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004cd3e`

## pseudocode

```c
void __fastcall CWcnWfdClientSession::StartDisconnect(CWcnWfdClientSession *this)
{
  __int64 v1; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  CWcnWfdClientSession ***v4; // r14
  CWcnWfdClientSession **v5; // rdx
  CWcnWfdClientSession **v6; // rbx
  CWcnWfdClientSession **v7; // rax
  CWcnWfdClientSession **v8; // rax
  size_t v9; // rdi
  CWcnMessageSinkSession *v10; // rcx

  v1 = *((_QWORD *)this + 18);
  v3 = (struct _RTL_CRITICAL_SECTION *)(v1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 192));
  v4 = *(CWcnWfdClientSession ****)(v1 + 184);
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
  v10 = (CWcnMessageSinkSession *)*((_QWORD *)this + 17);
  if ( v10 )
  {
    CWcnMessageSinkSession::EndSessionAndPreventMoreMessages(v10);
    CWcnMessageSinkSession::Release(*((CWcnMessageSinkSession **)this + 17));
    *((_QWORD *)this + 17) = 0;
  }
  SubmitThreadpoolWork(*((PTP_WORK *)this + 19));
}

```

## disassembly

```asm
0x18004cc60  push    rbx
0x18004cc62  push    rbp
0x18004cc63  push    rsi
0x18004cc64  push    rdi
0x18004cc65  push    r14
0x18004cc67  sub     rsp, 20h
0x18004cc6b  mov     rbx, [rcx+90h]
0x18004cc72  mov     rsi, rcx
0x18004cc75  lea     rbp, [rbx+0C0h]
0x18004cc7c  mov     rcx, rbp; lpCriticalSection
0x18004cc7f  call    cs:__imp_EnterCriticalSection
0x18004cc85  mov     r14, [rbx+0B8h]
0x18004cc8c  mov     rdx, [r14+8]; Src
0x18004cc90  mov     rbx, [r14]
0x18004cc93  cmp     rbx, rdx
0x18004cc96  jz      short loc_18004CCC3
0x18004cc98  lea     rax, [rbx+8]
0x18004cc9c  cmp     [rbx], rsi
0x18004cc9f  jz      short loc_18004CCBE
0x18004cca1  mov     rbx, rax
0x18004cca4  cmp     rax, rdx
0x18004cca7  jnz     short loc_18004CC98
0x18004cca9  jmp     short loc_18004CCC3
0x18004ccab  mov     rcx, [rax]
0x18004ccae  cmp     rcx, rsi
0x18004ccb1  jz      short loc_18004CCBA
0x18004ccb3  mov     [rbx], rcx
0x18004ccb6  add     rbx, 8
0x18004ccba  add     rax, 8
0x18004ccbe  cmp     rax, rdx
0x18004ccc1  jnz     short loc_18004CCAB
0x18004ccc3  mov     rax, [r14]
0x18004ccc6  cmp     rbx, rax
0x18004ccc9  jnz     short loc_18004CCD1
0x18004cccb  cmp     rdx, [r14+8]
0x18004cccf  jz      short loc_18004CCF8
0x18004ccd1  cmp     rbx, rdx
0x18004ccd4  jz      short loc_18004CCFC
0x18004ccd6  mov     rax, [r14+8]
0x18004ccda  mov     rcx, rbx; void *
0x18004ccdd  sub     rax, rdx
0x18004cce0  sar     rax, 3
0x18004cce4  lea     rdi, ds:0[rax*8]
0x18004ccec  mov     r8, rdi; Size
0x18004ccef  call    memmove_0
0x18004ccf4  lea     rax, [rdi+rbx]
0x18004ccf8  mov     [r14+8], rax
0x18004ccfc  mov     rcx, rbp; lpCriticalSection
0x18004ccff  call    cs:__imp_LeaveCriticalSection
0x18004cd05  mov     rcx, [rsi+88h]; this
0x18004cd0c  test    rcx, rcx
0x18004cd0f  jz      short loc_18004CD2D
0x18004cd11  call    ?EndSessionAndPreventMoreMessages@CWcnMessageSinkSession@@QEAAXXZ; CWcnMessageSinkSession::EndSessionAndPreventMoreMessages(void)
0x18004cd16  mov     rcx, [rsi+88h]; this
0x18004cd1d  call    ?Release@CWcnMessageSinkSession@@QEAAXXZ; CWcnMessageSinkSession::Release(void)
0x18004cd22  mov     qword ptr [rsi+88h], 0
0x18004cd2d  mov     rcx, [rsi+98h]
0x18004cd34  add     rsp, 20h
0x18004cd38  pop     r14
0x18004cd3a  pop     rdi
0x18004cd3b  pop     rsi
0x18004cd3c  pop     rbp
0x18004cd3d  pop     rbx
0x18004cd3e  jmp     cs:__imp_SubmitThreadpoolWork
```
