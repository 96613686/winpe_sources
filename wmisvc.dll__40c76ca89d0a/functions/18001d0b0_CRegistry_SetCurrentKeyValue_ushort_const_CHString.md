# CRegistry::SetCurrentKeyValue(ushort const *,CHString &)

- ea: `0x18001d0b0`
- end: `0x18001d103`
- name: `?SetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z`
- size: `83`
- prototype: `LSTATUS __fastcall(CRegistry *this, const unsigned __int16 *, struct CHString *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800174ec`

## callees

- `0x18001cebc`
- `0x18001d058`
- `0x18001d0b0`
- `0x18001d10c`

## pseudocode

```c
LSTATUS __fastcall CRegistry::SetCurrentKeyValue(CRegistry *this, const unsigned __int16 *a2, struct CHString *a3)
{
  int v6; // eax
  HKEY v7; // rdx

  v6 = CHString::Find(a3, 0x25u);
  v7 = (HKEY)*((_QWORD *)this + 1);
  if ( v6 == -1 )
    return CRegistry::SetCurrentKeyValue(this, v7, a2, (const BYTE **)a3);
  else
    return CRegistry::SetCurrentKeyValueExpand(this, v7, a2, a3);
}

```

## disassembly

```asm
0x18001d0b0  mov     [rsp+arg_0], rbx
0x18001d0b5  mov     [rsp+arg_8], rsi
0x18001d0ba  push    rdi
0x18001d0bb  sub     rsp, 20h
0x18001d0bf  mov     rsi, rdx
0x18001d0c2  mov     rdi, rcx
0x18001d0c5  mov     edx, 25h ; '%'; unsigned __int16
0x18001d0ca  mov     rcx, r8; this
0x18001d0cd  mov     rbx, r8
0x18001d0d0  call    ?Find@CHString@@QEBAHG@Z; CHString::Find(ushort)
0x18001d0d5  mov     rdx, [rdi+8]; HKEY
0x18001d0d9  mov     r9, rbx; struct CHString *
0x18001d0dc  mov     r8, rsi; unsigned __int16 *
0x18001d0df  mov     rcx, rdi; this
0x18001d0e2  cmp     eax, 0FFFFFFFFh
0x18001d0e5  jz      short loc_18001D0EE
0x18001d0e7  call    ?SetCurrentKeyValueExpand@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z; CRegistry::SetCurrentKeyValueExpand(HKEY__ *,ushort const *,CHString &)
0x18001d0ec  jmp     short loc_18001D0F3
0x18001d0ee  call    ?SetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z; CRegistry::SetCurrentKeyValue(HKEY__ *,ushort const *,CHString &)
0x18001d0f3  mov     rbx, [rsp+28h+arg_0]
0x18001d0f8  mov     rsi, [rsp+28h+arg_8]
0x18001d0fd  add     rsp, 20h
0x18001d101  pop     rdi
0x18001d102  retn
```
