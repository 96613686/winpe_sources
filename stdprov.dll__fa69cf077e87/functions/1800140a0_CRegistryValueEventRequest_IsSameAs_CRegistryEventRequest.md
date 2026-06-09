# CRegistryValueEventRequest::IsSameAs(CRegistryEventRequest *)

- ea: `0x1800140a0`
- end: `0x1800140e4`
- name: `?IsSameAs@CRegistryValueEventRequest@@UEAAHPEAVCRegistryEventRequest@@@Z`
- size: `68`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 **this, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180006f50`
- `0x180006fe0`
- `0x1800140a0`

## pseudocode

```c
_BOOL8 __fastcall CRegistryValueEventRequest::IsSameAs(const unsigned __int16 **this, const unsigned __int16 **a2)
{
  return CRegistryEventRequest::IsSameAs(this, a2) && !(unsigned int)wbem_wcsicmp(this[28], a2[28]);
}

```

## disassembly

```asm
0x1800140a0  mov     [rsp+arg_0], rbx
0x1800140a5  push    rdi
0x1800140a6  sub     rsp, 20h
0x1800140aa  mov     rbx, rdx
0x1800140ad  mov     rdi, rcx
0x1800140b0  call    ?IsSameAs@CRegistryEventRequest@@UEAAHPEAV1@@Z; CRegistryEventRequest::IsSameAs(CRegistryEventRequest *)
0x1800140b5  test    eax, eax
0x1800140b7  jz      short loc_1800140D7
0x1800140b9  mov     rdx, [rbx+0E0h]; unsigned __int16 *
0x1800140c0  mov     rcx, [rdi+0E0h]; unsigned __int16 *
0x1800140c7  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800140cc  test    eax, eax
0x1800140ce  jnz     short loc_1800140D7
0x1800140d0  mov     eax, 1
0x1800140d5  jmp     short loc_1800140D9
0x1800140d7  xor     eax, eax
0x1800140d9  mov     rbx, [rsp+28h+arg_0]
0x1800140de  add     rsp, 20h
0x1800140e2  pop     rdi
0x1800140e3  retn
```
