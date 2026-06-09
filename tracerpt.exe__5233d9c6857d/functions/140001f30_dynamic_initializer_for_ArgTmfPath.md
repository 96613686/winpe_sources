# _dynamic_initializer_for___ArgTmfPath__

- ea: `0x140001f30`
- end: `0x140001fd6`
- name: `_dynamic_initializer_for___ArgTmfPath__`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001f30`
- `0x1400400d6`

## pseudocode

```c
__int64 dynamic_initializer_for___ArgTmfPath__()
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
  memset_0(&unk_1400613D0, 0, 0x50u);
  if ( *v0 != &g_ArgsHead )
    __fastfail(3u);
  v1 = g_ArgumentCount;
  qword_1400613A8 = (__int64)v0;
  _ArgTmfPath = (__int64)&g_ArgsHead;
  *v0 = (struct ARGUMENT **)&_ArgTmfPath;
  qword_140083430 = (__int64)&_ArgTmfPath;
  result = (unsigned int)(v1 + 1);
  g_ArgumentCount = v1 + 1;
  dword_140061410 = v1;
  qword_1400613B8 = 136;
  return result;
}

```

## disassembly

```asm
0x140001f30  mov     [rsp+arg_0], rbx
0x140001f35  push    rdi
0x140001f36  sub     rsp, 20h
0x140001f3a  cmp     cs:dword_140060D18, 0
0x140001f41  lea     rdi, ?g_ArgsHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ArgsHead
0x140001f48  jz      short loc_140001F67
0x140001f4a  mov     rbx, rdi
0x140001f4d  mov     cs:?g_ArgsHead@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY g_ArgsHead
0x140001f54  mov     cs:qword_140083430, rbx
0x140001f5b  mov     cs:dword_140060D18, 0
0x140001f65  jmp     short loc_140001F6E
0x140001f67  mov     rbx, cs:qword_140083430
0x140001f6e  xor     edx, edx; Val
0x140001f70  lea     rcx, unk_1400613D0; void *
0x140001f77  lea     r8d, [rdx+50h]; Size
0x140001f7b  call    memset_0
0x140001f80  cmp     [rbx], rdi
0x140001f83  jz      short loc_140001F8C
0x140001f85  mov     ecx, 3
0x140001f8a  int     29h; Win8: RtlFailFast(ecx)
0x140001f8c  mov     ecx, cs:?g_ArgumentCount@@3IA; uint g_ArgumentCount
0x140001f92  lea     rax, ?_ArgTmfPath@@3V?$TYPED_ARGUMENT@PEAG@@A; TYPED_ARGUMENT<ushort *> _ArgTmfPath
0x140001f99  mov     cs:qword_1400613A8, rbx
0x140001fa0  mov     cs:?_ArgTmfPath@@3V?$TYPED_ARGUMENT@PEAG@@A, rdi; TYPED_ARGUMENT<ushort *> _ArgTmfPath
0x140001fa7  mov     [rbx], rax
0x140001faa  mov     rbx, [rsp+28h+arg_0]
0x140001faf  mov     cs:qword_140083430, rax
0x140001fb6  lea     eax, [rcx+1]
0x140001fb9  mov     cs:?g_ArgumentCount@@3IA, eax; uint g_ArgumentCount
0x140001fbf  mov     cs:dword_140061410, ecx
0x140001fc5  mov     cs:qword_1400613B8, 88h
0x140001fd0  add     rsp, 20h
0x140001fd4  pop     rdi
0x140001fd5  retn
```
