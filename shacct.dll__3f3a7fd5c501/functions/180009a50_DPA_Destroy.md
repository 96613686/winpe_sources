# DPA_Destroy

- ea: `0x180009a50`
- end: `0x180009aa4`
- name: `DPA_Destroy`
- size: `84`
- prototype: `BOOL __stdcall(HDPA hdpa)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180008a60`
- `0x18000bbd0`
- `0x18000bd50`
- `0x18000d934`
- `0x18000dd44`

## callees

- `0x180009a50`
- `0x180016bd0`

## pseudocode

```c
BOOL __stdcall DPA_Destroy(HDPA hdpa)
{
  void *v3; // rdx

  if ( !hdpa )
    return 1;
  v3 = (void *)*((_QWORD *)hdpa + 1);
  return (!v3 || CCv6s_HeapFree(*((void **)hdpa + 2), v3) >= 0) && CCv6s_HeapFree(*((void **)hdpa + 2), hdpa) >= 0;
}

```

## disassembly

```asm
0x180009a50  push    rbx
0x180009a52  sub     rsp, 20h
0x180009a56  mov     rbx, rcx
0x180009a59  test    rcx, rcx
0x180009a5c  jnz     short loc_180009A69
0x180009a5e  mov     eax, 1
0x180009a63  add     rsp, 20h
0x180009a67  pop     rbx
0x180009a68  retn
0x180009a69  mov     rdx, [rcx+8]; void *
0x180009a6d  mov     [rsp+28h+arg_0], rdi
0x180009a72  test    rdx, rdx
0x180009a75  jz      short loc_180009A88
0x180009a77  mov     rcx, [rcx+10h]; void *
0x180009a7b  call    ?CCv6s_HeapFree@@YAJPEAX0@Z; CCv6s_HeapFree(void *,void *)
0x180009a80  test    eax, eax
0x180009a82  jns     short loc_180009A88
0x180009a84  xor     eax, eax
0x180009a86  jmp     short loc_180009A99
0x180009a88  mov     rcx, [rbx+10h]; void *
0x180009a8c  mov     rdx, rbx; void *
0x180009a8f  call    ?CCv6s_HeapFree@@YAJPEAX0@Z; CCv6s_HeapFree(void *,void *)
0x180009a94  not     eax
0x180009a96  shr     eax, 1Fh
0x180009a99  mov     rdi, [rsp+28h+arg_0]
0x180009a9e  add     rsp, 20h
0x180009aa2  pop     rbx
0x180009aa3  retn
```
