# XMLScrSite::OnJobFinished(IServiceProvider *,IUnknown *)

- ea: `0x14000c410`
- end: `0x14000c445`
- name: `?OnJobFinished@XMLScrSite@@UEAAJPEAUIServiceProvider@@PEAUIUnknown@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, struct IServiceProvider *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x14000c410`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::OnJobFinished(XMLScrSite *this, struct IServiceProvider *a2, struct IUnknown *a3)
{
  __int64 v3; // rbx
  __int64 v4; // rcx

  v3 = *((_QWORD *)this + 2);
  v4 = *(_QWORD *)(v3 + 672);
  if ( v4 )
    (*(void (__fastcall **)(__int64, struct IServiceProvider *, struct IUnknown *))(*(_QWORD *)v4 + 16LL))(v4, a2, a3);
  *(_QWORD *)(v3 + 672) = 0;
  return 0;
}

```

## disassembly

```asm
0x14000c410  push    rbx
0x14000c412  sub     rsp, 20h
0x14000c416  mov     rbx, [rcx+10h]
0x14000c41a  mov     rcx, [rbx+2A0h]
0x14000c421  test    rcx, rcx
0x14000c424  jz      short loc_14000C432
0x14000c426  mov     rax, [rcx]
0x14000c429  mov     rax, [rax+10h]
0x14000c42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c432  mov     qword ptr [rbx+2A0h], 0
0x14000c43d  xor     eax, eax
0x14000c43f  add     rsp, 20h
0x14000c443  pop     rbx
0x14000c444  retn
```
