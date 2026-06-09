# CreateWindowsEk(Tpm20Context *,TpmStack *,Event *)

- ea: `0x14002d050`
- end: `0x14002d8ac`
- name: `?CreateWindowsEk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVEvent@@@Z`
- size: `2140`
- prototype: `__int64 __fastcall(struct Tpm20Context *, struct TpmStack *, struct Event *)`
- caller_count: `2`
- callee_count: `25`
- tags: `registry_config, installer_update`

## callers

- `0x14001d224`
- `0x14002f4a0`

## callees

- `0x140001374`
- `0x140001424`
- `0x1400014a0`
- `0x1400078b8`
- `0x140008758`
- `0x140009fc8`
- `0x140016ac4`
- `0x140019dd8`
- `0x140029eec`
- `0x14002a254`
- `0x14002a350`
- `0x14002a410`
- `0x14002a528`
- `0x14002a6c4`
- `0x14002d004`
- `0x14002d050`
- `0x14002df64`
- `0x14002e118`
- `0x14002e488`
- `0x14002f0b0`
- `0x14002f5f8`
- `0x140039740`
- `0x140045190`
- `0x140045430`
- `0x1400454a0`

## string_xrefs

- `0x14002d1a6`: `Persistent EK already present; EK creation not needed.`

## pseudocode

```c
__int64 __fastcall CreateWindowsEk(struct Tpm20Context *a1, struct TpmStack *a2, struct Event *a3)
{
  unsigned int v3; // ebx
  unsigned __int8 *v7; // r14
  unsigned __int8 *v8; // r12
  signed int PublicEk; // edi
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  char v13; // r14
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  const struct TPM2B_BUFFER *v16; // r14
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v18; // rdx
  int v19; // eax
  unsigned __int8 *v20; // rax
  int v21; // eax
  int v22; // ecx
  unsigned __int8 *v23; // rax
  int v24; // eax
  int v25; // ecx
  unsigned __int8 *v26; // rax
  unsigned __int8 *v27; // rax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  bool v34; // cf
  int v35; // ecx
  int v36; // r8d
  unsigned int v37; // r9d
  unsigned __int8 *Src; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *Srca; // [rsp+20h] [rbp-E0h]
  struct EkCertNvIndex *v41; // [rsp+30h] [rbp-D0h]
  unsigned __int8 *v42; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v43; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v44; // [rsp+4Ch] [rbp-B4h] BYREF
  int v45; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v47; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v48; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v49; // [rsp+64h] [rbp-9Ch] BYREF
  struct TPM2B_BUFFER *v50; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v51[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v52; // [rsp+78h] [rbp-88h]
  unsigned __int8 *v53; // [rsp+80h] [rbp-80h]
  __int16 v54; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v55; // [rsp+90h] [rbp-70h]
  __int16 v56; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 *v57; // [rsp+A0h] [rbp-60h]
  __int16 v58; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v59; // [rsp+B0h] [rbp-50h]
  __int16 v60; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v61; // [rsp+C0h] [rbp-40h]
  unsigned __int8 v62[16]; // [rsp+C8h] [rbp-38h] BYREF
  int v63; // [rsp+D8h] [rbp-28h]
  unsigned __int8 v64[16]; // [rsp+E0h] [rbp-20h] BYREF
  int v65; // [rsp+F0h] [rbp-10h]
  unsigned __int16 v66[8]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v67; // [rsp+108h] [rbp+8h]
  _BYTE v68[26]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 retaddr; // [rsp+178h] [rbp+78h]

  v3 = 0;
  v53 = 0;
  v43 = 0;
  v42 = 0;
  v44 = 0;
  v48 = 0;
  v7 = 0;
  v60 = 0;
  v8 = 0;
  v61 = 0;
  TPM2B_BUFFER::Clear((TPM2B_BUFFER *)&v60, 1u);
  v58 = 0;
  v59 = 0;
  TPM2B_BUFFER::Clear((TPM2B_BUFFER *)&v58, 1u);
  v56 = 0;
  v57 = 0;
  memset(v68, 0, sizeof(v68));
  v65 = 0;
  *(_OWORD *)v66 = 0;
  v67 = 0;
  *(_OWORD *)v64 = 0;
  TPM2B_BUFFER::Clear((TPM2B_BUFFER *)&v56, 1u);
  v54 = 0;
  v55 = 0;
  v63 = 0;
  *(_OWORD *)v62 = 0;
  TPM2B_BUFFER::Clear((TPM2B_BUFFER *)&v54, 1u);
  *(_QWORD *)v51 = 0;
  v52 = 0;
  LOBYTE(v45) = 0;
  LOBYTE(v46) = 0;
  v49 = 0;
  PublicEk = CheckForCancellation(a3);
  if ( PublicEk < 0 )
    goto LABEL_84;
  PublicEk = Tpm20ReadPublicEk(a1, a2, 0, 0);
  if ( PublicEk >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
    if ( (unsigned int)dword_1400470A0 > 5 && (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
    {
      v42 = (unsigned __int8 *)0x1000000;
      v50 = (struct TPM2B_BUFFER *)L"Persistent EK already present; EK creation not needed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v10,
        (unsigned int)byte_140041DAB,
        v11,
        v12,
        (__int64)&v42,
        (__int64)&v50);
    }
    goto LABEL_84;
  }
  PublicEk = CheckForCancellation(a3);
  if ( PublicEk < 0 )
    goto LABEL_84;
  v47 = 0;
  PublicEk = Tpm20GetPermanent(a1, a2, &v47);
  if ( PublicEk < 0 )
    goto LABEL_84;
  v13 = v47;
  v50 = 0;
  if ( (v47 & 2) != 0 )
  {
    PublicEk = TpmRegistry::QueryValue(4, L"EndorsementAuth", 1, v66, 58, 0);
    if ( PublicEk < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_17;
      v15 = 18;
LABEL_16:
      WPP_SF_(v14->AttachedDevice, v15, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
LABEL_17:
      v7 = 0;
      goto LABEL_84;
    }
    v47 = 20;
    PublicEk = TpmBase64Decode(v66, v62, &v47);
    if ( PublicEk < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_17;
      v15 = 19;
      goto LABEL_16;
    }
    v54 = v47;
    v55 = v62;
    v50 = (struct TPM2B_BUFFER *)&v54;
  }
  if ( (v13 & 1) != 0 )
  {
    PublicEk = TpmRegistry::QueryValue(3, L"StorageOwnerAuth", 1, v66, 58, 0);
    if ( PublicEk < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_17;
      v15 = 20;
      goto LABEL_16;
    }
    v47 = 20;
    PublicEk = TpmBase64Decode(v66, v64, &v47);
    if ( PublicEk < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_17;
      v15 = 21;
      goto LABEL_16;
    }
    v16 = (const struct TPM2B_BUFFER *)&v56;
    v56 = v47;
    v57 = v64;
  }
  else
  {
    v16 = 0;
  }
  PublicEk = CheckForCancellation(a3);
  if ( PublicEk < 0 )
    goto LABEL_83;
  IsEnabledDeviceUsageNoInline = Feature_Prefer2kEkOver3k__private_IsEnabledDeviceUsageNoInline();
  v18 = *((_QWORD *)a2 + 5);
  v19 = IsEnabledDeviceUsageNoInline ? GetEkNvIndex2kFirst(v51, v18, a3) : GetEkNvIndex(v51, v18, a3);
  PublicEk = v19;
  if ( v19 < 0 )
    goto LABEL_83;
  PublicEk = CheckForCancellation(a3);
  if ( PublicEk < 0 )
    goto LABEL_83;
  if ( (int)Tpm20NVReadPublic(a1, a2, v51[1], &v44, (struct TPM2B_BUFFER *)Src) < 0 || !v44 )
    goto LABEL_49;
  PublicEk = CheckForCancellation(a3);
  if ( PublicEk < 0 )
  {
LABEL_83:
    v7 = 0;
    goto LABEL_84;
  }
  v20 = TpmAlloc(1, v44, retaddr);
  v42 = v20;
  if ( !v20 )
  {
    PublicEk = -1073741670;
    v7 = 0;
    goto LABEL_84;
  }
  PublicEk = Tpm20NVRead(a1, a2, v51[1], v20, &v44, v16);
  if ( PublicEk < 0 )
    goto LABEL_56;
  v21 = Feature_Prefer2kEkOver3k__private_IsEnabledDeviceUsageNoInline();
  v22 = (unsigned __int8)v45;
  if ( v21 )
    v22 = 1;
  v45 = v22;
LABEL_49:
  PublicEk = CheckForCancellation(a3);
  if ( PublicEk < 0 )
    goto LABEL_56;
  if ( v52 )
  {
    if ( (int)Tpm20NVReadPublic(a1, a2, v52, &v43, (struct TPM2B_BUFFER *)Srca) >= 0 && v43 )
    {
      PublicEk = CheckForCancellation(a3);
      if ( PublicEk < 0 )
        goto LABEL_56;
      v23 = TpmAlloc(1, v43, retaddr);
      v53 = v23;
      if ( !v23 )
      {
LABEL_55:
        PublicEk = -1073741670;
        goto LABEL_56;
      }
      PublicEk = Tpm20NVRead(a1, a2, v52, v23, &v43, v16);
      if ( PublicEk < 0 )
        goto LABEL_56;
      v24 = Feature_Prefer2kEkOver3k__private_IsEnabledDeviceUsageNoInline();
      v25 = (unsigned __int8)v46;
      if ( v24 )
        v25 = 1;
      v46 = v25;
    }
    PublicEk = CheckForCancellation(a3);
    if ( PublicEk < 0 )
      goto LABEL_56;
  }
  v48 = 391;
  v26 = TpmAlloc(1, 0x187u, retaddr);
  v8 = v26;
  if ( !v26 )
    goto LABEL_55;
  PublicEk = PrepareEkTemplate(v26, &v48, v42, v44, v53, v43, (struct EkCertNvIndex *)v51);
  if ( PublicEk == -1073741764 )
  {
    TpmFree(v8);
    v27 = TpmAlloc(1, v48, retaddr);
    v8 = v27;
    if ( !v27 )
      goto LABEL_55;
    PublicEk = PrepareEkTemplate(v27, &v48, v42, v44, v53, v43, (struct EkCertNvIndex *)v51);
  }
  if ( PublicEk < 0 )
    goto LABEL_56;
  PublicEk = Tpm20CreatePrimaryEk(a1, a2, (union _TPM20_HANDLE *)&v49, v8, v48, v50, v41);
  if ( (unsigned int)dword_1400470A0 > 5 && (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
  {
    v47 = PublicEk;
    v50 = (struct TPM2B_BUFFER *)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v28,
      (unsigned int)byte_140041D79,
      v29,
      v30,
      (__int64)&v50,
      (__int64)&v47);
  }
  if ( PublicEk < 0 || (PublicEk = CheckForCancellation(a3), PublicEk < 0) )
  {
    v3 = v49;
    goto LABEL_56;
  }
  v3 = v49;
  PublicEk = Tpm20EvictControl(a1, a2, v49, 2164326401LL, v16);
  if ( PublicEk < 0 )
  {
LABEL_56:
    v7 = v42;
    goto LABEL_84;
  }
  PublicEk = Tpm20ReadPublicEk(a1, a2, (struct TPM2B_BUFFER *)&v60, (struct TPM2B_BUFFER *)&v58);
  if ( PublicEk >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
    UpdateRegistryEkValues((const struct TPM2B_BUFFER *)&v60, (struct TPM2B_BUFFER *)&v58);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
  v7 = v42;
LABEL_84:
  if ( (unsigned int)Feature_Prefer2kEkOver3k__private_IsEnabledDeviceUsageNoInline() )
  {
    v34 = (_BYTE)v45 != 0;
    LOBYTE(v45) = -(char)v45;
    v33 = v34 ? v51[1] : 0;
    v34 = (_BYTE)v46 != 0;
    LOBYTE(v46) = -(char)v46;
    if ( (unsigned int)dword_1400470A0 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(v32, v31, v33, v34 ? v52 : 0) )
      {
        v49 = v37;
        v46 = v36;
        v45 = PublicEk;
        v50 = (struct TPM2B_BUFFER *)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v35,
          (unsigned int)byte_140041D21,
          v36,
          v37,
          (__int64)&v50,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v49);
      }
    }
  }
  if ( v3 )
    Tpm20CmdFlushContextWorker(a1, a2, 0, v3);
  if ( PublicEk == -1073741536
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
  }
  v57 = 0;
  v55 = 0;
  if ( v53 )
    TpmFree(v53);
  if ( v7 )
    TpmFree(v7);
  if ( v8 )
    TpmFree(v8);
  TPM2B_BUFFER::Clear((TPM2B_BUFFER *)&v54, 0);
  TPM2B_BUFFER::Clear((TPM2B_BUFFER *)&v56, 0);
  TPM2B_BUFFER::Clear((TPM2B_BUFFER *)&v58, 0);
  TPM2B_BUFFER::Clear((TPM2B_BUFFER *)&v60, 0);
  return (unsigned int)PublicEk;
}

```

## disassembly

```asm
0x14002d050  mov     [rsp-8+arg_18], rbx
0x14002d055  push    rbp
0x14002d056  push    rsi
0x14002d057  push    rdi
0x14002d058  push    r12
0x14002d05a  push    r13
0x14002d05c  push    r14
0x14002d05e  push    r15
0x14002d060  lea     rbp, [rsp-40h]
0x14002d065  sub     rsp, 140h
0x14002d06c  mov     rax, cs:__security_cookie
0x14002d073  xor     rax, rsp
0x14002d076  mov     [rbp+70h+var_38], rax
0x14002d07a  xor     ebx, ebx
0x14002d07c  mov     r15, rdx
0x14002d07f  mov     r13, rcx
0x14002d082  mov     [rbp+70h+var_F0], rbx
0x14002d086  lea     rcx, [rbp+70h+var_B8]; this
0x14002d08a  mov     [rsp+170h+var_128], ebx
0x14002d08e  mov     rsi, r8
0x14002d091  mov     [rsp+170h+var_130], rbx
0x14002d096  lea     edi, [rbx+1]
0x14002d099  mov     [rsp+170h+var_124], ebx
0x14002d09d  mov     dl, dil; unsigned __int8
0x14002d0a0  mov     [rsp+170h+var_110], ebx
0x14002d0a4  mov     r14d, ebx
0x14002d0a7  mov     [rbp+70h+var_B8], bx
0x14002d0ab  mov     r12d, ebx
0x14002d0ae  mov     [rbp+70h+var_B0], rbx
0x14002d0b2  call    ?Clear@TPM2B_BUFFER@@AEAAJE@Z; TPM2B_BUFFER::Clear(uchar)
0x14002d0b7  mov     dl, dil; unsigned __int8
0x14002d0ba  mov     [rbp+70h+var_C8], bx
0x14002d0be  lea     rcx, [rbp+70h+var_C8]; this
0x14002d0c2  mov     [rbp+70h+var_C0], rbx
0x14002d0c6  call    ?Clear@TPM2B_BUFFER@@AEAAJE@Z; TPM2B_BUFFER::Clear(uchar)
0x14002d0cb  xorps   xmm0, xmm0
0x14002d0ce  mov     [rbp+70h+var_D8], bx
0x14002d0d2  xor     eax, eax
0x14002d0d4  mov     [rbp+70h+var_D0], rbx
0x14002d0d8  movups  xmmword ptr [rbp+70h+var_58], xmm0
0x14002d0dc  mov     dl, dil; unsigned __int8
0x14002d0df  mov     [rbp+70h+var_80], eax
0x14002d0e2  lea     rcx, [rbp+70h+var_D8]; this
0x14002d0e6  movups  xmmword ptr [rbp+70h+var_58+0Ah], xmm0
0x14002d0ea  movups  xmmword ptr [rbp+70h+var_78], xmm0
0x14002d0ee  movups  [rbp+70h+var_68], xmm0
0x14002d0f2  movups  xmmword ptr [rbp+70h+var_90], xmm0
0x14002d0f6  call    ?Clear@TPM2B_BUFFER@@AEAAJE@Z; TPM2B_BUFFER::Clear(uchar)
0x14002d0fb  xorps   xmm0, xmm0
0x14002d0fe  mov     [rbp+70h+var_E8], bx
0x14002d102  xor     eax, eax
0x14002d104  mov     [rbp+70h+var_E0], rbx
0x14002d108  mov     dl, dil; unsigned __int8
0x14002d10b  mov     [rbp+70h+var_98], eax
0x14002d10e  lea     rcx, [rbp+70h+var_E8]; this
0x14002d112  movups  xmmword ptr [rbp+70h+var_A8], xmm0
0x14002d116  call    ?Clear@TPM2B_BUFFER@@AEAAJE@Z; TPM2B_BUFFER::Clear(uchar)
0x14002d11b  mov     rcx, rsi; struct Event *
0x14002d11e  mov     qword ptr [rsp+170h+var_100], rbx
0x14002d123  mov     [rsp+170h+var_F8], ebx
0x14002d127  mov     byte ptr [rsp+170h+var_120], bl
0x14002d12b  mov     byte ptr [rsp+170h+var_11C], bl
0x14002d12f  mov     [rsp+170h+var_10C], ebx
0x14002d133  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002d138  mov     edi, eax
0x14002d13a  test    eax, eax
0x14002d13c  js      loc_14002D74F
0x14002d142  xor     r9d, r9d; struct TPM2B_BUFFER *
0x14002d145  xor     r8d, r8d; struct TPM2B_BUFFER *
0x14002d148  mov     rdx, r15; struct TpmStack *
0x14002d14b  mov     rcx, r13; struct Tpm20Context *
0x14002d14e  call    ?Tpm20ReadPublicEk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVTPM2B_BUFFER@@2@Z; Tpm20ReadPublicEk(Tpm20Context *,TpmStack *,TPM2B_BUFFER *,TPM2B_BUFFER *)
0x14002d153  mov     edi, eax
0x14002d155  test    eax, eax
0x14002d157  js      loc_14002D1E0
0x14002d15d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d164  lea     rsi, WPP_GLOBAL_Control
0x14002d16b  cmp     rcx, rsi
0x14002d16e  jz      short loc_14002D18A
0x14002d170  mov     eax, [rcx+2Ch]
0x14002d173  test    al, 4
0x14002d175  jz      short loc_14002D18A
0x14002d177  mov     rcx, [rcx+18h]
0x14002d17b  lea     edx, [rbx+11h]
0x14002d17e  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002d185  call    WPP_SF_
0x14002d18a  mov     eax, cs:dword_1400470A0
0x14002d190  cmp     eax, 5
0x14002d193  jbe     loc_14002D756
0x14002d199  call    _tlgKeywordOn
0x14002d19e  test    al, al
0x14002d1a0  jz      loc_14002D756
0x14002d1a6  lea     rax, aPersistentEkAl; "Persistent EK already present; EK creat"...
0x14002d1ad  mov     [rsp+170h+var_130], 1000000h
0x14002d1b6  mov     [rsp+170h+var_108], rax
0x14002d1bb  lea     rdx, byte_140041DAB
0x14002d1c2  lea     rax, [rsp+170h+var_108]
0x14002d1c7  mov     [rsp+170h+var_148], rax
0x14002d1cc  lea     rax, [rsp+170h+var_130]
0x14002d1d1  mov     [rsp+170h+Src], rax
0x14002d1d6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14002d1db  jmp     loc_14002D756
0x14002d1e0  mov     rcx, rsi; struct Event *
0x14002d1e3  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002d1e8  mov     edi, eax
0x14002d1ea  test    eax, eax
0x14002d1ec  js      loc_14002D74F
0x14002d1f2  lea     r8, [rsp+170h+var_118]; unsigned int *
0x14002d1f7  mov     [rsp+170h+var_118], ebx
0x14002d1fb  mov     rdx, r15; this
0x14002d1fe  mov     rcx, r13; struct Tpm20Context *
0x14002d201  call    ?Tpm20GetPermanent@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAI@Z; Tpm20GetPermanent(Tpm20Context *,TpmStack *,uint *)
0x14002d206  mov     edi, eax
0x14002d208  test    eax, eax
0x14002d20a  js      loc_14002D74F
0x14002d210  mov     r14d, [rsp+170h+var_118]
0x14002d215  mov     [rsp+170h+var_108], rbx
0x14002d21a  test    r14b, 2
0x14002d21e  jz      loc_14002D2E3
0x14002d224  mov     r8d, 1
0x14002d22a  mov     [rsp+170h+var_148], rbx
0x14002d22f  lea     r9, [rbp+70h+var_78]
0x14002d233  mov     dword ptr [rsp+170h+Src], 3Ah ; ':'; struct TPM2B_BUFFER *
0x14002d23b  lea     rdx, aEndorsementaut; "EndorsementAuth"
0x14002d242  lea     ecx, [r8+3]
0x14002d246  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x14002d24b  mov     edi, eax
0x14002d24d  test    eax, eax
0x14002d24f  jns     short loc_14002D288
0x14002d251  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d258  lea     rsi, WPP_GLOBAL_Control
0x14002d25f  cmp     rcx, rsi
0x14002d262  jz      short loc_14002D280
0x14002d264  mov     eax, [rcx+2Ch]
0x14002d267  test    al, 4
0x14002d269  jz      short loc_14002D280
0x14002d26b  mov     edx, 12h
0x14002d270  mov     rcx, [rcx+18h]
0x14002d274  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002d27b  call    WPP_SF_
0x14002d280  mov     r14, rbx
0x14002d283  jmp     loc_14002D756
0x14002d288  lea     r8, [rsp+170h+var_118]; unsigned int *
0x14002d28d  mov     [rsp+170h+var_118], 14h
0x14002d295  lea     rdx, [rbp+70h+var_A8]; unsigned __int8 *
0x14002d299  lea     rcx, [rbp+70h+var_78]; unsigned __int16 *
0x14002d29d  call    ?TpmBase64Decode@@YAJPEBGPEAEPEAI@Z; TpmBase64Decode(ushort const *,uchar *,uint *)
0x14002d2a2  mov     edi, eax
0x14002d2a4  test    eax, eax
0x14002d2a6  jns     short loc_14002D2C9
0x14002d2a8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d2af  lea     rsi, WPP_GLOBAL_Control
0x14002d2b6  cmp     rcx, rsi
0x14002d2b9  jz      short loc_14002D280
0x14002d2bb  mov     eax, [rcx+2Ch]
0x14002d2be  test    al, 4
0x14002d2c0  jz      short loc_14002D280
0x14002d2c2  mov     edx, 13h
0x14002d2c7  jmp     short loc_14002D270
0x14002d2c9  movzx   eax, word ptr [rsp+170h+var_118]
0x14002d2ce  mov     [rbp+70h+var_E8], ax
0x14002d2d2  lea     rax, [rbp+70h+var_A8]
0x14002d2d6  mov     [rbp+70h+var_E0], rax
0x14002d2da  lea     rax, [rbp+70h+var_E8]
0x14002d2de  mov     [rsp+170h+var_108], rax
0x14002d2e3  mov     eax, 1
0x14002d2e8  and     r14d, eax
0x14002d2eb  test    r14b, r14b
0x14002d2ee  jz      loc_14002D3AC
0x14002d2f4  mov     [rsp+170h+var_148], rbx
0x14002d2f9  lea     r9, [rbp+70h+var_78]
0x14002d2fd  mov     r8d, eax
0x14002d300  mov     dword ptr [rsp+170h+Src], 3Ah ; ':'
0x14002d308  lea     rdx, aStorageownerau; "StorageOwnerAuth"
0x14002d30f  lea     ecx, [rax+2]
0x14002d312  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x14002d317  mov     edi, eax
0x14002d319  test    eax, eax
0x14002d31b  jns     short loc_14002D349
0x14002d31d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d324  lea     rsi, WPP_GLOBAL_Control
0x14002d32b  cmp     rcx, rsi
0x14002d32e  jz      loc_14002D280
0x14002d334  mov     eax, [rcx+2Ch]
0x14002d337  test    al, 4
0x14002d339  jz      loc_14002D280
0x14002d33f  mov     edx, 14h
0x14002d344  jmp     loc_14002D270
0x14002d349  lea     r8, [rsp+170h+var_118]; unsigned int *
0x14002d34e  mov     [rsp+170h+var_118], 14h
0x14002d356  lea     rdx, [rbp+70h+var_90]; unsigned __int8 *
0x14002d35a  lea     rcx, [rbp+70h+var_78]; unsigned __int16 *
0x14002d35e  call    ?TpmBase64Decode@@YAJPEBGPEAEPEAI@Z; TpmBase64Decode(ushort const *,uchar *,uint *)
0x14002d363  mov     edi, eax
0x14002d365  test    eax, eax
0x14002d367  jns     short loc_14002D395
0x14002d369  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d370  lea     rsi, WPP_GLOBAL_Control
0x14002d377  cmp     rcx, rsi
0x14002d37a  jz      loc_14002D280
0x14002d380  mov     eax, [rcx+2Ch]
0x14002d383  test    al, 4
0x14002d385  jz      loc_14002D280
0x14002d38b  mov     edx, 15h
0x14002d390  jmp     loc_14002D270
0x14002d395  movzx   eax, word ptr [rsp+170h+var_118]
0x14002d39a  lea     r14, [rbp+70h+var_D8]
0x14002d39e  mov     [rbp+70h+var_D8], ax
0x14002d3a2  lea     rax, [rbp+70h+var_90]
0x14002d3a6  mov     [rbp+70h+var_D0], rax
0x14002d3aa  jmp     short loc_14002D3AF
0x14002d3ac  mov     r14, rbx
0x14002d3af  mov     rcx, rsi; struct Event *
0x14002d3b2  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002d3b7  mov     edi, eax
0x14002d3b9  test    eax, eax
0x14002d3bb  js      loc_14002D74C
0x14002d3c1  call    Feature_Prefer2kEkOver3k__private_IsEnabledDeviceUsageNoInline
0x14002d3c6  mov     rdx, [r15+28h]
0x14002d3ca  mov     r8, rsi
0x14002d3cd  lea     rcx, [rsp+170h+var_100]
0x14002d3d2  test    eax, eax
0x14002d3d4  jz      short loc_14002D3DD
0x14002d3d6  call    GetEkNvIndex2kFirst
0x14002d3db  jmp     short loc_14002D3E2
0x14002d3dd  call    GetEkNvIndex
0x14002d3e2  mov     edi, eax
0x14002d3e4  test    eax, eax
0x14002d3e6  js      loc_14002D74C
0x14002d3ec  mov     rcx, rsi; struct Event *
0x14002d3ef  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002d3f4  mov     edi, eax
0x14002d3f6  test    eax, eax
0x14002d3f8  js      loc_14002D74C
0x14002d3fe  mov     r8d, [rsp+170h+var_100+4]; unsigned int
0x14002d403  lea     r9, [rsp+170h+var_124]; unsigned int *
0x14002d408  mov     rdx, r15; this
0x14002d40b  mov     rcx, r13; struct Tpm20Context *
0x14002d40e  call    ?Tpm20NVReadPublic@@YAJPEAVTpm20Context@@PEAVTpmStack@@IPEAIPEAVTPM2B_BUFFER@@@Z; Tpm20NVReadPublic(Tpm20Context *,TpmStack *,uint,uint *,TPM2B_BUFFER *)
0x14002d413  test    eax, eax
0x14002d415  js      loc_14002D49B
0x14002d41b  cmp     [rsp+170h+var_124], ebx
0x14002d41f  jbe     short loc_14002D49B
0x14002d421  mov     rcx, rsi; struct Event *
0x14002d424  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002d429  mov     edi, eax
0x14002d42b  test    eax, eax
0x14002d42d  js      loc_14002D74C
0x14002d433  mov     r8, [rbp+78h]; unsigned __int64
0x14002d437  mov     cl, 1; bool
0x14002d439  mov     edx, [rsp+170h+var_124]; unsigned __int64
0x14002d43d  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14002d442  mov     [rsp+170h+var_130], rax
0x14002d447  test    rax, rax
0x14002d44a  jnz     short loc_14002D459
0x14002d44c  mov     edi, 0C000009Ah
0x14002d451  mov     r14, rax
0x14002d454  jmp     loc_14002D74F
0x14002d459  mov     r8d, [rsp+170h+var_100+4]; unsigned int
0x14002d45e  lea     rcx, [rsp+170h+var_124]
0x14002d463  mov     [rsp+170h+var_148], r14; struct TPM2B_BUFFER *
0x14002d468  mov     r9, rax; unsigned __int8 *
0x14002d46b  mov     [rsp+170h+Src], rcx; struct TPM2B_BUFFER *
0x14002d470  mov     rdx, r15; struct TpmStack *
0x14002d473  mov     rcx, r13; struct Tpm20Context *
0x14002d476  call    ?Tpm20NVRead@@YAJPEAVTpm20Context@@PEAVTpmStack@@IPEAEPEAIPEBVTPM2B_BUFFER@@@Z; Tpm20NVRead(Tpm20Context *,TpmStack *,uint,uchar *,uint *,TPM2B_BUFFER const *)
0x14002d47b  mov     edi, eax
0x14002d47d  test    eax, eax
0x14002d47f  js      short loc_14002D4FC
0x14002d481  call    Feature_Prefer2kEkOver3k__private_IsEnabledDeviceUsageNoInline
0x14002d486  mov     ecx, [rsp+170h+var_120]
0x14002d48a  test    eax, eax
0x14002d48c  movzx   ecx, cl
0x14002d48f  mov     eax, 1
0x14002d494  cmovnz  ecx, eax
0x14002d497  mov     [rsp+170h+var_120], ecx
0x14002d49b  mov     rcx, rsi; struct Event *
0x14002d49e  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002d4a3  mov     edi, eax
0x14002d4a5  test    eax, eax
0x14002d4a7  js      short loc_14002D4FC
0x14002d4a9  mov     r8d, [rsp+170h+var_F8]; unsigned int
0x14002d4ae  test    r8d, r8d
0x14002d4b1  jz      loc_14002D556
0x14002d4b7  lea     r9, [rsp+170h+var_128]; unsigned int *
0x14002d4bc  mov     rdx, r15; this
0x14002d4bf  mov     rcx, r13; struct Tpm20Context *
0x14002d4c2  call    ?Tpm20NVReadPublic@@YAJPEAVTpm20Context@@PEAVTpmStack@@IPEAIPEAVTPM2B_BUFFER@@@Z; Tpm20NVReadPublic(Tpm20Context *,TpmStack *,uint,uint *,TPM2B_BUFFER *)
0x14002d4c7  test    eax, eax
0x14002d4c9  js      short loc_14002D548
0x14002d4cb  cmp     [rsp+170h+var_128], ebx
0x14002d4cf  jbe     short loc_14002D548
0x14002d4d1  mov     rcx, rsi; struct Event *
0x14002d4d4  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002d4d9  mov     edi, eax
0x14002d4db  test    eax, eax
0x14002d4dd  js      short loc_14002D4FC
0x14002d4df  mov     r8, [rbp+78h]; unsigned __int64
0x14002d4e3  mov     cl, 1; bool
0x14002d4e5  mov     edx, [rsp+170h+var_128]; unsigned __int64
  ... truncated ...
```
