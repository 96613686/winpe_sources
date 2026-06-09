# CRegSetting::~CRegSetting(void)

- ea: `0x140004b90`
- end: `0x140004beb`
- name: `??1CRegSetting@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(CRegSetting *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x140003224`
- `0x140004b90`

## pseudocode

```c
void __fastcall CRegSetting::~CRegSetting(CRegSetting *this)
{
  char *v2; // rcx
  char *v3; // rcx
  void *v4; // rcx

  v2 = (char *)*((_QWORD *)this + 8);
  if ( v2 != (char *)this + 80 )
    operator delete(v2, (const struct std::nothrow_t *)&std::nothrow);
  v3 = (char *)*((_QWORD *)this + 4);
  if ( v3 != (char *)this + 48 )
    operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 != (void *)-1LL )
  {
    *((_QWORD *)this + 2) = v4;
    operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
  }
}

```

## disassembly

```asm
0x140004b90  push    rbx
0x140004b92  sub     rsp, 20h
0x140004b96  mov     rbx, rcx
0x140004b99  mov     rcx, [rcx+40h]; void *
0x140004b9d  lea     rax, [rbx+50h]
0x140004ba1  cmp     rcx, rax
0x140004ba4  jz      short loc_140004BB2
0x140004ba6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140004bad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004bb2  mov     rcx, [rbx+20h]; void *
0x140004bb6  lea     rax, [rbx+30h]
0x140004bba  cmp     rcx, rax
0x140004bbd  jz      short loc_140004BCB
0x140004bbf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140004bc6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004bcb  mov     rcx, [rbx+8]; void *
0x140004bcf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140004bd3  jz      short loc_140004BE5
0x140004bd5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140004bdc  mov     [rbx+10h], rcx
0x140004be0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004be5  add     rsp, 20h
0x140004be9  pop     rbx
0x140004bea  retn
```
