# CalcGeneralHeaderCRC(uchar const *,ulong,ulong,ulong)

- ea: `0x180033b4c`
- end: `0x180033b8b`
- name: `?CalcGeneralHeaderCRC@@YAKPEBEKKK@Z`
- size: `63`
- prototype: `unsigned int __fastcall(PUCHAR Buffer, unsigned int, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033078`
- `0x180033cdc`
- `0x180033de0`
- `0x180033f34`
- `0x180035894`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x180033b67`
- `ntdll!RtlComputeCrc32` at `0x180033b67`
- `ntdll!RtlComputeCrc32` at `0x180033b84`

## pseudocode

```c
ULONG __fastcall CalcGeneralHeaderCRC(PUCHAR Buffer, __int64 a2, __int64 a3, int a4)
{
  ULONG v6; // eax

  v6 = RtlComputeCrc32(0, Buffer, 0x78u);
  return RtlComputeCrc32(v6, Buffer + 128, a4 - 128);
}

```

## disassembly

```asm
0x180033b4c  mov     [rsp+arg_0], rbx
0x180033b51  push    rdi
0x180033b52  sub     rsp, 20h
0x180033b56  mov     rbx, rcx
0x180033b59  mov     rdx, rcx; Buffer
0x180033b5c  xor     ecx, ecx; InitialCrc
0x180033b5e  mov     r8d, 78h ; 'x'; Length
0x180033b64  mov     edi, r9d
0x180033b67  call    cs:__imp_RtlComputeCrc32
0x180033b6d  mov     ecx, eax
0x180033b6f  lea     r8d, [rdi-80h]
0x180033b73  lea     rdx, [rbx+80h]
0x180033b7a  mov     rbx, [rsp+28h+arg_0]
0x180033b7f  add     rsp, 20h
0x180033b83  pop     rdi
0x180033b84  jmp     cs:__imp_RtlComputeCrc32
```
