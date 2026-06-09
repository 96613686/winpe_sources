# BlbFreeCatComponentInfo(_BLBCAT_COMPONENT_INFO *)

- ea: `0x1400f5850`
- end: `0x1400f5910`
- name: `?BlbFreeCatComponentInfo@@YAXPEAU_BLBCAT_COMPONENT_INFO@@@Z`
- size: `192`
- prototype: `void __fastcall(struct _BLBCAT_COMPONENT_INFO *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400f4808`
- `0x1400f4f8c`
- `0x1400f5918`

## callees

- `0x140007ad3`
- `0x1400f5850`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400f586a`
- `ole32!CoTaskMemFree` at `0x1400f5881`
- `ole32!CoTaskMemFree` at `0x1400f5898`
- `ole32!CoTaskMemFree` at `0x1400f58af`
- `ole32!CoTaskMemFree` at `0x1400f58c6`
- `ole32!CoTaskMemFree` at `0x1400f58dd`
- `ole32!CoTaskMemFree` at `0x1400f58f4`
- `ole32!CoTaskMemFree` at `0x1400f586a`
- `ole32!CoTaskMemFree` at `0x1400f5881`
- `ole32!CoTaskMemFree` at `0x1400f5898`
- `ole32!CoTaskMemFree` at `0x1400f58af`
- `ole32!CoTaskMemFree` at `0x1400f58c6`
- `ole32!CoTaskMemFree` at `0x1400f58dd`
- `ole32!CoTaskMemFree` at `0x1400f58f4`

## pseudocode

```c
void __fastcall BlbFreeCatComponentInfo(struct _BLBCAT_COMPONENT_INFO *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( a1 )
  {
    v2 = (void *)*((_QWORD *)a1 + 13);
    if ( v2 )
    {
      CoTaskMemFree(v2);
      *((_QWORD *)a1 + 13) = 0;
    }
    v3 = (void *)*((_QWORD *)a1 + 6);
    if ( v3 )
    {
      CoTaskMemFree(v3);
      *((_QWORD *)a1 + 6) = 0;
    }
    v4 = (void *)*((_QWORD *)a1 + 7);
    if ( v4 )
    {
      CoTaskMemFree(v4);
      *((_QWORD *)a1 + 7) = 0;
    }
    v5 = (void *)*((_QWORD *)a1 + 8);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *((_QWORD *)a1 + 8) = 0;
    }
    v6 = (void *)*((_QWORD *)a1 + 9);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *((_QWORD *)a1 + 9) = 0;
    }
    v7 = (void *)*((_QWORD *)a1 + 11);
    if ( v7 )
    {
      CoTaskMemFree(v7);
      *((_QWORD *)a1 + 11) = 0;
    }
    v8 = (void *)*((_QWORD *)a1 + 15);
    if ( v8 )
      CoTaskMemFree(v8);
    memset_0(a1, 0, 0x88u);
  }
}

```

## disassembly

```asm
0x1400f5850  test    rcx, rcx
0x1400f5853  jz      locret_1400F590F
0x1400f5859  push    rbx
0x1400f585a  sub     rsp, 20h
0x1400f585e  mov     rbx, rcx
0x1400f5861  mov     rcx, [rcx+68h]; pv
0x1400f5865  test    rcx, rcx
0x1400f5868  jz      short loc_1400F5878
0x1400f586a  call    cs:__imp_CoTaskMemFree
0x1400f5870  mov     qword ptr [rbx+68h], 0
0x1400f5878  mov     rcx, [rbx+30h]; pv
0x1400f587c  test    rcx, rcx
0x1400f587f  jz      short loc_1400F588F
0x1400f5881  call    cs:__imp_CoTaskMemFree
0x1400f5887  mov     qword ptr [rbx+30h], 0
0x1400f588f  mov     rcx, [rbx+38h]; pv
0x1400f5893  test    rcx, rcx
0x1400f5896  jz      short loc_1400F58A6
0x1400f5898  call    cs:__imp_CoTaskMemFree
0x1400f589e  mov     qword ptr [rbx+38h], 0
0x1400f58a6  mov     rcx, [rbx+40h]; pv
0x1400f58aa  test    rcx, rcx
0x1400f58ad  jz      short loc_1400F58BD
0x1400f58af  call    cs:__imp_CoTaskMemFree
0x1400f58b5  mov     qword ptr [rbx+40h], 0
0x1400f58bd  mov     rcx, [rbx+48h]; pv
0x1400f58c1  test    rcx, rcx
0x1400f58c4  jz      short loc_1400F58D4
0x1400f58c6  call    cs:__imp_CoTaskMemFree
0x1400f58cc  mov     qword ptr [rbx+48h], 0
0x1400f58d4  mov     rcx, [rbx+58h]; pv
0x1400f58d8  test    rcx, rcx
0x1400f58db  jz      short loc_1400F58EB
0x1400f58dd  call    cs:__imp_CoTaskMemFree
0x1400f58e3  mov     qword ptr [rbx+58h], 0
0x1400f58eb  mov     rcx, [rbx+78h]; pv
0x1400f58ef  test    rcx, rcx
0x1400f58f2  jz      short loc_1400F58FA
0x1400f58f4  call    cs:__imp_CoTaskMemFree
0x1400f58fa  xor     edx, edx; Val
0x1400f58fc  mov     r8d, 88h; Size
0x1400f5902  mov     rcx, rbx; void *
0x1400f5905  call    memset_0
0x1400f590a  add     rsp, 20h
0x1400f590e  pop     rbx
0x1400f590f  retn
```
