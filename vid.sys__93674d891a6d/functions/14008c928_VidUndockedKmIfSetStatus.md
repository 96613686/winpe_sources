# VidUndockedKmIfSetStatus

- ea: `0x14008c928`
- end: `0x14008ca5b`
- name: `VidUndockedKmIfSetStatus`
- size: `307`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140023b00`
- `0x14008c82c`
- `0x1400cf890`

## callees

- `0x14000f744`
- `0x14002f724`
- `0x14008c928`

## import_xrefs

- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14008c992`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14008c992`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14008c9ee`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14008c9ee`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x14008ca41`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x14008ca41`
- `ntoskrnl!KeInitializeEvent` at `0x14008c95a`
- `ntoskrnl!KeInitializeEvent` at `0x14008c95a`

## pseudocode

```c
__int64 __fastcall VidUndockedKmIfSetStatus(char a1, char a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int updated; // eax
  struct _KEVENT Object; // [rsp+40h] [rbp-28h] BYREF
  char v8; // [rsp+70h] [rbp+8h] BYREF
  __int64 v9; // [rsp+80h] [rbp+18h] BYREF

  v8 = a1;
  v9 = 0;
  memset(&Object, 0, sizeof(Object));
  if ( a2
    && (KeInitializeEvent(&Object, NotificationEvent, 0),
        v3 = ExSubscribeWnfStateChange(&v9, &WNF_VID_UNDOCKED_INTERFACES_AVAILABLE, 8),
        v4 = v3,
        v3 < 0) )
  {
    VidTraceErrorStatusInternal0(
      "VidUndockedKmIfSetStatus",
      "onecore\\vm\\vid\\sys\\driver\\vidkminterface.c",
      319,
      (unsigned int)v3);
  }
  else
  {
    updated = ZwUpdateWnfStateData(&WNF_VID_UNDOCKED_INTERFACES_AVAILABLE, &v8, 1);
    v4 = updated;
    if ( updated >= 0 )
    {
      if ( a2 )
        VidWaitForSingleObjectInfinite(&Object);
      v4 = 0;
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VidUndockedKmIfSetStatus",
        "onecore\\vm\\vid\\sys\\driver\\vidkminterface.c",
        336,
        (unsigned int)updated);
    }
  }
  if ( v9 )
    ExUnsubscribeWnfStateChange();
  return v4;
}

```

## disassembly

```asm
0x14008c928  mov     r11, rsp
0x14008c92b  mov     [r11+10h], rbx
0x14008c92f  mov     [rsp+arg_0], cl
0x14008c933  push    rdi
0x14008c934  sub     rsp, 60h
0x14008c938  xor     eax, eax
0x14008c93a  xorps   xmm0, xmm0
0x14008c93d  mov     [r11+18h], rax
0x14008c941  mov     dil, dl
0x14008c944  movups  xmmword ptr [rsp+68h+Object.Header], xmm0
0x14008c949  mov     [r11-18h], rax
0x14008c94d  test    dl, dl
0x14008c94f  jz      short loc_14008C9C2
0x14008c951  xor     r8d, r8d; State
0x14008c954  lea     rcx, [r11-28h]; Event
0x14008c958  xor     edx, edx; Type
0x14008c95a  call    cs:__imp_KeInitializeEvent
0x14008c961  nop     dword ptr [rax+rax+00h]
0x14008c966  xor     r9d, r9d
0x14008c969  lea     rax, [rsp+68h+Object]
0x14008c96e  mov     [rsp+68h+var_40], rax
0x14008c973  lea     rdx, WNF_VID_UNDOCKED_INTERFACES_AVAILABLE
0x14008c97a  lea     rax, VidUndockedKmIfpWnfSelfSubscribeCallback
0x14008c981  lea     rcx, [rsp+68h+arg_10]
0x14008c989  mov     [rsp+68h+var_48], rax
0x14008c98e  lea     r8d, [r9+8]
0x14008c992  call    cs:__imp_ExSubscribeWnfStateChange
0x14008c999  nop     dword ptr [rax+rax+00h]
0x14008c99e  mov     ebx, eax
0x14008c9a0  test    eax, eax
0x14008c9a2  jns     short loc_14008C9C2
0x14008c9a4  mov     r9d, eax
0x14008c9a7  lea     rdx, aOnecoreVmVidSy_36; "onecore\\vm\\vid\\sys\\driver\\vidkmint"...
0x14008c9ae  mov     r8d, 13Fh
0x14008c9b4  lea     rcx, aVidundockedkmi_0; "VidUndockedKmIfSetStatus"
0x14008c9bb  call    VidTraceErrorStatusInternal0
0x14008c9c0  jmp     short loc_14008CA34
0x14008c9c2  xor     r9d, r9d
0x14008c9c5  mov     [rsp+68h+var_38], 0
0x14008c9cd  mov     dword ptr [rsp+68h+var_40], 0
0x14008c9d5  lea     rdx, [rsp+68h+arg_0]
0x14008c9da  lea     rcx, WNF_VID_UNDOCKED_INTERFACES_AVAILABLE
0x14008c9e1  mov     [rsp+68h+var_48], 0
0x14008c9ea  lea     r8d, [r9+1]
0x14008c9ee  call    cs:__imp_ZwUpdateWnfStateData
0x14008c9f5  nop     dword ptr [rax+rax+00h]
0x14008c9fa  mov     ebx, eax
0x14008c9fc  test    eax, eax
0x14008c9fe  jns     short loc_14008CA1E
0x14008ca00  mov     r9d, eax
0x14008ca03  lea     rdx, aOnecoreVmVidSy_36; "onecore\\vm\\vid\\sys\\driver\\vidkmint"...
0x14008ca0a  mov     r8d, 150h
0x14008ca10  lea     rcx, aVidundockedkmi_0; "VidUndockedKmIfSetStatus"
0x14008ca17  call    VidTraceErrorStatusInternal0
0x14008ca1c  jmp     short loc_14008CA34
0x14008ca1e  test    dil, dil
0x14008ca21  jz      short loc_14008CA32
0x14008ca23  mov     edx, 7530h
0x14008ca28  lea     rcx, [rsp+68h+Object]; Object
0x14008ca2d  call    VidWaitForSingleObjectInfinite
0x14008ca32  xor     ebx, ebx
0x14008ca34  mov     rcx, [rsp+68h+arg_10]
0x14008ca3c  test    rcx, rcx
0x14008ca3f  jz      short loc_14008CA4D
0x14008ca41  call    cs:__imp_ExUnsubscribeWnfStateChange
0x14008ca48  nop     dword ptr [rax+rax+00h]
0x14008ca4d  mov     eax, ebx
0x14008ca4f  mov     rbx, [rsp+68h+arg_8]
0x14008ca54  add     rsp, 60h
0x14008ca58  pop     rdi
0x14008ca59  retn
```
