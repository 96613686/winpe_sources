# GetEvtChannelProperty(void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,std::vector<uchar,std::allocator<uchar>> &,_EVT_VARIANT * &)

- ea: `0x18000632c`
- end: `0x1800064df`
- name: `?GetEvtChannelProperty@@YAXPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(EVT_HANDLE ChannelConfig)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000908c`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x18000632c`
- `0x18000a2bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000638b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000646b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000638b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000646b`
- `wevtapi!EvtGetChannelConfigProperty` at `0x180006381`
- `wevtapi!EvtGetChannelConfigProperty` at `0x1800063d5`
- `wevtapi!EvtGetChannelConfigProperty` at `0x180006381`
- `wevtapi!EvtGetChannelConfigProperty` at `0x1800063d5`

## pseudocode

```c
struct _EVT_VARIANT *__fastcall GetEvtChannelProperty(EVT_HANDLE ChannelConfig, DWORD a2, __int64 a3, _QWORD *a4)
{
  struct _EVT_VARIANT *PropertyValueBuffer; // rax
  struct _EVT_VARIANT *v8; // rax
  struct _EVT_VARIANT *result; // rax
  DWORD v10; // ebx
  DWORD LastError; // ebx
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-48h] BYREF
  DWORD PropertyValueBufferUsed; // [rsp+88h] [rbp+10h] BYREF

  PropertyValueBufferUsed = a2;
  std::vector<unsigned char>::resize(a3, 16);
  PropertyValueBuffer = *(struct _EVT_VARIANT **)a3;
  PropertyValueBufferUsed = *(_DWORD *)(a3 + 8) - *(_QWORD *)a3;
  if ( !EvtGetChannelConfigProperty(
          ChannelConfig,
          EvtChannelConfigEnabled,
          0,
          PropertyValueBufferUsed,
          PropertyValueBuffer,
          &PropertyValueBufferUsed) )
  {
    if ( GetLastError() != 122 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, LastError);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        LastError,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        1040);
      throw (wmi::GenericException *)pExceptionObject;
    }
    std::vector<unsigned char>::resize(a3, PropertyValueBufferUsed);
    v8 = *(struct _EVT_VARIANT **)a3;
    PropertyValueBufferUsed = *(_DWORD *)(a3 + 8) - *(_QWORD *)a3;
    if ( !EvtGetChannelConfigProperty(
            ChannelConfig,
            EvtChannelConfigEnabled,
            0,
            PropertyValueBufferUsed,
            v8,
            &PropertyValueBufferUsed) )
    {
      v10 = GetLastError();
      if ( !v10 )
        v10 = 1287;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, v10);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        v10,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        1046);
      throw (wmi::GenericException *)pExceptionObject;
    }
  }
  result = *(struct _EVT_VARIANT **)a3;
  *a4 = *(_QWORD *)a3;
  return result;
}

```

## disassembly

```asm
0x18000632c  mov     [rsp+arg_0], rbx
0x180006331  mov     [rsp+arg_10], rsi
0x180006336  mov     [rsp+arg_8], edx
0x18000633a  push    rdi
0x18000633b  sub     rsp, 70h
0x18000633f  mov     rsi, rcx
0x180006342  mov     edx, 10h
0x180006347  mov     rcx, r8
0x18000634a  mov     rdi, r9
0x18000634d  mov     rbx, r8
0x180006350  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180006355  mov     rax, [rbx]
0x180006358  lea     rcx, [rsp+78h+arg_8]
0x180006360  mov     r9d, [rbx+8]
0x180006364  xor     r8d, r8d; Flags
0x180006367  mov     [rsp+78h+PropertyValueBufferUsed], rcx; PropertyValueBufferUsed
0x18000636c  sub     r9d, eax; PropertyValueBufferSize
0x18000636f  mov     rcx, rsi; ChannelConfig
0x180006372  mov     [rsp+78h+arg_8], r9d
0x18000637a  xor     edx, edx; PropertyId
0x18000637c  mov     [rsp+78h+PropertyValueBuffer], rax; PropertyValueBuffer
0x180006381  call    cs:__imp_EvtGetChannelConfigProperty
0x180006387  test    eax, eax
0x180006389  jnz     short loc_1800063DF
0x18000638b  call    cs:__imp_GetLastError
0x180006391  cmp     eax, 7Ah ; 'z'
0x180006394  jnz     loc_18000646B
0x18000639a  mov     edx, [rsp+78h+arg_8]
0x1800063a1  mov     rcx, rbx
0x1800063a4  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800063a9  mov     rax, [rbx]
0x1800063ac  lea     rcx, [rsp+78h+arg_8]
0x1800063b4  mov     r9d, [rbx+8]
0x1800063b8  xor     r8d, r8d; Flags
0x1800063bb  mov     [rsp+78h+PropertyValueBufferUsed], rcx; PropertyValueBufferUsed
0x1800063c0  sub     r9d, eax; PropertyValueBufferSize
0x1800063c3  mov     rcx, rsi; ChannelConfig
0x1800063c6  mov     [rsp+78h+arg_8], r9d
0x1800063ce  xor     edx, edx; PropertyId
0x1800063d0  mov     [rsp+78h+PropertyValueBuffer], rax; PropertyValueBuffer
0x1800063d5  call    cs:__imp_EvtGetChannelConfigProperty
0x1800063db  test    eax, eax
0x1800063dd  jz      short loc_1800063F7
0x1800063df  mov     rax, [rbx]
0x1800063e2  lea     r11, [rsp+78h+var_8]
0x1800063e7  mov     rbx, [r11+10h]
0x1800063eb  mov     rsi, [r11+20h]
0x1800063ef  mov     [rdi], rax
0x1800063f2  mov     rsp, r11
0x1800063f5  pop     rdi
0x1800063f6  retn
0x1800063f7  call    cs:__imp_GetLastError
0x1800063fd  mov     ebx, eax
0x1800063ff  mov     eax, 507h
0x180006404  test    ebx, ebx
0x180006406  cmovz   ebx, eax
0x180006409  mov     rcx, cs:WPP_GLOBAL_Control
0x180006410  lea     rax, WPP_GLOBAL_Control
0x180006417  cmp     rcx, rax
0x18000641a  jz      short loc_180006440
0x18000641c  test    byte ptr [rcx+1Ch], 1
0x180006420  jz      short loc_180006440
0x180006422  cmp     byte ptr [rcx+19h], 2
0x180006426  jb      short loc_180006440
0x180006428  mov     rcx, [rcx+10h]
0x18000642c  lea     r8, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids
0x180006433  mov     edx, 4Dh ; 'M'
0x180006438  mov     r9d, ebx
0x18000643b  call    WPP_SF_D
0x180006440  mov     r9d, 416h; int
0x180006446  lea     r8, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18000644d  mov     edx, ebx; unsigned int
0x18000644f  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180006454  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x180006459  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180006460  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180006465  call    _CxxThrowException_0
0x18000646b  call    cs:__imp_GetLastError
0x180006471  mov     ebx, eax
0x180006473  mov     eax, 507h
0x180006478  test    ebx, ebx
0x18000647a  cmovz   ebx, eax
0x18000647d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006484  lea     rax, WPP_GLOBAL_Control
0x18000648b  cmp     rcx, rax
0x18000648e  jz      short loc_1800064B4
0x180006490  test    byte ptr [rcx+1Ch], 1
0x180006494  jz      short loc_1800064B4
0x180006496  cmp     byte ptr [rcx+19h], 2
0x18000649a  jb      short loc_1800064B4
0x18000649c  mov     rcx, [rcx+10h]
0x1800064a0  lea     r8, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids
0x1800064a7  mov     edx, 4Ch ; 'L'
0x1800064ac  mov     r9d, ebx
0x1800064af  call    WPP_SF_D
0x1800064b4  mov     r9d, 410h; int
0x1800064ba  lea     r8, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x1800064c1  mov     edx, ebx; unsigned int
0x1800064c3  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800064c8  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x1800064cd  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800064d4  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800064d9  call    _CxxThrowException_0
```
