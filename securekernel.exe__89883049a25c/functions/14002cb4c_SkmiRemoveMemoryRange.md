# SkmiRemoveMemoryRange

- ea: `0x14002cb4c`
- end: `0x14002cd25`
- name: `SkmiRemoveMemoryRange`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14004d104`

## callees

- `0x1400010f0`
- `0x1400024b0`
- `0x140002e40`
- `0x140012ea4`
- `0x14002cb4c`
- `0x14002cd2c`
- `0x140037e68`

## pseudocode

```c
__int64 __fastcall SkmiRemoveMemoryRange(unsigned __int64 a1, unsigned __int64 a2, _QWORD *a3)
{
  __int64 v3; // r14
  __int64 v7; // rdi
  _QWORD *v8; // rbx
  int v9; // r15d
  int v10; // eax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r12
  char v13; // al
  _QWORD *v14; // rbx
  __int64 v15; // r8
  _QWORD *v16; // rax
  __int64 v17; // rdx
  char v18; // bl
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rax
  __int64 result; // rax
  __int64 v22; // [rsp+20h] [rbp-78h] BYREF
  __int128 v23; // [rsp+28h] [rbp-70h]
  unsigned __int64 v24; // [rsp+38h] [rbp-60h]
  unsigned __int64 v25; // [rsp+40h] [rbp-58h]
  char v26; // [rsp+B8h] [rbp+20h]

  v3 = SkmiDynamicMemorySupport;
  v22 = 0;
  v23 = 0;
  if ( !SkmiDynamicMemorySupport )
    return 3221225626LL;
  if ( !*(_BYTE *)SkmiDynamicMemorySupport )
    return 3221225626LL;
  v7 = *(_QWORD *)(SkmiDynamicMemorySupport + 8);
  if ( !v7 || *(_DWORD *)(SkmiDynamicMemorySupport + 24) < 0x28u )
    return 3221225626LL;
  v8 = (_QWORD *)SkmiMemoryRangeTree;
  v9 = 0;
  v24 = a1;
  v25 = a2;
  while ( v8 )
  {
    v10 = SkmiCompareMemoryRangeNodes(&v22, v8);
    if ( v10 >= 0 )
    {
      if ( v10 <= 0 )
        break;
      v8 = (_QWORD *)v8[1];
    }
    else
    {
      v8 = (_QWORD *)*v8;
    }
  }
  v11 = v8[3];
  v12 = a1 + a2;
  if ( v11 >= a1 || v8[4] + v11 <= v12 )
  {
    v7 = (__int64)v8;
    v18 = SkAcquireSpinLockExclusive(&SkmiMemoryRangeSpinLock);
    goto LABEL_22;
  }
  *(_QWORD *)(v3 + 8) = 0;
  *(_QWORD *)(v7 + 24) = a1;
  *(_QWORD *)(v7 + 32) = v8[4] + v8[3] - a1;
  v8[4] = a1 - v8[3];
  v13 = SkAcquireSpinLockExclusive(&SkmiMemoryRangeSpinLock);
  v14 = (_QWORD *)SkmiMemoryRangeTree;
  LOBYTE(v15) = 0;
  v26 = v13;
  if ( !SkmiMemoryRangeTree )
    goto LABEL_20;
  while ( (int)SkmiCompareMemoryRangeNodes(v7, v14) >= 0 )
  {
    v16 = (_QWORD *)v14[1];
    if ( !v16 )
    {
      LOBYTE(v15) = 1;
      goto LABEL_20;
    }
LABEL_18:
    v14 = v16;
  }
  v16 = (_QWORD *)*v14;
  if ( *v14 )
    goto LABEL_18;
  LOBYTE(v15) = 0;
LABEL_20:
  RtlAvlInsertNodeEx(&SkmiMemoryRangeTree, v14, v15, v7);
  v18 = v26;
LABEL_22:
  v19 = *(_QWORD *)(v7 + 24);
  if ( v19 >= a1 )
  {
    v20 = *(_QWORD *)(v7 + 32);
    if ( v20 <= a2 )
    {
      RtlAvlRemoveNode((unsigned __int64 *)&SkmiMemoryRangeTree, v7);
      v9 = 1;
    }
    else
    {
      *(_QWORD *)(v7 + 24) = v12;
      *(_QWORD *)(v7 + 32) = v20 - a2;
    }
  }
  else
  {
    *(_QWORD *)(v7 + 32) = a1 - v19;
  }
  LOBYTE(v17) = v18;
  SkReleaseSpinLockExclusive(&SkmiMemoryRangeSpinLock, v17);
  if ( a3 )
    *a3 = 0;
  *(_BYTE *)v3 = 0;
  result = 0;
  if ( v9 )
  {
    SkFreePool(512, v7);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002cb4c  mov     rax, rsp
0x14002cb4f  push    rbx
0x14002cb50  push    rbp
0x14002cb51  push    rsi
0x14002cb52  push    rdi
0x14002cb53  push    r12
0x14002cb55  push    r13
0x14002cb57  push    r14
0x14002cb59  push    r15
0x14002cb5b  sub     rsp, 58h
0x14002cb5f  mov     r14, cs:SkmiDynamicMemorySupport
0x14002cb66  xorps   xmm0, xmm0
0x14002cb69  mov     qword ptr [rax-78h], 0
0x14002cb71  mov     r13, r8
0x14002cb74  mov     rbp, rdx
0x14002cb77  mov     rsi, rcx
0x14002cb7a  movdqu  xmmword ptr [rax-70h], xmm0
0x14002cb7f  test    r14, r14
0x14002cb82  jz      loc_14002CD0E
0x14002cb88  cmp     byte ptr [r14], 0
0x14002cb8c  jz      loc_14002CD0E
0x14002cb92  mov     rdi, [r14+8]
0x14002cb96  test    rdi, rdi
0x14002cb99  jz      loc_14002CD0E
0x14002cb9f  cmp     dword ptr [r14+18h], 28h ; '('
0x14002cba4  jb      loc_14002CD0E
0x14002cbaa  mov     rbx, cs:SkmiMemoryRangeTree
0x14002cbb1  xor     r15d, r15d
0x14002cbb4  mov     [rax-60h], rcx
0x14002cbb8  mov     [rax-58h], rdx
0x14002cbbc  jmp     short loc_14002CBDA
0x14002cbbe  mov     rdx, rbx
0x14002cbc1  lea     rcx, [rsp+98h+var_78]
0x14002cbc6  call    SkmiCompareMemoryRangeNodes
0x14002cbcb  test    eax, eax
0x14002cbcd  jns     short loc_14002CBD4
0x14002cbcf  mov     rbx, [rbx]
0x14002cbd2  jmp     short loc_14002CBDA
0x14002cbd4  jle     short loc_14002CBDF
0x14002cbd6  mov     rbx, [rbx+8]
0x14002cbda  test    rbx, rbx
0x14002cbdd  jnz     short loc_14002CBBE
0x14002cbdf  mov     rcx, [rbx+18h]
0x14002cbe3  lea     r12, [rsi+rbp]
0x14002cbe7  cmp     rcx, rsi
0x14002cbea  jnb     loc_14002CC89
0x14002cbf0  add     rcx, [rbx+20h]
0x14002cbf4  cmp     rcx, r12
0x14002cbf7  jbe     loc_14002CC89
0x14002cbfd  mov     [r14+8], r15
0x14002cc01  lea     rcx, SkmiMemoryRangeSpinLock
0x14002cc08  mov     [rdi+18h], rsi
0x14002cc0c  mov     rax, [rbx+18h]
0x14002cc10  sub     rax, rsi
0x14002cc13  add     rax, [rbx+20h]
0x14002cc17  mov     [rdi+20h], rax
0x14002cc1b  mov     rax, rsi
0x14002cc1e  sub     rax, [rbx+18h]
0x14002cc22  mov     [rbx+20h], rax
0x14002cc26  call    SkAcquireSpinLockExclusive
0x14002cc2b  mov     rbx, cs:SkmiMemoryRangeTree
0x14002cc32  xor     r8b, r8b
0x14002cc35  mov     [rsp+98h+arg_18], al
0x14002cc3c  test    rbx, rbx
0x14002cc3f  jz      short loc_14002CC6E
0x14002cc41  mov     rdx, rbx
0x14002cc44  mov     rcx, rdi
0x14002cc47  call    SkmiCompareMemoryRangeNodes
0x14002cc4c  test    eax, eax
0x14002cc4e  js      short loc_14002CC5E
0x14002cc50  mov     rax, [rbx+8]
0x14002cc54  test    rax, rax
0x14002cc57  jnz     short loc_14002CC66
0x14002cc59  mov     r8b, 1
0x14002cc5c  jmp     short loc_14002CC6E
0x14002cc5e  mov     rax, [rbx]
0x14002cc61  test    rax, rax
0x14002cc64  jz      short loc_14002CC6B
0x14002cc66  mov     rbx, rax
0x14002cc69  jmp     short loc_14002CC41
0x14002cc6b  xor     r8b, r8b
0x14002cc6e  mov     r9, rdi
0x14002cc71  lea     rcx, SkmiMemoryRangeTree
0x14002cc78  mov     rdx, rbx
0x14002cc7b  call    RtlAvlInsertNodeEx
0x14002cc80  mov     bl, [rsp+98h+arg_18]
0x14002cc87  jmp     short loc_14002CC9A
0x14002cc89  lea     rcx, SkmiMemoryRangeSpinLock
0x14002cc90  mov     rdi, rbx
0x14002cc93  call    SkAcquireSpinLockExclusive
0x14002cc98  mov     bl, al
0x14002cc9a  mov     rax, [rdi+18h]
0x14002cc9e  cmp     rax, rsi
0x14002cca1  jnb     short loc_14002CCAC
0x14002cca3  sub     rsi, rax
0x14002cca6  mov     [rdi+20h], rsi
0x14002ccaa  jmp     short loc_14002CCD7
0x14002ccac  mov     rax, [rdi+20h]
0x14002ccb0  cmp     rax, rbp
0x14002ccb3  jbe     short loc_14002CCC2
0x14002ccb5  sub     rax, rbp
0x14002ccb8  mov     [rdi+18h], r12
0x14002ccbc  mov     [rdi+20h], rax
0x14002ccc0  jmp     short loc_14002CCD7
0x14002ccc2  mov     rdx, rdi
0x14002ccc5  lea     rcx, SkmiMemoryRangeTree
0x14002cccc  call    RtlAvlRemoveNode
0x14002ccd1  mov     r15d, 1
0x14002ccd7  mov     dl, bl
0x14002ccd9  lea     rcx, SkmiMemoryRangeSpinLock
0x14002cce0  call    SkReleaseSpinLockExclusive
0x14002cce5  test    r13, r13
0x14002cce8  jz      short loc_14002CCF2
0x14002ccea  mov     qword ptr [r13+0], 0
0x14002ccf2  mov     byte ptr [r14], 0
0x14002ccf6  xor     eax, eax
0x14002ccf8  test    r15d, r15d
0x14002ccfb  jz      short loc_14002CD13
0x14002ccfd  mov     rdx, rdi
0x14002cd00  mov     ecx, 200h
0x14002cd05  call    SkFreePool
0x14002cd0a  xor     eax, eax
0x14002cd0c  jmp     short loc_14002CD13
0x14002cd0e  mov     eax, 0C000009Ah
0x14002cd13  add     rsp, 58h
0x14002cd17  pop     r15
0x14002cd19  pop     r14
0x14002cd1b  pop     r13
0x14002cd1d  pop     r12
0x14002cd1f  pop     rdi
0x14002cd20  pop     rsi
0x14002cd21  pop     rbp
0x14002cd22  pop     rbx
0x14002cd23  retn
```
