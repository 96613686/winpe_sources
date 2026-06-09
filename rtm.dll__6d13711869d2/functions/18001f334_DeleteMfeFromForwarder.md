# DeleteMfeFromForwarder

- ea: `0x18001f334`
- end: `0x18001f46d`
- name: `DeleteMfeFromForwarder`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001decc`

## callees

- `0x18001f334`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001f383`
- `KERNEL32!HeapAlloc` at `0x18001f383`
- `KERNEL32!HeapFree` at `0x18001f442`
- `KERNEL32!HeapFree` at `0x18001f442`
- `rtutils!RouterLogEventA` at `0x18001f401`
- `rtutils!RouterLogEventA` at `0x18001f401`

## string_xrefs

- `0x18001f3a3`: `DeleteMfeFromForwarder : Failed to create MFE of size : %x`

## pseudocode

```c
void __fastcall DeleteMfeFromForwarder(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rax
  void *v5; // rbx
  int v6; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v7[2044]; // [rsp+34h] [rbp-814h] BYREF

  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  v4 = HeapAlloc(hHeap, 0, 0xCu);
  v5 = v4;
  if ( v4 )
  {
    *v4 = 0;
    *((_DWORD *)v4 + 2) = 0;
    *(_DWORD *)v4 = *(_DWORD *)(a1 + 32);
    *((_DWORD *)v4 + 1) = *(_DWORD *)(a2 + 104);
    *((_DWORD *)v4 + 2) = *(_DWORD *)(a2 + 108);
    if ( qword_18002B940 )
      qword_18002B940(v4);
    HeapFree(hHeap, 0, v5);
  }
  else
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(&v6, L"DeleteMfeFromForwarder : Failed to create MFE of size : %x", 12);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v6);
    }
    if ( dword_18002BA54 )
      RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
  }
}

```

## disassembly

```asm
0x18001f334  mov     [rsp+arg_0], rbx
0x18001f339  mov     [rsp+arg_8], rsi
0x18001f33e  push    rdi
0x18001f33f  sub     rsp, 840h
0x18001f346  mov     rax, cs:__security_cookie
0x18001f34d  xor     rax, rsp
0x18001f350  mov     [rsp+848h+var_18], rax
0x18001f358  mov     rdi, rdx
0x18001f35b  mov     rsi, rcx
0x18001f35e  xor     eax, eax
0x18001f360  lea     rcx, [rsp+848h+var_814]; void *
0x18001f365  xor     edx, edx; Val
0x18001f367  mov     [rsp+848h+var_818], eax
0x18001f36b  mov     r8d, 7FCh; Size
0x18001f371  call    memset_0
0x18001f376  mov     rcx, cs:hHeap; hHeap
0x18001f37d  xor     edx, edx; dwFlags
0x18001f37f  lea     r8d, [rdx+0Ch]; dwBytes
0x18001f383  call    cs:__imp_HeapAlloc
0x18001f389  mov     rbx, rax
0x18001f38c  test    rax, rax
0x18001f38f  jnz     short loc_18001F409
0x18001f391  cmp     cs:qword_18002B8A8, rax
0x18001f398  jz      short loc_18001F3D3
0x18001f39a  lea     r8d, [rax+0Ch]
0x18001f39e  mov     word ptr [rsp+848h+var_818], ax
0x18001f3a3  lea     rdx, aDeletemfefromf; "DeleteMfeFromForwarder : Failed to crea"...
0x18001f3aa  lea     rcx, [rsp+848h+var_818]
0x18001f3af  call    FormatRRASErrorString
0x18001f3b4  mov     rdx, cs:qword_18002B8A8
0x18001f3bb  lea     r8, [rsp+848h+var_818]
0x18001f3c0  mov     rcx, cs:gMgmEtwContext
0x18001f3c7  mov     rax, cs:gMgmTemplateFunc
0x18001f3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3d3  mov     edx, 1; dwEventType
0x18001f3d8  cmp     cs:dword_18002BA54, edx
0x18001f3de  jb      short loc_18001F448
0x18001f3e0  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001f3e7  xor     r9d, r9d; dwSubStringCount
0x18001f3ea  mov     [rsp+848h+dwErrorCode], 8; dwErrorCode
0x18001f3f2  mov     r8d, 0C353h; dwMessageId
0x18001f3f8  mov     [rsp+848h+plpszSubStringArray], 0; plpszSubStringArray
0x18001f401  call    cs:__imp_RouterLogEventA
0x18001f407  jmp     short loc_18001F448
0x18001f409  xor     eax, eax
0x18001f40b  mov     [rbx], rax
0x18001f40e  mov     [rbx+8], eax
0x18001f411  mov     eax, [rsi+20h]
0x18001f414  mov     [rbx], eax
0x18001f416  mov     eax, [rdi+68h]
0x18001f419  mov     [rbx+4], eax
0x18001f41c  mov     eax, [rdi+6Ch]
0x18001f41f  mov     [rbx+8], eax
0x18001f422  mov     rax, cs:qword_18002B940
0x18001f429  test    rax, rax
0x18001f42c  jz      short loc_18001F436
0x18001f42e  mov     rcx, rbx
0x18001f431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f436  mov     rcx, cs:hHeap; hHeap
0x18001f43d  mov     r8, rbx; lpMem
0x18001f440  xor     edx, edx; dwFlags
0x18001f442  call    cs:__imp_HeapFree
0x18001f448  mov     rcx, [rsp+848h+var_18]
0x18001f450  xor     rcx, rsp; StackCookie
0x18001f453  call    __security_check_cookie
0x18001f458  lea     r11, [rsp+848h+var_8]
0x18001f460  mov     rbx, [r11+10h]
0x18001f464  mov     rsi, [r11+18h]
0x18001f468  mov     rsp, r11
0x18001f46b  pop     rdi
0x18001f46c  retn
```
