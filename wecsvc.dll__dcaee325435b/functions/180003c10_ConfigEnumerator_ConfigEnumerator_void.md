# ConfigEnumerator::~ConfigEnumerator(void)

- ea: `0x180003c10`
- end: `0x180003c40`
- name: `??1ConfigEnumerator@@UEAA@XZ`
- size: `48`
- prototype: `void __fastcall(ConfigEnumerator *this, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003c7c`
- `0x180004434`
- `0x180005ad0`
- `0x180015530`
- `0x1800222ae`

## callees

- `0x1800062d4`
- `0x180011d6c`

## pseudocode

```c
void __fastcall ConfigEnumerator::~ConfigEnumerator(ConfigEnumerator *this, __int64 a2)
{
  LOBYTE(a2) = 1;
  std::wstring::_Tidy((char *)this + 80, a2, 0);
  RegistryKeyEnumerator::~RegistryKeyEnumerator((ConfigEnumerator *)((char *)this + 16));
  *(_QWORD *)this = &wmi::RefBase::`vftable';
}

```

## disassembly

```asm
0x180003c10  push    rbx
0x180003c12  sub     rsp, 20h
0x180003c16  mov     rbx, rcx
0x180003c19  xor     r8d, r8d
0x180003c1c  add     rcx, 50h ; 'P'
0x180003c20  mov     dl, 1
0x180003c22  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180003c27  lea     rcx, [rbx+10h]; this
0x180003c2b  call    ??1RegistryKeyEnumerator@@QEAA@XZ; RegistryKeyEnumerator::~RegistryKeyEnumerator(void)
0x180003c30  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180003c37  mov     [rbx], rax
0x180003c3a  add     rsp, 20h
0x180003c3e  pop     rbx
0x180003c3f  retn
```
