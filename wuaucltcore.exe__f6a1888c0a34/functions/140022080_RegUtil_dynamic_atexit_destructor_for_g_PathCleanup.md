# RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__

- ea: `0x140022080`
- end: `0x1400220ba`
- name: `RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000d4cc`
- `0x140022080`

## pseudocode

```c
void RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__()
{
  void **v0; // rbx
  __int64 v1; // rdi

  v0 = (void **)&qword_14002E160;
  v1 = 38;
  do
  {
    SusFree(*v0);
    *v0 = 0;
    v0 += 3;
    --v1;
  }
  while ( v1 );
}

```

## disassembly

```asm
0x140022080  mov     [rsp+arg_0], rbx
0x140022085  push    rdi
0x140022086  sub     rsp, 20h
0x14002208a  lea     rbx, qword_14002E160
0x140022091  mov     edi, 26h ; '&'
0x140022096  mov     rcx, [rbx]; lpMem
0x140022099  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002209e  mov     qword ptr [rbx], 0
0x1400220a5  lea     rbx, [rbx+18h]
0x1400220a9  sub     rdi, 1
0x1400220ad  jnz     short loc_140022096
0x1400220af  mov     rbx, [rsp+28h+arg_0]
0x1400220b4  add     rsp, 20h
0x1400220b8  pop     rdi
0x1400220b9  retn
```
