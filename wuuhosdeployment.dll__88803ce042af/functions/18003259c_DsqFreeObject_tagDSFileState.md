# DsqFreeObject(tagDSFileState &)

- ea: `0x18003259c`
- end: `0x18003261e`
- name: `?DsqFreeObject@@YAXAEAUtagDSFileState@@@Z`
- size: `130`
- prototype: `void __fastcall(struct tagDSFileState *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032624`

## callees

- `0x18003259c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800325ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800325c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800325dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800325f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003260a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800325ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800325c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800325dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800325f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003260a`

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
0x18003259c  push    rbx
0x18003259e  sub     rsp, 20h
0x1800325a2  mov     rbx, rcx
0x1800325a5  mov     rcx, [rcx+10h]; pv
0x1800325a9  test    rcx, rcx
0x1800325ac  jz      short loc_1800325B4
0x1800325ae  call    cs:__imp_CoTaskMemFree
0x1800325b4  mov     rcx, [rbx+18h]; pv
0x1800325b8  mov     qword ptr [rbx+10h], 0
0x1800325c0  test    rcx, rcx
0x1800325c3  jz      short loc_1800325CB
0x1800325c5  call    cs:__imp_CoTaskMemFree
0x1800325cb  mov     rcx, [rbx+20h]; pv
0x1800325cf  mov     qword ptr [rbx+18h], 0
0x1800325d7  test    rcx, rcx
0x1800325da  jz      short loc_1800325E2
0x1800325dc  call    cs:__imp_CoTaskMemFree
0x1800325e2  mov     rcx, [rbx+28h]; pv
0x1800325e6  mov     qword ptr [rbx+20h], 0
0x1800325ee  test    rcx, rcx
0x1800325f1  jz      short loc_1800325F9
0x1800325f3  call    cs:__imp_CoTaskMemFree
0x1800325f9  mov     rcx, [rbx+30h]; pv
0x1800325fd  mov     qword ptr [rbx+28h], 0
0x180032605  test    rcx, rcx
0x180032608  jz      short loc_180032610
0x18003260a  call    cs:__imp_CoTaskMemFree
0x180032610  mov     qword ptr [rbx+30h], 0
0x180032618  add     rsp, 20h
0x18003261c  pop     rbx
0x18003261d  retn
```
