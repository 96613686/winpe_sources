# OFFLINE_REGISTRY_KEY::~OFFLINE_REGISTRY_KEY(void)

- ea: `0x180002758`
- end: `0x18000278e`
- name: `??1OFFLINE_REGISTRY_KEY@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(OFFLINE_REGISTRY_KEY *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180002694`

## callees

- `0x180001de0`
- `0x180002758`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000276a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000276a`

## pseudocode

```c
void __fastcall OFFLINE_REGISTRY_KEY::~OFFLINE_REGISTRY_KEY(OFFLINE_REGISTRY_KEY *this)
{
  HKEY v2; // rcx
  __int64 v3; // rcx

  v2 = (HKEY)*((_QWORD *)this + 2);
  if ( v2 )
    RegCloseKey(v2);
  v3 = *(_QWORD *)this;
  *((_DWORD *)this + 2) = 0;
  if ( v3 )
    operator delete((void *)(v3 - 8));
}

```

## disassembly

```asm
0x180002758  push    rbx
0x18000275a  sub     rsp, 20h
0x18000275e  mov     rbx, rcx
0x180002761  mov     rcx, [rcx+10h]; hKey
0x180002765  test    rcx, rcx
0x180002768  jz      short loc_180002770
0x18000276a  call    cs:__imp_RegCloseKey
0x180002770  mov     rcx, [rbx]
0x180002773  mov     dword ptr [rbx+8], 0
0x18000277a  test    rcx, rcx
0x18000277d  jz      short loc_180002788
0x18000277f  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180002783  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002788  add     rsp, 20h
0x18000278c  pop     rbx
0x18000278d  retn
```
