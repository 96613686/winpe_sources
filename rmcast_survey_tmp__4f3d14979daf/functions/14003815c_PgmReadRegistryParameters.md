# PgmReadRegistryParameters

- ea: `0x14003815c`
- end: `0x140038349`
- name: `PgmReadRegistryParameters`
- size: `493`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14003770c`

## callees

- `0x140005038`
- `0x140005068`
- `0x14000a18c`
- `0x14000a2f8`
- `0x14000a434`
- `0x14003815c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400382f1`
- `ntoskrnl!ZwClose` at `0x140038302`
- `ntoskrnl!ZwClose` at `0x1400382f1`
- `ntoskrnl!ZwClose` at `0x140038302`
- `ntoskrnl!ExAllocatePool2` at `0x140038190`
- `ntoskrnl!ExAllocatePool2` at `0x140038190`

## pseudocode

```c
__int64 __fastcall PgmReadRegistryParameters(struct _UNICODE_STRING *a1, __int64 *a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rbx
  int v7; // eax
  __int64 v8; // rdx
  unsigned __int64 v9; // r9
  HANDLE Handle; // [rsp+40h] [rbp+18h] BYREF
  HANDLE v11; // [rsp+48h] [rbp+20h] BYREF

  v11 = 0;
  Handle = 0;
  Pool2 = ExAllocatePool2(64, 32, 812476240);
  v5 = Pool2;
  if ( Pool2 )
  {
    *a2 = Pool2;
    v7 = PgmOpenRegistryParameters(a1, &v11, &Handle);
    if ( v7 >= 0 )
    {
      if ( (int)ReadRegistryStringValue(Handle, v8, (struct _UNICODE_STRING *)(v5 + 8)) >= 0 )
        *(_DWORD *)(v5 + 4) |= 1u;
      if ( (int)ReadRegistryDwordValue(Handle) >= 0 )
      {
        if ( *(_DWORD *)(v5 + 24) > 0x6DDD00u )
          *(_DWORD *)(v5 + 24) = 7200000;
      }
      else
      {
        *(_DWORD *)(v5 + 24) = 300000;
      }
      if ( (int)ReadRegistryDwordValue(Handle) >= 0 )
      {
        v9 = (unsigned __int64)(unsigned int)ConfiguredMaxPacketSize << 10;
        if ( v9 > 0xFFFFFFFF )
          v9 = 0xFFFF;
        ConfiguredMaxPacketSize = v9;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids, v9);
        }
      }
      ZwClose(Handle);
      ZwClose(v11);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids,
        (unsigned int)v7);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids, 32);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14003815c  mov     rax, rsp
0x14003815f  mov     [rax+8], rbx
0x140038163  mov     [rax+10h], rsi
0x140038167  push    rdi
0x140038168  sub     rsp, 20h
0x14003816c  mov     rdi, rdx
0x14003816f  mov     qword ptr [rax+20h], 0
0x140038177  mov     edx, 20h ; ' '
0x14003817c  mov     qword ptr [rax+18h], 0
0x140038184  mov     rsi, rcx
0x140038187  mov     r8d, 306D6750h
0x14003818d  lea     ecx, [rdx+20h]
0x140038190  call    cs:__imp_ExAllocatePool2
0x140038197  nop     dword ptr [rax+rax+00h]
0x14003819c  mov     rbx, rax
0x14003819f  test    rax, rax
0x1400381a2  jnz     short loc_1400381E1
0x1400381a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400381ab  lea     rbx, WPP_GLOBAL_Control
0x1400381b2  cmp     rcx, rbx
0x1400381b5  jz      short loc_1400381D7
0x1400381b7  mov     eax, [rcx+2Ch]
0x1400381ba  test    al, 2
0x1400381bc  jz      short loc_1400381D7
0x1400381be  mov     rcx, [rcx+18h]
0x1400381c2  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x1400381c9  mov     edx, 13h
0x1400381ce  lea     r9d, [rdx+0Dh]
0x1400381d2  call    WPP_SF_d
0x1400381d7  mov     eax, 0C000009Ah
0x1400381dc  jmp     loc_140038338
0x1400381e1  lea     r8, [rsp+28h+Handle]
0x1400381e6  mov     [rdi], rbx
0x1400381e9  lea     rdx, [rsp+28h+arg_18]
0x1400381ee  mov     rcx, rsi
0x1400381f1  call    PgmOpenRegistryParameters
0x1400381f6  test    eax, eax
0x1400381f8  jns     short loc_14003823A
0x1400381fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140038201  lea     rbx, WPP_GLOBAL_Control
0x140038208  cmp     rcx, rbx
0x14003820b  jz      loc_140038336
0x140038211  mov     edx, [rcx+2Ch]
0x140038214  test    dl, 2
0x140038217  jz      loc_140038336
0x14003821d  mov     rcx, [rcx+18h]
0x140038221  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140038228  mov     edx, 14h
0x14003822d  mov     r9d, eax
0x140038230  call    WPP_SF_d
0x140038235  jmp     loc_140038336
0x14003823a  mov     rcx, [rsp+28h+Handle]; KeyHandle
0x14003823f  lea     r8, [rbx+8]
0x140038243  call    ReadRegistryStringValue
0x140038248  test    eax, eax
0x14003824a  js      short loc_140038250
0x14003824c  or      dword ptr [rbx+4], 1
0x140038250  mov     rcx, [rsp+28h+Handle]; KeyHandle
0x140038255  lea     r8, [rbx+18h]
0x140038259  lea     rdx, aMaxspminterval; "MaxSPMInterval"
0x140038260  call    ReadRegistryDwordValue
0x140038265  test    eax, eax
0x140038267  jns     short loc_140038272
0x140038269  mov     dword ptr [rbx+18h], 493E0h
0x140038270  jmp     short loc_14003827F
0x140038272  mov     eax, 6DDD00h
0x140038277  cmp     [rbx+18h], eax
0x14003827a  jbe     short loc_14003827F
0x14003827c  mov     [rbx+18h], eax
0x14003827f  mov     rcx, [rsp+28h+Handle]; KeyHandle
0x140038284  lea     r8, ConfiguredMaxPacketSize
0x14003828b  lea     rdx, aMaxpacketsize; "MaxPacketSize"
0x140038292  call    ReadRegistryDwordValue
0x140038297  lea     rbx, WPP_GLOBAL_Control
0x14003829e  test    eax, eax
0x1400382a0  js      short loc_1400382EC
0x1400382a2  mov     r9d, cs:ConfiguredMaxPacketSize
0x1400382a9  mov     eax, 0FFFFFFFFh
0x1400382ae  shl     r9, 0Ah
0x1400382b2  cmp     r9, rax
0x1400382b5  jbe     short loc_1400382BD
0x1400382b7  mov     r9d, 0FFFFh
0x1400382bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400382c4  mov     cs:ConfiguredMaxPacketSize, r9d
0x1400382cb  cmp     rcx, rbx
0x1400382ce  jz      short loc_1400382EC
0x1400382d0  mov     eax, [rcx+2Ch]
0x1400382d3  test    al, 10h
0x1400382d5  jz      short loc_1400382EC
0x1400382d7  mov     rcx, [rcx+18h]
0x1400382db  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x1400382e2  mov     edx, 15h
0x1400382e7  call    WPP_SF_d
0x1400382ec  mov     rcx, [rsp+28h+Handle]; Handle
0x1400382f1  call    cs:__imp_ZwClose
0x1400382f8  nop     dword ptr [rax+rax+00h]
0x1400382fd  mov     rcx, [rsp+28h+arg_18]; Handle
0x140038302  call    cs:__imp_ZwClose
0x140038309  nop     dword ptr [rax+rax+00h]
0x14003830e  mov     rcx, cs:WPP_GLOBAL_Control
0x140038315  cmp     rcx, rbx
0x140038318  jz      short loc_140038336
0x14003831a  mov     eax, [rcx+2Ch]
0x14003831d  test    al, 10h
0x14003831f  jz      short loc_140038336
0x140038321  mov     rcx, [rcx+18h]
0x140038325  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x14003832c  mov     edx, 16h
0x140038331  call    WPP_SF_
0x140038336  xor     eax, eax
0x140038338  mov     rbx, [rsp+28h+arg_0]
0x14003833d  mov     rsi, [rsp+28h+arg_8]
0x140038342  add     rsp, 20h
0x140038346  pop     rdi
0x140038347  retn
```
