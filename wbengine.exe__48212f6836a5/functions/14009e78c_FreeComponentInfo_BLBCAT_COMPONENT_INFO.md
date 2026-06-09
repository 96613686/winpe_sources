# FreeComponentInfo(_BLBCAT_COMPONENT_INFO *)

- ea: `0x14009e78c`
- end: `0x14009e865`
- name: `?FreeComponentInfo@@YAXPEAU_BLBCAT_COMPONENT_INFO@@@Z`
- size: `217`
- prototype: `void __fastcall(struct _BLBCAT_COMPONENT_INFO *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002667c`
- `0x140098d20`
- `0x14009e734`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14009e78c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14009e7c0`
- `ole32!CoTaskMemFree` at `0x14009e7d7`
- `ole32!CoTaskMemFree` at `0x14009e7ee`
- `ole32!CoTaskMemFree` at `0x14009e805`
- `ole32!CoTaskMemFree` at `0x14009e81c`
- `ole32!CoTaskMemFree` at `0x14009e833`
- `ole32!CoTaskMemFree` at `0x14009e84a`
- `ole32!CoTaskMemFree` at `0x14009e7c0`
- `ole32!CoTaskMemFree` at `0x14009e7d7`
- `ole32!CoTaskMemFree` at `0x14009e7ee`
- `ole32!CoTaskMemFree` at `0x14009e805`
- `ole32!CoTaskMemFree` at `0x14009e81c`
- `ole32!CoTaskMemFree` at `0x14009e833`
- `ole32!CoTaskMemFree` at `0x14009e84a`

## string_xrefs

- `0x14009e79a`: `pComponentInfo`

## pseudocode

```c
void __fastcall FreeComponentInfo(struct _BLBCAT_COMPONENT_INFO *a1)
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
  else
  {
    BlbAssert("base\\stor\\blb\\catalog\\catglbl.cpp", 0x316u, "pComponentInfo");
  }
}

```

## disassembly

```asm
0x14009e78c  push    rbx
0x14009e78e  sub     rsp, 20h
0x14009e792  mov     rbx, rcx
0x14009e795  test    rcx, rcx
0x14009e798  jnz     short loc_14009E7B7
0x14009e79a  lea     r8, aPcomponentinfo; "pComponentInfo"
0x14009e7a1  mov     edx, 316h; unsigned int
0x14009e7a6  lea     rcx, aBaseStorBlbCat_9; "base\\stor\\blb\\catalog\\catglbl.cpp"
0x14009e7ad  add     rsp, 20h
0x14009e7b1  pop     rbx
0x14009e7b2  jmp     ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14009e7b7  mov     rcx, [rcx+68h]; pv
0x14009e7bb  test    rcx, rcx
0x14009e7be  jz      short loc_14009E7CE
0x14009e7c0  call    cs:__imp_CoTaskMemFree
0x14009e7c6  mov     qword ptr [rbx+68h], 0
0x14009e7ce  mov     rcx, [rbx+30h]; pv
0x14009e7d2  test    rcx, rcx
0x14009e7d5  jz      short loc_14009E7E5
0x14009e7d7  call    cs:__imp_CoTaskMemFree
0x14009e7dd  mov     qword ptr [rbx+30h], 0
0x14009e7e5  mov     rcx, [rbx+38h]; pv
0x14009e7e9  test    rcx, rcx
0x14009e7ec  jz      short loc_14009E7FC
0x14009e7ee  call    cs:__imp_CoTaskMemFree
0x14009e7f4  mov     qword ptr [rbx+38h], 0
0x14009e7fc  mov     rcx, [rbx+40h]; pv
0x14009e800  test    rcx, rcx
0x14009e803  jz      short loc_14009E813
0x14009e805  call    cs:__imp_CoTaskMemFree
0x14009e80b  mov     qword ptr [rbx+40h], 0
0x14009e813  mov     rcx, [rbx+48h]; pv
0x14009e817  test    rcx, rcx
0x14009e81a  jz      short loc_14009E82A
0x14009e81c  call    cs:__imp_CoTaskMemFree
0x14009e822  mov     qword ptr [rbx+48h], 0
0x14009e82a  mov     rcx, [rbx+58h]; pv
0x14009e82e  test    rcx, rcx
0x14009e831  jz      short loc_14009E841
0x14009e833  call    cs:__imp_CoTaskMemFree
0x14009e839  mov     qword ptr [rbx+58h], 0
0x14009e841  mov     rcx, [rbx+78h]; pv
0x14009e845  test    rcx, rcx
0x14009e848  jz      short loc_14009E850
0x14009e84a  call    cs:__imp_CoTaskMemFree
0x14009e850  xor     edx, edx; Val
0x14009e852  mov     r8d, 88h; Size
0x14009e858  mov     rcx, rbx; void *
0x14009e85b  add     rsp, 20h
0x14009e85f  pop     rbx
0x14009e860  jmp     memset_0
```
