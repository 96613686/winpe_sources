# OpenOrCreatePolicySourceRegKey(WCM_POLICY_SOURCE,ATL::CRegKey &,int)

- ea: `0x18001aa44`
- end: `0x18001aca6`
- name: `?OpenOrCreatePolicySourceRegKey@@YAJW4WCM_POLICY_SOURCE@@AEAVCRegKey@ATL@@H@Z`
- size: `610`
- prototype: `int __high(enum WCM_POLICY_SOURCE, struct ATL::CRegKey *, int)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180006750`
- `0x180007db0`
- `0x180008010`
- `0x1800176c0`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x1800075e8`
- `0x180007a70`
- `0x180008a90`
- `0x18001728c`
- `0x1800172ec`
- `0x180017a60`
- `0x180017d3c`
- `0x1800185e8`
- `0x180018d84`
- `0x18001a2d0`
- `0x18001a6a4`
- `0x18001aa44`
- `0x18001acac`
- `0x18001b0cc`

## string_xrefs

- `0x18001aa97`: `OpenOrCreatePolicySourceRegKey`
- `0x18001ac55`: `OpenOrCreatePolicySourceRegKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OpenOrCreatePolicySourceRegKey(int a1, ATL::CRegKey *a2, int a3)
{
  __int64 v5; // rsi
  signed int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  const WCHAR *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  const WCHAR *v14; // rax
  unsigned __int16 *v15; // r9
  __int64 v16; // rdx
  int v17; // edi
  __int64 v18; // r8
  __int64 v19; // r9
  WcmPolicyManager *v20; // r10
  __int64 v21; // rax
  __int64 v22; // r10
  __int64 v23; // rax
  __int64 v24; // r10
  int v26; // [rsp+28h] [rbp-51h]
  HKEY hKey[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v28; // [rsp+50h] [rbp-29h]
  _BYTE v29[32]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v30[32]; // [rsp+80h] [rbp+7h] BYREF

  v5 = a1;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids,
      "OpenOrCreatePolicySourceRegKey");
  }
  hKey[0] = 0;
  hKey[1] = 0;
  v28 = 0;
  std::wstring::wstring(v30);
  v6 = OpenPolicyRootRegKey((struct ATL::CRegKey *)hKey);
  if ( v6 < 0 )
    goto LABEL_24;
  std::_Integral_to_string<unsigned short,unsigned __int64>(v29, v5);
  std::wstring::operator=(v30, v29);
  std::wstring::_Tidy_deallocate(v29);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30, v7, v8, v9);
  if ( !(unsigned int)ATL::CRegKey::Open(a2, hKey[0], v10, 0xF003Fu) )
    goto LABEL_24;
  if ( !a3 )
  {
    v6 = -2147467259;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WcmPolicyManager *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids,
      (unsigned int)v5,
      -2147467259);
    goto LABEL_24;
  }
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30, v11, v12, v13);
  v17 = ATL::CRegKey::Create(a2, hKey[0], v14, v15);
  if ( v17 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30, v16, v18, v19);
      WPP_SF_DDSS(*(_QWORD *)(v22 + 16), v5, v26, v21);
      v20 = WPP_GLOBAL_Control;
    }
    if ( v17 > 0 )
      v6 = (unsigned __int16)v17 | 0x80070000;
    else
      v6 = v17;
    goto LABEL_25;
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (WcmPolicyManager *)&WPP_GLOBAL_Control )
    goto LABEL_29;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30, v16, v18, v19);
    WPP_SF_DSS(*(_QWORD *)(v24 + 16), (__int64)L"PoliciesBySource", v23);
LABEL_24:
    v20 = WPP_GLOBAL_Control;
  }
LABEL_25:
  if ( v20 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v20 + 25) >= 5u && (*((_BYTE *)v20 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v20 + 2),
      16,
      (unsigned int)&WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids,
      (unsigned int)"OpenOrCreatePolicySourceRegKey",
      v6);
LABEL_29:
  std::wstring::_Tidy_deallocate(v30);
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001aa44  mov     [rsp-8+arg_10], rbx
0x18001aa49  push    rbp
0x18001aa4a  push    rsi
0x18001aa4b  push    rdi
0x18001aa4c  push    r13
0x18001aa4e  push    r14
0x18001aa50  lea     rbp, [rsp-37h]
0x18001aa55  sub     rsp, 0B0h
0x18001aa5c  mov     rax, cs:__security_cookie
0x18001aa63  xor     rax, rsp
0x18001aa66  mov     [rbp+57h+var_30], rax
0x18001aa6a  mov     edi, r8d
0x18001aa6d  mov     r14, rdx
0x18001aa70  movsxd  rsi, ecx
0x18001aa73  lea     r13, WPP_GLOBAL_Control
0x18001aa7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa81  cmp     rcx, r13
0x18001aa84  jz      short loc_18001AAAE
0x18001aa86  cmp     byte ptr [rcx+19h], 5
0x18001aa8a  jb      short loc_18001AAAE
0x18001aa8c  test    byte ptr [rcx+1Ch], 1
0x18001aa90  jz      short loc_18001AAAE
0x18001aa92  mov     edx, 0Ch
0x18001aa97  lea     r9, aOpenorcreatepo; "OpenOrCreatePolicySourceRegKey"
0x18001aa9e  lea     r8, WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids
0x18001aaa5  mov     rcx, [rcx+10h]
0x18001aaa9  call    WPP_SF_s
0x18001aaae  xorps   xmm0, xmm0
0x18001aab1  xor     eax, eax
0x18001aab3  movups  xmmword ptr [rbp+57h+hKey], xmm0
0x18001aab7  mov     [rbp+57h+hKey], rax
0x18001aabb  mov     [rbp+57h+hKey+8], rax
0x18001aabf  mov     [rbp+57h+var_80], rax
0x18001aac3  lea     rcx, [rbp+57h+var_50]
0x18001aac7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001aacc  nop
0x18001aacd  lea     rcx, [rbp+57h+hKey]; this
0x18001aad1  call    ?OpenPolicyRootRegKey@@YAJAEAVCRegKey@ATL@@@Z; OpenPolicyRootRegKey(ATL::CRegKey &)
0x18001aad6  mov     ebx, eax
0x18001aad8  test    eax, eax
0x18001aada  js      loc_18001AC32
0x18001aae0  mov     rdx, rsi
0x18001aae3  lea     rcx, [rbp+57h+var_70]
0x18001aae7  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x18001aaec  lea     rdx, [rbp+57h+var_70]
0x18001aaf0  lea     rcx, [rbp+57h+var_50]
0x18001aaf4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001aaf9  lea     rcx, [rbp+57h+var_70]
0x18001aafd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ab02  lea     rcx, [rbp+57h+var_50]
0x18001ab06  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ab0b  mov     r8, rax; lpSubKey
0x18001ab0e  mov     r9d, 0F003Fh; unsigned int
0x18001ab14  mov     rdx, [rbp+57h+hKey]; hKey
0x18001ab18  mov     rcx, r14; this
0x18001ab1b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001ab20  test    eax, eax
0x18001ab22  jz      loc_18001AC32
0x18001ab28  test    edi, edi
0x18001ab2a  jz      loc_18001ABF3
0x18001ab30  lea     rcx, [rbp+57h+var_50]
0x18001ab34  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ab39  mov     r8, rax; lpSubKey
0x18001ab3c  mov     rdx, [rbp+57h+hKey]; hKey
0x18001ab40  mov     rcx, r14; this
0x18001ab43  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001ab48  mov     edi, eax
0x18001ab4a  test    eax, eax
0x18001ab4c  jz      short loc_18001ABA6
0x18001ab4e  mov     r10, cs:WPP_GLOBAL_Control
0x18001ab55  cmp     r10, r13
0x18001ab58  jz      short loc_18001AB8D
0x18001ab5a  cmp     byte ptr [r10+19h], 1
0x18001ab5f  jb      short loc_18001AB8D
0x18001ab61  test    byte ptr [r10+1Ch], 1
0x18001ab66  jz      short loc_18001AB8D
0x18001ab68  lea     rcx, [rbp+57h+var_50]
0x18001ab6c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ab71  mov     [rsp+0D0h+var_A0], rax; __int64
0x18001ab76  mov     dword ptr [rsp+0D0h+var_B0], esi; char
0x18001ab7a  mov     r9d, edi
0x18001ab7d  mov     rcx, [r10+10h]; LoggerHandle
0x18001ab81  call    WPP_SF_DDSS
0x18001ab86  mov     r10, cs:WPP_GLOBAL_Control
0x18001ab8d  test    edi, edi
0x18001ab8f  jg      short loc_18001AB98
0x18001ab91  mov     ebx, edi
0x18001ab93  jmp     loc_18001AC39
0x18001ab98  movzx   ebx, di
0x18001ab9b  or      ebx, 80070000h
0x18001aba1  jmp     loc_18001AC39
0x18001aba6  mov     r10, cs:WPP_GLOBAL_Control
0x18001abad  cmp     r10, r13
0x18001abb0  jz      loc_18001AC6D
0x18001abb6  cmp     byte ptr [r10+19h], 4
0x18001abbb  jb      short loc_18001AC39
0x18001abbd  test    byte ptr [r10+1Ch], 1
0x18001abc2  jz      short loc_18001AC39
0x18001abc4  lea     rcx, [rbp+57h+var_50]
0x18001abc8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001abcd  mov     [rsp+0D0h+var_A8], rax; __int64
0x18001abd2  lea     rax, ?c_szWcmPoliciesBySourceSubkey@@3QBGB; "PoliciesBySource"
0x18001abd9  mov     qword ptr [rsp+0D0h+var_B0], rax; __int64
0x18001abde  mov     r9d, esi
0x18001abe1  lea     r8, WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids
0x18001abe8  mov     rcx, [r10+10h]; LoggerHandle
0x18001abec  call    WPP_SF_DSS
0x18001abf1  jmp     short loc_18001AC32
0x18001abf3  mov     ebx, 80004005h
0x18001abf8  mov     r10, cs:WPP_GLOBAL_Control
0x18001abff  cmp     r10, r13
0x18001ac02  jz      short loc_18001AC6D
0x18001ac04  cmp     byte ptr [r10+19h], 4
0x18001ac09  jb      short loc_18001AC39
0x18001ac0b  test    byte ptr [r10+1Ch], 1
0x18001ac10  jz      short loc_18001AC39
0x18001ac12  mov     edx, 0Fh
0x18001ac17  mov     dword ptr [rsp+0D0h+var_B0], 80004005h
0x18001ac1f  mov     r9d, esi
0x18001ac22  lea     r8, WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids
0x18001ac29  mov     rcx, [r10+10h]
0x18001ac2d  call    WPP_SF_DD
0x18001ac32  mov     r10, cs:WPP_GLOBAL_Control
0x18001ac39  cmp     r10, r13
0x18001ac3c  jz      short loc_18001AC6D
0x18001ac3e  cmp     byte ptr [r10+19h], 5
0x18001ac43  jb      short loc_18001AC6D
0x18001ac45  test    byte ptr [r10+1Ch], 1
0x18001ac4a  jz      short loc_18001AC6D
0x18001ac4c  mov     edx, 10h
0x18001ac51  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18001ac55  lea     r9, aOpenorcreatepo; "OpenOrCreatePolicySourceRegKey"
0x18001ac5c  lea     r8, WPP_227ec7eaf66936e2d90bc32ed9537d75_Traceguids
0x18001ac63  mov     rcx, [r10+10h]
0x18001ac67  call    WPP_SF_sL
0x18001ac6c  nop
0x18001ac6d  lea     rcx, [rbp+57h+var_50]
0x18001ac71  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ac76  nop
0x18001ac77  lea     rcx, [rbp+57h+hKey]; this
0x18001ac7b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001ac80  mov     eax, ebx
0x18001ac82  mov     rcx, [rbp+57h+var_30]
0x18001ac86  xor     rcx, rsp; StackCookie
0x18001ac89  call    __security_check_cookie
0x18001ac8e  mov     rbx, [rsp+0D0h+arg_10]
0x18001ac96  add     rsp, 0B0h
0x18001ac9d  pop     r14
0x18001ac9f  pop     r13
0x18001aca1  pop     rdi
0x18001aca2  pop     rsi
0x18001aca3  pop     rbp
0x18001aca4  retn
```
