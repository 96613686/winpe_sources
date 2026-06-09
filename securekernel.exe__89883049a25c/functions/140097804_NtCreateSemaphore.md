# NtCreateSemaphore

- ea: `0x140097804`
- end: `0x1400979f0`
- name: `NtCreateSemaphore`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140002ef0`
- `0x140097804`
- `0x1400a0c00`
- `0x1400a0df8`
- `0x1400a18a0`
- `0x1400eff90`
- `0x1400f02c0`
- `0x1400fc664`
- `0x1400fc7c0`

## pseudocode

```c
__int64 __fastcall NtCreateSemaphore(_QWORD *a1, unsigned int a2, __int64 a3, int a4, int a5)
{
  char v9; // r12
  __int64 ULong64FromUser; // rdi
  int Semaphore; // ebx
  __int64 v12; // rdi
  __int64 v13; // rsi
  __int64 v15; // [rsp+38h] [rbp-60h] BYREF
  __int64 v16; // [rsp+40h] [rbp-58h]
  _DWORD *v17; // [rsp+48h] [rbp-50h] BYREF
  __int64 v18; // [rsp+50h] [rbp-48h]

  v15 = 0;
  v17 = 0;
  v9 = *((_BYTE *)KeGetPcr()->NtTib.StackBase + 96);
  ULong64FromUser = 0;
  v18 = 0;
  if ( a4 < 0 || a5 <= 0 || a4 > a5 )
  {
    Semaphore = -1073741811;
  }
  else
  {
    if ( a3 && v9 == 1 )
    {
      ULong64FromUser = RtlReadULong64FromUser((volatile void *)(a3 + 16));
      v18 = ULong64FromUser;
    }
    Semaphore = NkCreateSemaphore(a1, a2, a3, (unsigned int)a4, a5);
  }
  if ( Semaphore >= 0 && !ULong64FromUser )
  {
    v16 = 0;
    if ( v9 == 1 )
    {
      v12 = RtlReadULong64FromUser(a1);
      v16 = v12;
      Semaphore = SkobCreateObjectEx(0, (__int64)&SkeShadowSyncObjectType, 0, &v17);
      if ( Semaphore >= 0 )
      {
        v13 = (__int64)v17;
        *v17 = 2;
        *(_BYTE *)(v13 + 4) = 0;
        *(_DWORD *)(v13 + 8) = a4;
        *(_DWORD *)(v13 + 12) = a5;
        Semaphore = SkobCreateHandle(v13, 0, v12, (__int64)&v15);
        if ( Semaphore >= 0 )
          RtlWriteULong64ToUser(a1, v15);
        SkobDereferenceObject(v13);
      }
      if ( Semaphore < 0 && v12 )
        NkClose(v12);
    }
  }
  return (unsigned int)Semaphore;
}

```

## disassembly

```asm
0x140097804  mov     rax, rsp
0x140097807  mov     [rax+20h], r9d
0x14009780b  mov     [rax+18h], r8
0x14009780f  mov     [rax+10h], edx
0x140097812  mov     [rax+8], rcx
0x140097816  push    rbx
0x140097817  push    rsi
0x140097818  push    rdi
0x140097819  push    r12
0x14009781b  push    r13
0x14009781d  push    r14
0x14009781f  push    r15
0x140097821  sub     rsp, 60h
0x140097825  mov     r14d, r9d
0x140097828  mov     rsi, r8
0x14009782b  mov     r13d, edx
0x14009782e  mov     r15, rcx
0x140097831  mov     qword ptr [rax-60h], 0
0x140097839  mov     qword ptr [rax-50h], 0
0x140097841  mov     rax, gs:8
0x14009784a  mov     r12b, [rax+60h]
0x14009784e  mov     [rsp+98h+var_68], r12b
0x140097853  xor     edi, edi
0x140097855  mov     [rsp+98h+var_48], rdi
0x14009785a  test    r9d, r9d
0x14009785d  js      loc_1400978E7
0x140097863  mov     eax, [rsp+98h+arg_20]
0x14009786a  test    eax, eax
0x14009786c  jle     short loc_1400978E7
0x14009786e  cmp     r9d, eax
0x140097871  jg      short loc_1400978E7
0x140097873  xor     ebx, ebx
0x140097875  test    r8, r8
0x140097878  jz      short loc_1400978BF
0x14009787a  cmp     r12b, 1
0x14009787e  jnz     short loc_1400978BF
0x140097880  lea     rcx, [r8+10h]
0x140097884  call    RtlReadULong64FromUser
0x140097889  mov     rdi, rax
0x14009788c  mov     [rsp+98h+var_48], rax
0x140097891  jmp     short loc_1400978BF
0x140097893  mov     ebx, eax
0x140097895  mov     r14d, [rsp+98h+arg_18]
0x14009789d  mov     rsi, [rsp+98h+arg_10]
0x1400978a5  mov     r13d, [rsp+98h+arg_8]
0x1400978ad  mov     r15, [rsp+98h+arg_0]
0x1400978b5  mov     rdi, [rsp+98h+var_48]
0x1400978ba  mov     r12b, [rsp+98h+var_68]
0x1400978bf  test    ebx, ebx
0x1400978c1  js      loc_1400979DD
0x1400978c7  mov     eax, [rsp+98h+arg_20]
0x1400978ce  mov     dword ptr [rsp+98h+var_78], eax
0x1400978d2  mov     r9d, r14d
0x1400978d5  mov     r8, rsi
0x1400978d8  mov     edx, r13d
0x1400978db  mov     rcx, r15
0x1400978de  call    NkCreateSemaphore
0x1400978e3  mov     ebx, eax
0x1400978e5  jmp     short loc_1400978EC
0x1400978e7  mov     ebx, 0C000000Dh
0x1400978ec  test    ebx, ebx
0x1400978ee  js      loc_1400979DD
0x1400978f4  test    rdi, rdi
0x1400978f7  jnz     loc_1400979DD
0x1400978fd  mov     [rsp+98h+var_58], rdi
0x140097902  cmp     r12b, 1
0x140097906  jnz     loc_1400979DD
0x14009790c  mov     rcx, r15
0x14009790f  call    RtlReadULong64FromUser
0x140097914  mov     rdi, rax
0x140097917  mov     [rsp+98h+var_58], rax
0x14009791c  jmp     short loc_140097935
0x14009791e  mov     ebx, eax
0x140097920  mov     r14d, [rsp+98h+arg_18]
0x140097928  mov     r15, [rsp+98h+arg_0]
0x140097930  mov     rdi, [rsp+98h+var_58]
0x140097935  test    ebx, ebx
0x140097937  js      loc_1400979D0
0x14009793d  lea     r9, [rsp+98h+var_50]
0x140097942  xor     r8d, r8d
0x140097945  lea     rdx, SkeShadowSyncObjectType
0x14009794c  xor     ecx, ecx
0x14009794e  call    SkobCreateObjectEx
0x140097953  mov     ebx, eax
0x140097955  test    eax, eax
0x140097957  js      short loc_1400979CC
0x140097959  mov     rsi, [rsp+98h+var_50]
0x14009795e  mov     dword ptr [rsi], 2
0x140097964  mov     byte ptr [rsi+4], 0
0x140097968  mov     [rsi+8], r14d
0x14009796c  mov     eax, [rsp+98h+arg_20]
0x140097973  mov     [rsi+0Ch], eax
0x140097976  lea     r9, [rsp+98h+var_60]
0x14009797b  mov     r8, rdi
0x14009797e  xor     edx, edx
0x140097980  mov     rcx, rsi
0x140097983  call    SkobCreateHandle
0x140097988  mov     ebx, eax
0x14009798a  test    eax, eax
0x14009798c  js      short loc_1400979C4
0x14009798e  mov     rdx, [rsp+98h+var_60]
0x140097993  mov     rcx, r15
0x140097996  call    RtlWriteULong64ToUser
0x14009799b  jmp     short loc_1400979C4
0x14009799d  mov     ebx, eax
0x14009799f  mov     [rsp+98h+var_78], 0
0x1400979a8  xor     r9d, r9d
0x1400979ab  xor     r8d, r8d
0x1400979ae  xor     edx, edx
0x1400979b0  mov     rcx, [rsp+98h+var_60]
0x1400979b5  call    SkobCloseHandleEx
0x1400979ba  mov     rdi, [rsp+98h+var_58]
0x1400979bf  mov     rsi, [rsp+98h+var_50]
0x1400979c4  mov     rcx, rsi
0x1400979c7  call    SkobDereferenceObject
0x1400979cc  test    ebx, ebx
0x1400979ce  jns     short loc_1400979DD
0x1400979d0  test    rdi, rdi
0x1400979d3  jz      short loc_1400979DD
0x1400979d5  mov     rcx, rdi
0x1400979d8  call    NkClose
0x1400979dd  mov     eax, ebx
0x1400979df  add     rsp, 60h
0x1400979e3  pop     r15
0x1400979e5  pop     r14
0x1400979e7  pop     r13
0x1400979e9  pop     r12
0x1400979eb  pop     rdi
0x1400979ec  pop     rsi
0x1400979ed  pop     rbx
0x1400979ee  retn
```
