# CbsUIHandler::ResolveSource(ushort const *,ICbsIdentity *,ushort const *,ushort * *,int *)

- ea: `0x1400117f0`
- end: `0x14001180a`
- name: `?ResolveSource@CbsUIHandler@@UEAAJPEBGPEAUICbsIdentity@@0PEAPEAGPEAH@Z`
- size: `26`
- prototype: `__int64 __fastcall(CbsUIHandler *__hidden this, const unsigned __int16 *, struct ICbsIdentity *, const unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## pseudocode

```c
__int64 __fastcall CbsUIHandler::ResolveSource(
        CbsUIHandler *this,
        const unsigned __int16 *a2,
        struct ICbsIdentity *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5,
        int *a6)
{
  *a5 = 0;
  *a6 = 1;
  return 0;
}

```

## disassembly

```asm
0x1400117f0  mov     rax, [rsp+arg_20]
0x1400117f5  mov     qword ptr [rax], 0
0x1400117fc  mov     rax, [rsp+arg_28]
0x140011801  mov     dword ptr [rax], 1
0x140011807  xor     eax, eax
0x140011809  retn
```
