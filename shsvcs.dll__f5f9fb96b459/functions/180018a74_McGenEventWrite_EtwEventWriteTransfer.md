# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180018a74`
- end: `0x180018ac6`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001530`
- `0x180005b30`
- `0x180006750`
- `0x1800074c0`
- `0x1800077e0`
- `0x180027350`
- `0x180028988`
- `0x180028a28`

## callees

- `0x180018a74`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180018abb`
- `ntdll!EtwEventWriteTransfer` at `0x180018abb`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_18003E018;
  if ( qword_18003E018 )
  {
    *(_QWORD *)a5 = qword_18003E018;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v6 = 0;
  }
  *(_DWORD *)(a5 + 8) = (_DWORD)v5;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWriteTransfer(Microsoft_Windows_Shsvcs_Provider_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x180018a74  sub     rsp, 38h
0x180018a78  mov     rcx, cs:qword_18003E018
0x180018a7f  mov     rax, [rsp+38h+arg_20]
0x180018a84  test    rcx, rcx
0x180018a87  jnz     short loc_180018A91
0x180018a89  mov     [rax], rcx
0x180018a8c  xor     r8d, r8d
0x180018a8f  jmp     short loc_180018A9D
0x180018a91  mov     [rax], rcx
0x180018a94  mov     r8d, 2
0x180018a9a  movzx   ecx, word ptr [rcx]
0x180018a9d  mov     [rax+8], ecx
0x180018aa0  mov     [rax+0Ch], r8d
0x180018aa4  xor     r8d, r8d
0x180018aa7  mov     rcx, cs:Microsoft_Windows_Shsvcs_Provider_Context
0x180018aae  mov     [rsp+38h+var_10], rax
0x180018ab3  mov     [rsp+38h+var_18], r9d
0x180018ab8  xor     r9d, r9d
0x180018abb  call    cs:__imp_EtwEventWriteTransfer
0x180018ac1  add     rsp, 38h
0x180018ac5  retn
```
