# CWcnwizDevice::PopulateFromFunctionInstance(IFunctionInstance *)

- ea: `0x18001af24`
- end: `0x18001b391`
- name: `?PopulateFromFunctionInstance@CWcnwizDevice@@QEAAJPEAUIFunctionInstance@@@Z`
- size: `1133`
- prototype: `__int64 __fastcall(CWcnwizDevice *__hidden this, struct IFunctionInstance *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017a20`
- `0x18001c580`

## callees

- `0x180003abc`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18001abbc`
- `0x18001ad60`
- `0x18001af24`
- `0x18001b3b0`
- `0x18001b464`
- `0x18001eaac`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b057`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWcnwizDevice::PopulateFromFunctionInstance(GUID *this, struct IFunctionInstance *a2)
{
  _QWORD *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  int v7; // ebx
  int v8; // eax
  _QWORD *v9; // r10
  __int64 v10; // rdx
  __int64 (*OpenPropertyStore)(void); // rax
  bool v12; // r12
  char v13; // r13
  __int64 v14; // rax
  __int64 v15; // rdx
  char v16; // bl
  _DWORD *v17; // rcx
  int v18; // ebx
  int v19; // r14d
  unsigned int Data1; // r15d
  unsigned int v21; // eax
  __int64 v22; // r10
  int v23; // edx
  int v24; // r8d
  __int64 v25; // r11
  const char *v26; // rax
  __int64 v27; // r10
  unsigned int v28; // eax
  __int64 v29; // r10
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // [rsp+50h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-70h] BYREF
  std::bad_alloc *v35; // [rsp+60h] [rbp-68h] BYREF
  std::bad_alloc *v36; // [rsp+68h] [rbp-60h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+70h] [rbp-58h] BYREF
  _DWORD *v38; // [rsp+80h] [rbp-48h]
  char v39; // [rsp+D8h] [rbp+10h]
  char v40; // [rsp+E0h] [rbp+18h]
  char v41; // [rsp+E8h] [rbp+20h]

  v33 = 0;
  *(_OWORD *)lpsz = 0;
  v38 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 10, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_s(v4[2], 11, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids, "pFunctionInstance");
    v7 = -2147467261;
    goto LABEL_60;
  }
  *(_OWORD *)lpsz = 0;
  v38 = 0;
  pv = 0;
  v8 = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))a2->lpVtbl->GetID)(a2, &pv);
  v7 = v8;
  if ( v8 >= 0 )
  {
    std::_WChar_traits<unsigned short>::length(pv);
    try
    {
      ((void (*)(void))std::wstring::_Assign<unsigned short>)();
      CoTaskMemFree(pv);
      pv = 0;
      OpenPropertyStore = (__int64 (*)(void))a2->lpVtbl->OpenPropertyStore;
    }
    catch ( std::bad_alloc *v36 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v32 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v36 + 8LL))(v36);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids, v32);
      }
      v7 = -2147024882;
      goto LABEL_55;
    }
    v8 = OpenPropertyStore();
    v7 = v8;
    if ( v8 >= 0 )
    {
      v12 = 0;
      v41 = 0;
      v39 = 0;
      v40 = 0;
      v13 = 0;
      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPCOLESTR *))(*(_QWORD *)v33 + 40LL))(
             v33,
             &PKEY_PNPX_GlobalIdentity,
             lpsz) >= 0
        && LOWORD(lpsz[0]) == 31 )
      {
        v12 = (int)WcnGuidFromString(lpsz[1], this) >= 0;
      }
      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPCOLESTR *))(*(_QWORD *)v33 + 40LL))(
             v33,
             &PKEY_WCN_ConfigMethods,
             lpsz) >= 0
        && LOWORD(lpsz[0]) == 3 )
      {
        this[5].Data1 = (unsigned int)lpsz[1];
        v41 = 1;
      }
      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPCOLESTR *))(*(_QWORD *)v33 + 40LL))(
             v33,
             &PKEY_WCN_AuthType,
             lpsz) >= 0
        && LOWORD(lpsz[0]) == 3 )
      {
        *(_DWORD *)&this[5].Data2 = lpsz[1];
        v39 = 1;
      }
      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPCOLESTR *))(*(_QWORD *)v33 + 40LL))(
             v33,
             &PKEY_WCN_EncryptType,
             lpsz) >= 0
        && LOWORD(lpsz[0]) == 3 )
      {
        *(_DWORD *)this[5].Data4 = lpsz[1];
        v40 = 1;
      }
      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPCOLESTR *))(*(_QWORD *)v33 + 40LL))(
             v33,
             &PKEY_DeviceDisplay_FriendlyName,
             lpsz) >= 0
        && LOWORD(lpsz[0]) == 31 )
      {
        try
        {
          v14 = std::_WChar_traits<unsigned short>::length(lpsz[1]);
          std::wstring::_Assign<unsigned short>(&this[3], v15, v14);
        }
        catch ( std::bad_alloc *v35 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v31 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v35 + 8LL))(v35);
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids, v31);
          }
          v7 = -2147024882;
          goto LABEL_55;
        }
        v13 = 1;
      }
      v16 = 0;
      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPCOLESTR *))(*(_QWORD *)v33 + 40LL))(
             v33,
             &PKEY_PNPX_PhysicalAddress,
             lpsz) >= 0
        && LOWORD(lpsz[0]) == 4113
        && LODWORD(lpsz[1]) == 6 )
      {
        v17 = v38;
        *(_DWORD *)&this[6].Data2 = *v38;
        *(_WORD *)this[6].Data4 = *((_WORD *)v17 + 2);
        v16 = 1;
      }
      CWcnwizDevice::GetVendorExtensionsIfAny((CWcnwizDevice *)this, a2);
      if ( !v39 )
        *(_DWORD *)&this[5].Data2 = 35;
      if ( !v40 )
        *(_DWORD *)this[5].Data4 = 15;
      if ( v12 && v13 && v16 && v41 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v18 = *(_DWORD *)this[5].Data4;
          v19 = *(_DWORD *)&this[5].Data2;
          Data1 = this[5].Data1;
          v21 = (unsigned int)GetIndent(0);
          WPP_SF_s_guid_SDDD(*(_QWORD *)(v22 + 16), v23, v24, v21, (__int64)this, v25, Data1, v19, v18);
          v9 = WPP_GLOBAL_Control;
        }
        v7 = 0;
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v26 = GetIndent(0);
          WPP_SF_s(*(_QWORD *)(v27 + 16), 17, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids, v26);
          v9 = WPP_GLOBAL_Control;
        }
        v7 = 1;
      }
      goto LABEL_56;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_60;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_56;
    v10 = 14;
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_60;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_56;
    v10 = 12;
  }
  WPP_SF_d(v9[2], v10, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids, (unsigned int)v8);
LABEL_55:
  v9 = WPP_GLOBAL_Control;
LABEL_56:
  if ( v9 != &WPP_GLOBAL_Control && (v7 < 0 || *((_BYTE *)v9 + 25) >= 6u) )
  {
    v28 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v29 + 16), 18, (unsigned int)WPP_510faab3c43a30fab228fe98e5d76271_Traceguids, v28, v7);
  }
LABEL_60:
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(&v33);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001af24  mov     r11, rsp
0x18001af27  push    rbx
0x18001af28  push    rsi
0x18001af29  push    rdi
0x18001af2a  push    r12
0x18001af2c  push    r13
0x18001af2e  push    r14
0x18001af30  push    r15
0x18001af32  sub     rsp, 90h
0x18001af39  mov     r15, rdx
0x18001af3c  mov     rdi, rcx
0x18001af3f  mov     qword ptr [r11-78h], 0
0x18001af47  xorps   xmm0, xmm0
0x18001af4a  xor     eax, eax
0x18001af4c  movups  xmmword ptr [rsp+0C8h+lpsz], xmm0
0x18001af51  mov     [r11-48h], rax
0x18001af55  lea     rsi, WPP_GLOBAL_Control
0x18001af5c  mov     r10, cs:WPP_GLOBAL_Control
0x18001af63  lea     r14d, [rax+1]
0x18001af67  cmp     r10, rsi
0x18001af6a  jz      short loc_18001AF99
0x18001af6c  cmp     byte ptr [r10+19h], 6
0x18001af71  jb      short loc_18001AF99
0x18001af73  mov     ecx, r14d; int
0x18001af76  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001af7b  lea     edx, [r14+9]
0x18001af7f  mov     r9, rax
0x18001af82  lea     r8, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids
0x18001af89  mov     rcx, [r10+10h]
0x18001af8d  call    WPP_SF_s
0x18001af92  mov     r10, cs:WPP_GLOBAL_Control
0x18001af99  test    r15, r15
0x18001af9c  jnz     short loc_18001AFCF
0x18001af9e  cmp     r10, rsi
0x18001afa1  jz      short loc_18001AFC5
0x18001afa3  cmp     byte ptr [r10+19h], 2
0x18001afa8  jb      short loc_18001AFC5
0x18001afaa  lea     edx, [r15+0Bh]
0x18001afae  lea     r9, aPfunctioninsta; "pFunctionInstance"
0x18001afb5  lea     r8, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids
0x18001afbc  mov     rcx, [r10+10h]
0x18001afc0  call    WPP_SF_s
0x18001afc5  mov     ebx, 80004003h
0x18001afca  jmp     loc_18001B372
0x18001afcf  xorps   xmm0, xmm0
0x18001afd2  xor     eax, eax
0x18001afd4  movups  xmmword ptr [rsp+0C8h+lpsz], xmm0
0x18001afd9  mov     [rsp+0C8h+var_48], rax
0x18001afe1  mov     [rsp+0C8h+pv], rax
0x18001afe6  mov     rax, [r15]
0x18001afe9  lea     rdx, [rsp+0C8h+pv]
0x18001afee  mov     rcx, r15
0x18001aff1  mov     rax, [rax+20h]
0x18001aff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001affa  mov     ebx, eax
0x18001affc  test    eax, eax
0x18001affe  jns     short loc_18001B038
0x18001b000  mov     r10, cs:WPP_GLOBAL_Control
0x18001b007  cmp     r10, rsi
0x18001b00a  jz      loc_18001B372
0x18001b010  cmp     byte ptr [r10+19h], 2
0x18001b015  jb      loc_18001B33D
0x18001b01b  mov     edx, 0Ch
0x18001b020  mov     r9d, eax
0x18001b023  lea     r8, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids
0x18001b02a  mov     rcx, [r10+10h]
0x18001b02e  call    WPP_SF_d
0x18001b033  jmp     loc_18001B336
0x18001b038  mov     rdx, [rsp+0C8h+pv]
0x18001b03d  mov     rcx, rdx
0x18001b040  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001b045  lea     rcx, [rdi+10h]
0x18001b049  mov     r8, rax
0x18001b04c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001b051  nop
0x18001b052  mov     rcx, [rsp+0C8h+pv]; pv
0x18001b057  call    cs:__imp_CoTaskMemFree
0x18001b05d  mov     [rsp+0C8h+pv], 0
0x18001b066  mov     rax, [r15]
0x18001b069  lea     r8, [rsp+0C8h+var_78]
0x18001b06e  xor     edx, edx
0x18001b070  mov     rcx, r15
0x18001b073  mov     rax, [rax+30h]
0x18001b077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b07c  mov     ebx, eax
0x18001b07e  test    eax, eax
0x18001b080  jns     short loc_18001B0A7
0x18001b082  mov     r10, cs:WPP_GLOBAL_Control
0x18001b089  cmp     r10, rsi
0x18001b08c  jz      loc_18001B372
0x18001b092  cmp     byte ptr [r10+19h], 2
0x18001b097  jb      loc_18001B33D
0x18001b09d  mov     edx, 0Eh
0x18001b0a2  jmp     loc_18001B020
0x18001b0a7  xor     r12b, r12b
0x18001b0aa  mov     [rsp+0C8h+arg_18], r12b
0x18001b0b2  mov     byte ptr [rsp+0C8h+arg_8], r12b
0x18001b0ba  mov     [rsp+0C8h+arg_10], r12b
0x18001b0c2  xor     r13b, r13b
0x18001b0c5  mov     rcx, [rsp+0C8h+var_78]
0x18001b0ca  mov     rax, [rcx]
0x18001b0cd  lea     r8, [rsp+0C8h+lpsz]
0x18001b0d2  lea     rdx, PKEY_PNPX_GlobalIdentity
0x18001b0d9  mov     rax, [rax+28h]
0x18001b0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0e2  test    eax, eax
0x18001b0e4  js      short loc_18001B105
0x18001b0e6  cmp     word ptr [rsp+0C8h+lpsz], 1Fh
0x18001b0ec  jnz     short loc_18001B105
0x18001b0ee  mov     rdx, rdi; lpiid
0x18001b0f1  mov     rcx, [rsp+0C8h+lpsz+8]; lpsz
0x18001b0f6  call    ?WcnGuidFromString@@YAJPEBGPEAU_GUID@@@Z; WcnGuidFromString(ushort const *,_GUID *)
0x18001b0fb  movzx   r12d, r12b
0x18001b0ff  test    eax, eax
0x18001b101  cmovns  r12d, r14d
0x18001b105  mov     rcx, [rsp+0C8h+var_78]
0x18001b10a  mov     rax, [rcx]
0x18001b10d  lea     r8, [rsp+0C8h+lpsz]
0x18001b112  lea     rdx, PKEY_WCN_ConfigMethods
0x18001b119  mov     rax, [rax+28h]
0x18001b11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b122  test    eax, eax
0x18001b124  js      short loc_18001B13D
0x18001b126  cmp     word ptr [rsp+0C8h+lpsz], 3
0x18001b12c  jnz     short loc_18001B13D
0x18001b12e  mov     eax, dword ptr [rsp+0C8h+lpsz+8]
0x18001b132  mov     [rdi+50h], eax
0x18001b135  mov     [rsp+0C8h+arg_18], r14b
0x18001b13d  mov     rcx, [rsp+0C8h+var_78]
0x18001b142  mov     rax, [rcx]
0x18001b145  lea     r8, [rsp+0C8h+lpsz]
0x18001b14a  lea     rdx, PKEY_WCN_AuthType
0x18001b151  mov     rax, [rax+28h]
0x18001b155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b15a  test    eax, eax
0x18001b15c  js      short loc_18001B175
0x18001b15e  cmp     word ptr [rsp+0C8h+lpsz], 3
0x18001b164  jnz     short loc_18001B175
0x18001b166  mov     eax, dword ptr [rsp+0C8h+lpsz+8]
0x18001b16a  mov     [rdi+54h], eax
0x18001b16d  mov     byte ptr [rsp+0C8h+arg_8], r14b
0x18001b175  mov     rcx, [rsp+0C8h+var_78]
0x18001b17a  mov     rax, [rcx]
0x18001b17d  lea     r8, [rsp+0C8h+lpsz]
0x18001b182  lea     rdx, PKEY_WCN_EncryptType
0x18001b189  mov     rax, [rax+28h]
0x18001b18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b192  test    eax, eax
0x18001b194  js      short loc_18001B1AD
0x18001b196  cmp     word ptr [rsp+0C8h+lpsz], 3
0x18001b19c  jnz     short loc_18001B1AD
0x18001b19e  mov     eax, dword ptr [rsp+0C8h+lpsz+8]
0x18001b1a2  mov     [rdi+58h], eax
0x18001b1a5  mov     [rsp+0C8h+arg_10], r14b
0x18001b1ad  mov     rcx, [rsp+0C8h+var_78]
0x18001b1b2  mov     rax, [rcx]
0x18001b1b5  lea     r8, [rsp+0C8h+lpsz]
0x18001b1ba  lea     rdx, PKEY_DeviceDisplay_FriendlyName
0x18001b1c1  mov     rax, [rax+28h]
0x18001b1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1ca  test    eax, eax
0x18001b1cc  js      short loc_18001B1F3
0x18001b1ce  cmp     word ptr [rsp+0C8h+lpsz], 1Fh
0x18001b1d4  jnz     short loc_18001B1F3
0x18001b1d6  mov     rdx, [rsp+0C8h+lpsz+8]
0x18001b1db  mov     rcx, rdx
0x18001b1de  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001b1e3  lea     rcx, [rdi+30h]
0x18001b1e7  mov     r8, rax
0x18001b1ea  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001b1ef  nop
0x18001b1f0  mov     r13b, r14b
0x18001b1f3  xor     bl, bl
0x18001b1f5  mov     rcx, [rsp+0C8h+var_78]
0x18001b1fa  mov     rax, [rcx]
0x18001b1fd  lea     r8, [rsp+0C8h+lpsz]
0x18001b202  lea     rdx, PKEY_PNPX_PhysicalAddress
0x18001b209  mov     rax, [rax+28h]
0x18001b20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b212  test    eax, eax
0x18001b214  js      short loc_18001B241
0x18001b216  mov     eax, 1011h
0x18001b21b  cmp     word ptr [rsp+0C8h+lpsz], ax
0x18001b220  jnz     short loc_18001B241
0x18001b222  cmp     dword ptr [rsp+0C8h+lpsz+8], 6
0x18001b227  jnz     short loc_18001B241
0x18001b229  mov     rcx, [rsp+0C8h+var_48]
0x18001b231  mov     eax, [rcx]
0x18001b233  mov     [rdi+64h], eax
0x18001b236  movzx   eax, word ptr [rcx+4]
0x18001b23a  mov     [rdi+68h], ax
0x18001b23e  mov     bl, r14b
0x18001b241  mov     rdx, r15; struct IFunctionInstance *
0x18001b244  mov     rcx, rdi; this
0x18001b247  call    ?GetVendorExtensionsIfAny@CWcnwizDevice@@AEAAXPEAUIFunctionInstance@@@Z; CWcnwizDevice::GetVendorExtensionsIfAny(IFunctionInstance *)
0x18001b24c  cmp     byte ptr [rsp+0C8h+arg_8], 0
0x18001b254  jnz     short loc_18001B25D
0x18001b256  mov     dword ptr [rdi+54h], 23h ; '#'
0x18001b25d  cmp     [rsp+0C8h+arg_10], 0
0x18001b265  jnz     short loc_18001B26E
0x18001b267  mov     dword ptr [rdi+58h], 0Fh
0x18001b26e  test    r12b, r12b
0x18001b271  jz      short loc_18001B2EA
0x18001b273  test    r13b, r13b
0x18001b276  jz      short loc_18001B2EA
0x18001b278  test    bl, bl
0x18001b27a  jz      short loc_18001B2EA
0x18001b27c  cmp     [rsp+0C8h+arg_18], 0
0x18001b284  jz      short loc_18001B2EA
0x18001b286  mov     r10, cs:WPP_GLOBAL_Control
0x18001b28d  cmp     r10, rsi
0x18001b290  jz      short loc_18001B2E4
0x18001b292  cmp     byte ptr [r10+19h], 5
0x18001b297  jb      short loc_18001B2E4
0x18001b299  mov     ebx, [rdi+58h]
0x18001b29c  mov     r14d, [rdi+54h]
0x18001b2a0  mov     r15d, [rdi+50h]
0x18001b2a4  lea     r11, [rdi+30h]
0x18001b2a8  cmp     qword ptr [r11+18h], 7
0x18001b2ad  jbe     short loc_18001B2B2
0x18001b2af  mov     r11, [r11]
0x18001b2b2  xor     ecx, ecx; int
0x18001b2b4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001b2b9  mov     [rsp+0C8h+var_88], ebx
0x18001b2bd  mov     [rsp+0C8h+var_90], r14d
0x18001b2c2  mov     [rsp+0C8h+var_98], r15d
0x18001b2c7  mov     [rsp+0C8h+var_A0], r11
0x18001b2cc  mov     [rsp+0C8h+var_A8], rdi
0x18001b2d1  mov     r9, rax
0x18001b2d4  mov     rcx, [r10+10h]
0x18001b2d8  call    WPP_SF_s_guid_SDDD
0x18001b2dd  mov     r10, cs:WPP_GLOBAL_Control
0x18001b2e4  xor     ebx, ebx
0x18001b2e6  jmp     short loc_18001B33D
0x18001b2e8  jmp     short loc_18001B328
0x18001b2ea  mov     r10, cs:WPP_GLOBAL_Control
0x18001b2f1  cmp     r10, rsi
0x18001b2f4  jz      short loc_18001B323
0x18001b2f6  cmp     byte ptr [r10+19h], 3
0x18001b2fb  jb      short loc_18001B323
0x18001b2fd  xor     ecx, ecx; int
0x18001b2ff  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001b304  mov     edx, 11h
0x18001b309  mov     r9, rax
0x18001b30c  lea     r8, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids
0x18001b313  mov     rcx, [r10+10h]
0x18001b317  call    WPP_SF_s
0x18001b31c  mov     r10, cs:WPP_GLOBAL_Control
0x18001b323  mov     ebx, r14d
0x18001b326  jmp     short loc_18001B33D
0x18001b328  mov     ebx, [rsp+0C8h+arg_8]
0x18001b32f  lea     rsi, WPP_GLOBAL_Control
0x18001b336  mov     r10, cs:WPP_GLOBAL_Control
0x18001b33d  cmp     r10, rsi
0x18001b340  jz      short loc_18001B372
0x18001b342  test    ebx, ebx
0x18001b344  js      short loc_18001B34D
0x18001b346  cmp     byte ptr [r10+19h], 6
0x18001b34b  jb      short loc_18001B372
0x18001b34d  or      ecx, 0FFFFFFFFh; int
0x18001b350  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001b355  mov     edx, 12h
0x18001b35a  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x18001b35e  mov     r9, rax
0x18001b361  lea     r8, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids
0x18001b368  mov     rcx, [r10+10h]
0x18001b36c  call    WPP_SF_sd
0x18001b371  nop
0x18001b372  lea     rcx, [rsp+0C8h+var_78]
0x18001b377  call    ??1?$CComPtrBase@UIWCNDevicePrivate@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(void)
0x18001b37c  mov     eax, ebx
0x18001b37e  add     rsp, 90h
0x18001b385  pop     r15
0x18001b387  pop     r14
0x18001b389  pop     r13
0x18001b38b  pop     r12
0x18001b38d  pop     rdi
0x18001b38e  pop     rsi
0x18001b38f  pop     rbx
0x18001b390  retn
```
