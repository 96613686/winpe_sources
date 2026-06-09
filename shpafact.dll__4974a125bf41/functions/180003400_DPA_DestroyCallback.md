# DPA_DestroyCallback

- ea: `0x180003400`
- end: `0x180003452`
- name: `DPA_DestroyCallback`
- size: `82`
- prototype: `void __stdcall(HDPA hdpa, PFNDAENUMCALLBACK pfnCB, void *pData)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001b6c`

## callees

- `0x180003384`
- `0x180003400`
- `0x180004010`

## pseudocode

```c
void __stdcall DPA_DestroyCallback(HDPA hdpa, PFNDAENUMCALLBACK pfnCB, void *pData)
{
  int i; // edi

  if ( hdpa )
  {
    if ( pfnCB )
    {
      for ( i = 0; i < *(_DWORD *)hdpa; ++i )
      {
        if ( !((unsigned int (__fastcall *)(_QWORD, void *))pfnCB)(*(_QWORD *)(*((_QWORD *)hdpa + 1) + 8LL * i), pData) )
          break;
      }
    }
  }
  DPA_Destroy(hdpa);
}

```

## disassembly

```asm
0x180003400  push    rbx
0x180003402  push    rbp
0x180003403  push    rsi
0x180003404  push    rdi
0x180003405  sub     rsp, 28h
0x180003409  mov     rbp, r8
0x18000340c  mov     rsi, rdx
0x18000340f  mov     rbx, rcx
0x180003412  test    rcx, rcx
0x180003415  jz      short loc_180003442
0x180003417  test    rdx, rdx
0x18000341a  jz      short loc_180003442
0x18000341c  xor     edi, edi
0x18000341e  cmp     [rcx], edi
0x180003420  jle     short loc_180003442
0x180003422  mov     rcx, [rbx+8]
0x180003426  mov     rdx, rbp
0x180003429  movsxd  rax, edi
0x18000342c  mov     rcx, [rcx+rax*8]
0x180003430  mov     rax, rsi
0x180003433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003438  test    eax, eax
0x18000343a  jz      short loc_180003442
0x18000343c  inc     edi
0x18000343e  cmp     edi, [rbx]
0x180003440  jl      short loc_180003422
0x180003442  mov     rcx, rbx
0x180003445  add     rsp, 28h
0x180003449  pop     rdi
0x18000344a  pop     rsi
0x18000344b  pop     rbp
0x18000344c  pop     rbx
0x18000344d  jmp     DPA_Destroy
```
