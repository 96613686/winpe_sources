# HTTP_LOG_PENDING_CONTEXT::~HTTP_LOG_PENDING_CONTEXT(void)

- ea: `0x180008cf4`
- end: `0x180008da4`
- name: `??1HTTP_LOG_PENDING_CONTEXT@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(HTTP_LOG_PENDING_CONTEXT *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000921c`
- `0x180009604`
- `0x180009d10`

## callees

- `0x1800062c4`
- `0x180008cf4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d27`

## pseudocode

```c
void __fastcall HTTP_LOG_PENDING_CONTEXT::~HTTP_LOG_PENDING_CONTEXT(HTTP_LOG_PENDING_CONTEXT *this)
{
  __int64 v2; // rcx
  __int64 i; // rdi
  __int64 v4; // rcx

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *((_QWORD *)this + 3) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 80048));
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 20010); i = (unsigned int)(i + 1) )
  {
    v4 = *((_QWORD *)this + i + 5);
    if ( v4 )
    {
      *(_QWORD *)(v4 + 816) = 0;
      LOG_WRITER::Write(*(RTL_SRWLOCK **)(v4 + 1184), (struct HTTP_LOG_CONTEXT *)v4);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + i + 5) + 8LL))(*((_QWORD *)this + i + 5));
      *((_QWORD *)this + i + 5) = 0;
    }
  }
  *((_DWORD *)this + 20010) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 80048));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 80048));
}

```

## disassembly

```asm
0x180008cf4  push    rbx
0x180008cf6  push    rbp
0x180008cf7  push    rsi
0x180008cf8  push    rdi
0x180008cf9  sub     rsp, 28h
0x180008cfd  mov     rbx, rcx
0x180008d00  mov     rcx, [rcx+18h]
0x180008d04  test    rcx, rcx
0x180008d07  jz      short loc_180008D1D
0x180008d09  mov     rax, [rcx]
0x180008d0c  mov     rax, [rax+8]
0x180008d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d15  mov     qword ptr [rbx+18h], 0
0x180008d1d  lea     rsi, [rbx+138B0h]
0x180008d24  mov     rcx, rsi; lpCriticalSection
0x180008d27  call    cs:__imp_EnterCriticalSection
0x180008d2d  xor     edi, edi
0x180008d2f  cmp     [rbx+138A8h], edi
0x180008d35  jbe     short loc_180008D7F
0x180008d37  mov     rcx, [rbx+rdi*8+28h]
0x180008d3c  test    rcx, rcx
0x180008d3f  jz      short loc_180008D75
0x180008d41  mov     qword ptr [rcx+330h], 0
0x180008d4c  mov     rdx, rcx; struct HTTP_LOG_CONTEXT *
0x180008d4f  mov     rcx, [rcx+4A0h]; this
0x180008d56  call    ?Write@LOG_WRITER@@QEAAJPEAVHTTP_LOG_CONTEXT@@@Z; LOG_WRITER::Write(HTTP_LOG_CONTEXT *)
0x180008d5b  mov     rcx, [rbx+rdi*8+28h]
0x180008d60  mov     rax, [rcx]
0x180008d63  mov     rax, [rax+8]
0x180008d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d6c  mov     qword ptr [rbx+rdi*8+28h], 0
0x180008d75  inc     edi
0x180008d77  cmp     edi, [rbx+138A8h]
0x180008d7d  jb      short loc_180008D37
0x180008d7f  mov     dword ptr [rbx+138A8h], 0
0x180008d89  mov     rcx, rsi; lpCriticalSection
0x180008d8c  call    cs:__imp_LeaveCriticalSection
0x180008d92  mov     rcx, rsi
0x180008d95  add     rsp, 28h
0x180008d99  pop     rdi
0x180008d9a  pop     rsi
0x180008d9b  pop     rbp
0x180008d9c  pop     rbx
0x180008d9d  jmp     cs:__imp_DeleteCriticalSection
```
