# InpAllocatePacketProfilerLocked

- ea: `0x1400084f0`
- end: `0x140008626`
- name: `InpAllocatePacketProfilerLocked`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000802c`

## callees

- `0x1400084f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140008530`
- `ntoskrnl!ExAllocatePool2` at `0x140008530`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000859d`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000859d`

## pseudocode

```c
__int64 __fastcall InpAllocatePacketProfilerLocked(ULONG *a1, unsigned int a2, __int64 *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebp
  __int64 Pool2; // rax
  __int64 v8; // rsi
  __int64 result; // rax
  _QWORD *v10; // rdi
  unsigned int v11; // r15d
  unsigned __int64 v12; // rbx
  _QWORD *v13; // rax

  v5 = (a2 >> 10) + 1;
  if ( (a2 & 0x3FF) == 0 )
    v5 = a2 >> 10;
  v6 = v5;
  Pool2 = ExAllocatePool2(64, ((unsigned __int64)v5 << 7) + 64, 1852402518);
  v8 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v10 = (_QWORD *)(Pool2 + 8);
  v11 = 0;
  *(_QWORD *)(Pool2 + 16) = Pool2 + 8;
  for ( *(_QWORD *)(Pool2 + 8) = Pool2 + 8; v11 < v6; *(_WORD *)(v12 + v8 + 82) = 1024 )
  {
    v12 = (unsigned __int64)v11 << 7;
    ExInitializeNPagedLookasideList(
      (PNPAGED_LOOKASIDE_LIST)(v12 + v8 + 64),
      InLookasideAllocate,
      0,
      0x200u,
      ++v11 << 10,
      a1[411],
      0);
  }
  *(_DWORD *)v8 = v6;
  *(_WORD *)(v8 + 40) = *(_WORD *)(*(_QWORD *)a1 + 3272LL);
  *(_QWORD *)(v8 + 48) = *(_QWORD *)(*(_QWORD *)a1 + 3264LL);
  *(_OWORD *)(v8 + 24) = *(_OWORD *)(*(_QWORD *)a1 + 2736LL);
  v13 = (_QWORD *)qword_140016248;
  if ( *(__int64 **)qword_140016248 != &KmclProfilerList )
    __fastfail(3u);
  v10[1] = qword_140016248;
  *v10 = &KmclProfilerList;
  *v13 = v10;
  result = 0;
  qword_140016248 = (__int64)v10;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1400084f0  push    rbx
0x1400084f2  push    rbp
0x1400084f3  push    rsi
0x1400084f4  push    rdi
0x1400084f5  push    r12
0x1400084f7  push    r14
0x1400084f9  push    r15
0x1400084fb  sub     rsp, 40h
0x1400084ff  mov     r9d, edx
0x140008502  mov     r14, rcx
0x140008505  shr     r9d, 0Ah
0x140008509  mov     ecx, 40h ; '@'
0x14000850e  test    edx, 3FFh
0x140008514  mov     r12, r8
0x140008517  mov     r8d, 6E696B56h
0x14000851d  lea     eax, [r9+1]
0x140008521  cmovz   eax, r9d
0x140008525  mov     edx, eax
0x140008527  shl     rdx, 7
0x14000852b  add     rdx, rcx
0x14000852e  mov     ebp, eax
0x140008530  call    cs:__imp_ExAllocatePool2
0x140008537  nop     dword ptr [rax+rax+00h]
0x14000853c  mov     rsi, rax
0x14000853f  test    rax, rax
0x140008542  jnz     short loc_14000854E
0x140008544  mov     eax, 0C000009Ah
0x140008549  jmp     loc_140008616
0x14000854e  lea     rdi, [rax+8]
0x140008552  xor     r15d, r15d
0x140008555  mov     [rdi+8], rdi
0x140008559  mov     [rdi], rdi
0x14000855c  test    ebp, ebp
0x14000855e  jz      short loc_1400085B8
0x140008560  mov     eax, [r14+66Ch]
0x140008567  lea     r8d, [r15+1]
0x14000856b  xor     edx, edx
0x14000856d  shl     r8d, 0Ah
0x140008571  mov     [rsp+78h+Depth], dx; Depth
0x140008576  lea     rcx, [rsi+40h]
0x14000857a  mov     [rsp+78h+Tag], eax; Tag
0x14000857e  lea     rdx, InLookasideAllocate; Allocate
0x140008585  mov     [rsp+78h+Size], r8; Size
0x14000858a  mov     r9d, 200h; Flags
0x140008590  mov     ebx, r15d
0x140008593  xor     r8d, r8d; Free
0x140008596  shl     rbx, 7
0x14000859a  add     rcx, rbx; Lookaside
0x14000859d  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400085a4  nop     dword ptr [rax+rax+00h]
0x1400085a9  inc     r15d
0x1400085ac  mov     word ptr [rbx+rsi+52h], 400h
0x1400085b3  cmp     r15d, ebp
0x1400085b6  jb      short loc_140008560
0x1400085b8  mov     [rsi], ebp
0x1400085ba  mov     rax, [r14]
0x1400085bd  movzx   ecx, word ptr [rax+0CC8h]
0x1400085c4  mov     [rsi+28h], cx
0x1400085c8  mov     rax, [r14]
0x1400085cb  mov     rcx, [rax+0CC0h]
0x1400085d2  mov     [rsi+30h], rcx
0x1400085d6  lea     rcx, KmclProfilerList
0x1400085dd  mov     rax, [r14]
0x1400085e0  movups  xmm0, xmmword ptr [rax+0AB0h]
0x1400085e7  movdqu  xmmword ptr [rsi+18h], xmm0
0x1400085ec  mov     rax, cs:qword_140016248
0x1400085f3  cmp     [rax], rcx
0x1400085f6  jz      short loc_1400085FF
0x1400085f8  mov     ecx, 3
0x1400085fd  int     29h; Win8: RtlFailFast(ecx)
0x1400085ff  mov     [rdi+8], rax
0x140008603  mov     [rdi], rcx
0x140008606  mov     [rax], rdi
0x140008609  xor     eax, eax
0x14000860b  mov     cs:qword_140016248, rdi
0x140008612  mov     [r12], rsi
0x140008616  add     rsp, 40h
0x14000861a  pop     r15
0x14000861c  pop     r14
0x14000861e  pop     r12
0x140008620  pop     rdi
0x140008621  pop     rsi
0x140008622  pop     rbp
0x140008623  pop     rbx
0x140008624  retn
```
