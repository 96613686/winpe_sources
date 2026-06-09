# WriteFileView::UpdateBothCRCValues(void)

- ea: `0x18000a108`
- end: `0x18000a179`
- name: `?UpdateBothCRCValues@WriteFileView@@QEAAXXZ`
- size: `113`
- prototype: `void __fastcall(WriteFileView *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180009c5c`
- `0x1800b29b8`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x18000a130`
- `ntdll!RtlComputeCrc32` at `0x18000a14c`
- `ntdll!RtlComputeCrc32` at `0x18000a161`
- `ntdll!RtlComputeCrc32` at `0x18000a130`
- `ntdll!RtlComputeCrc32` at `0x18000a14c`
- `ntdll!RtlComputeCrc32` at `0x18000a161`

## pseudocode

```c
void __fastcall WriteFileView::UpdateBothCRCValues(WriteFileView *this)
{
  UCHAR *v2; // rbx
  ULONG v3; // eax

  *(_DWORD *)(*((_QWORD *)this + 1) + 52LL) = RtlComputeCrc32(
                                                0,
                                                (PUCHAR)(*((_QWORD *)this + 3) + 512LL),
                                                *(_DWORD *)(*((_QWORD *)this + 1) + 48LL) - 512);
  v2 = (UCHAR *)*((_QWORD *)this + 1);
  v3 = RtlComputeCrc32(0, v2, 0x78u);
  *(_DWORD *)(*((_QWORD *)this + 1) + 124LL) = RtlComputeCrc32(v3, v2 + 128, 0x180u);
}

```

## disassembly

```asm
0x18000a108  mov     [rsp+arg_0], rbx
0x18000a10d  push    rdi
0x18000a10e  sub     rsp, 20h
0x18000a112  mov     r9, [rcx+18h]
0x18000a116  mov     rdi, rcx
0x18000a119  mov     rax, [rcx+8]
0x18000a11d  xor     ecx, ecx; InitialCrc
0x18000a11f  lea     rdx, [r9+200h]; Buffer
0x18000a126  mov     r8d, [rax+30h]
0x18000a12a  sub     r8d, edx
0x18000a12d  add     r8d, r9d; Length
0x18000a130  call    cs:__imp_RtlComputeCrc32
0x18000a136  mov     rcx, [rdi+8]
0x18000a13a  mov     r8d, 78h ; 'x'; Length
0x18000a140  mov     [rcx+34h], eax
0x18000a143  xor     ecx, ecx; InitialCrc
0x18000a145  mov     rbx, [rdi+8]
0x18000a149  mov     rdx, rbx; Buffer
0x18000a14c  call    cs:__imp_RtlComputeCrc32
0x18000a152  lea     rdx, [rbx+80h]; Buffer
0x18000a159  mov     r8d, 180h; Length
0x18000a15f  mov     ecx, eax; InitialCrc
0x18000a161  call    cs:__imp_RtlComputeCrc32
0x18000a167  mov     rcx, [rdi+8]
0x18000a16b  mov     rbx, [rsp+28h+arg_0]
0x18000a170  mov     [rcx+7Ch], eax
0x18000a173  add     rsp, 20h
0x18000a177  pop     rdi
0x18000a178  retn
```
