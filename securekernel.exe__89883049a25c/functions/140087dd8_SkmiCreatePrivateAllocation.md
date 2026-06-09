# SkmiCreatePrivateAllocation

- ea: `0x140087dd8`
- end: `0x14008805a`
- name: `SkmiCreatePrivateAllocation`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140066464`

## callees

- `0x140002900`
- `0x14000b084`
- `0x14001e518`
- `0x140034d50`
- `0x1400809dc`
- `0x140087dd8`
- `0x140088060`
- `0x140088240`
- `0x140095cd8`

## pseudocode

```c
__int64 __fastcall SkmiCreatePrivateAllocation(
        unsigned int *a1,
        unsigned __int64 *a2,
        __int64 *a3,
        int a4,
        unsigned int a5,
        unsigned __int64 a6,
        unsigned __int64 a7,
        unsigned int **a8)
{
  unsigned __int64 v8; // r10
  unsigned __int64 v10; // rbp
  unsigned __int64 v13; // rsi
  __int64 result; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rax
  __int64 v18; // rdx
  unsigned int *v19; // rbx
  _QWORD *StackBase; // rcx
  __int64 v21; // rcx
  int v22; // eax
  unsigned int v23; // edi
  __int64 v24; // r9
  _QWORD *v25; // rcx
  __int64 v26; // r8
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // rdx
  __int64 v30; // [rsp+28h] [rbp-40h]
  __int64 v31; // [rsp+70h] [rbp+8h] BYREF
  int v32; // [rsp+88h] [rbp+20h]

  v32 = a4;
  v8 = a1[140] | ((unsigned __int64)(a1[142] & 0xFFF) << 32);
  v10 = a1[141] | ((unsigned __int64)(a1[142] & 0xFFF000) << 20);
  v31 = 0;
  if ( a6 <= v8 << 12 )
  {
    LODWORD(v13) = v8;
  }
  else
  {
    v13 = a6 >> 12;
    if ( a6 >> 12 > v10 )
      return 3221225485LL;
  }
  v15 = 0x10000;
  if ( a7 >= 0x10000 )
    v16 = a7 >> 12;
  else
    v16 = 16;
  v17 = *a2;
  if ( *a2 )
  {
    v18 = *a3;
    v15 = v17;
  }
  else
  {
    v18 = 1;
  }
  result = SkmiCreateLockedVad(v15, v18, 0, (unsigned int)(v17 != 0) + 56, &v31);
  if ( (int)result >= 0 )
  {
    v19 = (unsigned int *)v31;
    *(_QWORD *)(v31 + 48) = ((unsigned __int64)a5 << 50)
                          & 0x7C000000000000LL
                          ^ (*(_QWORD *)(v31 + 48) & 0xFF838FFFFFFFFFFFuLL | 0x200000000000LL);
    StackBase = KeGetPcr()->NtTib.StackBase;
    if ( StackBase )
    {
      v21 = StackBase[18];
      if ( v21 )
        --*(_WORD *)(v21 + xmmword_140167150);
    }
    SkAcquirePushLockExclusive(a1 + 28);
    if ( *a2
      || ((v30 = *a3, (v32 & 0x100000) == 0)
        ? (v22 = SkmiSelectAddressBottomUp((_DWORD)a1, (_DWORD)v19, v13, v10, v16, v30))
        : (v22 = SkmiSelectAddressTopDown((_DWORD)a1, (_DWORD)v19, v13, v10, v16, v30)),
          v23 = v22,
          v22 >= 0) )
    {
      SkmiInsertVad(a1, v19);
      v23 = 0;
      v28 = v19[6] | ((unsigned __int64)(v19[8] & 0xFFF) << 32);
      *a2 = v28 << 12;
      v29 = ((v19[7] | ((unsigned __int64)(v19[8] & 0xFFF000) << 20)) - v28 + 1) << 12;
      *a8 = v19;
      v19 = 0;
      *a3 = v29;
    }
    RtlReleaseSRWLockExclusive(a1 + 28);
    v25 = KeGetPcr()->NtTib.StackBase;
    if ( v25 )
    {
      v26 = v25[18];
      if ( v26 )
      {
        if ( (*(_WORD *)(v26 + xmmword_140167150))++ == 0xFFFF
          && *(_QWORD *)(v26 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v25[17]
          && !*(_WORD *)(v26 + *((_QWORD *)&xmmword_140167150 + 1)) )
        {
          SkiCheckForKernelApcDelivery(v25, xmmword_140167160, v26, v24);
        }
      }
    }
    if ( v19 )
      SkmiUnlockAndDereferenceVad(v19);
    return v23;
  }
  return result;
}

```

## disassembly

```asm
0x140087dd8  mov     [rsp+arg_8], rbx
0x140087ddd  mov     [rsp+arg_18], r9d
0x140087de2  push    rbp
0x140087de3  push    rsi
0x140087de4  push    rdi
0x140087de5  push    r12
0x140087de7  push    r13
0x140087de9  push    r14
0x140087deb  push    r15
0x140087ded  sub     rsp, 30h
0x140087df1  mov     ebp, [rcx+238h]
0x140087df7  xor     r15d, r15d
0x140087dfa  mov     eax, [rcx+230h]
0x140087e00  mov     r10d, ebp
0x140087e03  mov     rsi, [rsp+68h+arg_28]
0x140087e0b  and     r10d, 0FFFh
0x140087e12  and     ebp, 0FFF000h
0x140087e18  shl     r10, 20h
0x140087e1c  or      r10, rax
0x140087e1f  shl     rbp, 14h
0x140087e23  mov     eax, [rcx+234h]
0x140087e29  mov     r13, r8
0x140087e2c  or      rbp, rax
0x140087e2f  mov     [rsp+68h+arg_0], r15
0x140087e34  mov     rax, r10
0x140087e37  mov     r12, rdx
0x140087e3a  shl     rax, 0Ch
0x140087e3e  mov     r14, rcx
0x140087e41  cmp     rsi, rax
0x140087e44  jbe     short loc_140087E59
0x140087e46  shr     rsi, 0Ch
0x140087e4a  cmp     rsi, rbp
0x140087e4d  jbe     short loc_140087E5C
0x140087e4f  mov     eax, 0C000000Dh
0x140087e54  jmp     loc_140087FDC
0x140087e59  mov     rsi, r10
0x140087e5c  mov     rdi, [rsp+68h+arg_30]
0x140087e64  mov     ecx, 10000h
0x140087e69  cmp     rdi, rcx
0x140087e6c  jnb     short loc_140087E75
0x140087e6e  mov     edi, 10h
0x140087e73  jmp     short loc_140087E79
0x140087e75  shr     rdi, 0Ch
0x140087e79  mov     rax, [rdx]
0x140087e7c  test    rax, rax
0x140087e7f  jnz     short loc_140087E86
0x140087e81  lea     edx, [rax+1]
0x140087e84  jmp     short loc_140087E8C
0x140087e86  mov     rdx, [r8]
0x140087e89  mov     rcx, rax
0x140087e8c  neg     rax
0x140087e8f  lea     rax, [rsp+68h+arg_0]
0x140087e94  sbb     r9d, r9d
0x140087e97  mov     [rsp+68h+var_48], rax
0x140087e9c  neg     r9d
0x140087e9f  xor     r8d, r8d
0x140087ea2  add     r9d, 38h ; '8'
0x140087ea6  call    SkmiCreateLockedVad
0x140087eab  test    eax, eax
0x140087ead  js      loc_140087FDC
0x140087eb3  mov     rbx, [rsp+68h+arg_0]
0x140087eb8  mov     rdx, 0FF83AFFFFFFFFFFFh
0x140087ec2  mov     ecx, [rsp+68h+arg_20]
0x140087ec9  shl     rcx, 32h
0x140087ecd  mov     rax, [rbx+30h]
0x140087ed1  and     rax, rdx
0x140087ed4  mov     rdx, 200000000000h
0x140087ede  or      rax, rdx
0x140087ee1  mov     rdx, 7C000000000000h
0x140087eeb  and     rcx, rdx
0x140087eee  xor     rax, rcx
0x140087ef1  mov     [rbx+30h], rax
0x140087ef5  mov     rcx, gs:8
0x140087efe  test    rcx, rcx
0x140087f01  jz      short loc_140087F1B
0x140087f03  mov     rcx, [rcx+90h]
0x140087f0a  test    rcx, rcx
0x140087f0d  jz      short loc_140087F1B
0x140087f0f  mov     rax, qword ptr cs:xmmword_140167150
0x140087f16  dec     word ptr [rcx+rax]
0x140087f1a  nop
0x140087f1b  lea     rcx, [r14+70h]
0x140087f1f  call    SkAcquirePushLockExclusive
0x140087f24  cmp     [r12], r15
0x140087f28  jnz     loc_140087FF2
0x140087f2e  test    [rsp+68h+arg_18], 100000h
0x140087f39  mov     r9, rbp
0x140087f3c  mov     rax, [r13+0]
0x140087f40  mov     r8, rsi
0x140087f43  mov     [rsp+68h+var_40], rax
0x140087f48  mov     rdx, rbx
0x140087f4b  mov     [rsp+68h+var_48], rdi
0x140087f50  mov     rcx, r14
0x140087f53  jz      short loc_140087F5C
0x140087f55  call    SkmiSelectAddressTopDown
0x140087f5a  jmp     short loc_140087F61
0x140087f5c  call    SkmiSelectAddressBottomUp
0x140087f61  xor     esi, esi
0x140087f63  mov     edi, eax
0x140087f65  test    eax, eax
0x140087f67  jns     loc_140087FF4
0x140087f6d  lea     ebp, [rsi+1]
0x140087f70  lea     rcx, [r14+70h]
0x140087f74  call    RtlReleaseSRWLockExclusive
0x140087f79  mov     rcx, gs:8
0x140087f82  test    rcx, rcx
0x140087f85  jz      short loc_140087FCD
0x140087f87  mov     r8, [rcx+90h]
0x140087f8e  test    r8, r8
0x140087f91  jz      short loc_140087FCD
0x140087f93  nop
0x140087f94  mov     rax, qword ptr cs:xmmword_140167150
0x140087f9b  add     [r8+rax], bp
0x140087fa0  jnz     short loc_140087FCD
0x140087fa2  mov     rax, [rcx+88h]
0x140087fa9  nop
0x140087faa  mov     rdx, qword ptr cs:xmmword_140167160
0x140087fb1  add     rax, rdx
0x140087fb4  cmp     [r8+rdx], rax
0x140087fb8  jz      short loc_140087FCD
0x140087fba  mov     rax, qword ptr cs:xmmword_140167150+8
0x140087fc1  cmp     [r8+rax], si
0x140087fc6  jnz     short loc_140087FCD
0x140087fc8  call    SkiCheckForKernelApcDelivery
0x140087fcd  test    rbx, rbx
0x140087fd0  jz      short loc_140087FDA
0x140087fd2  mov     rcx, rbx
0x140087fd5  call    SkmiUnlockAndDereferenceVad
0x140087fda  mov     eax, edi
0x140087fdc  mov     rbx, [rsp+68h+arg_8]
0x140087fe1  add     rsp, 30h
0x140087fe5  pop     r15
0x140087fe7  pop     r14
0x140087fe9  pop     r13
0x140087feb  pop     r12
0x140087fed  pop     rdi
0x140087fee  pop     rsi
0x140087fef  pop     rbp
0x140087ff0  retn
0x140087ff2  xor     esi, esi
0x140087ff4  mov     rdx, rbx
0x140087ff7  mov     rcx, r14
0x140087ffa  call    SkmiInsertVad
0x140087fff  mov     r8d, [rbx+20h]
0x140088003  mov     ebp, 1
0x140088008  mov     eax, [rbx+18h]
0x14008800b  and     r8d, 0FFFh
0x140088012  shl     r8, 20h
0x140088016  mov     edi, esi
0x140088018  or      r8, rax
0x14008801b  mov     rax, r8
0x14008801e  shl     rax, 0Ch
0x140088022  mov     [r12], rax
0x140088026  mov     edx, [rbx+20h]
0x140088029  mov     eax, [rbx+1Ch]
0x14008802c  and     edx, 0FFF000h
0x140088032  shl     rdx, 14h
0x140088036  or      rdx, rax
0x140088039  mov     rax, [rsp+68h+arg_38]
0x140088041  sub     rdx, r8
0x140088044  add     rdx, rbp
0x140088047  shl     rdx, 0Ch
0x14008804b  mov     [rax], rbx
0x14008804e  mov     rbx, rsi
0x140088051  mov     [r13+0], rdx
0x140088055  jmp     loc_140087F70
```
