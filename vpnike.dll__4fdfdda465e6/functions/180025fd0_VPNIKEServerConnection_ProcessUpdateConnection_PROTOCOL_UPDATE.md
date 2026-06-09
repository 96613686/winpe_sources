# VPNIKEServerConnection::ProcessUpdateConnection(_PROTOCOL_UPDATE &)

- ea: `0x180025fd0`
- end: `0x180026338`
- name: `?ProcessUpdateConnection@VPNIKEServerConnection@@UEAAXAEAU_PROTOCOL_UPDATE@@@Z`
- size: `872`
- prototype: `void __fastcall(void **this, struct _PROTOCOL_UPDATE *)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007610`
- `0x180007794`
- `0x18001104c`
- `0x1800131c8`
- `0x18002422c`
- `0x180025fd0`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## string_xrefs

- `0x180026155`: `ProcessUpdateConnectionParameters failed: %d.`
- `0x180026223`: `SendMobikeUpdate failed: %d`
- `0x1800260ce`: `VPNIKEServerConnection::ProcessUpdateConnection`

## pseudocode

```c
void __fastcall VPNIKEServerConnection::ProcessUpdateConnection(void **this, struct _PROTOCOL_UPDATE *a2)
{
  unsigned int v4; // edi
  char v5; // al
  _DWORD *v6; // rax
  void *v7; // rdx
  __int128 *v8; // r9
  _DWORD *v9; // rax
  _DWORD *v10; // rax
  void *v11; // rdx
  __int128 *v12; // r9
  unsigned int updated; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-CCh] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v16; // [rsp+3Ch] [rbp-C4h]
  __int128 v17; // [rsp+4Ch] [rbp-B4h]
  int v18; // [rsp+5Ch] [rbp-A4h]
  __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v20; // [rsp+68h] [rbp-98h]
  __int128 v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  int v23; // [rsp+90h] [rbp-70h]
  int v24; // [rsp+94h] [rbp-6Ch]
  __int128 v25; // [rsp+98h] [rbp-68h] BYREF
  int v26; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v27; // [rsp+ACh] [rbp-54h]
  __int128 v28; // [rsp+BCh] [rbp-44h]
  int v29; // [rsp+CCh] [rbp-34h]
  int v30; // [rsp+D0h] [rbp-30h] BYREF
  char v31[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
  }
  updated = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v25 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v4 = -1;
  v23 = -1;
  v24 = 0;
  v5 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v19,
      L"VPNIKEServerConnection::ProcessUpdateConnection",
      &updated,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      this[14]);
    v5 = byte_1800AA941;
  }
  if ( *((_BYTE *)this + 264) && *((_BYTE *)this + 265) )
  {
    updated = VPNIKEConnection::ProcessUpdateConnectionParameters(
                (VPNIKEConnection *)this,
                a2,
                (struct _PROTOCOL_ENDPOINT_RESULT *)&v15,
                &v14);
    if ( updated )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_35;
      LOWORD(v30) = 0;
      LOWORD(v26) = 0;
      v6 = this[14];
      if ( v6 && *((_QWORD *)v6 + 2) )
        v4 = v6[4];
      ConvertPortNoToString(&v26, v4);
      FormatRRASErrorString(&v30, L"ProcessUpdateConnectionParameters failed: %d.", updated);
    }
    else
    {
      updated = (**(__int64 (__fastcall ***)(void *, void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, unsigned int), int *))this[26])(
                  this[26],
                  VPNIKEServerConnection::IkeUpdateMobikeCompleteCallback,
                  &v15);
      if ( !updated )
      {
        VPNIKEConnection::UpdateConnectionState((VPNIKEConnection *)this, 0x40u);
        goto LABEL_35;
      }
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_35;
      LOWORD(v30) = 0;
      LOWORD(v26) = 0;
      v9 = this[14];
      if ( v9 && *((_QWORD *)v9 + 2) )
        v4 = v9[4];
      ConvertPortNoToString(&v26, v4);
      FormatRRASErrorString(&v30, L"SendMobikeUpdate failed: %d", updated);
    }
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v7 = this[14];
      LODWORD(v8) = (_DWORD)v7 + 2120;
      if ( !v7 )
        v8 = &v25;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)&v30,
        (_DWORD)v8,
        ((unsigned __int64)v7 + 2686) & -(__int64)(this[14] != 0),
        (__int64)&v26);
    }
  }
  else
  {
    if ( (v5 & 4) != 0 )
    {
      LOWORD(v26) = 0;
      v10 = this[14];
      if ( v10 && *((_QWORD *)v10 + 2) )
        v4 = v10[4];
      ConvertPortNoToString(&v26, v4);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v11 = this[14];
        LODWORD(v12) = (_DWORD)v11 + 2120;
        if ( !v11 )
          v12 = &v25;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Mobike is disabled either on initiator/responder. Hence this request is invalid.",
          (_DWORD)v12,
          ((unsigned __int64)v11 + 2686) & -(__int64)(v11 != 0),
          (__int64)&v26);
      }
    }
    updated = 843;
  }
LABEL_35:
  if ( updated )
    VPNIKEServerConnection::NotifyUpdateConnectionStatus((VPNIKEServerConnection *)this, updated);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
}

```

## disassembly

```asm
0x180025fd0  mov     [rsp-8+arg_10], rbx
0x180025fd5  mov     [rsp-8+arg_18], rsi
0x180025fda  push    rbp
0x180025fdb  push    rdi
0x180025fdc  push    r15
0x180025fde  lea     rbp, [rsp-7E0h]
0x180025fe6  sub     rsp, 8E0h
0x180025fed  mov     rax, cs:__security_cookie
0x180025ff4  xor     rax, rsp
0x180025ff7  mov     [rbp+7F0h+var_20], rax
0x180025ffe  mov     rsi, rdx
0x180026001  mov     rbx, rcx
0x180026004  lea     r15, WPP_GLOBAL_Control
0x18002600b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026012  cmp     rcx, r15
0x180026015  jz      short loc_180026038
0x180026017  test    byte ptr [rcx+1Ch], 1
0x18002601b  jz      short loc_180026038
0x18002601d  cmp     byte ptr [rcx+19h], 6
0x180026021  jb      short loc_180026038
0x180026023  mov     edx, 13h
0x180026028  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x18002602f  mov     rcx, [rcx+10h]
0x180026033  call    WPP_SF_
0x180026038  mov     [rsp+8F0h+var_8C0], 0
0x180026040  mov     [rsp+8F0h+var_8BC], 0
0x180026048  mov     [rsp+8F0h+var_8B8], 0
0x180026050  xorps   xmm0, xmm0
0x180026053  xor     eax, eax
0x180026055  movups  [rsp+8F0h+var_8B4], xmm0
0x18002605a  movups  [rsp+8F0h+var_8A4], xmm0
0x18002605f  mov     [rsp+8F0h+var_894], eax
0x180026063  mov     [rbp+7F0h+var_820], eax
0x180026066  xor     edx, edx; Val
0x180026068  mov     r8d, 7FCh; Size
0x18002606e  lea     rcx, [rbp+7F0h+var_81C]; void *
0x180026072  call    memset_0
0x180026077  xor     eax, eax
0x180026079  mov     [rbp+7F0h+var_848], eax
0x18002607c  xorps   xmm0, xmm0
0x18002607f  movups  [rbp+7F0h+var_844], xmm0
0x180026083  movups  [rbp+7F0h+var_834], xmm0
0x180026087  mov     [rbp+7F0h+var_824], eax
0x18002608a  movups  [rbp+7F0h+var_858], xmm0
0x18002608e  xorps   xmm1, xmm1
0x180026091  movdqu  [rsp+8F0h+var_888], xmm1
0x180026097  mov     [rsp+8F0h+var_890], rax
0x18002609c  movdqu  [rsp+8F0h+var_878], xmm0
0x1800260a2  mov     [rbp+7F0h+var_868], rax
0x1800260a6  or      edi, 0FFFFFFFFh
0x1800260a9  mov     [rbp+7F0h+var_860], edi
0x1800260ac  mov     [rbp+7F0h+var_85C], eax
0x1800260af  mov     al, cs:byte_1800AA941
0x1800260b5  test    al, 8
0x1800260b7  jz      short loc_1800260E5
0x1800260b9  mov     rax, [rbx+70h]
0x1800260bd  mov     [rsp+8F0h+var_8D0], rax; void *
0x1800260c2  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800260c9  lea     r8, [rsp+8F0h+var_8C0]; unsigned int *
0x1800260ce  lea     rdx, aVpnikeserverco_21; "VPNIKEServerConnection::ProcessUpdateCo"...
0x1800260d5  lea     rcx, [rsp+8F0h+var_890]; this
0x1800260da  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x1800260df  mov     al, cs:byte_1800AA941
0x1800260e5  cmp     byte ptr [rbx+108h], 0
0x1800260ec  jz      loc_180026241
0x1800260f2  cmp     byte ptr [rbx+109h], 0
0x1800260f9  jz      loc_180026241
0x1800260ff  lea     r9, [rsp+8F0h+var_8BC]; unsigned int *
0x180026104  lea     r8, [rsp+8F0h+var_8B8]; struct _PROTOCOL_ENDPOINT_RESULT *
0x180026109  mov     rdx, rsi; struct _PROTOCOL_UPDATE *
0x18002610c  mov     rcx, rbx; this
0x18002610f  call    ?ProcessUpdateConnectionParameters@VPNIKEConnection@@IEAAKAEAU_PROTOCOL_UPDATE@@AEAU_PROTOCOL_ENDPOINT_RESULT@@AEAK@Z; VPNIKEConnection::ProcessUpdateConnectionParameters(_PROTOCOL_UPDATE &,_PROTOCOL_ENDPOINT_RESULT &,ulong &)
0x180026114  mov     [rsp+8F0h+var_8C0], eax
0x180026118  test    eax, eax
0x18002611a  jz      loc_1800261C8
0x180026120  test    cs:byte_1800AA941, 4
0x180026127  jz      loc_1800262C9
0x18002612d  xor     eax, eax
0x18002612f  mov     word ptr [rbp+7F0h+var_820], ax
0x180026133  mov     word ptr [rbp+7F0h+var_848], ax
0x180026137  mov     rax, [rbx+70h]
0x18002613b  test    rax, rax
0x18002613e  jz      short loc_18002614A
0x180026140  cmp     qword ptr [rax+10h], 0
0x180026145  jz      short loc_18002614A
0x180026147  mov     edi, [rax+10h]
0x18002614a  mov     edx, edi
0x18002614c  lea     rcx, [rbp+7F0h+var_848]
0x180026150  call    ConvertPortNoToString
0x180026155  lea     rdx, aProcessupdatec; "ProcessUpdateConnectionParameters faile"...
0x18002615c  mov     r8d, [rsp+8F0h+var_8C0]
0x180026161  lea     rcx, [rbp+7F0h+var_820]
0x180026165  call    FormatRRASErrorString
0x18002616a  test    cs:byte_1800AA941, 4
0x180026171  jz      loc_1800262C9
0x180026177  mov     rdx, [rbx+70h]
0x18002617b  mov     rax, rdx
0x18002617e  neg     rax
0x180026181  lea     rcx, [rdx+0A7Eh]
0x180026188  sbb     r8, r8
0x18002618b  and     r8, rcx
0x18002618e  lea     r9, [rdx+848h]
0x180026195  test    rdx, rdx
0x180026198  jnz     short loc_18002619E
0x18002619a  lea     r9, [rbp+7F0h+var_858]
0x18002619e  lea     rax, [rbp+7F0h+var_848]
0x1800261a2  mov     [rsp+8F0h+var_8C8], rax
0x1800261a7  mov     [rsp+8F0h+var_8D0], r8
0x1800261ac  lea     r8, [rbp+7F0h+var_820]
0x1800261b0  lea     rdx, RasVpnIkeParamTraceError
0x1800261b7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800261be  call    McTemplateU0zjzz_EventWriteTransfer
0x1800261c3  jmp     loc_1800262C9
0x1800261c8  mov     rcx, [rbx+0D0h]
0x1800261cf  mov     rax, [rcx]
0x1800261d2  lea     r8, [rsp+8F0h+var_8B8]
0x1800261d7  lea     rdx, ?IkeUpdateMobikeCompleteCallback@VPNIKEServerConnection@@KAXPEAXK@Z; VPNIKEServerConnection::IkeUpdateMobikeCompleteCallback(void *,ulong)
0x1800261de  mov     rax, [rax]
0x1800261e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261e6  mov     [rsp+8F0h+var_8C0], eax
0x1800261ea  test    eax, eax
0x1800261ec  jz      short loc_18002622F
0x1800261ee  test    cs:byte_1800AA941, 4
0x1800261f5  jz      loc_1800262C9
0x1800261fb  xor     eax, eax
0x1800261fd  mov     word ptr [rbp+7F0h+var_820], ax
0x180026201  mov     word ptr [rbp+7F0h+var_848], ax
0x180026205  mov     rax, [rbx+70h]
0x180026209  test    rax, rax
0x18002620c  jz      short loc_180026218
0x18002620e  cmp     qword ptr [rax+10h], 0
0x180026213  jz      short loc_180026218
0x180026215  mov     edi, [rax+10h]
0x180026218  mov     edx, edi
0x18002621a  lea     rcx, [rbp+7F0h+var_848]
0x18002621e  call    ConvertPortNoToString
0x180026223  lea     rdx, aSendmobikeupda; "SendMobikeUpdate failed: %d"
0x18002622a  jmp     loc_18002615C
0x18002622f  mov     edx, 40h ; '@'; unsigned int
0x180026234  mov     rcx, rbx; this
0x180026237  call    ?UpdateConnectionState@VPNIKEConnection@@IEAAXK@Z; VPNIKEConnection::UpdateConnectionState(ulong)
0x18002623c  jmp     loc_1800262C9
0x180026241  test    al, 4
0x180026243  jz      short loc_1800262C1
0x180026245  xor     eax, eax
0x180026247  mov     word ptr [rbp+7F0h+var_848], ax
0x18002624b  mov     rax, [rbx+70h]
0x18002624f  test    rax, rax
0x180026252  jz      short loc_18002625E
0x180026254  cmp     qword ptr [rax+10h], 0
0x180026259  jz      short loc_18002625E
0x18002625b  mov     edi, [rax+10h]
0x18002625e  mov     edx, edi
0x180026260  lea     rcx, [rbp+7F0h+var_848]
0x180026264  call    ConvertPortNoToString
0x180026269  test    cs:byte_1800AA941, 4
0x180026270  jz      short loc_1800262C1
0x180026272  mov     rdx, [rbx+70h]
0x180026276  mov     rax, rdx
0x180026279  lea     rcx, [rdx+0A7Eh]
0x180026280  neg     rax
0x180026283  sbb     r8, r8
0x180026286  and     r8, rcx
0x180026289  test    rdx, rdx
0x18002628c  lea     r9, [rdx+848h]
0x180026293  jnz     short loc_180026299
0x180026295  lea     r9, [rbp+7F0h+var_858]
0x180026299  lea     rax, [rbp+7F0h+var_848]
0x18002629d  mov     [rsp+8F0h+var_8C8], rax
0x1800262a2  mov     [rsp+8F0h+var_8D0], r8
0x1800262a7  lea     r8, aMobikeIsDisabl; "Mobike is disabled either on initiator/"...
0x1800262ae  lea     rdx, RasVpnIkeParamTraceError
0x1800262b5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800262bc  call    McTemplateU0zjzz_EventWriteTransfer
0x1800262c1  mov     [rsp+8F0h+var_8C0], 34Bh
0x1800262c9  mov     edx, [rsp+8F0h+var_8C0]; unsigned int
0x1800262cd  test    edx, edx
0x1800262cf  jz      short loc_1800262D9
0x1800262d1  mov     rcx, rbx; this
0x1800262d4  call    ?NotifyUpdateConnectionStatus@VPNIKEServerConnection@@IEAAXK@Z; VPNIKEServerConnection::NotifyUpdateConnectionStatus(ulong)
0x1800262d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262e0  cmp     rcx, r15
0x1800262e3  jz      short loc_180026307
0x1800262e5  test    byte ptr [rcx+1Ch], 1
0x1800262e9  jz      short loc_180026307
0x1800262eb  cmp     byte ptr [rcx+19h], 6
0x1800262ef  jb      short loc_180026307
0x1800262f1  mov     edx, 14h
0x1800262f6  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x1800262fd  mov     rcx, [rcx+10h]
0x180026301  call    WPP_SF_
0x180026306  nop
0x180026307  lea     rcx, [rsp+8F0h+var_890]; this
0x18002630c  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180026311  mov     rcx, [rbp+7F0h+var_20]
0x180026318  xor     rcx, rsp; StackCookie
0x18002631b  call    __security_check_cookie
0x180026320  lea     r11, [rsp+8F0h+var_10]
0x180026328  mov     rbx, [r11+30h]
0x18002632c  mov     rsi, [r11+38h]
0x180026330  mov     rsp, r11
0x180026333  pop     r15
0x180026335  pop     rdi
0x180026336  pop     rbp
0x180026337  retn
```
