# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180013744`
- end: `0x180013799`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `85`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012e30`
- `0x180013090`
- `0x180016b80`
- `0x180016f60`
- `0x180019ff0`

## callees

- `0x180013744`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18001378e`
- `ntdll!EtwEventWriteTransfer` at `0x18001378e`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_1800485A8;
  if ( qword_1800485A8 )
  {
    *(_QWORD *)a5 = qword_1800485A8;
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
  return EtwEventWriteTransfer(Microsoft_Windows_WCNWiz_Context, a2, 0, 0, 1, a5);
}

```

## disassembly

```asm
0x180013744  sub     rsp, 38h
0x180013748  mov     rcx, cs:qword_1800485A8
0x18001374f  mov     rax, [rsp+38h+arg_20]
0x180013754  test    rcx, rcx
0x180013757  jnz     short loc_180013761
0x180013759  mov     [rax], rcx
0x18001375c  xor     r8d, r8d
0x18001375f  jmp     short loc_18001376D
0x180013761  mov     [rax], rcx
0x180013764  mov     r8d, 2
0x18001376a  movzx   ecx, word ptr [rcx]
0x18001376d  mov     [rax+8], ecx
0x180013770  xor     r9d, r9d
0x180013773  mov     [rax+0Ch], r8d
0x180013777  xor     r8d, r8d
0x18001377a  mov     rcx, cs:Microsoft_Windows_WCNWiz_Context
0x180013781  mov     [rsp+38h+var_10], rax
0x180013786  mov     [rsp+38h+var_18], 1
0x18001378e  call    cs:__imp_EtwEventWriteTransfer
0x180013794  add     rsp, 38h
0x180013798  retn
```
