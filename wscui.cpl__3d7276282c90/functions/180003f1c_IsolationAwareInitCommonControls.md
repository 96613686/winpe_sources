# IsolationAwareInitCommonControls

- ea: `0x180003f1c`
- end: `0x180003fa0`
- name: `IsolationAwareInitCommonControls`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003ba0`

## callees

- `0x180003e54`
- `0x180003f1c`
- `0x180003fa8`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180003f94`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000abd3`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180003f94`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000abd3`

## string_xrefs

- `0x180003f57`: `InitCommonControls`

## pseudocode

```c
int IsolationAwareInitCommonControls()
{
  __int64 (*v0)(void); // rbx
  __int64 v1; // rax
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF

  v0 = (__int64 (*)(void))`IsolationAwareInitCommonControls'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    LODWORD(v1) = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)v1 )
      return v1;
  }
  if ( v0 )
    goto LABEL_7;
  v1 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("InitCommonControls");
  v0 = (__int64 (*)(void))v1;
  if ( v1 )
  {
    `IsolationAwareInitCommonControls'::`2'::s_pfn = v1;
LABEL_7:
    LODWORD(v1) = v0();
  }
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    LODWORD(v1) = DeactivateActCtx(0, ulCookie);
  return v1;
}

```

## disassembly

```asm
0x180003f1c  push    rbx
0x180003f1e  sub     rsp, 20h
0x180003f22  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControls@@9@4P6AXXZEA; void (*`IsolationAwareInitCommonControls'::`2'::s_pfn)(void)
0x180003f29  mov     [rsp+28h+ulCookie], 0
0x180003f32  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180003f39  jnz     short loc_180003F52
0x180003f3b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180003f42  jnz     short loc_180003F52
0x180003f44  lea     rcx, [rsp+28h+ulCookie]; lpCookie
0x180003f49  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180003f4e  test    eax, eax
0x180003f50  jz      short loc_180003F9A
0x180003f52  test    rbx, rbx
0x180003f55  jnz     short loc_180003F72
0x180003f57  lea     rcx, aInitcommoncont; "InitCommonControls"
0x180003f5e  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180003f63  mov     rbx, rax
0x180003f66  test    rax, rax
0x180003f69  jz      short loc_180003F7B
0x180003f6b  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControls@@9@4P6AXXZEA, rax; void (*`IsolationAwareInitCommonControls'::`2'::s_pfn)(void)
0x180003f72  mov     rax, rbx
0x180003f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f7a  nop
0x180003f7b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180003f82  jz      short loc_180003F8D
0x180003f84  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180003f8b  jnz     short loc_180003F9A
0x180003f8d  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180003f92  xor     ecx, ecx; dwFlags
0x180003f94  call    cs:__imp_DeactivateActCtx
0x180003f9a  add     rsp, 20h
0x180003f9e  pop     rbx
0x180003f9f  retn
0x18000abb2  push    rbp
0x18000abb4  sub     rsp, 20h
0x18000abb8  mov     rbp, rdx
0x18000abbb  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000abc2  jz      short loc_18000ABCD
0x18000abc4  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000abcb  jnz     short loc_18000ABDA
0x18000abcd  mov     rdx, [rbp+30h]; ulCookie
0x18000abd1  xor     ecx, ecx; dwFlags
0x18000abd3  call    cs:__imp_DeactivateActCtx
0x18000abd9  nop
0x18000abda  add     rsp, 20h
0x18000abde  pop     rbp
0x18000abdf  retn
```
