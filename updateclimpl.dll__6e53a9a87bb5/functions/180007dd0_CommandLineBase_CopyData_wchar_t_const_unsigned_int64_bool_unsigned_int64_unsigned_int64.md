# CommandLineBase::CopyData(wchar_t const * *,unsigned __int64,bool *,unsigned __int64,unsigned __int64 *)

- ea: `0x180007dd0`
- end: `0x180007de3`
- name: `?CopyData@CommandLineBase@@SAJPEAPEB_W_KPEA_N1PEA_K@Z`
- size: `19`
- prototype: `__int64 __fastcall(const wchar_t **, __int64, bool *, __int64, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CommandLineBase::CopyData(
        const wchar_t **a1,
        __int64 a2,
        bool *a3,
        __int64 a4,
        unsigned __int64 *a5)
{
  *a3 = 1;
  *a5 = 0;
  return 0;
}

```

## disassembly

```asm
0x180007dd0  mov     rax, [rsp+arg_20]
0x180007dd5  mov     byte ptr [r8], 1
0x180007dd9  mov     qword ptr [rax], 0
0x180007de0  xor     eax, eax
0x180007de2  retn
```
