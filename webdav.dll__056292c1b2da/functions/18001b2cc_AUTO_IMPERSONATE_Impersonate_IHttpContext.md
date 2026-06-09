# AUTO_IMPERSONATE::Impersonate(IHttpContext *)

- ea: `0x18001b2cc`
- end: `0x18001b30b`
- name: `?Impersonate@AUTO_IMPERSONATE@@QEAAJPEAVIHttpContext@@@Z`
- size: `63`
- prototype: `__int64 __fastcall(AUTO_IMPERSONATE *__hidden this, struct IHttpContext *)`
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006434`
- `0x180007710`
- `0x180009480`
- `0x180009d00`
- `0x18000bc4c`
- `0x18000dcb8`
- `0x18000ed10`
- `0x18000f200`
- `0x18000f3ec`
- `0x180011300`
- `0x180011f30`

## callees

- `0x18001a068`
- `0x18001b2cc`
- `0x18001b314`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001b2e7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001b2e7`

## pseudocode

```c
__int64 __fastcall AUTO_IMPERSONATE::Impersonate(AUTO_IMPERSONATE *this, struct IHttpContext *a2)
{
  if ( *(_DWORD *)this )
  {
    *(_DWORD *)this = 0;
    RevertToSelf();
  }
  *((_QWORD *)this + 1) = GetEffectiveToken(a2);
  return AUTO_IMPERSONATE::Reimpersonate(this);
}

```

## disassembly

```asm
0x18001b2cc  mov     [rsp+arg_0], rbx
0x18001b2d1  push    rdi
0x18001b2d2  sub     rsp, 20h
0x18001b2d6  cmp     dword ptr [rcx], 0
0x18001b2d9  mov     rdi, rdx
0x18001b2dc  mov     rbx, rcx
0x18001b2df  jz      short loc_18001B2ED
0x18001b2e1  mov     dword ptr [rcx], 0
0x18001b2e7  call    cs:__imp_RevertToSelf
0x18001b2ed  mov     rcx, rdi; struct IHttpContext *
0x18001b2f0  call    ?GetEffectiveToken@@YAPEAXPEAVIHttpContext@@@Z; GetEffectiveToken(IHttpContext *)
0x18001b2f5  mov     rcx, rbx; this
0x18001b2f8  mov     [rbx+8], rax
0x18001b2fc  mov     rbx, [rsp+28h+arg_0]
0x18001b301  add     rsp, 20h
0x18001b305  pop     rdi
0x18001b306  jmp     ?Reimpersonate@AUTO_IMPERSONATE@@QEAAJXZ; AUTO_IMPERSONATE::Reimpersonate(void)
```
