# SessionDataUtil::WUOptionalSessionInfo2::Initialize(ulong,void const *,ulong,IUnknown *)

- ea: `0x1400164c8`
- end: `0x140016714`
- name: `?Initialize@WUOptionalSessionInfo2@SessionDataUtil@@AEAAJKPEBXKPEAUIUnknown@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(wchar_t *this, unsigned int, const void *, unsigned int, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x140016318`

## callees

- `0x140002ac0`
- `0x14000ce5c`
- `0x14000d4cc`
- `0x14000d538`
- `0x140013ec4`
- `0x140015c4c`
- `0x140016440`
- `0x1400164c8`
- `0x1400183a0`
- `0x14001aa60`
- `0x14001acf4`
- `0x1400206e0`

## string_xrefs

- `0x14001669b`: `MergedSandboxPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo2::Initialize(
        wchar_t *this,
        unsigned int a2,
        const void *a3,
        unsigned int a4,
        struct IUnknown *a5)
{
  void *v10; // rcx
  int v11; // eax
  signed int Instance; // edi
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  void *v15; // rcx
  void *v16; // rax
  __int64 v17; // rdx
  void *v18; // rdi
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-58h]
  int v22; // [rsp+20h] [rbp-58h]
  JsonUtil *v23; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  if ( a2 >= 2 )
  {
    v10 = *(void **)this;
    if ( v10 )
    {
      SusFree(v10);
      *(_QWORD *)this = 0;
    }
    v11 = DuplicateOptionalString<wchar_t const *,wchar_t *>(*((_QWORD *)a3 + 6), this);
    Instance = v11;
    if ( v11 < 0 )
    {
      v13 = (unsigned int)v11;
      v14 = 372;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)v13,
        v21);
      v17 = 385;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)(unsigned int)Instance,
        v22);
      return (unsigned int)Instance;
    }
    v15 = (void *)*((_QWORD *)this + 2);
    if ( v15 )
    {
      SusFree(v15);
      *((_QWORD *)this + 2) = 0;
    }
    v16 = SafeSusAllocArray(1u, 0x38u);
    *((_QWORD *)this + 2) = v16;
    Instance = v16 == 0 ? 0x8007000E : 0;
    if ( !v16 )
    {
      v13 = (unsigned int)Instance;
      v14 = 374;
      goto LABEL_12;
    }
  }
  v18 = (void *)*((_QWORD *)this + 1);
  if ( v18 )
  {
    SessionDataUtil::WUOptionalSessionInfo::~WUOptionalSessionInfo(*((SessionDataUtil::WUOptionalSessionInfo **)this + 1));
    operator delete(v18, (const struct std::nothrow_t *)0x38);
    *((_QWORD *)this + 1) = 0;
  }
  Instance = SessionDataUtil::WUOptionalSessionInfo::CreateInstance(
               a2,
               a3,
               a4,
               a5,
               (struct SessionDataUtil::WUOptionalSessionInfo **)this + 1);
  if ( Instance < 0 )
  {
    v17 = 391;
    goto LABEL_13;
  }
  Instance = SessionDataUtil::WUOptionalSessionInfo2::InitOptionalSessionInfo2(
               (SessionDataUtil::WUOptionalSessionInfo2 *)this,
               *((void **)this + 2));
  if ( Instance < 0 )
  {
    v17 = 393;
    goto LABEL_13;
  }
  if ( a2 >= 2 && a5 && a4 >= 2 )
  {
    lpVtbl = a5->lpVtbl;
    v23 = 0;
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, JsonUtil **))lpVtbl->QueryInterface)(
                 a5,
                 &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
                 &v23);
    if ( Instance >= 0 )
    {
      if ( *(_QWORD *)this )
      {
        SusFree(*(void **)this);
        *(_QWORD *)this = 0;
      }
      Instance = JsonUtil::GetStringPropertyWithDefault(
                   v23,
                   (struct ABI::Windows::Data::Json::IJsonObject *)L"MergedSandboxPath",
                   *((const wchar_t **)a3 + 6),
                   this);
      if ( Instance >= 0 )
      {
        *(_QWORD *)(*((_QWORD *)this + 2) + 48LL) = *(_QWORD *)this;
        Instance = 0;
LABEL_32:
        if ( v23 )
          (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v23 + 16LL))(v23);
        return (unsigned int)Instance;
      }
      v20 = 407;
    }
    else
    {
      v20 = 400;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)Instance,
      v22);
    goto LABEL_32;
  }
  return 0;
}

```

## disassembly

```asm
0x1400164c8  push    rbx
0x1400164ca  push    rbp
0x1400164cb  push    rsi
0x1400164cc  push    rdi
0x1400164cd  push    r12
0x1400164cf  push    r14
0x1400164d1  push    r15
0x1400164d3  sub     rsp, 40h
0x1400164d7  mov     rax, cs:__security_cookie
0x1400164de  xor     rax, rsp
0x1400164e1  mov     [rsp+78h+var_40], rax
0x1400164e6  mov     r12d, r9d
0x1400164e9  mov     r15, r8
0x1400164ec  mov     ebp, edx
0x1400164ee  mov     rbx, rcx
0x1400164f1  mov     r14, [rsp+78h+arg_20]
0x1400164f9  test    r8, r8
0x1400164fc  jnz     short loc_140016523
0x1400164fe  mov     rcx, [rsp+78h]; this
0x140016503  mov     ebx, 80070057h
0x140016508  mov     r9d, ebx; char *
0x14001650b  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140016512  mov     edx, 180h; void *
0x140016517  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001651c  mov     eax, ebx
0x14001651e  jmp     loc_1400166F8
0x140016523  cmp     ebp, 2
0x140016526  jb      loc_1400165D1
0x14001652c  mov     rcx, [rcx]; lpMem
0x14001652f  test    rcx, rcx
0x140016532  jz      short loc_140016540
0x140016534  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140016539  mov     qword ptr [rbx], 0
0x140016540  mov     rdx, rbx
0x140016543  mov     rcx, [r15+30h]
0x140016547  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x14001654c  mov     edi, eax
0x14001654e  test    eax, eax
0x140016550  jns     short loc_14001655C
0x140016552  mov     r9d, eax
0x140016555  mov     edx, 174h
0x14001655a  jmp     short loc_1400165A0
0x14001655c  mov     rcx, [rbx+10h]; lpMem
0x140016560  test    rcx, rcx
0x140016563  jz      short loc_140016572
0x140016565  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001656a  mov     qword ptr [rbx+10h], 0
0x140016572  mov     edx, 38h ; '8'; unsigned __int64
0x140016577  lea     ecx, [rdx-37h]; unsigned __int64
0x14001657a  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14001657f  mov     [rbx+10h], rax
0x140016583  mov     rcx, rax
0x140016586  neg     rcx
0x140016589  sbb     edi, edi
0x14001658b  not     edi
0x14001658d  and     edi, 8007000Eh
0x140016593  test    rax, rax
0x140016596  jnz     short loc_1400165D1
0x140016598  mov     r9d, edi; char *
0x14001659b  mov     edx, 176h; void *
0x1400165a0  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400165a7  mov     rcx, [rsp+78h]; this
0x1400165ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400165b1  mov     edx, 181h; void *
0x1400165b6  mov     rcx, [rsp+78h]; this
0x1400165bb  mov     r9d, edi; char *
0x1400165be  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400165c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400165ca  mov     eax, edi
0x1400165cc  jmp     loc_1400166F8
0x1400165d1  lea     rsi, [rbx+8]
0x1400165d5  mov     rdi, [rsi]
0x1400165d8  test    rdi, rdi
0x1400165db  jz      short loc_1400165F9
0x1400165dd  mov     rcx, rdi; this
0x1400165e0  call    ??1WUOptionalSessionInfo@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfo::~WUOptionalSessionInfo(void)
0x1400165e5  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x1400165ea  mov     rcx, rdi; void *
0x1400165ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400165f2  mov     qword ptr [rsi], 0
0x1400165f9  mov     qword ptr [rsp+78h+var_58], rsi; int
0x1400165fe  mov     r9, r14; struct IUnknown *
0x140016601  mov     r8d, r12d; unsigned int
0x140016604  mov     rdx, r15; void *
0x140016607  mov     ecx, ebp; unsigned int
0x140016609  call    ?CreateInstance@WUOptionalSessionInfo@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfo::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo * *)
0x14001660e  mov     edi, eax
0x140016610  test    eax, eax
0x140016612  jns     short loc_14001661B
0x140016614  mov     edx, 187h
0x140016619  jmp     short loc_1400165B6
0x14001661b  mov     rdx, [rbx+10h]; void *
0x14001661f  mov     rcx, rbx; this
0x140016622  call    ?InitOptionalSessionInfo2@WUOptionalSessionInfo2@SessionDataUtil@@QEAAJPEAX@Z; SessionDataUtil::WUOptionalSessionInfo2::InitOptionalSessionInfo2(void *)
0x140016627  mov     edi, eax
0x140016629  test    eax, eax
0x14001662b  jns     short loc_140016634
0x14001662d  mov     edx, 189h
0x140016632  jmp     short loc_1400165B6
0x140016634  cmp     ebp, 2
0x140016637  jb      loc_1400166F6
0x14001663d  test    r14, r14
0x140016640  jz      loc_1400166F6
0x140016646  cmp     r12d, 2
0x14001664a  jb      loc_1400166F6
0x140016650  mov     rax, [r14]
0x140016653  mov     [rsp+78h+var_48], 0
0x14001665c  lea     r8, [rsp+78h+var_48]
0x140016661  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x140016668  mov     rcx, r14
0x14001666b  mov     rax, [rax]
0x14001666e  call    _guard_dispatch_icall
0x140016673  mov     edi, eax
0x140016675  test    eax, eax
0x140016677  jns     short loc_140016680
0x140016679  mov     edx, 190h
0x14001667e  jmp     short loc_1400166B7
0x140016680  mov     rcx, [rbx]; lpMem
0x140016683  test    rcx, rcx
0x140016686  jz      short loc_140016694
0x140016688  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001668d  mov     qword ptr [rbx], 0
0x140016694  mov     r9, rbx; wchar_t *
0x140016697  mov     r8, [r15+30h]; wchar_t *
0x14001669b  lea     rdx, aMergedsandboxp; "MergedSandboxPath"
0x1400166a2  mov     rcx, [rsp+78h+var_48]; this
0x1400166a7  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x1400166ac  mov     edi, eax
0x1400166ae  test    eax, eax
0x1400166b0  jns     short loc_1400166CD
0x1400166b2  mov     edx, 197h; void *
0x1400166b7  mov     rcx, [rsp+78h]; this
0x1400166bc  mov     r9d, edi; char *
0x1400166bf  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400166c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400166cb  jmp     short loc_1400166DA
0x1400166cd  mov     rcx, [rbx+10h]
0x1400166d1  mov     rax, [rbx]
0x1400166d4  mov     [rcx+30h], rax
0x1400166d8  xor     edi, edi
0x1400166da  mov     rcx, [rsp+78h+var_48]
0x1400166df  test    rcx, rcx
0x1400166e2  jz      short loc_1400166F1
0x1400166e4  mov     rdx, [rcx]
0x1400166e7  mov     rax, [rdx+10h]
0x1400166eb  call    _guard_dispatch_icall
0x1400166f0  nop
0x1400166f1  jmp     loc_1400165CA
0x1400166f6  xor     eax, eax
0x1400166f8  mov     rcx, [rsp+78h+var_40]
0x1400166fd  xor     rcx, rsp; StackCookie
0x140016700  call    __security_check_cookie
0x140016705  add     rsp, 40h
0x140016709  pop     r15
0x14001670b  pop     r14
0x14001670d  pop     r12
0x14001670f  pop     rdi
0x140016710  pop     rsi
0x140016711  pop     rbp
0x140016712  pop     rbx
0x140016713  retn
```
