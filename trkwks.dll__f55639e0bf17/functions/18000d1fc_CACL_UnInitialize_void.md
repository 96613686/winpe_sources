# CACL::UnInitialize(void)

- ea: `0x18000d1fc`
- end: `0x18000d222`
- name: `?UnInitialize@CACL@@QEAAXXZ`
- size: `38`
- prototype: `void __fastcall(CACL *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000d1d0`
- `0x18000d228`

## callees

- `0x18000d1fc`
- `0x18000db28`

## pseudocode

```c
void __fastcall CACL::UnInitialize(CACL *this)
{
  void *v2; // rcx

  if ( (*((_BYTE *)this + 12) & 1) != 0 )
  {
    v2 = *(void **)this;
    if ( v2 )
      operator delete(v2);
    *((_DWORD *)this + 3) &= ~1u;
  }
}

```

## disassembly

```asm
0x18000d1fc  push    rbx
0x18000d1fe  sub     rsp, 20h
0x18000d202  test    byte ptr [rcx+0Ch], 1
0x18000d206  mov     rbx, rcx
0x18000d209  jz      short loc_18000D21C
0x18000d20b  mov     rcx, [rcx]; Block
0x18000d20e  test    rcx, rcx
0x18000d211  jz      short loc_18000D218
0x18000d213  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d218  and     dword ptr [rbx+0Ch], 0FFFFFFFEh
0x18000d21c  add     rsp, 20h
0x18000d220  pop     rbx
0x18000d221  retn
```
