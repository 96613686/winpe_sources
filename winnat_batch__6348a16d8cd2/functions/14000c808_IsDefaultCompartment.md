# IsDefaultCompartment

- ea: `0x14000c808`
- end: `0x14000c876`
- name: `IsDefaultCompartment`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140033cc8`

## callees

- `0x14000c808`

## import_xrefs

- `NETIO!NsiGetParameter` at `0x14000c854`
- `NETIO!NsiGetParameter` at `0x14000c854`

## pseudocode

```c
bool __fastcall IsDefaultCompartment(__int64 a1)
{
  __int64 v2; // [rsp+60h] [rbp+8h] BYREF
  int v3; // [rsp+68h] [rbp+10h] BYREF

  v2 = a1;
  v3 = 0;
  return (int)NsiGetParameter(1, &NPI_MS_NDIS_MODULEID, 0, &v2, 8, 1, &v3, 4, 208) >= 0 && v3 == 1;
}

```

## disassembly

```asm
0x14000c808  mov     rax, rsp
0x14000c80b  mov     [rax+8], rcx
0x14000c80f  sub     rsp, 58h
0x14000c813  mov     dword ptr [rax-18h], 0D0h
0x14000c81a  xor     r8d, r8d
0x14000c81d  mov     dword ptr [rax-20h], 4
0x14000c824  lea     r9, [rsp+58h+arg_0]
0x14000c829  mov     dword ptr [rax+10h], 0
0x14000c830  lea     rax, [rax+10h]
0x14000c834  mov     [rsp+58h+var_28], rax
0x14000c839  lea     rdx, NPI_MS_NDIS_MODULEID
0x14000c840  mov     [rsp+58h+var_30], 1
0x14000c848  lea     ecx, [r8+1]
0x14000c84c  mov     [rsp+58h+var_38], 8
0x14000c854  call    cs:__imp_NsiGetParameter
0x14000c85b  nop     dword ptr [rax+rax+00h]
0x14000c860  test    eax, eax
0x14000c862  js      short loc_14000C86E
0x14000c864  cmp     [rsp+58h+arg_8], 1
0x14000c869  setz    al
0x14000c86c  jmp     short loc_14000C870
0x14000c86e  xor     al, al
0x14000c870  add     rsp, 58h
0x14000c874  retn
```
