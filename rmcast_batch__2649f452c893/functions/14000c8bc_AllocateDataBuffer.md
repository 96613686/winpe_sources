# AllocateDataBuffer

- ea: `0x14000c8bc`
- end: `0x14000ca02`
- name: `AllocateDataBuffer`
- size: `326`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000f2d8`
- `0x1400138b0`

## callees

- `0x14000c8bc`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000c96c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000c96c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000c994`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000c994`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000c92b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000c92b`
- `ntoskrnl!ExAllocatePool2` at `0x14000c9cd`
- `ntoskrnl!ExAllocatePool2` at `0x14000c9cd`

## pseudocode

```c
__int64 __fastcall AllocateDataBuffer(__int64 a1, _DWORD *a2, unsigned int a3)
{
  __int64 v3; // rdi
  _DWORD *v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  PVOID v10; // rax
  __int64 v11; // rax

  v3 = a3;
  v6 = *(_DWORD **)(a1 + 48);
  if ( a3 > v6[70] && !v6[71] )
  {
    if ( a3 > v6[69] )
      v6[69] = a3;
    *(_DWORD *)(*(_QWORD *)(a1 + 48) + 276LL) += 100;
    *(_DWORD *)(*(_QWORD *)(a1 + 48) + 280LL) = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 276LL);
    v7 = *(_QWORD *)(a1 + 48);
    *(_DWORD *)(a1 + 32) |= 0x8000u;
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v7 + 320));
    ExInitializeNPagedLookasideList(
      (PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 48) + 320LL),
      0,
      0,
      0x200u,
      *(unsigned int *)(*(_QWORD *)(a1 + 48) + 280LL),
      0x446D6750u,
      *(_WORD *)(*(_QWORD *)(a1 + 48) + 288LL));
  }
  v8 = *(_DWORD *)(a1 + 32);
  if ( (v8 & 0x8000) != 0 && (v9 = *(_QWORD *)(a1 + 48), (unsigned int)v3 <= *(_DWORD *)(v9 + 280)) )
  {
    v10 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v9 + 320));
    *(_QWORD *)a2 = v10;
    if ( v10 )
    {
      ++*(_DWORD *)(*(_QWORD *)(a1 + 48) + 284LL);
      a2[9] |= 1u;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 32) = v8 & 0xFFFF7FFF;
    *(_QWORD *)a2 = ExAllocatePool2(64, v3, 1148020560);
    v11 = *(_QWORD *)(a1 + 48);
    if ( (unsigned int)v3 > *(_DWORD *)(v11 + 276) )
      *(_DWORD *)(v11 + 276) = v3;
  }
  return *(_QWORD *)a2;
}

```

## disassembly

```asm
0x14000c8bc  mov     [rsp+arg_0], rbx
0x14000c8c1  mov     [rsp+arg_8], rsi
0x14000c8c6  push    rdi
0x14000c8c7  sub     rsp, 40h
0x14000c8cb  mov     edi, r8d
0x14000c8ce  mov     rsi, rdx
0x14000c8d1  mov     rbx, rcx
0x14000c8d4  mov     rax, [rcx+30h]
0x14000c8d8  cmp     r8d, [rax+118h]
0x14000c8df  jbe     loc_14000C978
0x14000c8e5  cmp     dword ptr [rax+11Ch], 0
0x14000c8ec  jnz     loc_14000C978
0x14000c8f2  cmp     edi, [rax+114h]
0x14000c8f8  jbe     short loc_14000C900
0x14000c8fa  mov     [rax+114h], edi
0x14000c900  mov     rax, [rcx+30h]
0x14000c904  add     dword ptr [rax+114h], 64h ; 'd'
0x14000c90b  mov     rcx, [rcx+30h]
0x14000c90f  mov     eax, [rcx+114h]
0x14000c915  mov     [rcx+118h], eax
0x14000c91b  mov     rcx, [rbx+30h]
0x14000c91f  bts     dword ptr [rbx+20h], 0Fh
0x14000c924  add     rcx, 140h; Lookaside
0x14000c92b  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000c932  nop     dword ptr [rax+rax+00h]
0x14000c937  mov     rax, [rbx+30h]
0x14000c93b  mov     r9d, 200h; Flags
0x14000c941  xor     r8d, r8d; Free
0x14000c944  mov     edx, [rax+118h]
0x14000c94a  lea     rcx, [rax+140h]; Lookaside
0x14000c951  movzx   eax, word ptr [rax+120h]
0x14000c958  mov     [rsp+48h+Depth], ax; Depth
0x14000c95d  mov     [rsp+48h+Tag], 446D6750h; Tag
0x14000c965  mov     [rsp+48h+Size], rdx; Size
0x14000c96a  xor     edx, edx; Allocate
0x14000c96c  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000c973  nop     dword ptr [rax+rax+00h]
0x14000c978  mov     eax, [rbx+20h]
0x14000c97b  bt      eax, 0Fh
0x14000c97f  jnb     short loc_14000C9B8
0x14000c981  mov     rcx, [rbx+30h]
0x14000c985  cmp     edi, [rcx+118h]
0x14000c98b  ja      short loc_14000C9B8
0x14000c98d  add     rcx, 140h; Lookaside
0x14000c994  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000c99b  nop     dword ptr [rax+rax+00h]
0x14000c9a0  mov     [rsi], rax
0x14000c9a3  test    rax, rax
0x14000c9a6  jz      short loc_14000C9EE
0x14000c9a8  mov     rax, [rbx+30h]
0x14000c9ac  inc     dword ptr [rax+11Ch]
0x14000c9b2  or      dword ptr [rsi+24h], 1
0x14000c9b6  jmp     short loc_14000C9EE
0x14000c9b8  btr     eax, 0Fh
0x14000c9bc  mov     rdx, rdi
0x14000c9bf  mov     ecx, 40h ; '@'
0x14000c9c4  mov     [rbx+20h], eax
0x14000c9c7  mov     r8d, 446D6750h
0x14000c9cd  call    cs:__imp_ExAllocatePool2
0x14000c9d4  nop     dword ptr [rax+rax+00h]
0x14000c9d9  mov     [rsi], rax
0x14000c9dc  mov     rax, [rbx+30h]
0x14000c9e0  cmp     edi, [rax+114h]
0x14000c9e6  jbe     short loc_14000C9EE
0x14000c9e8  mov     [rax+114h], edi
0x14000c9ee  mov     rax, [rsi]
0x14000c9f1  mov     rsi, [rsp+48h+arg_8]
0x14000c9f6  mov     rbx, [rsp+48h+arg_0]
0x14000c9fb  add     rsp, 40h
0x14000c9ff  pop     rdi
0x14000ca00  retn
```
