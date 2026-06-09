# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180019a1c`
- end: `0x180019a75`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800197f0`
- `0x180019a7c`

## callees

- `0x180019a1c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180019a63`
- `ntdll!EtwEventWriteTransfer` at `0x180019a63`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180029098;
  if ( qword_180029098 )
  {
    *(_QWORD *)a5 = qword_180029098;
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
  return EtwEventWriteTransfer(S_Microsoft_Windows_Userenv_Context, a2, 0);
}

```

## disassembly

```asm
0x180019a1c  sub     rsp, 38h
0x180019a20  mov     rcx, cs:qword_180029098
0x180019a27  mov     rax, [rsp+38h+arg_20]
0x180019a2c  test    rcx, rcx
0x180019a2f  jnz     short loc_180019A39
0x180019a31  mov     [rax], rcx
0x180019a34  xor     r8d, r8d
0x180019a37  jmp     short loc_180019A45
0x180019a39  mov     [rax], rcx
0x180019a3c  mov     r8d, 2
0x180019a42  movzx   ecx, word ptr [rcx]
0x180019a45  mov     [rax+8], ecx
0x180019a48  mov     [rax+0Ch], r8d
0x180019a4c  xor     r8d, r8d
0x180019a4f  mov     rcx, cs:S_Microsoft_Windows_Userenv_Context
0x180019a56  mov     [rsp+38h+var_10], rax
0x180019a5b  mov     [rsp+38h+var_18], r9d
0x180019a60  xor     r9d, r9d
0x180019a63  call    cs:__imp_EtwEventWriteTransfer
0x180019a6a  nop     dword ptr [rax+rax+00h]
0x180019a6f  add     rsp, 38h
0x180019a73  retn
```
