# SkpspCreateTeb

- ea: `0x1400af528`
- end: `0x1400af6b9`
- name: `SkpspCreateTeb`
- size: `401`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140033b58`
- `0x1400b068c`

## callees

- `0x14002ba08`
- `0x14005af28`
- `0x14005b9e4`
- `0x1400af528`
- `0x1400fc554`
- `0x1400fc718`
- `0x1400fc7c0`
- `0x1400fc84c`
- `0x1400fee4c`
- `0x1400ff128`

## string_xrefs

- `0x1400af5a7`: `TebCreate: User page alloc failed.\n`

## pseudocode

```c
__int64 __fastcall SkpspCreateTeb(_QWORD *a1, _QWORD *a2, __int64 a3, __int64 a4, unsigned __int16 a5, int a6, int a7)
{
  __int64 result; // rax
  char *PebOrTeb; // rax
  char *v13; // rbx
  ULONG_PTR v14; // [rsp+20h] [rbp-78h]
  __int128 v15; // [rsp+38h] [rbp-60h] BYREF
  __int128 Src; // [rsp+48h] [rbp-50h] BYREF
  __int128 v17; // [rsp+58h] [rbp-40h]
  __int128 v18; // [rsp+68h] [rbp-30h]
  char *v19; // [rsp+78h] [rbp-20h]

  v15 = 0;
  Src = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  result = RtlCreateUserStack(a6, a7, a3, a4, v14, (__int64)a2);
  if ( (int)result >= 0 )
  {
    PebOrTeb = (char *)SkmiAllocatePebOrTeb(6256);
    v13 = PebOrTeb;
    if ( PebOrTeb )
    {
      *(_QWORD *)&Src = 0;
      *((_QWORD *)&v17 + 1) = 0;
      v18 = 0x1E00u;
      *((_QWORD *)&Src + 1) = a2[2];
      *(_QWORD *)&v17 = a2[3];
      v19 = PebOrTeb;
      *(_QWORD *)&v15 = *(_QWORD *)(a3 + 56);
      *((_QWORD *)&v15 + 1) = a4;
      RtlSetUserMemory(PebOrTeb);
      RtlWriteULong64ToUser(v13 + 96, *(_QWORD *)(a3 + 160));
      RtlWriteULong64ToUser(v13 + 5240, a2[4]);
      RtlWriteUShortToUser(v13 + 6126, a5);
      RtlCopyToUser(v13, &Src, 0x38u);
      RtlCopyToUser(v13 + 64, &v15, 0x10u);
      *a1 = v13;
      return 0;
    }
    else
    {
      DbgPrint("TebCreate: User page alloc failed.\n");
      return 3221225626LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400af528  mov     r11, rsp
0x1400af52b  mov     [r11+8], rbx
0x1400af52f  mov     [r11+18h], rsi
0x1400af533  mov     [r11+10h], rdx
0x1400af537  push    rdi
0x1400af538  push    r14
0x1400af53a  push    r15
0x1400af53c  sub     rsp, 80h
0x1400af543  mov     r15, r9
0x1400af546  mov     rsi, r8
0x1400af549  mov     rdi, rdx
0x1400af54c  mov     r14, rcx
0x1400af54f  xorps   xmm0, xmm0
0x1400af552  movups  [rsp+98h+var_60], xmm0
0x1400af557  xorps   xmm1, xmm1
0x1400af55a  xor     eax, eax
0x1400af55c  movups  [rsp+98h+Src], xmm1
0x1400af561  movups  [rsp+98h+var_40], xmm1
0x1400af566  movups  [rsp+98h+var_30], xmm1
0x1400af56b  mov     [r11-20h], rax
0x1400af56f  mov     [r11-70h], rdx
0x1400af573  mov     rdx, qword ptr [rsp+98h+arg_30]; int
0x1400af57b  mov     rcx, qword ptr [rsp+98h+arg_28]; int
0x1400af583  call    RtlCreateUserStack
0x1400af588  test    eax, eax
0x1400af58a  js      loc_1400AF69F
0x1400af590  mov     ecx, 1870h
0x1400af595  call    SkmiAllocatePebOrTeb
0x1400af59a  mov     rbx, rax
0x1400af59d  mov     [rsp+98h+var_68], rax
0x1400af5a2  test    rax, rax
0x1400af5a5  jnz     short loc_1400AF5BD
0x1400af5a7  lea     rcx, aTebcreateUserP; "TebCreate: User page alloc failed.\n"
0x1400af5ae  call    DbgPrint
0x1400af5b3  mov     eax, 0C000009Ah
0x1400af5b8  jmp     loc_1400AF69F
0x1400af5bd  mov     qword ptr [rsp+98h+Src], 0
0x1400af5c6  mov     qword ptr [rsp+98h+var_40+8], 0
0x1400af5cf  mov     qword ptr [rsp+98h+var_30+4], 0
0x1400af5d8  mov     dword ptr [rsp+98h+var_30+0Ch], 0
0x1400af5e0  mov     dword ptr [rsp+98h+var_30], 1E00h
0x1400af5e8  mov     rax, [rdi+10h]
0x1400af5ec  mov     qword ptr [rsp+98h+Src+8], rax
0x1400af5f1  mov     rax, [rdi+18h]
0x1400af5f5  mov     qword ptr [rsp+98h+var_40], rax
0x1400af5fa  mov     [rsp+98h+var_20], rbx
0x1400af5ff  mov     rax, [rsi+38h]
0x1400af603  mov     qword ptr [rsp+98h+var_60], rax
0x1400af608  mov     qword ptr [rsp+98h+var_60+8], r15
0x1400af60d  xor     edx, edx
0x1400af60f  mov     r8d, 1870h
0x1400af615  mov     rcx, rbx; void *
0x1400af618  call    RtlSetUserMemory
0x1400af61d  lea     rcx, [rbx+60h]
0x1400af621  mov     rdx, [rsi+0A0h]
0x1400af628  call    RtlWriteULong64ToUser
0x1400af62d  lea     rcx, [rbx+1478h]
0x1400af634  mov     rdx, [rdi+20h]
0x1400af638  call    RtlWriteULong64ToUser
0x1400af63d  lea     rcx, [rbx+17EEh]
0x1400af644  movzx   edx, [rsp+98h+arg_20]
0x1400af64c  call    RtlWriteUShortToUser
0x1400af651  mov     r8d, 38h ; '8'; Size
0x1400af657  lea     rdx, [rsp+98h+Src]; Src
0x1400af65c  mov     rcx, rbx; void *
0x1400af65f  call    RtlCopyToUser
0x1400af664  lea     rcx, [rbx+40h]; void *
0x1400af668  mov     r8d, 10h; Size
0x1400af66e  lea     rdx, [rsp+98h+var_60]; Src
0x1400af673  call    RtlCopyToUser
0x1400af678  nop
0x1400af679  mov     [r14], rbx
0x1400af67c  xor     eax, eax
0x1400af67e  jmp     short loc_1400AF69F
0x1400af680  mov     ebx, eax
0x1400af682  mov     rcx, [rsp+98h+arg_8]
0x1400af68a  mov     rcx, [rcx+20h]
0x1400af68e  call    RtlFreeUserStack
0x1400af693  mov     rcx, [rsp+98h+var_68]
0x1400af698  call    SkmmFreeTeb
0x1400af69d  mov     eax, ebx
0x1400af69f  lea     r11, [rsp+98h+var_18]
0x1400af6a7  mov     rbx, [r11+20h]
0x1400af6ab  mov     rsi, [r11+30h]
0x1400af6af  mov     rsp, r11
0x1400af6b2  pop     r15
0x1400af6b4  pop     r14
0x1400af6b6  pop     rdi
0x1400af6b7  retn
```
