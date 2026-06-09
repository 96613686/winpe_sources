# CNTService::ServiceMain(ulong,ushort * *)

- ea: `0x1400493a0`
- end: `0x140049639`
- name: `?ServiceMain@CNTService@@SAXKPEAPEAG@Z`
- size: `665`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x140006d70`
- `0x14000b3b0`
- `0x14000c920`
- `0x140018df0`
- `0x14003f17c`
- `0x140047798`
- `0x1400484e0`
- `0x140048530`
- `0x1400488f4`
- `0x1400493a0`
- `0x140049640`
- `0x140049aa8`
- `0x14004a744`
- `0x140095368`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x14004943e`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x14004943e`
- `KERNEL32!GetLastError` at `0x140049458`
- `KERNEL32!GetLastError` at `0x14004953c`
- `KERNEL32!GetLastError` at `0x140049458`
- `KERNEL32!GetLastError` at `0x14004953c`
- `KERNEL32!SetEvent` at `0x1400495f0`
- `KERNEL32!SetEvent` at `0x1400495f0`
- `KERNEL32!RaiseException` at `0x140049632`
- `KERNEL32!RaiseException` at `0x140049632`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CNTService::ServiceMain(unsigned int a1, char **a2, __int64 a3)
{
  __int64 v4; // rcx
  int Key; // eax
  __int64 v6; // rbx
  SERVICE_STATUS_HANDLE v7; // rax
  DWORD LastError; // eax
  DWORD v9; // edi
  unsigned __int16 *v10; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)&v10,
    *a2);
  Key = ATL::CSimpleMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CNTService *,ATL::CSimpleMapEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CNTService *>>::FindKey(
          v4,
          &v10);
  if ( Key == -1 )
  {
    v6 = 0;
  }
  else
  {
    if ( Key < 0 || Key >= dword_1400BFF80 )
    {
      RaiseException(0xC000008C, 1u, 0, 0);
      JUMPOUT(0x140049638LL);
    }
    v6 = *((_QWORD *)qword_1400BFF78 + Key);
  }
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v10);
  *(_DWORD *)(v6 + 12) = 2;
  v7 = RegisterServiceCtrlHandlerExW(*(LPCWSTR *)(v6 + 40), CNTService::HandlerEx, (LPVOID)v6);
  *(_QWORD *)(v6 + 64) = v7;
  if ( v7 )
  {
    if ( !CNTService::Initialize((CNTService *)v6) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
      }
      if ( (unsigned int)IsHMEAllowedByGroupPolicy() )
      {
        *(_DWORD *)(v6 + 28) = 0;
        *(_DWORD *)(v6 + 32) = 500;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
        *(_DWORD *)(v6 + 20) = GetLastError();
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
        }
        CNTService::LogEvent(
          (CNTService *)v6,
          &WMC_E_SERVICE_GROUP_POLICY_PREVENTSTARTUP,
          *(const unsigned __int16 **)(v6 + 40),
          0,
          0);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
      }
      CNTService::Uninitialize((CNTService *)v6);
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, LastError);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v10);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
      &v10,
      L"%lu",
      v9);
    CNTService::LogEvent(
      (CNTService *)v6,
      &WMC_E_SERVICE_CTRL_HANDLER_FAILED,
      *(const unsigned __int16 **)(v6 + 40),
      v10,
      0);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v10);
  }
  CNTService::SetStatus((CNTService *)v6, 1u);
  CNTService::LogEvent((CNTService *)v6, &WMC_I_SERVICE_STOPPED, *(const unsigned __int16 **)(v6 + 40), 0, 0);
  SetEvent(*(HANDLE *)(v6 + 80));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
}

```

## disassembly

```asm
0x1400493a0  push    rbx
0x1400493a2  push    rbp
0x1400493a3  push    rdi
0x1400493a4  push    r14
0x1400493a6  sub     rsp, 38h
0x1400493aa  mov     rbx, rdx
0x1400493ad  mov     r9d, ecx
0x1400493b0  lea     rbp, WPP_GLOBAL_Control
0x1400493b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400493be  cmp     rcx, rbp
0x1400493c1  jz      short loc_1400493DD
0x1400493c3  test    byte ptr [rcx+1Ch], 1
0x1400493c7  jz      short loc_1400493DD
0x1400493c9  cmp     byte ptr [rcx+19h], 5
0x1400493cd  jb      short loc_1400493DD
0x1400493cf  mov     [rsp+58h+var_38], rdx
0x1400493d4  mov     rcx, [rcx+10h]
0x1400493d8  call    WPP_SF_Lq
0x1400493dd  mov     rdx, [rbx]
0x1400493e0  lea     rcx, [rsp+58h+arg_8]
0x1400493e5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400493ea  lea     rdx, [rsp+58h+arg_8]
0x1400493ef  call    ?FindKey@?$CSimpleMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAVCNTService@@V?$CSimpleMapEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAVCNTService@@@2@@ATL@@QEBAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; ATL::CSimpleMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CNTService *,ATL::CSimpleMapEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CNTService *>>::FindKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x1400493f4  cmp     eax, 0FFFFFFFFh
0x1400493f7  jnz     short loc_1400493FD
0x1400493f9  xor     ebx, ebx
0x1400493fb  jmp     short loc_14004941F
0x1400493fd  test    eax, eax
0x1400493ff  js      loc_140049623
0x140049405  cmp     eax, cs:dword_1400BFF80
0x14004940b  jge     loc_140049623
0x140049411  movsxd  rcx, eax
0x140049414  mov     rax, cs:qword_1400BFF78
0x14004941b  mov     rbx, [rax+rcx*8]
0x14004941f  lea     rcx, [rsp+58h+arg_8]
0x140049424  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140049429  mov     dword ptr [rbx+0Ch], 2
0x140049430  mov     r8, rbx; lpContext
0x140049433  lea     rdx, ?HandlerEx@CNTService@@SAKKKPEAX0@Z; lpHandlerProc
0x14004943a  mov     rcx, [rbx+28h]; lpServiceName
0x14004943e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x140049444  mov     [rbx+40h], rax
0x140049448  lea     r14, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x14004944f  test    rax, rax
0x140049452  jnz     loc_1400494DC
0x140049458  call    cs:__imp_GetLastError
0x14004945e  mov     edi, eax
0x140049460  mov     rcx, cs:WPP_GLOBAL_Control
0x140049467  cmp     rcx, rbp
0x14004946a  jz      short loc_14004948C
0x14004946c  test    byte ptr [rcx+1Ch], 2
0x140049470  jz      short loc_14004948C
0x140049472  cmp     byte ptr [rcx+19h], 2
0x140049476  jb      short loc_14004948C
0x140049478  mov     edx, 51h ; 'Q'
0x14004947d  mov     r9d, eax
0x140049480  mov     r8, r14
0x140049483  mov     rcx, [rcx+10h]
0x140049487  call    WPP_SF_d
0x14004948c  lea     rcx, [rsp+58h+arg_8]
0x140049491  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140049496  nop
0x140049497  mov     r8d, edi
0x14004949a  lea     rdx, aLu; "%lu"
0x1400494a1  lea     rcx, [rsp+58h+arg_8]
0x1400494a6  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x1400494ab  mov     [rsp+58h+var_38], 0; unsigned __int16 *
0x1400494b4  mov     r9, [rsp+58h+arg_8]; unsigned __int16 *
0x1400494b9  mov     r8, [rbx+28h]; unsigned __int16 *
0x1400494bd  lea     rdx, WMC_E_SERVICE_CTRL_HANDLER_FAILED; struct _EVENT_DESCRIPTOR *
0x1400494c4  mov     rcx, rbx; this
0x1400494c7  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x1400494cc  nop
0x1400494cd  lea     rcx, [rsp+58h+arg_8]
0x1400494d2  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400494d7  jmp     loc_1400495C0
0x1400494dc  mov     rcx, rbx; this
0x1400494df  call    ?Initialize@CNTService@@QEAAKXZ; CNTService::Initialize(void)
0x1400494e4  test    eax, eax
0x1400494e6  jnz     loc_1400495C0
0x1400494ec  mov     dil, 4
0x1400494ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400494f6  cmp     rcx, rbp
0x1400494f9  jz      short loc_140049516
0x1400494fb  test    byte ptr [rcx+1Ch], 2
0x1400494ff  jz      short loc_140049516
0x140049501  cmp     [rcx+19h], dil
0x140049505  jb      short loc_140049516
0x140049507  lea     edx, [rax+52h]
0x14004950a  mov     r8, r14
0x14004950d  mov     rcx, [rcx+10h]
0x140049511  call    WPP_SF_
0x140049516  call    ?IsHMEAllowedByGroupPolicy@@YAHXZ; IsHMEAllowedByGroupPolicy(void)
0x14004951b  test    eax, eax
0x14004951d  jz      short loc_140049547
0x14004951f  mov     dword ptr [rbx+1Ch], 0
0x140049526  mov     dword ptr [rbx+20h], 1F4h
0x14004952d  mov     rax, [rbx]
0x140049530  mov     rcx, rbx
0x140049533  mov     rax, [rax+18h]
0x140049537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004953c  call    cs:__imp_GetLastError
0x140049542  mov     [rbx+14h], eax
0x140049545  jmp     short loc_14004958F
0x140049547  mov     rcx, cs:WPP_GLOBAL_Control
0x14004954e  cmp     rcx, rbp
0x140049551  jz      short loc_140049570
0x140049553  test    byte ptr [rcx+1Ch], 2
0x140049557  jz      short loc_140049570
0x140049559  cmp     [rcx+19h], dil
0x14004955d  jb      short loc_140049570
0x14004955f  mov     edx, 53h ; 'S'
0x140049564  mov     r8, r14
0x140049567  mov     rcx, [rcx+10h]
0x14004956b  call    WPP_SF_
0x140049570  mov     [rsp+58h+var_38], 0; unsigned __int16 *
0x140049579  xor     r9d, r9d; unsigned __int16 *
0x14004957c  mov     r8, [rbx+28h]; unsigned __int16 *
0x140049580  lea     rdx, WMC_E_SERVICE_GROUP_POLICY_PREVENTSTARTUP; struct _EVENT_DESCRIPTOR *
0x140049587  mov     rcx, rbx; this
0x14004958a  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x14004958f  mov     rcx, cs:WPP_GLOBAL_Control
0x140049596  cmp     rcx, rbp
0x140049599  jz      short loc_1400495B8
0x14004959b  test    byte ptr [rcx+1Ch], 2
0x14004959f  jz      short loc_1400495B8
0x1400495a1  cmp     [rcx+19h], dil
0x1400495a5  jb      short loc_1400495B8
0x1400495a7  mov     edx, 54h ; 'T'
0x1400495ac  mov     r8, r14
0x1400495af  mov     rcx, [rcx+10h]
0x1400495b3  call    WPP_SF_
0x1400495b8  mov     rcx, rbx; this
0x1400495bb  call    ?Uninitialize@CNTService@@QEAAKXZ; CNTService::Uninitialize(void)
0x1400495c0  mov     edx, 1; unsigned int
0x1400495c5  mov     rcx, rbx; this
0x1400495c8  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x1400495cd  mov     [rsp+58h+var_38], 0; unsigned __int16 *
0x1400495d6  xor     r9d, r9d; unsigned __int16 *
0x1400495d9  mov     r8, [rbx+28h]; unsigned __int16 *
0x1400495dd  lea     rdx, WMC_I_SERVICE_STOPPED; struct _EVENT_DESCRIPTOR *
0x1400495e4  mov     rcx, rbx; this
0x1400495e7  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x1400495ec  mov     rcx, [rbx+50h]; hEvent
0x1400495f0  call    cs:__imp_SetEvent
0x1400495f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400495fd  cmp     rcx, rbp
0x140049600  jz      short loc_140049619
0x140049602  test    byte ptr [rcx+1Ch], 1
0x140049606  jz      short loc_140049619
0x140049608  mov     edx, 55h ; 'U'
0x14004960d  mov     r8, r14
0x140049610  mov     rcx, [rcx+10h]
0x140049614  call    WPP_SF_
0x140049619  add     rsp, 38h
0x14004961d  pop     r14
0x14004961f  pop     rdi
0x140049620  pop     rbp
0x140049621  pop     rbx
0x140049622  retn
0x140049623  xor     r9d, r9d; lpArguments
0x140049626  xor     r8d, r8d; nNumberOfArguments
0x140049629  lea     edx, [r9+1]; dwExceptionFlags
0x14004962d  mov     ecx, 0C000008Ch; dwExceptionCode
0x140049632  call    cs:__imp_RaiseException
```
