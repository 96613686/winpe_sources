# WcmConnectionSelectionByName::WriteToRegistry(ATL::CRegKey &)

- ea: `0x18001b420`
- end: `0x18001b588`
- name: `?WriteToRegistry@WcmConnectionSelectionByName@@UEAAJAEAVCRegKey@ATL@@@Z`
- size: `360`
- prototype: `int(WcmConnectionSelectionByName *__hidden this, struct ATL::CRegKey *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x1800189d8`
- `0x180018ac0`
- `0x180018d84`
- `0x180018f18`
- `0x18001b420`

## string_xrefs

- `0x18001b455`: `WcmConnectionSelectionByName::WriteToRegistry`
- `0x18001b55d`: `WcmConnectionSelectionByName::WriteToRegistry`

## pseudocode

```c
__int64 __fastcall WcmConnectionSelectionByName::WriteToRegistry(WcmConnectionSelectionByName *this, HKEY *a2)
{
  __int64 v4; // rdx
  LSTATUS v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  WcmPolicyManager *v8; // rcx
  const BYTE *v9; // rax
  LSTATUS v10; // edi

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids,
      "WcmConnectionSelectionByName::WriteToRegistry");
  }
  v5 = ATL::CRegKey::SetDWORDValue(a2, L"SelectionType", *((_DWORD *)this + 2));
  if ( !v5 )
  {
    v5 = 0;
    v9 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 16, v4, v6, v7);
    v10 = ATL::CRegKey::SetStringValue(a2, L"ConnectionName", v9);
    if ( !v10 )
    {
      v8 = WPP_GLOBAL_Control;
      goto LABEL_22;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ConnectionName");
      v8 = WPP_GLOBAL_Control;
    }
    if ( v10 <= 0 )
    {
      v5 = v10;
      goto LABEL_22;
    }
    v5 = (unsigned __int16)v10;
    goto LABEL_12;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"SelectionType");
    v8 = WPP_GLOBAL_Control;
  }
  if ( v5 > 0 )
  {
    v5 = (unsigned __int16)v5;
LABEL_12:
    v5 |= 0x80070000;
  }
LABEL_22:
  if ( v8 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) >= 5u && (*((_BYTE *)v8 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v8 + 2),
      13,
      (unsigned int)WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids,
      (unsigned int)"WcmConnectionSelectionByName::WriteToRegistry",
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001b420  push    rbx
0x18001b422  push    rsi
0x18001b423  push    rdi
0x18001b424  push    r12
0x18001b426  push    r14
0x18001b428  sub     rsp, 30h
0x18001b42c  mov     rdi, rdx
0x18001b42f  mov     rsi, rcx
0x18001b432  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b439  lea     r14, WPP_GLOBAL_Control
0x18001b440  cmp     rcx, r14
0x18001b443  jz      short loc_18001B46D
0x18001b445  cmp     byte ptr [rcx+19h], 5
0x18001b449  jb      short loc_18001B46D
0x18001b44b  test    byte ptr [rcx+1Ch], 1
0x18001b44f  jz      short loc_18001B46D
0x18001b451  mov     rcx, [rcx+10h]
0x18001b455  lea     r9, aWcmconnections_4; "WcmConnectionSelectionByName::WriteToRe"...
0x18001b45c  mov     edx, 0Ah
0x18001b461  lea     r8, WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids
0x18001b468  call    WPP_SF_s
0x18001b46d  mov     r8d, [rsi+8]; unsigned int
0x18001b471  lea     r12, ?c_szConnectionSelection_SelectionTypeRegKey@@3QBGB; "SelectionType"
0x18001b478  mov     rdx, r12; unsigned __int16 *
0x18001b47b  mov     rcx, rdi; this
0x18001b47e  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001b483  mov     ebx, eax
0x18001b485  test    eax, eax
0x18001b487  jz      short loc_18001B4D4
0x18001b489  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b490  cmp     rcx, r14
0x18001b493  jz      short loc_18001B4C5
0x18001b495  cmp     byte ptr [rcx+19h], 1
0x18001b499  jb      short loc_18001B4C5
0x18001b49b  test    byte ptr [rcx+1Ch], 1
0x18001b49f  jz      short loc_18001B4C5
0x18001b4a1  mov     rcx, [rcx+10h]; LoggerHandle
0x18001b4a5  lea     r8, WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids
0x18001b4ac  mov     edx, 0Bh
0x18001b4b1  mov     [rsp+58h+var_38], r12; __int64
0x18001b4b6  mov     r9d, eax
0x18001b4b9  call    WPP_SF_DS
0x18001b4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4c5  test    ebx, ebx
0x18001b4c7  jle     short loc_18001B548
0x18001b4c9  movzx   ebx, bx
0x18001b4cc  or      ebx, 80070000h
0x18001b4d2  jmp     short loc_18001B548
0x18001b4d4  lea     rcx, [rsi+10h]
0x18001b4d8  xor     ebx, ebx
0x18001b4da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b4df  lea     rsi, ?c_szConnectionSelection_ConnectionNameRegKey@@3QBGB; "ConnectionName"
0x18001b4e6  mov     r8, rax; unsigned __int16 *
0x18001b4e9  mov     rdx, rsi; unsigned __int16 *
0x18001b4ec  mov     rcx, rdi; this
0x18001b4ef  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18001b4f4  mov     edi, eax
0x18001b4f6  test    eax, eax
0x18001b4f8  jz      short loc_18001B541
0x18001b4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b501  cmp     rcx, r14
0x18001b504  jz      short loc_18001B534
0x18001b506  cmp     byte ptr [rcx+19h], 1
0x18001b50a  jb      short loc_18001B534
0x18001b50c  test    byte ptr [rcx+1Ch], 1
0x18001b510  jz      short loc_18001B534
0x18001b512  mov     rcx, [rcx+10h]; LoggerHandle
0x18001b516  lea     edx, [rbx+0Ch]
0x18001b519  mov     r9d, eax
0x18001b51c  mov     [rsp+58h+var_38], rsi; __int64
0x18001b521  lea     r8, WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids
0x18001b528  call    WPP_SF_DS
0x18001b52d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b534  test    edi, edi
0x18001b536  jg      short loc_18001B53C
0x18001b538  mov     ebx, edi
0x18001b53a  jmp     short loc_18001B548
0x18001b53c  movzx   ebx, di
0x18001b53f  jmp     short loc_18001B4CC
0x18001b541  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b548  cmp     rcx, r14
0x18001b54b  jz      short loc_18001B579
0x18001b54d  cmp     byte ptr [rcx+19h], 5
0x18001b551  jb      short loc_18001B579
0x18001b553  test    byte ptr [rcx+1Ch], 1
0x18001b557  jz      short loc_18001B579
0x18001b559  mov     rcx, [rcx+10h]
0x18001b55d  lea     r9, aWcmconnections_4; "WcmConnectionSelectionByName::WriteToRe"...
0x18001b564  mov     edx, 0Dh
0x18001b569  mov     dword ptr [rsp+58h+var_38], ebx
0x18001b56d  lea     r8, WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids
0x18001b574  call    WPP_SF_sL
0x18001b579  mov     eax, ebx
0x18001b57b  add     rsp, 30h
0x18001b57f  pop     r14
0x18001b581  pop     r12
0x18001b583  pop     rdi
0x18001b584  pop     rsi
0x18001b585  pop     rbx
0x18001b586  retn
```
