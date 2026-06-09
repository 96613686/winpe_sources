# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x18000db74`
- end: `0x18000dbcb`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d9e8`
- `0x18000ff40`
- `0x1800104f8`
- `0x18001386d`

## callees

- `0x18000db74`
- `0x18000e6bc`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this, void *a2)
{
  wil::details *v3; // rcx
  wil::details *v4; // rcx
  wil::details *v5; // rcx

  v3 = (wil::details *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v3 )
    wil::details::FreeProcessHeap(v3, a2);
  v4 = (wil::details *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
    wil::details::FreeProcessHeap(v4, a2);
  v5 = (wil::details *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v5 )
    wil::details::FreeProcessHeap(v5, a2);
}

```

## disassembly

```asm
0x18000db74  push    rbx
0x18000db76  sub     rsp, 20h
0x18000db7a  mov     rbx, rcx
0x18000db7d  mov     rcx, [rcx+0B0h]; this
0x18000db84  mov     qword ptr [rbx+0B0h], 0
0x18000db8f  test    rcx, rcx
0x18000db92  jz      short loc_18000DB99
0x18000db94  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000db99  mov     rcx, [rbx+70h]; this
0x18000db9d  mov     qword ptr [rbx+70h], 0
0x18000dba5  test    rcx, rcx
0x18000dba8  jz      short loc_18000DBAF
0x18000dbaa  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000dbaf  mov     rcx, [rbx+30h]; this
0x18000dbb3  mov     qword ptr [rbx+30h], 0
0x18000dbbb  test    rcx, rcx
0x18000dbbe  jz      short loc_18000DBC5
0x18000dbc0  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000dbc5  add     rsp, 20h
0x18000dbc9  pop     rbx
0x18000dbca  retn
```
