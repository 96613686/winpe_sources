# WcmConnectionMappingPolicyKey::WriteToRegistry(ATL::CRegKey &)

- ea: `0x180018b14`
- end: `0x180018d1b`
- name: `?WriteToRegistry@WcmConnectionMappingPolicyKey@@QEAAJAEAVCRegKey@ATL@@@Z`
- size: `519`
- prototype: `int(WcmConnectionMappingPolicyKey *__hidden this, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180008010`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x1800189d8`
- `0x180018ac0`
- `0x180018b14`
- `0x180018d84`
- `0x180018f18`

## string_xrefs

- `0x180018b52`: `WcmConnectionMappingPolicyKey::WriteToRegistry`
- `0x180018cf2`: `WcmConnectionMappingPolicyKey::WriteToRegistry`

## pseudocode

```c
__int64 __fastcall WcmConnectionMappingPolicyKey::WriteToRegistry(
        WcmConnectionMappingPolicyKey *this,
        HKEY *a2,
        __int64 a3,
        __int64 a4)
{
  const BYTE *v6; // rax
  const unsigned __int16 *v7; // r12
  __int64 v8; // rdx
  LSTATUS v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  WcmPolicyManager *v12; // rcx
  const BYTE *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  const BYTE *v17; // rax
  LSTATUS v18; // edi

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_c091792df07e35dda6dca04425677804_Traceguids,
      "WcmConnectionMappingPolicyKey::WriteToRegistry");
  }
  v6 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 16, a2, a3, a4);
  v7 = L"PolicyContext";
  v9 = ATL::CRegKey::SetStringValue(a2, L"PolicyContext", v6);
  if ( v9 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
LABEL_9:
      WPP_SF_DS(*((_QWORD *)v12 + 2), (__int64)v7);
LABEL_10:
      v12 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v13 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48, v8, v10, v11);
    v7 = L"ClientIdentifier";
    v9 = ATL::CRegKey::SetStringValue(a2, L"ClientIdentifier", v13);
    if ( v9 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        goto LABEL_9;
      }
    }
    else
    {
      v17 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80, v14, v15, v16);
      v9 = ATL::CRegKey::SetStringValue(a2, L"Host", v17);
      if ( !v9 )
      {
        v9 = 0;
        v18 = ATL::CRegKey::SetDWORDValue(a2, L"Version", 1);
        if ( !v18 )
        {
          v12 = WPP_GLOBAL_Control;
          goto LABEL_33;
        }
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"Version");
          v12 = WPP_GLOBAL_Control;
        }
        if ( v18 <= 0 )
        {
          v9 = v18;
          goto LABEL_33;
        }
        v9 = (unsigned __int16)v18;
        goto LABEL_13;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"Host");
        goto LABEL_10;
      }
    }
  }
  if ( v9 > 0 )
  {
    v9 = (unsigned __int16)v9;
LABEL_13:
    v9 |= 0x80070000;
  }
LABEL_33:
  if ( v12 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v12 + 25) >= 5u && (*((_BYTE *)v12 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v12 + 2),
      15,
      (unsigned int)WPP_c091792df07e35dda6dca04425677804_Traceguids,
      (unsigned int)"WcmConnectionMappingPolicyKey::WriteToRegistry",
      v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180018b14  push    rbx
0x180018b16  push    rsi
0x180018b17  push    rdi
0x180018b18  push    r12
0x180018b1a  push    r14
0x180018b1c  push    r15
0x180018b1e  sub     rsp, 38h
0x180018b22  mov     rdi, rdx
0x180018b25  mov     rsi, rcx
0x180018b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b2f  lea     r14, WPP_GLOBAL_Control
0x180018b36  lea     r15, WPP_c091792df07e35dda6dca04425677804_Traceguids
0x180018b3d  cmp     rcx, r14
0x180018b40  jz      short loc_180018B66
0x180018b42  cmp     byte ptr [rcx+19h], 5
0x180018b46  jb      short loc_180018B66
0x180018b48  test    byte ptr [rcx+1Ch], 1
0x180018b4c  jz      short loc_180018B66
0x180018b4e  mov     rcx, [rcx+10h]
0x180018b52  lea     r9, aWcmconnectionm_6; "WcmConnectionMappingPolicyKey::WriteToR"...
0x180018b59  mov     edx, 0Ah
0x180018b5e  mov     r8, r15
0x180018b61  call    WPP_SF_s
0x180018b66  lea     rcx, [rsi+10h]
0x180018b6a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018b6f  lea     r12, ?c_szPolicyContextRegValue@@3QBGB; "PolicyContext"
0x180018b76  mov     r8, rax; unsigned __int16 *
0x180018b79  mov     rdx, r12; unsigned __int16 *
0x180018b7c  mov     rcx, rdi; this
0x180018b7f  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180018b84  mov     ebx, eax
0x180018b86  test    eax, eax
0x180018b88  jz      short loc_180018BD8
0x180018b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b91  cmp     rcx, r14
0x180018b94  jz      short loc_180018BC2
0x180018b96  cmp     byte ptr [rcx+19h], 1
0x180018b9a  jb      short loc_180018BC2
0x180018b9c  test    byte ptr [rcx+1Ch], 1
0x180018ba0  jz      short loc_180018BC2
0x180018ba2  mov     edx, 0Bh
0x180018ba7  mov     [rsp+68h+var_48], r12; __int64
0x180018bac  mov     rcx, [rcx+10h]; LoggerHandle
0x180018bb0  mov     r9d, ebx
0x180018bb3  mov     r8, r15
0x180018bb6  call    WPP_SF_DS
0x180018bbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bc2  test    ebx, ebx
0x180018bc4  jle     loc_180018CDD
0x180018bca  movzx   ebx, bx
0x180018bcd  or      ebx, 80070000h
0x180018bd3  jmp     loc_180018CDD
0x180018bd8  lea     rcx, [rsi+30h]
0x180018bdc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018be1  lea     r12, ?c_szClientIdentifierRegValue@@3QBGB; "ClientIdentifier"
0x180018be8  mov     r8, rax; unsigned __int16 *
0x180018beb  mov     rdx, r12; unsigned __int16 *
0x180018bee  mov     rcx, rdi; this
0x180018bf1  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180018bf6  mov     ebx, eax
0x180018bf8  test    eax, eax
0x180018bfa  jz      short loc_180018C1B
0x180018bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c03  cmp     rcx, r14
0x180018c06  jz      short loc_180018BC2
0x180018c08  cmp     byte ptr [rcx+19h], 1
0x180018c0c  jb      short loc_180018BC2
0x180018c0e  test    byte ptr [rcx+1Ch], 1
0x180018c12  jz      short loc_180018BC2
0x180018c14  mov     edx, 0Ch
0x180018c19  jmp     short loc_180018BA7
0x180018c1b  lea     rcx, [rsi+50h]
0x180018c1f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018c24  lea     rsi, ?c_szHostRegValue@@3QBGB; "Host"
0x180018c2b  mov     r8, rax; unsigned __int16 *
0x180018c2e  mov     rdx, rsi; unsigned __int16 *
0x180018c31  mov     rcx, rdi; this
0x180018c34  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180018c39  mov     ebx, eax
0x180018c3b  test    eax, eax
0x180018c3d  jz      short loc_180018C72
0x180018c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c46  cmp     rcx, r14
0x180018c49  jz      loc_180018BC2
0x180018c4f  cmp     byte ptr [rcx+19h], 1
0x180018c53  jb      loc_180018BC2
0x180018c59  test    byte ptr [rcx+1Ch], 1
0x180018c5d  jz      loc_180018BC2
0x180018c63  mov     edx, 0Dh
0x180018c68  mov     [rsp+68h+var_48], rsi
0x180018c6d  jmp     loc_180018BAC
0x180018c72  xor     ebx, ebx
0x180018c74  lea     rsi, ?c_szVersionRegValue@@3QBGB; "Version"
0x180018c7b  mov     rdx, rsi; unsigned __int16 *
0x180018c7e  mov     rcx, rdi; this
0x180018c81  lea     r8d, [rbx+1]; unsigned int
0x180018c85  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180018c8a  mov     edi, eax
0x180018c8c  test    eax, eax
0x180018c8e  jz      short loc_180018CD6
0x180018c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c97  cmp     rcx, r14
0x180018c9a  jz      short loc_180018CC6
0x180018c9c  cmp     byte ptr [rcx+19h], 1
0x180018ca0  jb      short loc_180018CC6
0x180018ca2  test    byte ptr [rcx+1Ch], 1
0x180018ca6  jz      short loc_180018CC6
0x180018ca8  mov     rcx, [rcx+10h]; LoggerHandle
0x180018cac  lea     edx, [rbx+0Eh]
0x180018caf  mov     r9d, eax
0x180018cb2  mov     [rsp+68h+var_48], rsi; __int64
0x180018cb7  mov     r8, r15
0x180018cba  call    WPP_SF_DS
0x180018cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180018cc6  test    edi, edi
0x180018cc8  jg      short loc_180018CCE
0x180018cca  mov     ebx, edi
0x180018ccc  jmp     short loc_180018CDD
0x180018cce  movzx   ebx, di
0x180018cd1  jmp     loc_180018BCD
0x180018cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180018cdd  cmp     rcx, r14
0x180018ce0  jz      short loc_180018D0A
0x180018ce2  cmp     byte ptr [rcx+19h], 5
0x180018ce6  jb      short loc_180018D0A
0x180018ce8  test    byte ptr [rcx+1Ch], 1
0x180018cec  jz      short loc_180018D0A
0x180018cee  mov     rcx, [rcx+10h]
0x180018cf2  lea     r9, aWcmconnectionm_6; "WcmConnectionMappingPolicyKey::WriteToR"...
0x180018cf9  mov     edx, 0Fh
0x180018cfe  mov     dword ptr [rsp+68h+var_48], ebx
0x180018d02  mov     r8, r15
0x180018d05  call    WPP_SF_sL
0x180018d0a  mov     eax, ebx
0x180018d0c  add     rsp, 38h
0x180018d10  pop     r15
0x180018d12  pop     r14
0x180018d14  pop     r12
0x180018d16  pop     rdi
0x180018d17  pop     rsi
0x180018d18  pop     rbx
0x180018d19  retn
```
