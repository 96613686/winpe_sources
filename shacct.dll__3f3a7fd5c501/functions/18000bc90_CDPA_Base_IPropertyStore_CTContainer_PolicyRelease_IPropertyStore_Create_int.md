# CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::Create(int)

- ea: `0x18000bc90`
- end: `0x18000bcb8`
- name: `?Create@?$CDPA_Base@UIPropertyStore@@V?$CTContainer_PolicyRelease@UIPropertyStore@@@@@@QEAAHH@Z`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007cb0`
- `0x180009900`
- `0x18000e3a0`
- `0x1800145c4`
- `0x180014b50`

## callees

- `0x180008c10`

## pseudocode

```c
_BOOL8 __fastcall CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::Create(HDPA *a1)
{
  HDPA v2; // rax

  v2 = g_pfn_DPA_Create(5);
  *a1 = v2;
  return v2 != 0;
}

```

## disassembly

```asm
0x18000bc90  push    rbx
0x18000bc92  sub     rsp, 20h
0x18000bc96  mov     rbx, rcx
0x18000bc99  mov     ecx, 5; cItemGrow
0x18000bc9e  call    cs:g_pfn_DPA_Create
0x18000bca4  mov     rdx, rax
0x18000bca7  mov     [rbx], rax
0x18000bcaa  xor     eax, eax
0x18000bcac  test    rdx, rdx
0x18000bcaf  setnz   al
0x18000bcb2  add     rsp, 20h
0x18000bcb6  pop     rbx
0x18000bcb7  retn
```
