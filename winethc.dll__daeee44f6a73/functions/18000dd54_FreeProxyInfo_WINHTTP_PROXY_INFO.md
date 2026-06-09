# FreeProxyInfo(_WINHTTP_PROXY_INFO *)

- ea: `0x18000dd54`
- end: `0x18000dda3`
- name: `?FreeProxyInfo@@YAXPEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `79`
- prototype: `void __fastcall(struct _WINHTTP_PROXY_INFO *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f7c`
- `0x180008ec0`
- `0x18000d160`

## callees

- `0x18000dd54`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18000dd6a`
- `KERNEL32!GlobalFree` at `0x18000dd7f`
- `KERNEL32!GlobalFree` at `0x18000dd6a`
- `KERNEL32!GlobalFree` at `0x18000dd7f`

## pseudocode

```c
void __fastcall FreeProxyInfo(struct _WINHTTP_PROXY_INFO *a1)
{
  struct _WINHTTP_PROXY_INFO *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rax

  if ( a1 )
  {
    v1 = a1;
    v2 = (void *)*((_QWORD *)a1 + 1);
    if ( v2 )
      GlobalFree(v2);
    v3 = (void *)*((_QWORD *)v1 + 2);
    if ( v3 )
      GlobalFree(v3);
    v4 = 24;
    do
    {
      *(_BYTE *)v1 = 0;
      v1 = (struct _WINHTTP_PROXY_INFO *)((char *)v1 + 1);
      --v4;
    }
    while ( v4 );
  }
}

```

## disassembly

```asm
0x18000dd54  test    rcx, rcx
0x18000dd57  jz      short locret_18000DDA1
0x18000dd59  push    rbx
0x18000dd5a  sub     rsp, 20h
0x18000dd5e  mov     rbx, rcx
0x18000dd61  mov     rcx, [rcx+8]; hMem
0x18000dd65  test    rcx, rcx
0x18000dd68  jz      short loc_18000DD76
0x18000dd6a  call    cs:__imp_GlobalFree
0x18000dd71  nop     dword ptr [rax+rax+00h]
0x18000dd76  mov     rcx, [rbx+10h]; hMem
0x18000dd7a  test    rcx, rcx
0x18000dd7d  jz      short loc_18000DD8B
0x18000dd7f  call    cs:__imp_GlobalFree
0x18000dd86  nop     dword ptr [rax+rax+00h]
0x18000dd8b  mov     eax, 18h
0x18000dd90  mov     byte ptr [rbx], 0
0x18000dd93  inc     rbx
0x18000dd96  sub     rax, 1
0x18000dd9a  jnz     short loc_18000DD90
0x18000dd9c  add     rsp, 20h
0x18000dda0  pop     rbx
0x18000dda1  retn
```
