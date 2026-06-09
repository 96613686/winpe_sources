# HMEHelpers::RetrieveWMPDeviceSettings(IWMPPlayerInternalMarshalled *,ushort *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)

- ea: `0x180016d00`
- end: `0x180016da2`
- name: `?RetrieveWMPDeviceSettings@HMEHelpers@@YAJPEAUIWMPPlayerInternalMarshalled@@PEAGPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z`
- size: `162`
- prototype: `int(HMEHelpers *__hidden this, struct IWMPPlayerInternalMarshalled *, unsigned __int16 *, struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000653c`
- `0x1800069d4`
- `0x18000b380`
- `0x1800125c0`

## callees

- `0x1800166a0`
- `0x180016b00`
- `0x180016d00`
- `0x18001e010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180016d73`
- `KERNEL32!Sleep` at `0x180016d73`
- `OLEAUT32!__imp_SysAllocString` at `0x180016d36`
- `OLEAUT32!__imp_SysAllocString` at `0x180016d36`
- `OLEAUT32!__imp_SysFreeString` at `0x180016d81`
- `OLEAUT32!__imp_SysFreeString` at `0x180016d81`
- `OLEAUT32!__imp_SysStringLen` at `0x180016d42`
- `OLEAUT32!__imp_SysStringLen` at `0x180016d42`

## pseudocode

```c
__int64 __fastcall HMEHelpers::RetrieveWMPDeviceSettings(
        HMEHelpers *this,
        struct IWMPPlayerInternalMarshalled *a2,
        HMEHelpers *a3,
        struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *a4)
{
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v7; // rdx
  OLECHAR *v8; // rbp
  int i; // edi
  unsigned int v10; // ebx

  if ( this && a2 && a3 )
  {
    HMEHelpers::CleanupWMPDeviceSettings(a3, a2);
    HMEHelpers::InitializeWMPDeviceSettings(a3, v7);
    v8 = SysAllocString((const OLECHAR *)a2);
    if ( SysStringLen(v8) )
    {
      for ( i = 0; i < 5; ++i )
      {
        v10 = (*(__int64 (__fastcall **)(HMEHelpers *, OLECHAR *, HMEHelpers *))(*(_QWORD *)this + 48LL))(this, v8, a3);
        if ( v10 != -2147023659 )
          break;
        Sleep(0x64u);
      }
      SysFreeString(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v10;
}

```

## disassembly

```asm
0x180016d00  push    rbx
0x180016d02  push    rbp
0x180016d03  push    rsi
0x180016d04  push    rdi
0x180016d05  push    r14
0x180016d07  sub     rsp, 20h
0x180016d0b  mov     rsi, r8
0x180016d0e  mov     rbx, rdx
0x180016d11  mov     r14, rcx
0x180016d14  test    rcx, rcx
0x180016d17  jz      short loc_180016D90
0x180016d19  test    rdx, rdx
0x180016d1c  jz      short loc_180016D90
0x180016d1e  test    r8, r8
0x180016d21  jz      short loc_180016D90
0x180016d23  mov     rcx, r8; this
0x180016d26  call    ?CleanupWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::CleanupWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180016d2b  mov     rcx, rsi; this
0x180016d2e  call    ?InitializeWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::InitializeWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180016d33  mov     rcx, rbx; psz
0x180016d36  call    cs:__imp_SysAllocString
0x180016d3c  mov     rcx, rax; pbstr
0x180016d3f  mov     rbp, rax
0x180016d42  call    cs:__imp_SysStringLen
0x180016d48  test    eax, eax
0x180016d4a  jz      short loc_180016D89
0x180016d4c  xor     edi, edi
0x180016d4e  mov     rcx, [r14]
0x180016d51  mov     r8, rsi
0x180016d54  mov     rdx, rbp
0x180016d57  mov     rax, [rcx+30h]
0x180016d5b  mov     rcx, r14
0x180016d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d63  mov     ebx, eax
0x180016d65  cmp     eax, 800704D5h
0x180016d6a  jnz     short loc_180016D7E
0x180016d6c  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180016d71  inc     edi
0x180016d73  call    cs:__imp_Sleep
0x180016d79  cmp     edi, 5
0x180016d7c  jl      short loc_180016D4E
0x180016d7e  mov     rcx, rbp; bstrString
0x180016d81  call    cs:__imp_SysFreeString
0x180016d87  jmp     short loc_180016D95
0x180016d89  mov     ebx, 8007000Eh
0x180016d8e  jmp     short loc_180016D95
0x180016d90  mov     ebx, 80004003h
0x180016d95  mov     eax, ebx
0x180016d97  add     rsp, 20h
0x180016d9b  pop     r14
0x180016d9d  pop     rdi
0x180016d9e  pop     rsi
0x180016d9f  pop     rbp
0x180016da0  pop     rbx
0x180016da1  retn
```
