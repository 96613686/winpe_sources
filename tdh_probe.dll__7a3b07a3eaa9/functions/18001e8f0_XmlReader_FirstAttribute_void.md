# XmlReader::FirstAttribute(void)

- ea: `0x18001e8f0`
- end: `0x18001e928`
- name: `?FirstAttribute@XmlReader@@QEAA_NXZ`
- size: `56`
- prototype: `bool __fastcall(XmlReader *__hidden this)`
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

- `0x18001e8f0`
- `0x18003bbbc`
- `0x18004c010`

## string_xrefs

- `0x18001e90f`: `MoveToFirstAttribute`

## pseudocode

```c
bool __fastcall XmlReader::FirstAttribute(XmlReader *this)
{
  int v2; // eax

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 64LL))(*(_QWORD *)this);
  if ( v2 < 0 )
    XmlReader::ThrowError(this, "MoveToFirstAttribute", v2);
  return v2 == 0;
}

```

## disassembly

```asm
0x18001e8f0  push    rbx
0x18001e8f2  sub     rsp, 20h
0x18001e8f6  mov     rbx, rcx
0x18001e8f9  mov     rcx, [rcx]
0x18001e8fc  mov     rax, [rcx]
0x18001e8ff  mov     rax, [rax+40h]
0x18001e903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e908  test    eax, eax
0x18001e90a  jns     short loc_18001E91F
0x18001e90c  mov     r8d, eax; int
0x18001e90f  lea     rdx, aMovetofirstatt; "MoveToFirstAttribute"
0x18001e916  mov     rcx, rbx; this
0x18001e919  call    ?ThrowError@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowError(char const *,long)
0x18001e91f  setz    al
0x18001e922  add     rsp, 20h
0x18001e926  pop     rbx
0x18001e927  retn
```
