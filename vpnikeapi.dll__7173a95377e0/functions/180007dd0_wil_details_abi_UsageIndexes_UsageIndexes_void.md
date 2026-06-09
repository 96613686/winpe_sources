# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180007dd0`
- end: `0x180007e27`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ca0`
- `0x18000a028`
- `0x18000a65c`

## callees

- `0x180007dd0`
- `0x18000882c`

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
0x180007dd0  push    rbx
0x180007dd2  sub     rsp, 20h
0x180007dd6  mov     rbx, rcx
0x180007dd9  mov     rcx, [rcx+0B0h]; this
0x180007de0  mov     qword ptr [rbx+0B0h], 0
0x180007deb  test    rcx, rcx
0x180007dee  jz      short loc_180007DF5
0x180007df0  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007df5  mov     rcx, [rbx+70h]; this
0x180007df9  mov     qword ptr [rbx+70h], 0
0x180007e01  test    rcx, rcx
0x180007e04  jz      short loc_180007E0B
0x180007e06  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007e0b  mov     rcx, [rbx+30h]; this
0x180007e0f  mov     qword ptr [rbx+30h], 0
0x180007e17  test    rcx, rcx
0x180007e1a  jz      short loc_180007E21
0x180007e1c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007e21  add     rsp, 20h
0x180007e25  pop     rbx
0x180007e26  retn
```
