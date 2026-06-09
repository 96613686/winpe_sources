# _Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__

- ea: `0x18001bd40`
- end: `0x18001bd7a`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__`
- size: `58`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001bd40`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001bd64`
- `ntdll!RtlFreeHeap` at `0x18001bd64`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__()
{
  if ( Sid )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Sid);
    Sid = 0;
  }
}

```

## disassembly

```asm
0x18001bd40  sub     rsp, 28h
0x18001bd44  cmp     cs:Sid, 0
0x18001bd4c  jz      short loc_18001BD75
0x18001bd4e  mov     rcx, gs:60h
0x18001bd57  xor     edx, edx; Flags
0x18001bd59  mov     r8, cs:Sid; P
0x18001bd60  mov     rcx, [rcx+30h]; HeapHandle
0x18001bd64  call    cs:__imp_RtlFreeHeap
0x18001bd6a  mov     cs:Sid, 0
0x18001bd75  add     rsp, 28h
0x18001bd79  retn
```
