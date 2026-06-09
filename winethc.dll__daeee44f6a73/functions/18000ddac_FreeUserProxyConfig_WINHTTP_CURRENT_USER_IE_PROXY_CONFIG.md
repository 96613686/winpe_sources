# FreeUserProxyConfig(_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)

- ea: `0x18000ddac`
- end: `0x18000de10`
- name: `?FreeUserProxyConfig@@YAXPEAU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z`
- size: `100`
- prototype: `void __fastcall(struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002f7c`
- `0x18000d160`

## callees

- `0x18000ddac`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18000ddc2`
- `KERNEL32!GlobalFree` at `0x18000ddd7`
- `KERNEL32!GlobalFree` at `0x18000ddec`
- `KERNEL32!GlobalFree` at `0x18000ddc2`
- `KERNEL32!GlobalFree` at `0x18000ddd7`
- `KERNEL32!GlobalFree` at `0x18000ddec`

## pseudocode

```c
void __fastcall FreeUserProxyConfig(struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *a1)
{
  struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rax

  if ( a1 )
  {
    v1 = a1;
    v2 = (void *)*((_QWORD *)a1 + 1);
    if ( v2 )
      GlobalFree(v2);
    v3 = (void *)*((_QWORD *)v1 + 2);
    if ( v3 )
      GlobalFree(v3);
    v4 = (void *)*((_QWORD *)v1 + 3);
    if ( v4 )
      GlobalFree(v4);
    v5 = 32;
    do
    {
      *(_BYTE *)v1 = 0;
      v1 = (struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)((char *)v1 + 1);
      --v5;
    }
    while ( v5 );
  }
}

```

## disassembly

```asm
0x18000ddac  test    rcx, rcx
0x18000ddaf  jz      short locret_18000DE0E
0x18000ddb1  push    rbx
0x18000ddb2  sub     rsp, 20h
0x18000ddb6  mov     rbx, rcx
0x18000ddb9  mov     rcx, [rcx+8]; hMem
0x18000ddbd  test    rcx, rcx
0x18000ddc0  jz      short loc_18000DDCE
0x18000ddc2  call    cs:__imp_GlobalFree
0x18000ddc9  nop     dword ptr [rax+rax+00h]
0x18000ddce  mov     rcx, [rbx+10h]; hMem
0x18000ddd2  test    rcx, rcx
0x18000ddd5  jz      short loc_18000DDE3
0x18000ddd7  call    cs:__imp_GlobalFree
0x18000ddde  nop     dword ptr [rax+rax+00h]
0x18000dde3  mov     rcx, [rbx+18h]; hMem
0x18000dde7  test    rcx, rcx
0x18000ddea  jz      short loc_18000DDF8
0x18000ddec  call    cs:__imp_GlobalFree
0x18000ddf3  nop     dword ptr [rax+rax+00h]
0x18000ddf8  mov     eax, 20h ; ' '
0x18000ddfd  mov     byte ptr [rbx], 0
0x18000de00  inc     rbx
0x18000de03  sub     rax, 1
0x18000de07  jnz     short loc_18000DDFD
0x18000de09  add     rsp, 20h
0x18000de0d  pop     rbx
0x18000de0e  retn
```
