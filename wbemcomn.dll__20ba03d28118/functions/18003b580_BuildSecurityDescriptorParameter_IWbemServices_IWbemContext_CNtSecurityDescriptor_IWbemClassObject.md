# BuildSecurityDescriptorParameter(IWbemServices *,IWbemContext *,CNtSecurityDescriptor *,IWbemClassObject *)

- ea: `0x18003b580`
- end: `0x18003bd58`
- name: `?BuildSecurityDescriptorParameter@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAVCNtSecurityDescriptor@@PEAUIWbemClassObject@@@Z`
- size: `2008`
- prototype: `__int64 __fastcall(struct IWbemServices *, struct IWbemContext *, void **this, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180013564`
- `0x180014120`
- `0x18001c010`
- `0x18001c790`
- `0x180025974`
- `0x180028484`
- `0x18002cc00`
- `0x18003ac1c`
- `0x18003b210`
- `0x18003b580`
- `0x18003bd60`
- `0x18003cef0`
- `0x18003d1d0`
- `0x18003d280`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b6b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b6b0`
- `OLEAUT32!__imp_VariantInit` at `0x18003b723`
- `OLEAUT32!__imp_VariantInit` at `0x18003b8a9`
- `OLEAUT32!__imp_VariantInit` at `0x18003ba2b`
- `OLEAUT32!__imp_VariantInit` at `0x18003bc34`
- `OLEAUT32!__imp_VariantInit` at `0x18003b723`
- `OLEAUT32!__imp_VariantInit` at `0x18003b8a9`
- `OLEAUT32!__imp_VariantInit` at `0x18003ba2b`
- `OLEAUT32!__imp_VariantInit` at `0x18003bc34`

## string_xrefs

- `0x18003b5d5`: `__SecurityDescriptor`
- `0x18003bc62`: `Descriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BuildSecurityDescriptorParameter(
        struct IWbemServices *a1,
        struct IWbemContext *a2,
        void **this,
        struct IWbemClassObject *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  _QWORD *v13; // rax
  signed int LastError; // eax
  int v15; // eax
  CNtSid *Group; // rax
  int v17; // eax
  unsigned int v18; // edx
  int v19; // eax
  _QWORD *v20; // r10
  __int64 v21; // rdx
  int v22; // eax
  int v23; // eax
  unsigned int v24; // edx
  int v25; // eax
  _QWORD *v26; // r10
  __int64 v27; // rdx
  int v28; // eax
  int v29; // eax
  unsigned int v30; // edx
  int v31; // eax
  unsigned int v32; // edx
  struct IWbemClassObject *v33; // rax
  int v34; // eax
  struct IWbemClassObject *v36; // [rsp+40h] [rbp-79h] BYREF
  struct IWbemClassObject *v37; // [rsp+48h] [rbp-71h] BYREF
  CNtSid *v38; // [rsp+50h] [rbp-69h] BYREF
  struct IWbemClassObject *v39; // [rsp+58h] [rbp-61h] BYREF
  CNtSid *Owner; // [rsp+60h] [rbp-59h] BYREF
  __int64 v41; // [rsp+68h] [rbp-51h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-49h] BYREF
  unsigned int v43; // [rsp+88h] [rbp-31h] BYREF
  CNtAcl *Dacl; // [rsp+90h] [rbp-29h] BYREF
  VARIANTARG v45; // [rsp+98h] [rbp-21h] BYREF
  CNtAcl *Sacl; // [rsp+B0h] [rbp-9h] BYREF
  VARIANTARG v47; // [rsp+B8h] [rbp-1h] BYREF
  VARIANTARG v48; // [rsp+D0h] [rbp+17h] BYREF
  unsigned __int16 v49; // [rsp+120h] [rbp+67h] BYREF

  v41 = 0;
  v37 = 0;
  v8 = ((__int64 (__fastcall *)(struct IWbemServices *, const wchar_t *, _QWORD, struct IWbemContext *, __int64 *, _QWORD))a1->lpVtbl->GetObjectA)(
         a1,
         L"__SecurityDescriptor",
         0,
         a2,
         &v41,
         0);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWbemClassObject **))(*(_QWORD *)v41 + 120LL))(
            v41,
            0,
            &v37);
    v9 = v12;
    if ( v12 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v12);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v10 = 49;
      goto LABEL_20;
    }
    v49 = 0;
    v43 = 0;
    if ( !(unsigned int)DLGetSecurityDescriptorControl(*this, &v49, &v43) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (v9 & 0x80000000) != 0 )
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v9);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v10 = 50;
LABEL_20:
      v11 = v13[2];
      goto LABEL_21;
    }
    VariantInit(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = v49;
    v15 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v37->lpVtbl->Put)(
            v37,
            L"ControlFlags",
            0,
            &pvarg,
            0);
    v9 = v15;
    if ( v15 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v15);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
      }
      goto LABEL_88;
    }
    v36 = 0;
    Group = CNtSecurityDescriptor::GetGroup((CNtSecurityDescriptor *)this);
    if ( !Group )
    {
      v9 = -2147217407;
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217407);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749889LL);
      }
      goto LABEL_87;
    }
    v38 = Group;
    v17 = BuildTrusteeObject(a1, a2, Group, &v36);
    v9 = v17;
    if ( v17 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v17);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
      }
      goto LABEL_86;
    }
    VariantInit(&v45);
    v45.vt = 13;
    v19 = ((__int64 (__fastcall *)(struct IWbemClassObject *, GUID *, ULONG *))v36->lpVtbl->QueryInterface)(
            v36,
            &IID_IUnknown,
            &v45.decVal.Lo32);
    v9 = v19;
    if ( v19 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v19);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      v21 = 54;
      goto LABEL_42;
    }
    v22 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v37->lpVtbl->Put)(
            v37,
            L"Group",
            0,
            &v45,
            0);
    v9 = v22;
    if ( v22 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v22);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      v21 = 55;
LABEL_42:
      WPP_SF_D(v20[2], v21, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
LABEL_85:
      _variant_t::~_variant_t(&v45);
LABEL_86:
      CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v38, v18);
LABEL_87:
      _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v36);
LABEL_88:
      _variant_t::~_variant_t(&pvarg);
      goto LABEL_89;
    }
    v39 = 0;
    Owner = CNtSecurityDescriptor::GetOwner((CNtSecurityDescriptor *)this);
    v23 = BuildTrusteeObject(a1, a2, Owner, &v39);
    v9 = v23;
    if ( v23 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v23);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
      }
      goto LABEL_84;
    }
    VariantInit(&v47);
    v47.vt = 13;
    v25 = ((__int64 (__fastcall *)(struct IWbemClassObject *, GUID *, ULONG *))v39->lpVtbl->QueryInterface)(
            v39,
            &IID_IUnknown,
            &v47.decVal.Lo32);
    v9 = v25;
    if ( v25 >= 0 )
    {
      v28 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v37->lpVtbl->Put)(
              v37,
              L"Owner",
              0,
              &v47,
              0);
      v9 = v28;
      if ( v28 >= 0 )
      {
        Dacl = CNtSecurityDescriptor::GetDacl((CNtSecurityDescriptor *)this);
        v29 = BuildACLObject(a1, L"DACL", a2, Dacl, v37);
        v9 = v29;
        if ( v29 >= 0 )
        {
          Sacl = CNtSecurityDescriptor::GetSacl((CNtSecurityDescriptor *)this);
          v31 = BuildACLObject(a1, L"SACL", a2, Sacl, v37);
          v9 = v31;
          if ( v31 >= 0 )
          {
            VariantInit(&v48);
            v48.vt = 13;
            v33 = v37;
            v37 = 0;
            v48.llVal = (LONGLONG)v33;
            v34 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))a4->lpVtbl->Put)(
                    a4,
                    L"Descriptor",
                    0,
                    &v48,
                    0);
            v9 = v34;
            if ( v34 < 0 )
              CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v34);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
            }
            _variant_t::~_variant_t(&v48);
          }
          else
          {
            CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v31);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
            }
          }
          CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&Sacl, v32);
        }
        else
        {
          CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v29);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
          }
        }
        CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&Dacl, v30);
        goto LABEL_83;
      }
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v28);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_83:
        _variant_t::~_variant_t(&v47);
LABEL_84:
        CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&Owner, v24);
        _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v39);
        goto LABEL_85;
      }
      v27 = 58;
    }
    else
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v25);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_83;
      }
      v27 = 57;
    }
    WPP_SF_D(v26[2], v27, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
    goto LABEL_83;
  }
  CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 48;
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_21:
    WPP_SF_D(v11, v10, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
  }
LABEL_89:
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v37);
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v41);
  return v9;
}

```

## disassembly

```asm
0x18003b580  mov     [rsp-8+arg_8], rbx
0x18003b585  mov     [rsp-8+arg_10], rsi
0x18003b58a  push    rbp
0x18003b58b  push    rdi
0x18003b58c  push    r13
0x18003b58e  push    r14
0x18003b590  push    r15
0x18003b592  lea     rbp, [rsp-37h]
0x18003b597  sub     rsp, 0F0h
0x18003b59e  mov     r15, r9
0x18003b5a1  mov     rdi, r8
0x18003b5a4  mov     r14, rdx
0x18003b5a7  mov     rsi, rcx
0x18003b5aa  mov     [rbp+57h+var_A8], 0
0x18003b5b2  mov     [rbp+57h+var_C8], 0
0x18003b5ba  mov     rax, [rcx]
0x18003b5bd  mov     [rsp+110h+var_E8], 0
0x18003b5c6  lea     rcx, [rbp+57h+var_A8]
0x18003b5ca  mov     [rsp+110h+var_F0], rcx
0x18003b5cf  mov     r9, rdx
0x18003b5d2  xor     r8d, r8d
0x18003b5d5  lea     rdx, aSecuritydescri; "__SecurityDescriptor"
0x18003b5dc  mov     rcx, rsi
0x18003b5df  mov     rax, [rax+30h]
0x18003b5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5e8  mov     ebx, eax
0x18003b5ea  test    eax, eax
0x18003b5ec  jns     short loc_18003B637
0x18003b5ee  mov     edx, eax; int
0x18003b5f0  lea     rcx, qword_18006A9C0; this
0x18003b5f7  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b5fc  lea     rcx, WPP_GLOBAL_Control
0x18003b603  mov     r10, cs:WPP_GLOBAL_Control
0x18003b60a  cmp     r10, rcx
0x18003b60d  jz      loc_18003BD27
0x18003b613  test    byte ptr [r10+1Ch], 1
0x18003b618  jz      loc_18003BD27
0x18003b61e  cmp     byte ptr [r10+19h], 2
0x18003b623  jb      loc_18003BD27
0x18003b629  mov     edx, 30h ; '0'
0x18003b62e  mov     rcx, [r10+10h]
0x18003b632  jmp     loc_18003B70B
0x18003b637  mov     rcx, [rbp+57h+var_A8]
0x18003b63b  mov     rax, [rcx]
0x18003b63e  lea     r8, [rbp+57h+var_C8]
0x18003b642  xor     edx, edx
0x18003b644  mov     rax, [rax+78h]
0x18003b648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b64d  mov     ebx, eax
0x18003b64f  test    eax, eax
0x18003b651  jns     short loc_18003B693
0x18003b653  mov     edx, eax; int
0x18003b655  lea     rcx, qword_18006A9C0; this
0x18003b65c  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b661  lea     rcx, WPP_GLOBAL_Control
0x18003b668  mov     rax, cs:WPP_GLOBAL_Control
0x18003b66f  cmp     rax, rcx
0x18003b672  jz      loc_18003BD27
0x18003b678  test    byte ptr [rax+1Ch], 1
0x18003b67c  jz      loc_18003BD27
0x18003b682  cmp     byte ptr [rax+19h], 2
0x18003b686  jb      loc_18003BD27
0x18003b68c  mov     edx, 31h ; '1'
0x18003b691  jmp     short loc_18003B707
0x18003b693  xor     eax, eax
0x18003b695  mov     [rbp+57h+arg_0], ax
0x18003b699  mov     [rbp+57h+var_88], eax
0x18003b69c  lea     r8, [rbp+57h+var_88]; unsigned int *
0x18003b6a0  lea     rdx, [rbp+57h+arg_0]; unsigned __int16 *
0x18003b6a4  mov     rcx, [rdi]; void *
0x18003b6a7  call    ?DLGetSecurityDescriptorControl@@YAHPEAXPEAGPEAK@Z; DLGetSecurityDescriptorControl(void *,ushort *,ulong *)
0x18003b6ac  test    eax, eax
0x18003b6ae  jnz     short loc_18003B71F
0x18003b6b0  call    cs:__imp_GetLastError
0x18003b6b6  mov     ebx, eax
0x18003b6b8  test    eax, eax
0x18003b6ba  jle     short loc_18003B6C5
0x18003b6bc  movzx   ebx, ax
0x18003b6bf  or      ebx, 80070000h
0x18003b6c5  test    ebx, ebx
0x18003b6c7  jns     short loc_18003B6D7
0x18003b6c9  mov     edx, ebx; int
0x18003b6cb  lea     rcx, qword_18006A9C0; this
0x18003b6d2  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b6d7  lea     rcx, WPP_GLOBAL_Control
0x18003b6de  mov     rax, cs:WPP_GLOBAL_Control
0x18003b6e5  cmp     rax, rcx
0x18003b6e8  jz      loc_18003BD27
0x18003b6ee  test    byte ptr [rax+1Ch], 1
0x18003b6f2  jz      loc_18003BD27
0x18003b6f8  cmp     byte ptr [rax+19h], 2
0x18003b6fc  jb      loc_18003BD27
0x18003b702  mov     edx, 32h ; '2'
0x18003b707  mov     rcx, [rax+10h]
0x18003b70b  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003b712  mov     r9d, ebx
0x18003b715  call    WPP_SF_D
0x18003b71a  jmp     loc_18003BD27
0x18003b71f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003b723  call    cs:__imp_VariantInit
0x18003b729  nop
0x18003b72a  mov     eax, 3
0x18003b72f  mov     word ptr [rbp+57h+pvarg], ax
0x18003b733  movzx   eax, [rbp+57h+arg_0]
0x18003b737  mov     dword ptr [rbp+57h+pvarg+8], eax
0x18003b73a  mov     rcx, [rbp+57h+var_C8]
0x18003b73e  mov     rax, [rcx]
0x18003b741  mov     dword ptr [rsp+110h+var_F0], 0
0x18003b749  lea     r9, [rbp+57h+pvarg]
0x18003b74d  xor     r8d, r8d
0x18003b750  lea     rdx, aControlflags; "ControlFlags"
0x18003b757  mov     rax, [rax+28h]
0x18003b75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b760  mov     ebx, eax
0x18003b762  test    eax, eax
0x18003b764  jns     short loc_18003B7BE
0x18003b766  mov     edx, eax; int
0x18003b768  lea     rcx, qword_18006A9C0; this
0x18003b76f  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b774  lea     rcx, WPP_GLOBAL_Control
0x18003b77b  mov     r10, cs:WPP_GLOBAL_Control
0x18003b782  cmp     r10, rcx
0x18003b785  jz      loc_18003BD1D
0x18003b78b  test    byte ptr [r10+1Ch], 1
0x18003b790  jz      loc_18003BD1D
0x18003b796  cmp     byte ptr [r10+19h], 2
0x18003b79b  jb      loc_18003BD1D
0x18003b7a1  mov     edx, 33h ; '3'
0x18003b7a6  mov     r9d, ebx
0x18003b7a9  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003b7b0  mov     rcx, [r10+10h]
0x18003b7b4  call    WPP_SF_D
0x18003b7b9  jmp     loc_18003BD1D
0x18003b7be  mov     [rbp+57h+var_D0], 0
0x18003b7c6  mov     rcx, rdi; this
0x18003b7c9  call    ?GetGroup@CNtSecurityDescriptor@@QEAAPEAVCNtSid@@XZ; CNtSecurityDescriptor::GetGroup(void)
0x18003b7ce  test    rax, rax
0x18003b7d1  jnz     short loc_18003B831
0x18003b7d3  mov     ebx, 80041001h
0x18003b7d8  mov     edx, ebx; int
0x18003b7da  lea     rcx, qword_18006A9C0; this
0x18003b7e1  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b7e6  lea     rcx, WPP_GLOBAL_Control
0x18003b7ed  mov     rax, cs:WPP_GLOBAL_Control
0x18003b7f4  cmp     rax, rcx
0x18003b7f7  jz      loc_18003BD13
0x18003b7fd  test    byte ptr [rax+1Ch], 1
0x18003b801  jz      loc_18003BD13
0x18003b807  cmp     byte ptr [rax+19h], 2
0x18003b80b  jb      loc_18003BD13
0x18003b811  mov     edx, 34h ; '4'
0x18003b816  mov     r9d, 80041001h
0x18003b81c  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003b823  mov     rcx, [rax+10h]
0x18003b827  call    WPP_SF_D
0x18003b82c  jmp     loc_18003BD13
0x18003b831  mov     [rbp+57h+var_C0], rax
0x18003b835  lea     r9, [rbp+57h+var_D0]; struct IWbemClassObject **
0x18003b839  mov     r8, rax; struct CNtSid *
0x18003b83c  mov     rdx, r14; struct IWbemContext *
0x18003b83f  mov     rcx, rsi; struct IWbemServices *
0x18003b842  call    ?BuildTrusteeObject@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAVCNtSid@@PEAPEAUIWbemClassObject@@@Z; BuildTrusteeObject(IWbemServices *,IWbemContext *,CNtSid *,IWbemClassObject * *)
0x18003b847  mov     ebx, eax
0x18003b849  test    eax, eax
0x18003b84b  jns     short loc_18003B8A5
0x18003b84d  mov     edx, eax; int
0x18003b84f  lea     rcx, qword_18006A9C0; this
0x18003b856  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b85b  lea     rcx, WPP_GLOBAL_Control
0x18003b862  mov     r10, cs:WPP_GLOBAL_Control
0x18003b869  cmp     r10, rcx
0x18003b86c  jz      loc_18003BD09
0x18003b872  test    byte ptr [r10+1Ch], 1
0x18003b877  jz      loc_18003BD09
0x18003b87d  cmp     byte ptr [r10+19h], 2
0x18003b882  jb      loc_18003BD09
0x18003b888  mov     edx, 35h ; '5'
0x18003b88d  mov     r9d, ebx
0x18003b890  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003b897  mov     rcx, [r10+10h]
0x18003b89b  call    WPP_SF_D
0x18003b8a0  jmp     loc_18003BD09
0x18003b8a5  lea     rcx, [rbp+57h+var_78]; pvarg
0x18003b8a9  call    cs:__imp_VariantInit
0x18003b8af  nop
0x18003b8b0  mov     r13d, 0Dh
0x18003b8b6  mov     word ptr [rbp+57h+var_78], r13w
0x18003b8bb  mov     rcx, [rbp+57h+var_D0]
0x18003b8bf  mov     rax, [rcx]
0x18003b8c2  lea     r8, [rbp+57h+var_78+8]
0x18003b8c6  lea     rdx, IID_IUnknown
0x18003b8cd  mov     rax, [rax]
0x18003b8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8d5  mov     ebx, eax
0x18003b8d7  test    eax, eax
0x18003b8d9  jns     short loc_18003B932
0x18003b8db  mov     edx, eax; int
0x18003b8dd  lea     rcx, qword_18006A9C0; this
0x18003b8e4  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b8e9  lea     rcx, WPP_GLOBAL_Control
0x18003b8f0  mov     r10, cs:WPP_GLOBAL_Control
0x18003b8f7  cmp     r10, rcx
0x18003b8fa  jz      loc_18003BCFF
0x18003b900  test    byte ptr [r10+1Ch], 1
0x18003b905  jz      loc_18003BCFF
0x18003b90b  cmp     byte ptr [r10+19h], 2
0x18003b910  jb      loc_18003BCFF
0x18003b916  lea     edx, [r13+29h]
0x18003b91a  mov     r9d, ebx
0x18003b91d  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003b924  mov     rcx, [r10+10h]
0x18003b928  call    WPP_SF_D
0x18003b92d  jmp     loc_18003BCFF
0x18003b932  mov     rcx, [rbp+57h+var_C8]
0x18003b936  mov     rax, [rcx]
0x18003b939  mov     dword ptr [rsp+110h+var_F0], 0
0x18003b941  lea     r9, [rbp+57h+var_78]
0x18003b945  xor     r8d, r8d
0x18003b948  lea     rdx, aGroup_0; "Group"
0x18003b94f  mov     rax, [rax+28h]
0x18003b953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b958  mov     ebx, eax
0x18003b95a  test    eax, eax
0x18003b95c  jns     short loc_18003B9A3
0x18003b95e  mov     edx, eax; int
0x18003b960  lea     rcx, qword_18006A9C0; this
0x18003b967  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b96c  lea     rcx, WPP_GLOBAL_Control
0x18003b973  mov     r10, cs:WPP_GLOBAL_Control
0x18003b97a  cmp     r10, rcx
0x18003b97d  jz      loc_18003BCFF
0x18003b983  test    byte ptr [r10+1Ch], 1
0x18003b988  jz      loc_18003BCFF
0x18003b98e  cmp     byte ptr [r10+19h], 2
0x18003b993  jb      loc_18003BCFF
0x18003b999  mov     edx, 37h ; '7'
0x18003b99e  jmp     loc_18003B91A
0x18003b9a3  mov     [rbp+57h+var_B8], 0
0x18003b9ab  mov     rcx, rdi; this
0x18003b9ae  call    ?GetOwner@CNtSecurityDescriptor@@QEAAPEAVCNtSid@@XZ; CNtSecurityDescriptor::GetOwner(void)
0x18003b9b3  mov     [rbp+57h+var_B0], rax
0x18003b9b7  lea     r9, [rbp+57h+var_B8]; struct IWbemClassObject **
0x18003b9bb  mov     r8, rax; struct CNtSid *
0x18003b9be  mov     rdx, r14; struct IWbemContext *
0x18003b9c1  mov     rcx, rsi; struct IWbemServices *
0x18003b9c4  call    ?BuildTrusteeObject@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAVCNtSid@@PEAPEAUIWbemClassObject@@@Z; BuildTrusteeObject(IWbemServices *,IWbemContext *,CNtSid *,IWbemClassObject * *)
0x18003b9c9  mov     ebx, eax
0x18003b9cb  test    eax, eax
0x18003b9cd  jns     short loc_18003BA27
0x18003b9cf  mov     edx, eax; int
0x18003b9d1  lea     rcx, qword_18006A9C0; this
0x18003b9d8  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b9dd  lea     rcx, WPP_GLOBAL_Control
0x18003b9e4  mov     r10, cs:WPP_GLOBAL_Control
0x18003b9eb  cmp     r10, rcx
0x18003b9ee  jz      loc_18003BCEB
0x18003b9f4  test    byte ptr [r10+1Ch], 1
0x18003b9f9  jz      loc_18003BCEB
0x18003b9ff  cmp     byte ptr [r10+19h], 2
0x18003ba04  jb      loc_18003BCEB
0x18003ba0a  mov     edx, 38h ; '8'
0x18003ba0f  mov     r9d, ebx
0x18003ba12  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003ba19  mov     rcx, [r10+10h]
0x18003ba1d  call    WPP_SF_D
0x18003ba22  jmp     loc_18003BCEB
0x18003ba27  lea     rcx, [rbp+57h+var_58]; pvarg
0x18003ba2b  call    cs:__imp_VariantInit
0x18003ba31  nop
0x18003ba32  mov     word ptr [rbp+57h+var_58], r13w
0x18003ba37  mov     rcx, [rbp+57h+var_B8]
0x18003ba3b  mov     rax, [rcx]
0x18003ba3e  lea     r8, [rbp+57h+var_58+8]
0x18003ba42  lea     rdx, IID_IUnknown
0x18003ba49  mov     rax, [rax]
0x18003ba4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba51  mov     ebx, eax
0x18003ba53  test    eax, eax
0x18003ba55  jns     short loc_18003BAAF
0x18003ba57  mov     edx, eax; int
0x18003ba59  lea     rcx, qword_18006A9C0; this
0x18003ba60  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ba65  lea     rcx, WPP_GLOBAL_Control
0x18003ba6c  mov     r10, cs:WPP_GLOBAL_Control
0x18003ba73  cmp     r10, rcx
0x18003ba76  jz      loc_18003BCE1
0x18003ba7c  test    byte ptr [r10+1Ch], 1
0x18003ba81  jz      loc_18003BCE1
0x18003ba87  cmp     byte ptr [r10+19h], 2
0x18003ba8c  jb      loc_18003BCE1
0x18003ba92  mov     edx, 39h ; '9'
0x18003ba97  mov     r9d, ebx
0x18003ba9a  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003baa1  mov     rcx, [r10+10h]
0x18003baa5  call    WPP_SF_D
0x18003baaa  jmp     loc_18003BCE1
0x18003baaf  mov     rcx, [rbp+57h+var_C8]
0x18003bab3  mov     rax, [rcx]
0x18003bab6  mov     dword ptr [rsp+110h+var_F0], 0
0x18003babe  lea     r9, [rbp+57h+var_58]
  ... truncated ...
```
