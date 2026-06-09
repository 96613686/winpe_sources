# CWcnPeer::~CWcnPeer(void)

- ea: `0x18001d9dc`
- end: `0x18001da9d`
- name: `??1CWcnPeer@@QEAA@XZ`
- size: `193`
- prototype: `void __fastcall(CWcnPeer *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000e714`
- `0x18001daa4`

## callees

- `0x18000a5ac`
- `0x18000b414`
- `0x18001d9dc`
- `0x18005a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001da36`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da59`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da79`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da36`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da59`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da79`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001da83`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001da83`

## pseudocode

```c
void __fastcall CWcnPeer::~CWcnPeer(CWcnPeer *this)
{
  unsigned int i; // ebx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  CSbSafeBuffer ***v4; // rbx
  CSbSafeBuffer **v5; // rbp
  CSbSafeBuffer **j; // rbx
  CSbSafeBuffer *v7; // rsi
  __int64 v8; // rbx

  for ( i = 0; i < 7; ++i )
  {
    v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + (int)i + 7);
    if ( v3 )
      (**v3)(v3, 1);
  }
  v4 = (CSbSafeBuffer ***)*((_QWORD *)this + 32);
  if ( v4 )
  {
    v5 = v4[1];
    for ( j = *v4; j != v5; ++j )
    {
      v7 = *j;
      if ( *j )
      {
        CSbSafeBuffer::~CSbSafeBuffer(*j);
        operator delete(v7);
      }
    }
    v8 = *((_QWORD *)this + 32);
    if ( v8 )
    {
      if ( *(_QWORD *)v8 )
      {
        operator delete(*(void **)v8);
        *(_QWORD *)v8 = 0;
        *(_QWORD *)(v8 + 8) = 0;
        *(_QWORD *)(v8 + 16) = 0;
      }
      operator delete((void *)v8);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CWcnIdentity::~CWcnIdentity((CWcnPeer *)((char *)this + 136));
}

```

## disassembly

```asm
0x18001d9dc  push    rbx
0x18001d9de  push    rbp
0x18001d9df  push    rsi
0x18001d9e0  push    rdi
0x18001d9e1  sub     rsp, 28h
0x18001d9e5  mov     rdi, rcx
0x18001d9e8  xor     ebx, ebx
0x18001d9ea  movsxd  rax, ebx
0x18001d9ed  mov     rcx, [rdi+rax*8+38h]
0x18001d9f2  test    rcx, rcx
0x18001d9f5  jz      short loc_18001DA07
0x18001d9f7  mov     rax, [rcx]
0x18001d9fa  mov     edx, 1
0x18001d9ff  mov     rax, [rax]
0x18001da02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da07  inc     ebx
0x18001da09  cmp     ebx, 7
0x18001da0c  jb      short loc_18001D9EA
0x18001da0e  mov     rbx, [rdi+100h]
0x18001da15  test    rbx, rbx
0x18001da18  jz      short loc_18001DA7F
0x18001da1a  mov     rbp, [rbx+8]
0x18001da1e  mov     rbx, [rbx]
0x18001da21  jmp     short loc_18001DA40
0x18001da23  mov     rsi, [rbx]
0x18001da26  test    rsi, rsi
0x18001da29  jz      short loc_18001DA3C
0x18001da2b  mov     rcx, rsi; this
0x18001da2e  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18001da33  mov     rcx, rsi
0x18001da36  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001da3c  add     rbx, 8
0x18001da40  cmp     rbx, rbp
0x18001da43  jnz     short loc_18001DA23
0x18001da45  mov     rbx, [rdi+100h]
0x18001da4c  test    rbx, rbx
0x18001da4f  jz      short loc_18001DA7F
0x18001da51  mov     rcx, [rbx]
0x18001da54  test    rcx, rcx
0x18001da57  jz      short loc_18001DA76
0x18001da59  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001da5f  mov     qword ptr [rbx], 0
0x18001da66  mov     qword ptr [rbx+8], 0
0x18001da6e  mov     qword ptr [rbx+10h], 0
0x18001da76  mov     rcx, rbx
0x18001da79  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001da7f  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001da83  call    cs:__imp_DeleteCriticalSection
0x18001da89  lea     rcx, [rdi+88h]; this
0x18001da90  add     rsp, 28h
0x18001da94  pop     rdi
0x18001da95  pop     rsi
0x18001da96  pop     rbp
0x18001da97  pop     rbx
0x18001da98  jmp     ??1CWcnIdentity@@QEAA@XZ; CWcnIdentity::~CWcnIdentity(void)
```
