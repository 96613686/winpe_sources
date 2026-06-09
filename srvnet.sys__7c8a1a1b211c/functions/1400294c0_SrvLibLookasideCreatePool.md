# SrvLibLookasideCreatePool

- ea: `0x1400294c0`
- end: `0x1400295d3`
- name: `SrvLibLookasideCreatePool`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1400294c0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002958d`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002958d`
- `ntoskrnl!ExAllocatePool3` at `0x14002952e`
- `ntoskrnl!ExAllocatePool3` at `0x14002952e`

## pseudocode

```c
__int64 __fastcall SrvLibLookasideCreatePool(
        ALLOCATE_FUNCTION *a1,
        FREE_FUNCTION *a2,
        int a3,
        SIZE_T a4,
        ULONG Tag,
        USHORT Depth)
{
  __int64 v7; // rax
  unsigned int v9; // r15d
  __int64 v10; // rax
  __int64 v11; // r14
  ULONG v12; // ebp
  unsigned int v13; // esi
  __int64 v14; // rbx
  __int64 v16; // [rsp+40h] [rbp-58h]
  __int128 v17; // [rsp+48h] [rbp-50h] BYREF

  v17 = 0;
  LOBYTE(v17) = 1;
  DWORD2(v17) = 0;
  v7 = (unsigned int)(SrvNetNumberOfActiveProcessorsAtServerStart + 1);
  if ( (unsigned int)SrvNetNumberOfActiveProcessorsAtServerStart <= 1 )
    v7 = (unsigned int)SrvNetNumberOfActiveProcessorsAtServerStart;
  v9 = v7;
  v10 = ExAllocatePool3(74, 192 * v7, 1280529228, &v17, 1);
  v16 = v10;
  v11 = v10;
  if ( v10 )
  {
    v12 = a3 | 0x200;
    v13 = 0;
    v14 = v10;
    if ( v9 )
    {
      do
      {
        ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v14, a1, a2, v12, a4, Tag, Depth);
        *(_WORD *)(v14 + 128) = Depth;
        ++v13;
        *(_WORD *)(v14 + 18) = Depth;
        v14 += 192;
      }
      while ( v13 < v9 );
      return v16;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1400294c0  mov     r11, rsp
0x1400294c3  mov     [r11+18h], rbx
0x1400294c7  mov     [r11+10h], rdx
0x1400294cb  mov     [r11+8], rcx
0x1400294cf  push    rbp
0x1400294d0  push    rsi
0x1400294d1  push    rdi
0x1400294d2  push    r12
0x1400294d4  push    r13
0x1400294d6  push    r14
0x1400294d8  push    r15
0x1400294da  sub     rsp, 60h
0x1400294de  mov     r10d, cs:SrvNetNumberOfActiveProcessorsAtServerStart
0x1400294e5  xorps   xmm0, xmm0
0x1400294e8  movups  [rsp+98h+var_50], xmm0
0x1400294ed  cmp     r10d, 1
0x1400294f1  mov     byte ptr [rsp+98h+var_50], 1
0x1400294f6  mov     r13, r9
0x1400294f9  mov     dword ptr [rsp+98h+var_50+8], 0
0x140029501  lea     eax, [r10+1]
0x140029505  mov     dword ptr [rsp+98h+Size], 1
0x14002950d  cmovbe  eax, r10d
0x140029511  lea     r9, [r11-50h]
0x140029515  mov     ebp, r8d
0x140029518  mov     r15d, eax
0x14002951b  mov     ecx, 4Ah ; 'J'
0x140029520  mov     r8d, 4C53534Ch
0x140029526  lea     rdx, [rax+rax*2]
0x14002952a  shl     rdx, 6
0x14002952e  call    cs:__imp_ExAllocatePool3
0x140029535  nop     dword ptr [rax+rax+00h]
0x14002953a  mov     [rsp+98h+var_58], rax
0x14002953f  mov     r14, rax
0x140029542  test    rax, rax
0x140029545  jz      short loc_1400295B7
0x140029547  bts     ebp, 9
0x14002954b  xor     esi, esi
0x14002954d  mov     rbx, rax
0x140029550  test    r15d, r15d
0x140029553  jz      short loc_1400295B7
0x140029555  movzx   edi, [rsp+98h+arg_28]
0x14002955d  mov     r12d, [rsp+98h+arg_20]
0x140029565  mov     r14, [rsp+98h+Free]
0x14002956d  mov     rdx, [rsp+98h+Allocate]; Allocate
0x140029575  mov     r9d, ebp; Flags
0x140029578  mov     [rsp+98h+Depth], di; Depth
0x14002957d  mov     r8, r14; Free
0x140029580  mov     [rsp+98h+Tag], r12d; Tag
0x140029585  mov     rcx, rbx; Lookaside
0x140029588  mov     [rsp+98h+Size], r13; Size
0x14002958d  call    cs:__imp_ExInitializeNPagedLookasideList
0x140029594  nop     dword ptr [rax+rax+00h]
0x140029599  mov     [rbx+80h], di
0x1400295a0  inc     esi
0x1400295a2  mov     [rbx+12h], di
0x1400295a6  add     rbx, 0C0h
0x1400295ad  cmp     esi, r15d
0x1400295b0  jb      short loc_14002956D
0x1400295b2  mov     r14, [rsp+98h+var_58]
0x1400295b7  mov     rbx, [rsp+98h+arg_10]
0x1400295bf  mov     rax, r14
0x1400295c2  add     rsp, 60h
0x1400295c6  pop     r15
0x1400295c8  pop     r14
0x1400295ca  pop     r13
0x1400295cc  pop     r12
0x1400295ce  pop     rdi
0x1400295cf  pop     rsi
0x1400295d0  pop     rbp
0x1400295d1  retn
```
