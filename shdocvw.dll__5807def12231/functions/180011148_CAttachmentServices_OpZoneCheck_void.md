# CAttachmentServices::_OpZoneCheck(void)

- ea: `0x180011148`
- end: `0x18001134d`
- name: `?_OpZoneCheck@CAttachmentServices@@AEAAXXZ`
- size: `517`
- prototype: `void __fastcall(CAttachmentServices *__hidden this)`
- caller_count: `5`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ce10`
- `0x18000d110`
- `0x18000f420`
- `0x1800113a0`
- `0x18001143c`

## callees

- `0x180002d10`
- `0x180003080`
- `0x180003f30`
- `0x180004190`
- `0x180006844`
- `0x180008320`
- `0x18000f1e0`
- `0x18000f3b0`
- `0x180010bf4`
- `0x180011148`
- `0x1800115bc`

## import_xrefs

- `SHLWAPI!__imp_SKGetValueW` at `0x1800112fe`
- `SHLWAPI!__imp_SKGetValueW` at `0x1800112fe`

## pseudocode

```c
void __fastcall CAttachmentServices::_OpZoneCheck(CAttachmentServices *this)
{
  __int64 v2; // rcx
  const unsigned __int16 *v3; // rdx
  const unsigned __int16 **v4; // rdi
  unsigned int v5; // r10d
  unsigned int v6; // r10d
  unsigned int v7; // r11d
  __int64 v8; // rax
  unsigned int v9; // r9d
  int v10; // r11d
  bool v11; // zf
  int v12; // ecx
  int v13; // eax
  __int64 v14; // rdx
  const unsigned __int16 *Type; // rdi
  int v16; // r8d
  __int64 v17; // rcx
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v19; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v21; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v23[3]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 v24[264]; // [rsp+50h] [rbp-B0h] BYREF

  v23[0] = 0;
  if ( (unsigned int)CAttachmentServices::PushOp(this, 8, v23) )
  {
    v3 = *(const unsigned __int16 **)(v2 + 48);
    v4 = (const unsigned __int16 **)(v2 + 56);
    v18 = 3;
    if ( v3 || *v4 )
    {
      v6 = 0;
      v7 = 0;
      v19 = 0;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      if ( v3 )
      {
        CAttachmentServices::_ZoneCheck((CAttachmentServices *)v2, v3, *(_DWORD *)(v2 + 88), &v19);
        CAttachmentServices::MapUrlToZone(this, *((const unsigned __int16 **)this + 6), &v21);
        v6 = v19;
        v7 = v20;
      }
      if ( *v4 )
      {
        CAttachmentServices::_ZoneCheck(this, *v4, *((_DWORD *)this + 22), &v20);
        CAttachmentServices::MapUrlToZone(this, *v4, &v22);
        v6 = v19;
        v7 = v20;
      }
      if ( v6 <= v7 )
        v18 = v7;
      else
        v18 = v6;
      _GetZoneTrust(v21);
      LODWORD(v8) = _GetZoneTrust(v22);
      if ( v9 < (unsigned int)v8 )
        v8 = v9;
      v11 = *((_DWORD *)this + 2) == 0;
      v12 = *((_DWORD *)qword_18002CB70 + v8);
      *((_DWORD *)this + 23) = v12;
      if ( !v11 )
      {
        v13 = 1;
        *((_DWORD *)this + 4) = 1;
        if ( !v12 || !v10 )
          v13 = 0;
        *((_DWORD *)this + 5) = v13;
      }
    }
    else
    {
      CAttachmentServices::_ZoneCheck((CAttachmentServices *)v2, 0, *(_DWORD *)(v2 + 88), &v18);
      v5 = v18;
      *((_DWORD *)this + 23) = 4;
    }
    if ( !v5 )
      goto LABEL_25;
    if ( v5 != 1 )
    {
      v14 = 2148270094LL;
LABEL_27:
      CAttachmentServices::ReportResult(this, v14, 2);
      CAttachmentServices::PopOp(v17, v23[0]);
      return;
    }
    if ( *((_DWORD *)this + 22) != 6150 )
    {
      Type = CAttachmentServices::_GetType(this);
      if ( _ClientKey((const struct _GUID *)((char *)this + 72), v24, v16) )
      {
        if ( (int)SKGetValueW(17, v24, Type) >= 0 )
LABEL_25:
          CAttachmentServices::OpSkip(this);
      }
    }
    v14 = 0;
    goto LABEL_27;
  }
}

```

## disassembly

```asm
0x180011148  mov     [rsp-8+arg_8], rbx
0x18001114d  mov     [rsp-8+arg_10], rdi
0x180011152  push    rbp
0x180011153  lea     rbp, [rsp-170h]
0x18001115b  sub     rsp, 270h
0x180011162  mov     rax, cs:__security_cookie
0x180011169  xor     rax, rsp
0x18001116c  mov     [rbp+170h+var_10], rax
0x180011173  lea     r8, [rsp+270h+var_22C]
0x180011178  mov     [rsp+270h+var_22C], 0
0x180011180  mov     edx, 8
0x180011185  mov     rbx, rcx
0x180011188  call    ?PushOp@CAttachmentServices@@AEAAHW4ATTACHMENT_OP@@PEAW42@@Z; CAttachmentServices::PushOp(ATTACHMENT_OP,ATTACHMENT_OP *)
0x18001118d  test    eax, eax
0x18001118f  jz      loc_180011329
0x180011195  mov     rdx, [rcx+30h]; unsigned __int16 *
0x180011199  lea     rdi, [rcx+38h]
0x18001119d  mov     [rsp+270h+var_240], 3
0x1800111a5  test    rdx, rdx
0x1800111a8  jnz     short loc_1800111CE
0x1800111aa  cmp     [rdi], rdx
0x1800111ad  jnz     short loc_1800111CE
0x1800111af  mov     r8d, [rcx+58h]; unsigned int
0x1800111b3  lea     r9, [rsp+270h+var_240]; unsigned int *
0x1800111b8  call    ?_ZoneCheck@CAttachmentServices@@AEAAJPEBGKPEAK@Z; CAttachmentServices::_ZoneCheck(ushort const *,ulong,ulong *)
0x1800111bd  mov     r10d, [rsp+270h+var_240]
0x1800111c2  mov     dword ptr [rbx+5Ch], 4
0x1800111c9  jmp     loc_1800112A5
0x1800111ce  xor     r10d, r10d
0x1800111d1  xor     r11d, r11d
0x1800111d4  mov     [rsp+270h+var_23C], r10d
0x1800111d9  mov     [rsp+270h+var_238], r11d
0x1800111de  mov     [rsp+270h+var_234], r10d
0x1800111e3  mov     [rsp+270h+var_230], r10d
0x1800111e8  test    rdx, rdx
0x1800111eb  jz      short loc_180011216
0x1800111ed  mov     r8d, [rcx+58h]; unsigned int
0x1800111f1  lea     r9, [rsp+270h+var_23C]; unsigned int *
0x1800111f6  call    ?_ZoneCheck@CAttachmentServices@@AEAAJPEBGKPEAK@Z; CAttachmentServices::_ZoneCheck(ushort const *,ulong,ulong *)
0x1800111fb  mov     rdx, [rbx+30h]; unsigned __int16 *
0x1800111ff  lea     r8, [rsp+270h+var_234]; unsigned int *
0x180011204  mov     rcx, rbx; this
0x180011207  call    ?MapUrlToZone@CAttachmentServices@@AEAAXPEBGPEAK@Z; CAttachmentServices::MapUrlToZone(ushort const *,ulong *)
0x18001120c  mov     r10d, [rsp+270h+var_23C]
0x180011211  mov     r11d, [rsp+270h+var_238]
0x180011216  mov     rdx, [rdi]; unsigned __int16 *
0x180011219  test    rdx, rdx
0x18001121c  jz      short loc_180011249
0x18001121e  mov     r8d, [rbx+58h]; unsigned int
0x180011222  lea     r9, [rsp+270h+var_238]; unsigned int *
0x180011227  mov     rcx, rbx; this
0x18001122a  call    ?_ZoneCheck@CAttachmentServices@@AEAAJPEBGKPEAK@Z; CAttachmentServices::_ZoneCheck(ushort const *,ulong,ulong *)
0x18001122f  mov     rdx, [rdi]; unsigned __int16 *
0x180011232  lea     r8, [rsp+270h+var_230]; unsigned int *
0x180011237  mov     rcx, rbx; this
0x18001123a  call    ?MapUrlToZone@CAttachmentServices@@AEAAXPEBGPEAK@Z; CAttachmentServices::MapUrlToZone(ushort const *,ulong *)
0x18001123f  mov     r10d, [rsp+270h+var_23C]
0x180011244  mov     r11d, [rsp+270h+var_238]
0x180011249  cmp     r10d, r11d
0x18001124c  jbe     short loc_180011258
0x18001124e  mov     [rsp+270h+var_240], r10d
0x180011253  mov     r11d, r10d
0x180011256  jmp     short loc_180011260
0x180011258  mov     r10d, r11d
0x18001125b  mov     [rsp+270h+var_240], r11d
0x180011260  mov     ecx, [rsp+270h+var_234]; unsigned int
0x180011264  call    ?_GetZoneTrust@@YAIK@Z; _GetZoneTrust(ulong)
0x180011269  mov     ecx, [rsp+270h+var_230]; unsigned int
0x18001126d  mov     r9d, eax
0x180011270  call    ?_GetZoneTrust@@YAIK@Z; _GetZoneTrust(ulong)
0x180011275  cmp     r9d, eax
0x180011278  lea     rcx, qword_18002CB70
0x18001127f  cmovb   eax, r9d
0x180011283  cmp     dword ptr [rbx+8], 0
0x180011287  mov     ecx, [rcx+rax*4]
0x18001128a  mov     [rbx+5Ch], ecx
0x18001128d  jz      short loc_1800112A5
0x18001128f  mov     eax, 1
0x180011294  mov     [rbx+10h], eax
0x180011297  test    ecx, ecx
0x180011299  jz      short loc_1800112A0
0x18001129b  test    r11d, r11d
0x18001129e  jnz     short loc_1800112A2
0x1800112a0  xor     eax, eax
0x1800112a2  mov     [rbx+14h], eax
0x1800112a5  test    r10d, r10d
0x1800112a8  jz      short loc_180011308
0x1800112aa  sub     r10d, 1
0x1800112ae  jz      short loc_1800112B7
0x1800112b0  mov     edx, 800C000Eh
0x1800112b5  jmp     short loc_180011312
0x1800112b7  cmp     dword ptr [rbx+58h], 1806h
0x1800112be  jz      short loc_180011310
0x1800112c0  mov     rcx, rbx; this
0x1800112c3  call    ?_GetType@CAttachmentServices@@AEAAPEBGXZ; CAttachmentServices::_GetType(void)
0x1800112c8  lea     rcx, [rbx+48h]; struct _GUID *
0x1800112cc  mov     rdi, rax
0x1800112cf  lea     rdx, [rsp+270h+var_220]; unsigned __int16 *
0x1800112d4  call    ?_ClientKey@@YAHAEBU_GUID@@PEAGH@Z; _ClientKey(_GUID const &,ushort *,int)
0x1800112d9  test    eax, eax
0x1800112db  jz      short loc_180011310
0x1800112dd  xor     r9d, r9d
0x1800112e0  mov     [rsp+270h+var_248], 0
0x1800112e9  mov     r8, rdi
0x1800112ec  mov     [rsp+270h+var_250], 0
0x1800112f5  lea     rdx, [rsp+270h+var_220]
0x1800112fa  lea     ecx, [r9+11h]
0x1800112fe  call    cs:__imp_SKGetValueW
0x180011304  test    eax, eax
0x180011306  js      short loc_180011310
0x180011308  mov     rcx, rbx
0x18001130b  call    ?OpSkip@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::OpSkip(ATTACHMENT_OP)
0x180011310  xor     edx, edx
0x180011312  mov     r8d, 2
0x180011318  mov     rcx, rbx
0x18001131b  call    ?ReportResult@CAttachmentServices@@AEAAHJW4OP_RESULT@1@@Z; CAttachmentServices::ReportResult(long,CAttachmentServices::OP_RESULT)
0x180011320  mov     edx, [rsp+270h+var_22C]
0x180011324  call    ?PopOp@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::PopOp(ATTACHMENT_OP)
0x180011329  mov     rcx, [rbp+170h+var_10]
0x180011330  xor     rcx, rsp; StackCookie
0x180011333  call    __security_check_cookie
0x180011338  lea     r11, [rsp+270h+var_s0]
0x180011340  mov     rbx, [r11+18h]
0x180011344  mov     rdi, [r11+20h]
0x180011348  mov     rsp, r11
0x18001134b  pop     rbp
0x18001134c  retn
```
