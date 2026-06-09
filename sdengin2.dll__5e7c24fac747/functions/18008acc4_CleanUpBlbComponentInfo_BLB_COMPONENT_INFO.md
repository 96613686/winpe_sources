# CleanUpBlbComponentInfo(_BLB_COMPONENT_INFO *)

- ea: `0x18008acc4`
- end: `0x18008ad42`
- name: `?CleanUpBlbComponentInfo@@YAXPEAU_BLB_COMPONENT_INFO@@@Z`
- size: `126`
- prototype: `void __fastcall(struct _BLB_COMPONENT_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008b040`

## callees

- `0x18008acc4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008acd5`
- `ole32!CoTaskMemFree` at `0x18008ace7`
- `ole32!CoTaskMemFree` at `0x18008acf9`
- `ole32!CoTaskMemFree` at `0x18008ad0b`
- `ole32!CoTaskMemFree` at `0x18008ad1d`
- `ole32!CoTaskMemFree` at `0x18008acd5`
- `ole32!CoTaskMemFree` at `0x18008ace7`
- `ole32!CoTaskMemFree` at `0x18008acf9`
- `ole32!CoTaskMemFree` at `0x18008ad0b`
- `ole32!CoTaskMemFree` at `0x18008ad1d`

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
0x18008acc4  test    rcx, rcx
0x18008acc7  jz      short locret_18008AD41
0x18008acc9  push    rbx
0x18008acca  sub     rsp, 20h
0x18008acce  mov     rbx, rcx
0x18008acd1  mov     rcx, [rcx+10h]; pv
0x18008acd5  call    cs:__imp_CoTaskMemFree
0x18008acdb  mov     rcx, [rbx+18h]; pv
0x18008acdf  mov     qword ptr [rbx+10h], 0
0x18008ace7  call    cs:__imp_CoTaskMemFree
0x18008aced  mov     rcx, [rbx+38h]; pv
0x18008acf1  mov     qword ptr [rbx+18h], 0
0x18008acf9  call    cs:__imp_CoTaskMemFree
0x18008acff  mov     rcx, [rbx+48h]; pv
0x18008ad03  mov     qword ptr [rbx+38h], 0
0x18008ad0b  call    cs:__imp_CoTaskMemFree
0x18008ad11  mov     rcx, [rbx+68h]; pv
0x18008ad15  mov     qword ptr [rbx+48h], 0
0x18008ad1d  call    cs:__imp_CoTaskMemFree
0x18008ad23  mov     eax, 70h ; 'p'
0x18008ad28  mov     qword ptr [rbx+68h], 0
0x18008ad30  mov     byte ptr [rbx], 0
0x18008ad33  inc     rbx
0x18008ad36  sub     rax, 1
0x18008ad3a  jnz     short loc_18008AD30
0x18008ad3c  add     rsp, 20h
0x18008ad40  pop     rbx
0x18008ad41  retn
```
