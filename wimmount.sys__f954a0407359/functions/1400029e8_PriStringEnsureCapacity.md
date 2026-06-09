# PriStringEnsureCapacity

- ea: `0x1400029e8`
- end: `0x140002a71`
- name: `PriStringEnsureCapacity`
- size: `137`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000223c`
- `0x140002950`

## callees

- `0x1400029e8`
- `0x140002d00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002a4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a4a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002a13`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002a13`

## pseudocode

```c
__int64 __fastcall PriStringEnsureCapacity(unsigned __int16 *a1, unsigned int a2)
{
  unsigned int v2; // esi
  unsigned __int16 v3; // di
  PVOID PoolWithTag; // rax
  PVOID v6; // rbp
  const void *v7; // rdx
  void *v8; // rcx

  v2 = 0;
  v3 = a2;
  if ( a2 >= a1[1] && a2 <= 0xFFFF )
  {
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, a2, 0x574D6365u);
    v6 = PoolWithTag;
    if ( PoolWithTag )
    {
      v7 = (const void *)*((_QWORD *)a1 + 1);
      if ( v7 )
      {
        memmove(PoolWithTag, v7, *a1);
        v8 = (void *)*((_QWORD *)a1 + 1);
        if ( v8 )
          ExFreePoolWithTag(v8, 0x574D6365u);
      }
      *((_QWORD *)a1 + 1) = v6;
      a1[1] = v3;
    }
    else
    {
      return (unsigned int)-1073741789;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400029e8  push    rbx
0x1400029ea  push    rbp
0x1400029eb  push    rsi
0x1400029ec  push    rdi
0x1400029ed  sub     rsp, 28h
0x1400029f1  movzx   eax, word ptr [rcx+2]
0x1400029f5  xor     esi, esi
0x1400029f7  mov     edi, edx
0x1400029f9  mov     rbx, rcx
0x1400029fc  cmp     edx, eax
0x1400029fe  jb      short loc_140002A65
0x140002a00  cmp     edi, 0FFFFh
0x140002a06  ja      short loc_140002A65
0x140002a08  mov     edx, edi; NumberOfBytes
0x140002a0a  lea     ecx, [rsi+1]; PoolType
0x140002a0d  mov     r8d, 574D6365h; Tag
0x140002a13  call    cs:__imp_ExAllocatePoolWithTag
0x140002a1a  nop     dword ptr [rax+rax+00h]
0x140002a1f  mov     rbp, rax
0x140002a22  test    rax, rax
0x140002a25  jz      short loc_140002A60
0x140002a27  mov     rdx, [rbx+8]; Src
0x140002a2b  test    rdx, rdx
0x140002a2e  jz      short loc_140002A56
0x140002a30  movzx   r8d, word ptr [rbx]; Size
0x140002a34  mov     rcx, rax; void *
0x140002a37  call    memmove
0x140002a3c  mov     rcx, [rbx+8]; P
0x140002a40  test    rcx, rcx
0x140002a43  jz      short loc_140002A56
0x140002a45  mov     edx, 574D6365h; Tag
0x140002a4a  call    cs:__imp_ExFreePoolWithTag
0x140002a51  nop     dword ptr [rax+rax+00h]
0x140002a56  mov     [rbx+8], rbp
0x140002a5a  mov     [rbx+2], di
0x140002a5e  jmp     short loc_140002A65
0x140002a60  mov     esi, 0C0000023h
0x140002a65  mov     eax, esi
0x140002a67  add     rsp, 28h
0x140002a6b  pop     rdi
0x140002a6c  pop     rsi
0x140002a6d  pop     rbp
0x140002a6e  pop     rbx
0x140002a6f  retn
```
