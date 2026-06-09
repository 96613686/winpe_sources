# I_UpdateSymAuthKey(VCHANNEL_DATA *,uchar,uchar,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x180024f14`
- end: `0x18002518e`
- name: `?I_UpdateSymAuthKey@@YAKPEAUVCHANNEL_DATA@@EEAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@1@Z`
- size: `634`
- prototype: `__int64 __fastcall(const struct VCARD_DATA **, unsigned __int8, char, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000acb4`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x18000bc48`
- `0x18000c124`
- `0x18000c198`
- `0x18000fafc`
- `0x18000fcb0`
- `0x18001cd84`
- `0x18001dc80`
- `0x180024378`
- `0x180024f14`
- `0x1800348a0`

## string_xrefs

- `0x180024f53`: `I_UpdateSymAuthKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_UpdateSymAuthKey(
        const struct VCARD_DATA **a1,
        unsigned __int8 a2,
        char a3,
        _QWORD *a4,
        __int64 a5)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // edx
  __int64 v12; // rcx
  int v13; // r8d
  int v14; // r9d
  unsigned int v15; // eax
  int v16; // r9d
  __int64 v17; // rcx
  unsigned int v18; // ebx
  unsigned __int8 v20; // [rsp+30h] [rbp-91h] BYREF
  unsigned int v21; // [rsp+38h] [rbp-89h] BYREF
  int v22; // [rsp+3Ch] [rbp-85h] BYREF
  const struct VCARD_DATA **v23; // [rsp+40h] [rbp-81h] BYREF
  _QWORD *v24; // [rsp+48h] [rbp-79h] BYREF
  _QWORD v25[4]; // [rsp+50h] [rbp-71h] BYREF
  _QWORD v26[10]; // [rsp+70h] [rbp-51h] BYREF
  int v27; // [rsp+C0h] [rbp-1h]
  char v28[24]; // [rsp+D0h] [rbp+Fh] BYREF

  v23 = a1;
  v20 = a2;
  v21 = 0;
  v22 = 0;
  strcpy(v28, "I_UpdateSymAuthKey");
  v25[0] = v28;
  v25[1] = &v22;
  v25[2] = &v21;
  lambda_7b3df7d4f5b3baca8f0a20385e7c3a40_::operator()(v25);
  v22 = 1;
  v24 = v25;
  if ( !v23 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  if ( (unsigned __int8)(v20 + 0x80) > 0x20u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  if ( (unsigned __int8)((a3 & 0xF) - 2) > 3u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  if ( *a4 == a4[1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  memset_0(v26, 0, 0x54u);
  I_KeyMapGetRecord(*v23, v20, (struct KEY_MAP_RECORD *)v26);
  if ( !I_KeyMapIsActive((const struct KEY_MAP_RECORD *)v26) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9);
  if ( v27 != 3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9);
  if ( !I_KeyMapIsActive((const struct KEY_MAP_RECORD *)v26) )
  {
    WppTraceIndent(v12, 2);
    v15 = -2146435024;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          153,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          v14,
          48);
        v15 = -2146435024;
      }
    }
    goto LABEL_23;
  }
  if ( v27 != 3 )
  {
    WppTraceIndent(v12, 2);
    v15 = -2146435068;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        154,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        v16,
        4);
      v15 = -2146435068;
    }
LABEL_23:
    __fastfail(v15);
  }
  v26[0] = off_180038280;
  v26[1] = &v23;
  v26[2] = &v20;
  v26[3] = a5;
  v26[7] = v26;
  LOBYTE(v13) = a3;
  LOBYTE(v11) = v20;
  v21 = I_StoreSymAuthKey((_DWORD)v23, v11, v13, (_DWORD)a4, (__int64)v26);
  if ( v21 )
  {
    WppTraceIndent(v17, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        159,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        v21,
        (__int64)"Unable to store symmetric auth key");
    }
    v18 = v21;
  }
  else
  {
    v18 = 0;
  }
  WppTraceUnwinder__lambda_7b3df7d4f5b3baca8f0a20385e7c3a40____::_WppTraceUnwinder__lambda_7b3df7d4f5b3baca8f0a20385e7c3a40____(&v24);
  return v18;
}

```

## disassembly

```asm
0x180024f14  push    rbp
0x180024f16  push    rbx
0x180024f17  push    rdi
0x180024f18  push    r15
0x180024f1a  lea     rbp, [rsp-37h]
0x180024f1f  sub     rsp, 0F8h
0x180024f26  mov     rax, cs:__security_cookie
0x180024f2d  xor     rax, rsp
0x180024f30  mov     [rbp+4Fh+var_28], rax
0x180024f34  mov     rbx, r9
0x180024f37  mov     dil, r8b
0x180024f3a  mov     [rsp+110h+var_D0], rcx
0x180024f3f  mov     [rsp+110h+var_E0], dl
0x180024f43  mov     [rsp+110h+var_D8], 0
0x180024f4b  mov     [rsp+110h+var_D4], 0
0x180024f53  movups  xmm0, xmmword ptr cs:aIUpdatesymauth; "I_UpdateSymAuthKey"
0x180024f5a  movups  xmmword ptr [rbp+4Fh+var_40], xmm0
0x180024f5e  mov     eax, dword ptr cs:aIUpdatesymauth+0Fh; "Key"
0x180024f64  mov     dword ptr [rbp+4Fh+var_40+0Fh], eax
0x180024f67  lea     rax, [rbp+4Fh+var_40]
0x180024f6b  mov     [rbp+4Fh+var_C0], rax
0x180024f6f  lea     rax, [rsp+110h+var_D4]
0x180024f74  mov     [rbp+4Fh+var_B8], rax
0x180024f78  lea     rax, [rsp+110h+var_D8]
0x180024f7d  mov     [rbp+4Fh+var_B0], rax
0x180024f81  lea     rcx, [rbp+4Fh+var_C0]
0x180024f85  call    _lambda_7b3df7d4f5b3baca8f0a20385e7c3a40___operator__
0x180024f8a  mov     [rsp+110h+var_D4], 1
0x180024f92  lea     rax, [rbp+4Fh+var_C0]
0x180024f96  mov     [rbp+4Fh+var_C8], rax
0x180024f9a  cmp     [rsp+110h+var_D0], 0
0x180024fa0  jnz     short loc_180024FA7
0x180024fa2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024fa7  mov     al, [rsp+110h+var_E0]
0x180024fab  sub     al, 80h
0x180024fad  cmp     al, 20h ; ' '
0x180024faf  jbe     short loc_180024FB6
0x180024fb1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024fb6  mov     al, dil
0x180024fb9  and     al, 0Fh
0x180024fbb  sub     al, 2
0x180024fbd  cmp     al, 3
0x180024fbf  jbe     short loc_180024FC6
0x180024fc1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024fc6  mov     rax, [rbx+8]
0x180024fca  cmp     [rbx], rax
0x180024fcd  jnz     short loc_180024FD4
0x180024fcf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024fd4  xor     edx, edx; Val
0x180024fd6  lea     r8d, [rdx+54h]; Size
0x180024fda  lea     rcx, [rbp+4Fh+var_A0]; void *
0x180024fde  call    memset_0
0x180024fe3  lea     r8, [rbp+4Fh+var_A0]; struct KEY_MAP_RECORD *
0x180024fe7  mov     dl, [rsp+110h+var_E0]; unsigned __int8
0x180024feb  mov     rcx, [rsp+110h+var_D0]
0x180024ff0  mov     rcx, [rcx]; struct VCARD_DATA *
0x180024ff3  call    ?I_KeyMapGetRecord@@YAXPEBUVCARD_DATA@@EPEAUKEY_MAP_RECORD@@@Z; I_KeyMapGetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD *)
0x180024ff8  lea     rcx, [rbp+4Fh+var_A0]; struct KEY_MAP_RECORD *
0x180024ffc  call    ?I_KeyMapIsActive@@YAHPEBUKEY_MAP_RECORD@@@Z; I_KeyMapIsActive(KEY_MAP_RECORD const *)
0x180025001  test    eax, eax
0x180025003  jnz     short loc_18002500A
0x180025005  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002500a  cmp     [rbp+4Fh+var_50], 3
0x18002500e  jz      short loc_180025015
0x180025010  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025015  lea     rcx, [rbp+4Fh+var_A0]; struct KEY_MAP_RECORD *
0x180025019  call    ?I_KeyMapIsActive@@YAHPEBUKEY_MAP_RECORD@@@Z; I_KeyMapIsActive(KEY_MAP_RECORD const *)
0x18002501e  lea     r15, WPP_GLOBAL_Control
0x180025025  test    eax, eax
0x180025027  jnz     short loc_18002506E
0x180025029  lea     edx, [rax+2]
0x18002502c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025031  mov     eax, 80100030h
0x180025036  mov     rcx, cs:WPP_GLOBAL_Control
0x18002503d  cmp     rcx, r15
0x180025040  jz      short loc_1800250B9
0x180025042  test    byte ptr [rcx+1Ch], 1
0x180025046  jz      short loc_1800250B9
0x180025048  cmp     byte ptr [rcx+19h], 1
0x18002504c  jb      short loc_1800250B9
0x18002504e  mov     edx, 99h
0x180025053  mov     dword ptr [rsp+110h+var_F0], eax
0x180025057  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18002505e  mov     rcx, [rcx+10h]
0x180025062  call    WPP_SF_sD
0x180025067  mov     eax, 80100030h
0x18002506c  jmp     short loc_1800250B9
0x18002506e  cmp     [rbp+4Fh+var_50], 3
0x180025072  jz      short loc_1800250BE
0x180025074  mov     edx, 2
0x180025079  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002507e  mov     eax, 80100004h
0x180025083  mov     rcx, cs:WPP_GLOBAL_Control
0x18002508a  cmp     rcx, r15
0x18002508d  jz      short loc_1800250B9
0x18002508f  test    byte ptr [rcx+1Ch], 1
0x180025093  jz      short loc_1800250B9
0x180025095  cmp     byte ptr [rcx+19h], 1
0x180025099  jb      short loc_1800250B9
0x18002509b  mov     edx, 9Ah
0x1800250a0  mov     dword ptr [rsp+110h+var_F0], eax
0x1800250a4  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x1800250ab  mov     rcx, [rcx+10h]
0x1800250af  call    WPP_SF_sD
0x1800250b4  mov     eax, 80100004h
0x1800250b9  mov     rcx, rax
0x1800250bc  int     29h; Win8: RtlFailFast(ecx)
0x1800250be  lea     rax, off_180038280
0x1800250c5  mov     [rbp+4Fh+var_A0], rax
0x1800250c9  lea     rax, [rsp+110h+var_D0]
0x1800250ce  mov     [rbp+4Fh+var_98], rax
0x1800250d2  lea     rax, [rsp+110h+var_E0]
0x1800250d7  mov     [rbp+4Fh+var_90], rax
0x1800250db  mov     rax, [rbp+4Fh+arg_20]
0x1800250df  mov     [rbp+4Fh+var_88], rax
0x1800250e3  lea     rax, [rbp+4Fh+var_A0]
0x1800250e7  mov     [rbp+4Fh+var_68], rax
0x1800250eb  lea     rax, [rbp+4Fh+var_A0]
0x1800250ef  mov     [rsp+110h+var_F0], rax
0x1800250f4  mov     r9, rbx
0x1800250f7  mov     r8b, dil
0x1800250fa  mov     dl, [rsp+110h+var_E0]
0x1800250fe  mov     rcx, [rsp+110h+var_D0]
0x180025103  call    I_StoreSymAuthKey
0x180025108  mov     [rsp+110h+var_D8], eax
0x18002510c  test    eax, eax
0x18002510e  jz      short loc_180025168
0x180025110  mov     edx, 2
0x180025115  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002511a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025121  cmp     rcx, r15
0x180025124  jz      short loc_180025162
0x180025126  test    byte ptr [rcx+1Ch], 1
0x18002512a  jz      short loc_180025162
0x18002512c  cmp     byte ptr [rcx+19h], 2
0x180025130  jb      short loc_180025162
0x180025132  mov     edx, 9Fh
0x180025137  lea     rax, aUnableToStoreS_0; "Unable to store symmetric auth key"
0x18002513e  mov     [rsp+110h+var_E8], rax
0x180025143  mov     eax, [rsp+110h+var_D8]
0x180025147  mov     dword ptr [rsp+110h+var_F0], eax
0x18002514b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025152  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180025159  mov     rcx, [rcx+10h]
0x18002515d  call    WPP_SF_sDs
0x180025162  mov     ebx, [rsp+110h+var_D8]
0x180025166  jmp     short loc_18002516A
0x180025168  xor     ebx, ebx
0x18002516a  lea     rcx, [rbp+4Fh+var_C8]
0x18002516e  call    WppTraceUnwinder__lambda_7b3df7d4f5b3baca8f0a20385e7c3a40_______WppTraceUnwinder__lambda_7b3df7d4f5b3baca8f0a20385e7c3a40____
0x180025173  mov     eax, ebx
0x180025175  mov     rcx, [rbp+4Fh+var_28]
0x180025179  xor     rcx, rsp; StackCookie
0x18002517c  call    __security_check_cookie
0x180025181  add     rsp, 0F8h
0x180025188  pop     r15
0x18002518a  pop     rdi
0x18002518b  pop     rbx
0x18002518c  pop     rbp
0x18002518d  retn
```
