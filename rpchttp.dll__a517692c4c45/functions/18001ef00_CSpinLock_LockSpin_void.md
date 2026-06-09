# CSpinLock::_LockSpin(void)

- ea: `0x18001ef00`
- end: `0x18001efe2`
- name: `?_LockSpin@CSpinLock@@AEAAXXZ`
- size: `226`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010c30`

## callees

- `0x18001eeb4`
- `0x18001eed4`
- `0x18001ef00`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001ef10`
- `KERNEL32!GetCurrentThreadId` at `0x18001efb6`
- `KERNEL32!GetCurrentThreadId` at `0x18001ef10`
- `KERNEL32!GetCurrentThreadId` at `0x18001efb6`

## pseudocode

```c
void __fastcall CSpinLock::_LockSpin(CSpinLock *this)
{
  DWORD v2; // ebp
  unsigned int v3; // esi
  int v4; // ebx
  int v5; // edx

  v2 = 0;
  v3 = 0;
  v4 = (int)(*(double *)&qword_180028700[GetCurrentThreadId() % 0xD] * 4000.0);
  while ( 1 )
  {
    if ( gNumberOfProcessors <= 1 )
    {
      SwitchOrSleep(v2);
      v2 = SleepTime(v3);
    }
    else
    {
      v5 = v4;
      while ( *(_DWORD *)this )
      {
        if ( --v5 < 0 )
        {
          SwitchOrSleep(v2);
          v4 = (int)((double)v4 * 0.5);
          if ( v4 <= 10000 )
          {
            if ( v4 <= 100 )
              v4 = 100;
          }
          else
          {
            v4 = 10000;
          }
          v2 = SleepTime(v3);
        }
      }
    }
    if ( !*(_DWORD *)this
      && !_InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFF | 0x10000000, 0) )
    {
      break;
    }
    ++v3;
  }
}

```

## disassembly

```asm
0x18001ef00  push    rbx
0x18001ef02  push    rbp
0x18001ef03  push    rsi
0x18001ef04  push    rdi
0x18001ef05  push    r15
0x18001ef07  sub     rsp, 20h
0x18001ef0b  mov     rdi, rcx
0x18001ef0e  xor     ebp, ebp
0x18001ef10  call    cs:__imp_GetCurrentThreadId
0x18001ef16  mov     r9d, eax
0x18001ef19  lea     rcx, qword_180028700
0x18001ef20  mov     eax, 4EC4EC4Fh
0x18001ef25  lea     r15d, [rbp+64h]
0x18001ef29  mul     r9d
0x18001ef2c  shr     edx, 2
0x18001ef2f  imul    r8d, edx, 0Dh
0x18001ef33  sub     r9d, r8d
0x18001ef36  xor     esi, esi
0x18001ef38  movsd   xmm0, qword ptr [rcx+r9*8]
0x18001ef3e  mulsd   xmm0, cs:__real@40af400000000000
0x18001ef46  cvttsd2si ebx, xmm0
0x18001ef4a  cmp     cs:?gNumberOfProcessors@@3IA, 1; uint gNumberOfProcessors
0x18001ef51  jbe     short loc_18001EFA0
0x18001ef53  mov     edx, ebx
0x18001ef55  jmp     short loc_18001EF98
0x18001ef57  sub     edx, 1
0x18001ef5a  jns     short loc_18001EF98
0x18001ef5c  mov     ecx, ebp; dwMilliseconds
0x18001ef5e  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18001ef63  movd    xmm0, ebx
0x18001ef67  cvtdq2pd xmm0, xmm0
0x18001ef6b  mulsd   xmm0, cs:__real@3fe0000000000000
0x18001ef73  cvttsd2si ebx, xmm0
0x18001ef77  cmp     ebx, 2710h
0x18001ef7d  jle     short loc_18001EF86
0x18001ef7f  mov     ebx, 2710h
0x18001ef84  jmp     short loc_18001EF8D
0x18001ef86  cmp     ebx, r15d
0x18001ef89  cmovle  ebx, r15d
0x18001ef8d  mov     ecx, esi; unsigned int
0x18001ef8f  mov     edx, ebx
0x18001ef91  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18001ef96  mov     ebp, eax
0x18001ef98  mov     eax, [rdi]
0x18001ef9a  test    eax, eax
0x18001ef9c  jnz     short loc_18001EF57
0x18001ef9e  jmp     short loc_18001EFB0
0x18001efa0  mov     ecx, ebp; dwMilliseconds
0x18001efa2  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18001efa7  mov     ecx, esi; unsigned int
0x18001efa9  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18001efae  mov     ebp, eax
0x18001efb0  mov     eax, [rdi]
0x18001efb2  test    eax, eax
0x18001efb4  jnz     short loc_18001EFD0
0x18001efb6  call    cs:__imp_GetCurrentThreadId
0x18001efbc  mov     ecx, eax
0x18001efbe  and     ecx, 0FFFFFFFh
0x18001efc4  bts     ecx, 1Ch
0x18001efc8  xor     eax, eax
0x18001efca  lock cmpxchg [rdi], ecx
0x18001efce  jz      short loc_18001EFD7
0x18001efd0  inc     esi
0x18001efd2  jmp     loc_18001EF4A
0x18001efd7  add     rsp, 20h
0x18001efdb  pop     r15
0x18001efdd  pop     rdi
0x18001efde  pop     rsi
0x18001efdf  pop     rbp
0x18001efe0  pop     rbx
0x18001efe1  retn
```
