# CPropertyName::Empty(void)

- ea: `0x180009f40`
- end: `0x180009fbd`
- name: `?Empty@CPropertyName@@QEAAXXZ`
- size: `125`
- prototype: `void __fastcall(CPropertyName *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800087b0`
- `0x180009950`
- `0x1800099b0`
- `0x180009c40`
- `0x18000ab60`
- `0x18000ae40`

## callees

- `0x180009f40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009fb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009fb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f89`

## pseudocode

```c
void __fastcall CPropertyName::Empty(CPropertyName *this)
{
  int i; // edi
  __int64 v3; // rax
  void *v4; // r8

  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; i < *(_DWORD *)this; ++i )
    {
      v3 = *((_QWORD *)this + 1);
      if ( !*(_WORD *)(v3 + 16LL * i) )
        CoTaskMemFree(*(LPVOID *)(v3 + 16LL * i + 8));
    }
    if ( hHeap )
    {
      v4 = (void *)*((_QWORD *)this + 1);
      if ( v4 )
        HeapFree(hHeap, 0, v4);
    }
    *((_QWORD *)this + 1) = 0;
  }
  *(_DWORD *)this = 0;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180009f40  mov     [rsp+arg_8], rbx
0x180009f45  push    rsi
0x180009f46  sub     rsp, 20h
0x180009f4a  xor     esi, esi
0x180009f4c  mov     rbx, rcx
0x180009f4f  cmp     [rcx+8], rsi
0x180009f53  jnz     short loc_180009F69
0x180009f55  mov     [rbx], esi
0x180009f57  mov     [rbx+10h], esi
0x180009f5a  mov     [rbx+18h], rsi
0x180009f5e  mov     rbx, [rsp+28h+arg_8]
0x180009f63  add     rsp, 20h
0x180009f67  pop     rsi
0x180009f68  retn
0x180009f69  mov     [rsp+28h+arg_0], rdi
0x180009f6e  mov     edi, esi
0x180009f70  cmp     [rcx], esi
0x180009f72  jle     short loc_180009F95
0x180009f74  mov     rax, [rbx+8]
0x180009f78  movsxd  rcx, edi
0x180009f7b  add     rcx, rcx
0x180009f7e  cmp     [rax+rcx*8], si
0x180009f82  jnz     short loc_180009F8F
0x180009f84  mov     rcx, [rax+rcx*8+8]; pv
0x180009f89  call    cs:__imp_CoTaskMemFree
0x180009f8f  inc     edi
0x180009f91  cmp     edi, [rbx]
0x180009f93  jl      short loc_180009F74
0x180009f95  mov     rcx, cs:hHeap; hHeap
0x180009f9c  mov     rdi, [rsp+28h+arg_0]
0x180009fa1  test    rcx, rcx
0x180009fa4  jz      short loc_180009FB7
0x180009fa6  mov     r8, [rbx+8]; lpMem
0x180009faa  test    r8, r8
0x180009fad  jz      short loc_180009FB7
0x180009faf  xor     edx, edx; dwFlags
0x180009fb1  call    cs:__imp_HeapFree
0x180009fb7  mov     [rbx+8], rsi
0x180009fbb  jmp     short loc_180009F55
```
