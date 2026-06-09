# WdipCreateClientSecurityAttributes

- ea: `0x18000d6cc`
- end: `0x18000d718`
- name: `WdipCreateClientSecurityAttributes`
- size: `76`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a280`
- `0x18000a420`
- `0x18000a744`
- `0x18000a9b0`
- `0x18000ab6c`
- `0x18000ae18`

## callees

- `0x180007ee0`
- `0x18000d6cc`

## import_xrefs

- `ntdll!AlpcGetMessageAttribute` at `0x18000d6ec`
- `ntdll!AlpcGetMessageAttribute` at `0x18000d6ec`

## pseudocode

```c
__int64 WdipCreateClientSecurityAttributes()
{
  __int64 MessageAttributes; // rax
  __int64 v1; // rbx
  __int64 MessageAttribute; // rax

  MessageAttributes = WdipCreateMessageAttributes(0x80000000LL);
  v1 = MessageAttributes;
  if ( MessageAttributes )
  {
    MessageAttribute = AlpcGetMessageAttribute(MessageAttributes, 0x80000000LL);
    *(_QWORD *)(MessageAttribute + 8) = 0;
    *(_DWORD *)(v1 + 4) = 0x80000000;
    *(_QWORD *)(MessageAttribute + 16) = -2;
    *(_DWORD *)MessageAttribute = 0x20000;
  }
  return v1;
}

```

## disassembly

```asm
0x18000d6cc  push    rbx
0x18000d6ce  sub     rsp, 20h
0x18000d6d2  mov     ecx, 80000000h
0x18000d6d7  call    WdipCreateMessageAttributes
0x18000d6dc  mov     rbx, rax
0x18000d6df  test    rax, rax
0x18000d6e2  jz      short loc_18000D70F
0x18000d6e4  mov     edx, 80000000h
0x18000d6e9  mov     rcx, rax
0x18000d6ec  call    cs:__imp_AlpcGetMessageAttribute
0x18000d6f2  mov     qword ptr [rax+8], 0
0x18000d6fa  mov     dword ptr [rbx+4], 80000000h
0x18000d701  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFEh
0x18000d709  mov     dword ptr [rax], 20000h
0x18000d70f  mov     rax, rbx
0x18000d712  add     rsp, 20h
0x18000d716  pop     rbx
0x18000d717  retn
```
