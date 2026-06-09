# PplpCreateLookasideListEx

- ea: `0x14000d984`
- end: `0x14000dabf`
- name: `PplpCreateLookasideListEx`
- size: `315`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, SIZE_T, ULONG, int, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000d8c8`

## callees

- `0x14000d984`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x14000d9cc`
- `ntoskrnl!ExAllocatePool3` at `0x14000d9cc`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000da42`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000da42`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da9f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000da0f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000da0f`

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
0x14000d984  push    rbx
0x14000d986  push    rbp
0x14000d987  push    rsi
0x14000d988  push    rdi
0x14000d989  push    r12
0x14000d98b  push    r13
0x14000d98d  push    r14
0x14000d98f  push    r15
0x14000d991  sub     rsp, 58h
0x14000d995  mov     r14d, [rsp+98h+arg_48]
0x14000d99d  lea     r9, [rsp+98h+var_58]
0x14000d9a2  mov     eax, 1
0x14000d9a7  mov     [rsp+98h+var_50], 0
0x14000d9b0  mov     r8d, r14d
0x14000d9b3  mov     [rsp+98h+var_58], rax
0x14000d9b8  mov     [rsp+98h+Flags], eax
0x14000d9bc  lea     edi, [rax+rcx]
0x14000d9bf  mov     edx, edi
0x14000d9c1  lea     ecx, [rax+47h]
0x14000d9c4  shl     rdx, 7
0x14000d9c8  add     rdx, 40h ; '@'
0x14000d9cc  call    cs:__imp_ExAllocatePool3
0x14000d9d3  nop     dword ptr [rax+rax+00h]
0x14000d9d8  mov     rbx, rax
0x14000d9db  test    rax, rax
0x14000d9de  jz      loc_14000DAAB
0x14000d9e4  mov     r12d, [rsp+98h+arg_38]
0x14000d9ec  xor     ebp, ebp
0x14000d9ee  mov     r13, [rsp+98h+arg_30]
0x14000d9f6  test    edi, edi
0x14000d9f8  jle     short loc_14000DA6E
0x14000d9fa  lea     r15, [rax+40h]
0x14000d9fe  mov     eax, ebp
0x14000da00  lea     rcx, [r15+68h]
0x14000da04  shl     rax, 7
0x14000da08  add     rcx, rax; SpinLock
0x14000da0b  lea     rsi, [rax+r15]
0x14000da0f  call    cs:__imp_KeInitializeSpinLock
0x14000da16  nop     dword ptr [rax+rax+00h]
0x14000da1b  test    ebp, ebp
0x14000da1d  jnz     short loc_14000DA60
0x14000da1f  xor     eax, eax
0x14000da21  mov     r9d, 200h; PoolType
0x14000da27  mov     [rsp+98h+Depth], ax; Depth
0x14000da2c  xor     r8d, r8d; Free
0x14000da2f  mov     [rsp+98h+Tag], r12d; Tag
0x14000da34  xor     edx, edx; Allocate
0x14000da36  mov     [rsp+98h+Size], r13; Size
0x14000da3b  mov     rcx, rsi; Lookaside
0x14000da3e  mov     [rsp+98h+Flags], eax; Flags
0x14000da42  call    cs:__imp_ExInitializeLookasideListEx
0x14000da49  nop     dword ptr [rax+rax+00h]
0x14000da4e  test    eax, eax
0x14000da50  js      short loc_14000DA99
0x14000da52  mov     qword ptr [rsi+60h], 0
0x14000da5a  mov     byte ptr [rsi+70h], 1
0x14000da5e  jmp     short loc_14000DA68
0x14000da60  mov     [rsi+60h], r15
0x14000da64  mov     byte ptr [rsi+70h], 0
0x14000da68  inc     ebp
0x14000da6a  cmp     ebp, edi
0x14000da6c  jl      short loc_14000D9FE
0x14000da6e  xor     eax, eax
0x14000da70  mov     [rbx], edi
0x14000da72  mov     [rbx+24h], ax
0x14000da76  mov     [rbx+18h], rax
0x14000da7a  mov     rax, rbx
0x14000da7d  mov     dword ptr [rbx+4], 0
0x14000da84  mov     [rbx+8], r12d
0x14000da88  mov     [rbx+0Ch], r14d
0x14000da8c  mov     [rbx+10h], r13
0x14000da90  mov     dword ptr [rbx+20h], 200h
0x14000da97  jmp     short loc_14000DAAD
0x14000da99  mov     edx, r14d; Tag
0x14000da9c  mov     rcx, rbx; P
0x14000da9f  call    cs:__imp_ExFreePoolWithTag
0x14000daa6  nop     dword ptr [rax+rax+00h]
0x14000daab  xor     eax, eax
0x14000daad  add     rsp, 58h
0x14000dab1  pop     r15
0x14000dab3  pop     r14
0x14000dab5  pop     r13
0x14000dab7  pop     r12
0x14000dab9  pop     rdi
0x14000daba  pop     rsi
0x14000dabb  pop     rbp
0x14000dabc  pop     rbx
0x14000dabd  retn
```
