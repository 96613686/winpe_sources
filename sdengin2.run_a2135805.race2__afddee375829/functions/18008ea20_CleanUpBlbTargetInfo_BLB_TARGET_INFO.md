# CleanUpBlbTargetInfo(_BLB_TARGET_INFO *)

- ea: `0x18008ea20`
- end: `0x18008eac1`
- name: `?CleanUpBlbTargetInfo@@YAXPEAU_BLB_TARGET_INFO@@@Z`
- size: `161`
- prototype: `void __fastcall(struct _BLB_TARGET_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180041410`
- `0x18008e690`

## callees

- `0x18008ea20`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008ea35`
- `ole32!CoTaskMemFree` at `0x18008ea4d`
- `ole32!CoTaskMemFree` at `0x18008ea65`
- `ole32!CoTaskMemFree` at `0x18008ea7d`
- `ole32!CoTaskMemFree` at `0x18008ea95`
- `ole32!CoTaskMemFree` at `0x18008ea35`
- `ole32!CoTaskMemFree` at `0x18008ea4d`
- `ole32!CoTaskMemFree` at `0x18008ea65`
- `ole32!CoTaskMemFree` at `0x18008ea7d`
- `ole32!CoTaskMemFree` at `0x18008ea95`

## pseudocode

```c
void __fastcall CleanUpBlbTargetInfo(LPVOID *a1)
{
  LPVOID *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rax

  if ( a1 )
  {
    v1 = a1;
    CoTaskMemFree(a1[1]);
    v2 = v1[2];
    v1[1] = 0;
    CoTaskMemFree(v2);
    v3 = v1[3];
    v1[2] = 0;
    CoTaskMemFree(v3);
    v4 = v1[4];
    v1[3] = 0;
    CoTaskMemFree(v4);
    v5 = v1[10];
    v1[4] = 0;
    CoTaskMemFree(v5);
    v6 = 96;
    v1[10] = 0;
    do
    {
      *(_BYTE *)v1 = 0;
      v1 = (LPVOID *)((char *)v1 + 1);
      --v6;
    }
    while ( v6 );
  }
}

```

## disassembly

```asm
0x18008ea20  test    rcx, rcx
0x18008ea23  jz      locret_18008EABF
0x18008ea29  push    rbx
0x18008ea2a  sub     rsp, 20h
0x18008ea2e  mov     rbx, rcx
0x18008ea31  mov     rcx, [rcx+8]; pv
0x18008ea35  call    cs:__imp_CoTaskMemFree
0x18008ea3c  nop     dword ptr [rax+rax+00h]
0x18008ea41  mov     rcx, [rbx+10h]; pv
0x18008ea45  mov     qword ptr [rbx+8], 0
0x18008ea4d  call    cs:__imp_CoTaskMemFree
0x18008ea54  nop     dword ptr [rax+rax+00h]
0x18008ea59  mov     rcx, [rbx+18h]; pv
0x18008ea5d  mov     qword ptr [rbx+10h], 0
0x18008ea65  call    cs:__imp_CoTaskMemFree
0x18008ea6c  nop     dword ptr [rax+rax+00h]
0x18008ea71  mov     rcx, [rbx+20h]; pv
0x18008ea75  mov     qword ptr [rbx+18h], 0
0x18008ea7d  call    cs:__imp_CoTaskMemFree
0x18008ea84  nop     dword ptr [rax+rax+00h]
0x18008ea89  mov     rcx, [rbx+50h]; pv
0x18008ea8d  mov     qword ptr [rbx+20h], 0
0x18008ea95  call    cs:__imp_CoTaskMemFree
0x18008ea9c  nop     dword ptr [rax+rax+00h]
0x18008eaa1  mov     eax, 60h ; '`'
0x18008eaa6  mov     qword ptr [rbx+50h], 0
0x18008eaae  mov     byte ptr [rbx], 0
0x18008eab1  inc     rbx
0x18008eab4  sub     rax, 1
0x18008eab8  jnz     short loc_18008EAAE
0x18008eaba  add     rsp, 20h
0x18008eabe  pop     rbx
0x18008eabf  retn
```
