# OpenPolicyRootRegKey(ATL::CRegKey &)

- ea: `0x18001acac`
- end: `0x18001ae29`
- name: `?OpenPolicyRootRegKey@@YAJAEAVCRegKey@ATL@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001aa44`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180007a70`
- `0x180008a90`
- `0x18001728c`
- `0x180017a60`
- `0x1800180c4`
- `0x180018d84`
- `0x180018e48`
- `0x18001a8d0`
- `0x18001acac`
- `0x18001afa4`

## string_xrefs

- `0x18001acec`: `OpenPolicyRootRegKey`
- `0x18001ade6`: `OpenPolicyRootRegKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OpenPolicyRootRegKey(struct ATL::CRegKey *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int PersistentRegPathWstring; // eax
  unsigned int v5; // r8d
  unsigned int v6; // ebx
  __int64 result; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  const WCHAR *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // r8d
  unsigned int v18; // ebx
  unsigned int v19; // r8d
  const char *v20; // r9
  __int64 v21; // [rsp+0h] [rbp-68h] BYREF
  unsigned int v22; // [rsp+20h] [rbp-48h]
  _BYTE v23[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids,
      "OpenPolicyRootRegKey");
  }
  std::wstring::wstring(v23);
  PersistentRegPathWstring = GetPersistentRegPathWstring(v3, v2, (__int64)v23);
  if ( PersistentRegPathWstring )
  {
    v6 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x3A, v5, (const char *)PersistentRegPathWstring, v22);
    std::wstring::_Tidy_deallocate(v23);
    return v6;
  }
  else
  {
    v8 = std::_WChar_traits<unsigned short>::length(L"\\");
    try
    {
      std::wstring::_Append<unsigned short>(v23, v9, v8);
      v10 = std::_WChar_traits<unsigned short>::length(L"PoliciesBySource");
      std::wstring::_Append<unsigned short>(v23, v11, v10);
      v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23, v12, v13, v14);
      v16 = ATL::CRegKey::Open(this, HKEY_LOCAL_MACHINE, v15, 0xF003Fu);
      if ( v16 )
      {
        v18 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x3F, v17, (const char *)v16, v22);
        std::wstring::_Tidy_deallocate(v23);
        result = v18;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            (unsigned int)&WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids,
            (unsigned int)"OpenPolicyRootRegKey",
            0);
        }
        std::wstring::_Tidy_deallocate(v23);
        result = 0;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, &v21, v19, v20);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001acac  mov     [rsp+arg_8], rbx
0x18001acb1  push    rdi
0x18001acb2  sub     rsp, 60h
0x18001acb6  mov     rax, cs:__security_cookie
0x18001acbd  xor     rax, rsp
0x18001acc0  mov     [rsp+68h+var_10], rax
0x18001acc5  mov     rbx, rcx
0x18001acc8  lea     rdi, WPP_GLOBAL_Control
0x18001accf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acd6  cmp     rcx, rdi
0x18001acd9  jz      short loc_18001AD03
0x18001acdb  cmp     byte ptr [rcx+19h], 5
0x18001acdf  jb      short loc_18001AD03
0x18001ace1  test    byte ptr [rcx+1Ch], 1
0x18001ace5  jz      short loc_18001AD03
0x18001ace7  mov     edx, 0Ah
0x18001acec  lea     r9, aOpenpolicyroot; "OpenPolicyRootRegKey"
0x18001acf3  lea     r8, WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids
0x18001acfa  mov     rcx, [rcx+10h]
0x18001acfe  call    WPP_SF_s
0x18001ad03  lea     rcx, [rsp+68h+var_30]
0x18001ad08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001ad0d  nop
0x18001ad0e  lea     r8, [rsp+68h+var_30]
0x18001ad13  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x18001ad18  test    eax, eax
0x18001ad1a  jz      short loc_18001AD41
0x18001ad1c  mov     rcx, [rsp+68h]; this
0x18001ad21  mov     r9d, eax; char *
0x18001ad24  mov     edx, 3Ah ; ':'; void *
0x18001ad29  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ad2e  mov     ebx, eax
0x18001ad30  lea     rcx, [rsp+68h+var_30]
0x18001ad35  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ad3a  mov     eax, ebx
0x18001ad3c  jmp     loc_18001AE10
0x18001ad41  lea     rcx, asc_180022108; "\\"
0x18001ad48  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001ad4d  mov     r8, rax
0x18001ad50  mov     rdx, rcx
0x18001ad53  lea     rcx, [rsp+68h+var_30]
0x18001ad58  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001ad5d  lea     rcx, ?c_szWcmPoliciesBySourceSubkey@@3QBGB; "PoliciesBySource"
0x18001ad64  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001ad69  mov     r8, rax
0x18001ad6c  mov     rdx, rcx
0x18001ad6f  lea     rcx, [rsp+68h+var_30]
0x18001ad74  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001ad79  lea     rcx, [rsp+68h+var_30]
0x18001ad7e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ad83  mov     r8, rax; lpSubKey
0x18001ad86  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001ad8d  mov     r9d, 0F003Fh; unsigned int
0x18001ad93  mov     rcx, rbx; this
0x18001ad96  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001ad9b  test    eax, eax
0x18001ad9d  jz      short loc_18001ADC1
0x18001ad9f  mov     rcx, [rsp+68h]; this
0x18001ada4  mov     r9d, eax; char *
0x18001ada7  mov     edx, 3Fh ; '?'; void *
0x18001adac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001adb1  mov     ebx, eax
0x18001adb3  lea     rcx, [rsp+68h+var_30]
0x18001adb8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001adbd  mov     eax, ebx
0x18001adbf  jmp     short loc_18001AE10
0x18001adc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adc8  cmp     rcx, rdi
0x18001adcb  jz      short loc_18001ADFE
0x18001adcd  cmp     byte ptr [rcx+19h], 5
0x18001add1  jb      short loc_18001ADFE
0x18001add3  test    byte ptr [rcx+1Ch], 1
0x18001add7  jz      short loc_18001ADFE
0x18001add9  mov     edx, 0Bh
0x18001adde  mov     [rsp+68h+var_48], 0
0x18001ade6  lea     r9, aOpenpolicyroot; "OpenPolicyRootRegKey"
0x18001aded  lea     r8, WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids
0x18001adf4  mov     rcx, [rcx+10h]
0x18001adf8  call    WPP_SF_sL
0x18001adfd  nop
0x18001adfe  lea     rcx, [rsp+68h+var_30]
0x18001ae03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ae08  xor     eax, eax
0x18001ae0a  jmp     short loc_18001AE10
0x18001ae0c  mov     eax, [rsp+68h+var_38]
0x18001ae10  mov     rcx, [rsp+68h+var_10]
0x18001ae15  xor     rcx, rsp; StackCookie
0x18001ae18  call    __security_check_cookie
0x18001ae1d  mov     rbx, [rsp+68h+arg_8]
0x18001ae22  add     rsp, 60h
0x18001ae26  pop     rdi
0x18001ae27  retn
```
