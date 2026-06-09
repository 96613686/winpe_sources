# WinHvpDereferencePartition

- ea: `0x1400024d0`
- end: `0x140002505`
- name: `WinHvpDereferencePartition`
- size: `53`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ef0`
- `0x140002358`
- `0x140002454`
- `0x140004870`
- `0x140007310`
- `0x140007760`
- `0x1400077b0`
- `0x14000794c`
- `0x1400079f0`
- `0x140007bec`
- `0x140007cc4`
- `0x140007d0c`
- `0x140008df4`
- `0x140009750`
- `0x14000bf34`
- `0x14001f990`
- `0x14001fb40`
- `0x140020130`
- `0x1400204a4`
- `0x140024020`

## callees

- `0x1400024d0`
- `0x140007828`

## pseudocode

```c
__int64 __fastcall WinHvpDereferencePartition(volatile signed __int64 *a1)
{
  signed __int64 v1; // rax
  bool v2; // cc
  __int64 result; // rax

  v1 = _InterlockedExchangeAdd64(a1, 0xFFFFFFFFFFFFFFFFuLL);
  v2 = v1 <= 1;
  result = v1 - 1;
  if ( v2 )
  {
    if ( result )
      __fastfail(0xEu);
    return WinHvpDeletePartitionObject((__int64)a1);
  }
  return result;
}

```

## disassembly

```asm
0x1400024d0  sub     rsp, 28h
0x1400024d4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400024db  lock xadd [rcx], rax
0x1400024e0  sub     rax, 1
0x1400024e4  jle     short loc_1400024EC
0x1400024e6  add     rsp, 28h
0x1400024ea  retn
0x1400024ec  test    rax, rax
0x1400024ef  jz      short loc_1400024FE
0x1400024f1  mov     ecx, 0Eh
0x1400024f6  int     29h; Win8: RtlFailFast(ecx)
0x1400024f8  add     rsp, 28h
0x1400024fc  retn
0x1400024fe  call    WinHvpDeletePartitionObject
0x140002503  jmp     short loc_1400024E6
```
