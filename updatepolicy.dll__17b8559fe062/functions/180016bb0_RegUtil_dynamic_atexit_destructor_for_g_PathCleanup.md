# RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__

- ea: `0x180016bb0`
- end: `0x180016bea`
- name: `RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__`
- size: `58`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a150`
- `0x180016bb0`

## pseudocode

```c
void RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__()
{
  void **v0; // rbx
  __int64 v1; // rdi

  v0 = (void **)&qword_18001F190;
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
0x180016bb0  mov     [rsp+arg_0], rbx
0x180016bb5  push    rdi
0x180016bb6  sub     rsp, 20h
0x180016bba  lea     rbx, qword_18001F190
0x180016bc1  mov     edi, 26h ; '&'
0x180016bc6  mov     rcx, [rbx]; lpMem
0x180016bc9  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180016bce  mov     qword ptr [rbx], 0
0x180016bd5  lea     rbx, [rbx+18h]
0x180016bd9  sub     rdi, 1
0x180016bdd  jnz     short loc_180016BC6
0x180016bdf  mov     rbx, [rsp+28h+arg_0]
0x180016be4  add     rsp, 20h
0x180016be8  pop     rdi
0x180016be9  retn
```
