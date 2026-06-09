# SP_HLOCAL<uchar>::operator=(CTypeWrapper<uchar *>)

- ea: `0x18003ad54`
- end: `0x18003ad8a`
- name: `??4?$SP_HLOCAL@E@@QEAAAEAV0@V?$CTypeWrapper@PEAE@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`

## callees

- `0x18003ad54`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ad6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ad6c`

## pseudocode

```c
void **__fastcall SP_HLOCAL<unsigned char>::operator=(void **a1, void *a2)
{
  void *v4; // rcx

  v4 = *a1;
  if ( v4 )
    LocalFree(v4);
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x18003ad54  mov     [rsp+arg_0], rbx
0x18003ad59  push    rdi
0x18003ad5a  sub     rsp, 20h
0x18003ad5e  mov     rdi, rcx
0x18003ad61  mov     rbx, rdx
0x18003ad64  mov     rcx, [rcx]; hMem
0x18003ad67  test    rcx, rcx
0x18003ad6a  jz      short loc_18003AD78
0x18003ad6c  call    cs:__imp_LocalFree
0x18003ad73  nop     dword ptr [rax+rax+00h]
0x18003ad78  mov     [rdi], rbx
0x18003ad7b  mov     rax, rdi
0x18003ad7e  mov     rbx, [rsp+28h+arg_0]
0x18003ad83  add     rsp, 20h
0x18003ad87  pop     rdi
0x18003ad88  retn
```
