# TpmSubmitPPICommand(void *,TpmStack *,_DEVICE_OBJECT *,uchar const *,uint,uchar *,uint,uint *)

- ea: `0x140016628`
- end: `0x140016abe`
- name: `?TpmSubmitPPICommand@@YAJPEAXPEAVTpmStack@@PEAU_DEVICE_OBJECT@@PEBEIPEAEIPEAI@Z`
- size: `1174`
- prototype: `int(void *, struct TpmStack *, struct _DEVICE_OBJECT *, const unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140017ea0`

## callees

- `0x140001148`
- `0x140004a90`
- `0x140009278`
- `0x140009d00`
- `0x14000f63c`
- `0x14000f910`
- `0x14001319c`
- `0x140016628`
- `0x140016ac4`
- `0x14001a770`
- `0x14001ade8`
- `0x14001b220`
- `0x140039780`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400166c0`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400166c0`

## pseudocode

```c
__int64 __fastcall TpmSubmitPPICommand(
        void *a1,
        struct TpmStack *a2,
        struct _DEVICE_OBJECT *a3,
        unsigned int *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int *a8)
{
  unsigned int v8; // r12d
  unsigned int *v10; // rbx
  int v11; // r9d
  unsigned int v12; // esi
  int v13; // ebx
  unsigned int *v14; // rdi
  unsigned int v15; // ebx
  int v16; // eax
  struct _EPROCESS *CurrentProcess; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned __int16 *v22; // rdi
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rcx
  unsigned __int8 *v27; // r15
  unsigned __int16 v28; // di
  PDEVICE_OBJECT v29; // rcx
  int v30; // edx
  int v31; // r13d
  __int64 v32; // r8
  int v33; // r15d
  unsigned __int16 v34; // di
  bool v35; // cf
  unsigned __int8 *v36; // r12
  __int16 v37; // dx
  __int64 v38; // r8
  int v39; // ebx
  int v41[2]; // [rsp+28h] [rbp-48h]
  ULONG InputBufferLength; // [rsp+30h] [rbp-40h]
  unsigned __int16 *v43[2]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v44; // [rsp+60h] [rbp-10h] BYREF
  int v47; // [rsp+C0h] [rbp+50h]

  v47 = (int)a3;
  v8 = a5;
  v10 = a4;
  v11 = (int)a3;
  if ( a5 >= 4 )
  {
    v14 = a8;
    *a8 = 0;
    v12 = *v10;
    if ( (*v10 == 2 || v12 == 7) && v8 >= 8 )
    {
      v15 = v10[1];
      if ( v15 <= 0x16 )
      {
        v16 = 6307872;
        if ( _bittest(&v16, v15) )
        {
          v43[0] = 0;
          CurrentProcess = (struct _EPROCESS *)PsGetCurrentProcess(2, 4, a3, a3);
          Utils::GetProcessPath(CurrentProcess, (const unsigned __int16 **)v43);
          v22 = L"TPM Driver";
          if ( v43[0] )
            v22 = v43[0];
          if ( (TPMEnableBits & 2) != 0 )
            McTemplateK0dqz_EtwWriteTransfer(v19, (unsigned int)TPM_CLEAR_PENDING, v20, 2, 241, (__int64)v22);
          if ( (unsigned int)dword_1400470A0 > 5 && (unsigned __int8)tlgKeywordOn(v19, v18, v20, v21) )
          {
            v43[0] = v22;
            a5 = v15;
            *(_QWORD *)&v44 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v23,
              (unsigned int)byte_140041A91,
              v24,
              v25,
              (__int64)&v44,
              (__int64)&a5,
              (__int64)v43);
          }
          v14 = a8;
          v11 = v47;
        }
      }
      v10 = a4;
    }
    if ( TpmTransportType::m_Version == 2 && *(_DWORD *)(*((_QWORD *)a2 + 5) + 244LL) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_5da39d5982eb3c55461d51d673252f3f_Traceguids, v12);
      v26 = *((_QWORD *)a2 + 5);
      v27 = a6;
      *(_QWORD *)v41 = v14;
      v28 = a7;
      v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, unsigned __int8 *, unsigned int, int *))(*(_QWORD *)v26 + 56LL))(
              v26,
              v10,
              v8,
              a6,
              a7,
              *(int **)v41);
      if ( v13 >= 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          v30 = 14;
          *(_QWORD *)&v44 = v27;
          *((_QWORD *)&v44 + 1) = v28;
LABEL_63:
          WPP_SF_L_HEX_(
            v29->AttachedDevice,
            v30,
            (unsigned int)WPP_5da39d5982eb3c55461d51d673252f3f_Traceguids,
            v12,
            (__int64)&v44);
        }
      }
LABEL_64:
      if ( !v13 )
        return (unsigned int)v13;
      goto LABEL_65;
    }
    v31 = a7;
    v32 = 0;
    a5 = 0;
    LODWORD(v43[0]) = 1;
    if ( v12 != 1 )
    {
      if ( v12 == 2 )
      {
LABEL_33:
        if ( v8 < 8 )
          goto LABEL_3;
        v33 = v10[1];
        v34 = v12 != 2;
        if ( v12 == 7 && v8 == 12 )
        {
          v32 = v10[2];
          v34 |= 4u;
          a5 = v10[2];
          LODWORD(v43[0]) = 2;
        }
LABEL_44:
        if ( TpmTransportType::m_TalkingToTpmSimulator )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_LLDD(WPP_GLOBAL_Control->AttachedDevice, 15, v32, v12, v33, v32, v34);
          }
          v36 = a6;
          v13 = TpmCall20EmulatedDSMMethod(a1, a2, a5, v34, a6, &a7);
          if ( v13 < 0 )
            goto LABEL_64;
          v37 = a7;
          *a8 = a7;
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
          {
            goto LABEL_64;
          }
          v44 = 0;
          WORD4(v44) = v37;
          v30 = 16;
        }
        else
        {
          v13 = TpmPpiCheckFirmwareSupportForDsmFunction(v11);
          if ( v13 < 0 )
            goto LABEL_64;
          v39 = a5;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_LLDD(WPP_GLOBAL_Control->AttachedDevice, 17, v38, v12, v33, a5, v34);
          }
          v36 = a6;
          LOWORD(InputBufferLength) = v34;
          v13 = TpmCallDSMMethod(
                  v47,
                  (int)&PHYSICAL_PRESENCE_INTERFACE_GUID,
                  (int)v43[0],
                  v12,
                  v33,
                  v39,
                  InputBufferLength,
                  (__int64)a6,
                  v31,
                  (__int64)a8);
          if ( v13 < 0 )
            goto LABEL_64;
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
          {
            goto LABEL_64;
          }
          v30 = 18;
          v44 = 0;
          WORD4(v44) = v31;
        }
        *(_QWORD *)&v44 = v36;
        goto LABEL_63;
      }
      if ( v12 != 3 && v12 != 4 && v12 != 5 )
      {
        if ( v12 - 7 > 1 )
          goto LABEL_3;
        goto LABEL_33;
      }
    }
    if ( v8 != 4 )
      goto LABEL_3;
    switch ( v12 )
    {
      case 3u:
        v35 = a7 < 8;
        break;
      case 4u:
        v35 = a7 < 4;
        break;
      case 5u:
        v35 = a7 < 0xC;
        break;
      default:
LABEL_43:
        v33 = 0;
        v34 = 2;
        goto LABEL_44;
    }
    if ( v35 )
      goto LABEL_3;
    goto LABEL_43;
  }
  v12 = 0;
LABEL_3:
  v13 = -1073741811;
LABEL_65:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_5da39d5982eb3c55461d51d673252f3f_Traceguids, v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140016628  mov     rax, rsp
0x14001662b  mov     [rax+20h], r9
0x14001662f  mov     [rax+18h], r8
0x140016633  mov     [rax+10h], rdx
0x140016637  mov     [rax+8], rcx
0x14001663b  push    rbp
0x14001663c  push    rbx
0x14001663d  push    rsi
0x14001663e  push    rdi
0x14001663f  push    r12
0x140016641  push    r13
0x140016643  push    r15
0x140016645  mov     rbp, rsp
0x140016648  sub     rsp, 70h
0x14001664c  mov     r12d, [rbp+arg_20]
0x140016650  lea     r13, WPP_GLOBAL_Control
0x140016657  mov     r15, rdx
0x14001665a  mov     rbx, r9
0x14001665d  mov     edx, 4
0x140016662  mov     r9, r8
0x140016665  cmp     r12d, edx
0x140016668  jnb     short loc_140016676
0x14001666a  xor     esi, esi
0x14001666c  mov     ebx, 0C000000Dh
0x140016671  jmp     loc_140016A76
0x140016676  mov     rdi, [rbp+arg_38]
0x14001667a  mov     ecx, 2
0x14001667f  mov     dword ptr [rdi], 0
0x140016685  mov     esi, [rbx]
0x140016687  cmp     esi, ecx
0x140016689  jz      short loc_140016694
0x14001668b  cmp     esi, 7
0x14001668e  jnz     loc_14001676F
0x140016694  cmp     r12d, 8
0x140016698  jb      loc_14001676F
0x14001669e  mov     ebx, [rbx+4]
0x1400166a1  cmp     ebx, 16h
0x1400166a4  ja      loc_14001676B
0x1400166aa  mov     eax, 604020h
0x1400166af  bt      eax, ebx
0x1400166b2  jnb     loc_14001676B
0x1400166b8  mov     [rbp+var_20], 0
0x1400166c0  call    cs:__imp_PsGetCurrentProcess
0x1400166c7  nop     dword ptr [rax+rax+00h]
0x1400166cc  mov     rcx, rax; struct _EPROCESS *
0x1400166cf  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x1400166d3  call    ?GetProcessPath@Utils@@SAJPEAU_EPROCESS@@PEAPEBG@Z; Utils::GetProcessPath(_EPROCESS *,ushort const * *)
0x1400166d8  cmp     [rbp+var_20], 0
0x1400166dd  lea     rdi, aTpmDriver; "TPM Driver"
0x1400166e4  cmovnz  rdi, [rbp+var_20]
0x1400166e9  test    cs:TPMEnableBits, 2
0x1400166f0  jz      short loc_140016711
0x1400166f2  mov     qword ptr [rsp+70h+var_48], rdi
0x1400166f7  lea     rdx, TPM_CLEAR_PENDING
0x1400166fe  mov     r9d, 2
0x140016704  mov     [rsp+70h+var_50], 2F1h
0x14001670c  call    McTemplateK0dqz_EtwWriteTransfer
0x140016711  mov     eax, cs:dword_1400470A0
0x140016717  cmp     eax, 5
0x14001671a  jbe     short loc_14001675B
0x14001671c  call    _tlgKeywordOn
0x140016721  test    al, al
0x140016723  jz      short loc_14001675B
0x140016725  lea     rax, [rbp+var_20]
0x140016729  mov     [rbp+var_20], rdi
0x14001672d  mov     qword ptr [rsp+70h+InputBufferLength], rax
0x140016732  lea     rdx, byte_140041A91
0x140016739  lea     rax, [rbp+arg_20]
0x14001673d  mov     [rbp+arg_20], ebx
0x140016740  mov     qword ptr [rsp+70h+var_48], rax
0x140016745  lea     rax, [rbp+var_10]
0x140016749  mov     qword ptr [rsp+70h+var_50], rax
0x14001674e  mov     qword ptr [rbp+var_10], 1000000h
0x140016756  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14001675b  mov     rdi, [rbp+arg_38]
0x14001675f  mov     ecx, 2
0x140016764  mov     r9, qword ptr [rbp+arg_10]
0x140016768  lea     edx, [rcx+2]
0x14001676b  mov     rbx, [rbp+arg_18]
0x14001676f  cmp     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, ecx; TpmTransportType::VERSION TpmTransportType::m_Version
0x140016775  jnz     loc_14001681F
0x14001677b  mov     rax, [r15+28h]
0x14001677f  cmp     dword ptr [rax+0F4h], 0
0x140016786  jz      loc_14001681F
0x14001678c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140016793  cmp     rcx, r13
0x140016796  jz      short loc_1400167B7
0x140016798  mov     eax, [rcx+2Ch]
0x14001679b  test    dl, al
0x14001679d  jz      short loc_1400167B7
0x14001679f  mov     rcx, [rcx+18h]
0x1400167a3  lea     r8, WPP_5da39d5982eb3c55461d51d673252f3f_Traceguids
0x1400167aa  mov     edx, 0Dh
0x1400167af  mov     r9d, esi
0x1400167b2  call    WPP_SF_d
0x1400167b7  mov     rcx, [r15+28h]
0x1400167bb  mov     r8d, r12d
0x1400167be  mov     r15, [rbp+arg_28]
0x1400167c2  mov     rdx, rbx
0x1400167c5  mov     qword ptr [rsp+70h+var_48], rdi
0x1400167ca  mov     r9, r15
0x1400167cd  mov     edi, [rbp+arg_30]
0x1400167d0  mov     rax, [rcx]
0x1400167d3  mov     [rsp+70h+var_50], edi
0x1400167d7  mov     rax, [rax+38h]
0x1400167db  call    _guard_dispatch_icall
0x1400167e0  mov     ebx, eax
0x1400167e2  test    eax, eax
0x1400167e4  js      loc_140016A72
0x1400167ea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400167f1  cmp     rcx, r13
0x1400167f4  jz      loc_140016A72
0x1400167fa  mov     edx, [rcx+2Ch]
0x1400167fd  test    dl, 20h
0x140016800  jz      loc_140016A72
0x140016806  xorps   xmm0, xmm0
0x140016809  mov     edx, 0Eh
0x14001680e  movups  [rbp+var_10], xmm0
0x140016812  mov     qword ptr [rbp+var_10], r15
0x140016816  mov     word ptr [rbp+var_10+8], di
0x14001681a  jmp     loc_140016A4D
0x14001681f  mov     r13d, [rbp+arg_30]
0x140016823  xor     r8d, r8d
0x140016826  mov     eax, esi
0x140016828  mov     [rbp+arg_20], r8d
0x14001682c  mov     dword ptr [rbp+var_20], 1
0x140016833  sub     eax, 1
0x140016836  jz      short loc_14001688A
0x140016838  sub     eax, 1
0x14001683b  jz      short loc_140016859
0x14001683d  sub     eax, 1
0x140016840  jz      short loc_14001688A
0x140016842  sub     eax, 1
0x140016845  jz      short loc_14001688A
0x140016847  sub     eax, 1
0x14001684a  jz      short loc_14001688A
0x14001684c  sub     eax, ecx
0x14001684e  jz      short loc_140016859
0x140016850  cmp     eax, 1
0x140016853  jnz     loc_14001666C
0x140016859  cmp     r12d, 8
0x14001685d  jb      loc_14001666C
0x140016863  mov     r15d, [rbx+4]
0x140016867  xor     edi, edi
0x140016869  cmp     esi, ecx
0x14001686b  setnz   dil
0x14001686f  cmp     esi, 7
0x140016872  jnz     short loc_1400168BC
0x140016874  cmp     r12d, 0Ch
0x140016878  jnz     short loc_1400168BC
0x14001687a  mov     r8d, [rbx+8]
0x14001687e  or      di, dx
0x140016881  mov     [rbp+arg_20], r8d
0x140016885  mov     dword ptr [rbp+var_20], ecx
0x140016888  jmp     short loc_1400168BC
0x14001688a  cmp     r12d, edx
0x14001688d  jnz     loc_14001666C
0x140016893  mov     eax, esi
0x140016895  sub     eax, 3
0x140016898  jz      loc_140016981
0x14001689e  sub     eax, 1
0x1400168a1  jz      loc_140016979
0x1400168a7  cmp     eax, 1
0x1400168aa  jnz     short loc_1400168B6
0x1400168ac  cmp     r13d, 0Ch
0x1400168b0  jb      loc_14001666C
0x1400168b6  xor     r15d, r15d
0x1400168b9  movzx   edi, cx
0x1400168bc  cmp     cs:?m_TalkingToTpmSimulator@TpmTransportType@@0HA, 0; int TpmTransportType::m_TalkingToTpmSimulator
0x1400168c3  jz      loc_14001698A
0x1400168c9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400168d0  lea     r13, WPP_GLOBAL_Control
0x1400168d7  cmp     rcx, r13
0x1400168da  jz      short loc_140016905
0x1400168dc  mov     eax, [rcx+2Ch]
0x1400168df  test    dl, al
0x1400168e1  jz      short loc_140016905
0x1400168e3  mov     rcx, [rcx+18h]
0x1400168e7  mov     edx, 0Fh
0x1400168ec  movzx   eax, di
0x1400168ef  mov     r9d, esi
0x1400168f2  mov     [rsp+70h+InputBufferLength], eax
0x1400168f6  mov     [rsp+70h+var_48], r8d
0x1400168fb  mov     [rsp+70h+var_50], r15d
0x140016900  call    WPP_SF_LLDD
0x140016905  mov     r12, [rbp+arg_28]
0x140016909  lea     rax, [rbp+arg_30]
0x14001690d  mov     ebx, [rbp+arg_20]
0x140016910  mov     r9d, r15d
0x140016913  mov     rdx, [rbp+arg_8]
0x140016917  mov     r8d, esi
0x14001691a  mov     rcx, [rbp+arg_0]
0x14001691e  mov     [rsp+70h+var_38], rax
0x140016923  mov     qword ptr [rsp+70h+InputBufferLength], r12
0x140016928  mov     word ptr [rsp+70h+var_48], di
0x14001692d  mov     [rsp+70h+var_50], ebx
0x140016931  call    TpmCall20EmulatedDSMMethod
0x140016936  mov     ebx, eax
0x140016938  test    eax, eax
0x14001693a  js      loc_140016A72
0x140016940  mov     rax, [rbp+arg_38]
0x140016944  mov     edx, [rbp+arg_30]
0x140016947  mov     [rax], edx
0x140016949  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140016950  cmp     rcx, r13
0x140016953  jz      loc_140016A72
0x140016959  mov     eax, [rcx+2Ch]
0x14001695c  test    al, 20h
0x14001695e  jz      loc_140016A72
0x140016964  xorps   xmm0, xmm0
0x140016967  movups  [rbp+var_10], xmm0
0x14001696b  mov     word ptr [rbp+var_10+8], dx
0x14001696f  mov     edx, 10h
0x140016974  jmp     loc_140016A49
0x140016979  cmp     r13d, edx
0x14001697c  jmp     loc_1400168B0
0x140016981  cmp     r13d, 8
0x140016985  jmp     loc_1400168B0
0x14001698a  mov     edx, esi
0x14001698c  mov     rcx, r9; int
0x14001698f  call    TpmPpiCheckFirmwareSupportForDsmFunction
0x140016994  mov     ebx, eax
0x140016996  test    eax, eax
0x140016998  js      loc_140016A72
0x14001699e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400169a5  lea     rax, WPP_GLOBAL_Control
0x1400169ac  mov     ebx, [rbp+arg_20]
0x1400169af  cmp     rcx, rax
0x1400169b2  jz      short loc_1400169DC
0x1400169b4  mov     eax, [rcx+2Ch]
0x1400169b7  test    al, 4
0x1400169b9  jz      short loc_1400169DC
0x1400169bb  mov     rcx, [rcx+18h]
0x1400169bf  mov     edx, 11h
0x1400169c4  movzx   eax, di
0x1400169c7  mov     r9d, esi
0x1400169ca  mov     [rsp+70h+InputBufferLength], eax
0x1400169ce  mov     [rsp+70h+var_48], ebx
0x1400169d2  mov     [rsp+70h+var_50], r15d
0x1400169d7  call    WPP_SF_LLDD
0x1400169dc  mov     rax, [rbp+arg_38]
0x1400169e0  lea     rdx, PHYSICAL_PRESENCE_INTERFACE_GUID; int
0x1400169e7  mov     r12, [rbp+arg_28]
0x1400169eb  mov     r9d, esi; int
0x1400169ee  mov     r8d, dword ptr [rbp+var_20]; int
0x1400169f2  mov     rcx, qword ptr [rbp+arg_10]; int
0x1400169f6  mov     [rsp+70h+var_28], rax; __int64
0x1400169fb  mov     [rsp+70h+var_30], r13d; int
0x140016a00  mov     [rsp+70h+var_38], r12; __int64
0x140016a05  mov     word ptr [rsp+70h+InputBufferLength], di; InputBufferLength
0x140016a0a  mov     [rsp+70h+var_48], ebx; int
0x140016a0e  mov     [rsp+70h+var_50], r15d; int
0x140016a13  call    TpmCallDSMMethod
0x140016a18  mov     ebx, eax
0x140016a1a  test    eax, eax
0x140016a1c  js      short loc_140016A72
0x140016a1e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140016a25  lea     rax, WPP_GLOBAL_Control
0x140016a2c  cmp     rcx, rax
0x140016a2f  jz      short loc_140016A72
0x140016a31  mov     eax, [rcx+2Ch]
0x140016a34  test    al, 20h
0x140016a36  jz      short loc_140016A72
0x140016a38  xorps   xmm0, xmm0
0x140016a3b  mov     edx, 12h
0x140016a40  movups  [rbp+var_10], xmm0
0x140016a44  mov     word ptr [rbp+var_10+8], r13w
0x140016a49  mov     qword ptr [rbp+var_10], r12
0x140016a4d  movaps  xmm0, [rbp+var_10]
0x140016a51  lea     rax, [rbp+var_10]
0x140016a55  movdqa  [rbp+var_10], xmm0
0x140016a5a  lea     r8, WPP_5da39d5982eb3c55461d51d673252f3f_Traceguids
0x140016a61  mov     rcx, [rcx+18h]
0x140016a65  mov     r9d, esi
0x140016a68  mov     qword ptr [rsp+70h+var_50], rax
0x140016a6d  call    WPP_SF_L_HEX_
0x140016a72  test    ebx, ebx
0x140016a74  jz      short loc_140016AAC
0x140016a76  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140016a7d  lea     rax, WPP_GLOBAL_Control
0x140016a84  cmp     rcx, rax
0x140016a87  jz      short loc_140016AAC
0x140016a89  mov     eax, [rcx+2Ch]
0x140016a8c  test    al, 4
0x140016a8e  jz      short loc_140016AAC
0x140016a90  mov     rcx, [rcx+18h]
0x140016a94  lea     r8, WPP_5da39d5982eb3c55461d51d673252f3f_Traceguids
0x140016a9b  mov     edx, 13h
0x140016aa0  mov     [rsp+70h+var_50], ebx
0x140016aa4  mov     r9d, esi
0x140016aa7  call    WPP_SF_Dd
0x140016aac  mov     eax, ebx
0x140016aae  add     rsp, 70h
0x140016ab2  pop     r15
0x140016ab4  pop     r13
0x140016ab6  pop     r12
0x140016ab8  pop     rdi
0x140016ab9  pop     rsi
0x140016aba  pop     rbx
0x140016abb  pop     rbp
  ... truncated ...
```
