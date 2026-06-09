# SetRedirectDisabledValue(void)

- ea: `0x180024b20`
- end: `0x180024b45`
- name: `?SetRedirectDisabledValue@@YAXXZ`
- size: `37`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010898`
- `0x180021150`

## callees

- `0x1800249b0`
- `0x180024b20`

## string_xrefs

- `0x180024b24`: `Software\Policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
void SetRedirectDisabledValue(void)
{
  if ( !CheckRedirectDisabledValueLocation(L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services") )
    CheckRedirectDisabledValueLocation(L"System\\CurrentControlSet\\Control\\Terminal Server");
}

```

## disassembly

```asm
0x180024b20  sub     rsp, 28h
0x180024b24  lea     rcx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180024b2b  call    ?CheckRedirectDisabledValueLocation@@YA_NPEBG@Z; CheckRedirectDisabledValueLocation(ushort const *)
0x180024b30  test    al, al
0x180024b32  jnz     short loc_180024B40
0x180024b34  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ter"...
0x180024b3b  call    ?CheckRedirectDisabledValueLocation@@YA_NPEBG@Z; CheckRedirectDisabledValueLocation(ushort const *)
0x180024b40  add     rsp, 28h
0x180024b44  retn
```
