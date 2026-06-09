# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x1800180fc`
- end: `0x18001814e`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017ee0`
- `0x180018154`

## callees

- `0x1800180fc`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180018143`
- `ntdll!EtwEventWriteTransfer` at `0x180018143`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180028098;
  if ( qword_180028098 )
  {
    *(_QWORD *)a5 = qword_180028098;
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
0x1800180fc  sub     rsp, 38h
0x180018100  mov     rcx, cs:qword_180028098
0x180018107  mov     rax, [rsp+38h+arg_20]
0x18001810c  test    rcx, rcx
0x18001810f  jnz     short loc_180018119
0x180018111  mov     [rax], rcx
0x180018114  xor     r8d, r8d
0x180018117  jmp     short loc_180018125
0x180018119  mov     [rax], rcx
0x18001811c  mov     r8d, 2
0x180018122  movzx   ecx, word ptr [rcx]
0x180018125  mov     [rax+8], ecx
0x180018128  mov     [rax+0Ch], r8d
0x18001812c  xor     r8d, r8d
0x18001812f  mov     rcx, cs:S_Microsoft_Windows_Userenv_Context
0x180018136  mov     [rsp+38h+var_10], rax
0x18001813b  mov     [rsp+38h+var_18], r9d
0x180018140  xor     r9d, r9d
0x180018143  call    cs:__imp_EtwEventWriteTransfer
0x180018149  add     rsp, 38h
0x18001814d  retn
```
