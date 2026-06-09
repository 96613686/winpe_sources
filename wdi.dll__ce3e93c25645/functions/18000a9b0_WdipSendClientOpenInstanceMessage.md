# WdipSendClientOpenInstanceMessage

- ea: `0x18000a9b0`
- end: `0x18000ab66`
- name: `WdipSendClientOpenInstanceMessage`
- size: `438`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ca80`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180003160`
- `0x1800041a0`
- `0x180007000`
- `0x18000a9b0`
- `0x18000d6cc`
- `0x18000dc50`
- `0x18000f1c2`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000aa01`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000aa2f`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000aa01`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000aa2f`

## string_xrefs

- `0x18000ab2c`: `WdipSendClientOpenInstanceMessage`

## pseudocode

```c
__int64 __fastcall WdipSendClientOpenInstanceMessage(__int64 a1, _OWORD *a2)
{
  void *v4; // r14
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  _DWORD *v7; // rsi
  int v8; // ebx
  SIZE_T v9; // rax
  size_t v10; // rax
  __int64 ClientSecurityAttributes; // rax
  int Args; // eax
  int updated; // eax
  int v14; // r8d

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
      v6[11] = 26;
      v6[29] = *(_DWORD *)(a1 + 104);
      v6[10] = *(_DWORD *)(a1 + 152);
      v6[30] |= 8 * (_InterlockedExchange((volatile __int32 *)(a1 + 108), *(_DWORD *)(a1 + 108)) & 1);
      WdipCopyGuid((_OWORD *)v6 + 4, (_OWORD *)(a1 + 40));
      WdipCopyGuid((_OWORD *)v6 + 3, (_OWORD *)(a1 + 88));
      WdipCopyGuid((_OWORD *)v6 + 6, (_OWORD *)(a1 + 72));
      WdipCopyGuid((_OWORD *)v6 + 8, a2);
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
          if ( v8 >= 0 )
          {
            updated = WdipUpdateInstanceFromMessageBuffer(a1, v7, a2);
            v8 = updated;
            if ( updated >= 0 )
              goto LABEL_14;
            v14 = 204;
          }
          else
          {
            LOBYTE(updated) = v7[28];
            v14 = 195;
          }
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
            (int)L"WdipSendClientOpenInstanceMessage",
            v14,
            (int)L"Error = %d",
            updated);
          goto LABEL_14;
        }
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
          (int)L"WdipSendClientOpenInstanceMessage",
          189,
          (int)L"Error = %d",
          Args);
      }
      else
      {
        v8 = -2147023528;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
          (int)L"WdipSendClientOpenInstanceMessage",
          178,
          (int)L"Error = %d",
          88);
      }
    }
    else
    {
      v8 = -2147024882;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
        (int)L"WdipSendClientOpenInstanceMessage",
        159,
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
      (int)L"WdipSendClientOpenInstanceMessage",
      152,
      (int)L"Error = %d",
      14);
  }
LABEL_14:
  WdipFree(v6);
  WdipFree(v7);
  WdipFree(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a9b0  push    rbx
0x18000a9b2  push    rbp
0x18000a9b3  push    rsi
0x18000a9b4  push    rdi
0x18000a9b5  push    r14
0x18000a9b7  push    r15
0x18000a9b9  sub     rsp, 38h
0x18000a9bd  mov     rbp, rcx
0x18000a9c0  mov     ebx, 0F8h
0x18000a9c5  mov     ecx, ebx
0x18000a9c7  mov     r15, rdx
0x18000a9ca  xor     r14d, r14d
0x18000a9cd  call    WdipAlloc
0x18000a9d2  mov     rdi, rax
0x18000a9d5  test    rax, rax
0x18000a9d8  jnz     short loc_18000A9F4
0x18000a9da  xor     esi, esi
0x18000a9dc  mov     dword ptr [rsp+68h+Args], 0Eh
0x18000a9e4  mov     ebx, 8007000Eh
0x18000a9e9  mov     r8d, 98h
0x18000a9ef  jmp     loc_18000AB25
0x18000a9f4  mov     r8, rbx; Size
0x18000a9f7  xor     edx, edx; Val
0x18000a9f9  mov     rcx, rdi; void *
0x18000a9fc  call    memset_0
0x18000aa01  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18000aa07  mov     rcx, rax
0x18000aa0a  call    WdipAlloc
0x18000aa0f  mov     rsi, rax
0x18000aa12  test    rax, rax
0x18000aa15  jnz     short loc_18000AA2F
0x18000aa17  mov     ebx, 8007000Eh
0x18000aa1c  mov     dword ptr [rsp+68h+Args], 0Eh
0x18000aa24  mov     r8d, 9Fh
0x18000aa2a  jmp     loc_18000AB25
0x18000aa2f  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18000aa35  xor     edx, edx; Val
0x18000aa37  mov     rcx, rsi; void *
0x18000aa3a  mov     r8, rax; Size
0x18000aa3d  call    memset_0
0x18000aa42  mov     dword ptr [rdi+2Ch], 1Ah
0x18000aa49  lea     rdx, [rbp+28h]
0x18000aa4d  mov     eax, [rbp+68h]
0x18000aa50  lea     rcx, [rdi+40h]
0x18000aa54  mov     [rdi+74h], eax
0x18000aa57  mov     eax, [rbp+98h]
0x18000aa5d  mov     [rdi+28h], eax
0x18000aa60  mov     eax, [rbp+6Ch]
0x18000aa63  xchg    eax, [rbp+6Ch]
0x18000aa66  and     eax, 1
0x18000aa69  shl     eax, 3
0x18000aa6c  or      [rdi+78h], eax
0x18000aa6f  call    WdipCopyGuid
0x18000aa74  lea     rdx, [rbp+58h]
0x18000aa78  lea     rcx, [rdi+30h]
0x18000aa7c  call    WdipCopyGuid
0x18000aa81  lea     rdx, [rbp+48h]
0x18000aa85  lea     rcx, [rdi+60h]
0x18000aa89  call    WdipCopyGuid
0x18000aa8e  lea     rcx, [rdi+80h]
0x18000aa95  mov     rdx, r15
0x18000aa98  call    WdipCopyGuid
0x18000aa9d  call    WdipCreateClientSecurityAttributes
0x18000aaa2  mov     r14, rax
0x18000aaa5  test    rax, rax
0x18000aaa8  jnz     short loc_18000AABF
0x18000aaaa  mov     ebx, 80070558h
0x18000aaaf  mov     dword ptr [rsp+68h+Args], 558h
0x18000aab7  mov     r8d, 0B2h
0x18000aabd  jmp     short loc_18000AB25
0x18000aabf  mov     dword ptr [rdi+7Ch], 0D0h
0x18000aac6  mov     r8, rax
0x18000aac9  mov     r9, [rbp+78h]
0x18000aacd  mov     rdx, rsi
0x18000aad0  mov     rcx, rdi
0x18000aad3  mov     word ptr [rsp+68h+Args], bx
0x18000aad8  call    WdipSendSyncMessage
0x18000aadd  mov     ebx, eax
0x18000aadf  test    eax, eax
0x18000aae1  jns     short loc_18000AAF2
0x18000aae3  movzx   ecx, ax
0x18000aae6  mov     r8d, 0BDh
0x18000aaec  mov     dword ptr [rsp+68h+Args], ecx
0x18000aaf0  jmp     short loc_18000AB25
0x18000aaf2  mov     ebx, [rsi+70h]
0x18000aaf5  test    ebx, ebx
0x18000aaf7  jns     short loc_18000AB04
0x18000aaf9  movzx   eax, bx
0x18000aafc  mov     r8d, 0C3h
0x18000ab02  jmp     short loc_18000AB21
0x18000ab04  mov     r8, r15
0x18000ab07  mov     rdx, rsi
0x18000ab0a  mov     rcx, rbp
0x18000ab0d  call    WdipUpdateInstanceFromMessageBuffer
0x18000ab12  mov     ebx, eax
0x18000ab14  test    eax, eax
0x18000ab16  jns     short loc_18000AB3F
0x18000ab18  movzx   eax, ax
0x18000ab1b  mov     r8d, 0CCh; int
0x18000ab21  mov     dword ptr [rsp+68h+Args], eax; Args
0x18000ab25  lea     r9, aErrorD_0; "Error = %d"
0x18000ab2c  lea     rdx, aWdipsendclient_6; "WdipSendClientOpenInstanceMessage"
0x18000ab33  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000ab3a  call    WdipTraceError
0x18000ab3f  mov     rcx, rdi
0x18000ab42  call    WdipFree
0x18000ab47  mov     rcx, rsi
0x18000ab4a  call    WdipFree
0x18000ab4f  mov     rcx, r14
0x18000ab52  call    WdipFree
0x18000ab57  mov     eax, ebx
0x18000ab59  add     rsp, 38h
0x18000ab5d  pop     r15
0x18000ab5f  pop     r14
0x18000ab61  pop     rdi
0x18000ab62  pop     rsi
0x18000ab63  pop     rbp
0x18000ab64  pop     rbx
0x18000ab65  retn
```
