# DPA_DestroyCallback

- ea: `0x18000bbd0`
- end: `0x18000bc22`
- name: `DPA_DestroyCallback`
- size: `82`
- prototype: `void __stdcall(HDPA hdpa, PFNDAENUMCALLBACK pfnCB, void *pData)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180005e60`
- `0x180008a60`
- `0x18000bd50`
- `0x18000d934`
- `0x18000da74`
- `0x18000dd44`
- `0x18000dd8c`
- `0x180014d90`

## callees

- `0x180009a50`
- `0x18000bbd0`
- `0x180017010`

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
0x18000bbd0  push    rbx
0x18000bbd2  push    rbp
0x18000bbd3  push    rsi
0x18000bbd4  push    rdi
0x18000bbd5  sub     rsp, 28h
0x18000bbd9  mov     rbp, r8
0x18000bbdc  mov     rsi, rdx
0x18000bbdf  mov     rbx, rcx
0x18000bbe2  test    rcx, rcx
0x18000bbe5  jz      short loc_18000BC12
0x18000bbe7  test    rdx, rdx
0x18000bbea  jz      short loc_18000BC12
0x18000bbec  xor     edi, edi
0x18000bbee  cmp     [rcx], edi
0x18000bbf0  jle     short loc_18000BC12
0x18000bbf2  mov     rcx, [rbx+8]
0x18000bbf6  mov     rdx, rbp
0x18000bbf9  movsxd  rax, edi
0x18000bbfc  mov     rcx, [rcx+rax*8]
0x18000bc00  mov     rax, rsi
0x18000bc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc08  test    eax, eax
0x18000bc0a  jz      short loc_18000BC12
0x18000bc0c  inc     edi
0x18000bc0e  cmp     edi, [rbx]
0x18000bc10  jl      short loc_18000BBF2
0x18000bc12  mov     rcx, rbx
0x18000bc15  add     rsp, 28h
0x18000bc19  pop     rdi
0x18000bc1a  pop     rsi
0x18000bc1b  pop     rbp
0x18000bc1c  pop     rbx
0x18000bc1d  jmp     DPA_Destroy
```
