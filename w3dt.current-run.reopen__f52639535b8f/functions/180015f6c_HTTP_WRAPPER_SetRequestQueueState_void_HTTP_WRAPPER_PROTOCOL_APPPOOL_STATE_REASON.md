# HTTP_WRAPPER::SetRequestQueueState(void *,HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON)

- ea: `0x180015f6c`
- end: `0x180015fd1`
- name: `?SetRequestQueueState@HTTP_WRAPPER@@QEAAKPEAXW4HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON@@@Z`
- size: `101`
- prototype: `unsigned int __high(void *, enum HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012180`
- `0x180012530`
- `0x180012f88`

## callees

- `0x180015f6c`

## import_xrefs

- `HTTPAPI!HttpSetRequestQueueProperty` at `0x180015fc6`
- `HTTPAPI!HttpSetRequestQueueProperty` at `0x180015fc6`

## pseudocode

```c
ULONG __fastcall HTTP_WRAPPER::SetRequestQueueState(__int64 a1, void *a2, int a3)
{
  int v3; // r8d
  int v4; // r8d
  int PropertyInformation; // [rsp+50h] [rbp+18h] BYREF

  if ( a3 )
  {
    v3 = a3 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        if ( v4 != 1 )
          return 87;
        PropertyInformation = 5;
      }
      else
      {
        PropertyInformation = 4;
      }
    }
    else
    {
      PropertyInformation = 2;
    }
  }
  else
  {
    PropertyInformation = 0;
  }
  return HttpSetRequestQueueProperty(a2, HttpServerStateProperty, &PropertyInformation, 4u, 0, 0);
}

```

## disassembly

```asm
0x180015f6c  sub     rsp, 38h
0x180015f70  mov     r10, rdx
0x180015f73  xor     eax, eax
0x180015f75  mov     edx, 5; Property
0x180015f7a  lea     r9d, [rdx-1]; PropertyInformationLength
0x180015f7e  test    r8d, r8d
0x180015f81  jz      short loc_180015FB1
0x180015f83  sub     r8d, 1
0x180015f87  jz      short loc_180015FA7
0x180015f89  sub     r8d, 1
0x180015f8d  jz      short loc_180015FA0
0x180015f8f  cmp     r8d, 1
0x180015f93  jz      short loc_180015F9A
0x180015f95  lea     eax, [rdx+52h]
0x180015f98  jmp     short loc_180015FCC
0x180015f9a  mov     [rsp+38h+PropertyInformation], edx
0x180015f9e  jmp     short loc_180015FB5
0x180015fa0  mov     [rsp+38h+PropertyInformation], r9d
0x180015fa5  jmp     short loc_180015FB5
0x180015fa7  mov     [rsp+38h+PropertyInformation], 2
0x180015faf  jmp     short loc_180015FB5
0x180015fb1  mov     [rsp+38h+PropertyInformation], eax
0x180015fb5  mov     [rsp+38h+Reserved2], rax; Reserved2
0x180015fba  lea     r8, [rsp+38h+PropertyInformation]; PropertyInformation
0x180015fbf  mov     rcx, r10; RequestQueueHandle
0x180015fc2  mov     [rsp+38h+Reserved1], eax; Reserved1
0x180015fc6  call    cs:__imp_HttpSetRequestQueueProperty
0x180015fcc  add     rsp, 38h
0x180015fd0  retn
```
