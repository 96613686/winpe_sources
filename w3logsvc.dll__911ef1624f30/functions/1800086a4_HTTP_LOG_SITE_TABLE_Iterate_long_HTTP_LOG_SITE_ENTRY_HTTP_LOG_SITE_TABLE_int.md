# HTTP_LOG_SITE_TABLE::Iterate(long (*)(HTTP_LOG_SITE_ENTRY *,HTTP_LOG_SITE_TABLE *),int)

- ea: `0x1800086a4`
- end: `0x180008729`
- name: `?Iterate@HTTP_LOG_SITE_TABLE@@AEAAJP6AJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@ZH@Z`
- size: `133`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, int (*)(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *), int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ed0`
- `0x1800080d0`
- `0x180008858`
- `0x18000d180`

## callees

- `0x1800086a4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008714`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008714`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800086c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800086c7`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_TABLE::Iterate(
        RTL_SRWLOCK *this,
        int (*a2)(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *),
        int a3)
{
  int v3; // esi
  int v4; // ebp
  __int64 i; // rbx
  _QWORD *Ptr; // rax
  _QWORD *v9; // r14

  v3 = 0;
  v4 = 0;
  if ( a3 )
  {
    AcquireSRWLockExclusive(this + 137);
    v4 = 1;
  }
  for ( i = 0; i != 131; ++i )
  {
    Ptr = this[i + 1].Ptr;
    if ( Ptr )
    {
      do
      {
        v9 = (_QWORD *)Ptr[1];
        v3 = ((__int64 (__fastcall *)(_QWORD *, RTL_SRWLOCK *))a2)(Ptr - 1, this);
        if ( v3 < 0 )
          break;
        Ptr = v9;
      }
      while ( v9 );
    }
  }
  if ( v4 )
    ReleaseSRWLockExclusive(this + 137);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800086a4  push    rbx
0x1800086a6  push    rbp
0x1800086a7  push    rsi
0x1800086a8  push    rdi
0x1800086a9  push    r14
0x1800086ab  push    r15
0x1800086ad  sub     rsp, 28h
0x1800086b1  xor     esi, esi
0x1800086b3  xor     ebp, ebp
0x1800086b5  mov     r15, rdx
0x1800086b8  mov     rdi, rcx
0x1800086bb  test    r8d, r8d
0x1800086be  jz      short loc_1800086D0
0x1800086c0  add     rcx, 448h; SRWLock
0x1800086c7  call    cs:__imp_AcquireSRWLockExclusive
0x1800086cd  lea     ebp, [rsi+1]
0x1800086d0  xor     ebx, ebx
0x1800086d2  mov     rax, [rdi+rbx*8+8]
0x1800086d7  test    rax, rax
0x1800086da  jz      short loc_1800086FD
0x1800086dc  mov     r14, [rax+8]
0x1800086e0  lea     rcx, [rax-8]
0x1800086e4  mov     rax, r15
0x1800086e7  mov     rdx, rdi
0x1800086ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ef  mov     esi, eax
0x1800086f1  test    eax, eax
0x1800086f3  js      short loc_1800086FD
0x1800086f5  mov     rax, r14
0x1800086f8  test    r14, r14
0x1800086fb  jnz     short loc_1800086DC
0x1800086fd  inc     rbx
0x180008700  cmp     rbx, 83h
0x180008707  jnz     short loc_1800086D2
0x180008709  test    ebp, ebp
0x18000870b  jz      short loc_18000871A
0x18000870d  lea     rcx, [rdi+448h]; SRWLock
0x180008714  call    cs:__imp_ReleaseSRWLockExclusive
0x18000871a  mov     eax, esi
0x18000871c  add     rsp, 28h
0x180008720  pop     r15
0x180008722  pop     r14
0x180008724  pop     rdi
0x180008725  pop     rsi
0x180008726  pop     rbp
0x180008727  pop     rbx
0x180008728  retn
```
