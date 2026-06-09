# WriteFileView::UpdateBothCRCValues(void)

- ea: `0x180035894`
- end: `0x1800358e1`
- name: `?UpdateBothCRCValues@WriteFileView@@QEAAXXZ`
- size: `77`
- prototype: `void __fastcall(WriteFileView *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800315f8`
- `0x180032dbc`

## callees

- `0x180033b4c`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x1800358b8`
- `ntdll!RtlComputeCrc32` at `0x1800358b8`

## pseudocode

```c
void __fastcall WriteFileView::UpdateBothCRCValues(WriteFileView *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8

  *(_DWORD *)(*((_QWORD *)this + 1) + 52LL) = RtlComputeCrc32(
                                                0,
                                                (PUCHAR)(*((_QWORD *)this + 3) + 512LL),
                                                *(_DWORD *)(*((_QWORD *)this + 1) + 48LL) - 512);
  *(_DWORD *)(*((_QWORD *)this + 1) + 124LL) = CalcGeneralHeaderCRC(*((PUCHAR *)this + 1), v2, v3, 512);
}

```

## disassembly

```asm
0x180035894  push    rbx
0x180035896  sub     rsp, 20h
0x18003589a  mov     r9, [rcx+18h]
0x18003589e  mov     rbx, rcx
0x1800358a1  mov     rax, [rcx+8]
0x1800358a5  xor     ecx, ecx; InitialCrc
0x1800358a7  lea     rdx, [r9+200h]; Buffer
0x1800358ae  mov     r8d, [rax+30h]
0x1800358b2  sub     r8d, edx
0x1800358b5  add     r8d, r9d; Length
0x1800358b8  call    cs:__imp_RtlComputeCrc32
0x1800358be  mov     rcx, [rbx+8]
0x1800358c2  mov     r9d, 200h; unsigned int
0x1800358c8  mov     [rcx+34h], eax
0x1800358cb  mov     rcx, [rbx+8]; Buffer
0x1800358cf  call    ?CalcGeneralHeaderCRC@@YAKPEBEKKK@Z; CalcGeneralHeaderCRC(uchar const *,ulong,ulong,ulong)
0x1800358d4  mov     rcx, [rbx+8]
0x1800358d8  mov     [rcx+7Ch], eax
0x1800358db  add     rsp, 20h
0x1800358df  pop     rbx
0x1800358e0  retn
```
