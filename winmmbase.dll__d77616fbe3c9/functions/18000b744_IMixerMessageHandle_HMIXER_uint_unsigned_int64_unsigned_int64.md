# IMixerMessageHandle(HMIXER__ *,uint,unsigned __int64,unsigned __int64)

- ea: `0x18000b744`
- end: `0x18000b7ec`
- name: `?IMixerMessageHandle@@YAKPEAUHMIXER__@@I_K1@Z`
- size: `168`
- prototype: `unsigned int __fastcall(HMIXER, unsigned int, unsigned __int64, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000af80`
- `0x18000b090`
- `0x18000b800`
- `0x18001a7a0`
- `0x18001ac10`
- `0x18001ac80`

## callees

- `0x180007560`
- `0x18000b744`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b75f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b77a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b75f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b77a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b7ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b7c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b7ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b7c4`

## pseudocode

```c
__int64 __fastcall IMixerMessageHandle(struct _RTL_CRITICAL_SECTION *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  LONG RecursionCount; // ecx
  unsigned int v9; // ebx

  EnterCriticalSection(a1 - 1);
  RecursionCount = a1[-2].RecursionCount;
  if ( (RecursionCount & 1) != 0 )
  {
    v9 = 6;
  }
  else if ( (RecursionCount & 2) != 0 )
  {
    v9 = 12;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)a1->OwningThread + 3);
    if ( ValidateHandle((unsigned __int64)a1, 8) )
      v9 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, ULONG_PTR, __int64, __int64))a1->OwningThread + 10))(
             LODWORD(a1->LockSemaphore),
             a2,
             a1->SpinCount,
             a3,
             a4);
    else
      v9 = 5;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1->OwningThread + 3);
  }
  LeaveCriticalSection(a1 - 1);
  return v9;
}

```

## disassembly

```asm
0x18000b744  push    rbx
0x18000b746  push    rbp
0x18000b747  push    rsi
0x18000b748  push    rdi
0x18000b749  push    r14
0x18000b74b  sub     rsp, 30h
0x18000b74f  mov     rdi, rcx
0x18000b752  mov     rbx, r9
0x18000b755  add     rcx, 0FFFFFFFFFFFFFFD8h; lpCriticalSection
0x18000b759  mov     rbp, r8
0x18000b75c  mov     r14d, edx
0x18000b75f  call    cs:__imp_EnterCriticalSection
0x18000b765  mov     ecx, [rdi-44h]
0x18000b768  test    cl, 1
0x18000b76b  jnz     short loc_18000B7D7
0x18000b76d  test    cl, 2
0x18000b770  jnz     short loc_18000B7DE
0x18000b772  mov     rcx, [rdi+10h]
0x18000b776  add     rcx, 78h ; 'x'; lpCriticalSection
0x18000b77a  call    cs:__imp_EnterCriticalSection
0x18000b780  mov     edx, 8
0x18000b785  mov     rcx, rdi
0x18000b788  call    ValidateHandle
0x18000b78d  test    eax, eax
0x18000b78f  jz      short loc_18000B7E5
0x18000b791  mov     rax, [rdi+10h]
0x18000b795  mov     r9, rbp
0x18000b798  mov     r8, [rdi+20h]
0x18000b79c  mov     edx, r14d
0x18000b79f  mov     ecx, [rdi+18h]
0x18000b7a2  mov     [rsp+58h+var_38], rbx
0x18000b7a7  mov     rax, [rax+50h]
0x18000b7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7b0  mov     ebx, eax
0x18000b7b2  mov     rcx, [rdi+10h]
0x18000b7b6  add     rcx, 78h ; 'x'; lpCriticalSection
0x18000b7ba  call    cs:__imp_LeaveCriticalSection
0x18000b7c0  lea     rcx, [rdi-28h]; lpCriticalSection
0x18000b7c4  call    cs:__imp_LeaveCriticalSection
0x18000b7ca  mov     eax, ebx
0x18000b7cc  add     rsp, 30h
0x18000b7d0  pop     r14
0x18000b7d2  pop     rdi
0x18000b7d3  pop     rsi
0x18000b7d4  pop     rbp
0x18000b7d5  pop     rbx
0x18000b7d6  retn
0x18000b7d7  mov     ebx, 6
0x18000b7dc  jmp     short loc_18000B7C0
0x18000b7de  mov     ebx, 0Ch
0x18000b7e3  jmp     short loc_18000B7C0
0x18000b7e5  mov     ebx, 5
0x18000b7ea  jmp     short loc_18000B7B2
```
