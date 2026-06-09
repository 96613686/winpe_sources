# CreateWindowsSrk(Tpm20Context *,TpmStack *,Event *)

- ea: `0x14002d8b4`
- end: `0x14002dddf`
- name: `?CreateWindowsSrk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVEvent@@@Z`
- size: `1323`
- prototype: `__int64 __fastcall(struct Tpm20Context *, struct TpmStack *, struct Event *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x14001d224`
- `0x14002f4a0`

## callees

- `0x140001214`
- `0x14000153c`
- `0x1400078b8`
- `0x140008758`
- `0x140009fc8`
- `0x140016ac4`
- `0x140019dd8`
- `0x14002a0ac`
- `0x14002a254`
- `0x14002a350`
- `0x14002a89c`
- `0x14002d004`
- `0x14002d8b4`
- `0x14002dec4`
- `0x14002e300`
- `0x14002f650`
- `0x140039740`
- `0x140045190`

## pseudocode

```c
__int64 __fastcall CreateWindowsSrk(struct Tpm20Context *a1, struct TpmStack *a2, struct Event *a3)
{
  int PublicSrk; // edi
  struct TPM2B_BUFFER *v7; // r8
  struct TPM2B_BUFFER *v8; // r9
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  struct TpmStack *v13; // rdi
  unsigned int v14; // r12d
  unsigned int v15; // r13d
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 v19; // r8
  unsigned int v20; // ebx
  int v21; // ecx
  unsigned int v22; // r8d
  int v23; // r9d
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  unsigned int v31; // ebx
  int v32; // eax
  struct TpmStack *v33; // r13
  struct Tpm20Context *v34; // r12
  struct TPM2B_BUFFER *v36; // [rsp+20h] [rbp-E0h]
  bool v37; // [rsp+60h] [rbp-A0h]
  bool v38; // [rsp+61h] [rbp-9Fh]
  unsigned int v39; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v40; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v41; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v42; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v43; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v44; // [rsp+78h] [rbp-88h] BYREF
  struct TPM2B_BUFFER *v45; // [rsp+80h] [rbp-80h] BYREF
  struct Tpm20Context *v46; // [rsp+88h] [rbp-78h]
  struct TpmStack *v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v49; // [rsp+9Ch] [rbp-64h] BYREF
  __int16 v50; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 *v51; // [rsp+A8h] [rbp-58h]
  __int64 v52; // [rsp+B0h] [rbp-50h] BYREF
  struct Event *v53; // [rsp+B8h] [rbp-48h]
  unsigned __int8 v54[16]; // [rsp+C0h] [rbp-40h] BYREF
  int v55; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v56[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v57; // [rsp+E8h] [rbp-18h]
  _BYTE v58[26]; // [rsp+F8h] [rbp-8h] BYREF

  v47 = a2;
  v46 = a1;
  v53 = a3;
  v55 = 0;
  memset(v58, 0, sizeof(v58));
  v50 = 0;
  v51 = 0;
  *(_OWORD *)v56 = 0;
  v57 = 0;
  *(_OWORD *)v54 = 0;
  TPM2B_BUFFER::Clear((TPM2B_BUFFER *)&v50, 1u);
  v42 = 0;
  v41 = 0;
  v39 = 0;
  v43 = 0;
  v44 = 0;
  PublicSrk = CheckForCancellation(a3);
  if ( PublicSrk < 0 )
    goto LABEL_44;
  PublicSrk = Tpm20ReadPublicSrk(a1, a2, v7, v8);
  if ( PublicSrk >= 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v10 = 12;
LABEL_48:
      WPP_SF_(v9->AttachedDevice, v10, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  PublicSrk = CheckForCancellation(a3);
  if ( PublicSrk < 0 )
    goto LABEL_44;
  v40 = 0;
  PublicSrk = Tpm20GetPermanent(a1, a2, &v40);
  if ( PublicSrk < 0 )
    goto LABEL_44;
  v45 = 0;
  if ( (v40 & 1) == 0 )
  {
LABEL_19:
    PublicSrk = CheckForCancellation(a3);
    if ( PublicSrk >= 0 )
    {
      GetSrkPolicies(&v42, &v41);
      v13 = v47;
      v14 = v41;
      v15 = v42;
      DetermineSrkCapabilities(
        a1,
        v47,
        v42,
        v41,
        (enum _TPM_API_ALG_CAPABILITY *)&v39,
        (enum _TPM_API_ALG_CAPABILITY *)&v43);
      v19 = v39;
      v20 = v43;
      if ( v39 == 2 && v15 == 2 || v43 == 2 && v14 == 2 )
      {
        if ( (TPMEnableBits & 1) != 0 )
        {
          McTemplateK0qqqqqq_EtwWriteTransfer(v17, (unsigned int)TPM_SRK_CREATION_ERROR, v39, v15, v39, 0, v14, v43, 0);
          v19 = v39;
        }
        if ( (unsigned int)dword_1400470A0 > 5 && (unsigned __int8)tlgKeywordOn(v17, v16, v19, v18) )
        {
          v44 = v20;
          v43 = v14;
          v42 = v22;
          v41 = v15;
          v45 = (struct TPM2B_BUFFER *)0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v21,
            (unsigned int)byte_140041E93,
            v22,
            v23,
            (__int64)&v45,
            (__int64)&v41,
            (__int64)&v42,
            (__int64)&v43,
            (__int64)&v44);
        }
        PublicSrk = -1073741637;
        goto LABEL_49;
      }
      v38 = v39 == 1;
      v37 = v43 == 1;
      PublicSrk = Tpm20CreatePrimarySrk(v46, v13, (union _TPM20_HANDLE *)&v44, v45, v36, v39 == 1, v43 == 1);
      if ( (TPMEnableBits & 2) != 0 )
        McTemplateK0qqqqqq_EtwWriteTransfer(
          (v37 + 2) << 10,
          (unsigned int)TPM_SRK_CREATION_INFORMATION,
          v26,
          v15,
          v39,
          (v38 + 1) << 7,
          v14,
          v20,
          0);
      if ( (unsigned int)dword_1400470A0 > 5 && (unsigned __int8)tlgKeywordOn(v25, v24, v26, v27) )
      {
        v43 = PublicSrk;
        v42 = (v37 + 2) << 10;
        v41 = v20;
        v48 = (v38 + 1) << 7;
        v40 = v14;
        v49 = v15;
        v52 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v28,
          (unsigned int)byte_140041DE3,
          v29,
          v30,
          (__int64)&v52,
          (__int64)&v49,
          (__int64)&v39,
          (__int64)&v48,
          (__int64)&v40,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v43);
      }
      v31 = v44;
      if ( PublicSrk < 0 )
      {
        v34 = v46;
        v33 = v47;
      }
      else
      {
        v32 = CheckForCancellation(v53);
        v33 = v47;
        PublicSrk = v32;
        v34 = v46;
        if ( v32 >= 0 )
        {
          PublicSrk = Tpm20EvictControl(v46, v47, v31, 2164260865LL, v45);
          if ( PublicSrk >= 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
          }
        }
      }
      if ( v31 )
        Tpm20CmdFlushContextWorker(v34, v33, 0, v31);
    }
    goto LABEL_44;
  }
  PublicSrk = TpmRegistry::QueryValue(3, L"StorageOwnerAuth", 1, v56, 58, 0);
  if ( PublicSrk < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v12 = 13;
LABEL_13:
      WPP_SF_(v11->AttachedDevice, v12, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  v40 = 20;
  PublicSrk = TpmBase64Decode(v56, v54, &v40);
  if ( PublicSrk >= 0 )
  {
    v50 = v40;
    v51 = v54;
    v45 = (struct TPM2B_BUFFER *)&v50;
    goto LABEL_19;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    v12 = 14;
    goto LABEL_13;
  }
LABEL_44:
  if ( PublicSrk == -1073741536 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v10 = 16;
      goto LABEL_48;
    }
  }
LABEL_49:
  v51 = 0;
  TPM2B_BUFFER::Clear((TPM2B_BUFFER *)&v50, 0);
  return (unsigned int)PublicSrk;
}

```

## disassembly

```asm
0x14002d8b4  mov     [rsp-8+arg_18], rbx
0x14002d8b9  push    rbp
0x14002d8ba  push    rdi
0x14002d8bb  push    r12
0x14002d8bd  push    r13
0x14002d8bf  push    r14
0x14002d8c1  lea     rbp, [rsp-20h]
0x14002d8c6  sub     rsp, 120h
0x14002d8cd  mov     rax, cs:__security_cookie
0x14002d8d4  xor     rax, rsp
0x14002d8d7  mov     [rbp+40h+var_28], rax
0x14002d8db  xorps   xmm0, xmm0
0x14002d8de  mov     [rbp+40h+var_B0], rdx
0x14002d8e2  mov     r12, rdx
0x14002d8e5  mov     [rbp+40h+var_B8], rcx
0x14002d8e9  mov     rbx, rcx
0x14002d8ec  mov     [rbp+40h+var_88], r8
0x14002d8f0  xor     eax, eax
0x14002d8f2  lea     rcx, [rbp+40h+var_A0]; this
0x14002d8f6  xor     edi, edi
0x14002d8f8  mov     [rbp+40h+var_70], eax
0x14002d8fb  movups  xmmword ptr [rbp+40h+var_48], xmm0
0x14002d8ff  mov     dl, 1; unsigned __int8
0x14002d901  mov     [rbp+40h+var_A0], di
0x14002d905  movups  xmmword ptr [rbp+40h+var_48+0Ah], xmm0
0x14002d909  mov     r13, r8
0x14002d90c  mov     [rbp+40h+var_98], rdi
0x14002d910  movups  xmmword ptr [rbp+40h+var_68], xmm0
0x14002d914  movups  [rbp+40h+var_58], xmm0
0x14002d918  movups  xmmword ptr [rbp+40h+var_80], xmm0
0x14002d91c  call    ?Clear@TPM2B_BUFFER@@AEAAJE@Z; TPM2B_BUFFER::Clear(uchar)
0x14002d921  mov     rcx, r13; struct Event *
0x14002d924  mov     [rsp+140h+var_D0], edi
0x14002d928  mov     [rsp+140h+var_D4], edi
0x14002d92c  mov     [rsp+140h+var_DC], edi
0x14002d930  mov     [rsp+140h+var_CC], edi
0x14002d934  mov     [rsp+140h+var_C8], edi
0x14002d938  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002d93d  lea     r14, WPP_GLOBAL_Control
0x14002d944  mov     edi, eax
0x14002d946  test    eax, eax
0x14002d948  js      loc_14002DD75
0x14002d94e  mov     rdx, r12; struct TpmStack *
0x14002d951  mov     rcx, rbx; struct Tpm20Context *
0x14002d954  call    ?Tpm20ReadPublicSrk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVTPM2B_BUFFER@@2@Z; Tpm20ReadPublicSrk(Tpm20Context *,TpmStack *,TPM2B_BUFFER *,TPM2B_BUFFER *)
0x14002d959  mov     edi, eax
0x14002d95b  test    eax, eax
0x14002d95d  js      short loc_14002D98B
0x14002d95f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d966  lea     r14, WPP_GLOBAL_Control
0x14002d96d  cmp     rcx, r14
0x14002d970  jz      loc_14002DDA5
0x14002d976  mov     eax, [rcx+2Ch]
0x14002d979  test    al, 4
0x14002d97b  jz      loc_14002DDA5
0x14002d981  mov     edx, 0Ch
0x14002d986  jmp     loc_14002DD95
0x14002d98b  mov     rcx, r13; struct Event *
0x14002d98e  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002d993  mov     edi, eax
0x14002d995  test    eax, eax
0x14002d997  js      loc_14002DD75
0x14002d99d  lea     r8, [rsp+140h+var_D8]; unsigned int *
0x14002d9a2  mov     [rsp+140h+var_D8], 0
0x14002d9aa  mov     rdx, r12; this
0x14002d9ad  mov     rcx, rbx; struct Tpm20Context *
0x14002d9b0  call    ?Tpm20GetPermanent@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAI@Z; Tpm20GetPermanent(Tpm20Context *,TpmStack *,uint *)
0x14002d9b5  mov     edi, eax
0x14002d9b7  test    eax, eax
0x14002d9b9  js      loc_14002DD75
0x14002d9bf  mov     eax, [rsp+140h+var_D8]
0x14002d9c3  mov     [rbp+40h+var_C0], 0
0x14002d9cb  test    al, 1
0x14002d9cd  jz      loc_14002DA94
0x14002d9d3  mov     r8d, 1
0x14002d9d9  mov     [rsp+140h+var_118], 0
0x14002d9e2  lea     r9, [rbp+40h+var_68]
0x14002d9e6  mov     dword ptr [rsp+140h+var_120], 3Ah ; ':'
0x14002d9ee  lea     rdx, aStorageownerau; "StorageOwnerAuth"
0x14002d9f5  lea     ecx, [r8+2]
0x14002d9f9  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x14002d9fe  mov     edi, eax
0x14002da00  test    eax, eax
0x14002da02  jns     short loc_14002DA39
0x14002da04  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002da0b  cmp     rcx, r14
0x14002da0e  jz      loc_14002DD75
0x14002da14  mov     eax, [rcx+2Ch]
0x14002da17  test    al, 4
0x14002da19  jz      loc_14002DD75
0x14002da1f  mov     edx, 0Dh
0x14002da24  mov     rcx, [rcx+18h]
0x14002da28  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002da2f  call    WPP_SF_
0x14002da34  jmp     loc_14002DD75
0x14002da39  lea     r8, [rsp+140h+var_D8]; unsigned int *
0x14002da3e  mov     [rsp+140h+var_D8], 14h
0x14002da46  lea     rdx, [rbp+40h+var_80]; unsigned __int8 *
0x14002da4a  lea     rcx, [rbp+40h+var_68]; unsigned __int16 *
0x14002da4e  call    ?TpmBase64Decode@@YAJPEBGPEAEPEAI@Z; TpmBase64Decode(ushort const *,uchar *,uint *)
0x14002da53  mov     edi, eax
0x14002da55  test    eax, eax
0x14002da57  jns     short loc_14002DA7B
0x14002da59  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002da60  cmp     rcx, r14
0x14002da63  jz      loc_14002DD75
0x14002da69  mov     eax, [rcx+2Ch]
0x14002da6c  test    al, 4
0x14002da6e  jz      loc_14002DD75
0x14002da74  mov     edx, 0Eh
0x14002da79  jmp     short loc_14002DA24
0x14002da7b  movzx   eax, word ptr [rsp+140h+var_D8]
0x14002da80  mov     [rbp+40h+var_A0], ax
0x14002da84  lea     rax, [rbp+40h+var_80]
0x14002da88  mov     [rbp+40h+var_98], rax
0x14002da8c  lea     rax, [rbp+40h+var_A0]
0x14002da90  mov     [rbp+40h+var_C0], rax
0x14002da94  mov     rcx, r13; struct Event *
0x14002da97  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002da9c  mov     edi, eax
0x14002da9e  test    eax, eax
0x14002daa0  js      loc_14002DD75
0x14002daa6  lea     rdx, [rsp+140h+var_D4]; unsigned int *
0x14002daab  lea     rcx, [rsp+140h+var_D0]; unsigned int *
0x14002dab0  call    ?GetSrkPolicies@@YAXPEAK0@Z; GetSrkPolicies(ulong *,ulong *)
0x14002dab5  mov     rdi, [rbp+40h+var_B0]
0x14002dab9  lea     rax, [rsp+140h+var_CC]
0x14002dabe  mov     r12d, [rsp+140h+var_D4]
0x14002dac3  mov     rdx, rdi; struct TpmStack *
0x14002dac6  mov     r13d, [rsp+140h+var_D0]
0x14002dacb  mov     r9d, r12d; unsigned int
0x14002dace  mov     [rsp+140h+var_118], rax; enum _TPM_API_ALG_CAPABILITY *
0x14002dad3  mov     r8d, r13d; unsigned int
0x14002dad6  lea     rax, [rsp+140h+var_DC]
0x14002dadb  mov     rcx, rbx; struct Tpm20Context *
0x14002dade  mov     [rsp+140h+var_120], rax; struct TPM2B_BUFFER *
0x14002dae3  call    ?DetermineSrkCapabilities@@YAXPEAVTpm20Context@@PEAVTpmStack@@KKPEAW4_TPM_API_ALG_CAPABILITY@@2@Z; DetermineSrkCapabilities(Tpm20Context *,TpmStack *,ulong,ulong,_TPM_API_ALG_CAPABILITY *,_TPM_API_ALG_CAPABILITY *)
0x14002dae8  mov     r8d, [rsp+140h+var_DC]
0x14002daed  mov     ebx, [rsp+140h+var_CC]
0x14002daf1  cmp     r8d, 2
0x14002daf5  jnz     short loc_14002DAFC
0x14002daf7  cmp     r13d, r8d
0x14002dafa  jz      short loc_14002DB0E
0x14002dafc  cmp     ebx, 2
0x14002daff  jnz     loc_14002DBBF
0x14002db05  cmp     r12d, ebx
0x14002db08  jnz     loc_14002DBBF
0x14002db0e  test    cs:TPMEnableBits, 1
0x14002db15  jz      short loc_14002DB49
0x14002db17  mov     dword ptr [rsp+140h+var_100], 0
0x14002db1f  lea     rdx, TPM_SRK_CREATION_ERROR
0x14002db26  mov     dword ptr [rsp+140h+var_108], ebx
0x14002db2a  mov     r9d, r13d
0x14002db2d  mov     dword ptr [rsp+140h+var_110], r12d
0x14002db32  mov     dword ptr [rsp+140h+var_118], 0
0x14002db3a  mov     dword ptr [rsp+140h+var_120], r8d
0x14002db3f  call    McTemplateK0qqqqqq_EtwWriteTransfer
0x14002db44  mov     r8d, [rsp+140h+var_DC]
0x14002db49  mov     eax, cs:dword_1400470A0
0x14002db4f  cmp     eax, 5
0x14002db52  jbe     short loc_14002DBB5
0x14002db54  call    _tlgKeywordOn
0x14002db59  test    al, al
0x14002db5b  jz      short loc_14002DBB5
0x14002db5d  lea     rax, [rsp+140h+var_C8]
0x14002db62  mov     [rsp+140h+var_C8], ebx
0x14002db66  mov     [rsp+140h+var_100], rax
0x14002db6b  lea     rdx, byte_140041E93
0x14002db72  lea     rax, [rsp+140h+var_CC]
0x14002db77  mov     [rsp+140h+var_CC], r12d
0x14002db7c  mov     [rsp+140h+var_108], rax
0x14002db81  lea     rax, [rsp+140h+var_D0]
0x14002db86  mov     qword ptr [rsp+140h+var_110], rax
0x14002db8b  lea     rax, [rsp+140h+var_D4]
0x14002db90  mov     [rsp+140h+var_118], rax
0x14002db95  lea     rax, [rbp+40h+var_C0]
0x14002db99  mov     [rsp+140h+var_120], rax
0x14002db9e  mov     [rsp+140h+var_D0], r8d
0x14002dba3  mov     [rsp+140h+var_D4], r13d
0x14002dba8  mov     [rbp+40h+var_C0], 1000000h
0x14002dbb0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002dbb5  mov     edi, 0C00000BBh
0x14002dbba  jmp     loc_14002DDA5
0x14002dbbf  mov     r9, [rbp+40h+var_C0]; struct TPM2B_BUFFER *
0x14002dbc3  cmp     r8d, 1
0x14002dbc7  lea     r8, [rsp+140h+var_C8]; union _TPM20_HANDLE *
0x14002dbcc  mov     rdx, rdi; this
0x14002dbcf  setz    al
0x14002dbd2  cmp     ebx, 1
0x14002dbd5  mov     [rsp+140h+var_DF], al
0x14002dbd9  setz    cl
0x14002dbdc  mov     [rsp+140h+var_110], cl; bool
0x14002dbe0  mov     [rsp+140h+var_E0], cl
0x14002dbe4  mov     rcx, [rbp+40h+var_B8]; struct Tpm20Context *
0x14002dbe8  mov     byte ptr [rsp+140h+var_118], al; bool
0x14002dbec  call    ?Tpm20CreatePrimarySrk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAT_TPM20_HANDLE@@PEBVTPM2B_BUFFER@@PEAV4@_N5@Z; Tpm20CreatePrimarySrk(Tpm20Context *,TpmStack *,_TPM20_HANDLE *,TPM2B_BUFFER const *,TPM2B_BUFFER *,bool,bool)
0x14002dbf1  test    cs:TPMEnableBits, 2
0x14002dbf8  mov     edi, eax
0x14002dbfa  jz      short loc_14002DC39
0x14002dbfc  movzx   ecx, [rsp+140h+var_E0]
0x14002dc01  lea     rdx, TPM_SRK_CREATION_INFORMATION
0x14002dc08  movzx   eax, [rsp+140h+var_DF]
0x14002dc0d  add     ecx, 2
0x14002dc10  inc     eax
0x14002dc12  shl     ecx, 0Ah
0x14002dc15  mov     dword ptr [rsp+140h+var_100], ecx
0x14002dc19  mov     r9d, r13d
0x14002dc1c  mov     dword ptr [rsp+140h+var_108], ebx
0x14002dc20  shl     eax, 7
0x14002dc23  mov     dword ptr [rsp+140h+var_110], r12d
0x14002dc28  mov     dword ptr [rsp+140h+var_118], eax
0x14002dc2c  mov     eax, [rsp+140h+var_DC]
0x14002dc30  mov     dword ptr [rsp+140h+var_120], eax
0x14002dc34  call    McTemplateK0qqqqqq_EtwWriteTransfer
0x14002dc39  mov     eax, cs:dword_1400470A0
0x14002dc3f  cmp     eax, 5
0x14002dc42  jbe     loc_14002DCEB
0x14002dc48  call    _tlgKeywordOn
0x14002dc4d  test    al, al
0x14002dc4f  jz      loc_14002DCEB
0x14002dc55  movzx   eax, [rsp+140h+var_E0]
0x14002dc5a  lea     rdx, byte_140041DE3
0x14002dc61  add     eax, 2
0x14002dc64  mov     [rsp+140h+var_CC], edi
0x14002dc68  shl     eax, 0Ah
0x14002dc6b  mov     [rsp+140h+var_D0], eax
0x14002dc6f  movzx   eax, [rsp+140h+var_DF]
0x14002dc74  inc     eax
0x14002dc76  mov     [rsp+140h+var_D4], ebx
0x14002dc7a  shl     eax, 7
0x14002dc7d  mov     [rbp+40h+var_A8], eax
0x14002dc80  mov     eax, [rsp+140h+var_DC]
0x14002dc84  mov     [rsp+140h+var_DC], eax
0x14002dc88  lea     rax, [rsp+140h+var_CC]
0x14002dc8d  mov     [rsp+140h+var_E8], rax
0x14002dc92  lea     rax, [rsp+140h+var_D0]
0x14002dc97  mov     [rsp+140h+var_F0], rax
0x14002dc9c  lea     rax, [rsp+140h+var_D4]
0x14002dca1  mov     [rsp+140h+var_F8], rax
0x14002dca6  lea     rax, [rsp+140h+var_D8]
0x14002dcab  mov     [rsp+140h+var_100], rax
0x14002dcb0  lea     rax, [rbp+40h+var_A8]
0x14002dcb4  mov     [rsp+140h+var_108], rax
0x14002dcb9  lea     rax, [rsp+140h+var_DC]
0x14002dcbe  mov     qword ptr [rsp+140h+var_110], rax
0x14002dcc3  lea     rax, [rbp+40h+var_A4]
0x14002dcc7  mov     [rsp+140h+var_118], rax
0x14002dccc  lea     rax, [rbp+40h+var_90]
0x14002dcd0  mov     [rsp+140h+var_120], rax
0x14002dcd5  mov     [rsp+140h+var_D8], r12d
0x14002dcda  mov     [rbp+40h+var_A4], r13d
0x14002dcde  mov     [rbp+40h+var_90], 1000000h
0x14002dce6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002dceb  mov     ebx, [rsp+140h+var_C8]
0x14002dcef  test    edi, edi
0x14002dcf1  js      short loc_14002DD58
0x14002dcf3  mov     rcx, [rbp+40h+var_88]; struct Event *
0x14002dcf7  call    ?CheckForCancellation@@YAJPEAVEvent@@@Z; CheckForCancellation(Event *)
0x14002dcfc  mov     r13, [rbp+40h+var_B0]
0x14002dd00  mov     edi, eax
0x14002dd02  mov     r12, [rbp+40h+var_B8]
0x14002dd06  test    eax, eax
0x14002dd08  js      short loc_14002DD60
0x14002dd0a  mov     rax, [rbp+40h+var_C0]
0x14002dd0e  mov     r8d, ebx
0x14002dd11  mov     r9d, cs:dword_14003DF90
0x14002dd18  mov     rdx, r13
0x14002dd1b  mov     rcx, r12
0x14002dd1e  mov     [rsp+140h+var_120], rax
0x14002dd23  call    ?Tpm20EvictControl@@YAJPEAVTpm20Context@@PEAVTpmStack@@T_TPM20_HANDLE@@2PEBVTPM2B_BUFFER@@@Z; Tpm20EvictControl(Tpm20Context *,TpmStack *,_TPM20_HANDLE,_TPM20_HANDLE,TPM2B_BUFFER const *)
0x14002dd28  mov     edi, eax
0x14002dd2a  test    eax, eax
0x14002dd2c  js      short loc_14002DD60
0x14002dd2e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002dd35  cmp     rcx, r14
0x14002dd38  jz      short loc_14002DD60
0x14002dd3a  mov     eax, [rcx+2Ch]
0x14002dd3d  test    al, 4
0x14002dd3f  jz      short loc_14002DD60
0x14002dd41  mov     rcx, [rcx+18h]
0x14002dd45  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002dd4c  mov     edx, 0Fh
0x14002dd51  call    WPP_SF_
0x14002dd56  jmp     short loc_14002DD60
0x14002dd58  mov     r12, [rbp+40h+var_B8]
0x14002dd5c  mov     r13, [rbp+40h+var_B0]
0x14002dd60  test    ebx, ebx
0x14002dd62  jz      short loc_14002DD75
0x14002dd64  mov     r9d, ebx
0x14002dd67  xor     r8d, r8d
0x14002dd6a  mov     rdx, r13
0x14002dd6d  mov     rcx, r12
0x14002dd70  call    ?Tpm20CmdFlushContextWorker@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVTpmTransport@@T_TPM20_HANDLE@@@Z; Tpm20CmdFlushContextWorker(Tpm20Context *,TpmStack *,TpmTransport *,_TPM20_HANDLE)
0x14002dd75  cmp     edi, 0C0000120h
0x14002dd7b  jnz     short loc_14002DDA5
0x14002dd7d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002dd84  cmp     rcx, r14
0x14002dd87  jz      short loc_14002DDA5
0x14002dd89  mov     eax, [rcx+2Ch]
0x14002dd8c  test    al, 4
  ... truncated ...
```
