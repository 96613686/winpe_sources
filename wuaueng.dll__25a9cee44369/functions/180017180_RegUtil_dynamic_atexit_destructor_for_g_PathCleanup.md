# RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__

- ea: `0x180017180`
- end: `0x1800171ba`
- name: `RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__`
- size: `58`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b198`
- `0x180017180`

## pseudocode

```c
void RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__()
{
  void **v0; // rbx
  __int64 v1; // rdi

  v0 = (void **)&qword_180021190;
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
0x180017180  mov     [rsp+arg_0], rbx
0x180017185  push    rdi
0x180017186  sub     rsp, 20h
0x18001718a  lea     rbx, qword_180021190
0x180017191  mov     edi, 26h ; '&'
0x180017196  mov     rcx, [rbx]; lpMem
0x180017199  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18001719e  mov     qword ptr [rbx], 0
0x1800171a5  lea     rbx, [rbx+18h]
0x1800171a9  sub     rdi, 1
0x1800171ad  jnz     short loc_180017196
0x1800171af  mov     rbx, [rsp+28h+arg_0]
0x1800171b4  add     rsp, 20h
0x1800171b8  pop     rdi
0x1800171b9  retn
```
