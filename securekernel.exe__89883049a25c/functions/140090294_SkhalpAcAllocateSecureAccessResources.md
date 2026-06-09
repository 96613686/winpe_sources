# SkhalpAcAllocateSecureAccessResources

- ea: `0x140090294`
- end: `0x1400904eb`
- name: `SkhalpAcAllocateSecureAccessResources`
- size: `599`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter4)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14009011c`

## callees

- `0x14000f0f0`
- `0x1400119c4`
- `0x14003e32c`
- `0x140056f64`
- `0x140090294`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkhalpAcAllocateSecureAccessResources(
        ULONG_PTR BugCheckParameter3,
        ULONG_PTR BugCheckParameter4,
        __int64 a3)
{
  ULONG_PTR v4; // rsi
  __int64 v5; // r9
  unsigned int i; // r14d
  __int64 v7; // rax
  char *Pool; // rax
  char *v9; // rbp
  char v10; // r13
  __int64 result; // rax
  unsigned __int8 *v12; // rdi
  unsigned int j; // r12d
  int v14; // ecx
  __int64 v15; // r15
  __int64 v16; // r13
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rax
  char *v20; // rbx
  __int64 v21; // rax
  unsigned __int8 v22; // al
  char v23; // [rsp+70h] [rbp+8h]

  v4 = BugCheckParameter3;
  v5 = BugCheckParameter4;
  for ( i = 0; v5 > 0; BugCheckParameter3 += v7 )
  {
    v7 = *(unsigned __int16 *)(BugCheckParameter3 + 2);
    ++i;
    v5 -= v7;
  }
  if ( v5 < 0 )
    SkeBugCheckEx(0xA5u, 0x1000Bu, 0x56454453u, v4, 4u);
  Pool = (char *)SkAllocatePool(512, 32LL * i);
  v9 = Pool;
  if ( !Pool )
    SkeBugCheckEx(0xA3u, 1u, 0xFFFFFFFFC000009AuLL, 32LL * i, BugCheckParameter4);
  v23 = 0;
  v10 = 0;
  result = (__int64)memset_0(Pool, 0, 32LL * i);
  v12 = (unsigned __int8 *)v4;
  for ( j = 0; j < i; ++j )
  {
    v14 = *v12;
    v15 = 32LL * j;
    *(_DWORD *)&v9[v15] = v14;
    if ( v14 )
    {
      if ( v14 == 1 )
      {
        v16 = *((_QWORD *)v12 + 2);
        v17 = *((_QWORD *)v12 + 1);
        if ( (((unsigned int)v17 | (unsigned int)v16) & 0xFFF) != 0 )
          goto LABEL_25;
        v18 = SkmmProtectIoSpace(*((_QWORD *)v12 + 1), *((_QWORD *)v12 + 2), 0);
        if ( v18 < 0 )
        {
          if ( v18 != -1072431079 )
            SkeBugCheckEx(0x121u, v18, v18, 0, 0);
LABEL_25:
          SkeBugCheckEx(0xA5u, 0x1000Bu, 0x56454453u, v4, 7u);
        }
        *(_QWORD *)&v9[v15 + 16] = v16;
        v10 = v23;
        *(_QWORD *)&v9[v15 + 8] = v17;
      }
    }
    else
    {
      if ( v10 )
        SkeBugCheckEx(0xA5u, 0x1000Bu, 0x56454453u, v4, 5u);
      v19 = *((unsigned __int16 *)v12 + 2);
      if ( !(_WORD)v19 || !*((_WORD *)v12 + 3) )
        SkeBugCheckEx(0xA5u, 0x1000Bu, 0x56454453u, v4, 6u);
      v20 = &v9[v15];
      strncpy_s(&v9[v15 + 8], 9u, (const char *)&v12[v19], *((unsigned __int16 *)v12 + 3));
      v21 = *((unsigned __int16 *)v12 + 4);
      if ( (_WORD)v21 )
        strncpy_s(v20 + 17, 9u, (const char *)&v12[v21], *((unsigned __int16 *)v12 + 5));
      v22 = v12[14];
      v20[26] = v22;
      if ( v22 )
        *((_WORD *)v20 + 14) = *((_WORD *)v12 + 6);
      v10 = 1;
      v23 = 1;
    }
    result = *((unsigned __int16 *)v12 + 1);
    v12 += result;
  }
  *(_QWORD *)(a3 + 8) = v9;
  *(_DWORD *)(a3 + 16) = i;
  return result;
}

```

## disassembly

```asm
0x140090294  mov     [rsp+arg_8], rbx
0x140090299  mov     [rsp+arg_10], r8
0x14009029e  push    rbp
0x14009029f  push    rsi
0x1400902a0  push    rdi
0x1400902a1  push    r12
0x1400902a3  push    r13
0x1400902a5  push    r14
0x1400902a7  push    r15
0x1400902a9  sub     rsp, 30h
0x1400902ad  xor     r15d, r15d
0x1400902b0  mov     rdi, rdx
0x1400902b3  mov     rsi, rcx
0x1400902b6  mov     r9, rdx
0x1400902b9  mov     r14d, r15d
0x1400902bc  test    rdx, rdx
0x1400902bf  jle     short loc_1400902D3
0x1400902c1  movzx   eax, word ptr [rcx+2]
0x1400902c5  inc     r14d
0x1400902c8  sub     r9, rax
0x1400902cb  add     rcx, rax
0x1400902ce  test    r9, r9
0x1400902d1  jg      short loc_1400902C1
0x1400902d3  test    r9, r9
0x1400902d6  jns     short loc_1400902FA
0x1400902d8  mov     r9, rsi; BugCheckParameter3
0x1400902db  mov     [rsp+68h+BugCheckParameter4], 4; BugCheckParameter4
0x1400902e4  mov     edx, 1000Bh; BugCheckParameter1
0x1400902e9  mov     ecx, 0A5h; BugCheckCode
0x1400902ee  mov     r8d, 56454453h; BugCheckParameter2
0x1400902f4  call    SkeBugCheckEx
0x1400902fa  mov     ebx, r14d
0x1400902fd  mov     r8d, 74784544h
0x140090303  shl     rbx, 5
0x140090307  mov     ecx, 200h
0x14009030c  mov     rdx, rbx
0x14009030f  call    SkAllocatePool
0x140090314  mov     rbp, rax
0x140090317  test    rax, rax
0x14009031a  jnz     short loc_140090339
0x14009031c  mov     r9, rbx; BugCheckParameter3
0x14009031f  mov     [rsp+68h+BugCheckParameter4], rdi; BugCheckParameter4
0x140090324  lea     edx, [rax+1]; BugCheckParameter1
0x140090327  mov     ecx, 0A3h; BugCheckCode
0x14009032c  mov     r8, 0FFFFFFFFC000009Ah; BugCheckParameter2
0x140090333  call    SkeBugCheckEx
0x140090339  mov     r8, rbx; Size
0x14009033c  mov     [rsp+68h+arg_0], r15b
0x140090341  xor     edx, edx; Val
0x140090343  mov     rcx, rbp; void *
0x140090346  mov     r13b, r15b
0x140090349  call    memset_0
0x14009034e  mov     rdi, rsi
0x140090351  mov     r12d, r15d
0x140090354  cmp     r12d, r14d
0x140090357  jnb     loc_1400904C5
0x14009035d  movzx   ecx, byte ptr [rdi]
0x140090360  xor     r8d, r8d
0x140090363  mov     r15d, r12d
0x140090366  shl     r15, 5
0x14009036a  mov     [r15+rbp], ecx
0x14009036e  test    ecx, ecx
0x140090370  jz      short loc_1400903BA
0x140090372  cmp     ecx, 1
0x140090375  jnz     loc_140090430
0x14009037b  mov     r13, [rdi+10h]
0x14009037f  mov     rbx, [rdi+8]
0x140090383  mov     eax, r13d
0x140090386  or      eax, ebx
0x140090388  test    eax, 0FFFh
0x14009038d  jnz     loc_14009045F
0x140090393  mov     rdx, r13
0x140090396  mov     rcx, rbx
0x140090399  call    SkmmProtectIoSpace
0x14009039e  xor     r8d, r8d
0x1400903a1  test    eax, eax
0x1400903a3  js      loc_14009043F
0x1400903a9  mov     [r15+rbp+10h], r13
0x1400903ae  mov     r13b, [rsp+68h+arg_0]
0x1400903b3  mov     [r15+rbp+8], rbx
0x1400903b8  jmp     short loc_140090430
0x1400903ba  test    r13b, r13b
0x1400903bd  jnz     loc_1400904A3
0x1400903c3  movzx   eax, word ptr [rdi+4]
0x1400903c7  test    ax, ax
0x1400903ca  jz      loc_140090481
0x1400903d0  movzx   ecx, word ptr [rdi+6]
0x1400903d4  test    cx, cx
0x1400903d7  jz      loc_140090481
0x1400903dd  mov     r9d, ecx; MaxCount
0x1400903e0  lea     rbx, [r15+rbp]
0x1400903e4  lea     rcx, [rbx+8]; char *
0x1400903e8  mov     edx, 9; SizeInBytes
0x1400903ed  lea     r8, [rdi+rax]; Src
0x1400903f1  call    strncpy_s
0x1400903f6  movzx   eax, word ptr [rdi+8]
0x1400903fa  test    ax, ax
0x1400903fd  jz      short loc_140090416
0x1400903ff  movzx   r9d, word ptr [rdi+0Ah]; MaxCount
0x140090404  lea     r8, [rdi+rax]; Src
0x140090408  lea     rcx, [rbx+11h]; char *
0x14009040c  mov     edx, 9; SizeInBytes
0x140090411  call    strncpy_s
0x140090416  mov     al, [rdi+0Eh]
0x140090419  mov     [rbx+1Ah], al
0x14009041c  test    al, al
0x14009041e  jz      short loc_140090428
0x140090420  movzx   eax, word ptr [rdi+0Ch]
0x140090424  mov     [rbx+1Ch], ax
0x140090428  mov     r13b, 1
0x14009042b  mov     [rsp+68h+arg_0], r13b
0x140090430  movzx   eax, word ptr [rdi+2]
0x140090434  add     rdi, rax
0x140090437  inc     r12d
0x14009043a  jmp     loc_140090354
0x14009043f  cmp     eax, 0C0140019h
0x140090444  jz      short loc_14009045F
0x140090446  movsxd  rdx, eax; BugCheckParameter1
0x140090449  xor     r9d, r9d; BugCheckParameter3
0x14009044c  mov     [rsp+68h+BugCheckParameter4], r8; BugCheckParameter4
0x140090451  mov     ecx, 121h; BugCheckCode
0x140090456  mov     r8, rdx; BugCheckParameter2
0x140090459  call    SkeBugCheckEx
0x14009045f  mov     r9, rsi; BugCheckParameter3
0x140090462  mov     [rsp+68h+BugCheckParameter4], 7; BugCheckParameter4
0x14009046b  mov     edx, 1000Bh; BugCheckParameter1
0x140090470  mov     ecx, 0A5h; BugCheckCode
0x140090475  mov     r8d, 56454453h; BugCheckParameter2
0x14009047b  call    SkeBugCheckEx
0x140090481  mov     r9, rsi; BugCheckParameter3
0x140090484  mov     [rsp+68h+BugCheckParameter4], 6; BugCheckParameter4
0x14009048d  mov     edx, 1000Bh; BugCheckParameter1
0x140090492  mov     ecx, 0A5h; BugCheckCode
0x140090497  mov     r8d, 56454453h; BugCheckParameter2
0x14009049d  call    SkeBugCheckEx
0x1400904a3  mov     r9, rsi; BugCheckParameter3
0x1400904a6  mov     [rsp+68h+BugCheckParameter4], 5; BugCheckParameter4
0x1400904af  mov     edx, 1000Bh; BugCheckParameter1
0x1400904b4  mov     ecx, 0A5h; BugCheckCode
0x1400904b9  mov     r8d, 56454453h; BugCheckParameter2
0x1400904bf  call    SkeBugCheckEx
0x1400904c5  mov     r15, [rsp+68h+arg_10]
0x1400904cd  mov     rbx, [rsp+68h+arg_8]
0x1400904d2  mov     [r15+8], rbp
0x1400904d6  mov     [r15+10h], r14d
0x1400904da  add     rsp, 30h
0x1400904de  pop     r15
0x1400904e0  pop     r14
0x1400904e2  pop     r13
0x1400904e4  pop     r12
0x1400904e6  pop     rdi
0x1400904e7  pop     rsi
0x1400904e8  pop     rbp
0x1400904e9  retn
```
