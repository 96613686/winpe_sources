# TdxCleanupObjectHeader

- ea: `0x140008c50`
- end: `0x140008c7f`
- name: `TdxCleanupObjectHeader`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003840`
- `0x1400054ec`
- `0x140006b40`
- `0x140006db0`
- `0x1400075b0`
- `0x140007b90`
- `0x140008620`
- `0x1400087a0`
- `0x140008c90`
- `0x140009010`
- `0x140009290`
- `0x140009ad0`
- `0x14000a040`
- `0x14000a5f0`
- `0x14000a908`

## callees

- `0x140008c50`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140008c6d`
- `ntoskrnl!IofCompleteRequest` at `0x140008c6d`

## pseudocode

```c
void __fastcall TdxCleanupObjectHeader(__int64 a1)
{
  IRP *v2; // rcx

  v2 = *(IRP **)(a1 + 48);
  if ( v2 )
  {
    v2->IoStatus.Status = 0;
    v2->IoStatus.Information = 0;
    *(_QWORD *)(a1 + 48) = 0;
    IofCompleteRequest(v2, 0);
  }
}

```

## disassembly

```asm
0x140008c50  sub     rsp, 28h
0x140008c54  mov     rax, rcx
0x140008c57  mov     rcx, [rcx+30h]; Irp
0x140008c5b  test    rcx, rcx
0x140008c5e  jz      short loc_140008C79
0x140008c60  xor     edx, edx; PriorityBoost
0x140008c62  mov     [rcx+30h], edx
0x140008c65  mov     [rcx+38h], rdx
0x140008c69  mov     [rax+30h], rdx
0x140008c6d  call    cs:__imp_IofCompleteRequest
0x140008c74  nop     dword ptr [rax+rax+00h]
0x140008c79  add     rsp, 28h
0x140008c7d  retn
```
