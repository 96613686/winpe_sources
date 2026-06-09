# UdfCreateSparseReservationBitmap

- ea: `0x140030d3c`
- end: `0x140030f3b`
- name: `UdfCreateSparseReservationBitmap`
- size: `511`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140030fec`
- `0x140039d14`

## callees

- `0x140004340`
- `0x14000ca54`
- `0x14001c080`
- `0x140030d3c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030e6e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030eae`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030e6e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030eae`
- `ntoskrnl!ExInitializeResourceLite` at `0x140030f04`
- `ntoskrnl!ExInitializeResourceLite` at `0x140030f04`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140030dda`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140030dda`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140030e23`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140030e23`

## pseudocode

```c
__int64 __fastcall UdfCreateSparseReservationBitmap(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  bool v4; // bp
  unsigned __int64 v5; // rsi
  unsigned int v6; // ebp
  PVOID PoolWithTag; // rax
  PVOID v8; // rdi
  struct _ERESOURCE *v9; // rax
  struct _ERESOURCE *v10; // rsi
  __int64 result; // rax
  PVOID v12; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  v4 = *(_QWORD *)(v2 + 1640) != (_QWORD)KeGetCurrentThread();
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
  {
    WPP_SF_q(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      83,
      WPP_3702783af02333f5d52357996bb663b1_Traceguids,
      a2);
  }
  v5 = (~(unsigned __int64)(unsigned int)(*(_DWORD *)(v2 + 68) - 1)
      & ((unsigned int)(*(_DWORD *)(v2 + 68) - 1) + *(_QWORD *)(a2 + 32))) >> *(_DWORD *)(v2 + 72);
  if ( (unsigned int)v5 <= *(_DWORD *)(a2 + 296) )
    LODWORD(v5) = *(_DWORD *)(a2 + 296);
  if ( *(_DWORD *)(a2 + 328) > 1u )
  {
    if ( v4 )
    {
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v2 + 1584));
      *(_QWORD *)(v2 + 1640) = KeGetCurrentThread();
    }
    *(_DWORD *)(v2 + 672) += 1 - *(_DWORD *)(a2 + 328);
    *(_DWORD *)(a2 + 328) = 1;
    if ( v4 )
    {
      *(_QWORD *)(v2 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v2 + 1584));
    }
  }
  v6 = ((unsigned int)((((unsigned __int64)(unsigned int)v5 << *(_DWORD *)(v2 + 72)) + 0xFFFF) >> 16) + 0x1FFF) >> 13;
  if ( v6 <= 8 )
    v6 = 8;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, 8 * v6, 0x52666455u);
  v8 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported || !PoolWithTag )
  {
    v12 = PoolWithTag;
    if ( !PoolWithTag )
      return 3221225626LL;
  }
  else
  {
    memset(PoolWithTag, 0, 8 * v6);
    v12 = v8;
  }
  v9 = (struct _ERESOURCE *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x68u, 0x52666455u);
  v10 = v9;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( v9 )
      memset(v9, 0, sizeof(struct _ERESOURCE));
  }
  *(_QWORD *)(a2 + 336) = v10;
  if ( !v10 )
  {
    UdfFreePool(&v12);
    return 3221225626LL;
  }
  ExInitializeResourceLite(v10);
  *(_DWORD *)(a2 + 212) |= 0x2000u;
  result = 0;
  *(_DWORD *)(a2 + 348) = v6;
  *(_QWORD *)(a2 + 352) = v8;
  return result;
}

```

## disassembly

```asm
0x140030d3c  mov     [rsp+arg_8], rbx
0x140030d41  mov     [rsp+arg_10], rbp
0x140030d46  push    rsi
0x140030d47  push    rdi
0x140030d48  push    r15
0x140030d4a  sub     rsp, 20h
0x140030d4e  mov     rdi, [rcx+10h]
0x140030d52  mov     rbx, rdx
0x140030d55  mov     rax, gs:188h
0x140030d5e  cmp     [rdi+668h], rax
0x140030d65  setnz   bpl
0x140030d69  mov     rcx, cs:WPP_GLOBAL_Control
0x140030d70  lea     rax, WPP_GLOBAL_Control
0x140030d77  mov     r15d, 1
0x140030d7d  cmp     rcx, rax
0x140030d80  jz      short loc_140030DA1
0x140030d82  mov     eax, [rcx+2Ch]
0x140030d85  test    r15b, al
0x140030d88  jz      short loc_140030DA1
0x140030d8a  mov     rcx, [rcx+18h]
0x140030d8e  lea     edx, [r15+52h]
0x140030d92  mov     r9, rbx
0x140030d95  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x140030d9c  call    WPP_SF_q
0x140030da1  mov     ecx, [rdi+44h]
0x140030da4  mov     eax, [rbx+128h]
0x140030daa  sub     ecx, r15d
0x140030dad  mov     rsi, [rbx+20h]
0x140030db1  add     rsi, rcx
0x140030db4  not     rcx
0x140030db7  and     rsi, rcx
0x140030dba  mov     ecx, [rdi+48h]
0x140030dbd  shr     rsi, cl
0x140030dc0  cmp     esi, eax
0x140030dc2  cmovbe  esi, eax
0x140030dc5  cmp     [rbx+148h], r15d
0x140030dcc  jbe     short loc_140030E2F
0x140030dce  test    bpl, bpl
0x140030dd1  jz      short loc_140030DF6
0x140030dd3  lea     rcx, [rdi+630h]; FastMutex
0x140030dda  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140030de1  nop     dword ptr [rax+rax+00h]
0x140030de6  mov     rax, gs:188h
0x140030def  mov     [rdi+668h], rax
0x140030df6  mov     eax, r15d
0x140030df9  sub     eax, [rbx+148h]
0x140030dff  add     [rdi+2A0h], eax
0x140030e05  mov     [rbx+148h], r15d
0x140030e0c  test    bpl, bpl
0x140030e0f  jz      short loc_140030E2F
0x140030e11  lea     rcx, [rdi+630h]; FastMutex
0x140030e18  mov     qword ptr [rdi+668h], 0
0x140030e23  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140030e2a  nop     dword ptr [rax+rax+00h]
0x140030e2f  mov     ecx, [rdi+48h]
0x140030e32  mov     eax, 8
0x140030e37  mov     ebp, esi
0x140030e39  mov     r15d, 52666455h
0x140030e3f  shl     rbp, cl
0x140030e42  mov     r8d, r15d; Tag
0x140030e45  add     rbp, 0FFFFh
0x140030e4c  mov     ecx, 401h; PoolType
0x140030e51  shr     rbp, 10h
0x140030e55  add     ebp, 1FFFh
0x140030e5b  shr     ebp, 0Dh
0x140030e5e  cmp     ebp, eax
0x140030e60  cmovbe  ebp, eax
0x140030e63  lea     eax, ds:0[rbp*8]
0x140030e6a  mov     edx, eax; NumberOfBytes
0x140030e6c  mov     esi, eax
0x140030e6e  call    cs:__imp_ExAllocatePoolWithTag
0x140030e75  nop     dword ptr [rax+rax+00h]
0x140030e7a  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140030e81  mov     rdi, rax
0x140030e84  jnz     short loc_140030EF0
0x140030e86  test    rax, rax
0x140030e89  jz      short loc_140030EF0
0x140030e8b  mov     r8d, esi; Size
0x140030e8e  xor     edx, edx; Val
0x140030e90  mov     rcx, rax; void *
0x140030e93  call    memset
0x140030e98  mov     [rsp+38h+arg_0], rdi
0x140030e9d  mov     r8d, r15d; Tag
0x140030ea0  mov     ecx, 600h; PoolType
0x140030ea5  mov     r15d, 68h ; 'h'
0x140030eab  mov     edx, r15d; NumberOfBytes
0x140030eae  call    cs:__imp_ExAllocatePoolWithTag
0x140030eb5  nop     dword ptr [rax+rax+00h]
0x140030eba  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140030ec1  mov     rsi, rax
0x140030ec4  jnz     short loc_140030ED8
0x140030ec6  test    rax, rax
0x140030ec9  jz      short loc_140030ED8
0x140030ecb  mov     r8d, r15d; Size
0x140030ece  xor     edx, edx; Val
0x140030ed0  mov     rcx, rax; void *
0x140030ed3  call    memset
0x140030ed8  mov     [rbx+150h], rsi
0x140030edf  test    rsi, rsi
0x140030ee2  jnz     short loc_140030F01
0x140030ee4  lea     rcx, [rsp+38h+arg_0]
0x140030ee9  call    UdfFreePool
0x140030eee  jmp     short loc_140030EFA
0x140030ef0  mov     [rsp+38h+arg_0], rdi
0x140030ef5  test    rdi, rdi
0x140030ef8  jnz     short loc_140030E9D
0x140030efa  mov     eax, 0C000009Ah
0x140030eff  jmp     short loc_140030F27
0x140030f01  mov     rcx, rsi; Resource
0x140030f04  call    cs:__imp_ExInitializeResourceLite
0x140030f0b  nop     dword ptr [rax+rax+00h]
0x140030f10  bts     dword ptr [rbx+0D4h], 0Dh
0x140030f18  xor     eax, eax
0x140030f1a  mov     [rbx+15Ch], ebp
0x140030f20  mov     [rbx+160h], rdi
0x140030f27  mov     rbx, [rsp+38h+arg_8]
0x140030f2c  mov     rbp, [rsp+38h+arg_10]
0x140030f31  add     rsp, 20h
0x140030f35  pop     r15
0x140030f37  pop     rdi
0x140030f38  pop     rsi
0x140030f39  retn
```
