# _dynamic_initializer_for___ArgComp__

- ea: `0x140001010`
- end: `0x1400010b6`
- name: `_dynamic_initializer_for___ArgComp__`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001010`
- `0x1400400d6`

## pseudocode

```c
__int64 dynamic_initializer_for___ArgComp__()
{
  struct ARGUMENT ***v0; // rbx
  int v1; // ecx
  __int64 result; // rax

  if ( dword_140060D18 )
  {
    v0 = (struct ARGUMENT ***)&g_ArgsHead;
    g_ArgsHead = (struct ARGUMENT *)&g_ArgsHead;
    qword_140083430 = (__int64)&g_ArgsHead;
    dword_140060D18 = 0;
  }
  else
  {
    v0 = (struct ARGUMENT ***)qword_140083430;
  }
  memset_0(&unk_140061230, 0, 0x50u);
  if ( *v0 != &g_ArgsHead )
    __fastfail(3u);
  v1 = g_ArgumentCount;
  qword_140061208 = (__int64)v0;
  _ArgComp = (__int64)&g_ArgsHead;
  *v0 = (struct ARGUMENT **)&_ArgComp;
  qword_140083430 = (__int64)&_ArgComp;
  result = (unsigned int)(v1 + 1);
  g_ArgumentCount = v1 + 1;
  dword_140061270 = v1;
  qword_140061218 = 136;
  return result;
}

```

## disassembly

```asm
0x140001010  mov     [rsp+arg_0], rbx
0x140001015  push    rdi
0x140001016  sub     rsp, 20h
0x14000101a  cmp     cs:dword_140060D18, 0
0x140001021  lea     rdi, ?g_ArgsHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ArgsHead
0x140001028  jz      short loc_140001047
0x14000102a  mov     rbx, rdi
0x14000102d  mov     cs:?g_ArgsHead@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY g_ArgsHead
0x140001034  mov     cs:qword_140083430, rbx
0x14000103b  mov     cs:dword_140060D18, 0
0x140001045  jmp     short loc_14000104E
0x140001047  mov     rbx, cs:qword_140083430
0x14000104e  xor     edx, edx; Val
0x140001050  lea     rcx, unk_140061230; void *
0x140001057  lea     r8d, [rdx+50h]; Size
0x14000105b  call    memset_0
0x140001060  cmp     [rbx], rdi
0x140001063  jz      short loc_14000106C
0x140001065  mov     ecx, 3
0x14000106a  int     29h; Win8: RtlFailFast(ecx)
0x14000106c  mov     ecx, cs:?g_ArgumentCount@@3IA; uint g_ArgumentCount
0x140001072  lea     rax, ?_ArgComp@@3V?$TYPED_ARGUMENT@PEAG@@A; TYPED_ARGUMENT<ushort *> _ArgComp
0x140001079  mov     cs:qword_140061208, rbx
0x140001080  mov     cs:?_ArgComp@@3V?$TYPED_ARGUMENT@PEAG@@A, rdi; TYPED_ARGUMENT<ushort *> _ArgComp
0x140001087  mov     [rbx], rax
0x14000108a  mov     rbx, [rsp+28h+arg_0]
0x14000108f  mov     cs:qword_140083430, rax
0x140001096  lea     eax, [rcx+1]
0x140001099  mov     cs:?g_ArgumentCount@@3IA, eax; uint g_ArgumentCount
0x14000109f  mov     cs:dword_140061270, ecx
0x1400010a5  mov     cs:qword_140061218, 88h
0x1400010b0  add     rsp, 20h
0x1400010b4  pop     rdi
0x1400010b5  retn
```
