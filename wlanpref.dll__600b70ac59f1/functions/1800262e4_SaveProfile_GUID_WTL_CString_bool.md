# SaveProfile(_GUID &,WTL::CString &,bool)

- ea: `0x1800262e4`
- end: `0x180026512`
- name: `?SaveProfile@@YAJAEAU_GUID@@AEAVCString@WTL@@_N@Z`
- size: `558`
- prototype: `__int64 __fastcall(GUID *pInterfaceGuid, const unsigned __int16 **, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023550`

## callees

- `0x18000cdcc`
- `0x180020800`
- `0x180023054`
- `0x18002307c`
- `0x1800249d4`
- `0x1800262e4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800264fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800264fe`
- `wlanapi!WlanCloseHandle` at `0x1800264b4`
- `wlanapi!WlanCloseHandle` at `0x1800264b4`
- `wlanapi!WlanSetProfile` at `0x180026435`
- `wlanapi!WlanSetProfile` at `0x180026435`
- `wlanapi!WlanOpenHandle` at `0x1800263e8`
- `wlanapi!WlanOpenHandle` at `0x1800263e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SaveProfile(GUID *pInterfaceGuid, const unsigned __int16 **a2, unsigned __int8 a3)
{
  int v3; // esi
  const unsigned __int16 *v6; // rdx
  _QWORD *v7; // rcx
  DWORD v8; // eax
  signed int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  LPCWSTR strProfileXml[7]; // [rsp+40h] [rbp-38h] BYREF
  DWORD pdwReasonCode; // [rsp+88h] [rbp+10h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+90h] [rbp+18h] BYREF
  void *phClientHandle; // [rsp+98h] [rbp+20h] BYREF

  v3 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 22, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids);
  }
  v6 = *a2;
  phClientHandle = 0;
  pdwReasonCode = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)strProfileXml, v6);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 145) >= 3u && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
    {
      WPP_SF__guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        23,
        WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids,
        pInterfaceGuid);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 145) >= 3u && (*((_BYTE *)v7 + 148) & 1) != 0 )
      WPP_SF_S(v7[17], 24, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids, *a2);
  }
  pdwNegotiatedVersion = 0;
  v8 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  v9 = v8;
  if ( v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 145)
      && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
    {
      v11 = 26;
      goto LABEL_23;
    }
  }
  else
  {
    v8 = WlanSetProfile(phClientHandle, pInterfaceGuid, 2 * (v3 ^ 1), strProfileXml[0], 0, 1, 0, &pdwReasonCode);
    v9 = v8;
    if ( !v8 )
    {
LABEL_24:
      v10 = WPP_GLOBAL_Control;
      goto LABEL_25;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 145)
      && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
    {
      v11 = 25;
LABEL_23:
      WPP_SF_d(v10[17], v11, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids, v8);
      goto LABEL_24;
    }
  }
LABEL_25:
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 145) >= 4u && (*((_BYTE *)v10 + 148) & 1) != 0 )
    WPP_SF_(v10[17], 27, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids);
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  SysFreeString((BSTR)strProfileXml[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800262e4  push    rbx
0x1800262e6  push    rsi
0x1800262e7  push    rdi
0x1800262e8  push    r12
0x1800262ea  push    r15
0x1800262ec  sub     rsp, 50h
0x1800262f0  movzx   esi, r8b
0x1800262f4  mov     rbx, rdx
0x1800262f7  mov     rdi, rcx
0x1800262fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180026301  lea     r15, WPP_GLOBAL_Control
0x180026308  lea     r12, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids
0x18002630f  cmp     rcx, r15
0x180026312  jz      short loc_18002633A
0x180026314  cmp     byte ptr [rcx+91h], 4
0x18002631b  jb      short loc_18002633A
0x18002631d  test    byte ptr [rcx+94h], 1
0x180026324  jz      short loc_18002633A
0x180026326  mov     rcx, [rcx+88h]
0x18002632d  mov     edx, 16h
0x180026332  mov     r8, r12
0x180026335  call    WPP_SF_
0x18002633a  mov     rdx, [rbx]; unsigned __int16 *
0x18002633d  lea     rcx, [rsp+78h+strProfileXml]; this
0x180026342  mov     [rsp+78h+phClientHandle], 0
0x18002634e  mov     [rsp+78h+arg_8], 0
0x180026359  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002635e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026365  cmp     rcx, r15
0x180026368  jz      short loc_1800263C8
0x18002636a  cmp     byte ptr [rcx+91h], 3
0x180026371  jb      short loc_18002639A
0x180026373  test    byte ptr [rcx+94h], 1
0x18002637a  jz      short loc_18002639A
0x18002637c  mov     rcx, [rcx+88h]
0x180026383  mov     edx, 17h
0x180026388  mov     r9, rdi
0x18002638b  mov     r8, r12
0x18002638e  call    WPP_SF__guid_
0x180026393  mov     rcx, cs:WPP_GLOBAL_Control
0x18002639a  cmp     rcx, r15
0x18002639d  jz      short loc_1800263C8
0x18002639f  cmp     byte ptr [rcx+91h], 3
0x1800263a6  jb      short loc_1800263C8
0x1800263a8  test    byte ptr [rcx+94h], 1
0x1800263af  jz      short loc_1800263C8
0x1800263b1  mov     r9, [rbx]
0x1800263b4  mov     edx, 18h
0x1800263b9  mov     rcx, [rcx+88h]
0x1800263c0  mov     r8, r12
0x1800263c3  call    WPP_SF_S
0x1800263c8  xor     edx, edx; pReserved
0x1800263ca  mov     [rsp+78h+pdwNegotiatedVersion], 0
0x1800263d5  lea     r9, [rsp+78h+phClientHandle]; phClientHandle
0x1800263dd  lea     r8, [rsp+78h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x1800263e5  lea     ecx, [rdx+2]; dwClientVersion
0x1800263e8  call    cs:__imp_WlanOpenHandle
0x1800263ee  mov     ebx, eax
0x1800263f0  test    eax, eax
0x1800263f2  jnz     short loc_180026466
0x1800263f4  mov     r9, [rsp+78h+strProfileXml]; strProfileXml
0x1800263f9  lea     rax, [rsp+78h+arg_8]
0x180026401  mov     rcx, [rsp+78h+phClientHandle]; hClientHandle
0x180026409  mov     r8d, esi
0x18002640c  mov     [rsp+78h+pdwReasonCode], rax; pdwReasonCode
0x180026411  xor     r8d, 1
0x180026415  mov     [rsp+78h+pReserved], 0; pReserved
0x18002641e  add     r8d, r8d; dwFlags
0x180026421  mov     [rsp+78h+bOverwrite], 1; bOverwrite
0x180026429  mov     rdx, rdi; pInterfaceGuid
0x18002642c  mov     [rsp+78h+strAllUserProfileSecurity], 0; strAllUserProfileSecurity
0x180026435  call    cs:__imp_WlanSetProfile
0x18002643b  mov     ebx, eax
0x18002643d  test    eax, eax
0x18002643f  jz      short loc_18002649B
0x180026441  mov     rcx, cs:WPP_GLOBAL_Control
0x180026448  cmp     rcx, r15
0x18002644b  jz      short loc_1800264A2
0x18002644d  cmp     byte ptr [rcx+91h], 1
0x180026454  jb      short loc_1800264A2
0x180026456  test    byte ptr [rcx+94h], 1
0x18002645d  jz      short loc_1800264A2
0x18002645f  mov     edx, 19h
0x180026464  jmp     short loc_180026489
0x180026466  mov     rcx, cs:WPP_GLOBAL_Control
0x18002646d  cmp     rcx, r15
0x180026470  jz      short loc_1800264A2
0x180026472  cmp     byte ptr [rcx+91h], 1
0x180026479  jb      short loc_1800264A2
0x18002647b  test    byte ptr [rcx+94h], 1
0x180026482  jz      short loc_1800264A2
0x180026484  mov     edx, 1Ah
0x180026489  mov     rcx, [rcx+88h]
0x180026490  mov     r9d, eax
0x180026493  mov     r8, r12
0x180026496  call    WPP_SF_d
0x18002649b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264a2  mov     rax, [rsp+78h+phClientHandle]
0x1800264aa  test    rax, rax
0x1800264ad  jz      short loc_1800264C1
0x1800264af  xor     edx, edx; pReserved
0x1800264b1  mov     rcx, rax; hClientHandle
0x1800264b4  call    cs:__imp_WlanCloseHandle
0x1800264ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264c1  cmp     rcx, r15
0x1800264c4  jz      short loc_1800264EC
0x1800264c6  cmp     byte ptr [rcx+91h], 4
0x1800264cd  jb      short loc_1800264EC
0x1800264cf  test    byte ptr [rcx+94h], 1
0x1800264d6  jz      short loc_1800264EC
0x1800264d8  mov     rcx, [rcx+88h]
0x1800264df  mov     edx, 1Bh
0x1800264e4  mov     r8, r12
0x1800264e7  call    WPP_SF_
0x1800264ec  test    ebx, ebx
0x1800264ee  jle     short loc_1800264F9
0x1800264f0  movzx   ebx, bx
0x1800264f3  or      ebx, 80070000h
0x1800264f9  mov     rcx, [rsp+78h+strProfileXml]; bstrString
0x1800264fe  call    cs:__imp_SysFreeString
0x180026504  mov     eax, ebx
0x180026506  add     rsp, 50h
0x18002650a  pop     r15
0x18002650c  pop     r12
0x18002650e  pop     rdi
0x18002650f  pop     rsi
0x180026510  pop     rbx
0x180026511  retn
```
