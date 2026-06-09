# UnistoreUpgrade::UpgradeAppointmentRecurringData(IUSStoreManager *,IDBVolume *)

- ea: `0x180098260`
- end: `0x18009861d`
- name: `?UpgradeAppointmentRecurringData@UnistoreUpgrade@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@@Z`
- size: `957`
- prototype: `__int64 __fastcall(UnistoreUpgrade *__hidden this, struct IUSStoreManager *, struct IDBVolume *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18001e2f4`
- `0x180034664`
- `0x180035d40`
- `0x1800368d8`
- `0x1800576c0`
- `0x180072e68`
- `0x1800747a4`
- `0x180098260`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098502`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098549`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098502`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098549`

## string_xrefs

- `0x180098521`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098578`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098590`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x1800985a8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x1800985e3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreUpgrade::UpgradeAppointmentRecurringData(
        UnistoreUpgrade *this,
        struct IUSStoreManager *a2,
        struct IDBVolume *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v5)(UnistoreUpgrade *, __int64, _QWORD); // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  struct IUSObject *v12; // rdi
  __int64 (__fastcall *v13)(struct IUSObject *, __int64, _DWORD *); // rbx
  int v14; // eax
  int started; // eax
  const struct _USBLOB *v16; // rbx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rcx
  struct IUSObject *v22; // [rsp+40h] [rbp-89h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-81h] BYREF
  __int64 v24; // [rsp+50h] [rbp-79h] BYREF
  int v25; // [rsp+58h] [rbp-71h] BYREF
  __int128 v26; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v27[8]; // [rsp+70h] [rbp-59h] BYREF
  int v28; // [rsp+78h] [rbp-51h]
  _DWORD v29[8]; // [rsp+80h] [rbp-49h] BYREF
  int v30; // [rsp+A0h] [rbp-29h] BYREF
  _BYTE v31[4]; // [rsp+A4h] [rbp-25h] BYREF
  __int128 v32; // [rsp+A8h] [rbp-21h]
  int v33; // [rsp+B8h] [rbp-11h]
  __int16 v34; // [rsp+BEh] [rbp-Bh]
  int v35; // [rsp+D0h] [rbp+7h]
  __int16 v36; // [rsp+D6h] [rbp+Dh]

  v3 = *(_QWORD *)this;
  v29[0] = 131075;
  v5 = *(__int64 (__fastcall **)(UnistoreUpgrade *, __int64, _QWORD))(v3 + 136);
  v29[1] = 2228235;
  v29[2] = 3670081;
  v29[3] = 4128868;
  v29[4] = 4194404;
  v24 = 0;
  v6 = v5(this, 3, 0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 120LL))(v24);
    while ( !v7 )
    {
      v22 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, struct IUSObject **))(*(_QWORD *)v24 + 40LL))(v24, &v22);
      v7 = v11;
      if ( v11 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v11,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          181);
        goto LABEL_38;
      }
      v12 = v22;
      hMem = 0;
      v13 = *(__int64 (__fastcall **)(struct IUSObject *, __int64, _DWORD *))(*(_QWORD *)v22 + 48LL);
      tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>((__int64)&hMem);
      v14 = v13(v12, 5, v29);
      v7 = v14;
      if ( v14 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v14,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          184);
        goto LABEL_30;
      }
      if ( (*((_WORD *)hMem + 15) & 0x300) == 0 && (*((_WORD *)hMem + 27) & 0x300) != 0 )
      {
        ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v27, a2);
        v28 = 0;
        started = DBAutoTopLevelTransact::StartTransaction(
                    (DBAutoTopLevelTransact *)v27,
                    3u,
                    1u,
                    (const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *)((char *)hMem + 8));
        v7 = started;
        if ( started < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)started,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
            192);
          goto LABEL_29;
        }
        if ( (*((_WORD *)hMem + 39) & 0x300) != 0 )
        {
          v16 = 0;
          if ( (*((_WORD *)hMem + 51) & 0x300) == 0 )
            v16 = (const struct _USBLOB *)((char *)hMem + 104);
        }
        else
        {
          v16 = (const struct _USBLOB *)((char *)hMem + 80);
        }
        v30 = 0;
        v26 = 0;
        memset_0(v31, 0, 0x44u);
        if ( v16 )
        {
          v17 = UpgradeRecurrenceData(v16, v22, (struct _USBLOB *)&v26);
          v7 = v17;
          if ( v17 < 0 )
          {
            v19 = 212;
            goto LABEL_26;
          }
          v32 = v26;
          v30 = 3670081;
        }
        else
        {
          v30 = 2228235;
          LODWORD(v32) = 0;
        }
        v33 = 4128868;
        v34 = 512;
        v35 = 4194404;
        v36 = 512;
        v17 = (*(__int64 (__fastcall **)(struct IUSObject *, __int64, int *))(*(_QWORD *)v22 + 80LL))(v22, 3, &v30);
        v7 = v17;
        v18 = 1;
        if ( v17 < 0 )
        {
          v19 = 233;
          goto LABEL_27;
        }
        v25 = 0;
        v17 = DBAutoTopLevelTransact::EndTransaction((DBAutoTopLevelTransact *)v27, 1, &v25);
        v7 = v17;
        if ( v17 < 0 )
        {
          v19 = 236;
LABEL_26:
          v18 = 1;
LABEL_27:
          v20 = (unsigned int)v17;
          goto LABEL_28;
        }
        if ( !v25 )
        {
          v7 = -2147418113;
          v19 = 237;
          v20 = 2147549183LL;
          v18 = 0;
LABEL_28:
          Log_UnistoreHREvent_0(
            v20,
            v18,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
            v19);
          _FreeUSBlob((struct _USBLOB *)&v26);
LABEL_29:
          DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v27);
LABEL_30:
          if ( hMem )
            LocalFree(hMem);
LABEL_38:
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v22);
          goto LABEL_43;
        }
        _FreeUSBlob((struct _USBLOB *)&v26);
        DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v27);
      }
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 96LL))(v24);
      if ( hMem )
        LocalFree(hMem);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v22);
    }
    if ( v7 == -2147024871 )
    {
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v24);
      return 0;
    }
    v8 = 242;
    v9 = 0;
    v10 = v7;
  }
  else
  {
    v8 = 175;
    v9 = 1;
    v10 = (unsigned int)v6;
  }
  Log_UnistoreHREvent_0(
    v10,
    v9,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
    v8);
LABEL_43:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v24);
  return v7;
}

```

## disassembly

```asm
0x180098260  mov     [rsp-8+arg_10], rbx
0x180098265  push    rbp
0x180098266  push    rsi
0x180098267  push    rdi
0x180098268  push    r12
0x18009826a  push    r14
0x18009826c  lea     rbp, [rsp-37h]
0x180098271  sub     rsp, 100h
0x180098278  mov     rax, cs:__security_cookie
0x18009827f  xor     rax, rsp
0x180098282  mov     [rbp+57h+var_30], rax
0x180098286  mov     rax, [rcx]
0x180098289  mov     r14, rdx
0x18009828c  lea     rdx, [rbp+57h+var_D0]
0x180098290  mov     [rbp+57h+var_A0], 20003h
0x180098297  mov     [rsp+120h+var_F0], rdx
0x18009829c  xor     r9d, r9d
0x18009829f  mov     [rsp+120h+var_F8], 0
0x1800982a8  xor     r8d, r8d
0x1800982ab  mov     rax, [rax+88h]
0x1800982b2  mov     [rbp+57h+var_9C], 22000Bh
0x1800982b9  lea     edx, [r9+3]
0x1800982bd  mov     [rbp+57h+var_98], 380041h
0x1800982c4  mov     [rbp+57h+var_94], 3F0064h
0x1800982cb  mov     [rbp+57h+var_90], 400064h
0x1800982d2  mov     [rbp+57h+var_D0], 0
0x1800982da  mov     [rsp+120h+var_100], 0
0x1800982e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800982e8  mov     ebx, eax
0x1800982ea  test    eax, eax
0x1800982ec  jns     short loc_180098300
0x1800982ee  mov     r9d, 0AFh
0x1800982f4  mov     edx, 1
0x1800982f9  mov     ecx, eax
0x1800982fb  jmp     loc_1800985E3
0x180098300  mov     rcx, [rbp+57h+var_D0]
0x180098304  mov     rax, [rcx]
0x180098307  mov     rax, [rax+78h]
0x18009830b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098310  mov     ebx, eax
0x180098312  mov     esi, 1
0x180098317  mov     r12d, 300h
0x18009831d  test    ebx, ebx
0x18009831f  jnz     loc_1800985C4
0x180098325  mov     rcx, [rbp+57h+var_D0]
0x180098329  lea     rdx, [rsp+120h+var_E0]
0x18009832e  mov     [rsp+120h+var_E0], 0
0x180098337  mov     rax, [rcx]
0x18009833a  mov     rax, [rax+28h]
0x18009833e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098343  mov     ebx, eax
0x180098345  test    eax, eax
0x180098347  js      loc_1800985A2
0x18009834d  mov     rdi, [rsp+120h+var_E0]
0x180098352  lea     rcx, [rsp+120h+hMem]
0x180098357  mov     [rsp+120h+hMem], 0
0x180098360  mov     rax, [rdi]
0x180098363  mov     rbx, [rax+30h]
0x180098367  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_array_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_array_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x18009836c  xor     r9d, r9d
0x18009836f  mov     [rsp+120h+var_100], rax
0x180098374  lea     r8, [rbp+57h+var_A0]
0x180098378  mov     rcx, rdi
0x18009837b  mov     rax, rbx
0x18009837e  lea     edx, [r9+5]
0x180098382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098387  mov     ebx, eax
0x180098389  test    eax, eax
0x18009838b  js      loc_18009858A
0x180098391  mov     rax, [rsp+120h+hMem]
0x180098396  test    [rax+1Eh], r12w
0x18009839b  jnz     loc_1800984E6
0x1800983a1  test    [rax+36h], r12w
0x1800983a6  jz      loc_1800984E6
0x1800983ac  mov     rdx, r14
0x1800983af  lea     rcx, [rbp+57h+var_B0]
0x1800983b3  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x1800983b8  mov     r9, [rsp+120h+hMem]
0x1800983bd  lea     rcx, [rbp+57h+var_B0]; this
0x1800983c1  add     r9, 8; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x1800983c5  mov     [rbp+57h+var_A8], 0
0x1800983cc  mov     r8d, esi; unsigned int
0x1800983cf  mov     edx, 3; unsigned int
0x1800983d4  call    ?StartTransaction@DBAutoTopLevelTransact@@QEAAJKKPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@Z; DBAutoTopLevelTransact::StartTransaction(ulong,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *)
0x1800983d9  mov     ebx, eax
0x1800983db  test    eax, eax
0x1800983dd  js      loc_180098572
0x1800983e3  mov     rax, [rsp+120h+hMem]
0x1800983e8  test    [rax+4Eh], r12w
0x1800983ed  jnz     short loc_1800983F5
0x1800983ef  lea     rbx, [rax+50h]
0x1800983f3  jmp     short loc_180098402
0x1800983f5  xor     ebx, ebx
0x1800983f7  test    [rax+66h], r12w
0x1800983fc  jnz     short loc_180098402
0x1800983fe  lea     rbx, [rax+68h]
0x180098402  xor     edx, edx; Val
0x180098404  mov     [rbp+57h+var_80], 0
0x18009840b  xorps   xmm0, xmm0
0x18009840e  lea     rcx, [rbp+57h+var_7C]; void *
0x180098412  movdqa  [rbp+57h+var_C0], xmm0
0x180098417  lea     r8d, [rdx+44h]; Size
0x18009841b  call    memset_0
0x180098420  test    rbx, rbx
0x180098423  jz      short loc_18009845F
0x180098425  mov     rdx, [rsp+120h+var_E0]; struct IUSObject *
0x18009842a  lea     r8, [rbp+57h+var_C0]; struct _USBLOB *
0x18009842e  mov     rcx, rbx; struct _USBLOB *
0x180098431  call    ?UpgradeRecurrenceData@@YAJPEBU_USBLOB@@PEAUIUSObject@@PEAU1@@Z; UpgradeRecurrenceData(_USBLOB const *,IUSObject *,_USBLOB *)
0x180098436  mov     ebx, eax
0x180098438  test    eax, eax
0x18009843a  js      loc_180098517
0x180098440  mov     eax, dword ptr [rbp+57h+var_C0]
0x180098443  movsd   xmm0, qword ptr [rbp+57h+var_C0+4]
0x180098448  mov     [rbp+57h+var_78], eax
0x18009844b  mov     eax, dword ptr [rbp+57h+var_C0+0Ch]
0x18009844e  mov     [rbp+57h+var_6C], eax
0x180098451  mov     [rbp+57h+var_80], 380041h
0x180098458  movsd   [rbp+57h+var_74], xmm0
0x18009845d  jmp     short loc_18009846D
0x18009845f  mov     [rbp+57h+var_80], 22000Bh
0x180098466  mov     [rbp+57h+var_78], 0
0x18009846d  mov     rcx, [rsp+120h+var_E0]
0x180098472  lea     r8, [rbp+57h+var_80]
0x180098476  mov     edi, 200h
0x18009847b  mov     [rbp+57h+var_68], 3F0064h
0x180098482  mov     [rbp+57h+var_62], di
0x180098486  xor     r9d, r9d
0x180098489  mov     [rbp+57h+var_50], 400064h
0x180098490  mov     [rbp+57h+var_4A], di
0x180098494  mov     rax, [rcx]
0x180098497  lea     edx, [r9+3]
0x18009849b  mov     rax, [rax+50h]
0x18009849f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800984a4  mov     ebx, eax
0x1800984a6  mov     edx, esi; int
0x1800984a8  test    eax, eax
0x1800984aa  js      loc_18009856A
0x1800984b0  lea     r8, [rbp+57h+var_C8]; int *
0x1800984b4  mov     [rbp+57h+var_C8], 0
0x1800984bb  lea     rcx, [rbp+57h+var_B0]; this
0x1800984bf  call    ?EndTransaction@DBAutoTopLevelTransact@@QEAAJHPEAH@Z; DBAutoTopLevelTransact::EndTransaction(int,int *)
0x1800984c4  mov     ebx, eax
0x1800984c6  test    eax, eax
0x1800984c8  js      loc_180098562
0x1800984ce  cmp     [rbp+57h+var_C8], 0
0x1800984d2  jz      short loc_180098551
0x1800984d4  lea     rcx, [rbp+57h+var_C0]; struct _USBLOB *
0x1800984d8  call    ?_FreeUSBlob@@YAXPEAU_USBLOB@@@Z; _FreeUSBlob(_USBLOB *)
0x1800984dd  lea     rcx, [rbp+57h+var_B0]; this
0x1800984e1  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x1800984e6  mov     rcx, [rbp+57h+var_D0]
0x1800984ea  mov     rax, [rcx]
0x1800984ed  mov     rax, [rax+60h]
0x1800984f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800984f6  mov     rcx, [rsp+120h+hMem]; hMem
0x1800984fb  mov     ebx, eax
0x1800984fd  test    rcx, rcx
0x180098500  jz      short loc_180098508
0x180098502  call    cs:__imp_LocalFree
0x180098508  lea     rcx, [rsp+120h+var_E0]; void *
0x18009850d  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180098512  jmp     loc_18009831D
0x180098517  mov     r9d, 0D4h
0x18009851d  mov     edx, esi
0x18009851f  mov     ecx, eax
0x180098521  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098528  call    Log_UnistoreHREvent_0
0x18009852d  lea     rcx, [rbp+57h+var_C0]; struct _USBLOB *
0x180098531  call    ?_FreeUSBlob@@YAXPEAU_USBLOB@@@Z; _FreeUSBlob(_USBLOB *)
0x180098536  lea     rcx, [rbp+57h+var_B0]; this
0x18009853a  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18009853f  mov     rcx, [rsp+120h+hMem]; hMem
0x180098544  test    rcx, rcx
0x180098547  jz      short loc_1800985B8
0x180098549  call    cs:__imp_LocalFree
0x18009854f  jmp     short loc_1800985B8
0x180098551  mov     ebx, 8000FFFFh
0x180098556  mov     r9d, 0EDh
0x18009855c  mov     ecx, ebx
0x18009855e  xor     edx, edx
0x180098560  jmp     short loc_180098521
0x180098562  mov     r9d, 0ECh
0x180098568  jmp     short loc_18009851D
0x18009856a  mov     r9d, 0E9h
0x180098570  jmp     short loc_18009851F
0x180098572  mov     r9d, 0C0h
0x180098578  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009857f  mov     edx, esi
0x180098581  mov     ecx, eax
0x180098583  call    Log_UnistoreHREvent_0
0x180098588  jmp     short loc_180098536
0x18009858a  mov     r9d, 0B8h
0x180098590  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098597  mov     edx, esi
0x180098599  mov     ecx, eax
0x18009859b  call    Log_UnistoreHREvent_0
0x1800985a0  jmp     short loc_18009853F
0x1800985a2  mov     r9d, 0B5h
0x1800985a8  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800985af  mov     edx, esi
0x1800985b1  mov     ecx, eax
0x1800985b3  call    Log_UnistoreHREvent_0
0x1800985b8  lea     rcx, [rsp+120h+var_E0]; void *
0x1800985bd  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800985c2  jmp     short loc_1800985EF
0x1800985c4  cmp     ebx, 80070019h
0x1800985ca  jnz     short loc_1800985D9
0x1800985cc  lea     rcx, [rbp+57h+var_D0]; void *
0x1800985d0  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800985d5  xor     eax, eax
0x1800985d7  jmp     short loc_1800985FA
0x1800985d9  mov     r9d, 0F2h
0x1800985df  xor     edx, edx
0x1800985e1  mov     ecx, ebx
0x1800985e3  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800985ea  call    Log_UnistoreHREvent_0
0x1800985ef  lea     rcx, [rbp+57h+var_D0]; void *
0x1800985f3  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800985f8  mov     eax, ebx
0x1800985fa  mov     rcx, [rbp+57h+var_30]
0x1800985fe  xor     rcx, rsp; StackCookie
0x180098601  call    __security_check_cookie
0x180098606  mov     rbx, [rsp+120h+arg_10]
0x18009860e  add     rsp, 100h
0x180098615  pop     r14
0x180098617  pop     r12
0x180098619  pop     rdi
0x18009861a  pop     rsi
0x18009861b  pop     rbp
0x18009861c  retn
```
