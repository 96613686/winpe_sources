# SLGenerateOfflineInstallationId

- ea: `0x1800113e0`
- end: `0x18001140e`
- name: `SLGenerateOfflineInstallationId`
- size: `46`
- prototype: `HRESULT __stdcall(HSLC hSLC, const SLID *pProductSkuId, PWSTR *ppwszInstallationId)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180001430`
- `0x180011420`

## pseudocode

```c
HRESULT __stdcall SLGenerateOfflineInstallationId(HSLC hSLC, const SLID *pProductSkuId, PWSTR *ppwszInstallationId)
{
  HRESULT v3; // ebx

  v3 = SLGenerateOfflineInstallationIdEx(hSLC, pProductSkuId, 0, ppwszInstallationId);
  sub_180001430(byte_1800194C8, byte_18001EB20);
  return v3;
}

```

## disassembly

```asm
0x1800113e0  push    rbx
0x1800113e2  sub     rsp, 20h
0x1800113e6  mov     r9, r8; ppwszInstallationId
0x1800113e9  xor     r8d, r8d; pActivationInfo
0x1800113ec  call    SLGenerateOfflineInstallationIdEx
0x1800113f1  lea     rdx, byte_18001EB20
0x1800113f8  mov     ebx, eax
0x1800113fa  lea     rcx, byte_1800194C8
0x180011401  call    sub_180001430
0x180011406  mov     eax, ebx
0x180011408  add     rsp, 20h
0x18001140c  pop     rbx
0x18001140d  retn
```
