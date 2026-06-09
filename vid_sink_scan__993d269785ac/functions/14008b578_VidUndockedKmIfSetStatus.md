# VidUndockedKmIfSetStatus

- ea: `0x14008b578`
- end: `0x14008b6ab`
- name: `VidUndockedKmIfSetStatus`
- size: `307`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140023b00`
- `0x14008b47c`
- `0x1400cd0d0`

## callees

- `0x14000f8f4`
- `0x14002f524`
- `0x14008b578`

## import_xrefs

- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14008b5e2`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14008b5e2`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14008b63e`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14008b63e`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x14008b691`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x14008b691`
- `ntoskrnl!KeInitializeEvent` at `0x14008b5aa`
- `ntoskrnl!KeInitializeEvent` at `0x14008b5aa`

## pseudocode

```c
__int64 __fastcall VidUndockedKmIfSetStatus(char a1, char a2)
{
  int updated; // ebx
  struct _KEVENT Object; // [rsp+40h] [rbp-28h] BYREF
  char v6; // [rsp+70h] [rbp+8h] BYREF
  __int64 v7; // [rsp+80h] [rbp+18h] BYREF

  v6 = a1;
  v7 = 0;
  memset(&Object, 0, sizeof(Object));
  if ( a2
    && (KeInitializeEvent(&Object, NotificationEvent, 0),
        updated = ExSubscribeWnfStateChange(&v7, &WNF_VID_UNDOCKED_INTERFACES_AVAILABLE, 8),
        updated < 0) )
  {
    VidTraceErrorStatusInternal0("VidUndockedKmIfSetStatus", "onecore\\vm\\vid\\sys\\driver\\vidkminterface.c", 319);
  }
  else
  {
    updated = ZwUpdateWnfStateData(&WNF_VID_UNDOCKED_INTERFACES_AVAILABLE, &v6, 1);
    if ( updated >= 0 )
    {
      if ( a2 )
        VidWaitForSingleObjectInfinite(&Object);
      updated = 0;
    }
    else
    {
      VidTraceErrorStatusInternal0("VidUndockedKmIfSetStatus", "onecore\\vm\\vid\\sys\\driver\\vidkminterface.c", 336);
    }
  }
  if ( v7 )
    ExUnsubscribeWnfStateChange();
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14008b578  mov     r11, rsp
0x14008b57b  mov     [r11+10h], rbx
0x14008b57f  mov     [rsp+arg_0], cl
0x14008b583  push    rdi
0x14008b584  sub     rsp, 60h
0x14008b588  xor     eax, eax
0x14008b58a  xorps   xmm0, xmm0
0x14008b58d  mov     [r11+18h], rax
0x14008b591  mov     dil, dl
0x14008b594  movups  xmmword ptr [rsp+68h+Object.Header], xmm0
0x14008b599  mov     [r11-18h], rax
0x14008b59d  test    dl, dl
0x14008b59f  jz      short loc_14008B612
0x14008b5a1  xor     r8d, r8d; State
0x14008b5a4  lea     rcx, [r11-28h]; Event
0x14008b5a8  xor     edx, edx; Type
0x14008b5aa  call    cs:__imp_KeInitializeEvent
0x14008b5b1  nop     dword ptr [rax+rax+00h]
0x14008b5b6  xor     r9d, r9d
0x14008b5b9  lea     rax, [rsp+68h+Object]
0x14008b5be  mov     [rsp+68h+var_40], rax
0x14008b5c3  lea     rdx, WNF_VID_UNDOCKED_INTERFACES_AVAILABLE
0x14008b5ca  lea     rax, VidUndockedKmIfpWnfSelfSubscribeCallback
0x14008b5d1  lea     rcx, [rsp+68h+arg_10]
0x14008b5d9  mov     [rsp+68h+var_48], rax
0x14008b5de  lea     r8d, [r9+8]
0x14008b5e2  call    cs:__imp_ExSubscribeWnfStateChange
0x14008b5e9  nop     dword ptr [rax+rax+00h]
0x14008b5ee  mov     ebx, eax
0x14008b5f0  test    eax, eax
0x14008b5f2  jns     short loc_14008B612
0x14008b5f4  mov     r9d, eax
0x14008b5f7  lea     rdx, aOnecoreVmVidSy_36; "onecore\\vm\\vid\\sys\\driver\\vidkmint"...
0x14008b5fe  mov     r8d, 13Fh
0x14008b604  lea     rcx, aVidundockedkmi_0; "VidUndockedKmIfSetStatus"
0x14008b60b  call    VidTraceErrorStatusInternal0
0x14008b610  jmp     short loc_14008B684
0x14008b612  xor     r9d, r9d
0x14008b615  mov     [rsp+68h+var_38], 0
0x14008b61d  mov     dword ptr [rsp+68h+var_40], 0
0x14008b625  lea     rdx, [rsp+68h+arg_0]
0x14008b62a  lea     rcx, WNF_VID_UNDOCKED_INTERFACES_AVAILABLE
0x14008b631  mov     [rsp+68h+var_48], 0
0x14008b63a  lea     r8d, [r9+1]
0x14008b63e  call    cs:__imp_ZwUpdateWnfStateData
0x14008b645  nop     dword ptr [rax+rax+00h]
0x14008b64a  mov     ebx, eax
0x14008b64c  test    eax, eax
0x14008b64e  jns     short loc_14008B66E
0x14008b650  mov     r9d, eax
0x14008b653  lea     rdx, aOnecoreVmVidSy_36; "onecore\\vm\\vid\\sys\\driver\\vidkmint"...
0x14008b65a  mov     r8d, 150h
0x14008b660  lea     rcx, aVidundockedkmi_0; "VidUndockedKmIfSetStatus"
0x14008b667  call    VidTraceErrorStatusInternal0
0x14008b66c  jmp     short loc_14008B684
0x14008b66e  test    dil, dil
0x14008b671  jz      short loc_14008B682
0x14008b673  mov     edx, 7530h
0x14008b678  lea     rcx, [rsp+68h+Object]; Object
0x14008b67d  call    VidWaitForSingleObjectInfinite
0x14008b682  xor     ebx, ebx
0x14008b684  mov     rcx, [rsp+68h+arg_10]
0x14008b68c  test    rcx, rcx
0x14008b68f  jz      short loc_14008B69D
0x14008b691  call    cs:__imp_ExUnsubscribeWnfStateChange
0x14008b698  nop     dword ptr [rax+rax+00h]
0x14008b69d  mov     eax, ebx
0x14008b69f  mov     rbx, [rsp+68h+arg_8]
0x14008b6a4  add     rsp, 60h
0x14008b6a8  pop     rdi
0x14008b6a9  retn
```
