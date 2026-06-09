# ExecuteSecurityActionHandlerById(HWND__ *,ushort const *,SecurityLogicState *)

- ea: `0x180006ad0`
- end: `0x180006fe3`
- name: `?ExecuteSecurityActionHandlerById@@YA_NPEAUHWND__@@PEBGPEAVSecurityLogicState@@@Z`
- size: `1299`
- prototype: `bool(HWND, const unsigned __int16 *, struct SecurityLogicState *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800023f4`
- `0x180002708`
- `0x180002778`
- `0x18000485c`
- `0x180006520`
- `0x180006ad0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006ea4`
- `msvcrt!_wcsicmp` at `0x180006ec0`
- `msvcrt!_wcsicmp` at `0x180006edc`
- `msvcrt!_wcsicmp` at `0x180006ef8`
- `msvcrt!_wcsicmp` at `0x180006f14`
- `msvcrt!_wcsicmp` at `0x180006f30`
- `msvcrt!_wcsicmp` at `0x180006f4c`
- `msvcrt!_wcsicmp` at `0x180006f67`
- `msvcrt!_wcsicmp` at `0x180006f82`
- `msvcrt!_wcsicmp` at `0x180006f9d`
- `msvcrt!_wcsicmp` at `0x180006fbb`
- `msvcrt!_wcsicmp` at `0x180006ea4`
- `msvcrt!_wcsicmp` at `0x180006ec0`
- `msvcrt!_wcsicmp` at `0x180006edc`
- `msvcrt!_wcsicmp` at `0x180006ef8`
- `msvcrt!_wcsicmp` at `0x180006f14`
- `msvcrt!_wcsicmp` at `0x180006f30`
- `msvcrt!_wcsicmp` at `0x180006f4c`
- `msvcrt!_wcsicmp` at `0x180006f67`
- `msvcrt!_wcsicmp` at `0x180006f82`
- `msvcrt!_wcsicmp` at `0x180006f9d`
- `msvcrt!_wcsicmp` at `0x180006fbb`

## string_xrefs

- `0x180006c06`: `idShowWindowsSecurityAv`
- `0x180006c53`: `idShowWindowsSecurityFw`
- `0x180006ca0`: `idShowWindowsSecurityProviders`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
char __fastcall ExecuteSecurityActionHandlerById(HWND a1, const unsigned __int16 *a2, struct SecurityLogicState *a3)
{
  __int64 v6; // rbx
  int v7; // ebx

  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180014BE8 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014BE8);
    if ( dword_180014BE8 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &String1,
        L"idPurchaseAntivirus");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idPurchaseAntivirus__);
      Init_thread_footer(&dword_180014BE8);
    }
  }
  if ( dword_180014BF8 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014BF8);
    if ( dword_180014BF8 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014C00,
        L"idInternetSettingsManualFix");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idInternetSettingsManualFix__);
      Init_thread_footer(&dword_180014BF8);
    }
  }
  if ( dword_180014C08 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014C08);
    if ( dword_180014C08 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014C10,
        L"idWindowsFirewallControlPanel");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idWindowsFirewallControlPanel__);
      Init_thread_footer(&dword_180014C08);
    }
  }
  if ( dword_180014C18 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014C18);
    if ( dword_180014C18 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014C20,
        L"idShowWindowsSecurityAv");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idShowWindowsSecurityAv__);
      Init_thread_footer(&dword_180014C18);
    }
  }
  if ( dword_180014C28 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014C28);
    if ( dword_180014C28 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014C30,
        L"idShowWindowsSecurityFw");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idShowWindowsSecurityFw__);
      Init_thread_footer(&dword_180014C28);
    }
  }
  if ( dword_180014C38 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014C38);
    if ( dword_180014C38 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014C40,
        L"idShowWindowsSecurityProviders");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idShowWindowsSecurityProviders__);
      Init_thread_footer(&dword_180014C38);
    }
  }
  if ( dword_180014C48 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014C48);
    if ( dword_180014C48 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014C50,
        L"idcldAsListAndSelfMonitor");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idcldAsListAndSelfMonitor__);
      Init_thread_footer(&dword_180014C48);
    }
  }
  if ( dword_180014C58 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014C58);
    if ( dword_180014C58 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014C60,
        L"idcldAvPurchaseAndSelfMonitor");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idcldAvPurchaseAndSelfMonitor__);
      Init_thread_footer(&dword_180014C58);
    }
  }
  if ( dword_180014C68 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014C68);
    if ( dword_180014C68 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014C70,
        L"idcldAvPurchaseViewOthersAndSelfMonitor");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idcldAvPurchaseViewOthersAndSelfMonitor__);
      Init_thread_footer(&dword_180014C68);
    }
  }
  if ( dword_180014C78 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014C78);
    if ( dword_180014C78 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014C80,
        L"idcldAvListAndSelfMonitor");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idcldAvListAndSelfMonitor__);
      Init_thread_footer(&dword_180014C78);
    }
  }
  if ( dword_180014C88 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014C88);
    if ( dword_180014C88 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014C90,
        L"idAboutWindowsDefender");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idAboutWindowsDefender__);
      Init_thread_footer(&dword_180014C88);
    }
  }
  if ( dword_180014C98 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_180014C98);
    if ( dword_180014C98 == -1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &qword_180014CA0,
        L"idAboutWindowsFirewall");
      atexit(ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idAboutWindowsFirewall__);
      Init_thread_footer(&dword_180014C98);
    }
  }
  if ( _wcsicmp(String1, a2) )
  {
    if ( _wcsicmp(qword_180014C00, a2) )
    {
      if ( _wcsicmp(qword_180014C10, a2) )
      {
        if ( _wcsicmp(qword_180014C20, a2) )
        {
          if ( _wcsicmp(qword_180014C30, a2) )
          {
            if ( _wcsicmp(qword_180014C40, a2) )
            {
              if ( _wcsicmp(qword_180014C50, a2) )
              {
                if ( _wcsicmp(qword_180014C70, a2) )
                {
                  if ( _wcsicmp(qword_180014C80, a2) )
                  {
                    if ( _wcsicmp(qword_180014C90, a2) )
                    {
                      v7 = 100;
                      if ( !_wcsicmp(qword_180014CA0, a2) )
                        v7 = 123;
                    }
                    else
                    {
                      v7 = 124;
                    }
                  }
                  else
                  {
                    v7 = 130;
                  }
                }
                else
                {
                  v7 = 140;
                }
              }
              else
              {
                v7 = 137;
              }
            }
            else
            {
              v7 = 108;
            }
          }
          else
          {
            v7 = 107;
          }
        }
        else
        {
          v7 = 106;
        }
      }
      else
      {
        v7 = 120;
      }
    }
    else
    {
      v7 = 116;
    }
  }
  else
  {
    v7 = 103;
  }
  return ExecuteSecurityActionHandler(a1, v7, a3, 0);
}

```

## disassembly

```asm
0x180006ad0  push    rbx
0x180006ad2  push    rbp
0x180006ad3  push    rsi
0x180006ad4  push    rdi
0x180006ad5  push    r14
0x180006ad7  sub     rsp, 20h
0x180006adb  mov     rsi, r8
0x180006ade  mov     rdi, rdx
0x180006ae1  mov     rbp, rcx
0x180006ae4  mov     r9d, cs:_tls_index
0x180006aeb  mov     rax, gs:58h
0x180006af4  mov     r14d, 4
0x180006afa  mov     rbx, [rax+r9*8]
0x180006afe  mov     eax, [rbx+r14]
0x180006b02  cmp     cs:dword_180014BE8, eax
0x180006b08  jle     short loc_180006B4B
0x180006b0a  lea     rcx, dword_180014BE8
0x180006b11  call    _Init_thread_header
0x180006b16  cmp     cs:dword_180014BE8, 0FFFFFFFFh
0x180006b1d  jnz     short loc_180006B4B
0x180006b1f  lea     rdx, aIdpurchaseanti; "idPurchaseAntivirus"
0x180006b26  lea     rcx, String1
0x180006b2d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006b32  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idPurchaseAntivirus__; void (__cdecl *)()
0x180006b39  call    atexit
0x180006b3e  nop
0x180006b3f  lea     rcx, dword_180014BE8
0x180006b46  call    _Init_thread_footer
0x180006b4b  mov     eax, [rbx+r14]
0x180006b4f  cmp     cs:dword_180014BF8, eax
0x180006b55  jle     short loc_180006B98
0x180006b57  lea     rcx, dword_180014BF8
0x180006b5e  call    _Init_thread_header
0x180006b63  cmp     cs:dword_180014BF8, 0FFFFFFFFh
0x180006b6a  jnz     short loc_180006B98
0x180006b6c  lea     rdx, aIdinternetsett; "idInternetSettingsManualFix"
0x180006b73  lea     rcx, qword_180014C00
0x180006b7a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006b7f  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idInternetSettingsManualFix__; void (__cdecl *)()
0x180006b86  call    atexit
0x180006b8b  nop
0x180006b8c  lea     rcx, dword_180014BF8
0x180006b93  call    _Init_thread_footer
0x180006b98  mov     eax, [rbx+r14]
0x180006b9c  cmp     cs:dword_180014C08, eax
0x180006ba2  jle     short loc_180006BE5
0x180006ba4  lea     rcx, dword_180014C08
0x180006bab  call    _Init_thread_header
0x180006bb0  cmp     cs:dword_180014C08, 0FFFFFFFFh
0x180006bb7  jnz     short loc_180006BE5
0x180006bb9  lea     rdx, aIdwindowsfirew; "idWindowsFirewallControlPanel"
0x180006bc0  lea     rcx, qword_180014C10
0x180006bc7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006bcc  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idWindowsFirewallControlPanel__; void (__cdecl *)()
0x180006bd3  call    atexit
0x180006bd8  nop
0x180006bd9  lea     rcx, dword_180014C08
0x180006be0  call    _Init_thread_footer
0x180006be5  mov     eax, [rbx+r14]
0x180006be9  cmp     cs:dword_180014C18, eax
0x180006bef  jle     short loc_180006C32
0x180006bf1  lea     rcx, dword_180014C18
0x180006bf8  call    _Init_thread_header
0x180006bfd  cmp     cs:dword_180014C18, 0FFFFFFFFh
0x180006c04  jnz     short loc_180006C32
0x180006c06  lea     rdx, aIdshowwindowss; "idShowWindowsSecurityAv"
0x180006c0d  lea     rcx, qword_180014C20
0x180006c14  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006c19  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idShowWindowsSecurityAv__; void (__cdecl *)()
0x180006c20  call    atexit
0x180006c25  nop
0x180006c26  lea     rcx, dword_180014C18
0x180006c2d  call    _Init_thread_footer
0x180006c32  mov     eax, [rbx+r14]
0x180006c36  cmp     cs:dword_180014C28, eax
0x180006c3c  jle     short loc_180006C7F
0x180006c3e  lea     rcx, dword_180014C28
0x180006c45  call    _Init_thread_header
0x180006c4a  cmp     cs:dword_180014C28, 0FFFFFFFFh
0x180006c51  jnz     short loc_180006C7F
0x180006c53  lea     rdx, aIdshowwindowss_0; "idShowWindowsSecurityFw"
0x180006c5a  lea     rcx, qword_180014C30
0x180006c61  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006c66  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idShowWindowsSecurityFw__; void (__cdecl *)()
0x180006c6d  call    atexit
0x180006c72  nop
0x180006c73  lea     rcx, dword_180014C28
0x180006c7a  call    _Init_thread_footer
0x180006c7f  mov     eax, [rbx+r14]
0x180006c83  cmp     cs:dword_180014C38, eax
0x180006c89  jle     short loc_180006CCC
0x180006c8b  lea     rcx, dword_180014C38
0x180006c92  call    _Init_thread_header
0x180006c97  cmp     cs:dword_180014C38, 0FFFFFFFFh
0x180006c9e  jnz     short loc_180006CCC
0x180006ca0  lea     rdx, aIdshowwindowss_1; "idShowWindowsSecurityProviders"
0x180006ca7  lea     rcx, qword_180014C40
0x180006cae  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006cb3  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idShowWindowsSecurityProviders__; void (__cdecl *)()
0x180006cba  call    atexit
0x180006cbf  nop
0x180006cc0  lea     rcx, dword_180014C38
0x180006cc7  call    _Init_thread_footer
0x180006ccc  mov     eax, [rbx+r14]
0x180006cd0  cmp     cs:dword_180014C48, eax
0x180006cd6  jle     short loc_180006D19
0x180006cd8  lea     rcx, dword_180014C48
0x180006cdf  call    _Init_thread_header
0x180006ce4  cmp     cs:dword_180014C48, 0FFFFFFFFh
0x180006ceb  jnz     short loc_180006D19
0x180006ced  lea     rdx, aIdcldaslistand; "idcldAsListAndSelfMonitor"
0x180006cf4  lea     rcx, qword_180014C50
0x180006cfb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006d00  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idcldAsListAndSelfMonitor__; void (__cdecl *)()
0x180006d07  call    atexit
0x180006d0c  nop
0x180006d0d  lea     rcx, dword_180014C48
0x180006d14  call    _Init_thread_footer
0x180006d19  mov     eax, [rbx+r14]
0x180006d1d  cmp     cs:dword_180014C58, eax
0x180006d23  jle     short loc_180006D66
0x180006d25  lea     rcx, dword_180014C58
0x180006d2c  call    _Init_thread_header
0x180006d31  cmp     cs:dword_180014C58, 0FFFFFFFFh
0x180006d38  jnz     short loc_180006D66
0x180006d3a  lea     rdx, aIdcldavpurchas; "idcldAvPurchaseAndSelfMonitor"
0x180006d41  lea     rcx, qword_180014C60
0x180006d48  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006d4d  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idcldAvPurchaseAndSelfMonitor__; void (__cdecl *)()
0x180006d54  call    atexit
0x180006d59  nop
0x180006d5a  lea     rcx, dword_180014C58
0x180006d61  call    _Init_thread_footer
0x180006d66  mov     eax, [rbx+r14]
0x180006d6a  cmp     cs:dword_180014C68, eax
0x180006d70  jle     short loc_180006DB3
0x180006d72  lea     rcx, dword_180014C68
0x180006d79  call    _Init_thread_header
0x180006d7e  cmp     cs:dword_180014C68, 0FFFFFFFFh
0x180006d85  jnz     short loc_180006DB3
0x180006d87  lea     rdx, aIdcldavpurchas_0; "idcldAvPurchaseViewOthersAndSelfMonitor"
0x180006d8e  lea     rcx, qword_180014C70
0x180006d95  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006d9a  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idcldAvPurchaseViewOthersAndSelfMonitor__; void (__cdecl *)()
0x180006da1  call    atexit
0x180006da6  nop
0x180006da7  lea     rcx, dword_180014C68
0x180006dae  call    _Init_thread_footer
0x180006db3  mov     eax, [rbx+r14]
0x180006db7  cmp     cs:dword_180014C78, eax
0x180006dbd  jle     short loc_180006E00
0x180006dbf  lea     rcx, dword_180014C78
0x180006dc6  call    _Init_thread_header
0x180006dcb  cmp     cs:dword_180014C78, 0FFFFFFFFh
0x180006dd2  jnz     short loc_180006E00
0x180006dd4  lea     rdx, aIdcldavlistand; "idcldAvListAndSelfMonitor"
0x180006ddb  lea     rcx, qword_180014C80
0x180006de2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006de7  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idcldAvListAndSelfMonitor__; void (__cdecl *)()
0x180006dee  call    atexit
0x180006df3  nop
0x180006df4  lea     rcx, dword_180014C78
0x180006dfb  call    _Init_thread_footer
0x180006e00  mov     eax, [rbx+r14]
0x180006e04  cmp     cs:dword_180014C88, eax
0x180006e0a  jle     short loc_180006E4D
0x180006e0c  lea     rcx, dword_180014C88
0x180006e13  call    _Init_thread_header
0x180006e18  cmp     cs:dword_180014C88, 0FFFFFFFFh
0x180006e1f  jnz     short loc_180006E4D
0x180006e21  lea     rdx, aIdaboutwindows_0; "idAboutWindowsDefender"
0x180006e28  lea     rcx, qword_180014C90
0x180006e2f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006e34  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idAboutWindowsDefender__; void (__cdecl *)()
0x180006e3b  call    atexit
0x180006e40  nop
0x180006e41  lea     rcx, dword_180014C88
0x180006e48  call    _Init_thread_footer
0x180006e4d  mov     eax, [rbx+r14]
0x180006e51  cmp     cs:dword_180014C98, eax
0x180006e57  jle     short loc_180006E9A
0x180006e59  lea     rcx, dword_180014C98
0x180006e60  call    _Init_thread_header
0x180006e65  cmp     cs:dword_180014C98, 0FFFFFFFFh
0x180006e6c  jnz     short loc_180006E9A
0x180006e6e  lea     rdx, aIdaboutwindows; "idAboutWindowsFirewall"
0x180006e75  lea     rcx, qword_180014CA0
0x180006e7c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006e81  lea     rcx, _ExecuteSecurityActionHandlerById____2____dynamic_atexit_destructor_for__idAboutWindowsFirewall__; void (__cdecl *)()
0x180006e88  call    atexit
0x180006e8d  nop
0x180006e8e  lea     rcx, dword_180014C98
0x180006e95  call    _Init_thread_footer
0x180006e9a  mov     rdx, rdi; String2
0x180006e9d  mov     rcx, cs:String1; String1
0x180006ea4  call    cs:__imp__wcsicmp
0x180006eaa  test    eax, eax
0x180006eac  jnz     short loc_180006EB6
0x180006eae  lea     ebx, [rax+67h]
0x180006eb1  jmp     loc_180006FC9
0x180006eb6  mov     rdx, rdi; String2
0x180006eb9  mov     rcx, cs:qword_180014C00; String1
0x180006ec0  call    cs:__imp__wcsicmp
0x180006ec6  test    eax, eax
0x180006ec8  jnz     short loc_180006ED2
0x180006eca  lea     ebx, [rax+74h]
0x180006ecd  jmp     loc_180006FC9
0x180006ed2  mov     rdx, rdi; String2
0x180006ed5  mov     rcx, cs:qword_180014C10; String1
0x180006edc  call    cs:__imp__wcsicmp
0x180006ee2  test    eax, eax
0x180006ee4  jnz     short loc_180006EEE
0x180006ee6  lea     ebx, [rax+78h]
0x180006ee9  jmp     loc_180006FC9
0x180006eee  mov     rdx, rdi; String2
0x180006ef1  mov     rcx, cs:qword_180014C20; String1
0x180006ef8  call    cs:__imp__wcsicmp
0x180006efe  test    eax, eax
0x180006f00  jnz     short loc_180006F0A
0x180006f02  lea     ebx, [rax+6Ah]
0x180006f05  jmp     loc_180006FC9
0x180006f0a  mov     rdx, rdi; String2
0x180006f0d  mov     rcx, cs:qword_180014C30; String1
0x180006f14  call    cs:__imp__wcsicmp
0x180006f1a  test    eax, eax
0x180006f1c  jnz     short loc_180006F26
0x180006f1e  lea     ebx, [rax+6Bh]
0x180006f21  jmp     loc_180006FC9
0x180006f26  mov     rdx, rdi; String2
0x180006f29  mov     rcx, cs:qword_180014C40; String1
0x180006f30  call    cs:__imp__wcsicmp
0x180006f36  test    eax, eax
0x180006f38  jnz     short loc_180006F42
0x180006f3a  lea     ebx, [rax+6Ch]
0x180006f3d  jmp     loc_180006FC9
0x180006f42  mov     rdx, rdi; String2
0x180006f45  mov     rcx, cs:qword_180014C50; String1
0x180006f4c  call    cs:__imp__wcsicmp
0x180006f52  test    eax, eax
0x180006f54  jnz     short loc_180006F5D
0x180006f56  mov     ebx, 89h
0x180006f5b  jmp     short loc_180006FC9
0x180006f5d  mov     rdx, rdi; String2
0x180006f60  mov     rcx, cs:qword_180014C70; String1
0x180006f67  call    cs:__imp__wcsicmp
0x180006f6d  test    eax, eax
0x180006f6f  jnz     short loc_180006F78
0x180006f71  mov     ebx, 8Ch
0x180006f76  jmp     short loc_180006FC9
0x180006f78  mov     rdx, rdi; String2
0x180006f7b  mov     rcx, cs:qword_180014C80; String1
0x180006f82  call    cs:__imp__wcsicmp
0x180006f88  test    eax, eax
0x180006f8a  jnz     short loc_180006F93
0x180006f8c  mov     ebx, 82h
0x180006f91  jmp     short loc_180006FC9
0x180006f93  mov     rdx, rdi; String2
0x180006f96  mov     rcx, cs:qword_180014C90; String1
0x180006f9d  call    cs:__imp__wcsicmp
0x180006fa3  test    eax, eax
0x180006fa5  jnz     short loc_180006FAC
0x180006fa7  lea     ebx, [rax+7Ch]
0x180006faa  jmp     short loc_180006FC9
0x180006fac  mov     ebx, 64h ; 'd'
0x180006fb1  mov     rdx, rdi; String2
0x180006fb4  mov     rcx, cs:qword_180014CA0; String1
0x180006fbb  call    cs:__imp__wcsicmp
0x180006fc1  lea     ecx, [rbx+17h]
0x180006fc4  test    eax, eax
0x180006fc6  cmovz   ebx, ecx
0x180006fc9  xor     r9d, r9d
0x180006fcc  mov     r8, rsi
0x180006fcf  mov     edx, ebx
0x180006fd1  mov     rcx, rbp
0x180006fd4  add     rsp, 20h
0x180006fd8  pop     r14
0x180006fda  pop     rdi
0x180006fdb  pop     rsi
0x180006fdc  pop     rbp
0x180006fdd  pop     rbx
0x180006fde  jmp     ?ExecuteSecurityActionHandler@@YA_NPEAUHWND__@@W4SecurityAction@@PEAVSecurityLogicState@@_N@Z; ExecuteSecurityActionHandler(HWND__ *,SecurityAction,SecurityLogicState *,bool)
```
