# SLDepositOfflineConfirmationId

- ea: `0x180010b50`
- end: `0x180010b83`
- name: `SLDepositOfflineConfirmationId`
- size: `51`
- prototype: `HRESULT __stdcall(HSLC hSLC, const SLID *pProductSkuId, PCWSTR pwszInstallationId, PCWSTR pwszConfirmationId)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180003030`
- `0x180010b90`

## pseudocode

```c
HRESULT __stdcall SLDepositOfflineConfirmationId(
        HSLC hSLC,
        const SLID *pProductSkuId,
        PCWSTR pwszInstallationId,
        PCWSTR pwszConfirmationId)
{
  HRESULT v4; // ebx

  v4 = SLDepositOfflineConfirmationIdEx(hSLC, pProductSkuId, 0, pwszInstallationId, pwszConfirmationId);
  sub_180003030(byte_180018440, &dword_18001E614);
  return v4;
}

```

## disassembly

```asm
0x180010b50  push    rbx
0x180010b52  sub     rsp, 30h
0x180010b56  mov     [rsp+38h+pwszConfirmationId], r9; pwszConfirmationId
0x180010b5b  mov     r9, r8; pwszInstallationId
0x180010b5e  xor     r8d, r8d; pActivationInfo
0x180010b61  call    SLDepositOfflineConfirmationIdEx
0x180010b66  lea     rdx, dword_18001E614
0x180010b6d  mov     ebx, eax
0x180010b6f  lea     rcx, byte_180018440
0x180010b76  call    sub_180003030
0x180010b7b  mov     eax, ebx
0x180010b7d  add     rsp, 30h
0x180010b81  pop     rbx
0x180010b82  retn
```
