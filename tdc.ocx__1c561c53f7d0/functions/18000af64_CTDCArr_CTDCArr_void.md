# CTDCArr::~CTDCArr(void)

- ea: `0x18000af64`
- end: `0x18000b0fb`
- name: `??1CTDCArr@@AEAA@XZ`
- size: `407`
- prototype: `void __fastcall(CTDCArr *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18000cf10`

## callees

- `0x180001194`
- `0x180003f70`
- `0x18000af64`
- `0x18000b104`
- `0x18000b154`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000afe1`
- `ole32!CoTaskMemFree` at `0x18000b006`
- `ole32!CoTaskMemFree` at `0x18000b024`
- `ole32!CoTaskMemFree` at `0x18000b046`
- `ole32!CoTaskMemFree` at `0x18000afe1`
- `ole32!CoTaskMemFree` at `0x18000b006`
- `ole32!CoTaskMemFree` at `0x18000b024`
- `ole32!CoTaskMemFree` at `0x18000b046`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b084`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b0c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b084`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b0c5`
- `OLEAUT32!__imp_VariantClear` at `0x18000afbb`
- `OLEAUT32!__imp_VariantClear` at `0x18000b0b3`
- `OLEAUT32!__imp_VariantClear` at `0x18000afbb`
- `OLEAUT32!__imp_VariantClear` at `0x18000b0b3`

## pseudocode

```c
void __fastcall CTDCArr::~CTDCArr(CTDCArr *this)
{
  unsigned int v1; // esi
  LPVOID *v2; // rdi
  __int64 v4; // r15
  VARIANTARG *v5; // r14
  VARIANTARG *v6; // rdx
  unsigned int v7; // edx
  _QWORD *v8; // rdi
  CTDCSortCriterion *v9; // rcx
  unsigned int v10; // edx
  __int64 v11; // rdi
  CTDCFilterNode *v12; // rcx
  CTDCFilterNode *v13; // rcx
  __int64 v14; // rcx

  v1 = *((_DWORD *)this + 34);
  *(_QWORD *)this = &CTDCArr::`vftable'{for `OLEDBSimpleProvider'};
  v2 = (LPVOID *)((char *)this + 128);
  *((_QWORD *)this + 1) = &CTDCArr::`vftable'{for `CTDCFieldSink'};
  while ( (--v1 & 0x80000000) == 0 )
  {
    v4 = *((_QWORD *)*v2 + v1);
    v5 = *(VARIANTARG **)v4;
    if ( *(_QWORD *)v4 >= (unsigned __int64)(*(_QWORD *)v4 + 24LL * *(_QWORD *)(v4 + 8)) )
    {
      v6 = *(VARIANTARG **)v4;
    }
    else
    {
      do
      {
        VariantClear(v5++);
        v6 = *(VARIANTARG **)v4;
      }
      while ( (unsigned __int64)v5 < *(_QWORD *)v4 + 24LL * *(_QWORD *)(v4 + 8) );
    }
    CoTaskMemFree(v6);
    *(_QWORD *)v4 = 0;
    *(_QWORD *)(v4 + 8) = 0;
    *(_QWORD *)(v4 + 16) = 0;
    operator delete(*((void **)*v2 + v1));
  }
  CoTaskMemFree(*v2);
  *v2 = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  CoTaskMemFree(*((LPVOID *)this + 19));
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  CoTaskMemFree(*((LPVOID *)this + 22));
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  v8 = (_QWORD *)*((_QWORD *)this + 7);
  if ( v8 )
  {
    v9 = (CTDCSortCriterion *)v8[1];
    if ( v9 )
      CTDCSortCriterion::`scalar deleting destructor'(v9, v7);
    operator delete(v8);
  }
  SysFreeString(*((BSTR *)this + 8));
  v11 = *((_QWORD *)this + 9);
  if ( v11 )
  {
    v12 = *(CTDCFilterNode **)(v11 + 8);
    if ( v12 )
      CTDCFilterNode::`scalar deleting destructor'(v12, v10);
    v13 = *(CTDCFilterNode **)(v11 + 16);
    if ( v13 )
      CTDCFilterNode::`scalar deleting destructor'(v13, v10);
    VariantClear((VARIANTARG *)(v11 + 32));
    operator delete((void *)v11);
  }
  SysFreeString(*((BSTR *)this + 10));
  v14 = *((_QWORD *)this + 2);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    *((_QWORD *)this + 2) = 0;
  }
  ClearInterfaceFn((struct IUnknown **)this + 3);
}

```

## disassembly

```asm
0x18000af64  push    rbx
0x18000af66  push    rbp
0x18000af67  push    rsi
0x18000af68  push    rdi
0x18000af69  push    r12
0x18000af6b  push    r14
0x18000af6d  push    r15
0x18000af6f  sub     rsp, 20h
0x18000af73  mov     esi, [rcx+88h]
0x18000af79  lea     rax, ??_7CTDCArr@@6BOLEDBSimpleProvider@@@; const CTDCArr::`vftable'{for `OLEDBSimpleProvider'}
0x18000af80  mov     [rcx], rax
0x18000af83  lea     rdi, [rcx+80h]
0x18000af8a  lea     rax, ??_7CTDCArr@@6BCTDCFieldSink@@@; const CTDCArr::`vftable'{for `CTDCFieldSink'}
0x18000af91  mov     rbx, rcx
0x18000af94  mov     [rcx+8], rax
0x18000af98  xor     r12d, r12d
0x18000af9b  jmp     short loc_18000AFFE
0x18000af9d  mov     rax, [rdi]
0x18000afa0  mov     r15, [rax+rsi*8]
0x18000afa4  mov     rax, [r15+8]
0x18000afa8  mov     r14, [r15]
0x18000afab  lea     rcx, [rax+rax*2]
0x18000afaf  lea     rax, [r14+rcx*8]
0x18000afb3  cmp     r14, rax
0x18000afb6  jnb     short loc_18000AFDB
0x18000afb8  mov     rcx, r14; pvarg
0x18000afbb  call    cs:__imp_VariantClear
0x18000afc1  mov     rax, [r15+8]
0x18000afc5  add     r14, 18h
0x18000afc9  mov     rdx, [r15]
0x18000afcc  lea     rcx, [rax+rax*2]
0x18000afd0  lea     rax, [rdx+rcx*8]
0x18000afd4  cmp     r14, rax
0x18000afd7  jb      short loc_18000AFB8
0x18000afd9  jmp     short loc_18000AFDE
0x18000afdb  mov     rdx, r14
0x18000afde  mov     rcx, rdx; pv
0x18000afe1  call    cs:__imp_CoTaskMemFree
0x18000afe7  mov     [r15], r12
0x18000afea  mov     [r15+8], r12
0x18000afee  mov     [r15+10h], r12
0x18000aff2  mov     rcx, [rdi]
0x18000aff5  mov     rcx, [rcx+rsi*8]; Block
0x18000aff9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000affe  sub     esi, 1
0x18000b001  jns     short loc_18000AF9D
0x18000b003  mov     rcx, [rdi]; pv
0x18000b006  call    cs:__imp_CoTaskMemFree
0x18000b00c  mov     [rdi], r12
0x18000b00f  mov     [rbx+88h], r12
0x18000b016  mov     [rbx+90h], r12
0x18000b01d  mov     rcx, [rbx+98h]; pv
0x18000b024  call    cs:__imp_CoTaskMemFree
0x18000b02a  mov     [rbx+98h], r12
0x18000b031  mov     [rbx+0A0h], r12
0x18000b038  mov     [rbx+0A8h], r12
0x18000b03f  mov     rcx, [rbx+0B0h]; pv
0x18000b046  call    cs:__imp_CoTaskMemFree
0x18000b04c  mov     [rbx+0B0h], r12
0x18000b053  mov     [rbx+0B8h], r12
0x18000b05a  mov     [rbx+0C0h], r12
0x18000b061  mov     rdi, [rbx+38h]
0x18000b065  test    rdi, rdi
0x18000b068  jz      short loc_18000B080
0x18000b06a  mov     rcx, [rdi+8]; this
0x18000b06e  test    rcx, rcx
0x18000b071  jz      short loc_18000B078
0x18000b073  call    ??_GCTDCSortCriterion@@QEAAPEAXI@Z; CTDCSortCriterion::`scalar deleting destructor'(uint)
0x18000b078  mov     rcx, rdi; Block
0x18000b07b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b080  mov     rcx, [rbx+40h]; bstrString
0x18000b084  call    cs:__imp_SysFreeString
0x18000b08a  mov     rdi, [rbx+48h]
0x18000b08e  test    rdi, rdi
0x18000b091  jz      short loc_18000B0C1
0x18000b093  mov     rcx, [rdi+8]; this
0x18000b097  test    rcx, rcx
0x18000b09a  jz      short loc_18000B0A1
0x18000b09c  call    ??_GCTDCFilterNode@@QEAAPEAXI@Z; CTDCFilterNode::`scalar deleting destructor'(uint)
0x18000b0a1  mov     rcx, [rdi+10h]; this
0x18000b0a5  test    rcx, rcx
0x18000b0a8  jz      short loc_18000B0AF
0x18000b0aa  call    ??_GCTDCFilterNode@@QEAAPEAXI@Z; CTDCFilterNode::`scalar deleting destructor'(uint)
0x18000b0af  lea     rcx, [rdi+20h]; pvarg
0x18000b0b3  call    cs:__imp_VariantClear
0x18000b0b9  mov     rcx, rdi; Block
0x18000b0bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b0c1  mov     rcx, [rbx+50h]; bstrString
0x18000b0c5  call    cs:__imp_SysFreeString
0x18000b0cb  mov     rcx, [rbx+10h]
0x18000b0cf  test    rcx, rcx
0x18000b0d2  jz      short loc_18000B0E4
0x18000b0d4  mov     rax, [rcx]
0x18000b0d7  mov     rax, [rax+8]
0x18000b0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0e0  mov     [rbx+10h], r12
0x18000b0e4  lea     rcx, [rbx+18h]; struct IUnknown **
0x18000b0e8  add     rsp, 20h
0x18000b0ec  pop     r15
0x18000b0ee  pop     r14
0x18000b0f0  pop     r12
0x18000b0f2  pop     rdi
0x18000b0f3  pop     rsi
0x18000b0f4  pop     rbp
0x18000b0f5  pop     rbx
0x18000b0f6  jmp     ?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z; ClearInterfaceFn(IUnknown * *)
```
