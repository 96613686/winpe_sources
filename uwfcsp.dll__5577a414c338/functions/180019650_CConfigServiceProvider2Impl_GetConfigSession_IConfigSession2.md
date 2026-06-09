# CConfigServiceProvider2Impl::GetConfigSession(IConfigSession2 * *)

- ea: `0x180019650`
- end: `0x18001968d`
- name: `?GetConfigSession@CConfigServiceProvider2Impl@@UEAAJPEAPEAUIConfigSession2@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *__hidden this, struct IConfigSession2 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180019650`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::GetConfigSession(
        CConfigServiceProvider2Impl *this,
        struct IConfigSession2 **a2)
{
  struct IConfigSession2 *v2; // rcx

  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  v2 = (struct IConfigSession2 *)*((_QWORD *)this + 2);
  if ( !v2 )
    return 2147942402LL;
  *a2 = v2;
  (*(void (__fastcall **)(struct IConfigSession2 *))(*(_QWORD *)v2 + 8LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x180019650  sub     rsp, 28h
0x180019654  test    rdx, rdx
0x180019657  jz      short loc_180019683
0x180019659  mov     qword ptr [rdx], 0
0x180019660  mov     rcx, [rcx+10h]
0x180019664  test    rcx, rcx
0x180019667  jz      short loc_18001967C
0x180019669  mov     [rdx], rcx
0x18001966c  mov     rax, [rcx]
0x18001966f  mov     rax, [rax+8]
0x180019673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019678  xor     eax, eax
0x18001967a  jmp     short loc_180019688
0x18001967c  mov     eax, 80070002h
0x180019681  jmp     short loc_180019688
0x180019683  mov     eax, 80070057h
0x180019688  add     rsp, 28h
0x18001968c  retn
```
