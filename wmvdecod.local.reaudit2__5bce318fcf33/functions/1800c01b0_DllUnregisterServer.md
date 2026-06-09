# DllUnregisterServer

- ea: `0x1800c01b0`
- end: `0x1800c0200`
- name: `DllUnregisterServer`
- size: `80`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800c01b0`
- `0x1800c6cd8`

## import_xrefs

- `msdmo!DMOUnregister` at `0x1800c01cf`
- `msdmo!DMOUnregister` at `0x1800c01cf`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rcx
  LSTATUS v1; // ebx
  __int64 v2; // rcx
  int v3; // edi
  LSTATUS v4; // eax

  v1 = sub_1800C6CD8(v0);
  v3 = DMOUnregister(&clsidDMO, &guidCategory);
  if ( v1 < 0 )
    v3 = v1;
  v4 = sub_1800C6CD8(v2);
  if ( v3 >= 0 )
  {
    v3 = 0;
    if ( v4 < 0 )
      return v4;
  }
  return v3;
}

```

## disassembly

```asm
0x1800c01b0  mov     [rsp+arg_0], rbx
0x1800c01b5  push    rdi
0x1800c01b6  sub     rsp, 20h
0x1800c01ba  call    sub_1800C6CD8
0x1800c01bf  lea     rdx, guidCategory; guidCategory
0x1800c01c6  mov     ebx, eax
0x1800c01c8  lea     rcx, clsidDMO; clsidDMO
0x1800c01cf  call    cs:DMOUnregister
0x1800c01d6  nop     dword ptr [rax+rax+00h]
0x1800c01db  mov     edi, eax
0x1800c01dd  test    ebx, ebx
0x1800c01df  cmovs   edi, ebx
0x1800c01e2  call    sub_1800C6CD8
0x1800c01e7  test    edi, edi
0x1800c01e9  js      short loc_1800C01F2
0x1800c01eb  xor     edi, edi
0x1800c01ed  test    eax, eax
0x1800c01ef  cmovs   edi, eax
0x1800c01f2  mov     rbx, [rsp+28h+arg_0]
0x1800c01f7  mov     eax, edi
0x1800c01f9  add     rsp, 20h
0x1800c01fd  pop     rdi
0x1800c01fe  retn
```
