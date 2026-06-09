# SessionDataUtil::WUOptionalSessionInfo5::Initialize(ulong,void const *,ulong,IUnknown *)

- ea: `0x1400170dc`
- end: `0x1400174f5`
- name: `?Initialize@WUOptionalSessionInfo5@SessionDataUtil@@AEAAJKPEBXKPEAUIUnknown@@@Z`
- size: `1049`
- prototype: `__int64 __fastcall(SessionDataUtil::WUOptionalSessionInfo5 *__hidden this, unsigned int, const void *, unsigned int, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x140016ef8`

## callees

- `0x140002ac0`
- `0x14000d4cc`
- `0x14000d538`
- `0x140013cf0`
- `0x140016b20`
- `0x140017044`
- `0x1400170dc`
- `0x1400186e8`
- `0x1400187e4`
- `0x1400188c8`
- `0x14001aa60`
- `0x1400206e0`

## string_xrefs

- `0x1400173a7`: `DownloadFlagsUseUpdatePriority`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo5::Initialize(
        SessionDataUtil::WUOptionalSessionInfo5 *this,
        unsigned int a2,
        char *a3,
        unsigned int a4,
        struct IUnknown *a5)
{
  double v5; // xmm3_8
  signed int Instance; // ebx
  __int64 v11; // rdx
  void **v13; // r15
  void *v14; // rax
  struct IUnknownVtbl *lpVtbl; // rax
  int v16; // eax
  struct ABI::Windows::Data::Json::IJsonObject **v17; // r9
  unsigned int v18; // edi
  int NamedObject; // eax
  const wchar_t *v20; // r8
  JsonUtil *v21; // rbx
  __int64 v22; // rdx
  const wchar_t *v23; // r8
  const wchar_t *v24; // r8
  const wchar_t *v25; // r8
  const wchar_t *v26; // r8
  const wchar_t *v27; // r8
  const wchar_t *v28; // r8
  const wchar_t *v29; // r8
  const wchar_t *v30; // r8
  int v31; // eax
  __int128 v32; // xmm1
  int v33; // ecx
  char *v34; // rax
  int v35; // [rsp+20h] [rbp-58h]
  unsigned __int8 v36[8]; // [rsp+30h] [rbp-48h] BYREF
  double v37; // [rsp+38h] [rbp-40h]
  wchar_t v38[4]; // [rsp+40h] [rbp-38h] BYREF
  JsonUtil *v39; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  if ( !a3 )
  {
    Instance = -2147024809;
    v11 = 617;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)Instance,
      v35);
    return (unsigned int)Instance;
  }
  v13 = (void **)((char *)this + 48);
  if ( a2 >= 5 )
  {
    *(_OWORD *)this = *(_OWORD *)(a3 + 68);
    *((_OWORD *)this + 1) = *(_OWORD *)(a3 + 84);
    *((_DWORD *)this + 8) = *((_DWORD *)a3 + 25);
    if ( *v13 )
    {
      SusFree(*v13);
      *v13 = 0;
    }
    v14 = SafeSusAllocArray(1u, 0x68u);
    *v13 = v14;
    Instance = v14 == 0 ? 0x8007000E : 0;
    if ( !v14 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25F,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)(unsigned int)Instance,
        v35);
      v11 = 618;
      goto LABEL_3;
    }
  }
  WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease((char *)this + 40);
  Instance = SessionDataUtil::WUOptionalSessionInfo4::CreateInstance(
               a2,
               a3,
               a4,
               a5,
               (struct SessionDataUtil::WUOptionalSessionInfo4 **)this + 5);
  if ( Instance < 0 )
  {
    v11 = 624;
    goto LABEL_3;
  }
  Instance = SessionDataUtil::WUOptionalSessionInfo5::InitOptionalSessionInfo5(this, *v13);
  if ( Instance < 0 )
  {
    v11 = 626;
    goto LABEL_3;
  }
  if ( a2 < 5 || !a5 || a4 < 5 )
    return 0;
  lpVtbl = a5->lpVtbl;
  v39 = 0;
  v16 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, JsonUtil **))lpVtbl->QueryInterface)(
          a5,
          &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
          &v39);
  v18 = v16;
  if ( v16 >= 0 )
  {
    *(_QWORD *)v38 = 0;
    NamedObject = JsonUtil::GetNamedObject(v39, L"DownloadProperties", v38, v17);
    v18 = NamedObject;
    v21 = *(JsonUtil **)v38;
    if ( NamedObject < 0 )
    {
      v22 = 638;
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)(unsigned int)NamedObject,
        v35);
      goto LABEL_42;
    }
    if ( *(_QWORD *)v38 )
    {
      v36[0] = 0;
      LOBYTE(v20) = a3[68];
      NamedObject = JsonUtil::GetBooleanPropertyWithDefault(*(JsonUtil **)v38, L"DownloadFlagsInteractive", v20, v36);
      v18 = NamedObject;
      if ( NamedObject < 0 )
      {
        v22 = 648;
        goto LABEL_39;
      }
      *(_DWORD *)this = v36[0] != 0;
      LOBYTE(v23) = a3[72];
      NamedObject = JsonUtil::GetBooleanPropertyWithDefault(v21, L"DownloadFlagsBypassRegulation", v23, v36);
      v18 = NamedObject;
      if ( NamedObject < 0 )
      {
        v22 = 655;
        goto LABEL_39;
      }
      *((_DWORD *)this + 1) = v36[0] != 0;
      LOBYTE(v24) = a3[76];
      NamedObject = JsonUtil::GetBooleanPropertyWithDefault(v21, L"DownloadFlagsSerialize", v24, v36);
      v18 = NamedObject;
      if ( NamedObject < 0 )
      {
        v22 = 662;
        goto LABEL_39;
      }
      *((_DWORD *)this + 2) = v36[0] != 0;
      LOBYTE(v25) = a3[80];
      NamedObject = JsonUtil::GetBooleanPropertyWithDefault(v21, L"DownloadFlagsOnBattery", v25, v36);
      v18 = NamedObject;
      if ( NamedObject < 0 )
      {
        v22 = 669;
        goto LABEL_39;
      }
      *((_DWORD *)this + 3) = v36[0] != 0;
      LOBYTE(v26) = a3[84];
      NamedObject = JsonUtil::GetBooleanPropertyWithDefault(v21, L"DownloadFlagsFailOnTransient", v26, v36);
      v18 = NamedObject;
      if ( NamedObject < 0 )
      {
        v22 = 676;
        goto LABEL_39;
      }
      *((_DWORD *)this + 4) = v36[0] != 0;
      LOBYTE(v27) = a3[88];
      NamedObject = JsonUtil::GetBooleanPropertyWithDefault(v21, L"DownloadFlagsUseUpdatePriority", v27, v36);
      v18 = NamedObject;
      if ( NamedObject < 0 )
      {
        v22 = 683;
        goto LABEL_39;
      }
      *((_DWORD *)this + 5) = v36[0] != 0;
      LOBYTE(v28) = a3[92];
      NamedObject = JsonUtil::GetBooleanPropertyWithDefault(v21, L"DownloadFlagsIgnoreNetworkCostForSize", v28, v36);
      v18 = NamedObject;
      if ( NamedObject < 0 )
      {
        v22 = 690;
        goto LABEL_39;
      }
      *((_DWORD *)this + 6) = v36[0] != 0;
      v37 = 0.0;
      NamedObject = JsonUtil::GetNumberPropertyWithDefault(v21, L"DownloadPriority", v29, v5);
      v18 = NamedObject;
      if ( NamedObject < 0 )
      {
        v22 = 698;
        goto LABEL_39;
      }
      *((_DWORD *)this + 7) = (int)v37;
      v37 = 0.0;
      NamedObject = JsonUtil::GetNumberPropertyWithDefault(v21, L"CostPolicy", v30, v5);
      v18 = NamedObject;
      if ( NamedObject < 0 )
      {
        v22 = 706;
        goto LABEL_39;
      }
      v31 = (int)v37;
      *((_DWORD *)this + 8) = (int)v37;
      v32 = *((_OWORD *)this + 1);
      v33 = v31;
      v34 = (char *)*v13;
      *(_OWORD *)(v34 + 68) = *(_OWORD *)this;
      *(_OWORD *)(v34 + 84) = v32;
      *((_DWORD *)v34 + 25) = v33;
    }
    v18 = 0;
LABEL_42:
    if ( v21 )
      (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v21 + 16LL))(v21);
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x279,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)(unsigned int)v16,
    v35);
LABEL_44:
  if ( v39 )
    (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v39 + 16LL))(v39);
  return v18;
}

```

## disassembly

```asm
0x1400170dc  push    rbp
0x1400170de  push    rbx
0x1400170df  push    rsi
0x1400170e0  push    rdi
0x1400170e1  push    r12
0x1400170e3  push    r13
0x1400170e5  push    r14
0x1400170e7  push    r15
0x1400170e9  mov     rbp, rsp
0x1400170ec  sub     rsp, 78h
0x1400170f0  movaps  [rsp+78h+var_18], xmm6
0x1400170f5  mov     rax, cs:__security_cookie
0x1400170fc  xor     rax, rsp
0x1400170ff  mov     [rbp+var_28], rax
0x140017103  mov     r13d, r9d
0x140017106  mov     r14, r8
0x140017109  mov     edi, edx
0x14001710b  mov     rsi, rcx
0x14001710e  mov     r12, [rbp+arg_20]
0x140017112  test    r8, r8
0x140017115  jnz     short loc_14001713B
0x140017117  mov     ebx, 80070057h
0x14001711c  mov     edx, 269h; void *
0x140017121  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017128  mov     r9d, ebx; char *
0x14001712b  mov     rcx, [rbp+40h]; this
0x14001712f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017134  mov     eax, ebx
0x140017136  jmp     loc_1400174D3
0x14001713b  lea     r15, [rcx+30h]
0x14001713f  cmp     edi, 5
0x140017142  jb      short loc_1400171B7
0x140017144  movups  xmm0, xmmword ptr [r8+44h]
0x140017149  movups  xmmword ptr [rcx], xmm0
0x14001714c  movups  xmm1, xmmword ptr [r8+54h]
0x140017151  movups  xmmword ptr [rcx+10h], xmm1
0x140017155  mov     eax, [r8+64h]
0x140017159  mov     [rcx+20h], eax
0x14001715c  mov     rcx, [r15]; lpMem
0x14001715f  test    rcx, rcx
0x140017162  jz      short loc_140017170
0x140017164  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140017169  mov     qword ptr [r15], 0
0x140017170  mov     edx, 68h ; 'h'; unsigned __int64
0x140017175  lea     ecx, [rdx-67h]; unsigned __int64
0x140017178  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14001717d  mov     [r15], rax
0x140017180  mov     rcx, rax
0x140017183  neg     rcx
0x140017186  sbb     ebx, ebx
0x140017188  not     ebx
0x14001718a  and     ebx, 8007000Eh
0x140017190  test    rax, rax
0x140017193  jnz     short loc_1400171B7
0x140017195  mov     rcx, [rbp+40h]; this
0x140017199  mov     r9d, ebx; char *
0x14001719c  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400171a3  mov     edx, 25Fh; void *
0x1400171a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400171ad  mov     edx, 26Ah
0x1400171b2  jmp     loc_140017121
0x1400171b7  lea     rbx, [rsi+28h]
0x1400171bb  mov     rcx, rbx
0x1400171be  call    ?InternalRelease@?$XPtrBase@VWUOptionalSessionInfo4@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo4@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(void)
0x1400171c3  mov     qword ptr [rsp+78h+var_58], rbx; int
0x1400171c8  mov     r9, r12; struct IUnknown *
0x1400171cb  mov     r8d, r13d; unsigned int
0x1400171ce  mov     rdx, r14; void *
0x1400171d1  mov     ecx, edi; unsigned int
0x1400171d3  call    ?CreateInstance@WUOptionalSessionInfo4@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfo4::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo4 * *)
0x1400171d8  mov     ebx, eax
0x1400171da  test    eax, eax
0x1400171dc  jns     short loc_1400171E8
0x1400171de  mov     edx, 270h
0x1400171e3  jmp     loc_140017121
0x1400171e8  mov     rdx, [r15]; void *
0x1400171eb  mov     rcx, rsi; this
0x1400171ee  call    ?InitOptionalSessionInfo5@WUOptionalSessionInfo5@SessionDataUtil@@QEAAJPEAX@Z; SessionDataUtil::WUOptionalSessionInfo5::InitOptionalSessionInfo5(void *)
0x1400171f3  mov     ebx, eax
0x1400171f5  test    eax, eax
0x1400171f7  jns     short loc_140017203
0x1400171f9  mov     edx, 272h
0x1400171fe  jmp     loc_140017121
0x140017203  cmp     edi, 5
0x140017206  jb      loc_1400174D1
0x14001720c  test    r12, r12
0x14001720f  jz      loc_1400174D1
0x140017215  cmp     r13d, 5
0x140017219  jb      loc_1400174D1
0x14001721f  mov     rax, [r12]
0x140017223  xor     r13d, r13d
0x140017226  mov     [rbp+var_30], r13
0x14001722a  lea     r8, [rbp+var_30]
0x14001722e  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x140017235  mov     rcx, r12
0x140017238  mov     rax, [rax]
0x14001723b  call    _guard_dispatch_icall
0x140017240  mov     edi, eax
0x140017242  test    eax, eax
0x140017244  jns     short loc_140017263
0x140017246  mov     rcx, [rbp+40h]; this
0x14001724a  mov     r9d, eax; char *
0x14001724d  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017254  mov     edx, 279h; void *
0x140017259  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001725e  jmp     loc_1400174B7
0x140017263  mov     qword ptr [rbp+var_38], r13
0x140017267  lea     r8, [rbp+var_38]; wchar_t *
0x14001726b  lea     rdx, aDownloadproper; "DownloadProperties"
0x140017272  mov     rcx, [rbp+var_30]; this
0x140017276  call    ?GetNamedObject@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEAPEAU23456@@Z; JsonUtil::GetNamedObject(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,ABI::Windows::Data::Json::IJsonObject * *)
0x14001727b  mov     edi, eax
0x14001727d  mov     rbx, qword ptr [rbp+var_38]
0x140017281  test    eax, eax
0x140017283  jns     short loc_14001728F
0x140017285  mov     edx, 27Eh
0x14001728a  jmp     loc_14001746B
0x14001728f  test    rbx, rbx
0x140017292  jz      loc_14001749F
0x140017298  mov     [rbp+var_48], r13b
0x14001729c  lea     r9, [rbp+var_48]; unsigned __int8
0x1400172a0  mov     r8b, [r14+44h]; wchar_t *
0x1400172a4  lea     rdx, aDownloadflagsi_0; "DownloadFlagsInteractive"
0x1400172ab  mov     rcx, rbx; this
0x1400172ae  call    ?GetBooleanPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WEPEAE@Z; JsonUtil::GetBooleanPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,uchar,uchar *)
0x1400172b3  mov     edi, eax
0x1400172b5  test    eax, eax
0x1400172b7  jns     short loc_1400172C3
0x1400172b9  mov     edx, 288h
0x1400172be  jmp     loc_14001746B
0x1400172c3  mov     eax, r13d
0x1400172c6  cmp     [rbp+var_48], r13b
0x1400172ca  setnz   al
0x1400172cd  mov     [rsi], eax
0x1400172cf  lea     r9, [rbp+var_48]; unsigned __int8
0x1400172d3  mov     r8b, [r14+48h]; wchar_t *
0x1400172d7  lea     rdx, aDownloadflagsb; "DownloadFlagsBypassRegulation"
0x1400172de  mov     rcx, rbx; this
0x1400172e1  call    ?GetBooleanPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WEPEAE@Z; JsonUtil::GetBooleanPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,uchar,uchar *)
0x1400172e6  mov     edi, eax
0x1400172e8  test    eax, eax
0x1400172ea  jns     short loc_1400172F6
0x1400172ec  mov     edx, 28Fh
0x1400172f1  jmp     loc_14001746B
0x1400172f6  mov     eax, r13d
0x1400172f9  cmp     [rbp+var_48], r13b
0x1400172fd  setnz   al
0x140017300  mov     [rsi+4], eax
0x140017303  lea     r9, [rbp+var_48]; unsigned __int8
0x140017307  mov     r8b, [r14+4Ch]; wchar_t *
0x14001730b  lea     rdx, aDownloadflagss; "DownloadFlagsSerialize"
0x140017312  mov     rcx, rbx; this
0x140017315  call    ?GetBooleanPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WEPEAE@Z; JsonUtil::GetBooleanPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,uchar,uchar *)
0x14001731a  mov     edi, eax
0x14001731c  test    eax, eax
0x14001731e  jns     short loc_14001732A
0x140017320  mov     edx, 296h
0x140017325  jmp     loc_14001746B
0x14001732a  mov     eax, r13d
0x14001732d  cmp     [rbp+var_48], r13b
0x140017331  setnz   al
0x140017334  mov     [rsi+8], eax
0x140017337  lea     r9, [rbp+var_48]; unsigned __int8
0x14001733b  mov     r8b, [r14+50h]; wchar_t *
0x14001733f  lea     rdx, aDownloadflagso; "DownloadFlagsOnBattery"
0x140017346  mov     rcx, rbx; this
0x140017349  call    ?GetBooleanPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WEPEAE@Z; JsonUtil::GetBooleanPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,uchar,uchar *)
0x14001734e  mov     edi, eax
0x140017350  test    eax, eax
0x140017352  jns     short loc_14001735E
0x140017354  mov     edx, 29Dh
0x140017359  jmp     loc_14001746B
0x14001735e  mov     eax, r13d
0x140017361  cmp     [rbp+var_48], r13b
0x140017365  setnz   al
0x140017368  mov     [rsi+0Ch], eax
0x14001736b  lea     r9, [rbp+var_48]; unsigned __int8
0x14001736f  mov     r8b, [r14+54h]; wchar_t *
0x140017373  lea     rdx, aDownloadflagsf; "DownloadFlagsFailOnTransient"
0x14001737a  mov     rcx, rbx; this
0x14001737d  call    ?GetBooleanPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WEPEAE@Z; JsonUtil::GetBooleanPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,uchar,uchar *)
0x140017382  mov     edi, eax
0x140017384  test    eax, eax
0x140017386  jns     short loc_140017392
0x140017388  mov     edx, 2A4h
0x14001738d  jmp     loc_14001746B
0x140017392  mov     eax, r13d
0x140017395  cmp     [rbp+var_48], r13b
0x140017399  setnz   al
0x14001739c  mov     [rsi+10h], eax
0x14001739f  lea     r9, [rbp+var_48]; unsigned __int8
0x1400173a3  mov     r8b, [r14+58h]; wchar_t *
0x1400173a7  lea     rdx, aDownloadflagsu; "DownloadFlagsUseUpdatePriority"
0x1400173ae  mov     rcx, rbx; this
0x1400173b1  call    ?GetBooleanPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WEPEAE@Z; JsonUtil::GetBooleanPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,uchar,uchar *)
0x1400173b6  mov     edi, eax
0x1400173b8  test    eax, eax
0x1400173ba  jns     short loc_1400173C6
0x1400173bc  mov     edx, 2ABh
0x1400173c1  jmp     loc_14001746B
0x1400173c6  mov     eax, r13d
0x1400173c9  cmp     [rbp+var_48], r13b
0x1400173cd  setnz   al
0x1400173d0  mov     [rsi+14h], eax
0x1400173d3  lea     r9, [rbp+var_48]; unsigned __int8
0x1400173d7  mov     r8b, [r14+5Ch]; wchar_t *
0x1400173db  lea     rdx, aDownloadflagsi; "DownloadFlagsIgnoreNetworkCostForSize"
0x1400173e2  mov     rcx, rbx; this
0x1400173e5  call    ?GetBooleanPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WEPEAE@Z; JsonUtil::GetBooleanPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,uchar,uchar *)
0x1400173ea  mov     edi, eax
0x1400173ec  test    eax, eax
0x1400173ee  jns     short loc_1400173F7
0x1400173f0  mov     edx, 2B2h
0x1400173f5  jmp     short loc_14001746B
0x1400173f7  mov     eax, r13d
0x1400173fa  cmp     [rbp+var_48], r13b
0x1400173fe  setnz   al
0x140017401  mov     [rsi+18h], eax
0x140017404  xorps   xmm6, xmm6
0x140017407  movsd   [rbp+var_40], xmm6
0x14001740c  movd    xmm2, dword ptr [r14+60h]
0x140017412  cvtdq2pd xmm2, xmm2
0x140017416  lea     r9, [rbp+var_40]
0x14001741a  lea     rdx, aDownloadpriori; "DownloadPriority"
0x140017421  mov     rcx, rbx; this
0x140017424  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x140017429  mov     edi, eax
0x14001742b  test    eax, eax
0x14001742d  jns     short loc_140017436
0x14001742f  mov     edx, 2BAh
0x140017434  jmp     short loc_14001746B
0x140017436  cvttsd2si eax, [rbp+var_40]
0x14001743b  mov     [rsi+1Ch], eax
0x14001743e  movsd   [rbp+var_40], xmm6
0x140017443  movd    xmm2, dword ptr [r14+64h]
0x140017449  cvtdq2pd xmm2, xmm2
0x14001744d  lea     r9, [rbp+var_40]
0x140017451  lea     rdx, aCostpolicy; "CostPolicy"
0x140017458  mov     rcx, rbx; this
0x14001745b  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x140017460  mov     edi, eax
0x140017462  test    eax, eax
0x140017464  jns     short loc_140017480
0x140017466  mov     edx, 2C2h; void *
0x14001746b  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017472  mov     r9d, eax; char *
0x140017475  mov     rcx, [rbp+40h]; this
0x140017479  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001747e  jmp     short loc_1400174A2
0x140017480  cvttsd2si eax, [rbp+var_40]
0x140017485  mov     [rsi+20h], eax
0x140017488  movups  xmm0, xmmword ptr [rsi]
0x14001748b  movups  xmm1, xmmword ptr [rsi+10h]
0x14001748f  mov     ecx, eax
0x140017491  mov     rax, [r15]
0x140017494  movups  xmmword ptr [rax+44h], xmm0
0x140017498  movups  xmmword ptr [rax+54h], xmm1
0x14001749c  mov     [rax+64h], ecx
0x14001749f  mov     edi, r13d
0x1400174a2  test    rbx, rbx
0x1400174a5  jz      short loc_1400174B7
0x1400174a7  mov     rax, [rbx]
0x1400174aa  mov     rcx, rbx
0x1400174ad  mov     rax, [rax+10h]
0x1400174b1  call    _guard_dispatch_icall
0x1400174b6  nop
0x1400174b7  mov     rcx, [rbp+var_30]
0x1400174bb  test    rcx, rcx
0x1400174be  jz      short loc_1400174CD
0x1400174c0  mov     rdx, [rcx]
0x1400174c3  mov     rax, [rdx+10h]
0x1400174c7  call    _guard_dispatch_icall
0x1400174cc  nop
0x1400174cd  mov     eax, edi
0x1400174cf  jmp     short loc_1400174D3
0x1400174d1  xor     eax, eax
0x1400174d3  mov     rcx, [rbp+var_28]
0x1400174d7  xor     rcx, rsp; StackCookie
0x1400174da  call    __security_check_cookie
0x1400174df  movaps  xmm6, [rsp+78h+var_18]
0x1400174e4  add     rsp, 78h
0x1400174e8  pop     r15
0x1400174ea  pop     r14
0x1400174ec  pop     r13
0x1400174ee  pop     r12
0x1400174f0  pop     rdi
0x1400174f1  pop     rsi
0x1400174f2  pop     rbx
0x1400174f3  pop     rbp
0x1400174f4  retn
```
