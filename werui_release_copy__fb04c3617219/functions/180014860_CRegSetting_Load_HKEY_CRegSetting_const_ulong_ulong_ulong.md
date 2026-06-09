# CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)

- ea: `0x180014860`
- end: `0x1800148a2`
- name: `?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z`
- size: `66`
- prototype: `__int64 __fastcall(HKEY, struct CRegSetting *const, unsigned int, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800148a8`

## callees

- `0x180009d14`
- `0x180014860`

## pseudocode

```c
__int64 __fastcall CRegSetting::Load(HKEY a1, struct CRegSetting *const a2, __int64 a3, unsigned int *a4)
{
  __int64 i; // rbx
  __int64 result; // rax

  for ( i = 0; i != 7; ++i )
    result = CRegSetting::Load((struct CRegSetting *const)((char *)a2 + 104 * i), a1, 0);
  return result;
}

```

## disassembly

```asm
0x180014860  mov     [rsp+arg_0], rbx
0x180014865  mov     [rsp+arg_8], rsi
0x18001486a  push    rdi
0x18001486b  sub     rsp, 20h
0x18001486f  mov     rdi, rdx
0x180014872  mov     rsi, rcx
0x180014875  xor     ebx, ebx
0x180014877  imul    rcx, rbx, 68h ; 'h'
0x18001487b  xor     r8d, r8d; unsigned int
0x18001487e  mov     rdx, rsi; HKEY
0x180014881  add     rcx, rdi; this
0x180014884  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x180014889  inc     rbx
0x18001488c  cmp     rbx, 7
0x180014890  jnz     short loc_180014877
0x180014892  mov     rbx, [rsp+28h+arg_0]
0x180014897  mov     rsi, [rsp+28h+arg_8]
0x18001489c  add     rsp, 20h
0x1800148a0  pop     rdi
0x1800148a1  retn
```
