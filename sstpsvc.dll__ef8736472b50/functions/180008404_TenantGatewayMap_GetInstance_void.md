# TenantGatewayMap::GetInstance(void)

- ea: `0x180008404`
- end: `0x18000844b`
- name: `?GetInstance@TenantGatewayMap@@SAPEAV1@XZ`
- size: `71`
- prototype: `struct TenantGatewayMap *(void)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1800056e0`
- `0x180010d80`
- `0x1800111f4`
- `0x1800142b8`
- `0x180014484`
- `0x180014900`
- `0x1800151e0`
- `0x180015500`
- `0x1800158c0`

## callees

- `0x180008404`
- `0x180008f6c`
- `0x18001072c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct TenantGatewayMap *TenantGatewayMap::GetInstance(void)
{
  struct TenantGatewayMap *result; // rax

  if ( TenantGatewayMap::fInitialized )
    return TenantGatewayMap::pInstance;
  result = (struct TenantGatewayMap *)operator new(0x68u);
  if ( result )
    result = (struct TenantGatewayMap *)TenantGatewayMap::TenantGatewayMap((WCHAR *)result);
  TenantGatewayMap::pInstance = result;
  TenantGatewayMap::fInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x180008404  sub     rsp, 28h
0x180008408  cmp     cs:?fInitialized@TenantGatewayMap@@0_NA, 0; bool TenantGatewayMap::fInitialized
0x18000840f  jnz     short loc_18000843E
0x180008411  mov     ecx, 68h ; 'h'; Size
0x180008416  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000841b  mov     [rsp+28h+arg_0], rax
0x180008420  test    rax, rax
0x180008423  jz      short loc_18000842E
0x180008425  mov     rcx, rax; SRWLock
0x180008428  call    ??0TenantGatewayMap@@AEAA@XZ; TenantGatewayMap::TenantGatewayMap(void)
0x18000842d  nop
0x18000842e  mov     cs:?pInstance@TenantGatewayMap@@0PEAV1@EA, rax; TenantGatewayMap * TenantGatewayMap::pInstance
0x180008435  mov     cs:?fInitialized@TenantGatewayMap@@0_NA, 1; bool TenantGatewayMap::fInitialized
0x18000843c  jmp     short loc_180008445
0x18000843e  mov     rax, cs:?pInstance@TenantGatewayMap@@0PEAV1@EA; TenantGatewayMap * TenantGatewayMap::pInstance
0x180008445  add     rsp, 28h
0x180008449  retn
```
