# SkCreateThreadSystemServiceCallBuffer

- ea: `0x1400b7230`
- end: `0x1400b74e4`
- name: `SkCreateThreadSystemServiceCallBuffer`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x140033b58`

## callees

- `0x140002900`
- `0x14000b084`
- `0x14000f0f0`
- `0x140037e68`
- `0x140095cd8`
- `0x1400b7230`
- `0x1400b811c`
- `0x1400ef620`

## pseudocode

```c
__int64 __fastcall SkCreateThreadSystemServiceCallBuffer(_QWORD *a1)
{
  __int64 v1; // rsi
  volatile signed __int16 *v3; // rsi
  _QWORD *StackBase; // r14
  __int64 v5; // rdx
  volatile signed __int16 *v6; // rbx
  volatile signed __int16 *v7; // rcx
  int v8; // r8d
  unsigned int i; // edi
  volatile signed __int16 **v10; // rax
  int v11; // edx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  bool v15; // zf
  volatile signed __int16 *Pool; // rax
  __int64 SharedUserBuffer; // rax
  __int64 v19; // rcx
  volatile signed __int16 **v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // r14
  unsigned __int16 v26; // bp
  __int64 v27; // rcx
  ULONG_PTR RegionSize; // [rsp+78h] [rbp+10h] BYREF
  PVOID BaseAddress; // [rsp+80h] [rbp+18h] BYREF

  v1 = a1[9];
  BaseAddress = 0;
  v3 = (volatile signed __int16 *)(v1 + 288);
  RegionSize = 0;
  StackBase = KeGetPcr()->NtTib.StackBase;
  v5 = StackBase[18];
  if ( v5 )
    --*(_WORD *)(v5 + *((_QWORD *)&xmmword_140167150 + 1));
  SkAcquirePushLockExclusive(v3 + 12);
  v6 = (volatile signed __int16 *)*((_QWORD *)v3 + 2);
  if ( v6 )
  {
    v7 = (volatile signed __int16 *)*((_QWORD *)v3 + 2);
    v8 = 1;
  }
  else
  {
    v7 = *(volatile signed __int16 **)v3;
    v6 = 0;
    v8 = 0;
    if ( *(volatile signed __int16 **)v3 != v3 )
      v6 = *(volatile signed __int16 **)v3;
  }
  i = -1;
  while ( v6 )
  {
    v10 = *(volatile signed __int16 ***)v6;
    if ( *(volatile signed __int16 **)v6 == v7 )
      goto LABEL_16;
    if ( *((_WORD *)v6 + 12) != 0xFFFF )
    {
      for ( i = 0; i < 0x10; ++i )
      {
        v11 = *((__int16 *)v6 + 12);
        if ( !_bittest(&v11, i) )
          break;
      }
      _InterlockedOr16(v6 + 12, 1 << i);
      if ( !*((_QWORD *)v3 + 2) && *((_WORD *)v6 + 12) != 0xFFFF )
        *((_QWORD *)v3 + 2) = v6;
      break;
    }
    if ( v8 && v10 == (volatile signed __int16 **)v3 )
    {
      v6 = *v10;
      v8 = 0;
    }
    else
    {
      v6 = *(volatile signed __int16 **)v6;
    }
    if ( v6 == v3 )
    {
LABEL_16:
      v6 = 0;
      break;
    }
  }
  RtlReleaseSRWLockExclusive(v3 + 12);
  v14 = StackBase[18];
  if ( v14 )
  {
    v15 = (*(_WORD *)(v14 + *((_QWORD *)&xmmword_140167150 + 1)))++ == 0xFFFF;
    if ( v15 && *(_QWORD *)(v14 + xmmword_140167160) != (_QWORD)xmmword_140167160 + StackBase[17] )
      SkiCheckForKernelApcDelivery(xmmword_140167160, v14, v12, v13);
  }
  if ( !v6 )
  {
    Pool = (volatile signed __int16 *)SkAllocatePool(512, 0x20u);
    v6 = Pool;
    if ( !Pool )
      return 3221225626LL;
    *(_OWORD *)Pool = 0;
    *((_OWORD *)Pool + 1) = 0;
    SharedUserBuffer = SkpAllocateSharedUserBuffer(0x10000, 0);
    *((_QWORD *)v6 + 2) = SharedUserBuffer;
    if ( !SharedUserBuffer )
    {
      SkFreePool(512, v6);
      return 3221225626LL;
    }
    *((_WORD *)v6 + 12) = 1;
    v19 = StackBase[18];
    if ( v19 )
      --*(_WORD *)(v19 + *((_QWORD *)&xmmword_140167150 + 1));
    SkAcquirePushLockExclusive(v3 + 12);
    v20 = (volatile signed __int16 **)*((_QWORD *)v3 + 1);
    if ( *v20 != v3 )
      __fastfail(3u);
    *(_QWORD *)v6 = v3;
    i = 0;
    *((_QWORD *)v6 + 1) = v20;
    *v20 = v6;
    *((_QWORD *)v3 + 1) = v6;
    if ( !*((_QWORD *)v3 + 2) )
      *((_QWORD *)v3 + 2) = v6;
    RtlReleaseSRWLockExclusive(v3 + 12);
    v23 = StackBase[18];
    if ( v23 )
    {
      v15 = (*(_WORD *)(v23 + *((_QWORD *)&xmmword_140167150 + 1)))++ == 0xFFFF;
      if ( v15 && *(_QWORD *)(v23 + xmmword_140167160) != (_QWORD)xmmword_140167160 + StackBase[17] )
        SkiCheckForKernelApcDelivery(xmmword_140167160, v23, v21, v22);
    }
  }
  v24 = *((__int16 *)v6 + 13);
  v25 = i << 12;
  if ( !_bittest(&v24, i) )
  {
    BaseAddress = (PVOID)(v25 + *((_QWORD *)v6 + 2));
    RegionSize = 4096;
    v26 = 1 << i;
    if ( ZwAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x1000u, 4u) < 0 )
    {
      _InterlockedAnd16(v6 + 12, ~v26);
      return 3221225626LL;
    }
    _InterlockedOr16(v6 + 13, v26);
  }
  v27 = v25 + *((_QWORD *)v6 + 2);
  a1[38] = v6;
  a1[3] = v27;
  return 0;
}

```

## disassembly

```asm
0x1400b7230  mov     rax, rsp
0x1400b7233  push    rbx
0x1400b7234  push    rbp
0x1400b7235  push    rsi
0x1400b7236  push    rdi
0x1400b7237  push    r13
0x1400b7239  push    r14
0x1400b723b  push    r15
0x1400b723d  sub     rsp, 30h
0x1400b7241  mov     rsi, [rcx+48h]
0x1400b7245  mov     r13, rcx
0x1400b7248  mov     qword ptr [rax+18h], 0
0x1400b7250  add     rsi, 120h
0x1400b7257  mov     qword ptr [rax+10h], 0
0x1400b725f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400b7263  mov     r14, gs:8
0x1400b726c  mov     rdx, [r14+90h]
0x1400b7273  test    rdx, rdx
0x1400b7276  jz      short loc_1400B7284
0x1400b7278  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400b727f  add     [rdx+rax], cx
0x1400b7283  nop
0x1400b7284  lea     r15, [rsi+18h]
0x1400b7288  mov     rcx, r15
0x1400b728b  call    SkAcquirePushLockExclusive
0x1400b7290  mov     rbx, [rsi+10h]
0x1400b7294  mov     ebp, 1
0x1400b7299  test    rbx, rbx
0x1400b729c  jz      short loc_1400B72A6
0x1400b729e  mov     rcx, rbx
0x1400b72a1  mov     r8d, ebp
0x1400b72a4  jmp     short loc_1400B72B5
0x1400b72a6  mov     rcx, [rsi]
0x1400b72a9  xor     ebx, ebx
0x1400b72ab  xor     r8d, r8d
0x1400b72ae  cmp     rcx, rsi
0x1400b72b1  cmovnz  rbx, rcx
0x1400b72b5  or      edi, 0FFFFFFFFh
0x1400b72b8  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400b72bc  test    rbx, rbx
0x1400b72bf  jz      short loc_1400B72F3
0x1400b72c1  mov     rax, [rbx]
0x1400b72c4  cmp     rax, rcx
0x1400b72c7  jz      short loc_1400B72F1
0x1400b72c9  movsx   edx, word ptr [rbx+18h]
0x1400b72cd  cmp     dx, r9w
0x1400b72d1  jnz     loc_1400B7362
0x1400b72d7  test    r8d, r8d
0x1400b72da  jz      short loc_1400B72E9
0x1400b72dc  cmp     rax, rsi
0x1400b72df  jnz     short loc_1400B72E9
0x1400b72e1  mov     rbx, [rax]
0x1400b72e4  xor     r8d, r8d
0x1400b72e7  jmp     short loc_1400B72EC
0x1400b72e9  mov     rbx, rax
0x1400b72ec  cmp     rbx, rsi
0x1400b72ef  jnz     short loc_1400B72BC
0x1400b72f1  xor     ebx, ebx
0x1400b72f3  mov     rcx, r15
0x1400b72f6  call    RtlReleaseSRWLockExclusive
0x1400b72fb  mov     rdx, [r14+90h]
0x1400b7302  test    rdx, rdx
0x1400b7305  jz      short loc_1400B7332
0x1400b7307  nop
0x1400b7308  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400b730f  add     [rdx+rax], bp
0x1400b7313  jnz     short loc_1400B7332
0x1400b7315  mov     rax, [r14+88h]
0x1400b731c  nop
0x1400b731d  mov     rcx, qword ptr cs:xmmword_140167160
0x1400b7324  add     rax, rcx
0x1400b7327  cmp     [rdx+rcx], rax
0x1400b732b  jz      short loc_1400B7332
0x1400b732d  call    SkiCheckForKernelApcDelivery
0x1400b7332  test    rbx, rbx
0x1400b7335  jnz     loc_1400B7457
0x1400b733b  mov     edi, 200h
0x1400b7340  lea     edx, [rbx+20h]
0x1400b7343  mov     ecx, edi
0x1400b7345  mov     r8d, 46427953h
0x1400b734b  call    SkAllocatePool
0x1400b7350  mov     rbx, rax
0x1400b7353  test    rax, rax
0x1400b7356  jnz     short loc_1400B739B
0x1400b7358  mov     eax, 0C000009Ah
0x1400b735d  jmp     loc_1400B74D4
0x1400b7362  xor     edi, edi
0x1400b7364  bt      edx, edi
0x1400b7367  jnb     short loc_1400B7370
0x1400b7369  add     edi, ebp
0x1400b736b  cmp     edi, 10h
0x1400b736e  jb      short loc_1400B7364
0x1400b7370  mov     eax, ebp
0x1400b7372  mov     ecx, edi
0x1400b7374  shl     ax, cl
0x1400b7377  lock or [rbx+18h], ax
0x1400b737c  cmp     qword ptr [rsi+10h], 0
0x1400b7381  jnz     loc_1400B72F3
0x1400b7387  cmp     [rbx+18h], r9w
0x1400b738c  jz      loc_1400B72F3
0x1400b7392  mov     [rsi+10h], rbx
0x1400b7396  jmp     loc_1400B72F3
0x1400b739b  xorps   xmm0, xmm0
0x1400b739e  xor     edx, edx
0x1400b73a0  movups  xmmword ptr [rax], xmm0
0x1400b73a3  mov     ecx, 10000h
0x1400b73a8  movups  xmmword ptr [rax+10h], xmm0
0x1400b73ac  call    SkpAllocateSharedUserBuffer
0x1400b73b1  mov     [rbx+10h], rax
0x1400b73b5  test    rax, rax
0x1400b73b8  jnz     short loc_1400B73C6
0x1400b73ba  mov     rdx, rbx
0x1400b73bd  mov     ecx, edi
0x1400b73bf  call    SkFreePool
0x1400b73c4  jmp     short loc_1400B7358
0x1400b73c6  mov     [rbx+18h], bp
0x1400b73ca  mov     rcx, [r14+90h]
0x1400b73d1  test    rcx, rcx
0x1400b73d4  jz      short loc_1400B73E6
0x1400b73d6  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400b73dd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400b73e1  add     [rcx+rax], dx
0x1400b73e5  nop
0x1400b73e6  mov     rcx, r15
0x1400b73e9  call    SkAcquirePushLockExclusive
0x1400b73ee  mov     rax, [rsi+8]
0x1400b73f2  cmp     [rax], rsi
0x1400b73f5  jz      short loc_1400B73FE
0x1400b73f7  mov     ecx, 3
0x1400b73fc  int     29h; Win8: RtlFailFast(ecx)
0x1400b73fe  mov     [rbx], rsi
0x1400b7401  xor     edi, edi
0x1400b7403  mov     [rbx+8], rax
0x1400b7407  mov     [rax], rbx
0x1400b740a  mov     [rsi+8], rbx
0x1400b740e  cmp     [rsi+10h], rdi
0x1400b7412  jnz     short loc_1400B7418
0x1400b7414  mov     [rsi+10h], rbx
0x1400b7418  mov     rcx, r15
0x1400b741b  call    RtlReleaseSRWLockExclusive
0x1400b7420  mov     rdx, [r14+90h]
0x1400b7427  test    rdx, rdx
0x1400b742a  jz      short loc_1400B7457
0x1400b742c  nop
0x1400b742d  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400b7434  add     [rdx+rax], bp
0x1400b7438  jnz     short loc_1400B7457
0x1400b743a  mov     rax, [r14+88h]
0x1400b7441  nop
0x1400b7442  mov     rcx, qword ptr cs:xmmword_140167160
0x1400b7449  add     rax, rcx
0x1400b744c  cmp     [rdx+rcx], rax
0x1400b7450  jz      short loc_1400B7457
0x1400b7452  call    SkiCheckForKernelApcDelivery
0x1400b7457  movsx   eax, word ptr [rbx+1Ah]
0x1400b745b  mov     r14d, edi
0x1400b745e  shl     r14d, 0Ch
0x1400b7462  bt      eax, edi
0x1400b7465  jb      short loc_1400B74C0
0x1400b7467  mov     rdx, [rbx+10h]
0x1400b746b  lea     r9, [rsp+68h+RegionSize]; RegionSize
0x1400b7470  add     rdx, r14
0x1400b7473  mov     [rsp+68h+Protect], 4; Protect
0x1400b747b  mov     eax, 1000h
0x1400b7480  mov     [rsp+68h+BaseAddress], rdx
0x1400b7488  mov     ecx, edi
0x1400b748a  mov     [rsp+68h+RegionSize], rax
0x1400b748f  shl     bp, cl
0x1400b7492  lea     rdx, [rsp+68h+BaseAddress]; BaseAddress
0x1400b749a  xor     r8d, r8d; ZeroBits
0x1400b749d  mov     [rsp+68h+AllocationType], eax; AllocationType
0x1400b74a1  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400b74a5  call    ZwAllocateVirtualMemory
0x1400b74aa  test    eax, eax
0x1400b74ac  jns     short loc_1400B74BB
0x1400b74ae  not     bp
0x1400b74b1  lock and [rbx+18h], bp
0x1400b74b6  jmp     loc_1400B7358
0x1400b74bb  lock or [rbx+1Ah], bp
0x1400b74c0  mov     rcx, [rbx+10h]
0x1400b74c4  add     rcx, r14
0x1400b74c7  mov     [r13+130h], rbx
0x1400b74ce  mov     [r13+18h], rcx
0x1400b74d2  xor     eax, eax
0x1400b74d4  add     rsp, 30h
0x1400b74d8  pop     r15
0x1400b74da  pop     r14
0x1400b74dc  pop     r13
0x1400b74de  pop     rdi
0x1400b74df  pop     rsi
0x1400b74e0  pop     rbp
0x1400b74e1  pop     rbx
0x1400b74e2  retn
```
