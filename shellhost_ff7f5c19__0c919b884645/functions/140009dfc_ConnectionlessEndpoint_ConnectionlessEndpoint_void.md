# ConnectionlessEndpoint::ConnectionlessEndpoint(void)

- ea: `0x140009dfc`
- end: `0x140009e8f`
- name: `??0ConnectionlessEndpoint@@QEAA@XZ`
- size: `147`
- prototype: `ConnectionlessEndpoint *__fastcall(ConnectionlessEndpoint *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140009bfc`
- `0x14005bd30`

## callees

- `0x14005c0f8`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x140009e6b`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x140009e6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
ConnectionlessEndpoint *__fastcall ConnectionlessEndpoint::ConnectionlessEndpoint(ConnectionlessEndpoint *this)
{
  _QWORD *v2; // rcx

  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 16) = 0;
  *((_DWORD *)this + 5) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = &FlowEndpointBase::`vftable';
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_BYTE *)this + 92) = 0;
  v2 = (_QWORD *)((char *)this + 96);
  *v2 = 0;
  v2[1] = 0;
  std::list<std::pair<enum StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::_Alloc_sentinel_and_proxy();
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_WORD *)this + 64) = 0;
  *((_DWORD *)this + 33) = SHTaskPoolGetUniqueContext();
  *(_QWORD *)this = &FlowEndpointBase::`vftable';
  return this;
}

```

## disassembly

```asm
0x140009dfc  mov     [rsp+arg_8], rbx
0x140009e01  mov     [rsp+arg_0], rcx
0x140009e06  push    rdi
0x140009e07  sub     rsp, 20h
0x140009e0b  mov     rbx, rcx
0x140009e0e  xor     edi, edi
0x140009e10  mov     [rcx+8], rdi
0x140009e14  mov     [rcx+10h], dil
0x140009e18  mov     [rcx+14h], edi
0x140009e1b  mov     [rcx+18h], rdi
0x140009e1f  mov     [rcx+20h], rdi
0x140009e23  lea     rax, ??_7FlowEndpointBase@@6B@; const FlowEndpointBase::`vftable'
0x140009e2a  mov     [rcx], rax
0x140009e2d  mov     [rcx+28h], rdi
0x140009e31  mov     [rcx+30h], edi
0x140009e34  mov     [rcx+38h], rdi
0x140009e38  mov     [rcx+40h], rdi
0x140009e3c  mov     [rcx+48h], rdi
0x140009e40  mov     [rcx+50h], rdi
0x140009e44  mov     [rcx+58h], edi
0x140009e47  mov     [rcx+5Ch], dil
0x140009e4b  add     rcx, 60h ; '`'
0x140009e4f  mov     [rcx], rdi
0x140009e52  mov     [rcx+8], rdi
0x140009e56  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@V?$allocator@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::_Alloc_sentinel_and_proxy(void)
0x140009e5b  mov     [rbx+70h], edi
0x140009e5e  xor     eax, eax
0x140009e60  mov     [rbx+78h], rax
0x140009e64  mov     [rbx+80h], di
0x140009e6b  call    cs:__imp_SHTaskPoolGetUniqueContext
0x140009e71  mov     [rbx+84h], eax
0x140009e77  lea     rax, ??_7FlowEndpointBase@@6B@; const FlowEndpointBase::`vftable'
0x140009e7e  mov     [rbx], rax
0x140009e81  mov     rax, rbx
0x140009e84  mov     rbx, [rsp+28h+arg_8]
0x140009e89  add     rsp, 20h
0x140009e8d  pop     rdi
0x140009e8e  retn
```
