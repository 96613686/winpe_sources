# DelayedDeleteAltName

- ea: `0x14000157c`
- end: `0x140001679`
- name: `DelayedDeleteAltName`
- size: `253`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400028a4`

## callees

- `0x14000157c`
- `0x140003729`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400015cd`
- `ntdll!RtlAllocateHeap` at `0x140001624`
- `ntdll!RtlAllocateHeap` at `0x1400015cd`
- `ntdll!RtlAllocateHeap` at `0x140001624`
- `ntdll!RtlEqualUnicodeString` at `0x1400015a8`
- `ntdll!RtlEqualUnicodeString` at `0x1400015a8`

## pseudocode

```c
__int64 __fastcall DelayedDeleteAltName(PCUNICODE_STRING String2)
{
  const UNICODE_STRING *i; // rbx
  _QWORD *Heap; // rax
  _QWORD *v4; // rbx
  __int64 result; // rax
  PVOID v6; // rax
  _QWORD *v7; // rcx

  for ( i = (const UNICODE_STRING *)g_fDelayedList;
        i != (const UNICODE_STRING *)&g_fDelayedList;
        i = *(const UNICODE_STRING **)&i->Length )
  {
    if ( RtlEqualUnicodeString(i + 1, String2, 1u) )
      return 0x40000000;
  }
  Heap = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, 0x20u);
  v4 = Heap;
  if ( !Heap )
    return 3221225495LL;
  Heap[2] = 0;
  Heap[3] = 0;
  Heap[1] = Heap;
  *Heap = Heap;
  *((_WORD *)Heap + 8) = String2->Length;
  *((_WORD *)Heap + 9) = String2->Length;
  v6 = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, String2->Length);
  v4[3] = v6;
  if ( !v6 )
    return 3221225495LL;
  memmove_0(v6, String2->Buffer, String2->Length);
  v7 = off_140005128;
  if ( *off_140005128 != (_UNKNOWN *)&g_fDelayedList )
    __fastfail(3u);
  *v4 = &g_fDelayedList;
  result = 0;
  v4[1] = v7;
  *v7 = v4;
  off_140005128 = (_UNKNOWN **)v4;
  return result;
}

```

## disassembly

```asm
0x14000157c  mov     [rsp+arg_0], rbx
0x140001581  mov     [rsp+arg_8], rsi
0x140001586  push    rdi
0x140001587  sub     rsp, 20h
0x14000158b  mov     rbx, cs:g_fDelayedList
0x140001592  lea     rsi, g_fDelayedList
0x140001599  mov     rdi, rcx
0x14000159c  jmp     short loc_1400015B5
0x14000159e  lea     rcx, [rbx+10h]; String1
0x1400015a2  mov     r8b, 1; CaseInSensitive
0x1400015a5  mov     rdx, rdi; String2
0x1400015a8  call    cs:__imp_RtlEqualUnicodeString
0x1400015ae  test    al, al
0x1400015b0  jnz     short loc_1400015E5
0x1400015b2  mov     rbx, [rbx]
0x1400015b5  cmp     rbx, rsi
0x1400015b8  jnz     short loc_14000159E
0x1400015ba  mov     rcx, gs:60h
0x1400015c3  xor     edx, edx; Flags
0x1400015c5  mov     rcx, [rcx+30h]; HeapHandle
0x1400015c9  lea     r8d, [rdx+20h]; Size
0x1400015cd  call    cs:__imp_RtlAllocateHeap
0x1400015d3  mov     rbx, rax
0x1400015d6  test    rax, rax
0x1400015d9  jnz     short loc_1400015EC
0x1400015db  mov     eax, 0C0000017h
0x1400015e0  jmp     loc_140001669
0x1400015e5  mov     eax, 40000000h
0x1400015ea  jmp     short loc_140001669
0x1400015ec  mov     qword ptr [rax+10h], 0
0x1400015f4  xor     edx, edx; Flags
0x1400015f6  mov     qword ptr [rax+18h], 0
0x1400015fe  mov     [rax+8], rbx
0x140001602  mov     [rax], rbx
0x140001605  movzx   eax, word ptr [rdi]
0x140001608  mov     [rbx+10h], ax
0x14000160c  movzx   eax, word ptr [rdi]
0x14000160f  mov     [rbx+12h], ax
0x140001613  mov     rcx, gs:60h
0x14000161c  movzx   r8d, word ptr [rdi]; Size
0x140001620  mov     rcx, [rcx+30h]; HeapHandle
0x140001624  call    cs:__imp_RtlAllocateHeap
0x14000162a  mov     [rbx+18h], rax
0x14000162e  test    rax, rax
0x140001631  jz      short loc_1400015DB
0x140001633  movzx   r8d, word ptr [rdi]; Size
0x140001637  mov     rcx, rax; void *
0x14000163a  mov     rdx, [rdi+8]; Src
0x14000163e  call    memmove_0
0x140001643  mov     rcx, cs:off_140005128
0x14000164a  cmp     [rcx], rsi
0x14000164d  jz      short loc_140001656
0x14000164f  mov     ecx, 3
0x140001654  int     29h; Win8: RtlFailFast(ecx)
0x140001656  mov     [rbx], rsi
0x140001659  xor     eax, eax
0x14000165b  mov     [rbx+8], rcx
0x14000165f  mov     [rcx], rbx
0x140001662  mov     cs:off_140005128, rbx
0x140001669  mov     rbx, [rsp+28h+arg_0]
0x14000166e  mov     rsi, [rsp+28h+arg_8]
0x140001673  add     rsp, 20h
0x140001677  pop     rdi
0x140001678  retn
```
