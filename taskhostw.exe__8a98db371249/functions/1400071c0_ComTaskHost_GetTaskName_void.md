# ComTaskHost::GetTaskName(void)

- ea: `0x1400071c0`
- end: `0x1400071ce`
- name: `?GetTaskName@ComTaskHost@@UEAAPEBGXZ`
- size: `14`
- prototype: `const unsigned __int16 *__fastcall(ComTaskHost *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400071c0`

## pseudocode

```c
const unsigned __int16 *__fastcall ComTaskHost::GetTaskName(ComTaskHost *this)
{
  const unsigned __int16 *result; // rax

  result = (const unsigned __int16 *)*((_QWORD *)this + 5);
  if ( result )
    return *(const unsigned __int16 **)result;
  return result;
}

```

## disassembly

```asm
0x1400071c0  mov     rax, [rcx+28h]
0x1400071c4  test    rax, rax
0x1400071c7  jz      short locret_1400071CD
0x1400071c9  mov     rax, [rax]
0x1400071cc  retn
0x1400071cd  retn
```
