# DllUnload

- ea: `0x14001ba40`
- end: `0x14001bc55`
- name: `DllUnload`
- size: `533`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x140001008`
- `0x140001038`
- `0x140009c50`
- `0x14000b040`
- `0x14001ba40`
- `0x14001bd08`
- `0x14001e4a0`
- `0x14001e5ec`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14001ba77`
- `ntoskrnl!EtwActivityIdControl` at `0x14001ba8c`
- `ntoskrnl!EtwActivityIdControl` at `0x14001bb9c`
- `ntoskrnl!EtwActivityIdControl` at `0x14001bc2d`
- `ntoskrnl!EtwActivityIdControl` at `0x14001ba77`
- `ntoskrnl!EtwActivityIdControl` at `0x14001ba8c`
- `ntoskrnl!EtwActivityIdControl` at `0x14001bb9c`
- `ntoskrnl!EtwActivityIdControl` at `0x14001bc2d`

## string_xrefs

- `0x14001ba9e`: `DllUnload`

## pseudocode

```c
__int64 DllUnload()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  PWSTR Buffer; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  _WORD v14[2]; // [rsp+30h] [rbp-59h] BYREF
  int v15; // [rsp+34h] [rbp-55h] BYREF
  GUID ActivityId; // [rsp+38h] [rbp-51h] BYREF
  GUID v17; // [rsp+48h] [rbp-41h] BYREF
  int v18; // [rsp+58h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v19[2]; // [rsp+60h] [rbp-29h] BYREF
  const char *v20; // [rsp+80h] [rbp-9h]
  __int64 v21; // [rsp+88h] [rbp-1h]
  _WORD *v22; // [rsp+90h] [rbp+7h]
  __int64 v23; // [rsp+98h] [rbp+Fh]
  int *v24; // [rsp+A0h] [rbp+17h]
  __int64 v25; // [rsp+A8h] [rbp+1Fh]

  ActivityId = 0;
  v18 = 0;
  v17 = 0;
  EtwActivityIdControl(5u, &ActivityId);
  EtwActivityIdControl(1u, &v17);
  if ( (unsigned int)dword_140011000 > 4 && (unsigned __int8)tlgKeywordOn(v1, v0, v2) )
  {
    v20 = "DllUnload";
    v21 = 10;
    v23 = 2;
    v14[0] = 206;
    v22 = v14;
    tlgWriteTransfer_EtwWriteTransfer(v3, (unsigned __int8 *)&word_14000E4F6, &v17, &ActivityId, 4u, v19);
  }
  LOBYTE(v18) = 1;
  v6 = WinHvpPreUnInitialize();
  if ( v6 < 0 )
  {
    if ( (_BYTE)v18 )
    {
      if ( (unsigned int)dword_140011000 > 2 && (unsigned __int8)tlgKeywordOn(v5, v4, v7) )
      {
        v20 = "DllUnload";
        v14[0] = 209;
        v21 = 10;
        v22 = v14;
        v23 = 2;
        v24 = &v15;
        v15 = v6;
        v25 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v12, (unsigned __int8 *)byte_14000E491, &v17, 0, 5u, v19);
      }
      EtwActivityIdControl(2u, &ActivityId);
    }
  }
  else
  {
    WinHvpUnInitialize();
    Buffer = WinHvpRegistryPath.Buffer;
    if ( WinHvpRegistryPath.Buffer )
    {
      WinHvpFreePoolWithTag(WinHvpRegistryPath.Buffer, 1433815127);
      WinHvpRegistryPath.Buffer = 0;
    }
    if ( (_BYTE)v18 )
    {
      if ( (unsigned int)dword_140011000 > 4 && (unsigned __int8)tlgKeywordOn(Buffer, v8, v9) )
      {
        v20 = "DllUnload";
        v21 = 10;
        v23 = 2;
        v14[0] = 222;
        v22 = v14;
        tlgWriteTransfer_EtwWriteTransfer(v11, (unsigned __int8 *)byte_14000E4C9, &v17, 0, 4u, v19);
      }
      EtwActivityIdControl(2u, &ActivityId);
      LOBYTE(v18) = 0;
    }
    TraceLoggingUnregister_EtwUnregister();
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001ba40  push    rbp
0x14001ba42  push    rbx
0x14001ba43  push    rsi
0x14001ba44  push    r15
0x14001ba46  lea     rbp, [rsp-3Fh]
0x14001ba4b  sub     rsp, 0C8h
0x14001ba52  mov     rax, cs:__security_cookie
0x14001ba59  xor     rax, rsp
0x14001ba5c  mov     [rbp+57h+var_30], rax
0x14001ba60  xorps   xmm0, xmm0
0x14001ba63  xor     eax, eax
0x14001ba65  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x14001ba69  mov     [rbp+57h+var_88], eax
0x14001ba6c  movups  xmmword ptr [rbp+57h+var_98.Data1], xmm0
0x14001ba70  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x14001ba74  lea     ecx, [rax+5]; ControlCode
0x14001ba77  call    cs:__imp_EtwActivityIdControl
0x14001ba7e  nop     dword ptr [rax+rax+00h]
0x14001ba83  lea     rdx, [rbp+57h+var_98]; ActivityId
0x14001ba87  mov     ecx, 1; ControlCode
0x14001ba8c  call    cs:__imp_EtwActivityIdControl
0x14001ba93  nop     dword ptr [rax+rax+00h]
0x14001ba98  mov     eax, cs:dword_140011000
0x14001ba9e  lea     r15, aDllunload; "DllUnload"
0x14001baa5  mov     esi, 2
0x14001baaa  cmp     eax, 4
0x14001baad  jbe     short loc_14001BAFE
0x14001baaf  call    _tlgKeywordOn
0x14001bab4  test    al, al
0x14001bab6  jz      short loc_14001BAFE
0x14001bab8  mov     [rbp+57h+var_60], r15
0x14001babc  mov     [rbp+57h+var_58], 0Ah
0x14001bac4  mov     eax, 0CEh
0x14001bac9  mov     [rbp+57h+var_48], rsi
0x14001bacd  mov     [rbp+57h+var_B0], ax
0x14001bad1  lea     r9, [rbp+57h+ActivityId]
0x14001bad5  lea     rax, [rbp+57h+var_B0]
0x14001bad9  mov     [rbp+57h+var_50], rax
0x14001badd  lea     r8, [rbp+57h+var_98]
0x14001bae1  lea     rax, [rbp+57h+var_80]
0x14001bae5  mov     [rsp+0E0h+var_B8], rax
0x14001baea  lea     rdx, word_14000E4F6
0x14001baf1  mov     [rsp+0E0h+var_C0], 4
0x14001baf9  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001bafe  mov     byte ptr [rbp+57h+var_88], 1
0x14001bb02  call    WinHvpPreUnInitialize
0x14001bb07  mov     ebx, eax
0x14001bb09  test    eax, eax
0x14001bb0b  js      loc_14001BBB6
0x14001bb11  call    WinHvpUnInitialize
0x14001bb16  mov     rcx, cs:WinHvpRegistryPath.Buffer
0x14001bb1d  test    rcx, rcx
0x14001bb20  jz      short loc_14001BB37
0x14001bb22  mov     edx, 55764857h
0x14001bb27  call    WinHvpFreePoolWithTag
0x14001bb2c  mov     cs:WinHvpRegistryPath.Buffer, 0
0x14001bb37  cmp     byte ptr [rbp+57h+var_88], 0
0x14001bb3b  jz      short loc_14001BBAC
0x14001bb3d  mov     eax, cs:dword_140011000
0x14001bb43  cmp     eax, 4
0x14001bb46  jbe     short loc_14001BB96
0x14001bb48  call    _tlgKeywordOn
0x14001bb4d  test    al, al
0x14001bb4f  jz      short loc_14001BB96
0x14001bb51  mov     [rbp+57h+var_60], r15
0x14001bb55  mov     [rbp+57h+var_58], 0Ah
0x14001bb5d  mov     eax, 0DEh
0x14001bb62  mov     [rbp+57h+var_48], rsi
0x14001bb66  mov     [rbp+57h+var_B0], ax
0x14001bb6a  lea     r8, [rbp+57h+var_98]
0x14001bb6e  lea     rax, [rbp+57h+var_B0]
0x14001bb72  xor     r9d, r9d
0x14001bb75  mov     [rbp+57h+var_50], rax
0x14001bb79  lea     rdx, byte_14000E4C9
0x14001bb80  lea     rax, [rbp+57h+var_80]
0x14001bb84  mov     [rsp+0E0h+var_B8], rax
0x14001bb89  mov     [rsp+0E0h+var_C0], 4
0x14001bb91  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001bb96  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x14001bb9a  mov     ecx, esi; ControlCode
0x14001bb9c  call    cs:__imp_EtwActivityIdControl
0x14001bba3  nop     dword ptr [rax+rax+00h]
0x14001bba8  mov     byte ptr [rbp+57h+var_88], 0
0x14001bbac  call    TraceLoggingUnregister_EtwUnregister
0x14001bbb1  jmp     loc_14001BC39
0x14001bbb6  cmp     byte ptr [rbp+57h+var_88], 0
0x14001bbba  jz      short loc_14001BC39
0x14001bbbc  mov     eax, cs:dword_140011000
0x14001bbc2  cmp     eax, esi
0x14001bbc4  jbe     short loc_14001BC27
0x14001bbc6  call    _tlgKeywordOn
0x14001bbcb  test    al, al
0x14001bbcd  jz      short loc_14001BC27
0x14001bbcf  mov     eax, 0D1h
0x14001bbd4  mov     [rbp+57h+var_60], r15
0x14001bbd8  mov     [rbp+57h+var_B0], ax
0x14001bbdc  lea     r8, [rbp+57h+var_98]
0x14001bbe0  lea     rax, [rbp+57h+var_B0]
0x14001bbe4  mov     [rbp+57h+var_58], 0Ah
0x14001bbec  mov     [rbp+57h+var_50], rax
0x14001bbf0  lea     rdx, byte_14000E491
0x14001bbf7  lea     rax, [rbp+57h+var_AC]
0x14001bbfb  mov     [rbp+57h+var_48], rsi
0x14001bbff  mov     [rbp+57h+var_40], rax
0x14001bc03  xor     r9d, r9d
0x14001bc06  lea     rax, [rbp+57h+var_80]
0x14001bc0a  mov     [rbp+57h+var_AC], ebx
0x14001bc0d  mov     [rsp+0E0h+var_B8], rax
0x14001bc12  mov     [rsp+0E0h+var_C0], 5
0x14001bc1a  mov     [rbp+57h+var_38], 4
0x14001bc22  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001bc27  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x14001bc2b  mov     ecx, esi; ControlCode
0x14001bc2d  call    cs:__imp_EtwActivityIdControl
0x14001bc34  nop     dword ptr [rax+rax+00h]
0x14001bc39  mov     eax, ebx
0x14001bc3b  mov     rcx, [rbp+57h+var_30]
0x14001bc3f  xor     rcx, rsp; StackCookie
0x14001bc42  call    __security_check_cookie
0x14001bc47  add     rsp, 0C8h
0x14001bc4e  pop     r15
0x14001bc50  pop     rsi
0x14001bc51  pop     rbx
0x14001bc52  pop     rbp
0x14001bc53  retn
```
