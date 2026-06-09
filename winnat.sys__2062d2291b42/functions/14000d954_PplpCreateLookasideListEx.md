# PplpCreateLookasideListEx

- ea: `0x14000d954`
- end: `0x14000da8f`
- name: `PplpCreateLookasideListEx`
- size: `315`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, SIZE_T, ULONG, int, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000d898`

## callees

- `0x14000d954`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x14000d99c`
- `ntoskrnl!ExAllocatePool3` at `0x14000d99c`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000da12`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000da12`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da6f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000d9df`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000d9df`

## pseudocode

```c
_DWORD *__fastcall PplpCreateLookasideListEx(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        SIZE_T Size,
        ULONG Tag,
        int a9,
        ULONG a10)
{
  int v10; // edi
  __int64 Pool3; // rax
  _DWORD *v12; // rbx
  int v13; // ebp
  __int64 v14; // r15
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rsi
  _DWORD *result; // rax
  _QWORD v18[11]; // [rsp+40h] [rbp-58h] BYREF

  v18[1] = 0;
  v18[0] = 1;
  v10 = a1 + 1;
  Pool3 = ExAllocatePool3(72, ((unsigned __int64)(unsigned int)(a1 + 1) << 7) + 64, a10, v18, 1);
  v12 = (_DWORD *)Pool3;
  if ( !Pool3 )
    return 0;
  v13 = 0;
  if ( v10 > 0 )
  {
    v14 = Pool3 + 64;
    do
    {
      v15 = (unsigned __int64)(unsigned int)v13 << 7;
      v16 = v15 + v14;
      KeInitializeSpinLock((PKSPIN_LOCK)(v15 + v14 + 104));
      if ( v13 )
      {
        *(_QWORD *)(v16 + 96) = v14;
        *(_BYTE *)(v16 + 112) = 0;
      }
      else
      {
        if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)v16, 0, 0, (POOL_TYPE)512, 0, Size, Tag, 0) < 0 )
        {
          ExFreePoolWithTag(v12, a10);
          return 0;
        }
        *(_QWORD *)(v16 + 96) = 0;
        *(_BYTE *)(v16 + 112) = 1;
      }
      ++v13;
    }
    while ( v13 < v10 );
  }
  *v12 = v10;
  *((_WORD *)v12 + 18) = 0;
  *((_QWORD *)v12 + 3) = 0;
  result = v12;
  v12[1] = 0;
  v12[2] = Tag;
  v12[3] = a10;
  *((_QWORD *)v12 + 2) = Size;
  v12[8] = 512;
  return result;
}

```

## disassembly

```asm
0x14000d954  push    rbx
0x14000d956  push    rbp
0x14000d957  push    rsi
0x14000d958  push    rdi
0x14000d959  push    r12
0x14000d95b  push    r13
0x14000d95d  push    r14
0x14000d95f  push    r15
0x14000d961  sub     rsp, 58h
0x14000d965  mov     r14d, [rsp+98h+arg_48]
0x14000d96d  lea     r9, [rsp+98h+var_58]
0x14000d972  mov     eax, 1
0x14000d977  mov     [rsp+98h+var_50], 0
0x14000d980  mov     r8d, r14d
0x14000d983  mov     [rsp+98h+var_58], rax
0x14000d988  mov     [rsp+98h+Flags], eax
0x14000d98c  lea     edi, [rax+rcx]
0x14000d98f  mov     edx, edi
0x14000d991  lea     ecx, [rax+47h]
0x14000d994  shl     rdx, 7
0x14000d998  add     rdx, 40h ; '@'
0x14000d99c  call    cs:__imp_ExAllocatePool3
0x14000d9a3  nop     dword ptr [rax+rax+00h]
0x14000d9a8  mov     rbx, rax
0x14000d9ab  test    rax, rax
0x14000d9ae  jz      loc_14000DA7B
0x14000d9b4  mov     r12d, [rsp+98h+arg_38]
0x14000d9bc  xor     ebp, ebp
0x14000d9be  mov     r13, [rsp+98h+arg_30]
0x14000d9c6  test    edi, edi
0x14000d9c8  jle     short loc_14000DA3E
0x14000d9ca  lea     r15, [rax+40h]
0x14000d9ce  mov     eax, ebp
0x14000d9d0  lea     rcx, [r15+68h]
0x14000d9d4  shl     rax, 7
0x14000d9d8  add     rcx, rax; SpinLock
0x14000d9db  lea     rsi, [rax+r15]
0x14000d9df  call    cs:__imp_KeInitializeSpinLock
0x14000d9e6  nop     dword ptr [rax+rax+00h]
0x14000d9eb  test    ebp, ebp
0x14000d9ed  jnz     short loc_14000DA30
0x14000d9ef  xor     eax, eax
0x14000d9f1  mov     r9d, 200h; PoolType
0x14000d9f7  mov     [rsp+98h+Depth], ax; Depth
0x14000d9fc  xor     r8d, r8d; Free
0x14000d9ff  mov     [rsp+98h+Tag], r12d; Tag
0x14000da04  xor     edx, edx; Allocate
0x14000da06  mov     [rsp+98h+Size], r13; Size
0x14000da0b  mov     rcx, rsi; Lookaside
0x14000da0e  mov     [rsp+98h+Flags], eax; Flags
0x14000da12  call    cs:__imp_ExInitializeLookasideListEx
0x14000da19  nop     dword ptr [rax+rax+00h]
0x14000da1e  test    eax, eax
0x14000da20  js      short loc_14000DA69
0x14000da22  mov     qword ptr [rsi+60h], 0
0x14000da2a  mov     byte ptr [rsi+70h], 1
0x14000da2e  jmp     short loc_14000DA38
0x14000da30  mov     [rsi+60h], r15
0x14000da34  mov     byte ptr [rsi+70h], 0
0x14000da38  inc     ebp
0x14000da3a  cmp     ebp, edi
0x14000da3c  jl      short loc_14000D9CE
0x14000da3e  xor     eax, eax
0x14000da40  mov     [rbx], edi
0x14000da42  mov     [rbx+24h], ax
0x14000da46  mov     [rbx+18h], rax
0x14000da4a  mov     rax, rbx
0x14000da4d  mov     dword ptr [rbx+4], 0
0x14000da54  mov     [rbx+8], r12d
0x14000da58  mov     [rbx+0Ch], r14d
0x14000da5c  mov     [rbx+10h], r13
0x14000da60  mov     dword ptr [rbx+20h], 200h
0x14000da67  jmp     short loc_14000DA7D
0x14000da69  mov     edx, r14d; Tag
0x14000da6c  mov     rcx, rbx; P
0x14000da6f  call    cs:__imp_ExFreePoolWithTag
0x14000da76  nop     dword ptr [rax+rax+00h]
0x14000da7b  xor     eax, eax
0x14000da7d  add     rsp, 58h
0x14000da81  pop     r15
0x14000da83  pop     r14
0x14000da85  pop     r13
0x14000da87  pop     r12
0x14000da89  pop     rdi
0x14000da8a  pop     rsi
0x14000da8b  pop     rbp
0x14000da8c  pop     rbx
0x14000da8d  retn
```
