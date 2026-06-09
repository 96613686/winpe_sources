# DeleteInInterfaceRefs

- ea: `0x18001b9ac`
- end: `0x18001ba27`
- name: `DeleteInInterfaceRefs`
- size: `123`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180014580`
- `0x18001bce0`
- `0x18001be6c`

## callees

- `0x18001b9ac`
- `0x18001decc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001ba0d`
- `KERNEL32!HeapFree` at `0x18001ba0d`

## pseudocode

```c
void __fastcall DeleteInInterfaceRefs(void **a1, __int64 a2)
{
  void *v3; // rbx
  void **v4; // rax
  int v5; // [rsp+20h] [rbp-28h]

  while ( 1 )
  {
    v3 = *a1;
    if ( *a1 == a1 )
      break;
    if ( *((void ***)v3 + 1) != a1 || (v4 = *(void ***)v3, *(void **)(*(_QWORD *)v3 + 8LL) != v3) )
      __fastfail(3u);
    *a1 = v4;
    v4[1] = a1;
    LookupAndDeleteYourMfe(*((_DWORD *)v3 + 6), a2, *((_DWORD *)v3 + 4), *((_DWORD *)v3 + 5), v5, 0, 0, 0);
    HeapFree(hHeap, 0, v3);
  }
}

```

## disassembly

```asm
0x18001b9ac  mov     [rsp+arg_0], rbx
0x18001b9b1  push    rdi
0x18001b9b2  sub     rsp, 40h
0x18001b9b6  mov     rdi, rcx
0x18001b9b9  mov     rbx, [rdi]
0x18001b9bc  cmp     rbx, rdi
0x18001b9bf  jz      short loc_18001BA1C
0x18001b9c1  cmp     [rbx+8], rdi
0x18001b9c5  jnz     short loc_18001BA15
0x18001b9c7  mov     rax, [rbx]
0x18001b9ca  cmp     [rax+8], rbx
0x18001b9ce  jnz     short loc_18001BA15
0x18001b9d0  mov     [rdi], rax
0x18001b9d3  mov     [rax+8], rdi
0x18001b9d7  mov     r9d, [rbx+14h]
0x18001b9db  mov     r8d, [rbx+10h]
0x18001b9df  mov     ecx, [rbx+18h]
0x18001b9e2  mov     [rsp+48h+var_10], 0
0x18001b9ea  mov     [rsp+48h+var_18], 0
0x18001b9f3  mov     [rsp+48h+var_20], 0
0x18001b9fc  call    LookupAndDeleteYourMfe
0x18001ba01  mov     rcx, cs:hHeap; hHeap
0x18001ba08  mov     r8, rbx; lpMem
0x18001ba0b  xor     edx, edx; dwFlags
0x18001ba0d  call    cs:__imp_HeapFree
0x18001ba13  jmp     short loc_18001B9B9
0x18001ba15  mov     ecx, 3
0x18001ba1a  int     29h; Win8: RtlFailFast(ecx)
0x18001ba1c  mov     rbx, [rsp+48h+arg_0]
0x18001ba21  add     rsp, 40h
0x18001ba25  pop     rdi
0x18001ba26  retn
```
