# SkobDeleteReservedHandle

- ea: `0x140037e84`
- end: `0x140037f79`
- name: `SkobDeleteReservedHandle`
- size: `245`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002c5ec`
- `0x140036ea8`
- `0x140037c60`
- `0x14005c1e0`
- `0x14005e710`
- `0x1400ad0a4`
- `0x1400ad5c4`

## callees

- `0x140002f60`
- `0x140011830`
- `0x140033abc`
- `0x140037e84`
- `0x1400a180c`
- `0x1400f2fc0`

## pseudocode

```c
__int64 __fastcall SkobDeleteReservedHandle(unsigned __int64 a1)
{
  __int64 v1; // rsi
  __int64 HandleTable; // rbx
  char v3; // di
  __int64 v4; // rax
  volatile signed __int64 *v5; // r10
  __int64 v6; // r11
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  int v9; // eax
  __int16 v10; // dx
  __int64 v11; // rcx
  unsigned __int64 *v13; // [rsp+30h] [rbp+8h] BYREF

  v13 = 0;
  v1 = (a1 >> 2) & 0xAFFFFFFF;
  HandleTable = SkobpLocateHandleTable(a1, 0, 0);
  v3 = SkobpLockHandleTable(HandleTable);
  v4 = SkobpLocateHandleEntry(HandleTable, (unsigned int)(v1 - 1), &v13);
  v5 = (volatile signed __int64 *)v13;
  v6 = v4;
  if ( v13 )
  {
    _m_prefetchw(v13);
    v7 = *v13;
    do
    {
      if ( (v7 & 0x7FFF000000000000LL) == 0 )
LABEL_9:
        __fastfail(0xEu);
      v8 = v7;
      v7 = _InterlockedCompareExchange64(
             v5,
             ((HIWORD(v7) - 1) << 48) ^ (v7 ^ ((HIWORD(v7) - 1) << 48)) & 0x8000FFFFFFFFFFFFuLL,
             v7);
    }
    while ( v7 != v8 );
  }
  SkobpInsertFreeHandle(HandleTable, (unsigned int)(v1 - 1), v6);
  _m_prefetchw((const void *)(HandleTable + 6));
  v9 = *(unsigned __int16 *)(HandleTable + 6);
  do
  {
    if ( (_WORD)v9 == 0x8001 )
      goto LABEL_9;
    v10 = v9;
    v11 = (unsigned int)(v9 - 1);
    LOWORD(v9) = _InterlockedCompareExchange16((volatile signed __int16 *)(HandleTable + 6), v9 - 1, v9);
  }
  while ( (_WORD)v9 != v10 );
  LOBYTE(v11) = v3;
  return SkeLowerIrql(v11);
}

```

## disassembly

```asm
0x140037e84  mov     [rsp+arg_8], rbx
0x140037e89  mov     [rsp+arg_10], rsi
0x140037e8e  push    rdi
0x140037e8f  sub     rsp, 20h
0x140037e93  xor     r8d, r8d
0x140037e96  mov     [rsp+28h+arg_0], 0
0x140037e9f  xor     edx, edx
0x140037ea1  mov     rsi, rcx
0x140037ea4  call    SkobpLocateHandleTable
0x140037ea9  shr     rsi, 2
0x140037ead  mov     rcx, rax
0x140037eb0  and     esi, 0AFFFFFFFh
0x140037eb6  mov     rbx, rax
0x140037eb9  call    SkobpLockHandleTable
0x140037ebe  lea     r8, [rsp+28h+arg_0]
0x140037ec3  mov     rcx, rbx
0x140037ec6  lea     edx, [rsi-1]
0x140037ec9  mov     dil, al
0x140037ecc  call    SkobpLocateHandleEntry
0x140037ed1  mov     r10, [rsp+28h+arg_0]
0x140037ed6  mov     r11, rax
0x140037ed9  test    r10, r10
0x140037edc  jz      short loc_140037F28
0x140037ede  prefetchw byte ptr [r10]
0x140037ee2  mov     rax, [r10]
0x140037ee5  mov     r8, rax
0x140037ee8  shr     r8, 30h
0x140037eec  mov     rdx, r8
0x140037eef  and     edx, 7FFFh
0x140037ef5  lea     rcx, [rdx-1]
0x140037ef9  cmp     rcx, rdx
0x140037efc  ja      short loc_140037F72
0x140037efe  dec     r8
0x140037f01  mov     rdx, 8000FFFFFFFFFFFFh
0x140037f0b  shl     r8, 30h
0x140037f0f  mov     rcx, rax
0x140037f12  mov     r9, r8
0x140037f15  xor     r9, rax
0x140037f18  and     r9, rdx
0x140037f1b  xor     r9, r8
0x140037f1e  lock cmpxchg [r10], r9
0x140037f23  cmp     rax, rcx
0x140037f26  jnz     short loc_140037EE5
0x140037f28  mov     r8, r11
0x140037f2b  lea     edx, [rsi-1]
0x140037f2e  mov     rcx, rbx
0x140037f31  call    SkobpInsertFreeHandle
0x140037f36  prefetchw byte ptr [rbx+6]
0x140037f3a  movzx   eax, word ptr [rbx+6]
0x140037f3e  mov     ecx, 0FFFF8001h
0x140037f43  cmp     ax, cx
0x140037f46  jz      short loc_140037F72
0x140037f48  movzx   edx, ax
0x140037f4b  lea     ecx, [rax-1]
0x140037f4e  lock cmpxchg [rbx+6], cx
0x140037f54  cmp     ax, dx
0x140037f57  jnz     short loc_140037F3E
0x140037f59  mov     cl, dil
0x140037f5c  call    SkeLowerIrql
0x140037f61  mov     rbx, [rsp+28h+arg_8]
0x140037f66  mov     rsi, [rsp+28h+arg_10]
0x140037f6b  add     rsp, 20h
0x140037f6f  pop     rdi
0x140037f70  retn
0x140037f72  mov     ecx, 0Eh
0x140037f77  int     29h; Win8: RtlFailFast(ecx)
```
