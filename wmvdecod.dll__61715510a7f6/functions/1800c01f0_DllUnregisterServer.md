# DllUnregisterServer

- ea: `0x1800c01f0`
- end: `0x1800c0240`
- name: `DllUnregisterServer`
- size: `80`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800c01f0`
- `0x1800c6d18`

## import_xrefs

- `msdmo!DMOUnregister` at `0x1800c020f`
- `msdmo!DMOUnregister` at `0x1800c020f`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rcx
  LSTATUS v1; // ebx
  __int64 v2; // rcx
  int v3; // edi
  LSTATUS v4; // eax

  v1 = sub_1800C6D18(v0);
  v3 = DMOUnregister(&clsidDMO, &guidCategory);
  if ( v1 < 0 )
    v3 = v1;
  v4 = sub_1800C6D18(v2);
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
0x1800c01f0  mov     [rsp+arg_0], rbx
0x1800c01f5  push    rdi
0x1800c01f6  sub     rsp, 20h
0x1800c01fa  call    sub_1800C6D18
0x1800c01ff  lea     rdx, guidCategory; guidCategory
0x1800c0206  mov     ebx, eax
0x1800c0208  lea     rcx, clsidDMO; clsidDMO
0x1800c020f  call    cs:DMOUnregister
0x1800c0216  nop     dword ptr [rax+rax+00h]
0x1800c021b  mov     edi, eax
0x1800c021d  test    ebx, ebx
0x1800c021f  cmovs   edi, ebx
0x1800c0222  call    sub_1800C6D18
0x1800c0227  test    edi, edi
0x1800c0229  js      short loc_1800C0232
0x1800c022b  xor     edi, edi
0x1800c022d  test    eax, eax
0x1800c022f  cmovs   edi, eax
0x1800c0232  mov     rbx, [rsp+28h+arg_0]
0x1800c0237  mov     eax, edi
0x1800c0239  add     rsp, 20h
0x1800c023d  pop     rdi
0x1800c023e  retn
```
