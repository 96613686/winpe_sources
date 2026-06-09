# _Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__

- ea: `0x18001bcf0`
- end: `0x18001bd35`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__`
- size: `69`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001bcf0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001bd14`
- `ntdll!RtlFreeHeap` at `0x18001bd14`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__()
{
  if ( P )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    *(_OWORD *)&P = 0u;
  }
}

```

## disassembly

```asm
0x18001bcf0  sub     rsp, 28h
0x18001bcf4  cmp     qword ptr cs:P, 0
0x18001bcfc  jz      short loc_18001BD30
0x18001bcfe  mov     rcx, gs:60h
0x18001bd07  xor     edx, edx; Flags
0x18001bd09  mov     r8, qword ptr cs:P; P
0x18001bd10  mov     rcx, [rcx+30h]; HeapHandle
0x18001bd14  call    cs:__imp_RtlFreeHeap
0x18001bd1a  mov     qword ptr cs:P, 0
0x18001bd25  mov     qword ptr cs:P+8, 0
0x18001bd30  add     rsp, 28h
0x18001bd34  retn
```
