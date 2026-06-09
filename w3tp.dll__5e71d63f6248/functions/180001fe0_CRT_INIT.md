# _CRT_INIT

- ea: `0x180001fe0`
- end: `0x180002205`
- name: `_CRT_INIT`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002254`

## callees

- `0x180001fe0`
- `0x180002496`
- `0x180002500`
- `0x180002667`
- `0x180004210`

## import_xrefs

- `msvcrt!free` at `0x1800020bf`
- `msvcrt!free` at `0x1800020bf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000202b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000211f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000202b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000211f`

## pseudocode

```c
__int64 __fastcall CRT_INIT(__int64 a1, int a2, __int64 a3)
{
  int v5; // ebp
  PVOID StackBase; // rdi
  signed __int64 v7; // rax
  void (**v8)(void); // rsi
  void (**v9)(void); // rdi
  void *v10; // r15
  __int64 v11; // r14
  void (*v12)(void); // rax
  int v13; // esi
  PVOID v14; // rdi
  signed __int64 v15; // rax
  __int64 (**v16)(void); // rdi
  int v17; // eax

  if ( !a2 )
  {
    if ( dword_1800090C0 > 0 )
    {
      --dword_1800090C0;
      v5 = 0;
      StackBase = NtCurrentTeb()->NtTib.StackBase;
      while ( 1 )
      {
        v7 = _InterlockedCompareExchange64(&_native_startup_lock, (signed __int64)StackBase, 0);
        if ( !v7 )
          break;
        if ( (PVOID)v7 == StackBase )
        {
          v5 = 1;
          break;
        }
        Sleep(0x3E8u);
      }
      if ( _native_startup_state == 2 )
      {
        v8 = (void (**)(void))_onexitbegin;
        if ( _onexitbegin )
        {
          v9 = (void (**)(void))_onexitend;
          v10 = _onexitbegin;
          v11 = _onexitend;
          while ( --v9 >= v8 )
          {
            v12 = *v9;
            if ( *v9 )
            {
              *v9 = 0;
              v12();
              if ( v10 != _onexitbegin || v11 != _onexitend )
              {
                v10 = _onexitbegin;
                v8 = (void (**)(void))_onexitbegin;
                v11 = _onexitend;
                v9 = (void (**)(void))_onexitend;
              }
            }
          }
          free(v8);
          _onexitend = 0;
          _onexitbegin = 0;
        }
        _native_startup_state = 0;
        if ( !v5 )
          _InterlockedExchange64(&_native_startup_lock, 0);
      }
      else
      {
        amsg_exit_0(31);
      }
      return 1;
    }
    return 0;
  }
  if ( a2 == 1 )
  {
    v13 = 0;
    v14 = NtCurrentTeb()->NtTib.StackBase;
    while ( 1 )
    {
      v15 = _InterlockedCompareExchange64(&_native_startup_lock, (signed __int64)v14, 0);
      if ( !v15 )
        break;
      if ( (PVOID)v15 == v14 )
      {
        v13 = 1;
        break;
      }
      Sleep(0x3E8u);
    }
    if ( _native_startup_state )
    {
      amsg_exit_0(31);
    }
    else
    {
      v16 = (__int64 (**)(void))&_xi_a;
      _native_startup_state = 1;
      v17 = 0;
      if ( &_xi_a < &_xi_z )
      {
        while ( !v17 )
        {
          if ( *v16 )
            v17 = (*v16)();
          if ( ++v16 >= (__int64 (**)(void))&_xi_z )
          {
            if ( !v17 )
              goto LABEL_37;
            return 0;
          }
        }
        return 0;
      }
LABEL_37:
      initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
      _native_startup_state = 2;
    }
    if ( !v13 )
      _InterlockedExchange64(&_native_startup_lock, 0);
    if ( _dyn_tls_init_callback && (unsigned int)IsNonwritableInCurrentImage(&_dyn_tls_init_callback) )
      ((void (__fastcall *)(__int64, __int64, __int64))_dyn_tls_init_callback)(a1, 2, a3);
    ++dword_1800090C0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001fe0  push    rbp
0x180001fe2  push    rsi
0x180001fe3  push    rdi
0x180001fe4  push    r14
0x180001fe6  push    r15
0x180001fe8  sub     rsp, 20h
0x180001fec  mov     rbp, r8
0x180001fef  mov     r14, rcx
0x180001ff2  test    edx, edx
0x180001ff4  jnz     loc_1800020FB
0x180001ffa  mov     eax, cs:dword_1800090C0
0x180002000  test    eax, eax
0x180002002  jle     loc_18000218E
0x180002008  dec     eax
0x18000200a  mov     cs:dword_1800090C0, eax
0x180002010  xor     ebp, ebp
0x180002012  mov     rax, gs:30h
0x18000201b  mov     rdi, [rax+8]
0x18000201f  jmp     short loc_180002031
0x180002021  cmp     rax, rdi
0x180002024  jz      short loc_180002040
0x180002026  mov     ecx, 3E8h; dwMilliseconds
0x18000202b  call    cs:__imp_Sleep
0x180002031  xor     eax, eax
0x180002033  lock cmpxchg cs:__native_startup_lock, rdi
0x18000203c  jnz     short loc_180002021
0x18000203e  jmp     short loc_180002045
0x180002040  mov     ebp, 1
0x180002045  mov     eax, cs:__native_startup_state
0x18000204b  cmp     eax, 2
0x18000204e  jz      short loc_18000205F
0x180002050  mov     ecx, 1Fh
0x180002055  call    _amsg_exit_0
0x18000205a  jmp     loc_1800021F4
0x18000205f  mov     rsi, cs:__onexitbegin
0x180002066  test    rsi, rsi
0x180002069  jz      short loc_1800020DB
0x18000206b  mov     rdi, cs:__onexitend
0x180002072  mov     r15, rsi
0x180002075  mov     r14, rdi
0x180002078  sub     rdi, 8
0x18000207c  cmp     rdi, rsi
0x18000207f  jb      short loc_1800020BC
0x180002081  mov     rax, [rdi]
0x180002084  test    rax, rax
0x180002087  jz      short loc_180002078
0x180002089  mov     qword ptr [rdi], 0
0x180002090  call    cs:__guard_dispatch_icall_fptr
0x180002096  mov     rcx, cs:__onexitbegin
0x18000209d  mov     rax, cs:__onexitend
0x1800020a4  cmp     r15, rcx
0x1800020a7  jnz     short loc_1800020AE
0x1800020a9  cmp     r14, rax
0x1800020ac  jz      short loc_180002078
0x1800020ae  mov     r15, rcx
0x1800020b1  mov     rsi, rcx
0x1800020b4  mov     r14, rax
0x1800020b7  mov     rdi, rax
0x1800020ba  jmp     short loc_180002078
0x1800020bc  mov     rcx, rsi; Block
0x1800020bf  call    cs:__imp_free
0x1800020c5  mov     cs:__onexitend, 0
0x1800020d0  mov     cs:__onexitbegin, 0
0x1800020db  mov     cs:__native_startup_state, 0
0x1800020e5  test    ebp, ebp
0x1800020e7  jnz     loc_1800021F4
0x1800020ed  xor     eax, eax
0x1800020ef  xchg    rax, cs:__native_startup_lock
0x1800020f6  jmp     loc_1800021F4
0x1800020fb  cmp     edx, 1
0x1800020fe  jnz     loc_1800021F4
0x180002104  mov     rax, gs:30h
0x18000210d  xor     esi, esi
0x18000210f  mov     rdi, [rax+8]
0x180002113  jmp     short loc_180002125
0x180002115  cmp     rax, rdi
0x180002118  jz      short loc_180002134
0x18000211a  mov     ecx, 3E8h; dwMilliseconds
0x18000211f  call    cs:__imp_Sleep
0x180002125  xor     eax, eax
0x180002127  lock cmpxchg cs:__native_startup_lock, rdi
0x180002130  jnz     short loc_180002115
0x180002132  jmp     short loc_180002139
0x180002134  mov     esi, 1
0x180002139  mov     eax, cs:__native_startup_state
0x18000213f  test    eax, eax
0x180002141  jz      short loc_18000214F
0x180002143  mov     ecx, 1Fh
0x180002148  call    _amsg_exit_0
0x18000214d  jmp     short loc_1800021AF
0x18000214f  lea     rdi, __xi_a
0x180002156  mov     cs:__native_startup_state, 1
0x180002160  xor     eax, eax
0x180002162  lea     r15, __xi_z
0x180002169  cmp     rdi, r15
0x18000216c  jnb     short loc_180002192
0x18000216e  test    eax, eax
0x180002170  jnz     short loc_18000218E
0x180002172  cmp     qword ptr [rdi], 0
0x180002176  jz      short loc_180002181
0x180002178  mov     rax, [rdi]
0x18000217b  call    cs:__guard_dispatch_icall_fptr
0x180002181  add     rdi, 8
0x180002185  cmp     rdi, r15
0x180002188  jb      short loc_18000216E
0x18000218a  test    eax, eax
0x18000218c  jz      short loc_180002192
0x18000218e  xor     eax, eax
0x180002190  jmp     short loc_1800021F9
0x180002192  lea     rdx, __xc_z; Last
0x180002199  lea     rcx, __xc_a; First
0x1800021a0  call    _initterm_0
0x1800021a5  mov     cs:__native_startup_state, 2
0x1800021af  test    esi, esi
0x1800021b1  jnz     short loc_1800021BC
0x1800021b3  xor     eax, eax
0x1800021b5  xchg    rax, cs:__native_startup_lock
0x1800021bc  cmp     cs:__dyn_tls_init_callback, 0
0x1800021c4  jz      short loc_1800021EE
0x1800021c6  lea     rcx, __dyn_tls_init_callback
0x1800021cd  call    _IsNonwritableInCurrentImage
0x1800021d2  test    eax, eax
0x1800021d4  jz      short loc_1800021EE
0x1800021d6  mov     rax, cs:__dyn_tls_init_callback
0x1800021dd  mov     r8, rbp
0x1800021e0  mov     edx, 2
0x1800021e5  mov     rcx, r14
0x1800021e8  call    cs:__guard_dispatch_icall_fptr
0x1800021ee  inc     cs:dword_1800090C0
0x1800021f4  mov     eax, 1
0x1800021f9  add     rsp, 20h
0x1800021fd  pop     r15
0x1800021ff  pop     r14
0x180002201  pop     rdi
0x180002202  pop     rsi
0x180002203  pop     rbp
0x180002204  retn
```
