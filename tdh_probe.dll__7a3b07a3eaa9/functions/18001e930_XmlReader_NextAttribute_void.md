# XmlReader::NextAttribute(void)

- ea: `0x18001e930`
- end: `0x18001e968`
- name: `?NextAttribute@XmlReader@@QEAA_NXZ`
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

- `0x18001e930`
- `0x18003bbbc`
- `0x18004c010`

## string_xrefs

- `0x18001e94f`: `MoveToNextAttribute`

## pseudocode

```c
bool __fastcall XmlReader::NextAttribute(XmlReader *this)
{
  int v2; // eax

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 72LL))(*(_QWORD *)this);
  if ( v2 < 0 )
    XmlReader::ThrowError(this, "MoveToNextAttribute", v2);
  return v2 == 0;
}

```

## disassembly

```asm
0x18001e930  push    rbx
0x18001e932  sub     rsp, 20h
0x18001e936  mov     rbx, rcx
0x18001e939  mov     rcx, [rcx]
0x18001e93c  mov     rax, [rcx]
0x18001e93f  mov     rax, [rax+48h]
0x18001e943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e948  test    eax, eax
0x18001e94a  jns     short loc_18001E95F
0x18001e94c  mov     r8d, eax; int
0x18001e94f  lea     rdx, aMovetonextattr; "MoveToNextAttribute"
0x18001e956  mov     rcx, rbx; this
0x18001e959  call    ?ThrowError@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowError(char const *,long)
0x18001e95f  setz    al
0x18001e962  add     rsp, 20h
0x18001e966  pop     rbx
0x18001e967  retn
```
