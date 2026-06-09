# CommandImpl::GetArguments(CommandLineArg * *,unsigned __int64 *)

- ea: `0x180008e10`
- end: `0x180008e22`
- name: `?GetArguments@CommandImpl@@EEAAXPEAPEAUCommandLineArg@@PEA_K@Z`
- size: `18`
- prototype: `void __fastcall(CommandImpl *__hidden this, struct CommandLineArg **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void __fastcall CommandImpl::GetArguments(CommandImpl *this, struct CommandLineArg **a2, unsigned __int64 *a3)
{
  *a2 = (struct CommandLineArg *)&`CommandImpl::GetArguments'::`2'::s_args;
  *a3 = 4;
}

```

## disassembly

```asm
0x180008e10  lea     rax, ?s_args@?1??GetArguments@CommandImpl@@EEAAXPEAPEAUCommandLineArg@@PEA_K@Z@4PAU3@A; CommandLineArg near * `CommandImpl::GetArguments(CommandLineArg * *,unsigned __int64 *)'::`2'::s_args
0x180008e17  mov     [rdx], rax
0x180008e1a  mov     qword ptr [r8], 4
0x180008e21  retn
```
