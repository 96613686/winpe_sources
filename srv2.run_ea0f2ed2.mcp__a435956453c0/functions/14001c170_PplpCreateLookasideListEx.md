# PplpCreateLookasideListEx

- ea: `0x14001c170`
- end: `0x14001c2c9`
- name: `PplpCreateLookasideListEx`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001fbec`

## callees

- `0x14001c170`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x14001c1be`
- `ntoskrnl!ExAllocatePool3` at `0x14001c1be`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001c201`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001c201`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001c23b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001c23b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c27e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c27e`

## pseudocode

```c
_DWORD *__fastcall PplpCreateLookasideListEx(
        int a1,
        ALLOCATE_FUNCTION_EX *a2,
        FREE_FUNCTION_EX *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        SIZE_T Size,
        ULONG Tag,
        __int64 a9,
        ULONG a10)
{
  int v11; // ebp
  _DWORD *Pool3; // rbx
  int i; // esi
  _DWORD *v14; // rdi
  _DWORD *result; // rax
  _QWORD v16[11]; // [rsp+40h] [rbp-58h] BYREF

  v16[1] = 0;
  v16[0] = 1;
  v11 = a1 + 1;
  Pool3 = (_DWORD *)ExAllocatePool3(72, ((unsigned __int64)(unsigned int)(a1 + 1) << 7) + 64, a10, v16, 1);
  if ( !Pool3 )
    return 0;
  for ( i = 0; i < v11; ++i )
  {
    v14 = &Pool3[32 * (__int64)i];
    KeInitializeSpinLock((PKSPIN_LOCK)v14 + 21);
    if ( i )
    {
      *((_BYTE *)v14 + 176) = 0;
      *((_QWORD *)v14 + 20) = Pool3 + 16;
    }
    else
    {
      if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v14 + 16), a2, a3, (POOL_TYPE)512, 0, Size, Tag, 0) < 0 )
      {
        ExFreePoolWithTag(Pool3, a10);
        return 0;
      }
      *((_QWORD *)v14 + 20) = 0;
      *((_BYTE *)v14 + 176) = 1;
    }
  }
  *Pool3 = v11;
  *((_WORD *)Pool3 + 18) = 0;
  *((_QWORD *)Pool3 + 3) = 0;
  result = Pool3;
  Pool3[1] = 0;
  Pool3[2] = Tag;
  Pool3[3] = a10;
  *((_QWORD *)Pool3 + 2) = Size;
  Pool3[8] = 512;
  return result;
}

```

## disassembly

```asm
0x14001c170  mov     r11, rsp
0x14001c173  mov     [r11+10h], rdx
0x14001c177  push    rbx
0x14001c178  push    rbp
0x14001c179  push    rsi
0x14001c17a  push    rdi
0x14001c17b  push    r12
0x14001c17d  push    r13
0x14001c17f  push    r14
0x14001c181  push    r15
0x14001c183  sub     rsp, 58h
0x14001c187  mov     r14d, [rsp+98h+arg_48]
0x14001c18f  lea     r9, [r11-58h]
0x14001c193  mov     eax, 1
0x14001c198  mov     qword ptr [r11-50h], 0
0x14001c1a0  mov     r13, r8
0x14001c1a3  mov     [r11-58h], rax
0x14001c1a7  mov     r8d, r14d
0x14001c1aa  mov     [rsp+98h+Flags], eax
0x14001c1ae  lea     ebp, [rax+rcx]
0x14001c1b1  mov     edx, ebp
0x14001c1b3  lea     ecx, [rax+47h]
0x14001c1b6  shl     rdx, 7
0x14001c1ba  add     rdx, 40h ; '@'
0x14001c1be  call    cs:__imp_ExAllocatePool3
0x14001c1c5  nop     dword ptr [rax+rax+00h]
0x14001c1ca  mov     rbx, rax
0x14001c1cd  test    rax, rax
0x14001c1d0  jz      loc_14001C28A
0x14001c1d6  mov     r15d, [rsp+98h+arg_38]
0x14001c1de  xor     esi, esi
0x14001c1e0  mov     r12, [rsp+98h+arg_30]
0x14001c1e8  cmp     esi, ebp
0x14001c1ea  jge     loc_14001C29E
0x14001c1f0  movsxd  rdi, esi
0x14001c1f3  shl     rdi, 7
0x14001c1f7  add     rdi, rbx
0x14001c1fa  lea     rcx, [rdi+0A8h]; SpinLock
0x14001c201  call    cs:__imp_KeInitializeSpinLock
0x14001c208  nop     dword ptr [rax+rax+00h]
0x14001c20d  test    esi, esi
0x14001c20f  jnz     short loc_14001C25F
0x14001c211  mov     rdx, [rsp+98h+Allocate]; Allocate
0x14001c219  lea     rcx, [rdi+40h]; Lookaside
0x14001c21d  xor     eax, eax
0x14001c21f  mov     r9d, 200h; PoolType
0x14001c225  mov     [rsp+98h+Depth], ax; Depth
0x14001c22a  mov     r8, r13; Free
0x14001c22d  mov     [rsp+98h+Tag], r15d; Tag
0x14001c232  mov     [rsp+98h+Size], r12; Size
0x14001c237  mov     [rsp+98h+Flags], eax; Flags
0x14001c23b  call    cs:__imp_ExInitializeLookasideListEx
0x14001c242  nop     dword ptr [rax+rax+00h]
0x14001c247  test    eax, eax
0x14001c249  js      short loc_14001C278
0x14001c24b  mov     qword ptr [rdi+0A0h], 0
0x14001c256  mov     byte ptr [rdi+0B0h], 1
0x14001c25d  jmp     short loc_14001C271
0x14001c25f  lea     rax, [rbx+40h]
0x14001c263  mov     byte ptr [rdi+0B0h], 0
0x14001c26a  mov     [rdi+0A0h], rax
0x14001c271  inc     esi
0x14001c273  jmp     loc_14001C1E8
0x14001c278  mov     edx, r14d; Tag
0x14001c27b  mov     rcx, rbx; P
0x14001c27e  call    cs:__imp_ExFreePoolWithTag
0x14001c285  nop     dword ptr [rax+rax+00h]
0x14001c28a  xor     eax, eax
0x14001c28c  add     rsp, 58h
0x14001c290  pop     r15
0x14001c292  pop     r14
0x14001c294  pop     r13
0x14001c296  pop     r12
0x14001c298  pop     rdi
0x14001c299  pop     rsi
0x14001c29a  pop     rbp
0x14001c29b  pop     rbx
0x14001c29c  retn
0x14001c29e  xor     eax, eax
0x14001c2a0  mov     [rbx], ebp
0x14001c2a2  mov     [rbx+24h], ax
0x14001c2a6  mov     [rbx+18h], rax
0x14001c2aa  mov     rax, rbx
0x14001c2ad  mov     dword ptr [rbx+4], 0
0x14001c2b4  mov     [rbx+8], r15d
0x14001c2b8  mov     [rbx+0Ch], r14d
0x14001c2bc  mov     [rbx+10h], r12
0x14001c2c0  mov     dword ptr [rbx+20h], 200h
0x14001c2c7  jmp     short loc_14001C28C
```
