# SkmmRemoveLoadedModule

- ea: `0x140037ad4`
- end: `0x140037c59`
- name: `SkmmRemoveLoadedModule`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400b7040`

## callees

- `0x140002900`
- `0x14000b084`
- `0x140037ad4`
- `0x140037e68`
- `0x140037f80`
- `0x140037fac`
- `0x140095cd8`
- `0x1400d994c`

## pseudocode

```c
__int64 __fastcall SkmmRemoveLoadedModule(void *a1)
{
  _QWORD *StackBase; // rdx
  __int64 v3; // rdx
  _UNKNOWN **i; // rbx
  char v5; // al
  __int64 v6; // rcx
  _UNKNOWN **v7; // r8
  _QWORD *v8; // rdx
  __int64 v9; // r9
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  bool v12; // zf
  __int64 result; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  _QWORD *v16; // rcx
  __int64 v17; // rdx

  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
  {
    v3 = StackBase[18];
    if ( v3 )
      --*(_WORD *)(v3 + xmmword_140167150);
  }
  SkAcquirePushLockExclusive(&SkmiNarLock);
  for ( i = (_UNKNOWN **)SkLoadedModuleList; i != &SkLoadedModuleList; i = (_UNKNOWN **)*i )
  {
    if ( i[6] == a1 )
    {
      if ( ((_DWORD)i[13] & 0x200) != 0 )
        RtlRemoveInvertedFunctionTable();
      v5 = SkmmLockLoadedModuleListExclusive();
      v7 = (_UNKNOWN **)*i;
      if ( *((_UNKNOWN ***)*i + 1) != i || (v8 = i[1], (_UNKNOWN **)*v8 != i) )
        __fastfail(3u);
      *v8 = v7;
      LOBYTE(v6) = v5;
      v7[1] = v8;
      SkmmUnlockLoadedModuleListExclusive(v6);
      RtlReleaseSRWLockExclusive(&SkmiNarLock);
      v10 = KeGetPcr()->NtTib.StackBase;
      if ( v10 )
      {
        v11 = v10[18];
        if ( v11 )
        {
          v12 = (*(_WORD *)(v11 + xmmword_140167150))++ == 0xFFFF;
          if ( v12
            && *(_QWORD *)(v11 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v10[17]
            && !*(_WORD *)(v11 + *((_QWORD *)&xmmword_140167150 + 1)) )
          {
            SkiCheckForKernelApcDelivery(v10, v11, xmmword_140167160, v9);
          }
        }
      }
      return SkFreePool(512, i);
    }
  }
  result = RtlReleaseSRWLockExclusive(&SkmiNarLock);
  v16 = KeGetPcr()->NtTib.StackBase;
  if ( v16 )
  {
    v17 = v16[18];
    if ( v17 )
    {
      result = xmmword_140167150;
      v12 = (*(_WORD *)(v17 + xmmword_140167150))++ == 0xFFFF;
      if ( v12 )
      {
        result = xmmword_140167160 + v16[17];
        if ( *(_QWORD *)(v17 + xmmword_140167160) != result )
        {
          result = *((_QWORD *)&xmmword_140167150 + 1);
          if ( !*(_WORD *)(v17 + *((_QWORD *)&xmmword_140167150 + 1)) )
            return SkiCheckForKernelApcDelivery(xmmword_140167160, v17, v14, v15);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140037ad4  mov     [rsp+arg_0], rbx
0x140037ad9  mov     [rsp+arg_10], rsi
0x140037ade  push    rdi
0x140037adf  sub     rsp, 20h
0x140037ae3  mov     rdx, gs:8
0x140037aec  xor     esi, esi
0x140037aee  mov     rdi, rcx
0x140037af1  test    rdx, rdx
0x140037af4  jz      short loc_140037B0E
0x140037af6  mov     rdx, [rdx+90h]
0x140037afd  test    rdx, rdx
0x140037b00  jz      short loc_140037B0E
0x140037b02  mov     rax, qword ptr cs:xmmword_140167150
0x140037b09  dec     word ptr [rdx+rax]
0x140037b0d  nop
0x140037b0e  lea     rcx, SkmiNarLock
0x140037b15  call    SkAcquirePushLockExclusive
0x140037b1a  mov     rbx, cs:SkLoadedModuleList
0x140037b21  lea     rax, SkLoadedModuleList
0x140037b28  cmp     rbx, rax
0x140037b2b  jz      loc_140037BE9
0x140037b31  mov     rcx, [rbx+30h]
0x140037b35  cmp     rcx, rdi
0x140037b38  jz      short loc_140037B3F
0x140037b3a  mov     rbx, [rbx]
0x140037b3d  jmp     short loc_140037B21
0x140037b3f  mov     edi, 200h
0x140037b44  test    [rbx+68h], edi
0x140037b47  jz      short loc_140037B4E
0x140037b49  call    RtlRemoveInvertedFunctionTable
0x140037b4e  call    SkmmLockLoadedModuleListExclusive
0x140037b53  mov     r8, [rbx]
0x140037b56  cmp     [r8+8], rbx
0x140037b5a  jnz     loc_140037BE2
0x140037b60  mov     rdx, [rbx+8]
0x140037b64  cmp     [rdx], rbx
0x140037b67  jnz     short loc_140037BE2
0x140037b69  mov     [rdx], r8
0x140037b6c  mov     cl, al
0x140037b6e  mov     [r8+8], rdx
0x140037b72  call    SkmmUnlockLoadedModuleListExclusive
0x140037b77  lea     rcx, SkmiNarLock
0x140037b7e  call    RtlReleaseSRWLockExclusive
0x140037b83  mov     rcx, gs:8
0x140037b8c  test    rcx, rcx
0x140037b8f  jz      short loc_140037BD6
0x140037b91  mov     rdx, [rcx+90h]
0x140037b98  test    rdx, rdx
0x140037b9b  jz      short loc_140037BD6
0x140037b9d  nop
0x140037b9e  mov     rax, qword ptr cs:xmmword_140167150
0x140037ba5  add     word ptr [rdx+rax], 1
0x140037baa  jnz     short loc_140037BD6
0x140037bac  mov     rax, [rcx+88h]
0x140037bb3  nop
0x140037bb4  mov     r8, qword ptr cs:xmmword_140167160
0x140037bbb  add     rax, r8
0x140037bbe  cmp     [rdx+r8], rax
0x140037bc2  jz      short loc_140037BD6
0x140037bc4  mov     rax, qword ptr cs:xmmword_140167150+8
0x140037bcb  cmp     [rdx+rax], si
0x140037bcf  jnz     short loc_140037BD6
0x140037bd1  call    SkiCheckForKernelApcDelivery
0x140037bd6  mov     rdx, rbx
0x140037bd9  mov     ecx, edi
0x140037bdb  call    SkFreePool
0x140037be0  jmp     short loc_140037C48
0x140037be2  mov     ecx, 3
0x140037be7  int     29h; Win8: RtlFailFast(ecx)
0x140037be9  lea     rcx, SkmiNarLock
0x140037bf0  call    RtlReleaseSRWLockExclusive
0x140037bf5  mov     rcx, gs:8
0x140037bfe  test    rcx, rcx
0x140037c01  jz      short loc_140037C48
0x140037c03  mov     rdx, [rcx+90h]
0x140037c0a  test    rdx, rdx
0x140037c0d  jz      short loc_140037C48
0x140037c0f  nop
0x140037c10  mov     rax, qword ptr cs:xmmword_140167150
0x140037c17  add     word ptr [rdx+rax], 1
0x140037c1c  jnz     short loc_140037C48
0x140037c1e  mov     rax, [rcx+88h]
0x140037c25  nop
0x140037c26  mov     rcx, qword ptr cs:xmmword_140167160
0x140037c2d  add     rax, rcx
0x140037c30  cmp     [rdx+rcx], rax
0x140037c34  jz      short loc_140037C48
0x140037c36  mov     rax, qword ptr cs:xmmword_140167150+8
0x140037c3d  cmp     [rdx+rax], si
0x140037c41  jnz     short loc_140037C48
0x140037c43  call    SkiCheckForKernelApcDelivery
0x140037c48  mov     rbx, [rsp+28h+arg_0]
0x140037c4d  mov     rsi, [rsp+28h+arg_10]
0x140037c52  add     rsp, 20h
0x140037c56  pop     rdi
0x140037c57  retn
```
