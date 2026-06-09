# XML_RENDERER::AppendLockTokenSubmittedIfNecessary(IPubUriLockList *,int *)

- ea: `0x180014388`
- end: `0x1800143fe`
- name: `?AppendLockTokenSubmittedIfNecessary@XML_RENDERER@@AEAAJPEAVIPubUriLockList@@PEAH@Z`
- size: `118`
- prototype: `__int64 __fastcall(XML_RENDERER *__hidden this, struct IPubUriLockList *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015430`

## callees

- `0x180013fd4`
- `0x180014388`
- `0x180014ef4`
- `0x180023010`

## string_xrefs

- `0x1800143ce`: `lock-token-submitted`

## pseudocode

```c
__int64 __fastcall XML_RENDERER::AppendLockTokenSubmittedIfNecessary(
        const char **this,
        struct IPubUriLockList *a2,
        int *a3)
{
  int v6; // ebx
  const unsigned __int16 *v7; // rdi

  v6 = 0;
  if ( !(*(__int64 (__fastcall **)(struct IPubUriLockList *))(*(_QWORD *)a2 + 56LL))(a2) )
  {
    v7 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IPubUriLockList *))(*(_QWORD *)a2 + 16LL))(a2);
    if ( !*a3 )
      return (unsigned int)XML_RENDERER::AppendHRef(this, 0, v7);
    *a3 = 0;
    v6 = XML_RENDERER::OpenOrCloseXmlTag((XML_RENDERER *)this, "lock-token-submitted", 0);
    if ( v6 >= 0 )
      return (unsigned int)XML_RENDERER::AppendHRef(this, 0, v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180014388  push    rbx
0x18001438a  push    rsi
0x18001438b  push    rdi
0x18001438c  push    r14
0x18001438e  sub     rsp, 28h
0x180014392  mov     rax, [rdx]
0x180014395  mov     rsi, rcx
0x180014398  mov     rcx, rdx
0x18001439b  mov     r14, r8
0x18001439e  mov     rdi, rdx
0x1800143a1  xor     ebx, ebx
0x1800143a3  mov     rax, [rax+38h]
0x1800143a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143ac  test    rax, rax
0x1800143af  jnz     short loc_1800143F2
0x1800143b1  mov     rax, [rdi]
0x1800143b4  mov     rcx, rdi
0x1800143b7  mov     rax, [rax+10h]
0x1800143bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143c0  mov     rdi, rax
0x1800143c3  cmp     [r14], ebx
0x1800143c6  jz      short loc_1800143E3
0x1800143c8  xor     r8d, r8d; int
0x1800143cb  mov     [r14], ebx
0x1800143ce  lea     rdx, aLockTokenSubmi; "lock-token-submitted"
0x1800143d5  mov     rcx, rsi; this
0x1800143d8  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x1800143dd  mov     ebx, eax
0x1800143df  test    eax, eax
0x1800143e1  js      short loc_1800143F2
0x1800143e3  mov     r8, rdi; unsigned __int16 *
0x1800143e6  xor     edx, edx; unsigned __int16 *
0x1800143e8  mov     rcx, rsi; this
0x1800143eb  call    ?AppendHRef@XML_RENDERER@@AEAAJPEBG0@Z; XML_RENDERER::AppendHRef(ushort const *,ushort const *)
0x1800143f0  mov     ebx, eax
0x1800143f2  mov     eax, ebx
0x1800143f4  add     rsp, 28h
0x1800143f8  pop     r14
0x1800143fa  pop     rdi
0x1800143fb  pop     rsi
0x1800143fc  pop     rbx
0x1800143fd  retn
```
