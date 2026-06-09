# CWinSATTaskMangerTask::NeedToRunWinSAT(bool &)

- ea: `0x180020830`
- end: `0x180020993`
- name: `?NeedToRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEA_N@Z`
- size: `355`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020dcc`

## callees

- `0x180004114`
- `0x18000e6ac`
- `0x18000f8a4`
- `0x180020830`
- `0x18002dec0`
- `0x180031010`

## string_xrefs

- `0x1800208b1`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020937`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020954`: `base\winsat\api-dll\winsattaskmangertask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinSATTaskMangerTask::NeedToRunWinSAT(
        CWinSATTaskMangerTask *this,
        bool *a2,
        struct IXMLDOMDocument2 **a3)
{
  int State; // ebx
  void (__fastcall *v6)(__int64 *, __int64, _QWORD); // rax
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v7; // ebx
  __int32 v8; // ebx
  __int32 v9; // ebx
  __int32 v10; // ebx
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v12; // [rsp+20h] [rbp-1C8h] BYREF
  __int64 v13; // [rsp+28h] [rbp-1C0h]
  char v14[8]; // [rsp+30h] [rbp-1B8h] BYREF
  __int64 v15; // [rsp+38h] [rbp-1B0h]
  __int128 v16; // [rsp+40h] [rbp-1A8h]
  __int64 v17; // [rsp+68h] [rbp-180h]
  __int128 v18; // [rsp+70h] [rbp-178h]

  v13 = -2;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v12 = WINSAT_ASSESSMENT_STATE_MIN;
  State = DataStoreReader::LoadMostRecentResultsAndGetState((struct WinSATData *)v14, &v12, a3);
  if ( State >= 0 )
  {
    *a2 = 1;
    v6 = (void (__fastcall *)(__int64 *, __int64, _QWORD))*((_QWORD *)this + 17);
    v7 = v12;
    if ( v6 )
      v6(qword_1800487B0, 10266, (unsigned int)v12);
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            if ( v10 == 1 )
              Log_Text_F((__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp", 134, "assessment state is invalid");
          }
          else
          {
            Log_Text_F(
              (__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp",
              131,
              "assessment state is not avaialable");
          }
        }
        else
        {
          Log_Text_F(
            (__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp",
            128,
            "assessment state is incoherent with the hardware");
        }
      }
      else
      {
        Log_Text_F(
          (__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp",
          138,
          "assessment state is valid - no need to run winsat");
        *a2 = 0;
      }
    }
    else
    {
      Log_Text_F((__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp", 125, "assessment state is unknown");
    }
    State = 0;
  }
  else
  {
    Log_Text_F((__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp", 110, "failed to obtain winast result status");
  }
  WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo((WinSATCriticalHardwareInfo *)v14);
  return (unsigned int)State;
}

```

## disassembly

```asm
0x180020830  mov     rax, rsp
0x180020833  push    rdi
0x180020834  sub     rsp, 1E0h
0x18002083b  mov     [rsp+1E8h+var_1C0], 0FFFFFFFFFFFFFFFEh
0x180020844  mov     [rax+18h], rbx
0x180020848  mov     [rax+20h], rsi
0x18002084c  mov     rax, cs:__security_cookie
0x180020853  xor     rax, rsp
0x180020856  mov     [rsp+1E8h+var_18], rax
0x18002085e  mov     rdi, rdx
0x180020861  mov     rsi, rcx
0x180020864  mov     [rsp+1E8h+var_1B0], 0
0x18002086d  xorps   xmm0, xmm0
0x180020870  movdqa  [rsp+1E8h+var_1A8], xmm0
0x180020876  mov     [rsp+1E8h+var_180], 0
0x18002087f  xorps   xmm1, xmm1
0x180020882  movdqa  [rsp+1E8h+var_178], xmm1
0x180020888  mov     [rsp+1E8h+var_1C8], 0
0x180020890  lea     rdx, [rsp+1E8h+var_1C8]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *
0x180020895  lea     rcx, [rsp+1E8h+var_1B8]; struct WinSATData *
0x18002089a  call    ?LoadMostRecentResultsAndGetState@DataStoreReader@@SAJAEAUWinSATData@@AEAW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@_N@Z; DataStoreReader::LoadMostRecentResultsAndGetState(WinSATData &,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 &,bool)
0x18002089f  mov     ebx, eax
0x1800208a1  test    eax, eax
0x1800208a3  jns     short loc_1800208C2
0x1800208a5  lea     r8, aFailedToObtain; "failed to obtain winast result status"
0x1800208ac  mov     edx, 6Eh ; 'n'
0x1800208b1  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800208b8  call    Log_Text_F
0x1800208bd  jmp     loc_180020962
0x1800208c2  mov     byte ptr [rdi], 1
0x1800208c5  mov     rax, [rsi+88h]
0x1800208cc  mov     ebx, [rsp+1E8h+var_1C8]
0x1800208d0  test    rax, rax
0x1800208d3  jz      short loc_1800208E9
0x1800208d5  mov     r8d, ebx
0x1800208d8  mov     edx, 281Ah
0x1800208dd  lea     rcx, qword_1800487B0
0x1800208e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208e9  test    ebx, ebx
0x1800208eb  jz      short loc_180020948
0x1800208ed  sub     ebx, 1
0x1800208f0  jz      short loc_18002092B
0x1800208f2  sub     ebx, 1
0x1800208f5  jz      short loc_18002091D
0x1800208f7  sub     ebx, 1
0x1800208fa  jz      short loc_18002090F
0x1800208fc  cmp     ebx, 1
0x1800208ff  jnz     short loc_180020960
0x180020901  lea     r8, aAssessmentStat; "assessment state is invalid"
0x180020908  mov     edx, 86h
0x18002090d  jmp     short loc_180020954
0x18002090f  lea     r8, aAssessmentStat_1; "assessment state is not avaialable"
0x180020916  mov     edx, 83h
0x18002091b  jmp     short loc_180020954
0x18002091d  lea     r8, aAssessmentStat_2; "assessment state is incoherent with the"...
0x180020924  mov     edx, 80h
0x180020929  jmp     short loc_180020954
0x18002092b  lea     r8, aAssessmentStat_0; "assessment state is valid - no need to "...
0x180020932  mov     edx, 8Ah
0x180020937  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002093e  call    Log_Text_F
0x180020943  mov     byte ptr [rdi], 0
0x180020946  jmp     short loc_180020960
0x180020948  lea     r8, aAssessmentStat_3; "assessment state is unknown"
0x18002094f  mov     edx, 7Dh ; '}'
0x180020954  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002095b  call    Log_Text_F
0x180020960  xor     ebx, ebx
0x180020962  lea     rcx, [rsp+1E8h+var_1B8]; this
0x180020967  call    ??1WinSATCriticalHardwareInfo@@QEAA@XZ; WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo(void)
0x18002096c  mov     eax, ebx
0x18002096e  mov     rcx, [rsp+1E8h+var_18]
0x180020976  xor     rcx, rsp; StackCookie
0x180020979  call    __security_check_cookie
0x18002097e  lea     r11, [rsp+1E8h+var_8]
0x180020986  mov     rbx, [r11+20h]
0x18002098a  mov     rsi, [r11+28h]
0x18002098e  mov     rsp, r11
0x180020991  pop     rdi
0x180020992  retn
```
