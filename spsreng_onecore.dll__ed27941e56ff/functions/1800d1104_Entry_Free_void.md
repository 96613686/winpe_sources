# Entry::Free(void)

- ea: `0x1800d1104`
- end: `0x1800d115d`
- name: `?Free@Entry@@QEAAXXZ`
- size: `89`
- prototype: `void __fastcall(Entry *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800d0f40`
- `0x1800d0f8c`

## callees

- `0x180002e00`
- `0x1800d1104`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d113b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d113b`

## pseudocode

```c
void __fastcall Entry::Free(void **this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *this;
  if ( v2 )
  {
    operator delete(v2);
    *this = 0;
  }
  operator delete(this[1]);
  v3 = this[2];
  this[1] = 0;
  if ( v3 )
  {
    CoTaskMemFree(v3);
    this[2] = 0;
    *((_DWORD *)this + 6) = 0;
  }
  *((_DWORD *)this + 7) = 0;
}

```

## disassembly

```asm
0x1800d1104  push    rbx
0x1800d1106  sub     rsp, 20h
0x1800d110a  mov     rbx, rcx
0x1800d110d  mov     rcx, [rcx]; void *
0x1800d1110  test    rcx, rcx
0x1800d1113  jz      short loc_1800D1121
0x1800d1115  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800d111a  mov     qword ptr [rbx], 0
0x1800d1121  mov     rcx, [rbx+8]; void *
0x1800d1125  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800d112a  mov     rcx, [rbx+10h]; pv
0x1800d112e  mov     qword ptr [rbx+8], 0
0x1800d1136  test    rcx, rcx
0x1800d1139  jz      short loc_1800D1150
0x1800d113b  call    cs:__imp_CoTaskMemFree
0x1800d1141  mov     qword ptr [rbx+10h], 0
0x1800d1149  mov     dword ptr [rbx+18h], 0
0x1800d1150  mov     dword ptr [rbx+1Ch], 0
0x1800d1157  add     rsp, 20h
0x1800d115b  pop     rbx
0x1800d115c  retn
```
