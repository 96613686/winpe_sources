# CDynamicArray<_ACCESS_ALLOWED_ACE *>::Iterate(CDynamicArrayCallback<_ACCESS_ALLOWED_ACE *> *)

- ea: `0x180006354`
- end: `0x1800063ab`
- name: `?Iterate@?$CDynamicArray@PEAU_ACCESS_ALLOWED_ACE@@@@QEAAJPEAV?$CDynamicArrayCallback@PEAU_ACCESS_ALLOWED_ACE@@@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64 (__fastcall ***)(_QWORD, __int64, _QWORD))`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800062a0`

## callees

- `0x180006354`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CDynamicArray<_ACCESS_ALLOWED_ACE *>::Iterate(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64, _QWORD))
{
  __int64 result; // rax
  int v5; // ebx

  result = 0;
  if ( *(_QWORD *)(a1 + 8) )
  {
    v5 = *(_DWORD *)a1 - 1;
    do
    {
      if ( v5 < 0 )
        break;
      result = (**a2)(a2, *(_QWORD *)(a1 + 8) + 8LL * v5, (unsigned int)v5);
      --v5;
    }
    while ( (int)result >= 0 );
  }
  return result;
}

```

## disassembly

```asm
0x180006354  mov     [rsp+arg_0], rbx
0x180006359  mov     [rsp+arg_8], rsi
0x18000635e  push    rdi
0x18000635f  sub     rsp, 20h
0x180006363  xor     eax, eax
0x180006365  mov     rsi, rdx
0x180006368  mov     rdi, rcx
0x18000636b  cmp     [rcx+8], rax
0x18000636f  jz      short loc_18000639B
0x180006371  mov     ebx, [rcx]
0x180006373  dec     ebx
0x180006375  test    ebx, ebx
0x180006377  js      short loc_18000639B
0x180006379  mov     rax, [rdi+8]
0x18000637d  mov     r8, [rsi]
0x180006380  movsxd  rcx, ebx
0x180006383  lea     rdx, [rax+rcx*8]
0x180006387  mov     rax, [r8]
0x18000638a  mov     r8d, ebx
0x18000638d  mov     rcx, rsi
0x180006390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006395  dec     ebx
0x180006397  test    eax, eax
0x180006399  jns     short loc_180006375
0x18000639b  mov     rbx, [rsp+28h+arg_0]
0x1800063a0  mov     rsi, [rsp+28h+arg_8]
0x1800063a5  add     rsp, 20h
0x1800063a9  pop     rdi
0x1800063aa  retn
```
