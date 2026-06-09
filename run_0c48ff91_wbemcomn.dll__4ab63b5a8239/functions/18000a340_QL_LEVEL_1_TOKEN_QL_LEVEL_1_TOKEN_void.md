# QL_LEVEL_1_TOKEN::~QL_LEVEL_1_TOKEN(void)

- ea: `0x18000a340`
- end: `0x18000a40c`
- name: `??1QL_LEVEL_1_TOKEN@@QEAA@XZ`
- size: `204`
- prototype: `void __fastcall(QL_LEVEL_1_TOKEN *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a340`
- `0x18000ab30`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000a362`
- `OLEAUT32!__imp_VariantClear` at `0x18000a362`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall QL_LEVEL_1_TOKEN::~QL_LEVEL_1_TOKEN(VARIANTARG *this)
{
  LONG i; // edi
  IRecordInfo *pRecInfo; // rax
  LONG j; // edi
  IRecordInfo *v5; // rax

  *(_DWORD *)&this->vt = 0;
  *((_DWORD *)&this[1].decVal + 4) = 0;
  VariantClear(this + 2);
  if ( this[3].pRecInfo )
  {
    for ( i = 0; i < this[3].lVal; ++i )
    {
      pRecInfo = this[3].pRecInfo;
      if ( !LOWORD(pRecInfo[2 * i].lpVtbl) )
        CoTaskMemFree(pRecInfo[2 * i + 1].lpVtbl);
    }
    CMUILocale::_Free(this[3].pRecInfo);
    this[3].pRecInfo = 0;
  }
  this[3].lVal = 0;
  *(_DWORD *)&this[4].vt = 0;
  this[4].llVal = 0;
  if ( this->pRecInfo )
  {
    for ( j = 0; j < this->lVal; ++j )
    {
      v5 = this->pRecInfo;
      if ( !LOWORD(v5[2 * j].lpVtbl) )
        CoTaskMemFree(v5[2 * j + 1].lpVtbl);
    }
    CMUILocale::_Free(this->pRecInfo);
    this->pRecInfo = 0;
  }
  this->lVal = 0;
  *(_DWORD *)&this[1].vt = 0;
  this[1].llVal = 0;
}

```

## disassembly

```asm
0x18000a340  mov     [rsp+arg_8], rbx
0x18000a345  mov     [rsp+arg_10], rsi
0x18000a34a  mov     [rsp+arg_0], rcx
0x18000a34f  push    rdi
0x18000a350  sub     rsp, 20h
0x18000a354  mov     rbx, rcx
0x18000a357  xor     esi, esi
0x18000a359  mov     [rcx], esi
0x18000a35b  mov     [rcx+28h], esi
0x18000a35e  add     rcx, 30h ; '0'; pvarg
0x18000a362  call    cs:__imp_VariantClear
0x18000a368  nop
0x18000a369  cmp     [rbx+58h], rsi
0x18000a36d  jnz     short loc_18000A399
0x18000a36f  mov     [rbx+50h], esi
0x18000a372  mov     [rbx+60h], esi
0x18000a375  mov     [rbx+68h], rsi
0x18000a379  cmp     [rbx+10h], rsi
0x18000a37d  jnz     short loc_18000A3D1
0x18000a37f  mov     [rbx+8], esi
0x18000a382  mov     [rbx+18h], esi
0x18000a385  mov     [rbx+20h], rsi
0x18000a389  mov     rbx, [rsp+28h+arg_8]
0x18000a38e  mov     rsi, [rsp+28h+arg_10]
0x18000a393  add     rsp, 20h
0x18000a397  pop     rdi
0x18000a398  retn
0x18000a399  mov     edi, esi
0x18000a39b  cmp     [rbx+50h], esi
0x18000a39e  jle     short loc_18000A3C2
0x18000a3a0  movsxd  rcx, edi
0x18000a3a3  add     rcx, rcx
0x18000a3a6  mov     rax, [rbx+58h]
0x18000a3aa  cmp     [rax+rcx*8], si
0x18000a3ae  jnz     short loc_18000A3BB
0x18000a3b0  mov     rcx, [rax+rcx*8+8]; pv
0x18000a3b5  call    cs:__imp_CoTaskMemFree
0x18000a3bb  inc     edi
0x18000a3bd  cmp     edi, [rbx+50h]
0x18000a3c0  jl      short loc_18000A3A0
0x18000a3c2  mov     rcx, [rbx+58h]; void *
0x18000a3c6  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18000a3cb  mov     [rbx+58h], rsi
0x18000a3cf  jmp     short loc_18000A36F
0x18000a3d1  mov     edi, esi
0x18000a3d3  cmp     [rbx+8], esi
0x18000a3d6  jle     short loc_18000A3FA
0x18000a3d8  movsxd  rcx, edi
0x18000a3db  add     rcx, rcx
0x18000a3de  mov     rax, [rbx+10h]
0x18000a3e2  cmp     [rax+rcx*8], si
0x18000a3e6  jnz     short loc_18000A3F3
0x18000a3e8  mov     rcx, [rax+rcx*8+8]; pv
0x18000a3ed  call    cs:__imp_CoTaskMemFree
0x18000a3f3  inc     edi
0x18000a3f5  cmp     edi, [rbx+8]
0x18000a3f8  jl      short loc_18000A3D8
0x18000a3fa  mov     rcx, [rbx+10h]; void *
0x18000a3fe  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18000a403  mov     [rbx+10h], rsi
0x18000a407  jmp     loc_18000A37F
```
