# ShowFailDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x1800058b0`
- end: `0x180005925`
- name: `?ShowFailDialogCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `117`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001b90`
- `0x18000485c`
- `0x1800058b0`
- `0x180006520`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800058d8`
- `msvcrt!_wcsicmp` at `0x1800058f3`
- `msvcrt!_wcsicmp` at `0x1800058d8`
- `msvcrt!_wcsicmp` at `0x1800058f3`

## string_xrefs

- `0x1800058e7`: `errorActionInternetSettingsConfigure`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShowFailDialogCallbackProc(HWND a1, int a2, __int64 a3, __int64 a4)
{
  int v5; // edx
  wchar_t *String1; // [rsp+20h] [rbp-18h] BYREF

  if ( a2 == 3 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &String1,
      a4);
    if ( _wcsicmp(String1, L"errorActionWindowsFirewallControlPanel") )
    {
      if ( _wcsicmp(String1, L"errorActionInternetSettingsConfigure") )
      {
LABEL_7:
        ATL::CStringData::Release((ATL::CStringData *)(String1 - 12));
        return 0;
      }
      v5 = 116;
    }
    else
    {
      v5 = 120;
    }
    ExecuteSecurityActionHandler(a1, v5, 0, 0);
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x1800058b0  push    rbx
0x1800058b2  sub     rsp, 30h
0x1800058b6  mov     rbx, rcx
0x1800058b9  cmp     edx, 3
0x1800058bc  jnz     short loc_18000591D
0x1800058be  mov     rdx, r9
0x1800058c1  lea     rcx, [rsp+38h+String1]
0x1800058c6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800058cb  nop
0x1800058cc  lea     rdx, aErroractionwin; "errorActionWindowsFirewallControlPanel"
0x1800058d3  mov     rcx, [rsp+38h+String1]; String1
0x1800058d8  call    cs:__imp__wcsicmp
0x1800058de  test    eax, eax
0x1800058e0  jnz     short loc_1800058E7
0x1800058e2  lea     edx, [rax+78h]
0x1800058e5  jmp     short loc_180005900
0x1800058e7  lea     rdx, aErroractionint; "errorActionInternetSettingsConfigure"
0x1800058ee  mov     rcx, [rsp+38h+String1]; String1
0x1800058f3  call    cs:__imp__wcsicmp
0x1800058f9  test    eax, eax
0x1800058fb  jnz     short loc_18000590F
0x1800058fd  lea     edx, [rax+74h]
0x180005900  xor     r9d, r9d
0x180005903  xor     r8d, r8d
0x180005906  mov     rcx, rbx
0x180005909  call    ?ExecuteSecurityActionHandler@@YA_NPEAUHWND__@@W4SecurityAction@@PEAVSecurityLogicState@@_N@Z; ExecuteSecurityActionHandler(HWND__ *,SecurityAction,SecurityLogicState *,bool)
0x18000590e  nop
0x18000590f  mov     rcx, [rsp+38h+String1]
0x180005914  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180005918  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000591d  xor     eax, eax
0x18000591f  add     rsp, 30h
0x180005923  pop     rbx
0x180005924  retn
```
