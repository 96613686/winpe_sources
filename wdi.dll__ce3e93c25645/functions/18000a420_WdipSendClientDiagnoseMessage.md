# WdipSendClientDiagnoseMessage

- ea: `0x18000a420`
- end: `0x18000a73e`
- name: `WdipSendClientDiagnoseMessage`
- size: `798`
- prototype: `__int64 __fastcall(__int64, _OWORD *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b5c0`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180003160`
- `0x180004100`
- `0x180007000`
- `0x1800077e0`
- `0x180007d40`
- `0x18000a420`
- `0x18000d6cc`
- `0x18000d720`
- `0x18000f1b6`
- `0x18000f1c2`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000a69e`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000a69e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000a60c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000a60c`

## pseudocode

```c
__int64 __fastcall WdipSendClientDiagnoseMessage(__int64 a1, _OWORD *a2, int a3)
{
  void *ClientSecurityAttributes; // rbp
  _DWORD *v4; // rsi
  char *v5; // r14
  signed int v7; // ebx
  int Args; // eax
  size_t v9; // rbx
  char *v10; // rax
  int DesktopName; // eax
  int appended; // eax
  size_t v13; // r13
  unsigned int v14; // r15d
  _DWORD *v15; // rax
  _OWORD *v16; // rdx
  signed int v17; // eax
  int v18; // eax
  __int64 v19; // r8
  int v20; // eax
  size_t Size; // [rsp+70h] [rbp+8h] BYREF
  _OWORD *v23; // [rsp+78h] [rbp+10h]
  int v24; // [rsp+80h] [rbp+18h]

  v24 = a3;
  v23 = a2;
  ClientSecurityAttributes = 0;
  LODWORD(Size) = 0;
  v4 = 0;
  v5 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      ClientSecurityAttributes = (void *)WdipCreateClientSecurityAttributes();
      if ( ClientSecurityAttributes )
      {
        Args = WdipGetDesktopName(0, (DWORD *)&Size);
        v7 = Args;
        if ( Args >= 0 )
        {
          v9 = (unsigned int)Size;
          v10 = (char *)WdipAlloc((unsigned int)Size);
          v5 = v10;
          if ( v10 )
          {
            memset_0(v10, 0, v9);
            DesktopName = WdipGetDesktopName(v5, (DWORD *)&Size);
            v7 = DesktopName;
            if ( DesktopName >= 0 )
            {
              appended = WdipAppendNewParameterCollection(*(_QWORD *)(a1 + 24), *(_QWORD *)(a1 + 32));
              v7 = appended;
              if ( appended >= 0 )
              {
                v13 = (unsigned int)Size;
                v14 = **(_DWORD **)(a1 + 32) + Size + 296;
                v15 = WdipAlloc(v14);
                v4 = v15;
                if ( v15 )
                {
                  memset_0(v15, 0, v14);
                  v16 = v23;
                  v4[11] = 10;
                  v4[29] = *(_DWORD *)(a1 + 104);
                  v4[10] = *(_DWORD *)(a1 + 152);
                  v4[30] |= 8 * (_InterlockedExchange((volatile __int32 *)(a1 + 108), *(_DWORD *)(a1 + 108)) & 1);
                  WdipCopyGuid((_OWORD *)v4 + 3, v16);
                  WdipCopyGuid((_OWORD *)v4 + 4, (_OWORD *)(a1 + 40));
                  v17 = EventActivityIdControl(1u, (LPGUID)(a1 + 72));
                  v7 = v17;
                  if ( v17 > 0 )
                    v7 = (unsigned __int16)v17 | 0x80070000;
                  if ( v7 >= 0 )
                  {
                    WdipCopyGuid((_OWORD *)v4 + 6, (_OWORD *)(a1 + 72));
                    v4[37] = 208;
                    v4[31] = v13 + 208;
                    v4[32] = v24;
                    memcpy_0(v4 + 62, v5, v13);
                    v18 = WdipWriteParameterCollectionToMessageBuffer(*(_QWORD *)(a1 + 32), v4, v14);
                    v7 = v18;
                    if ( v18 >= 0 )
                    {
                      if ( v14 > (unsigned __int64)AlpcMaxAllowedMessageLength() || v14 < 0xF8 )
                      {
                        v7 = -2147024774;
                      }
                      else
                      {
                        v20 = WdipSendASyncMessage(
                                v4,
                                (__int64)ClientSecurityAttributes,
                                v19,
                                *(_QWORD *)(a1 + 120),
                                v14);
                        v7 = v20;
                        if ( v20 < 0 )
                          WdipTraceError(
                            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
                            (int)L"WdipSendClientDiagnoseMessage",
                            357,
                            (int)L"Error = %d",
                            v20);
                      }
                    }
                    else
                    {
                      WdipTraceError(
                        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
                        (int)L"WdipSendClientDiagnoseMessage",
                        339,
                        (int)L"Error = %d",
                        v18);
                    }
                  }
                  else
                  {
                    WdipTraceError(
                      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
                      (int)L"WdipSendClientDiagnoseMessage",
                      311,
                      (int)L"Error = %d",
                      v7);
                  }
                }
                else
                {
                  v7 = -2147024882;
                  WdipTraceError(
                    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
                    (int)L"WdipSendClientDiagnoseMessage",
                    288,
                    (int)L"Error = %d",
                    14);
                }
              }
              else
              {
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
                  (int)L"WdipSendClientDiagnoseMessage",
                  274,
                  (int)L"Error = %d",
                  appended);
              }
            }
            else
            {
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
                (int)L"WdipSendClientDiagnoseMessage",
                265,
                (int)L"Error = %d",
                DesktopName);
            }
          }
          else
          {
            v7 = -2147024882;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
              (int)L"WdipSendClientDiagnoseMessage",
              261,
              (int)L"Error = %d",
              14);
          }
        }
        else
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
            (int)L"WdipSendClientDiagnoseMessage",
            258,
            (int)L"Error = %d",
            Args);
        }
      }
      else
      {
        v7 = -2147023528;
      }
    }
    else
    {
      v7 = -2147024809;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
        (int)L"WdipSendClientDiagnoseMessage",
        243,
        (int)L"Error = %d",
        87);
    }
    WdipFree(*(void **)(*(_QWORD *)(a1 + 32) + 8LL));
    *(_QWORD *)(*(_QWORD *)(a1 + 32) + 8LL) = 0;
    *(_OWORD *)*(_QWORD *)(a1 + 32) = 0;
  }
  else
  {
    v7 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandcli.cpp",
      (int)L"WdipSendClientDiagnoseMessage",
      242,
      (int)L"Error = %d",
      87);
  }
  WdipFree(v4);
  WdipFree(v5);
  if ( ClientSecurityAttributes )
    WdipFree(ClientSecurityAttributes);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000a420  mov     [rsp+arg_18], rbx
0x18000a425  mov     [rsp+arg_10], r8d
0x18000a42a  mov     [rsp+arg_8], rdx
0x18000a42f  push    rbp
0x18000a430  push    rsi
0x18000a431  push    rdi
0x18000a432  push    r12
0x18000a434  push    r13
0x18000a436  push    r14
0x18000a438  push    r15
0x18000a43a  sub     rsp, 30h
0x18000a43e  xor     ebp, ebp
0x18000a440  mov     dword ptr [rsp+68h+Size], 0
0x18000a448  xor     esi, esi
0x18000a44a  xor     r14d, r14d
0x18000a44d  mov     rax, rdx
0x18000a450  mov     rdi, rcx
0x18000a453  test    rcx, rcx
0x18000a456  jnz     short loc_18000A48A
0x18000a458  lea     r9, aErrorD_0; "Error = %d"
0x18000a45f  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x18000a467  mov     r8d, 0F2h; int
0x18000a46d  lea     rdx, aWdipsendclient; "WdipSendClientDiagnoseMessage"
0x18000a474  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000a47b  mov     ebx, 80070057h
0x18000a480  call    WdipTraceError
0x18000a485  jmp     loc_18000A707
0x18000a48a  test    rax, rax
0x18000a48d  jnz     short loc_18000A4C1
0x18000a48f  mov     ebx, 80070057h
0x18000a494  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x18000a49c  mov     r8d, 0F3h; int
0x18000a4a2  lea     r9, aErrorD_0; "Error = %d"
0x18000a4a9  lea     rdx, aWdipsendclient; "WdipSendClientDiagnoseMessage"
0x18000a4b0  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000a4b7  call    WdipTraceError
0x18000a4bc  jmp     loc_18000A6E4
0x18000a4c1  call    WdipCreateClientSecurityAttributes
0x18000a4c6  mov     rbp, rax
0x18000a4c9  test    rax, rax
0x18000a4cc  jnz     short loc_18000A4D8
0x18000a4ce  mov     ebx, 80070558h
0x18000a4d3  jmp     loc_18000A6E4
0x18000a4d8  lea     rdx, [rsp+68h+Size]
0x18000a4dd  xor     ecx, ecx; pvInfo
0x18000a4df  call    WdipGetDesktopName
0x18000a4e4  mov     ebx, eax
0x18000a4e6  test    eax, eax
0x18000a4e8  jns     short loc_18000A4F9
0x18000a4ea  movzx   ecx, ax
0x18000a4ed  mov     r8d, 102h
0x18000a4f3  mov     dword ptr [rsp+68h+Args], ecx
0x18000a4f7  jmp     short loc_18000A4A2
0x18000a4f9  mov     ebx, dword ptr [rsp+68h+Size]
0x18000a4fd  mov     ecx, ebx
0x18000a4ff  call    WdipAlloc
0x18000a504  mov     r14, rax
0x18000a507  test    rax, rax
0x18000a50a  jnz     short loc_18000A521
0x18000a50c  mov     ebx, 8007000Eh
0x18000a511  mov     dword ptr [rsp+68h+Args], 0Eh
0x18000a519  mov     r8d, 105h
0x18000a51f  jmp     short loc_18000A4A2
0x18000a521  mov     r8, rbx; Size
0x18000a524  xor     edx, edx; Val
0x18000a526  mov     rcx, r14; void *
0x18000a529  call    memset_0
0x18000a52e  lea     rdx, [rsp+68h+Size]
0x18000a533  mov     rcx, r14; pvInfo
0x18000a536  call    WdipGetDesktopName
0x18000a53b  mov     ebx, eax
0x18000a53d  test    eax, eax
0x18000a53f  jns     short loc_18000A553
0x18000a541  movzx   eax, ax
0x18000a544  mov     r8d, 109h
0x18000a54a  mov     dword ptr [rsp+68h+Args], eax
0x18000a54e  jmp     loc_18000A4A2
0x18000a553  mov     rdx, [rdi+20h]
0x18000a557  mov     rcx, [rdi+18h]
0x18000a55b  call    WdipAppendNewParameterCollection
0x18000a560  mov     ebx, eax
0x18000a562  test    eax, eax
0x18000a564  jns     short loc_18000A578
0x18000a566  movzx   eax, ax
0x18000a569  mov     r8d, 112h
0x18000a56f  mov     dword ptr [rsp+68h+Args], eax
0x18000a573  jmp     loc_18000A4A2
0x18000a578  mov     rax, [rdi+20h]
0x18000a57c  mov     r13d, dword ptr [rsp+68h+Size]
0x18000a581  lea     r15d, [r13+128h]
0x18000a588  add     r15d, [rax]
0x18000a58b  mov     ecx, r15d
0x18000a58e  mov     r12d, r15d
0x18000a591  call    WdipAlloc
0x18000a596  mov     rsi, rax
0x18000a599  test    rax, rax
0x18000a59c  jnz     short loc_18000A5B6
0x18000a59e  mov     ebx, 8007000Eh
0x18000a5a3  mov     dword ptr [rsp+68h+Args], 0Eh
0x18000a5ab  mov     r8d, 120h
0x18000a5b1  jmp     loc_18000A4A2
0x18000a5b6  mov     r8, r12; Size
0x18000a5b9  xor     edx, edx; Val
0x18000a5bb  mov     rcx, rsi; void *
0x18000a5be  call    memset_0
0x18000a5c3  mov     rdx, [rsp+68h+arg_8]
0x18000a5c8  lea     rcx, [rsi+30h]
0x18000a5cc  mov     dword ptr [rsi+2Ch], 0Ah
0x18000a5d3  mov     eax, [rdi+68h]
0x18000a5d6  mov     [rsi+74h], eax
0x18000a5d9  mov     eax, [rdi+98h]
0x18000a5df  mov     [rsi+28h], eax
0x18000a5e2  mov     eax, [rdi+6Ch]
0x18000a5e5  xchg    eax, [rdi+6Ch]
0x18000a5e8  and     eax, 1
0x18000a5eb  shl     eax, 3
0x18000a5ee  or      [rsi+78h], eax
0x18000a5f1  call    WdipCopyGuid
0x18000a5f6  lea     rdx, [rdi+28h]
0x18000a5fa  lea     rcx, [rsi+40h]
0x18000a5fe  call    WdipCopyGuid
0x18000a603  lea     rdx, [rdi+48h]; ActivityId
0x18000a607  mov     ecx, 1; ControlCode
0x18000a60c  call    cs:__imp_EventActivityIdControl
0x18000a612  mov     ebx, eax
0x18000a614  test    eax, eax
0x18000a616  jle     short loc_18000A621
0x18000a618  movzx   ebx, ax
0x18000a61b  or      ebx, 80070000h
0x18000a621  test    ebx, ebx
0x18000a623  jns     short loc_18000A637
0x18000a625  movzx   eax, bx
0x18000a628  mov     r8d, 137h
0x18000a62e  mov     dword ptr [rsp+68h+Args], eax
0x18000a632  jmp     loc_18000A4A2
0x18000a637  lea     rcx, [rsi+60h]
0x18000a63b  lea     rdx, [rdi+48h]
0x18000a63f  call    WdipCopyGuid
0x18000a644  lea     eax, [r13+0D0h]
0x18000a64b  mov     dword ptr [rsi+94h], 0D0h
0x18000a655  mov     [rsi+7Ch], eax
0x18000a658  lea     rcx, [rsi+0F8h]; void *
0x18000a65f  mov     eax, [rsp+68h+arg_10]
0x18000a666  mov     r8, r13; Size
0x18000a669  mov     rdx, r14; Src
0x18000a66c  mov     [rsi+80h], eax
0x18000a672  call    memcpy_0
0x18000a677  mov     rcx, [rdi+20h]
0x18000a67b  mov     r8d, r15d
0x18000a67e  mov     rdx, rsi
0x18000a681  call    WdipWriteParameterCollectionToMessageBuffer
0x18000a686  mov     ebx, eax
0x18000a688  test    eax, eax
0x18000a68a  jns     short loc_18000A69E
0x18000a68c  movzx   eax, ax
0x18000a68f  mov     r8d, 153h
0x18000a695  mov     dword ptr [rsp+68h+Args], eax
0x18000a699  jmp     loc_18000A4A2
0x18000a69e  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18000a6a4  cmp     r12, rax
0x18000a6a7  ja      short loc_18000A6DF
0x18000a6a9  cmp     r15d, 0F8h
0x18000a6b0  jb      short loc_18000A6DF
0x18000a6b2  mov     r9, [rdi+78h]
0x18000a6b6  mov     rdx, rbp
0x18000a6b9  mov     rcx, rsi
0x18000a6bc  mov     word ptr [rsp+68h+Args], r15w
0x18000a6c2  call    WdipSendASyncMessage
0x18000a6c7  mov     ebx, eax
0x18000a6c9  test    eax, eax
0x18000a6cb  jns     short loc_18000A6E4
0x18000a6cd  movzx   eax, ax
0x18000a6d0  mov     r8d, 165h
0x18000a6d6  mov     dword ptr [rsp+68h+Args], eax
0x18000a6da  jmp     loc_18000A4A2
0x18000a6df  mov     ebx, 8007007Ah
0x18000a6e4  mov     rcx, [rdi+20h]
0x18000a6e8  mov     rcx, [rcx+8]
0x18000a6ec  call    WdipFree
0x18000a6f1  mov     rax, [rdi+20h]
0x18000a6f5  xorps   xmm0, xmm0
0x18000a6f8  mov     qword ptr [rax+8], 0
0x18000a700  mov     rax, [rdi+20h]
0x18000a704  movups  xmmword ptr [rax], xmm0
0x18000a707  mov     rcx, rsi
0x18000a70a  call    WdipFree
0x18000a70f  mov     rcx, r14
0x18000a712  call    WdipFree
0x18000a717  test    rbp, rbp
0x18000a71a  jz      short loc_18000A724
0x18000a71c  mov     rcx, rbp
0x18000a71f  call    WdipFree
0x18000a724  mov     eax, ebx
0x18000a726  mov     rbx, [rsp+68h+arg_18]
0x18000a72e  add     rsp, 30h
0x18000a732  pop     r15
0x18000a734  pop     r14
0x18000a736  pop     r13
0x18000a738  pop     r12
0x18000a73a  pop     rdi
0x18000a73b  pop     rsi
0x18000a73c  pop     rbp
0x18000a73d  retn
```
