# PplpCreateLookasideListEx

- ea: `0x14001b8dc`
- end: `0x14001ba33`
- name: `PplpCreateLookasideListEx`
- size: `343`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, SIZE_T, ULONG, int, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001b808`

## callees

- `0x14001b8dc`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001b9af`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001b9af`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001b971`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001b971`
- `ntoskrnl!ExAllocatePool3` at `0x14001b92e`
- `ntoskrnl!ExAllocatePool3` at `0x14001b92e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ba0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ba0c`

## pseudocode

```c
_DWORD *__fastcall PplpCreateLookasideListEx(
        int a1,
        ALLOCATE_FUNCTION_EX *a2,
        FREE_FUNCTION_EX *a3,
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
  _QWORD v18[9]; // [rsp+40h] [rbp-48h] BYREF

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
        if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)v16, a2, a3, (POOL_TYPE)512, 0, Size, Tag, 0) < 0 )
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
0x14001b8dc  mov     r11, rsp
0x14001b8df  mov     [r11+8], rbx
0x14001b8e3  mov     [r11+18h], r8
0x14001b8e7  mov     [r11+10h], rdx
0x14001b8eb  push    rbp
0x14001b8ec  push    rsi
0x14001b8ed  push    rdi
0x14001b8ee  push    r12
0x14001b8f0  push    r13
0x14001b8f2  push    r14
0x14001b8f4  push    r15
0x14001b8f6  sub     rsp, 50h
0x14001b8fa  mov     r14d, [rsp+88h+arg_48]
0x14001b902  lea     r9, [r11-48h]
0x14001b906  mov     eax, 1
0x14001b90b  mov     qword ptr [r11-40h], 0
0x14001b913  mov     r8d, r14d
0x14001b916  mov     [r11-48h], rax
0x14001b91a  mov     [rsp+88h+Flags], eax
0x14001b91e  lea     edi, [rax+rcx]
0x14001b921  mov     edx, edi
0x14001b923  lea     ecx, [rax+47h]
0x14001b926  shl     rdx, 7
0x14001b92a  add     rdx, 40h ; '@'
0x14001b92e  call    cs:__imp_ExAllocatePool3
0x14001b935  nop     dword ptr [rax+rax+00h]
0x14001b93a  mov     rbx, rax
0x14001b93d  test    rax, rax
0x14001b940  jz      loc_14001BA18
0x14001b946  mov     r12d, [rsp+88h+arg_38]
0x14001b94e  xor     ebp, ebp
0x14001b950  mov     r13, [rsp+88h+arg_30]
0x14001b958  test    edi, edi
0x14001b95a  jle     short loc_14001B9DB
0x14001b95c  lea     r15, [rax+40h]
0x14001b960  mov     eax, ebp
0x14001b962  lea     rcx, [r15+68h]
0x14001b966  shl     rax, 7
0x14001b96a  add     rcx, rax; SpinLock
0x14001b96d  lea     rsi, [rax+r15]
0x14001b971  call    cs:__imp_KeInitializeSpinLock
0x14001b978  nop     dword ptr [rax+rax+00h]
0x14001b97d  test    ebp, ebp
0x14001b97f  jnz     short loc_14001B9CD
0x14001b981  mov     r8, [rsp+88h+Free]; Free
0x14001b989  xor     eax, eax
0x14001b98b  mov     rdx, [rsp+88h+Allocate]; Allocate
0x14001b993  mov     r9d, 200h; PoolType
0x14001b999  mov     [rsp+88h+Depth], ax; Depth
0x14001b99e  mov     rcx, rsi; Lookaside
0x14001b9a1  mov     [rsp+88h+Tag], r12d; Tag
0x14001b9a6  mov     [rsp+88h+Size], r13; Size
0x14001b9ab  mov     [rsp+88h+Flags], eax; Flags
0x14001b9af  call    cs:__imp_ExInitializeLookasideListEx
0x14001b9b6  nop     dword ptr [rax+rax+00h]
0x14001b9bb  test    eax, eax
0x14001b9bd  js      short loc_14001BA06
0x14001b9bf  mov     qword ptr [rsi+60h], 0
0x14001b9c7  mov     byte ptr [rsi+70h], 1
0x14001b9cb  jmp     short loc_14001B9D5
0x14001b9cd  mov     [rsi+60h], r15
0x14001b9d1  mov     byte ptr [rsi+70h], 0
0x14001b9d5  inc     ebp
0x14001b9d7  cmp     ebp, edi
0x14001b9d9  jl      short loc_14001B960
0x14001b9db  xor     eax, eax
0x14001b9dd  mov     [rbx], edi
0x14001b9df  mov     [rbx+24h], ax
0x14001b9e3  mov     [rbx+18h], rax
0x14001b9e7  mov     rax, rbx
0x14001b9ea  mov     dword ptr [rbx+4], 0
0x14001b9f1  mov     [rbx+8], r12d
0x14001b9f5  mov     [rbx+0Ch], r14d
0x14001b9f9  mov     [rbx+10h], r13
0x14001b9fd  mov     dword ptr [rbx+20h], 200h
0x14001ba04  jmp     short loc_14001BA1A
0x14001ba06  mov     edx, r14d; Tag
0x14001ba09  mov     rcx, rbx; P
0x14001ba0c  call    cs:__imp_ExFreePoolWithTag
0x14001ba13  nop     dword ptr [rax+rax+00h]
0x14001ba18  xor     eax, eax
0x14001ba1a  mov     rbx, [rsp+88h+arg_0]
0x14001ba22  add     rsp, 50h
0x14001ba26  pop     r15
0x14001ba28  pop     r14
0x14001ba2a  pop     r13
0x14001ba2c  pop     r12
0x14001ba2e  pop     rdi
0x14001ba2f  pop     rsi
0x14001ba30  pop     rbp
0x14001ba31  retn
```
