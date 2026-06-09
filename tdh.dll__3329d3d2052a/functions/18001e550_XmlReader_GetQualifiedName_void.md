# XmlReader::GetQualifiedName(void)

- ea: `0x18001e550`
- end: `0x18001e5be`
- name: `?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ`
- size: `110`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `22`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001d638`
- `0x18001d810`
- `0x18003479c`
- `0x180034974`
- `0x180034e18`
- `0x1800355ac`
- `0x180035aa0`
- `0x180035e08`
- `0x180036e08`
- `0x180037ff0`
- `0x180038300`
- `0x180038570`
- `0x1800386fc`
- `0x180038e20`
- `0x180039878`
- `0x180039a80`
- `0x180039cdc`
- `0x18003b4dc`
- `0x18003b7e0`
- `0x18003ba24`
- `0x18003bec4`
- `0x18003c084`

## callees

- `0x18001e550`
- `0x18003bbbc`
- `0x18004c010`

## pseudocode

```c
_QWORD *__fastcall XmlReader::GetQualifiedName(XmlReader *this, _QWORD *a2)
{
  __int64 v3; // rcx
  int v5; // eax
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v3 = *(_QWORD *)this;
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v3 + 96LL))(v3, &v8, &v7);
  if ( v5 < 0 )
    XmlReader::ThrowError(this, "GetQualifiedName", v5);
  *a2 = v8;
  a2[1] = v7;
  return a2;
}

```

## disassembly

```asm
0x18001e550  mov     r11, rsp
0x18001e553  mov     [r11+10h], rbx
0x18001e557  push    rdi
0x18001e558  sub     rsp, 20h
0x18001e55c  mov     rdi, rcx
0x18001e55f  mov     qword ptr [r11+18h], 0
0x18001e567  mov     rcx, [rcx]
0x18001e56a  lea     r8, [r11+8]
0x18001e56e  mov     [rsp+28h+arg_0], 0
0x18001e576  mov     rbx, rdx
0x18001e579  lea     rdx, [r11+18h]
0x18001e57d  mov     rax, [rcx]
0x18001e580  mov     rax, [rax+60h]
0x18001e584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e589  test    eax, eax
0x18001e58b  jns     short loc_18001E5A0
0x18001e58d  mov     r8d, eax; int
0x18001e590  lea     rdx, aGetqualifiedna; "GetQualifiedName"
0x18001e597  mov     rcx, rdi; this
0x18001e59a  call    ?ThrowError@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowError(char const *,long)
0x18001e5a0  mov     rax, [rsp+28h+arg_10]
0x18001e5a5  mov     [rbx], rax
0x18001e5a8  mov     eax, [rsp+28h+arg_0]
0x18001e5ac  mov     [rbx+8], rax
0x18001e5b0  mov     rax, rbx
0x18001e5b3  mov     rbx, [rsp+28h+arg_8]
0x18001e5b8  add     rsp, 20h
0x18001e5bc  pop     rdi
0x18001e5bd  retn
```
