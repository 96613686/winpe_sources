# VistaEventProcessor::GetEvtChannelProperty(void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18001cee8`
- end: `0x18001d0d4`
- name: `?GetEvtChannelProperty@VistaEventProcessor@@CAXPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(EVT_HANDLE ChannelConfig, EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001c750`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180011270`
- `0x18001cee8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d01f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d01f`
- `wevtapi!EvtGetChannelConfigProperty` at `0x18001cf36`
- `wevtapi!EvtGetChannelConfigProperty` at `0x18001d011`
- `wevtapi!EvtGetChannelConfigProperty` at `0x18001cf36`
- `wevtapi!EvtGetChannelConfigProperty` at `0x18001d011`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VistaEventProcessor::GetEvtChannelProperty(
        EVT_HANDLE ChannelConfig,
        EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId,
        __int64 a3)
{
  struct _EVT_VARIANT *PropertyValueBuffer; // rax
  DWORD LastError; // ebx
  struct _EVT_VARIANT *v8; // rax
  DWORD v9; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-40h] BYREF
  char v12; // [rsp+38h] [rbp-38h]
  const char *v13; // [rsp+40h] [rbp-30h]
  __int64 v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h]
  DWORD v16; // [rsp+58h] [rbp-18h]
  int v17; // [rsp+5Ch] [rbp-14h]
  int v18; // [rsp+60h] [rbp-10h]
  DWORD PropertyValueBufferUsed; // [rsp+A0h] [rbp+30h] BYREF

  std::vector<unsigned char>::resize(a3, 16);
  PropertyValueBuffer = *(struct _EVT_VARIANT **)a3;
  PropertyValueBufferUsed = *(_DWORD *)(a3 + 8) - *(_QWORD *)a3;
  if ( !EvtGetChannelConfigProperty(
          ChannelConfig,
          PropertyId,
          0,
          PropertyValueBufferUsed,
          PropertyValueBuffer,
          &PropertyValueBufferUsed) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, LastError);
      }
      v12 = 0;
      v13 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
      v14 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v15 = 0;
      v16 = LastError;
      v17 = -1;
      v18 = 184;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    std::vector<unsigned char>::resize(a3, PropertyValueBufferUsed);
    v8 = *(struct _EVT_VARIANT **)a3;
    PropertyValueBufferUsed = *(_DWORD *)(a3 + 8) - *(_QWORD *)a3;
    if ( !EvtGetChannelConfigProperty(
            ChannelConfig,
            PropertyId,
            0,
            PropertyValueBufferUsed,
            v8,
            &PropertyValueBufferUsed) )
    {
      v9 = GetLastError();
      if ( !v9 )
        v9 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, v9);
      }
      v12 = 0;
      v13 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
      v14 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v15 = 0;
      v16 = v9;
      v17 = -1;
      v18 = 193;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  return std::vector<unsigned char>::resize(a3, PropertyValueBufferUsed);
}

```

## disassembly

```asm
0x18001cee8  mov     [rsp-18h+arg_0], rbx
0x18001ceed  mov     [rsp-18h+arg_8], rsi
0x18001cef2  push    rbp
0x18001cef3  push    rdi
0x18001cef4  push    r14
0x18001cef6  mov     rbp, rsp
0x18001cef9  sub     rsp, 70h
0x18001cefd  mov     esi, edx
0x18001ceff  mov     r14, rcx
0x18001cf02  mov     edx, 10h
0x18001cf07  mov     rcx, r8
0x18001cf0a  mov     rdi, r8
0x18001cf0d  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001cf12  mov     rax, [rdi]
0x18001cf15  lea     rcx, [rbp+arg_10]
0x18001cf19  mov     r9d, [rdi+8]
0x18001cf1d  xor     r8d, r8d; Flags
0x18001cf20  mov     [rsp+70h+PropertyValueBufferUsed], rcx; PropertyValueBufferUsed
0x18001cf25  sub     r9d, eax; PropertyValueBufferSize
0x18001cf28  mov     rcx, r14; ChannelConfig
0x18001cf2b  mov     [rbp+arg_10], r9d
0x18001cf2f  mov     edx, esi; PropertyId
0x18001cf31  mov     [rsp+70h+PropertyValueBuffer], rax; PropertyValueBuffer
0x18001cf36  call    cs:__imp_EvtGetChannelConfigProperty
0x18001cf3c  test    eax, eax
0x18001cf3e  jnz     loc_18001D0B4
0x18001cf44  call    cs:__imp_GetLastError
0x18001cf4a  mov     ebx, eax
0x18001cf4c  cmp     eax, 7Ah ; 'z'
0x18001cf4f  jz      loc_18001CFE2
0x18001cf55  test    ebx, ebx
0x18001cf57  mov     eax, 507h
0x18001cf5c  cmovz   ebx, eax
0x18001cf5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf66  lea     rax, WPP_GLOBAL_Control
0x18001cf6d  cmp     rcx, rax
0x18001cf70  jz      short loc_18001CF96
0x18001cf72  test    byte ptr [rcx+1Ch], 1
0x18001cf76  jz      short loc_18001CF96
0x18001cf78  cmp     byte ptr [rcx+19h], 2
0x18001cf7c  jb      short loc_18001CF96
0x18001cf7e  mov     rcx, [rcx+10h]
0x18001cf82  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001cf89  mov     edx, 11h
0x18001cf8e  mov     r9d, ebx
0x18001cf91  call    WPP_SF_D
0x18001cf96  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001cf9d  mov     [rbp+var_38], 0
0x18001cfa1  mov     [rbp+var_30], rax
0x18001cfa5  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001cfac  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001cfb3  mov     [rbp+var_28], 0
0x18001cfbb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001cfbf  mov     [rbp+pExceptionObject], rax
0x18001cfc3  mov     [rbp+var_20], 0
0x18001cfcb  mov     [rbp+var_18], ebx
0x18001cfce  mov     [rbp+var_14], 0FFFFFFFFh
0x18001cfd5  mov     [rbp+var_10], 0B8h
0x18001cfdc  call    _CxxThrowException_0
0x18001cfe2  mov     edx, [rbp+arg_10]
0x18001cfe5  mov     rcx, rdi
0x18001cfe8  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001cfed  mov     rax, [rdi]
0x18001cff0  lea     rcx, [rbp+arg_10]
0x18001cff4  mov     r9d, [rdi+8]
0x18001cff8  xor     r8d, r8d; Flags
0x18001cffb  mov     [rsp+70h+PropertyValueBufferUsed], rcx; PropertyValueBufferUsed
0x18001d000  sub     r9d, eax; PropertyValueBufferSize
0x18001d003  mov     rcx, r14; ChannelConfig
0x18001d006  mov     [rbp+arg_10], r9d
0x18001d00a  mov     edx, esi; PropertyId
0x18001d00c  mov     [rsp+70h+PropertyValueBuffer], rax; PropertyValueBuffer
0x18001d011  call    cs:__imp_EvtGetChannelConfigProperty
0x18001d017  test    eax, eax
0x18001d019  jnz     loc_18001D0B4
0x18001d01f  call    cs:__imp_GetLastError
0x18001d025  mov     ebx, eax
0x18001d027  mov     eax, 507h
0x18001d02c  test    ebx, ebx
0x18001d02e  cmovz   ebx, eax
0x18001d031  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d038  lea     rax, WPP_GLOBAL_Control
0x18001d03f  cmp     rcx, rax
0x18001d042  jz      short loc_18001D068
0x18001d044  test    byte ptr [rcx+1Ch], 1
0x18001d048  jz      short loc_18001D068
0x18001d04a  cmp     byte ptr [rcx+19h], 2
0x18001d04e  jb      short loc_18001D068
0x18001d050  mov     rcx, [rcx+10h]
0x18001d054  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001d05b  mov     edx, 12h
0x18001d060  mov     r9d, ebx
0x18001d063  call    WPP_SF_D
0x18001d068  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001d06f  mov     [rbp+var_38], 0
0x18001d073  mov     [rbp+var_30], rax
0x18001d077  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001d07e  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d085  mov     [rbp+var_28], 0
0x18001d08d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d091  mov     [rbp+pExceptionObject], rax
0x18001d095  mov     [rbp+var_20], 0
0x18001d09d  mov     [rbp+var_18], ebx
0x18001d0a0  mov     [rbp+var_14], 0FFFFFFFFh
0x18001d0a7  mov     [rbp+var_10], 0C1h
0x18001d0ae  call    _CxxThrowException_0
0x18001d0b4  mov     edx, [rbp+arg_10]
0x18001d0b7  mov     rcx, rdi
0x18001d0ba  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001d0bf  lea     r11, [rsp+70h+var_s0]
0x18001d0c4  mov     rbx, [r11+20h]
0x18001d0c8  mov     rsi, [r11+28h]
0x18001d0cc  mov     rsp, r11
0x18001d0cf  pop     r14
0x18001d0d1  pop     rdi
0x18001d0d2  pop     rbp
0x18001d0d3  retn
```
