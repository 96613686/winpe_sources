# CTNodePool<CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::NODEBLOCK,CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::NODE,16>::AcquireNode(CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::NODE * *)

- ea: `0x180007fdc`
- end: `0x180008073`
- name: `?AcquireNode@?$CTNodePool@UNODEBLOCK@?$CTOrderedList@_KPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@@UNODE@2@$0BA@@@QEAAJPEAPEAUNODE@?$CTOrderedList@_KPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@@@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800080b0`

## callees

- `0x180007fdc`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000800f`
- `KERNEL32!HeapAlloc` at `0x18000800f`
- `KERNEL32!GetProcessHeap` at `0x180008000`
- `KERNEL32!GetProcessHeap` at `0x180008000`

## pseudocode

```c
__int64 __fastcall CTNodePool<CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::NODEBLOCK,CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::NODE,16>::AcquireNode(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v6; // r8
  unsigned int i; // edx
  __int64 v9; // rcx
  _QWORD *v10; // rcx
  __int64 v11; // rax

  if ( !*a1 )
  {
    v4 = 32LL * (unsigned int)(*((_DWORD *)a1 + 4) - 1);
    ProcessHeap = GetProcessHeap();
    v6 = HeapAlloc(ProcessHeap, 0, v4 + 40);
    if ( !v6 )
      return 2147942414LL;
    for ( i = 0; i < *((_DWORD *)a1 + 4); *a1 = (__int64)v10 )
    {
      v9 = i++;
      v10 = &v6[4 * v9 + 1];
      v10[2] = *a1;
    }
    *v6 = a1[1];
    a1[1] = (__int64)v6;
  }
  v11 = *a1;
  *a2 = *a1;
  *a1 = *(_QWORD *)(v11 + 16);
  return 0;
}

```

## disassembly

```asm
0x180007fdc  mov     [rsp+arg_0], rbx
0x180007fe1  mov     [rsp+arg_8], rsi
0x180007fe6  push    rdi
0x180007fe7  sub     rsp, 20h
0x180007feb  cmp     qword ptr [rcx], 0
0x180007fef  mov     rsi, rdx
0x180007ff2  mov     rdi, rcx
0x180007ff5  jnz     short loc_180008054
0x180007ff7  mov     ebx, [rcx+10h]
0x180007ffa  dec     ebx
0x180007ffc  shl     rbx, 5
0x180008000  call    cs:__imp_GetProcessHeap
0x180008006  lea     r8, [rbx+28h]; dwBytes
0x18000800a  xor     edx, edx; dwFlags
0x18000800c  mov     rcx, rax; hHeap
0x18000800f  call    cs:__imp_HeapAlloc
0x180008015  mov     r8, rax
0x180008018  test    rax, rax
0x18000801b  jnz     short loc_180008024
0x18000801d  mov     eax, 8007000Eh
0x180008022  jmp     short loc_180008063
0x180008024  xor     edx, edx
0x180008026  cmp     [rdi+10h], edx
0x180008029  jbe     short loc_180008049
0x18000802b  mov     rax, [rdi]
0x18000802e  mov     ecx, edx
0x180008030  inc     edx
0x180008032  shl     rcx, 5
0x180008036  add     rcx, 8
0x18000803a  add     rcx, r8
0x18000803d  mov     [rcx+10h], rax
0x180008041  mov     [rdi], rcx
0x180008044  cmp     edx, [rdi+10h]
0x180008047  jb      short loc_18000802B
0x180008049  mov     rax, [rdi+8]
0x18000804d  mov     [r8], rax
0x180008050  mov     [rdi+8], r8
0x180008054  mov     rax, [rdi]
0x180008057  mov     [rsi], rax
0x18000805a  mov     rax, [rax+10h]
0x18000805e  mov     [rdi], rax
0x180008061  xor     eax, eax
0x180008063  mov     rbx, [rsp+28h+arg_0]
0x180008068  mov     rsi, [rsp+28h+arg_8]
0x18000806d  add     rsp, 20h
0x180008071  pop     rdi
0x180008072  retn
```
