# BinXmlVariantHolder::Clear(void)

- ea: `0x18000b6a0`
- end: `0x18000b75c`
- name: `?Clear@BinXmlVariantHolder@@QEAAXXZ`
- size: `188`
- prototype: `void __fastcall(BinXmlVariantHolder *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180007ae4`
- `0x18000a938`
- `0x18000ab80`
- `0x18000b638`
- `0x180012420`
- `0x180019700`
- `0x18001992c`
- `0x18003026c`

## callees

- `0x18000a0d0`
- `0x18000b6a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b6ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b6ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b6f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b6f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b6df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b6df`

## pseudocode

```c
void __fastcall BinXmlVariantHolder::Clear(void **this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax

  switch ( *((_DWORD *)this + 3) )
  {
    case 1:
    case 2:
    case 0xE:
      v2 = *this;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
      break;
    case 0xF:
    case 0x12:
      operator delete(*this);
      break;
    case 0x13:
      LocalFree(*this);
      break;
    default:
      break;
  }
  *((_DWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18000b6a0  mov     [rsp+arg_0], rbx
0x18000b6a5  push    rdi
0x18000b6a6  sub     rsp, 20h
0x18000b6aa  mov     eax, [rcx+0Ch]
0x18000b6ad  mov     rbx, rcx
0x18000b6b0  dec     eax; switch 19 cases
0x18000b6b2  cmp     eax, 12h
0x18000b6b5  jbe     short loc_18000B6C9
0x18000b6b7  mov     dword ptr [rbx+0Ch], 0; jumptable 000000018000B6DA default case, cases 3-13,16,17
0x18000b6be  mov     rbx, [rsp+28h+arg_0]
0x18000b6c3  add     rsp, 20h
0x18000b6c7  pop     rdi
0x18000b6c8  retn
0x18000b6c9  lea     rcx, __ImageBase
0x18000b6d0  mov     eax, ds:(jpt_18000B6DA - 180000000h)[rcx+rax*4]
0x18000b6d7  add     rax, rcx
0x18000b6da  jmp     rax; switch jump
0x18000b6dc  mov     rcx, [rbx]; jumptable 000000018000B6DA case 19
0x18000b6df  call    cs:__imp_LocalFree
0x18000b6e5  jmp     short def_18000B6DA; jumptable 000000018000B6DA default case, cases 3-13,16,17
0x18000b6e7  mov     rdi, [rbx]; jumptable 000000018000B6DA cases 1,2,14
0x18000b6ea  call    cs:__imp_GetProcessHeap
0x18000b6f0  mov     r8, rdi; lpMem
0x18000b6f3  xor     edx, edx; dwFlags
0x18000b6f5  mov     rcx, rax; hHeap
0x18000b6f8  call    cs:__imp_HeapFree
0x18000b6fe  jmp     short def_18000B6DA; jumptable 000000018000B6DA default case, cases 3-13,16,17
0x18000b700  mov     rcx, [rbx]; jumptable 000000018000B6DA cases 15,18
0x18000b703  mov     edx, 10h; unsigned __int64
0x18000b708  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b70d  jmp     short def_18000B6DA; jumptable 000000018000B6DA default case, cases 3-13,16,17
```
