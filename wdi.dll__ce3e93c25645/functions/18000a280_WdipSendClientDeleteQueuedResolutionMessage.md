# WdipSendClientDeleteQueuedResolutionMessage

- ea: `0x18000a280`
- end: `0x18000a419`
- name: `WdipSendClientDeleteQueuedResolutionMessage`
- size: `409`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b4a0`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180003160`
- `0x1800041a0`
- `0x180007000`
- `0x18000a280`
- `0x18000d6cc`
- `0x18000f1c2`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000a2d2`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000a300`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000a2d2`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000a300`

## string_xrefs

- `0x18000a3df`: `WdipSendClientDeleteQueuedResolutionMessage`

## pseudocode

```c
__int64 __fastcall WdipSendClientDeleteQueuedResolutionMessage(__int64 a1, _OWORD *a2)
{
  void *v4; // rbp
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  _DWORD *v7; // rsi
  int v8; // ebx
  SIZE_T v9; // rax
  size_t v10; // rax
  __int64 ClientSecurityAttributes; // rax
  int Args; // eax

  v4 = 0;
  v5 = WdipAlloc(0xF8u);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0xF8u);
    v9 = AlpcMaxAllowedMessageLength();
    v7 = WdipAlloc(v9);
    if ( v7 )
    {
      v10 = AlpcMaxAllowedMessageLength();
      memset_0(v7, 0, v10);
      v6[11] = 24;
      v6[29] = *(_DWORD *)(a1 + 104);
      v6[10] = *(_DWORD *)(a1 + 152);
      v6[30] |= 8 * (_InterlockedExchange((volatile __int32 *)(a1 + 108), *(_DWORD *)(a1 + 108)) & 1);
      WdipCopyGuid((_OWORD *)v6 + 8, a2);
      WdipCopyGuid((_OWORD *)v6 + 4, (_OWORD *)(a1 + 40));
      WdipCopyGuid((_OWORD *)v6 + 3, (_OWORD *)(a1 + 88));
      WdipCopyGuid((_OWORD *)v6 + 6, (_OWORD *)(a1 + 72));
      ClientSecurityAttributes = WdipCreateClientSecurityAttributes();
      v4 = (void *)ClientSecurityAttributes;
      if ( ClientSecurityAttributes )
      {
        v6[31] = 208;
        Args = WdipSendSyncMessage((_DWORD)v6, (_DWORD)v7, ClientSecurityAttributes, *(_QWORD *)(a1 + 120), 248);
        v8 = Args;
        if ( Args >= 0 )
        {
          v8 = v7[28];
          if ( v8 < 0 )
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
              (int)L"WdipSendClientDeleteQueuedResolutionMessage",
              857,
              (int)L"Error = %d",
              v8);
        }
        else
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
            (int)L"WdipSendClientDeleteQueuedResolutionMessage",
            851,
            (int)L"Error = %d",
            Args);
        }
      }
      else
      {
        v8 = -2147023528;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
          (int)L"WdipSendClientDeleteQueuedResolutionMessage",
          840,
          (int)L"Error = %d",
          88);
      }
    }
    else
    {
      v8 = -2147024882;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
        (int)L"WdipSendClientDeleteQueuedResolutionMessage",
        819,
        (int)L"Error = %d",
        14);
    }
  }
  else
  {
    v7 = 0;
    v8 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
      (int)L"WdipSendClientDeleteQueuedResolutionMessage",
      812,
      (int)L"Error = %d",
      14);
  }
  WdipFree(v6);
  WdipFree(v7);
  WdipFree(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a280  push    rbx
0x18000a282  push    rbp
0x18000a283  push    rsi
0x18000a284  push    rdi
0x18000a285  push    r14
0x18000a287  push    r15
0x18000a289  sub     rsp, 38h
0x18000a28d  mov     rbx, rcx
0x18000a290  mov     r15d, 0F8h
0x18000a296  mov     ecx, r15d
0x18000a299  mov     r14, rdx
0x18000a29c  xor     ebp, ebp
0x18000a29e  call    WdipAlloc
0x18000a2a3  mov     rdi, rax
0x18000a2a6  test    rax, rax
0x18000a2a9  jnz     short loc_18000A2C5
0x18000a2ab  xor     esi, esi
0x18000a2ad  mov     dword ptr [rsp+68h+Args], 0Eh
0x18000a2b5  mov     ebx, 8007000Eh
0x18000a2ba  mov     r8d, 32Ch
0x18000a2c0  jmp     loc_18000A3D8
0x18000a2c5  mov     r8, r15; Size
0x18000a2c8  xor     edx, edx; Val
0x18000a2ca  mov     rcx, rdi; void *
0x18000a2cd  call    memset_0
0x18000a2d2  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18000a2d8  mov     rcx, rax
0x18000a2db  call    WdipAlloc
0x18000a2e0  mov     rsi, rax
0x18000a2e3  test    rax, rax
0x18000a2e6  jnz     short loc_18000A300
0x18000a2e8  mov     ebx, 8007000Eh
0x18000a2ed  mov     dword ptr [rsp+68h+Args], 0Eh
0x18000a2f5  mov     r8d, 333h
0x18000a2fb  jmp     loc_18000A3D8
0x18000a300  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18000a306  xor     edx, edx; Val
0x18000a308  mov     rcx, rsi; void *
0x18000a30b  mov     r8, rax; Size
0x18000a30e  call    memset_0
0x18000a313  mov     dword ptr [rdi+2Ch], 18h
0x18000a31a  lea     rcx, [rdi+80h]
0x18000a321  mov     eax, [rbx+68h]
0x18000a324  mov     rdx, r14
0x18000a327  mov     [rdi+74h], eax
0x18000a32a  mov     eax, [rbx+98h]
0x18000a330  mov     [rdi+28h], eax
0x18000a333  mov     eax, [rbx+6Ch]
0x18000a336  xchg    eax, [rbx+6Ch]
0x18000a339  and     eax, 1
0x18000a33c  shl     eax, 3
0x18000a33f  or      [rdi+78h], eax
0x18000a342  call    WdipCopyGuid
0x18000a347  lea     rdx, [rbx+28h]
0x18000a34b  lea     rcx, [rdi+40h]
0x18000a34f  call    WdipCopyGuid
0x18000a354  lea     rdx, [rbx+58h]
0x18000a358  lea     rcx, [rdi+30h]
0x18000a35c  call    WdipCopyGuid
0x18000a361  lea     rdx, [rbx+48h]
0x18000a365  lea     rcx, [rdi+60h]
0x18000a369  call    WdipCopyGuid
0x18000a36e  call    WdipCreateClientSecurityAttributes
0x18000a373  mov     rbp, rax
0x18000a376  test    rax, rax
0x18000a379  jnz     short loc_18000A390
0x18000a37b  mov     ebx, 80070558h
0x18000a380  mov     dword ptr [rsp+68h+Args], 558h
0x18000a388  mov     r8d, 348h
0x18000a38e  jmp     short loc_18000A3D8
0x18000a390  mov     dword ptr [rdi+7Ch], 0D0h
0x18000a397  mov     r8, rax
0x18000a39a  mov     r9, [rbx+78h]
0x18000a39e  mov     rdx, rsi
0x18000a3a1  mov     rcx, rdi
0x18000a3a4  mov     word ptr [rsp+68h+Args], r15w
0x18000a3aa  call    WdipSendSyncMessage
0x18000a3af  mov     ebx, eax
0x18000a3b1  test    eax, eax
0x18000a3b3  jns     short loc_18000A3C4
0x18000a3b5  movzx   ecx, ax
0x18000a3b8  mov     r8d, 353h
0x18000a3be  mov     dword ptr [rsp+68h+Args], ecx
0x18000a3c2  jmp     short loc_18000A3D8
0x18000a3c4  mov     ebx, [rsi+70h]
0x18000a3c7  test    ebx, ebx
0x18000a3c9  jns     short loc_18000A3F2
0x18000a3cb  movzx   eax, bx
0x18000a3ce  mov     r8d, 359h; int
0x18000a3d4  mov     dword ptr [rsp+68h+Args], eax; Args
0x18000a3d8  lea     r9, aErrorD_0; "Error = %d"
0x18000a3df  lea     rdx, aWdipsendclient_4; "WdipSendClientDeleteQueuedResolutionMes"...
0x18000a3e6  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000a3ed  call    WdipTraceError
0x18000a3f2  mov     rcx, rdi
0x18000a3f5  call    WdipFree
0x18000a3fa  mov     rcx, rsi
0x18000a3fd  call    WdipFree
0x18000a402  mov     rcx, rbp
0x18000a405  call    WdipFree
0x18000a40a  mov     eax, ebx
0x18000a40c  add     rsp, 38h
0x18000a410  pop     r15
0x18000a412  pop     r14
0x18000a414  pop     rdi
0x18000a415  pop     rsi
0x18000a416  pop     rbp
0x18000a417  pop     rbx
0x18000a418  retn
```
