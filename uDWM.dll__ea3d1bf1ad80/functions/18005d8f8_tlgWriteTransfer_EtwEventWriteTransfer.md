# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x18005d8f8`
- end: `0x18005d98f`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `23`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001008`
- `0x180001100`
- `0x1800013d8`
- `0x1800014ac`
- `0x180001570`
- `0x180001824`
- `0x180001b40`
- `0x180001b88`
- `0x180001e9c`
- `0x180001f98`
- `0x18000223c`
- `0x1800022dc`
- `0x18000236c`
- `0x180002408`
- `0x18005d600`
- `0x18005d690`
- `0x18005d708`
- `0x18005d76c`
- `0x18005d7cc`
- `0x18005d860`
- `0x18007beb4`
- `0x1800a3504`
- `0x1800a3634`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18005d984`
- `ntdll!EtwEventWriteTransfer` at `0x18005d984`

## pseudocode

```c
__int64 __fastcall tlgWriteTransfer_EtwEventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // rax
  unsigned __int16 *v7; // rdx
  _DWORD v9[2]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+38h] [rbp-10h]

  v9[0] = *a2 << 24;
  v9[1] = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  v10 = v6;
  *(_QWORD *)a6 = *(_QWORD *)(a1 + 8);
  *(_DWORD *)(a6 + 8) = **(unsigned __int16 **)(a1 + 8);
  *(_QWORD *)(a6 + 16) = v7;
  *(_DWORD *)(a6 + 12) = 2;
  *(_DWORD *)(a6 + 24) = *v7;
  *(_DWORD *)(a6 + 28) = 1;
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v9, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x18005d8f8  sub     rsp, 48h
0x18005d8fc  movzx   eax, byte ptr [rdx]
0x18005d8ff  mov     r11, rcx
0x18005d902  shl     eax, 18h
0x18005d905  mov     r10, r8
0x18005d908  mov     r8, [rsp+48h+arg_28]
0x18005d90d  mov     [rsp+48h+var_18], eax
0x18005d911  movzx   eax, word ptr [rdx+1]
0x18005d915  mov     [rsp+48h+var_14], eax
0x18005d919  mov     rax, [rdx+3]
0x18005d91d  add     rdx, 0Bh
0x18005d921  mov     [rsp+48h+var_10], rax
0x18005d926  mov     rax, [rcx+8]
0x18005d92a  mov     [r8], rax
0x18005d92d  mov     rax, [rcx+8]
0x18005d931  mov     [rsp+48h+var_20], r8
0x18005d936  movzx   ecx, word ptr [rax]
0x18005d939  mov     [r8+8], ecx
0x18005d93d  lea     rcx, _TraceLoggingMetadata
0x18005d944  mov     [r8+10h], rdx
0x18005d948  mov     dword ptr [r8+0Ch], 2
0x18005d950  movzx   eax, word ptr [rdx]
0x18005d953  lea     rdx, [rsp+48h+var_18]
0x18005d958  mov     [r8+18h], eax
0x18005d95c  lea     rax, _TraceLoggingMetadataEnd
0x18005d963  sub     eax, ecx
0x18005d965  mov     dword ptr [r8+1Ch], 1
0x18005d96d  mov     dword ptr [rsp+48h+arg_28], eax
0x18005d971  mov     r8, r10
0x18005d974  mov     eax, dword ptr [rsp+48h+arg_28]
0x18005d978  mov     eax, [rsp+48h+arg_20]
0x18005d97c  mov     rcx, [r11+20h]
0x18005d980  mov     [rsp+48h+var_28], eax
0x18005d984  call    cs:__imp_EtwEventWriteTransfer
0x18005d98a  add     rsp, 48h
0x18005d98e  retn
```
