# CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)

- ea: `0x18000508c`
- end: `0x1800050d3`
- name: `?_FreeCbsHiveLoadInformation@CSxWindowsUpdateEnumerator@@SAXPEAU_CBS_LOADED_HIVE_INFORMATION@1@@Z`
- size: `71`
- prototype: `void __fastcall(LPVOID *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180003f1c`
- `0x1800055a4`
- `0x180005c6c`

## callees

- `0x18000508c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000509c`
- `ole32!CoTaskMemFree` at `0x1800050ad`
- `ole32!CoTaskMemFree` at `0x1800050bf`
- `ole32!CoTaskMemFree` at `0x18000509c`
- `ole32!CoTaskMemFree` at `0x1800050ad`
- `ole32!CoTaskMemFree` at `0x1800050bf`

## pseudocode

```c
void __fastcall CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(LPVOID *a1)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( a1 )
  {
    CoTaskMemFree(*a1);
    v2 = a1[1];
    *a1 = 0;
    CoTaskMemFree(v2);
    v3 = a1[2];
    a1[1] = 0;
    CoTaskMemFree(v3);
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18000508c  test    rcx, rcx
0x18000508f  jz      short locret_1800050D2
0x180005091  push    rbx
0x180005092  sub     rsp, 20h
0x180005096  mov     rbx, rcx
0x180005099  mov     rcx, [rcx]; pv
0x18000509c  call    cs:__imp_CoTaskMemFree
0x1800050a2  mov     rcx, [rbx+8]; pv
0x1800050a6  mov     qword ptr [rbx], 0
0x1800050ad  call    cs:__imp_CoTaskMemFree
0x1800050b3  mov     rcx, [rbx+10h]; pv
0x1800050b7  mov     qword ptr [rbx+8], 0
0x1800050bf  call    cs:__imp_CoTaskMemFree
0x1800050c5  mov     qword ptr [rbx+10h], 0
0x1800050cd  add     rsp, 20h
0x1800050d1  pop     rbx
0x1800050d2  retn
```
