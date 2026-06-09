# CUserPropertyStore::Commit(void)

- ea: `0x18000dcc0`
- end: `0x18000dd1b`
- name: `?Commit@CUserPropertyStore@@UEAAJXZ`
- size: `91`
- prototype: `__int64 __fastcall(CUserPropertyStore *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000dcc0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CUserPropertyStore::Commit(CUserPropertyStore *this)
{
  __int64 v1; // rdx
  int v3; // ebx
  int *v4; // rax
  int v5; // r8d
  __int64 v6; // rcx
  unsigned int v7; // eax

  v1 = 0;
  v3 = 0;
  do
  {
    v4 = (int *)*((_QWORD *)this + 3);
    if ( v4 )
      v5 = *v4;
    else
      v5 = 0;
    if ( v3 >= v5 )
      break;
    v6 = *(_QWORD *)(*((_QWORD *)v4 + 1) + 8LL * v3);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 56LL))(v6, v1);
    v1 = 0;
    if ( v7 != -2147467263 )
      v1 = v7;
    ++v3;
  }
  while ( (int)v1 >= 0 );
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000dcc0  mov     [rsp+arg_0], rbx
0x18000dcc5  push    rdi
0x18000dcc6  sub     rsp, 20h
0x18000dcca  xor     edx, edx
0x18000dccc  mov     rdi, rcx
0x18000dccf  xor     ebx, ebx
0x18000dcd1  mov     rax, [rdi+18h]
0x18000dcd5  test    rax, rax
0x18000dcd8  jz      short loc_18000DCDF
0x18000dcda  mov     r8d, [rax]
0x18000dcdd  jmp     short loc_18000DCE2
0x18000dcdf  xor     r8d, r8d
0x18000dce2  cmp     ebx, r8d
0x18000dce5  jge     short loc_18000DD0E
0x18000dce7  mov     rax, [rax+8]
0x18000dceb  movsxd  rcx, ebx
0x18000dcee  mov     rcx, [rax+rcx*8]
0x18000dcf2  mov     rax, [rcx]
0x18000dcf5  mov     rax, [rax+38h]
0x18000dcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcfe  xor     edx, edx
0x18000dd00  cmp     eax, 80004001h
0x18000dd05  cmovnz  edx, eax
0x18000dd08  inc     ebx
0x18000dd0a  test    edx, edx
0x18000dd0c  jns     short loc_18000DCD1
0x18000dd0e  mov     rbx, [rsp+28h+arg_0]
0x18000dd13  mov     eax, edx
0x18000dd15  add     rsp, 20h
0x18000dd19  pop     rdi
0x18000dd1a  retn
```
