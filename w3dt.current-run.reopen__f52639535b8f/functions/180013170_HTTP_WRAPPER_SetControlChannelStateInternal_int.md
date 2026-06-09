# HTTP_WRAPPER::SetControlChannelStateInternal(int)

- ea: `0x180013170`
- end: `0x1800131bd`
- name: `?SetControlChannelStateInternal@HTTP_WRAPPER@@AEAAKH@Z`
- size: `77`
- prototype: `unsigned int __fastcall(HTTP_WRAPPER *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800129c8`
- `0x1800130e8`

## callees

- `0x180013170`

## import_xrefs

- `HTTPAPI!HttpSetServerSessionProperty` at `0x1800131a5`
- `HTTPAPI!HttpSetServerSessionProperty` at `0x1800131a5`

## pseudocode

```c
ULONG __fastcall HTTP_WRAPPER::SetControlChannelStateInternal(HTTP_WRAPPER *this, int a2)
{
  HTTP_SERVER_SESSION_ID v4; // rcx
  ULONG result; // eax
  int PropertyInformation; // [rsp+30h] [rbp+8h] BYREF
  BOOL v7; // [rsp+34h] [rbp+Ch]

  PropertyInformation = 1;
  v4 = *((_QWORD *)this + 2);
  v7 = a2 == 0;
  result = HttpSetServerSessionProperty(v4, HttpServerStateProperty, &PropertyInformation, 8u);
  if ( !result )
    *((_DWORD *)this + 6) = a2;
  return result;
}

```

## disassembly

```asm
0x180013170  mov     [rsp+arg_8], rbx
0x180013175  push    rdi
0x180013176  sub     rsp, 20h
0x18001317a  xor     eax, eax
0x18001317c  mov     [rsp+28h+PropertyInformation], 1
0x180013184  test    edx, edx
0x180013186  lea     r8, [rsp+28h+PropertyInformation]; PropertyInformation
0x18001318b  mov     r9d, 8; PropertyInformationLength
0x180013191  mov     ebx, edx
0x180013193  setz    al
0x180013196  mov     rdi, rcx
0x180013199  mov     rcx, [rcx+10h]; ServerSessionId
0x18001319d  mov     [rsp+28h+arg_4], eax
0x1800131a1  lea     edx, [r9-3]; Property
0x1800131a5  call    cs:__imp_HttpSetServerSessionProperty
0x1800131ab  test    eax, eax
0x1800131ad  jnz     short loc_1800131B2
0x1800131af  mov     [rdi+18h], ebx
0x1800131b2  mov     rbx, [rsp+28h+arg_8]
0x1800131b7  add     rsp, 20h
0x1800131bb  pop     rdi
0x1800131bc  retn
```
