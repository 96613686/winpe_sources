# SkobCreateHandle

- ea: `0x1400a0df8`
- end: `0x1400a0f9a`
- name: `SkobCreateHandle`
- size: `418`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140014dd0`
- `0x14004444c`
- `0x140047ac8`
- `0x1400500b4`
- `0x14005bd70`
- `0x14005c7e4`
- `0x14005c98c`
- `0x140062a88`
- `0x14006b310`
- `0x14008969c`
- `0x140089b8c`
- `0x14009760c`
- `0x140097804`
- `0x1400a0988`
- `0x1400a1974`
- `0x1400b48c4`

## callees

- `0x140002ef0`
- `0x140002f60`
- `0x1400a0df8`
- `0x1400a1210`
- `0x1400a141c`
- `0x1400a1c88`
- `0x1400f2fc0`

## pseudocode

```c
__int64 __fastcall SkobCreateHandle(__int64 a1, char a2, __int64 a3, __int64 a4)
{
  __int64 v9; // rsi
  char v10; // r15
  __int64 v11; // rbx
  int inserted; // edi
  __int64 v13; // rbx
  _QWORD *StackBase; // rax
  __int64 v15; // rbx
  __int64 v16; // rdx
  char v17; // bp
  __int64 v18; // rcx
  signed __int16 v19; // ax
  signed __int16 v20; // r8
  __int64 *v21; // rax
  unsigned __int16 v22; // ax
  unsigned __int16 v23; // dx
  __int64 v24; // rcx
  __int64 *v25; // [rsp+20h] [rbp-58h] BYREF

  v25 = 0;
  if ( a2 && a3 )
    return 3221225485LL;
  v9 = a1 - 32;
  v10 = 0;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 - 32 + 24)) <= 1 )
    __fastfail(0xEu);
  v11 = (a1 - 112) & -(__int64)(*(_BYTE *)(a1 - 32 + 8) != 0);
  if ( v11 )
  {
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v11 + 16)) <= 0 )
      __fastfail(0xEu);
    if ( !_interlockedbittestandset((volatile signed __int32 *)(v11 + 72), 0) )
    {
      inserted = SkobpFindOrInsertObject(v11, 0, 14);
      if ( inserted < 0 )
      {
        _interlockedbittestandset((volatile signed __int32 *)(v11 + 72), 1u);
LABEL_24:
        SkobpDecrementHandleCount(v9);
        goto LABEL_25;
      }
    }
    v10 = 1;
  }
  if ( a2 )
  {
    v13 = SkobpGlobalHandleTable;
  }
  else
  {
    StackBase = KeGetPcr()->NtTib.StackBase;
    if ( StackBase )
      v15 = StackBase[10];
    else
      v15 = 0;
    v13 = *(_QWORD *)(v15 + 344);
  }
  LOBYTE(v16) = SkobpLockHandleTable(v13);
  v17 = v16;
  inserted = SkobpAllocateHandle(v13, v16, &v25, a4);
  if ( inserted >= 0 )
  {
    v21 = v25;
    v25[1] = a3;
    *v21 = v9;
    _m_prefetchw((const void *)(v13 + 6));
    v22 = *(_WORD *)(v13 + 6);
    do
    {
      if ( v22 == 0x8001 )
LABEL_31:
        __fastfail(0xEu);
      v24 = v22;
      v23 = v22;
      LOWORD(v24) = v22 - 1;
      v22 = _InterlockedCompareExchange16((volatile signed __int16 *)(v13 + 6), v22 - 1, v22);
    }
    while ( v22 != v23 );
    LOBYTE(v24) = v17;
    SkeLowerIrql(v24);
    return 0;
  }
  _m_prefetchw((const void *)(v13 + 6));
  v19 = *(_WORD *)(v13 + 6);
  do
  {
    if ( v19 == -32767 )
      goto LABEL_31;
    v20 = v19;
    v19 = _InterlockedCompareExchange16((volatile signed __int16 *)(v13 + 6), v19 - 1, v19);
  }
  while ( v19 != v20 );
  LOBYTE(v18) = v17;
  SkeLowerIrql(v18);
  if ( v10 )
    goto LABEL_24;
LABEL_25:
  SkobDereferenceObject(a1);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1400a0df8  push    rbx
0x1400a0dfa  push    rbp
0x1400a0dfb  push    rsi
0x1400a0dfc  push    rdi
0x1400a0dfd  push    r12
0x1400a0dff  push    r13
0x1400a0e01  push    r14
0x1400a0e03  push    r15
0x1400a0e05  sub     rsp, 38h
0x1400a0e09  mov     [rsp+78h+var_58], 0
0x1400a0e12  mov     r12, r9
0x1400a0e15  mov     r14, r8
0x1400a0e18  mov     bpl, dl
0x1400a0e1b  mov     r13, rcx
0x1400a0e1e  test    dl, dl
0x1400a0e20  jz      short loc_1400A0E3E
0x1400a0e22  test    r8, r8
0x1400a0e25  jz      short loc_1400A0E3E
0x1400a0e27  mov     eax, 0C000000Dh
0x1400a0e2c  add     rsp, 38h
0x1400a0e30  pop     r15
0x1400a0e32  pop     r14
0x1400a0e34  pop     r13
0x1400a0e36  pop     r12
0x1400a0e38  pop     rdi
0x1400a0e39  pop     rsi
0x1400a0e3a  pop     rbp
0x1400a0e3b  pop     rbx
0x1400a0e3c  retn
0x1400a0e3e  mov     edx, 1
0x1400a0e43  lea     rsi, [rcx-20h]
0x1400a0e47  mov     eax, edx
0x1400a0e49  xor     r15b, r15b
0x1400a0e4c  lock xadd [rsi+18h], rax
0x1400a0e52  add     rax, rdx
0x1400a0e55  lea     r8d, [rdx+0Dh]
0x1400a0e59  cmp     rax, rdx
0x1400a0e5c  jg      short loc_1400A0E63
0x1400a0e5e  mov     ecx, r8d
0x1400a0e61  int     29h; Win8: RtlFailFast(ecx)
0x1400a0e63  mov     al, [rsi+8]
0x1400a0e66  lea     rcx, [rsi-50h]
0x1400a0e6a  neg     al
0x1400a0e6c  sbb     rbx, rbx
0x1400a0e6f  and     rbx, rcx
0x1400a0e72  jz      short loc_1400A0EB5
0x1400a0e74  mov     rax, rdx
0x1400a0e77  lock xadd [rbx+10h], rax
0x1400a0e7d  add     rax, rdx
0x1400a0e80  test    rax, rax
0x1400a0e83  jg      short loc_1400A0E8A
0x1400a0e85  mov     rcx, r8
0x1400a0e88  int     29h; Win8: RtlFailFast(ecx)
0x1400a0e8a  lock bts dword ptr [rbx+48h], 0
0x1400a0e90  jb      short loc_1400A0EB2
0x1400a0e92  xor     edx, edx
0x1400a0e94  mov     rcx, rbx
0x1400a0e97  call    SkobpFindOrInsertObject
0x1400a0e9c  mov     edi, eax
0x1400a0e9e  test    eax, eax
0x1400a0ea0  jns     short loc_1400A0EAD
0x1400a0ea2  lock bts dword ptr [rbx+48h], 1
0x1400a0ea8  jmp     loc_1400A0F41
0x1400a0ead  mov     edx, 1
0x1400a0eb2  mov     r15b, dl
0x1400a0eb5  test    bpl, bpl
0x1400a0eb8  jz      short loc_1400A0EC3
0x1400a0eba  mov     rbx, cs:SkobpGlobalHandleTable
0x1400a0ec1  jmp     short loc_1400A0EE0
0x1400a0ec3  mov     rax, gs:8
0x1400a0ecc  test    rax, rax
0x1400a0ecf  jz      short loc_1400A0ED7
0x1400a0ed1  mov     rbx, [rax+50h]
0x1400a0ed5  jmp     short loc_1400A0ED9
0x1400a0ed7  xor     ebx, ebx
0x1400a0ed9  mov     rbx, [rbx+158h]
0x1400a0ee0  mov     rcx, rbx
0x1400a0ee3  call    SkobpLockHandleTable
0x1400a0ee8  mov     r9, r12
0x1400a0eeb  lea     r8, [rsp+78h+var_58]
0x1400a0ef0  mov     dl, al
0x1400a0ef2  mov     rcx, rbx
0x1400a0ef5  mov     bpl, al
0x1400a0ef8  call    SkobpAllocateHandle
0x1400a0efd  mov     edi, eax
0x1400a0eff  mov     r9d, 0FFFF8001h
0x1400a0f05  mov     r10d, 1
0x1400a0f0b  test    eax, eax
0x1400a0f0d  jns     short loc_1400A0F53
0x1400a0f0f  prefetchw byte ptr [rbx+6]
0x1400a0f13  movzx   eax, word ptr [rbx+6]
0x1400a0f17  cmp     ax, r9w
0x1400a0f1b  jz      short loc_1400A0F93
0x1400a0f1d  movzx   edx, ax
0x1400a0f20  movzx   r8d, ax
0x1400a0f24  sub     dx, r10w
0x1400a0f28  lock cmpxchg [rbx+6], dx
0x1400a0f2e  cmp     ax, r8w
0x1400a0f32  jnz     short loc_1400A0F17
0x1400a0f34  mov     cl, bpl
0x1400a0f37  call    SkeLowerIrql
0x1400a0f3c  test    r15b, r15b
0x1400a0f3f  jz      short loc_1400A0F49
0x1400a0f41  mov     rcx, rsi
0x1400a0f44  call    SkobpDecrementHandleCount
0x1400a0f49  mov     rcx, r13
0x1400a0f4c  call    SkobDereferenceObject
0x1400a0f51  jmp     short loc_1400A0F8C
0x1400a0f53  mov     rax, [rsp+78h+var_58]
0x1400a0f58  mov     [rax+8], r14
0x1400a0f5c  mov     [rax], rsi
0x1400a0f5f  prefetchw byte ptr [rbx+6]
0x1400a0f63  movzx   eax, word ptr [rbx+6]
0x1400a0f67  cmp     ax, r9w
0x1400a0f6b  jz      short loc_1400A0F93
0x1400a0f6d  movzx   ecx, ax
0x1400a0f70  movzx   edx, ax
0x1400a0f73  sub     cx, r10w
0x1400a0f77  lock cmpxchg [rbx+6], cx
0x1400a0f7d  cmp     ax, dx
0x1400a0f80  jnz     short loc_1400A0F67
0x1400a0f82  mov     cl, bpl
0x1400a0f85  call    SkeLowerIrql
0x1400a0f8a  xor     edi, edi
0x1400a0f8c  mov     eax, edi
0x1400a0f8e  jmp     loc_1400A0E2C
0x1400a0f93  mov     ecx, 0Eh
0x1400a0f98  int     29h; Win8: RtlFailFast(ecx)
```
