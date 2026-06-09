# McTemplateU0d_EventWriteTransfer

- ea: `0x18000ba10`
- end: `0x18000ba5f`
- name: `McTemplateU0d_EventWriteTransfer`
- size: `79`
- prototype: ``
- caller_count: `27`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011f0`
- `0x180001450`
- `0x180001800`
- `0x180002870`
- `0x180003760`
- `0x1800038b0`
- `0x18000c650`
- `0x18000c850`
- `0x18000ca60`
- `0x18000ccb0`
- `0x18000d020`
- `0x18000e0e0`
- `0x18000e2e0`
- `0x18000e4e0`
- `0x18000f5c0`
- `0x180010830`
- `0x180010a40`
- `0x180010e70`
- `0x1800110c0`
- `0x1800112c0`
- `0x1800114c0`
- `0x1800116c0`
- `0x180011aa0`
- `0x180011cb0`
- `0x180011ec0`
- `0x1800120d0`
- `0x1800123b0`

## callees

- `0x1800061d0`
- `0x180006620`

## pseudocode

```c
ULONG __fastcall McTemplateU0d_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  int *v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+80h] [rbp+18h] BYREF

  v7 = a3;
  v6 = 4;
  v5 = &v7;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 2u, &v4);
}

```

## disassembly

```asm
0x18000ba10  mov     r11, rsp
0x18000ba13  mov     [r11+18h], r8d
0x18000ba17  sub     rsp, 68h
0x18000ba1b  mov     rax, cs:__security_cookie
0x18000ba22  xor     rax, rsp
0x18000ba25  mov     [rsp+68h+var_18], rax
0x18000ba2a  lea     rax, [r11+18h]
0x18000ba2e  mov     qword ptr [r11-20h], 4
0x18000ba36  mov     [r11-28h], rax
0x18000ba3a  mov     r9d, 2
0x18000ba40  lea     rax, [r11-38h]
0x18000ba44  mov     [r11-48h], rax
0x18000ba48  call    McGenEventWrite_EventWriteTransfer
0x18000ba4d  mov     rcx, [rsp+68h+var_18]
0x18000ba52  xor     rcx, rsp; StackCookie
0x18000ba55  call    __security_check_cookie
0x18000ba5a  add     rsp, 68h
0x18000ba5e  retn
```
