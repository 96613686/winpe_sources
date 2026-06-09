# CMulticastServer::_ServiceControl(void *,ulong)

- ea: `0x180008650`
- end: `0x180008692`
- name: `?_ServiceControl@CMulticastServer@@SAXPEAXK@Z`
- size: `66`
- prototype: `void __fastcall(void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180005e28`
- `0x180008650`

## pseudocode

```c
void __fastcall CMulticastServer::_ServiceControl(void *a1, int a2)
{
  __int64 i; // r8

  if ( a2 == 128 )
  {
    CMulticastServer::ReadParameters((struct _RTL_CRITICAL_SECTION *)qword_1800336E8);
  }
  else if ( a2 == 133 )
  {
    for ( i = 0; (unsigned int)i < dword_1800336B8; i = (unsigned int)(i + 1) )
      _InterlockedExchange64((volatile __int64 *)(qword_1800336A8 + 8 * i), 0);
  }
}

```

## disassembly

```asm
0x180008650  cmp     edx, 80h
0x180008656  jnz     short loc_180008664
0x180008658  mov     rcx, cs:qword_1800336E8; this
0x18000865f  jmp     ?ReadParameters@CMulticastServer@@AEAAKXZ; CMulticastServer::ReadParameters(void)
0x180008664  cmp     edx, 85h
0x18000866a  jnz     short locret_180008691
0x18000866c  xor     r8d, r8d
0x18000866f  cmp     cs:dword_1800336B8, r8d
0x180008676  jbe     short locret_180008691
0x180008678  mov     rcx, cs:qword_1800336A8
0x18000867f  xor     eax, eax
0x180008681  xchg    rax, [rcx+r8*8]
0x180008685  inc     r8d
0x180008688  cmp     r8d, cs:dword_1800336B8
0x18000868f  jb      short loc_180008678
0x180008691  retn
```
