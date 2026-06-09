# WinHvpGetPartitionNodeRequirement

- ea: `0x14000794c`
- end: `0x140007977`
- name: `WinHvpGetPartitionNodeRequirement`
- size: `43`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140009750`
- `0x14001fbb0`
- `0x14001fd40`
- `0x140020a30`

## callees

- `0x1400024d0`
- `0x140002bf0`
- `0x14000794c`

## pseudocode

```c
__int64 __fastcall WinHvpGetPartitionNodeRequirement(unsigned __int64 a1)
{
  volatile signed __int64 *v1; // rax
  unsigned int v3; // ebx

  v1 = WinHvpReferencePartition(a1);
  if ( !v1 )
    return 0xFFFF;
  v3 = *((_DWORD *)v1 + 10);
  WinHvpDereferencePartition(v1);
  return v3;
}

```

## disassembly

```asm
0x14000794c  push    rbx
0x14000794e  sub     rsp, 20h
0x140007952  call    WinHvpReferencePartition
0x140007957  test    rax, rax
0x14000795a  jnz     short loc_140007963
0x14000795c  mov     eax, 0FFFFh
0x140007961  jmp     short loc_140007970
0x140007963  mov     ebx, [rax+28h]
0x140007966  mov     rcx, rax
0x140007969  call    WinHvpDereferencePartition
0x14000796e  mov     eax, ebx
0x140007970  add     rsp, 20h
0x140007974  pop     rbx
0x140007975  retn
```
