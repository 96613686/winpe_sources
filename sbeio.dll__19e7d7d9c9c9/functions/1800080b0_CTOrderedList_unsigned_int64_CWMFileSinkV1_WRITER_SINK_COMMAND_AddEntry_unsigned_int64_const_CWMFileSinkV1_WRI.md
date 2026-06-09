# CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::AddEntry(unsigned __int64 const &,CWMFileSinkV1::WRITER_SINK_COMMAND * const &)

- ea: `0x1800080b0`
- end: `0x18000817e`
- name: `?AddEntry@?$CTOrderedList@_KPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@@QEAAHAEB_KAEBQEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@Z`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bb80`
- `0x18000bc60`

## callees

- `0x180007fdc`
- `0x1800080b0`

## pseudocode

```c
__int64 __fastcall CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::AddEntry(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 result; // rax
  _QWORD *v7; // rcx
  _QWORD *v8; // rdx
  __int64 v9; // rax
  _QWORD *v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = 0;
  if ( (int)CTNodePool<CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::NODEBLOCK,CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::NODE,16>::AcquireNode(
              a1 + 32,
              &v10) < 0 )
    return 0;
  v7 = v10;
  *v10 = *a2;
  v7[1] = *a3;
  v7[2] = 0;
  v7[3] = 0;
  v8 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    while ( *v8 <= *a2 )
    {
      v8 = (_QWORD *)v8[2];
      if ( !v8 )
      {
        v7[3] = *(_QWORD *)(a1 + 8);
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = v7;
        goto LABEL_13;
      }
    }
    v7[2] = v8;
    v7[3] = v8[3];
    v9 = v8[3];
    if ( v9 )
      *(_QWORD *)(v9 + 16) = v7;
    v8[3] = v7;
    if ( v8 == *(_QWORD **)a1 )
      *(_QWORD *)a1 = v7;
  }
  else
  {
    *(_QWORD *)a1 = v7;
LABEL_13:
    *(_QWORD *)(a1 + 8) = v7;
  }
  result = 1;
  ++*(_DWORD *)(a1 + 24);
  return result;
}

```

## disassembly

```asm
0x1800080b0  mov     rax, rsp
0x1800080b3  mov     [rax+10h], rbx
0x1800080b7  mov     [rax+18h], rsi
0x1800080bb  push    rdi
0x1800080bc  sub     rsp, 20h
0x1800080c0  mov     rdi, rdx
0x1800080c3  mov     qword ptr [rax+8], 0
0x1800080cb  mov     rbx, rcx
0x1800080ce  lea     rdx, [rax+8]
0x1800080d2  add     rcx, 20h ; ' '
0x1800080d6  mov     rsi, r8
0x1800080d9  call    ?AcquireNode@?$CTNodePool@UNODEBLOCK@?$CTOrderedList@_KPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@@UNODE@2@$0BA@@@QEAAJPEAPEAUNODE@?$CTOrderedList@_KPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@@@Z; CTNodePool<CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::NODEBLOCK,CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::NODE,16>::AcquireNode(CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::NODE * *)
0x1800080de  test    eax, eax
0x1800080e0  jns     short loc_1800080E9
0x1800080e2  xor     eax, eax
0x1800080e4  jmp     loc_18000816E
0x1800080e9  mov     rax, [rdi]
0x1800080ec  mov     rcx, [rsp+28h+arg_0]
0x1800080f1  mov     [rcx], rax
0x1800080f4  mov     rax, [rsi]
0x1800080f7  mov     [rcx+8], rax
0x1800080fb  mov     qword ptr [rcx+10h], 0
0x180008103  mov     qword ptr [rcx+18h], 0
0x18000810b  mov     rdx, [rbx]
0x18000810e  test    rdx, rdx
0x180008111  jnz     short loc_18000811D
0x180008113  mov     [rbx], rcx
0x180008116  jmp     short loc_180008162
0x180008118  test    rdx, rdx
0x18000811b  jz      short loc_180008152
0x18000811d  mov     rax, [rdi]
0x180008120  cmp     [rdx], rax
0x180008123  ja      short loc_18000812B
0x180008125  mov     rdx, [rdx+10h]
0x180008129  jmp     short loc_180008118
0x18000812b  mov     [rcx+10h], rdx
0x18000812f  mov     rax, [rdx+18h]
0x180008133  mov     [rcx+18h], rax
0x180008137  mov     rax, [rdx+18h]
0x18000813b  test    rax, rax
0x18000813e  jz      short loc_180008144
0x180008140  mov     [rax+10h], rcx
0x180008144  mov     [rdx+18h], rcx
0x180008148  cmp     rdx, [rbx]
0x18000814b  jnz     short loc_180008166
0x18000814d  mov     [rbx], rcx
0x180008150  jmp     short loc_180008166
0x180008152  mov     rax, [rbx+8]
0x180008156  mov     [rcx+18h], rax
0x18000815a  mov     rax, [rbx+8]
0x18000815e  mov     [rax+10h], rcx
0x180008162  mov     [rbx+8], rcx
0x180008166  mov     eax, 1
0x18000816b  add     [rbx+18h], eax
0x18000816e  mov     rbx, [rsp+28h+arg_8]
0x180008173  mov     rsi, [rsp+28h+arg_10]
0x180008178  add     rsp, 20h
0x18000817c  pop     rdi
0x18000817d  retn
```
