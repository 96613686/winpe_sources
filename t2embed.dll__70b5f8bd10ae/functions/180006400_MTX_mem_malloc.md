# MTX_mem_malloc

- ea: `0x180006400`
- end: `0x1800064fb`
- name: `MTX_mem_malloc`
- size: `251`
- prototype: ``
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x180001f60`
- `0x180003550`
- `0x180004e10`
- `0x1800059a0`
- `0x180006548`
- `0x1800067cc`
- `0x180006d30`
- `0x180007210`
- `0x1800088a0`
- `0x180009d40`
- `0x18000a650`
- `0x18000b8f0`
- `0x18000dca8`
- `0x18000ddd4`
- `0x18000e2d4`
- `0x18000e580`
- `0x18000e640`
- `0x18000e788`
- `0x18000e840`
- `0x18000eb94`
- `0x180017920`
- `0x180017cf0`
- `0x18001a414`
- `0x18001c574`

## callees

- `0x180006400`
- `0x18001d428`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall MTX_mem_malloc(__int64 *a1, unsigned int a2)
{
  __int64 v4; // rsi
  __int64 result; // rax
  int v6; // ebp
  __int64 v7; // rax
  int v8; // edx
  __int64 v9; // rax
  __int64 v10; // rcx

  if ( !a2 )
    return 0;
  ++*((_DWORD *)a1 + 4);
  v4 = ((__int64 (__fastcall *)(_QWORD))a1[3])(a2);
  if ( !v4 )
    goto LABEL_3;
  v6 = *((_DWORD *)a1 + 2);
  if ( *((_DWORD *)a1 + 3) >= v6 )
  {
    v7 = *a1;
    v8 = v6 + v6 / 4 + 128;
    *((_DWORD *)a1 + 2) = v8;
    if ( v7 )
      v9 = ((__int64 (__fastcall *)(__int64, __int64))a1[4])(v7, 16LL * v8);
    else
      v9 = ((__int64 (__fastcall *)(__int64))a1[3])(16LL * v8);
    *a1 = v9;
    if ( !v9 )
LABEL_3:
      NoMoreMemory(a1);
    for ( ; v6 < *((_DWORD *)a1 + 2); *(_DWORD *)(*a1 + 8 * v10 + 8) = 0 )
    {
      v10 = v6++;
      v10 *= 2;
      *(_QWORD *)(*a1 + 8 * v10) = 0;
    }
  }
  *(_QWORD *)(*a1 + 16LL * *((int *)a1 + 3)) = v4;
  *(_DWORD *)(*a1 + 16LL * *((int *)a1 + 3) + 8) = a2;
  result = v4;
  ++*((_DWORD *)a1 + 3);
  return result;
}

```

## disassembly

```asm
0x180006400  mov     [rsp+arg_10], rbx
0x180006405  push    rdi
0x180006406  sub     rsp, 20h
0x18000640a  mov     edi, edx
0x18000640c  mov     rbx, rcx
0x18000640f  test    edx, edx
0x180006411  jz      short loc_18000643C
0x180006413  inc     dword ptr [rcx+10h]
0x180006416  mov     ecx, edi
0x180006418  mov     rax, [rbx+18h]
0x18000641c  mov     [rsp+28h+arg_0], rbp
0x180006421  mov     [rsp+28h+arg_8], rsi
0x180006426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000642b  mov     rsi, rax
0x18000642e  test    rax, rax
0x180006431  jnz     short loc_180006449
0x180006433  mov     rcx, rbx
0x180006436  call    NoMoreMemory
0x18000643c  xor     eax, eax
0x18000643e  mov     rbx, [rsp+28h+arg_10]
0x180006443  add     rsp, 20h
0x180006447  pop     rdi
0x180006448  retn
0x180006449  mov     ebp, [rbx+8]
0x18000644c  cmp     [rbx+0Ch], ebp
0x18000644f  jge     short loc_180006488
0x180006451  movsxd  rcx, dword ptr [rbx+0Ch]
0x180006455  mov     rax, [rbx]
0x180006458  add     rcx, rcx
0x18000645b  mov     rbp, [rsp+28h+arg_0]
0x180006460  mov     [rax+rcx*8], rsi
0x180006464  movsxd  rcx, dword ptr [rbx+0Ch]
0x180006468  mov     rax, [rbx]
0x18000646b  add     rcx, rcx
0x18000646e  mov     [rax+rcx*8+8], edi
0x180006472  mov     rax, rsi
0x180006475  inc     dword ptr [rbx+0Ch]
0x180006478  mov     rsi, [rsp+28h+arg_8]
0x18000647d  mov     rbx, [rsp+28h+arg_10]
0x180006482  add     rsp, 20h
0x180006486  pop     rdi
0x180006487  retn
0x180006488  mov     eax, ebp
0x18000648a  cdq
0x18000648b  and     edx, 3
0x18000648e  add     edx, eax
0x180006490  mov     rax, [rbx]
0x180006493  sar     edx, 2
0x180006496  sub     edx, 0FFFFFF80h
0x180006499  add     edx, ebp
0x18000649b  movsxd  rcx, edx
0x18000649e  shl     rcx, 4
0x1800064a2  mov     [rbx+8], edx
0x1800064a5  test    rax, rax
0x1800064a8  jz      short loc_1800064BB
0x1800064aa  mov     rdx, rcx
0x1800064ad  mov     rcx, rax
0x1800064b0  mov     rax, [rbx+20h]
0x1800064b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064b9  jmp     short loc_1800064C4
0x1800064bb  mov     rax, [rbx+18h]
0x1800064bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c4  mov     [rbx], rax
0x1800064c7  test    rax, rax
0x1800064ca  jz      loc_180006433
0x1800064d0  cmp     ebp, [rbx+8]
0x1800064d3  jge     loc_180006451
0x1800064d9  xor     edx, edx
0x1800064db  mov     rax, [rbx]
0x1800064de  movsxd  rcx, ebp
0x1800064e1  inc     ebp
0x1800064e3  add     rcx, rcx
0x1800064e6  mov     [rax+rcx*8], rdx
0x1800064ea  mov     rax, [rbx]
0x1800064ed  mov     [rax+rcx*8+8], edx
0x1800064f1  cmp     ebp, [rbx+8]
0x1800064f4  jl      short loc_1800064DB
0x1800064f6  jmp     loc_180006451
```
