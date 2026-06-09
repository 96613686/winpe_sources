# CleanUpBlbComponentInfo(_BLB_COMPONENT_INFO *)

- ea: `0x18008e978`
- end: `0x18008ea19`
- name: `?CleanUpBlbComponentInfo@@YAXPEAU_BLB_COMPONENT_INFO@@@Z`
- size: `161`
- prototype: `void __fastcall(struct _BLB_COMPONENT_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008edb0`

## callees

- `0x18008e978`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008e98d`
- `ole32!CoTaskMemFree` at `0x18008e9a5`
- `ole32!CoTaskMemFree` at `0x18008e9bd`
- `ole32!CoTaskMemFree` at `0x18008e9d5`
- `ole32!CoTaskMemFree` at `0x18008e9ed`
- `ole32!CoTaskMemFree` at `0x18008e98d`
- `ole32!CoTaskMemFree` at `0x18008e9a5`
- `ole32!CoTaskMemFree` at `0x18008e9bd`
- `ole32!CoTaskMemFree` at `0x18008e9d5`
- `ole32!CoTaskMemFree` at `0x18008e9ed`

## pseudocode

```c
void __fastcall CleanUpBlbComponentInfo(LPVOID *a1)
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
    CoTaskMemFree(a1[2]);
    v2 = v1[3];
    v1[2] = 0;
    CoTaskMemFree(v2);
    v3 = v1[7];
    v1[3] = 0;
    CoTaskMemFree(v3);
    v4 = v1[9];
    v1[7] = 0;
    CoTaskMemFree(v4);
    v5 = v1[13];
    v1[9] = 0;
    CoTaskMemFree(v5);
    v6 = 112;
    v1[13] = 0;
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
0x18008e978  test    rcx, rcx
0x18008e97b  jz      locret_18008EA17
0x18008e981  push    rbx
0x18008e982  sub     rsp, 20h
0x18008e986  mov     rbx, rcx
0x18008e989  mov     rcx, [rcx+10h]; pv
0x18008e98d  call    cs:__imp_CoTaskMemFree
0x18008e994  nop     dword ptr [rax+rax+00h]
0x18008e999  mov     rcx, [rbx+18h]; pv
0x18008e99d  mov     qword ptr [rbx+10h], 0
0x18008e9a5  call    cs:__imp_CoTaskMemFree
0x18008e9ac  nop     dword ptr [rax+rax+00h]
0x18008e9b1  mov     rcx, [rbx+38h]; pv
0x18008e9b5  mov     qword ptr [rbx+18h], 0
0x18008e9bd  call    cs:__imp_CoTaskMemFree
0x18008e9c4  nop     dword ptr [rax+rax+00h]
0x18008e9c9  mov     rcx, [rbx+48h]; pv
0x18008e9cd  mov     qword ptr [rbx+38h], 0
0x18008e9d5  call    cs:__imp_CoTaskMemFree
0x18008e9dc  nop     dword ptr [rax+rax+00h]
0x18008e9e1  mov     rcx, [rbx+68h]; pv
0x18008e9e5  mov     qword ptr [rbx+48h], 0
0x18008e9ed  call    cs:__imp_CoTaskMemFree
0x18008e9f4  nop     dword ptr [rax+rax+00h]
0x18008e9f9  mov     eax, 70h ; 'p'
0x18008e9fe  mov     qword ptr [rbx+68h], 0
0x18008ea06  mov     byte ptr [rbx], 0
0x18008ea09  inc     rbx
0x18008ea0c  sub     rax, 1
0x18008ea10  jnz     short loc_18008EA06
0x18008ea12  add     rsp, 20h
0x18008ea16  pop     rbx
0x18008ea17  retn
```
