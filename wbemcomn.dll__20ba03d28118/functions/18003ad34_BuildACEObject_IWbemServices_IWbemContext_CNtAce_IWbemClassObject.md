# BuildACEObject(IWbemServices *,IWbemContext *,CNtAce *,IWbemClassObject * *)

- ea: `0x18003ad34`
- end: `0x18003b20a`
- name: `?BuildACEObject@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAVCNtAce@@PEAPEAUIWbemClassObject@@@Z`
- size: `1238`
- prototype: `__int64 __fastcall(struct IWbemServices *, struct IWbemContext *, struct CNtAce *this, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003b210`

## callees

- `0x180013564`
- `0x180014120`
- `0x18001c010`
- `0x18001c2d0`
- `0x18001c5a0`
- `0x18001c6d0`
- `0x180028484`
- `0x18003ac1c`
- `0x18003ad34`
- `0x18003bd60`
- `0x18003cab0`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003ae56`
- `OLEAUT32!__imp_VariantInit` at `0x18003ae56`

## string_xrefs

- `0x18003ae89`: `AccessMask`

## pseudocode

```c
__int64 __fastcall BuildACEObject(
        struct IWbemServices *a1,
        struct IWbemContext *a2,
        struct CNtAce *this,
        struct IWbemClassObject **a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // r10
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  _QWORD *v14; // r10
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  CNtSid *Sid; // rax
  int v20; // eax
  unsigned int v21; // edx
  _QWORD *v22; // r10
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  struct IWbemClassObject *v27; // rax
  struct IWbemClassObject *v29; // [rsp+40h] [rbp-30h] BYREF
  __int64 v30; // [rsp+48h] [rbp-28h] BYREF
  CNtSid *v31; // [rsp+50h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  struct IWbemClassObject *v33; // [rsp+A0h] [rbp+30h] BYREF

  v30 = 0;
  v33 = 0;
  v8 = ((__int64 (__fastcall *)(struct IWbemServices *, const wchar_t *, _QWORD, struct IWbemContext *, __int64 *, _QWORD))a1->lpVtbl->GetObjectA)(
         a1,
         L"__ACE",
         0,
         a2,
         &v30,
         0);
  v9 = v8;
  if ( v8 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 33;
LABEL_6:
      WPP_SF_D(v10[2], v11, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWbemClassObject **))(*(_QWORD *)v30 + 120LL))(v30, 0, &v33);
  v9 = v12;
  if ( v12 >= 0 )
  {
    VariantInit(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = CNtAce::GetAccessMask(this);
    v13 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v33->lpVtbl->Put)(
            v33,
            L"AccessMask",
            0,
            &pvarg,
            0);
    v9 = v13;
    if ( v13 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v13);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_54;
      }
      v15 = 35;
      goto LABEL_17;
    }
    pvarg.vt = 3;
    pvarg.lVal = CNtAce::GetFlags(this);
    v17 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v33->lpVtbl->Put)(
            v33,
            L"AceFlags",
            0,
            &pvarg,
            0);
    v9 = v17;
    if ( v17 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v17);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_54;
      }
      v15 = 36;
LABEL_17:
      v16 = v14[2];
LABEL_28:
      WPP_SF_D(v16, v15, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
LABEL_54:
      _variant_t::~_variant_t(&pvarg);
      goto LABEL_55;
    }
    pvarg.vt = 3;
    pvarg.lVal = CNtAce::GetType(this);
    v18 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v33->lpVtbl->Put)(
            v33,
            L"AceType",
            0,
            &pvarg,
            0);
    v9 = v18;
    if ( v18 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v18);
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_54;
      }
      v15 = 37;
      v16 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      goto LABEL_28;
    }
    v29 = 0;
    Sid = CNtAce::GetSid(this);
    if ( !Sid )
    {
      v9 = -2147217402;
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217402);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749894LL);
      }
      goto LABEL_53;
    }
    v31 = Sid;
    v20 = BuildTrusteeObject(a1, a2, Sid, &v29);
    v9 = v20;
    if ( v20 >= 0 )
    {
      pvarg.vt = 13;
      v25 = ((__int64 (__fastcall *)(struct IWbemClassObject *, GUID *, ULONG *))v29->lpVtbl->QueryInterface)(
              v29,
              &IID_IUnknown,
              &pvarg.decVal.Lo32);
      v9 = v25;
      if ( v25 >= 0 )
      {
        v26 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v33->lpVtbl->Put)(
                v33,
                L"Trustee",
                0,
                &pvarg,
                0);
        v9 = v26;
        if ( v26 >= 0 )
        {
          v27 = v33;
          v33 = 0;
          *a4 = v27;
          goto LABEL_52;
        }
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v26);
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_52;
        }
        v23 = 41;
        v24 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_40:
        WPP_SF_D(v24, v23, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
LABEL_52:
        CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v31, v21);
LABEL_53:
        _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v29);
        goto LABEL_54;
      }
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v25);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_52;
      }
      v23 = 40;
    }
    else
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v20);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_52;
      }
      v23 = 39;
    }
    v24 = v22[2];
    goto LABEL_40;
  }
  CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v12);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 34;
    goto LABEL_6;
  }
LABEL_55:
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v33);
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v30);
  return v9;
}

```

## disassembly

```asm
0x18003ad34  mov     r11, rsp
0x18003ad37  mov     [r11+10h], rbx
0x18003ad3b  mov     [r11+18h], rsi
0x18003ad3f  push    rbp
0x18003ad40  push    rdi
0x18003ad41  push    r13
0x18003ad43  push    r14
0x18003ad45  push    r15
0x18003ad47  mov     rbp, rsp
0x18003ad4a  sub     rsp, 70h
0x18003ad4e  mov     r15, r9
0x18003ad51  mov     rdi, r8
0x18003ad54  mov     r14, rdx
0x18003ad57  mov     rsi, rcx
0x18003ad5a  mov     [rbp+var_28], 0
0x18003ad62  mov     [rbp+arg_0], 0
0x18003ad6a  mov     rax, [rcx]
0x18003ad6d  mov     qword ptr [r11-70h], 0
0x18003ad75  lea     rcx, [rbp+var_28]
0x18003ad79  mov     [r11-78h], rcx
0x18003ad7d  mov     r9, rdx
0x18003ad80  xor     r8d, r8d
0x18003ad83  lea     rdx, aAce; "__ACE"
0x18003ad8a  mov     rcx, rsi
0x18003ad8d  mov     rax, [rax+30h]
0x18003ad91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad96  mov     ebx, eax
0x18003ad98  test    eax, eax
0x18003ad9a  jns     short loc_18003ADF4
0x18003ad9c  mov     edx, eax; int
0x18003ad9e  lea     rcx, qword_18006A9C0; this
0x18003ada5  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003adaa  lea     rcx, WPP_GLOBAL_Control
0x18003adb1  mov     r10, cs:WPP_GLOBAL_Control
0x18003adb8  cmp     r10, rcx
0x18003adbb  jz      loc_18003B1DC
0x18003adc1  test    byte ptr [r10+1Ch], 1
0x18003adc6  jz      loc_18003B1DC
0x18003adcc  cmp     byte ptr [r10+19h], 2
0x18003add1  jb      loc_18003B1DC
0x18003add7  mov     edx, 21h ; '!'
0x18003addc  mov     r9d, ebx
0x18003addf  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003ade6  mov     rcx, [r10+10h]
0x18003adea  call    WPP_SF_D
0x18003adef  jmp     loc_18003B1DC
0x18003adf4  mov     rcx, [rbp+var_28]
0x18003adf8  mov     rax, [rcx]
0x18003adfb  lea     r8, [rbp+arg_0]
0x18003adff  xor     edx, edx
0x18003ae01  mov     rax, [rax+78h]
0x18003ae05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae0a  mov     ebx, eax
0x18003ae0c  test    eax, eax
0x18003ae0e  jns     short loc_18003AE52
0x18003ae10  mov     edx, eax; int
0x18003ae12  lea     rcx, qword_18006A9C0; this
0x18003ae19  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ae1e  lea     rcx, WPP_GLOBAL_Control
0x18003ae25  mov     r10, cs:WPP_GLOBAL_Control
0x18003ae2c  cmp     r10, rcx
0x18003ae2f  jz      loc_18003B1DC
0x18003ae35  test    byte ptr [r10+1Ch], 1
0x18003ae3a  jz      loc_18003B1DC
0x18003ae40  cmp     byte ptr [r10+19h], 2
0x18003ae45  jb      loc_18003B1DC
0x18003ae4b  mov     edx, 22h ; '"'
0x18003ae50  jmp     short loc_18003ADDC
0x18003ae52  lea     rcx, [rbp+pvarg]; pvarg
0x18003ae56  call    cs:__imp_VariantInit
0x18003ae5c  nop
0x18003ae5d  mov     r13d, 3
0x18003ae63  mov     word ptr [rbp+pvarg], r13w
0x18003ae68  mov     rcx, rdi; this
0x18003ae6b  call    ?GetAccessMask@CNtAce@@UEAAKXZ; CNtAce::GetAccessMask(void)
0x18003ae70  mov     dword ptr [rbp+pvarg+8], eax
0x18003ae73  mov     rcx, [rbp+arg_0]
0x18003ae77  mov     rax, [rcx]
0x18003ae7a  mov     [rsp+70h+var_50], 0
0x18003ae82  lea     r9, [rbp+pvarg]
0x18003ae86  xor     r8d, r8d
0x18003ae89  lea     rdx, aAccessmask; "AccessMask"
0x18003ae90  mov     rax, [rax+28h]
0x18003ae94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae99  mov     ebx, eax
0x18003ae9b  test    eax, eax
0x18003ae9d  jns     short loc_18003AEE7
0x18003ae9f  mov     edx, eax; int
0x18003aea1  lea     rcx, qword_18006A9C0; this
0x18003aea8  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003aead  lea     rcx, WPP_GLOBAL_Control
0x18003aeb4  mov     r10, cs:WPP_GLOBAL_Control
0x18003aebb  cmp     r10, rcx
0x18003aebe  jz      loc_18003B1D2
0x18003aec4  test    byte ptr [r10+1Ch], 1
0x18003aec9  jz      loc_18003B1D2
0x18003aecf  cmp     byte ptr [r10+19h], 2
0x18003aed4  jb      loc_18003B1D2
0x18003aeda  lea     edx, [r13+20h]
0x18003aede  mov     rcx, [r10+10h]
0x18003aee2  jmp     loc_18003AFE6
0x18003aee7  mov     word ptr [rbp+pvarg], r13w
0x18003aeec  mov     rcx, rdi; this
0x18003aeef  call    ?GetFlags@CNtAce@@UEAAHXZ; CNtAce::GetFlags(void)
0x18003aef4  mov     dword ptr [rbp+pvarg+8], eax
0x18003aef7  mov     rcx, [rbp+arg_0]
0x18003aefb  mov     rax, [rcx]
0x18003aefe  mov     [rsp+70h+var_50], 0
0x18003af06  lea     r9, [rbp+pvarg]
0x18003af0a  xor     r8d, r8d
0x18003af0d  lea     rdx, aAceflags; "AceFlags"
0x18003af14  mov     rax, [rax+28h]
0x18003af18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af1d  mov     ebx, eax
0x18003af1f  test    eax, eax
0x18003af21  jns     short loc_18003AF68
0x18003af23  mov     edx, eax; int
0x18003af25  lea     rcx, qword_18006A9C0; this
0x18003af2c  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003af31  lea     rcx, WPP_GLOBAL_Control
0x18003af38  mov     r10, cs:WPP_GLOBAL_Control
0x18003af3f  cmp     r10, rcx
0x18003af42  jz      loc_18003B1D2
0x18003af48  test    byte ptr [r10+1Ch], 1
0x18003af4d  jz      loc_18003B1D2
0x18003af53  cmp     byte ptr [r10+19h], 2
0x18003af58  jb      loc_18003B1D2
0x18003af5e  mov     edx, 24h ; '$'
0x18003af63  jmp     loc_18003AEDE
0x18003af68  mov     word ptr [rbp+pvarg], r13w
0x18003af6d  mov     rcx, rdi; this
0x18003af70  call    ?GetType@CNtAce@@UEAAHXZ; CNtAce::GetType(void)
0x18003af75  mov     dword ptr [rbp+pvarg+8], eax
0x18003af78  mov     rcx, [rbp+arg_0]
0x18003af7c  mov     rax, [rcx]
0x18003af7f  mov     [rsp+70h+var_50], 0
0x18003af87  lea     r9, [rbp+pvarg]
0x18003af8b  xor     r8d, r8d
0x18003af8e  lea     rdx, aAcetype; "AceType"
0x18003af95  mov     rax, [rax+28h]
0x18003af99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af9e  mov     ebx, eax
0x18003afa0  test    eax, eax
0x18003afa2  jns     short loc_18003AFFA
0x18003afa4  mov     edx, eax; int
0x18003afa6  lea     rcx, qword_18006A9C0; this
0x18003afad  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003afb2  lea     rcx, WPP_GLOBAL_Control
0x18003afb9  mov     rax, cs:WPP_GLOBAL_Control
0x18003afc0  cmp     rax, rcx
0x18003afc3  jz      loc_18003B1D2
0x18003afc9  test    byte ptr [rax+1Ch], 1
0x18003afcd  jz      loc_18003B1D2
0x18003afd3  cmp     byte ptr [rax+19h], 2
0x18003afd7  jb      loc_18003B1D2
0x18003afdd  mov     edx, 25h ; '%'
0x18003afe2  mov     rcx, [rax+10h]
0x18003afe6  mov     r9d, ebx
0x18003afe9  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003aff0  call    WPP_SF_D
0x18003aff5  jmp     loc_18003B1D2
0x18003affa  mov     [rbp+var_30], 0
0x18003b002  mov     rcx, rdi; this
0x18003b005  call    ?GetSid@CNtAce@@QEAAPEAVCNtSid@@XZ; CNtAce::GetSid(void)
0x18003b00a  test    rax, rax
0x18003b00d  jnz     short loc_18003B06D
0x18003b00f  mov     ebx, 80041006h
0x18003b014  mov     edx, ebx; int
0x18003b016  lea     rcx, qword_18006A9C0; this
0x18003b01d  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b022  lea     rcx, WPP_GLOBAL_Control
0x18003b029  mov     rax, cs:WPP_GLOBAL_Control
0x18003b030  cmp     rax, rcx
0x18003b033  jz      loc_18003B1C8
0x18003b039  test    byte ptr [rax+1Ch], 1
0x18003b03d  jz      loc_18003B1C8
0x18003b043  cmp     byte ptr [rax+19h], 2
0x18003b047  jb      loc_18003B1C8
0x18003b04d  mov     edx, 26h ; '&'
0x18003b052  mov     r9d, 80041006h
0x18003b058  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003b05f  mov     rcx, [rax+10h]
0x18003b063  call    WPP_SF_D
0x18003b068  jmp     loc_18003B1C8
0x18003b06d  mov     [rbp+var_20], rax
0x18003b071  lea     r9, [rbp+var_30]; struct IWbemClassObject **
0x18003b075  mov     r8, rax; struct CNtSid *
0x18003b078  mov     rdx, r14; struct IWbemContext *
0x18003b07b  mov     rcx, rsi; struct IWbemServices *
0x18003b07e  call    ?BuildTrusteeObject@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAVCNtSid@@PEAPEAUIWbemClassObject@@@Z; BuildTrusteeObject(IWbemServices *,IWbemContext *,CNtSid *,IWbemClassObject * *)
0x18003b083  mov     ebx, eax
0x18003b085  test    eax, eax
0x18003b087  jns     short loc_18003B0E1
0x18003b089  mov     edx, eax; int
0x18003b08b  lea     rcx, qword_18006A9C0; this
0x18003b092  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b097  lea     rcx, WPP_GLOBAL_Control
0x18003b09e  mov     r10, cs:WPP_GLOBAL_Control
0x18003b0a5  cmp     r10, rcx
0x18003b0a8  jz      loc_18003B1BE
0x18003b0ae  test    byte ptr [r10+1Ch], 1
0x18003b0b3  jz      loc_18003B1BE
0x18003b0b9  cmp     byte ptr [r10+19h], 2
0x18003b0be  jb      loc_18003B1BE
0x18003b0c4  mov     edx, 27h ; '''
0x18003b0c9  mov     rcx, [r10+10h]
0x18003b0cd  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003b0d4  mov     r9d, ebx
0x18003b0d7  call    WPP_SF_D
0x18003b0dc  jmp     loc_18003B1BE
0x18003b0e1  mov     eax, 0Dh
0x18003b0e6  mov     word ptr [rbp+pvarg], ax
0x18003b0ea  mov     rcx, [rbp+var_30]
0x18003b0ee  mov     rax, [rcx]
0x18003b0f1  lea     r8, [rbp+pvarg+8]
0x18003b0f5  lea     rdx, IID_IUnknown
0x18003b0fc  mov     rax, [rax]
0x18003b0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b104  mov     ebx, eax
0x18003b106  test    eax, eax
0x18003b108  jns     short loc_18003B148
0x18003b10a  mov     edx, eax; int
0x18003b10c  lea     rcx, qword_18006A9C0; this
0x18003b113  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b118  lea     rcx, WPP_GLOBAL_Control
0x18003b11f  mov     r10, cs:WPP_GLOBAL_Control
0x18003b126  cmp     r10, rcx
0x18003b129  jz      loc_18003B1BE
0x18003b12f  test    byte ptr [r10+1Ch], 1
0x18003b134  jz      loc_18003B1BE
0x18003b13a  cmp     byte ptr [r10+19h], 2
0x18003b13f  jb      short loc_18003B1BE
0x18003b141  mov     edx, 28h ; '('
0x18003b146  jmp     short loc_18003B0C9
0x18003b148  mov     rcx, [rbp+arg_0]
0x18003b14c  mov     rax, [rcx]
0x18003b14f  mov     [rsp+70h+var_50], 0
0x18003b157  lea     r9, [rbp+pvarg]
0x18003b15b  xor     r8d, r8d
0x18003b15e  lea     rdx, aTrustee_0; "Trustee"
0x18003b165  mov     rax, [rax+28h]
0x18003b169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b16e  mov     ebx, eax
0x18003b170  test    eax, eax
0x18003b172  jns     short loc_18003B1AF
0x18003b174  mov     edx, eax; int
0x18003b176  lea     rcx, qword_18006A9C0; this
0x18003b17d  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b182  lea     rcx, WPP_GLOBAL_Control
0x18003b189  mov     rax, cs:WPP_GLOBAL_Control
0x18003b190  cmp     rax, rcx
0x18003b193  jz      short loc_18003B1BE
0x18003b195  test    byte ptr [rax+1Ch], 1
0x18003b199  jz      short loc_18003B1BE
0x18003b19b  cmp     byte ptr [rax+19h], 2
0x18003b19f  jb      short loc_18003B1BE
0x18003b1a1  mov     edx, 29h ; ')'
0x18003b1a6  mov     rcx, [rax+10h]
0x18003b1aa  jmp     loc_18003B0CD
0x18003b1af  mov     rax, [rbp+arg_0]
0x18003b1b3  mov     [rbp+arg_0], 0
0x18003b1bb  mov     [r15], rax
0x18003b1be  lea     rcx, [rbp+var_20]
0x18003b1c2  call    ??1?$CDeleteMe@VCNtSid@@@@QEAA@XZ; CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(void)
0x18003b1c7  nop
0x18003b1c8  lea     rcx, [rbp+var_30]
0x18003b1cc  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003b1d1  nop
0x18003b1d2  lea     rcx, [rbp+pvarg]; this
0x18003b1d6  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003b1db  nop
0x18003b1dc  lea     rcx, [rbp+arg_0]
0x18003b1e0  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003b1e5  nop
0x18003b1e6  lea     rcx, [rbp+var_28]
0x18003b1ea  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003b1ef  mov     eax, ebx
0x18003b1f1  lea     r11, [rsp+70h+var_s0]
0x18003b1f6  mov     rbx, [r11+38h]
0x18003b1fa  mov     rsi, [r11+40h]
0x18003b1fe  mov     rsp, r11
0x18003b201  pop     r15
0x18003b203  pop     r14
0x18003b205  pop     r13
0x18003b207  pop     rdi
0x18003b208  pop     rbp
0x18003b209  retn
```
