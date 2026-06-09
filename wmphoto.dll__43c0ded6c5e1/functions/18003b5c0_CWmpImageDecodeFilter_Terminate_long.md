# CWmpImageDecodeFilter::Terminate(long)

- ea: `0x18003b5c0`
- end: `0x18003b600`
- name: `?Terminate@CWmpImageDecodeFilter@@UEAAJJ@Z`
- size: `64`
- prototype: `__int64 __fastcall(LPVOID *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003b5c0`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b5cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b5cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWmpImageDecodeFilter::Terminate(LPVOID *this)
{
  LPVOID v2; // rcx

  CoTaskMemFree(this[3]);
  v2 = this[1];
  this[3] = 0;
  if ( v2 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
    this[1] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18003b5c0  push    rbx
0x18003b5c2  sub     rsp, 20h
0x18003b5c6  mov     rbx, rcx
0x18003b5c9  mov     rcx, [rcx+18h]; pv
0x18003b5cd  call    cs:__imp_CoTaskMemFree
0x18003b5d3  mov     rcx, [rbx+8]
0x18003b5d7  mov     qword ptr [rbx+18h], 0
0x18003b5df  test    rcx, rcx
0x18003b5e2  jz      short loc_18003B5F8
0x18003b5e4  mov     rax, [rcx]
0x18003b5e7  mov     rax, [rax+10h]
0x18003b5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5f0  mov     qword ptr [rbx+8], 0
0x18003b5f8  xor     eax, eax
0x18003b5fa  add     rsp, 20h
0x18003b5fe  pop     rbx
0x18003b5ff  retn
```
