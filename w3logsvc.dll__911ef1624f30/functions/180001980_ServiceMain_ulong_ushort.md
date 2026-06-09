# ServiceMain(ulong,ushort * *)

- ea: `0x180001980`
- end: `0x1800019aa`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `42`
- prototype: `void __fastcall(int, const wchar_t **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180001980`
- `0x1800019b0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001996`
- `msvcrt!_wcsicmp` at `0x180001996`

## pseudocode

```c
void __fastcall ServiceMain(int a1, const wchar_t **a2)
{
  if ( a1 == 1 && !_wcsicmp(*a2, L"w3logsvc") )
    W3LogServiceMain();
}

```

## disassembly

```asm
0x180001980  sub     rsp, 28h
0x180001984  mov     rax, rdx
0x180001987  cmp     ecx, 1
0x18000198a  jnz     short loc_1800019A5
0x18000198c  mov     rcx, [rax]; String1
0x18000198f  lea     rdx, aW3logsvc_1; "w3logsvc"
0x180001996  call    cs:__imp__wcsicmp
0x18000199c  test    eax, eax
0x18000199e  jnz     short loc_1800019A5
0x1800019a0  call    ?W3LogServiceMain@@YAXXZ; W3LogServiceMain(void)
0x1800019a5  add     rsp, 28h
0x1800019a9  retn
```
