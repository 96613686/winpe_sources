# SkmiFreePhysicalPage

- ea: `0x140024724`
- end: `0x140024a16`
- name: `SkmiFreePhysicalPage`
- size: `754`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `40`
- callee_count: `12`
- tags: ``

## callers

- `0x1400017f4`
- `0x140021f24`
- `0x140022654`
- `0x14002286c`
- `0x140022a48`
- `0x140022db8`
- `0x14002341c`
- `0x1400241cc`
- `0x140024a1c`
- `0x140024d88`
- `0x140025694`
- `0x140026240`
- `0x14002eabc`
- `0x14002f42c`
- `0x14002fe88`
- `0x140030a5c`
- `0x140038588`
- `0x140038fd8`
- `0x140045e4c`
- `0x140047f4c`
- `0x14004d96c`
- `0x14005662c`
- `0x140058630`
- `0x140059dcc`
- `0x14005b200`
- `0x14005b814`
- `0x14005d184`
- `0x14005d374`
- `0x14005d674`
- `0x140068d04`
- `0x140069254`
- `0x14006f118`
- `0x140071704`
- `0x140074c10`
- `0x14007543c`
- `0x140079008`
- `0x1400801c0`
- `0x14008662c`
- `0x140086968`
- `0x1400fae7c`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140003780`
- `0x140008ec4`
- `0x1400119c4`
- `0x140024724`
- `0x14002b534`
- `0x140051d48`
- `0x140055918`
- `0x140081290`
- `0x1400bb844`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiFreePhysicalPage(__int64 *a1, ULONG_PTR a2, int a3)
{
  __int64 *v3; // rdi
  unsigned __int64 v5; // rbx
  BOOL v6; // ebp
  char v7; // r15
  _DWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r15
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rsi
  unsigned __int64 v15; // r14
  __int64 PteTrace; // rax
  __int64 v17; // r13
  PVOID *v18; // rsi
  PVOID StackBase; // rcx
  __int64 v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 result; // rax
  __int64 v25; // rdx
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+70h] [rbp+8h] BYREF
  int v28; // [rsp+80h] [rbp+18h]

  v28 = a3;
  v3 = SkmiSystemPartition;
  if ( a1 )
    v3 = a1;
  if ( a2 > 0xFFFFFFFFFFLL )
    __fastfail(0x3Fu);
  v5 = *(_QWORD *)(8 * a2 - 0x180000000000LL);
  if ( (v5 & 0xFFFFFFFFFFFLL) != 0 )
    SkeBugCheckEx(0x1Au, 0x56534Du, 0xB120u, a2, *(_QWORD *)(8 * a2 - 0x180000000000LL) & 0xFFFFFFFFFFFLL);
  if ( (SkmiFlags & 8) != 0 )
  {
    LODWORD(v5) = 0;
  }
  else if ( (v5 & 0x20000000000000LL) != 0 )
  {
    LODWORD(v5) = 10;
  }
  else
  {
    LODWORD(v5) = 2 * ((v5 >> 50) & 7);
  }
  v6 = 0;
  LOBYTE(v28) = SkAcquireSpinLockExclusive(v3 + 18);
  v7 = v28;
  if ( (_DWORD)v5 == 10 )
    v6 = SkmiSchedulePagesToFree(v3) != 0;
  v8 = (_DWORD *)v3[(unsigned int)v5 + 6];
  v9 = (unsigned int)SkmiAllocationSizeByAccess[(unsigned __int64)(unsigned int)v5 >> 1];
  if ( v8 && (*v8 < (unsigned int)v9 || (v5 = (unsigned int)(v5 + 1), (v8 = (_DWORD *)v3[v5 + 6]) != 0)) )
  {
    *(_QWORD *)(8 * a2 - 0x180000000000LL) |= 0x1000000000000uLL;
    *(_QWORD *)&v8[2 * (*v8)++ + 12] = a2;
    if ( *v8 >= (unsigned int)v9 && (v5 & 1) != 0 )
    {
      if ( *v8 >= 0x1FAu )
      {
        SkmiEmptyPageBundle(v3, (unsigned int)v5);
        LOBYTE(v25) = v7;
        return SkReleaseSpinLockExclusive(v3 + 18, v25);
      }
      if ( (unsigned int)SkmiSchedulePagesToFree(v3) )
        v6 = 1;
    }
  }
  else
  {
    SkmiProtectSinglePage(a2);
    v10 = v3[5];
    v11 = (unsigned int)v5;
    v12 = v10 + 8LL * (unsigned int)v5;
    v13 = *(_QWORD *)v12;
    if ( *(_QWORD *)v12 )
    {
      v12 = v10 + 8 * ((unsigned int)v11 ^ 1LL);
      v13 = *(_QWORD *)v12;
    }
    v14 = 16 * (a2 & 0xFFFFFFFFFFLL);
    v15 = ((v14 | word_140156D90 & 1) << 8) | 0x8000000000000063uLL;
    PteTrace = SkmiGetPteTrace(0, v12, 0, (((unsigned int)v14 | word_140156D90 & 1) << 8) | 0x63, v13);
    v17 = PteTrace;
    if ( PteTrace )
    {
      v18 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        StackBase = KeGetPcr()->NtTib.StackBase;
        if ( StackBase )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v18, &BackTraceHash) )
          {
            *(_QWORD *)(v17 + 40) = retaddr;
            *v18 = (PVOID)SkmiGetInstructionPointer(v20, v9);
          }
        }
      }
    }
    if ( (unsigned __int64)v12 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v12 < 0xFFFFF6FB7DBED800uLL )
    {
      v21 = KeGetPcr()->NtTib.StackBase;
      if ( v21 )
        v22 = v21[10];
      else
        v22 = 0;
      v9 = *(_QWORD *)(v22 + 232);
      if ( v9 )
        *(_QWORD *)(v9 + 8 * ((v12 >> 3) & 0x1FF)) = v15;
    }
    *(_QWORD *)v12 = v15;
    v23 = v12 << 25 >> 16;
    v3[v11 + 6] = v23;
    v7 = v28;
    *(_DWORD *)v23 = 0;
  }
  LOBYTE(v9) = v7;
  result = SkReleaseSpinLockExclusive(v3 + 18, v9);
  if ( v6 )
    return SkQueueWorkItem(&SkmiPagesToFreeWorkItem);
  return result;
}

```

## disassembly

```asm
0x140024724  mov     [rsp+arg_8], rbx
0x140024729  mov     [rsp+arg_10], r8d
0x14002472e  push    rbp
0x14002472f  push    rsi
0x140024730  push    rdi
0x140024731  push    r12
0x140024733  push    r13
0x140024735  push    r14
0x140024737  push    r15
0x140024739  sub     rsp, 30h
0x14002473d  xor     r13d, r13d
0x140024740  lea     rdi, SkmiSystemPartition
0x140024747  test    rcx, rcx
0x14002474a  mov     rsi, rdx
0x14002474d  cmovnz  rdi, rcx
0x140024751  mov     rcx, 0FFFFEFFFFFFFFFFFh
0x14002475b  mov     rdx, 0FFFFE80000000000h
0x140024765  mov     rax, rdx
0x140024768  sub     rcx, rax
0x14002476b  sar     rcx, 3
0x14002476f  cmp     rsi, rcx
0x140024772  jbe     short loc_14002477A
0x140024774  lea     ecx, [r13+3Fh]
0x140024778  int     29h; Win8: RtlFailFast(ecx)
0x14002477a  mov     r14, rdx
0x14002477d  mov     rbx, [r14+rsi*8]
0x140024781  mov     rcx, 0FFFFFFFFFFFh
0x14002478b  mov     rax, rbx
0x14002478e  and     rax, rcx
0x140024791  jz      short loc_1400247B1
0x140024793  mov     r9, rsi; BugCheckParameter3
0x140024796  mov     [rsp+68h+BugCheckParameter4], rax; BugCheckParameter4
0x14002479b  mov     edx, 56534Dh; BugCheckParameter1
0x1400247a0  mov     ecx, 1Ah; BugCheckCode
0x1400247a5  mov     r8d, 0B120h; BugCheckParameter2
0x1400247ab  call    SkeBugCheckEx
0x1400247b1  mov     eax, cs:SkmiFlags
0x1400247b7  test    al, 8
0x1400247b9  jz      short loc_1400247C0
0x1400247bb  mov     ebx, r13d
0x1400247be  jmp     short loc_1400247D7
0x1400247c0  bt      rbx, 35h ; '5'
0x1400247c5  jnb     short loc_1400247CE
0x1400247c7  mov     ebx, 0Ah
0x1400247cc  jmp     short loc_1400247D7
0x1400247ce  shr     rbx, 32h
0x1400247d2  and     ebx, 7
0x1400247d5  add     ebx, ebx
0x1400247d7  lea     r12, [rdi+90h]
0x1400247de  mov     ebp, r13d
0x1400247e1  mov     rcx, r12
0x1400247e4  call    SkAcquireSpinLockExclusive
0x1400247e9  mov     byte ptr [rsp+68h+arg_10], al
0x1400247f0  mov     r15b, al
0x1400247f3  mov     r8d, 1
0x1400247f9  cmp     ebx, 0Ah
0x1400247fc  jnz     short loc_140024810
0x1400247fe  mov     rcx, rdi
0x140024801  call    SkmiSchedulePagesToFree
0x140024806  test    eax, eax
0x140024808  lea     r8d, [rbx-9]
0x14002480c  cmovnz  ebp, r8d
0x140024810  mov     eax, ebx
0x140024812  lea     rdx, SkmiAllocationSizeByAccess
0x140024819  mov     rcx, [rdi+rax*8+30h]
0x14002481e  shr     rax, 1
0x140024821  mov     edx, [rdx+rax*4]
0x140024824  test    rcx, rcx
0x140024827  jz      short loc_140024842
0x140024829  cmp     [rcx], edx
0x14002482b  jb      loc_1400249C5
0x140024831  add     ebx, r8d
0x140024834  mov     rcx, [rdi+rbx*8+30h]
0x140024839  test    rcx, rcx
0x14002483c  jnz     loc_1400249C5
0x140024842  xor     edx, edx
0x140024844  mov     rcx, rsi; BugCheckParameter3
0x140024847  call    SkmiProtectSinglePage
0x14002484c  mov     rcx, [rdi+28h]
0x140024850  mov     r15d, ebx
0x140024853  lea     rbx, [rcx+r15*8]
0x140024857  mov     rax, [rbx]
0x14002485a  test    rax, rax
0x14002485d  jz      short loc_14002486D
0x14002485f  mov     eax, r15d
0x140024862  xor     rax, 1
0x140024866  lea     rbx, [rcx+rax*8]
0x14002486a  mov     rax, [rbx]
0x14002486d  movzx   r14d, byte ptr cs:word_140156D90
0x140024875  mov     rcx, 0FFFFFFFFFFh
0x14002487f  and     rsi, rcx
0x140024882  mov     [rsp+68h+BugCheckParameter4], rax
0x140024887  and     r14d, 1
0x14002488b  shl     rsi, 4
0x14002488f  or      r14, rsi
0x140024892  mov     rcx, 8000000000000063h
0x14002489c  shl     r14, 8
0x1400248a0  xor     r8d, r8d
0x1400248a3  or      r14, rcx
0x1400248a6  mov     rdx, rbx
0x1400248a9  mov     r9, r14
0x1400248ac  xor     ecx, ecx
0x1400248ae  call    SkmiGetPteTrace
0x1400248b3  mov     r13, rax
0x1400248b6  test    rax, rax
0x1400248b9  jz      short loc_14002490F
0x1400248bb  xor     edx, edx; Val
0x1400248bd  lea     rsi, [rax+20h]
0x1400248c1  mov     rcx, rsi; void *
0x1400248c4  lea     r8d, [rdx+40h]; Size
0x1400248c8  call    memset_0
0x1400248cd  test    cs:SkmiFlags, 400000h
0x1400248d7  jz      short loc_14002490F
0x1400248d9  mov     rcx, gs:8; FramesToSkip
0x1400248e2  test    rcx, rcx
0x1400248e5  jz      short loc_14002490F
0x1400248e7  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x1400248ec  mov     r8, rsi; BackTrace
0x1400248ef  mov     edx, 8; FramesToCapture
0x1400248f4  call    RtlCaptureStackBackTrace
0x1400248f9  test    ax, ax
0x1400248fc  jnz     short loc_14002490F
0x1400248fe  mov     rax, [rsp+68h]
0x140024903  mov     [r13+28h], rax
0x140024907  call    SkmiGetInstructionPointer
0x14002490c  mov     [rsi], rax
0x14002490f  mov     rax, 0FFFFF6FB7DBED000h
0x140024919  cmp     rbx, rax
0x14002491c  jb      short loc_140024965
0x14002491e  mov     rax, 0FFFFF6FB7DBED800h
0x140024928  xor     r13d, r13d
0x14002492b  cmp     rbx, rax
0x14002492e  jnb     short loc_140024968
0x140024930  mov     rax, gs:8
0x140024939  test    rax, rax
0x14002493c  jz      short loc_140024944
0x14002493e  mov     rcx, [rax+50h]
0x140024942  jmp     short loc_140024947
0x140024944  mov     rcx, r13
0x140024947  mov     rdx, [rcx+0E8h]
0x14002494e  test    rdx, rdx
0x140024951  jz      short loc_140024968
0x140024953  mov     rax, rbx
0x140024956  sar     rax, 3
0x14002495a  and     eax, 1FFh
0x14002495f  mov     [rdx+rax*8], r14
0x140024963  jmp     short loc_140024968
0x140024965  xor     r13d, r13d
0x140024968  mov     [rbx], r14
0x14002496b  shl     rbx, 19h
0x14002496f  mov     rax, 0FFFFF68000000000h
0x140024979  shl     rax, 19h
0x14002497d  sub     rbx, rax
0x140024980  sar     rbx, 10h
0x140024984  mov     [rdi+r15*8+30h], rbx
0x140024989  mov     r15b, byte ptr [rsp+68h+arg_10]
0x140024991  mov     [rbx], r13d
0x140024994  mov     dl, r15b
0x140024997  mov     rcx, r12
0x14002499a  call    SkReleaseSpinLockExclusive
0x14002499f  test    ebp, ebp
0x1400249a1  jz      short loc_1400249AF
0x1400249a3  lea     rcx, SkmiPagesToFreeWorkItem
0x1400249aa  call    SkQueueWorkItem
0x1400249af  mov     rbx, [rsp+68h+arg_8]
0x1400249b4  add     rsp, 30h
0x1400249b8  pop     r15
0x1400249ba  pop     r14
0x1400249bc  pop     r13
0x1400249be  pop     r12
0x1400249c0  pop     rdi
0x1400249c1  pop     rsi
0x1400249c2  pop     rbp
0x1400249c3  retn
0x1400249c5  mov     rax, 1000000000000h
0x1400249cf  or      [r14+rsi*8], rax
0x1400249d3  mov     eax, [rcx]
0x1400249d5  mov     [rcx+rax*8+30h], rsi
0x1400249da  add     [rcx], r8d
0x1400249dd  mov     eax, [rcx]
0x1400249df  cmp     eax, edx
0x1400249e1  jb      short loc_140024994
0x1400249e3  test    r8b, bl
0x1400249e6  jz      short loc_140024994
0x1400249e8  mov     rcx, rdi
0x1400249eb  cmp     eax, 1FAh
0x1400249f0  jnb     short loc_140024A02
0x1400249f2  call    SkmiSchedulePagesToFree
0x1400249f7  test    eax, eax
0x1400249f9  jz      short loc_140024994
0x1400249fb  mov     ebp, 1
0x140024a00  jmp     short loc_140024994
0x140024a02  mov     edx, ebx
0x140024a04  call    SkmiEmptyPageBundle
0x140024a09  mov     dl, r15b
0x140024a0c  mov     rcx, r12
0x140024a0f  call    SkReleaseSpinLockExclusive
0x140024a14  jmp     short loc_1400249AF
```
