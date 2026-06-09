# RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__

- ea: `0x1800171d0`
- end: `0x18001720a`
- name: `RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b1ec`
- `0x1800171d0`

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
0x1800171d0  mov     [rsp+arg_0], rbx
0x1800171d5  push    rdi
0x1800171d6  sub     rsp, 20h
0x1800171da  lea     rbx, qword_180021190
0x1800171e1  mov     edi, 26h ; '&'
0x1800171e6  mov     rcx, [rbx]; lpMem
0x1800171e9  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800171ee  mov     qword ptr [rbx], 0
0x1800171f5  lea     rbx, [rbx+18h]
0x1800171f9  sub     rdi, 1
0x1800171fd  jnz     short loc_1800171E6
0x1800171ff  mov     rbx, [rsp+28h+arg_0]
0x180017204  add     rsp, 20h
0x180017208  pop     rdi
0x180017209  retn
```
