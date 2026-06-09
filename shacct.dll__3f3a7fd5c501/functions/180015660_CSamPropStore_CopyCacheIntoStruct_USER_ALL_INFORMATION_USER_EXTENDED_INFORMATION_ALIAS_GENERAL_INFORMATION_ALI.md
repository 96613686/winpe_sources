# CSamPropStore::_CopyCacheIntoStruct(_USER_ALL_INFORMATION *,_USER_EXTENDED_INFORMATION *,_ALIAS_GENERAL_INFORMATION *,_ALIAS_EXTENDED_INFORMATION *,ulong *)

- ea: `0x180015660`
- end: `0x180015d2a`
- name: `?_CopyCacheIntoStruct@CSamPropStore@@AEAAJPEAU_USER_ALL_INFORMATION@@PEAU_USER_EXTENDED_INFORMATION@@PEAU_ALIAS_GENERAL_INFORMATION@@PEAU_ALIAS_EXTENDED_INFORMATION@@PEAK@Z`
- size: `1738`
- prototype: `__int64 __usercall@<rax>(struct IPropertyStore *this@<rcx>, struct _USER_ALL_INFORMATION *@<rdx>, struct _USER_EXTENDED_INFORMATION *@<r8>, struct _ALIAS_GENERAL_INFORMATION *@<r9>, struct _ALIAS_EXTENDED_INFORMATION *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014d90`

## callees

- `0x180003e20`
- `0x180006f80`
- `0x18000b89c`
- `0x18000c240`
- `0x18000ec7c`
- `0x180015660`
- `0x1800161e8`
- `0x18001645c`
- `0x18001675c`
- `0x180016cdd`
- `0x180016ce9`
- `0x180017010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180015a14`
- `ntdll!RtlInitUnicodeString` at `0x180015a14`
- `PROPSYS!PropVariantCompareEx` at `0x180015859`
- `PROPSYS!PropVariantCompareEx` at `0x180015859`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800158db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800158db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001586c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015929`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001586c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015929`

## pseudocode

```c
__int64 __fastcall CSamPropStore::_CopyCacheIntoStruct(
        struct IPropertyStore *this,
        struct _USER_ALL_INFORMATION *a2,
        struct _USER_EXTENDED_INFORMATION *a3,
        struct _ALIAS_GENERAL_INFORMATION *a4,
        struct _ALIAS_EXTENDED_INFORMATION *a5,
        unsigned int *a6)
{
  unsigned int *v6; // rdi
  unsigned int v7; // r14d
  struct IPropertyStore *v8; // r12
  struct _USER_EXTENDED_INFORMATION *v9; // r15
  int SamPropKey; // ebx
  unsigned int v12; // esi
  struct IPropertyStoreVtbl *lpVtbl; // rcx
  unsigned int v14; // eax
  struct IPropertyStoreVtbl *v15; // rcx
  DWORD pid; // edi
  struct IPropertyStoreVtbl *v17; // rcx
  struct _PROPMAP *v18; // r14
  __int64 v19; // rax
  DWORD v20; // edi
  SIZE_T v21; // rcx
  void *v22; // rdi
  size_t v23; // r14
  UCHAR *v24; // rax
  __int64 v25; // r8
  unsigned int v26; // r15d
  unsigned __int64 v27; // r14
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  unsigned __int16 *v31; // rdi
  unsigned int v32; // ebx
  const unsigned __int16 *v33; // r8
  int v34; // eax
  int v35; // eax
  CSamPropStore *v36; // rcx
  unsigned int v38; // [rsp+40h] [rbp-89h]
  unsigned int v39; // [rsp+44h] [rbp-85h] BYREF
  PROPVARIANT propvar2[2]; // [rsp+48h] [rbp-81h] BYREF
  void *Src; // [rsp+58h] [rbp-71h]
  struct _PROPMAP *v42; // [rsp+60h] [rbp-69h] BYREF
  PCWSTR SourceString; // [rsp+68h] [rbp-61h] BYREF
  struct IPropertyStore *v44; // [rsp+70h] [rbp-59h]
  struct _USER_EXTENDED_INFORMATION *v45; // [rsp+78h] [rbp-51h]
  struct _ALIAS_EXTENDED_INFORMATION *v46; // [rsp+80h] [rbp-49h]
  CSamPropStore *v47; // [rsp+88h] [rbp-41h]
  unsigned int *v48; // [rsp+90h] [rbp-39h]
  struct tagPROPVARIANT propvar1; // [rsp+98h] [rbp-31h] BYREF
  struct _tagpropertykey Buf1; // [rsp+B0h] [rbp-19h] BYREF

  v6 = a6;
  v7 = 0;
  v44 = this;
  v8 = this;
  v46 = a5;
  v9 = a3;
  v47 = a4;
  v45 = a3;
  v48 = a6;
  v42 = 0;
  v39 = 0;
  if ( !a2 && !a3 && !a4 && !a5 )
    return (unsigned int)-2147467261;
  *a6 = 0;
  v12 = 0;
  lpVtbl = this[12].lpVtbl;
  SamPropKey = 0;
  if ( !lpVtbl )
    goto LABEL_99;
  SamPropKey = (*((__int64 (__fastcall **)(struct IPropertyStoreVtbl *, unsigned int *))lpVtbl->QueryInterface + 3))(
                 lpVtbl,
                 &v39);
  if ( SamPropKey >= 0 )
  {
    v14 = v39;
    if ( !v39 )
      goto LABEL_99;
    while ( 1 )
    {
      v38 = v7;
      if ( v7 >= v14 )
      {
        if ( SamPropKey < 0 )
          return (unsigned int)SamPropKey;
        v6 = v48;
LABEL_99:
        *v6 = v12;
        return (unsigned int)SamPropKey;
      }
      v15 = v8[12].lpVtbl;
      memset(&Buf1, 0, sizeof(Buf1));
      SamPropKey = (*((__int64 (__fastcall **)(struct IPropertyStoreVtbl *, _QWORD, struct _tagpropertykey *))v15->QueryInterface
                    + 4))(
                     v15,
                     v7,
                     &Buf1);
      if ( SamPropKey >= 0 )
      {
        pid = Buf1.pid;
        if ( (Buf1.pid != 4 || memcmp_0(&Buf1, &PKEY_SAM_DateChanged, 0x10u))
          && (pid != 3 || memcmp_0(&Buf1, &PKEY_SAM_Version, 0x10u)) )
        {
          SamPropKey = CSamPropStore::_FindSamPropKey((CSamPropStore *)v8, &Buf1, &v42);
          if ( !SamPropKey )
            break;
        }
      }
LABEL_37:
      v14 = v39;
      ++v7;
    }
    v17 = v8[12].lpVtbl;
    Src = 0;
    *(_OWORD *)propvar2 = 0;
    SamPropKey = (*((__int64 (__fastcall **)(struct IPropertyStoreVtbl *, struct _tagpropertykey *, PROPVARIANT *))v17->QueryInterface
                  + 5))(
                   v17,
                   &Buf1,
                   propvar2);
    if ( SamPropKey >= 0 && LOWORD(propvar2[0]) )
    {
      v18 = v42;
      if ( Buf1.pid != *((_DWORD *)v42 + 4) )
        goto LABEL_35;
      v19 = *(_QWORD *)&Buf1.fmtid.Data1 - *(_QWORD *)v42;
      if ( *(_QWORD *)&Buf1.fmtid.Data1 == *(_QWORD *)v42 )
        v19 = *(_QWORD *)Buf1.fmtid.Data4 - *((_QWORD *)v42 + 1);
      if ( v19 )
        goto LABEL_35;
      memset(&propvar1, 0, sizeof(propvar1));
      SamPropKey = CSamPropStore::_GetValue(v8, &Buf1, &propvar1, 0);
      if ( SamPropKey >= 0 )
      {
        SamPropKey = PropVariantCompareEx((const PROPVARIANT *const)&propvar1, propvar2, PVCU_DEFAULT, 0) == 0;
        PropVariantClear((PROPVARIANT *)&propvar1);
      }
      if ( SamPropKey )
        goto LABEL_35;
      if ( *((_DWORD *)v18 + 6) == -1 )
      {
        v20 = Buf1.pid;
        if ( Buf1.pid == 20 && !memcmp_0(&Buf1, &PKEY_SAM_LogonHours, 0x10u) )
        {
          v21 = LODWORD(propvar2[1]);
          SamPropKey = 0;
          if ( LODWORD(propvar2[1]) && (v22 = Src) != 0 )
          {
            v23 = LODWORD(propvar2[1]);
            a2->LogonHours.UnitsPerWeek = 8 * LOWORD(propvar2[1]);
            v24 = (UCHAR *)CoTaskMemAlloc(v21);
            a2->LogonHours.LogonHours = v24;
            if ( v24 )
              memcpy_0(v24, v22, v23);
            else
              SamPropKey = -2147024882;
          }
          else
          {
            a2->LogonHours.UnitsPerWeek = 0;
            a2->LogonHours.LogonHours = 0;
          }
          a2->WhichFields |= 0x2000u;
          v12 |= 2u;
        }
        else if ( v20 == 15 && !memcmp_0(&Buf1, &PKEY_SAM_Workstations, 0x10u) )
        {
          v26 = (unsigned int)propvar2[1];
          if ( LODWORD(propvar2[1]) )
          {
            v27 = 0;
            LODWORD(v28) = 0;
            do
            {
              v29 = *((_QWORD *)Src + (unsigned int)v28);
              if ( v29 )
              {
                v30 = -1;
                do
                  ++v30;
                while ( *(_WORD *)(v29 + 2 * v30) );
                v27 += v30 + 1;
              }
              v28 = (unsigned int)(v28 + 1);
            }
            while ( (unsigned int)v28 < LODWORD(propvar2[1]) );
            v8 = v44;
            SourceString = 0;
            if ( (int)_AllocArray<unsigned short,CTCoAllocPolicy>(v28, 1, v27, &SourceString) >= 0 )
            {
              v31 = (unsigned __int16 *)SourceString;
              v32 = 0;
              do
              {
                v33 = (const unsigned __int16 *)*((_QWORD *)Src + v32);
                if ( v33 )
                {
                  StringCchCatW(v31, v27, v33);
                  StringCchCatW(v31, v27, L",");
                }
                ++v32;
              }
              while ( v32 < v26 );
              RtlInitUnicodeString(&a2->WorkStations, v31);
            }
            a2->WhichFields |= 0x400u;
            v12 |= 2u;
          }
          v9 = v45;
          SamPropKey = 0;
        }
        else if ( v20 == 36 && !memcmp_0(&Buf1, &PKEY_SAM_InteractiveLogin, 0x10u)
               || v20 == 37 && !memcmp_0(&Buf1, &PKEY_SAM_NetworkLogin, 0x10u)
               || v20 == 38 && !memcmp_0(&Buf1, &PKEY_SAM_BatchLogin, 0x10u)
               || v20 == 39 && !memcmp_0(&Buf1, &PKEY_SAM_ServiceLogin, 0x10u)
               || v20 == 40 && !memcmp_0(&Buf1, &PKEY_SAM_RemoteInteractiveLogin, 0x10u)
               || v20 == 41 && !memcmp_0(&Buf1, &PKEY_SAM_DenyInteractiveLogin, 0x10u)
               || v20 == 42 && !memcmp_0(&Buf1, &PKEY_SAM_DenyNetworkLogin, 0x10u)
               || v20 == 43 && !memcmp_0(&Buf1, &PKEY_SAM_DenyBatchLogin, 0x10u)
               || v20 == 44 && !memcmp_0(&Buf1, &PKEY_SAM_DenyServiceLogin, 0x10u)
               || v20 == 45 && !memcmp_0(&Buf1, &PKEY_SAM_DenyRemoteInteractiveLogin, 0x10u) )
        {
          SamPropKey = CSamPropStore::_PopulateAccountRights((CSamPropStore *)v8);
          if ( SamPropKey >= 0 )
          {
            v34 = *((_DWORD *)v18 + 7);
            if ( LOWORD(propvar2[1]) == 0xFFFF )
              LODWORD(v8[8].lpVtbl) |= v34;
            else
              LODWORD(v8[8].lpVtbl) &= ~v34;
            v12 |= 1u;
          }
        }
        goto LABEL_35;
      }
      if ( Buf1.pid == 17 && !memcmp_0(&Buf1, &PKEY_SAM_Password, 0x10u) && (a2->WhichFields & 0x20000000) != 0 )
        goto LABEL_35;
      if ( HIDWORD(v8[10].lpVtbl) == 1 )
      {
        v35 = *((_DWORD *)v18 + 7);
        if ( *((_DWORD *)v18 + 8) )
        {
          v12 |= 4u;
          v36 = v9;
          *(_DWORD *)v9 |= v35;
        }
        else
        {
          v12 |= 2u;
          v36 = (CSamPropStore *)a2;
          a2->WhichFields |= v35;
        }
      }
      else if ( *((_DWORD *)v18 + 8) )
      {
        v36 = v46;
        v12 |= 0x10u;
      }
      else
      {
        v36 = v47;
        v12 |= 8u;
      }
      SamPropKey = CSamPropStore::_CopyPropertyValueIntoStruct(
                     v36,
                     propvar2,
                     (FILETIME *)((char *)v36 + *((unsigned int *)v18 + 6)));
      if ( SamPropKey < 0 || Buf1.pid != 17 )
      {
LABEL_35:
        v7 = v38;
        goto LABEL_36;
      }
      v7 = v38;
      if ( !memcmp_0(&Buf1, &PKEY_SAM_Password, 0x10u) )
        a2->NtPasswordPresent = 1;
    }
LABEL_36:
    PropVariantClear(propvar2);
    if ( SamPropKey < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF__guid_dddD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          v25,
          &Buf1,
          Buf1.pid,
          HIDWORD(v8[10].lpVtbl),
          v8[10].lpVtbl,
          SamPropKey);
      return (unsigned int)SamPropKey;
    }
    goto LABEL_37;
  }
  return (unsigned int)SamPropKey;
}

```

## disassembly

```asm
0x180015660  push    rbp
0x180015662  push    rbx
0x180015663  push    rsi
0x180015664  push    rdi
0x180015665  push    r12
0x180015667  push    r13
0x180015669  push    r14
0x18001566b  push    r15
0x18001566d  lea     rbp, [rsp-0Fh]
0x180015672  sub     rsp, 0D8h
0x180015679  mov     rax, cs:__security_cookie
0x180015680  xor     rax, rsp
0x180015683  mov     [rbp+47h+var_48], rax
0x180015687  mov     rdi, [rbp+47h+arg_28]
0x18001568b  xor     r14d, r14d
0x18001568e  mov     [rbp+47h+var_A0], rcx
0x180015692  mov     r12, rcx
0x180015695  mov     rcx, [rbp+47h+arg_20]
0x180015699  mov     rax, r9
0x18001569c  mov     [rbp+47h+var_90], rcx
0x1800156a0  mov     r15, r8
0x1800156a3  mov     [rbp+47h+var_88], rax
0x1800156a7  mov     r13, rdx
0x1800156aa  mov     [rbp+47h+var_98], r8
0x1800156ae  mov     [rbp+47h+var_80], rdi
0x1800156b2  mov     [rbp+47h+var_B0], r14
0x1800156b6  mov     [rsp+110h+var_CC], r14d
0x1800156bb  test    rdx, rdx
0x1800156be  jnz     short loc_1800156D9
0x1800156c0  test    r8, r8
0x1800156c3  jnz     short loc_1800156D9
0x1800156c5  test    rax, rax
0x1800156c8  jnz     short loc_1800156D9
0x1800156ca  test    rcx, rcx
0x1800156cd  jnz     short loc_1800156D9
0x1800156cf  mov     ebx, 80004003h
0x1800156d4  jmp     loc_180015D08
0x1800156d9  mov     [rdi], r14d
0x1800156dc  mov     esi, r14d
0x1800156df  mov     rcx, [r12+60h]
0x1800156e4  mov     ebx, r14d
0x1800156e7  test    rcx, rcx
0x1800156ea  jz      loc_180015D06
0x1800156f0  mov     rax, [rcx]
0x1800156f3  lea     rdx, [rsp+110h+var_CC]
0x1800156f8  mov     rax, [rax+18h]
0x1800156fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015701  mov     ebx, eax
0x180015703  test    eax, eax
0x180015705  js      loc_180015D08
0x18001570b  mov     eax, [rsp+110h+var_CC]
0x18001570f  test    eax, eax
0x180015711  jz      loc_180015D06
0x180015717  mov     [rsp+110h+var_D0], r14d
0x18001571c  cmp     r14d, eax
0x18001571f  jnb     loc_180015CFE
0x180015725  mov     rcx, [r12+60h]
0x18001572a  lea     r8, [rbp+47h+Buf1]
0x18001572e  xor     eax, eax
0x180015730  xorps   xmm0, xmm0
0x180015733  mov     [rbp+47h+var_50], eax
0x180015736  mov     edx, r14d
0x180015739  movups  [rbp+47h+Buf1], xmm0
0x18001573d  mov     rax, [rcx]
0x180015740  mov     rax, [rax+20h]
0x180015744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015749  mov     ebx, eax
0x18001574b  test    eax, eax
0x18001574d  js      loc_180015937
0x180015753  mov     edi, [rbp+47h+var_50]
0x180015756  cmp     edi, cs:dword_18001A9A8
0x18001575c  jnz     short loc_18001577C
0x18001575e  mov     r8d, 10h; Size
0x180015764  lea     rdx, PKEY_SAM_DateChanged; Buf2
0x18001576b  lea     rcx, [rbp+47h+Buf1]; Buf1
0x18001576f  call    memcmp_0
0x180015774  test    eax, eax
0x180015776  jz      loc_180015937
0x18001577c  cmp     edi, cs:dword_18001AD08
0x180015782  jnz     short loc_1800157A2
0x180015784  mov     r8d, 10h; Size
0x18001578a  lea     rdx, PKEY_SAM_Version; Buf2
0x180015791  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180015795  call    memcmp_0
0x18001579a  test    eax, eax
0x18001579c  jz      loc_180015937
0x1800157a2  lea     r8, [rbp+47h+var_B0]; struct _PROPMAP **
0x1800157a6  mov     rcx, r12; this
0x1800157a9  lea     rdx, [rbp+47h+Buf1]; struct _tagpropertykey *
0x1800157ad  call    ?_FindSamPropKey@CSamPropStore@@AEAAJAEBU_tagpropertykey@@PEAPEAU_PROPMAP@@@Z; CSamPropStore::_FindSamPropKey(_tagpropertykey const &,_PROPMAP * *)
0x1800157b2  mov     ebx, eax
0x1800157b4  test    eax, eax
0x1800157b6  jnz     loc_180015937
0x1800157bc  mov     rcx, [r12+60h]
0x1800157c1  lea     r8, [rsp+110h+propvar2]
0x1800157c6  xor     eax, eax
0x1800157c8  lea     rdx, [rbp+47h+Buf1]
0x1800157cc  mov     [rbp+47h+Src], rax
0x1800157d0  xorps   xmm0, xmm0
0x1800157d3  movups  xmmword ptr [rsp+110h+propvar2], xmm0
0x1800157d8  mov     rax, [rcx]
0x1800157db  mov     rax, [rax+28h]
0x1800157df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157e4  xor     ecx, ecx
0x1800157e6  mov     ebx, eax
0x1800157e8  test    eax, eax
0x1800157ea  js      loc_180015924
0x1800157f0  cmp     word ptr [rsp+110h+propvar2], cx
0x1800157f5  jz      loc_180015924
0x1800157fb  mov     r14, [rbp+47h+var_B0]
0x1800157ff  mov     eax, [r14+10h]
0x180015803  cmp     [rbp+47h+var_50], eax
0x180015806  jnz     loc_18001591F
0x18001580c  mov     rax, qword ptr [rbp+47h+Buf1]
0x180015810  sub     rax, [r14]
0x180015813  jnz     short loc_18001581D
0x180015815  mov     rax, qword ptr [rbp+47h+Buf1+8]
0x180015819  sub     rax, [r14+8]
0x18001581d  test    rax, rax
0x180015820  jnz     loc_18001591F
0x180015826  xorps   xmm0, xmm0
0x180015829  mov     [rbp+47h+var_68], rax
0x18001582d  xor     r9d, r9d; int
0x180015830  lea     r8, [rbp+47h+propvar1]; struct tagPROPVARIANT *
0x180015834  lea     rdx, [rbp+47h+Buf1]; struct _tagpropertykey *
0x180015838  mov     rcx, r12; this
0x18001583b  movups  xmmword ptr [rbp+47h+propvar1], xmm0
0x18001583f  call    ?_GetValue@CSamPropStore@@AEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@H@Z; CSamPropStore::_GetValue(_tagpropertykey const &,tagPROPVARIANT *,int)
0x180015844  xor     r9d, r9d; flags
0x180015847  mov     ebx, eax
0x180015849  test    eax, eax
0x18001584b  js      short loc_180015875
0x18001584d  xor     r8d, r8d; unit
0x180015850  lea     rdx, [rsp+110h+propvar2]; propvar2
0x180015855  lea     rcx, [rbp+47h+propvar1]; propvar1
0x180015859  call    cs:__imp_PropVariantCompareEx
0x18001585f  xor     ecx, ecx
0x180015861  mov     ebx, ecx
0x180015863  test    eax, eax
0x180015865  lea     rcx, [rbp+47h+propvar1]; pvar
0x180015869  setz    bl
0x18001586c  call    cs:__imp_PropVariantClear
0x180015872  xor     r9d, r9d
0x180015875  test    ebx, ebx
0x180015877  jnz     loc_18001591F
0x18001587d  cmp     dword ptr [r14+18h], 0FFFFFFFFh
0x180015882  jnz     loc_180015BDF
0x180015888  mov     edi, [rbp+47h+var_50]
0x18001588b  cmp     edi, cs:dword_18001AB10
0x180015891  jnz     loc_180015943
0x180015897  lea     r8d, [rbx+10h]; Size
0x18001589b  lea     rdx, PKEY_SAM_LogonHours; Buf2
0x1800158a2  lea     rcx, [rbp+47h+Buf1]; Buf1
0x1800158a6  call    memcmp_0
0x1800158ab  xor     r9d, r9d
0x1800158ae  test    eax, eax
0x1800158b0  jnz     loc_180015943
0x1800158b6  mov     ecx, dword ptr [rbp+47h+propvar2+8]; cb
0x1800158b9  mov     ebx, r9d
0x1800158bc  test    ecx, ecx
0x1800158be  jz      short loc_180015904
0x1800158c0  mov     rdi, [rbp+47h+Src]
0x1800158c4  test    rdi, rdi
0x1800158c7  jz      short loc_180015904
0x1800158c9  movzx   eax, cx
0x1800158cc  mov     r14d, ecx
0x1800158cf  shl     ax, 3
0x1800158d3  mov     [r13+120h], ax
0x1800158db  call    cs:__imp_CoTaskMemAlloc
0x1800158e1  mov     [r13+128h], rax
0x1800158e8  test    rax, rax
0x1800158eb  jnz     short loc_1800158F4
0x1800158ed  mov     ebx, 8007000Eh
0x1800158f2  jmp     short loc_180015913
0x1800158f4  mov     r8, r14; Size
0x1800158f7  mov     rdx, rdi; Src
0x1800158fa  mov     rcx, rax; void *
0x1800158fd  call    memcpy_0
0x180015902  jmp     short loc_180015913
0x180015904  mov     [r13+120h], r9w
0x18001590c  mov     [r13+128h], r9
0x180015913  bts     dword ptr [r13+11Ch], 0Dh
0x18001591c  or      esi, 2
0x18001591f  mov     r14d, [rsp+110h+var_D0]
0x180015924  lea     rcx, [rsp+110h+propvar2]; pvar
0x180015929  call    cs:__imp_PropVariantClear
0x18001592f  test    ebx, ebx
0x180015931  js      loc_180015CB4
0x180015937  mov     eax, [rsp+110h+var_CC]
0x18001593b  inc     r14d
0x18001593e  jmp     loc_180015717
0x180015943  cmp     edi, cs:dword_18001AD20
0x180015949  jnz     loc_180015A35
0x18001594f  mov     r8d, 10h; Size
0x180015955  lea     rdx, PKEY_SAM_Workstations; Buf2
0x18001595c  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180015960  call    memcmp_0
0x180015965  xor     r9d, r9d
0x180015968  test    eax, eax
0x18001596a  jnz     loc_180015A35
0x180015970  mov     r15d, dword ptr [rbp+47h+propvar2+8]
0x180015974  test    r15d, r15d
0x180015977  jz      loc_180015A29
0x18001597d  mov     r8, [rbp+47h+Src]
0x180015981  mov     r14d, r9d
0x180015984  mov     ecx, r9d
0x180015987  mov     eax, ecx
0x180015989  mov     rdx, [r8+rax*8]
0x18001598d  test    rdx, rdx
0x180015990  jz      short loc_1800159A6
0x180015992  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015996  inc     rax
0x180015999  cmp     [rdx+rax*2], r9w
0x18001599e  jnz     short loc_180015996
0x1800159a0  inc     r14
0x1800159a3  add     r14, rax
0x1800159a6  inc     ecx
0x1800159a8  cmp     ecx, r15d
0x1800159ab  jb      short loc_180015987
0x1800159ad  mov     r12, [rbp+47h+var_A0]
0x1800159b1  mov     r8, r14
0x1800159b4  mov     [rbp+47h+SourceString], r9
0x1800159b8  mov     edx, 1
0x1800159bd  lea     r9, [rbp+47h+SourceString]
0x1800159c1  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1800159c6  xor     r9d, r9d
0x1800159c9  test    eax, eax
0x1800159cb  js      short loc_180015A1D
0x1800159cd  mov     rdi, [rbp+47h+SourceString]
0x1800159d1  mov     ebx, r9d
0x1800159d4  mov     rax, [rbp+47h+Src]
0x1800159d8  mov     ecx, ebx
0x1800159da  mov     r8, [rax+rcx*8]; unsigned __int16 *
0x1800159de  test    r8, r8
0x1800159e1  jz      short loc_180015A03
0x1800159e3  mov     rdx, r14; unsigned __int64
0x1800159e6  mov     rcx, rdi; unsigned __int16 *
0x1800159e9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800159ee  lea     r8, asc_18001B258; ","
0x1800159f5  mov     rdx, r14; unsigned __int64
0x1800159f8  mov     rcx, rdi; unsigned __int16 *
0x1800159fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015a00  xor     r9d, r9d
0x180015a03  inc     ebx
0x180015a05  cmp     ebx, r15d
0x180015a08  jb      short loc_1800159D4
0x180015a0a  lea     rcx, [r13+0A0h]; DestinationString
0x180015a11  mov     rdx, rdi; SourceString
0x180015a14  call    cs:__imp_RtlInitUnicodeString
0x180015a1a  xor     r9d, r9d
0x180015a1d  bts     dword ptr [r13+11Ch], 0Ah
0x180015a26  or      esi, 2
0x180015a29  mov     r15, [rbp+47h+var_98]
0x180015a2d  mov     ebx, r9d
0x180015a30  jmp     loc_18001591F
0x180015a35  cmp     edi, cs:dword_18001AAF8
0x180015a3b  jnz     short loc_180015A5B
0x180015a3d  mov     r8d, 10h; Size
0x180015a43  lea     rdx, PKEY_SAM_InteractiveLogin; Buf2
0x180015a4a  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180015a4e  call    memcmp_0
0x180015a53  test    eax, eax
0x180015a55  jz      loc_180015BA9
0x180015a5b  cmp     edi, cs:dword_18001AB40
0x180015a61  jnz     short loc_180015A81
0x180015a63  mov     r8d, 10h; Size
0x180015a69  lea     rdx, PKEY_SAM_NetworkLogin; Buf2
0x180015a70  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180015a74  call    memcmp_0
0x180015a79  test    eax, eax
0x180015a7b  jz      loc_180015BA9
0x180015a81  cmp     edi, cs:dword_18001A948
0x180015a87  jnz     short loc_180015AA7
0x180015a89  mov     r8d, 10h; Size
0x180015a8f  lea     rdx, PKEY_SAM_BatchLogin; Buf2
0x180015a96  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180015a9a  call    memcmp_0
0x180015a9f  test    eax, eax
0x180015aa1  jz      loc_180015BA9
0x180015aa7  cmp     edi, cs:dword_18001AC78
0x180015aad  jnz     short loc_180015ACD
0x180015aaf  mov     r8d, 10h; Size
0x180015ab5  lea     rdx, PKEY_SAM_ServiceLogin; Buf2
0x180015abc  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180015ac0  call    memcmp_0
0x180015ac5  test    eax, eax
0x180015ac7  jz      loc_180015BA9
0x180015acd  cmp     edi, cs:dword_18001AC18
0x180015ad3  jnz     short loc_180015AF3
0x180015ad5  mov     r8d, 10h; Size
0x180015adb  lea     rdx, PKEY_SAM_RemoteInteractiveLogin; Buf2
0x180015ae2  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180015ae6  call    memcmp_0
0x180015aeb  test    eax, eax
0x180015aed  jz      loc_180015BA9
0x180015af3  cmp     edi, cs:dword_18001A9D8
0x180015af9  jnz     short loc_180015B19
0x180015afb  mov     r8d, 10h; Size
0x180015b01  lea     rdx, PKEY_SAM_DenyInteractiveLogin; Buf2
0x180015b08  lea     rcx, [rbp+47h+Buf1]; Buf1
  ... truncated ...
```
