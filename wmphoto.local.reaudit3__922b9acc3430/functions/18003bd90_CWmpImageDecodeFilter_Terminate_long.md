# CWmpImageDecodeFilter::Terminate(long)

- ea: `0x18003bd90`
- end: `0x18003bdd7`
- name: `?Terminate@CWmpImageDecodeFilter@@UEAAJJ@Z`
- size: `71`
- prototype: `__int64 __fastcall(CWmpImageDecodeFilter *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003bd90`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd9d`

## pseudocode

```c
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
0x18003bd90  push    rbx
0x18003bd92  sub     rsp, 20h
0x18003bd96  mov     rbx, rcx
0x18003bd99  mov     rcx, [rcx+18h]; pv
0x18003bd9d  call    cs:__imp_CoTaskMemFree
0x18003bda4  nop     dword ptr [rax+rax+00h]
0x18003bda9  mov     rcx, [rbx+8]
0x18003bdad  mov     qword ptr [rbx+18h], 0
0x18003bdb5  test    rcx, rcx
0x18003bdb8  jz      short loc_18003BDCE
0x18003bdba  mov     rax, [rcx]
0x18003bdbd  mov     rax, [rax+10h]
0x18003bdc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdc6  mov     qword ptr [rbx+8], 0
0x18003bdce  xor     eax, eax
0x18003bdd0  add     rsp, 20h
0x18003bdd4  pop     rbx
0x18003bdd5  retn
```
