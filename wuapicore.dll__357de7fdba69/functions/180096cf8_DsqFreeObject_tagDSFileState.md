# DsqFreeObject(tagDSFileState &)

- ea: `0x180096cf8`
- end: `0x180096d7a`
- name: `?DsqFreeObject@@YAXAEAUtagDSFileState@@@Z`
- size: `130`
- prototype: `void __fastcall(struct tagDSFileState *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180096d80`

## callees

- `0x180096cf8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096d0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096d38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096d4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096d66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096d0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096d38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096d4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096d66`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSFileState *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v2 = (void *)*((_QWORD *)a1 + 2);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)a1 + 3);
  *((_QWORD *)a1 + 2) = 0;
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)a1 + 4);
  *((_QWORD *)a1 + 3) = 0;
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)a1 + 5);
  *((_QWORD *)a1 + 4) = 0;
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)a1 + 6);
  *((_QWORD *)a1 + 5) = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  *((_QWORD *)a1 + 6) = 0;
}

```

## disassembly

```asm
0x180096cf8  push    rbx
0x180096cfa  sub     rsp, 20h
0x180096cfe  mov     rbx, rcx
0x180096d01  mov     rcx, [rcx+10h]; pv
0x180096d05  test    rcx, rcx
0x180096d08  jz      short loc_180096D10
0x180096d0a  call    cs:__imp_CoTaskMemFree
0x180096d10  mov     rcx, [rbx+18h]; pv
0x180096d14  mov     qword ptr [rbx+10h], 0
0x180096d1c  test    rcx, rcx
0x180096d1f  jz      short loc_180096D27
0x180096d21  call    cs:__imp_CoTaskMemFree
0x180096d27  mov     rcx, [rbx+20h]; pv
0x180096d2b  mov     qword ptr [rbx+18h], 0
0x180096d33  test    rcx, rcx
0x180096d36  jz      short loc_180096D3E
0x180096d38  call    cs:__imp_CoTaskMemFree
0x180096d3e  mov     rcx, [rbx+28h]; pv
0x180096d42  mov     qword ptr [rbx+20h], 0
0x180096d4a  test    rcx, rcx
0x180096d4d  jz      short loc_180096D55
0x180096d4f  call    cs:__imp_CoTaskMemFree
0x180096d55  mov     rcx, [rbx+30h]; pv
0x180096d59  mov     qword ptr [rbx+28h], 0
0x180096d61  test    rcx, rcx
0x180096d64  jz      short loc_180096D6C
0x180096d66  call    cs:__imp_CoTaskMemFree
0x180096d6c  mov     qword ptr [rbx+30h], 0
0x180096d74  add     rsp, 20h
0x180096d78  pop     rbx
0x180096d79  retn
```
