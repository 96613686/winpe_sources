# FreeServerInstallEntry

- ea: `0x1800106dc`
- end: `0x180010758`
- name: `FreeServerInstallEntry`
- size: `124`
- prototype: `BOOLEAN __fastcall(_QWORD *P)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180008d20`
- `0x180009d70`
- `0x18000a3a0`

## callees

- `0x1800106dc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800106fb`
- `ntdll!RtlFreeHeap` at `0x180010713`
- `ntdll!RtlFreeHeap` at `0x18001072b`
- `ntdll!RtlFreeHeap` at `0x18001074c`
- `ntdll!RtlFreeHeap` at `0x1800106fb`
- `ntdll!RtlFreeHeap` at `0x180010713`
- `ntdll!RtlFreeHeap` at `0x18001072b`
- `ntdll!RtlFreeHeap` at `0x18001074c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001073a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001073a`

## pseudocode

```c
BOOLEAN __fastcall FreeServerInstallEntry(_QWORD *P)
{
  void *v1; // r8
  void *v3; // r8
  void *v4; // r8
  void *v5; // rcx
  BOOLEAN result; // al

  if ( P )
  {
    v1 = (void *)P[4];
    if ( v1 )
      RtlFreeHeap(PnpHeapHandle, 0, v1);
    v3 = (void *)P[6];
    if ( v3 )
      RtlFreeHeap(PnpHeapHandle, 0, v3);
    v4 = (void *)P[7];
    if ( v4 )
      RtlFreeHeap(PnpHeapHandle, 0, v4);
    v5 = (void *)P[3];
    if ( v5 )
      CloseHandle(v5);
    return RtlFreeHeap(PnpHeapHandle, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x1800106dc  test    rcx, rcx
0x1800106df  jz      short locret_180010757
0x1800106e1  push    rbx
0x1800106e2  sub     rsp, 20h
0x1800106e6  mov     r8, [rcx+20h]; P
0x1800106ea  mov     rbx, rcx
0x1800106ed  test    r8, r8
0x1800106f0  jz      short loc_180010701
0x1800106f2  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x1800106f9  xor     edx, edx; Flags
0x1800106fb  call    cs:__imp_RtlFreeHeap
0x180010701  mov     r8, [rbx+30h]; P
0x180010705  test    r8, r8
0x180010708  jz      short loc_180010719
0x18001070a  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180010711  xor     edx, edx; Flags
0x180010713  call    cs:__imp_RtlFreeHeap
0x180010719  mov     r8, [rbx+38h]; P
0x18001071d  test    r8, r8
0x180010720  jz      short loc_180010731
0x180010722  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180010729  xor     edx, edx; Flags
0x18001072b  call    cs:__imp_RtlFreeHeap
0x180010731  mov     rcx, [rbx+18h]; hObject
0x180010735  test    rcx, rcx
0x180010738  jz      short loc_180010740
0x18001073a  call    cs:__imp_CloseHandle
0x180010740  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180010747  mov     r8, rbx; P
0x18001074a  xor     edx, edx; Flags
0x18001074c  call    cs:__imp_RtlFreeHeap
0x180010752  add     rsp, 20h
0x180010756  pop     rbx
0x180010757  retn
```
