# CDNNEvaluationRequestAsync::~CDNNEvaluationRequestAsync(void)

- ea: `0x18008b7b0`
- end: `0x18008b7fc`
- name: `??1CDNNEvaluationRequestAsync@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(CDNNEvaluationRequestAsync *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18008b7b0`
- `0x18008ba28`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008b7d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008b7d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008b7c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008b7c3`

## pseudocode

```c
void __fastcall CDNNEvaluationRequestAsync::~CDNNEvaluationRequestAsync(struct _TP_WORK **this, unsigned int a2)
{
  struct _TP_WORK *v3; // rcx
  struct _TP_WORK *v4; // rcx
  CMLP *v5; // rcx

  v3 = *this;
  if ( v3 )
  {
    WaitForThreadpoolWorkCallbacks(v3, 0);
    v4 = *this;
    *((_DWORD *)this + 6) = -1;
    CloseThreadpoolWork(v4);
    *this = 0;
  }
  v5 = this[2];
  if ( v5 )
  {
    CMLP::`scalar deleting destructor'(v5, a2);
    this[2] = 0;
  }
}

```

## disassembly

```asm
0x18008b7b0  push    rbx
0x18008b7b2  sub     rsp, 20h
0x18008b7b6  mov     rbx, rcx
0x18008b7b9  mov     rcx, [rcx]; pwk
0x18008b7bc  test    rcx, rcx
0x18008b7bf  jz      short loc_18008B7E0
0x18008b7c1  xor     edx, edx; fCancelPendingCallbacks
0x18008b7c3  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008b7c9  mov     rcx, [rbx]; pwk
0x18008b7cc  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x18008b7d3  call    cs:__imp_CloseThreadpoolWork
0x18008b7d9  mov     qword ptr [rbx], 0
0x18008b7e0  mov     rcx, [rbx+10h]; this
0x18008b7e4  test    rcx, rcx
0x18008b7e7  jz      short loc_18008B7F6
0x18008b7e9  call    ??_GCMLP@@QEAAPEAXI@Z; CMLP::`scalar deleting destructor'(uint)
0x18008b7ee  mov     qword ptr [rbx+10h], 0
0x18008b7f6  add     rsp, 20h
0x18008b7fa  pop     rbx
0x18008b7fb  retn
```
