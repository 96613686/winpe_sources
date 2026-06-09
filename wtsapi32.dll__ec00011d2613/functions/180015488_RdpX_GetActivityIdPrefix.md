# RdpX_GetActivityIdPrefix

- ea: `0x180015488`
- end: `0x1800154d2`
- name: `RdpX_GetActivityIdPrefix`
- size: `74`
- prototype: ``
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x180012690`
- `0x180012a78`
- `0x180012c20`
- `0x180012e70`
- `0x180013020`
- `0x1800131b0`
- `0x180013290`
- `0x1800133f0`
- `0x180013600`
- `0x180013990`
- `0x180013c70`
- `0x180013d30`
- `0x180013e30`
- `0x180013fa0`
- `0x1800140f0`
- `0x180014230`
- `0x180014390`
- `0x1800144a4`
- `0x180014698`
- `0x180014898`
- `0x180014c74`
- `0x180015050`

## callees

- `0x1800155c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800154ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800154ad`

## pseudocode

```c
__int64 RdpX_GetActivityIdPrefix()
{
  signed int v0; // eax
  unsigned int Data1; // edx
  GUID ActivityId; // [rsp+20h] [rbp-28h] BYREF

  ActivityId = 0;
  v0 = EventActivityIdControl(1u, &ActivityId);
  Data1 = ActivityId.Data1;
  if ( v0 < 0 )
    return 0;
  return Data1;
}

```

## disassembly

```asm
0x180015488  sub     rsp, 48h
0x18001548c  mov     rax, cs:__security_cookie
0x180015493  xor     rax, rsp
0x180015496  mov     [rsp+48h+var_18], rax
0x18001549b  xorps   xmm0, xmm0
0x18001549e  lea     rdx, [rsp+48h+ActivityId]; ActivityId
0x1800154a3  mov     ecx, 1; ControlCode
0x1800154a8  movups  xmmword ptr [rsp+48h+ActivityId.Data1], xmm0
0x1800154ad  call    cs:__imp_EventActivityIdControl
0x1800154b3  mov     edx, [rsp+48h+ActivityId.Data1]
0x1800154b7  xor     ecx, ecx
0x1800154b9  test    eax, eax
0x1800154bb  cmovs   edx, ecx
0x1800154be  mov     eax, edx
0x1800154c0  mov     rcx, [rsp+48h+var_18]
0x1800154c5  xor     rcx, rsp; StackCookie
0x1800154c8  call    __security_check_cookie
0x1800154cd  add     rsp, 48h
0x1800154d1  retn
```
