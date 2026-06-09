# CPropertyBag::~CPropertyBag(void)

- ea: `0x18008dcd8`
- end: `0x18008df24`
- name: `??1CPropertyBag@@QEAA@XZ`
- size: `588`
- prototype: `void __fastcall(CPropertyBag *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18008e250`
- `0x1800cbc4a`
- `0x1800cbe22`

## callees

- `0x180001350`
- `0x180012210`
- `0x180016540`
- `0x18001a07c`
- `0x18004d7b8`
- `0x18005a774`
- `0x180062094`
- `0x18008dba8`
- `0x18008dcd8`
- `0x180099120`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18008dd6b`
- `KERNEL32!LeaveCriticalSection` at `0x18008dd6b`
- `KERNEL32!DeleteCriticalSection` at `0x18008dde5`
- `KERNEL32!DeleteCriticalSection` at `0x18008df05`
- `KERNEL32!DeleteCriticalSection` at `0x18008dde5`
- `KERNEL32!DeleteCriticalSection` at `0x18008df05`
- `KERNEL32!CloseHandle` at `0x18008de8a`
- `KERNEL32!CloseHandle` at `0x18008de8a`
- `KERNEL32!EnterCriticalSection` at `0x18008dd51`
- `KERNEL32!EnterCriticalSection` at `0x18008dd51`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CPropertyBag::~CPropertyBag(CPropertyBag *this)
{
  __int64 *v2; // rbx
  __int64 v3; // rdi
  __int64 *i; // rax
  __int64 *v5; // rcx
  void *v6; // rcx
  CPipelineConfiguration *v7; // rbx
  char *v8; // [rsp+38h] [rbp-18h] BYREF
  char v9; // [rsp+40h] [rbp-10h]

  v8 = (char *)this + 1248;
  CSrmCriticalSection::Lock((LPCRITICAL_SECTION)((char *)this + 1248));
  v9 = 1;
  v2 = (__int64 *)**((_QWORD **)this + 64);
  while ( v2 != *((__int64 **)this + 64) )
  {
    v3 = v2[8];
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 72));
    *(_QWORD *)(v3 + 64) = 0;
    if ( v3 != -72 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 72));
    if ( !*((_BYTE *)v2 + 73) )
    {
      i = (__int64 *)v2[2];
      if ( *((_BYTE *)i + 73) )
      {
        for ( i = (__int64 *)v2[1]; !*((_BYTE *)i + 73) && v2 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v2 = i;
LABEL_14:
        v2 = i;
      }
      else
      {
        v5 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 73) )
          goto LABEL_14;
        do
        {
          v2 = v5;
          v5 = (__int64 *)*v5;
        }
        while ( !*((_BYTE *)v5 + 73) );
      }
    }
  }
  CSrmAutomaticLock::~CSrmAutomaticLock((CSrmAutomaticLock *)&v8);
  if ( *((_BYTE *)this + 1288) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1248));
    *((_BYTE *)this + 1288) = 0;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear((char *)this + 1216);
  operator delete(*((void **)this + 153));
  std::_Tree<std::_Tmap_traits<std::wstring,CPropertyBag::CManualProperty,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,CPropertyBag::CManualProperty>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CPropertyBag::CManualProperty,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,CPropertyBag::CManualProperty>>,0>>((char *)this + 1184);
  if ( *((_QWORD *)this + 146) >= 8u )
    operator delete(*((void **)this + 143));
  *((_QWORD *)this + 146) = 7;
  *((_QWORD *)this + 145) = 0;
  *((_WORD *)this + 572) = 0;
  CFsrmFileStream::~CFsrmFileStream((CPropertyBag *)((char *)this + 848));
  CFsrmFileStream::~CFsrmFileStream((CPropertyBag *)((char *)this + 552));
  *((_QWORD *)this + 67) = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v6 = (void *)*((_QWORD *)this + 68);
  if ( v6 != (void *)-1LL )
    CloseHandle(v6);
  *((_QWORD *)this + 68) = -1;
  *((_QWORD *)this + 67) = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
  *((_QWORD *)this + 68) = -1;
  std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CScanRuleCollection>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CScanRuleCollection>>>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CScanRuleCollection>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CScanRuleCollection>>>>>,0>>((__int64)this + 504);
  *((_QWORD *)this + 11) = &CPropertyBagFields::`vftable';
  CPropertyBagFieldsContextual::~CPropertyBagFieldsContextual((CPropertyBag *)((char *)this + 88));
  v7 = (CPipelineConfiguration *)*((_QWORD *)this + 10);
  if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
  {
    CPipelineConfiguration::~CPipelineConfiguration(v7);
    operator delete(v7);
  }
  if ( *((_BYTE *)this + 72) )
  {
    *((_BYTE *)this + 72) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  }
}

```

## disassembly

```asm
0x18008dcd8  mov     [rsp-38h+arg_18], rbx
0x18008dcdd  mov     [rsp-38h+arg_0], rcx
0x18008dce2  push    rbp
0x18008dce3  push    rsi
0x18008dce4  push    rdi
0x18008dce5  push    r12
0x18008dce7  push    r13
0x18008dce9  push    r14
0x18008dceb  push    r15
0x18008dced  mov     rbp, rsp
0x18008dcf0  sub     rsp, 50h
0x18008dcf4  mov     rsi, rcx
0x18008dcf7  lea     r15, [rcx+4E0h]
0x18008dcfe  mov     [rbp+var_18], r15
0x18008dd02  xor     r12d, r12d
0x18008dd05  mov     [rbp+var_10], r12b
0x18008dd09  mov     rcx, r15; lpCriticalSection
0x18008dd0c  call    ?Lock@CSrmCriticalSection@@QEAAXXZ; CSrmCriticalSection::Lock(void)
0x18008dd11  mov     [rbp+var_10], 1
0x18008dd15  mov     rbx, [rsi+200h]
0x18008dd1c  mov     rbx, [rbx]
0x18008dd1f  lea     r13, ??_7?$CSrmAutoCppArray_Storage@E@@6B@; const CSrmAutoCppArray_Storage<uchar>::`vftable'
0x18008dd26  lea     r15, ??_7?$CSrmAuto@VCSrmSafeCriticalSection@@V?$CSrmAutoGenericObj_Storage@VCSrmSafeCriticalSection@@P6AAEAV1@AEAV1@@Z$1?CriticalUnlock@@YAAEAV1@0@ZP6AAEAV1@0@Z$1?CriticalLock@@YAAEAV1@0@Z@@@@6B@; const CSrmAuto<CSrmSafeCriticalSection,CSrmAutoGenericObj_Storage<CSrmSafeCriticalSection,CSrmSafeCriticalSection & (*)(CSrmSafeCriticalSection &),&CriticalUnlock(CSrmSafeCriticalSection &),CSrmSafeCriticalSection & (*)(CSrmSafeCriticalSection &),&CriticalLock(CSrmSafeCriticalSection &)>>::`vftable'
0x18008dd2d  cmp     rbx, [rsi+200h]
0x18008dd34  jz      loc_18008DDC4
0x18008dd3a  mov     rdi, [rbx+40h]
0x18008dd3e  lea     r14, [rdi+48h]
0x18008dd42  mov     [rbp+var_28], r13
0x18008dd46  mov     [rbp+var_20], r12
0x18008dd4a  mov     [rbp+var_28], r15
0x18008dd4e  mov     rcx, r14; lpCriticalSection
0x18008dd51  call    cs:__imp_EnterCriticalSection
0x18008dd57  mov     [rbp+var_20], r14
0x18008dd5b  mov     [rdi+40h], r12
0x18008dd5f  mov     [rbp+var_28], r15
0x18008dd63  test    r14, r14
0x18008dd66  jz      short loc_18008DD71
0x18008dd68  mov     rcx, r14; lpCriticalSection
0x18008dd6b  call    cs:__imp_LeaveCriticalSection
0x18008dd71  mov     [rbp+var_20], r12
0x18008dd75  mov     [rbp+var_28], r13
0x18008dd79  cmp     [rbx+49h], r12b
0x18008dd7d  jnz     short loc_18008DD2D
0x18008dd7f  mov     rax, [rbx+10h]
0x18008dd83  cmp     [rax+49h], r12b
0x18008dd87  jnz     short loc_18008DDA3
0x18008dd89  mov     rcx, [rax]
0x18008dd8c  cmp     [rcx+49h], r12b
0x18008dd90  jnz     short loc_18008DDBC
0x18008dd92  mov     rbx, rcx
0x18008dd95  mov     rax, [rcx]
0x18008dd98  mov     rcx, rax
0x18008dd9b  cmp     [rax+49h], r12b
0x18008dd9f  jz      short loc_18008DD92
0x18008dda1  jmp     short loc_18008DD2D
0x18008dda3  mov     rax, [rbx+8]
0x18008dda7  jmp     short loc_18008DDB6
0x18008dda9  cmp     rbx, [rax+10h]
0x18008ddad  jnz     short loc_18008DDBC
0x18008ddaf  mov     rbx, rax
0x18008ddb2  mov     rax, [rax+8]
0x18008ddb6  cmp     [rax+49h], r12b
0x18008ddba  jz      short loc_18008DDA9
0x18008ddbc  mov     rbx, rax
0x18008ddbf  jmp     loc_18008DD2D
0x18008ddc4  lea     rcx, [rbp+var_18]; this
0x18008ddc8  call    ??1CSrmAutomaticLock@@QEAA@XZ; CSrmAutomaticLock::~CSrmAutomaticLock(void)
0x18008ddcd  nop
0x18008ddce  lea     r15, [rsi+4E0h]
0x18008ddd5  cmp     [r15+28h], r12b
0x18008ddd9  lea     r13, [rsi+1F8h]
0x18008dde0  jz      short loc_18008DDEF
0x18008dde2  mov     rcx, r15; lpCriticalSection
0x18008dde5  call    cs:__imp_DeleteCriticalSection
0x18008ddeb  mov     [r15+28h], r12b
0x18008ddef  lea     rbx, [rsi+4C0h]
0x18008ddf6  mov     [rbp+var_30], rbx
0x18008ddfa  mov     rcx, rbx
0x18008ddfd  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x18008de02  nop
0x18008de03  mov     rcx, [rbx+8]; Block
0x18008de07  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008de0c  nop
0x18008de0d  lea     rcx, [rsi+4A0h]
0x18008de14  mov     [rbp+arg_8], rcx
0x18008de18  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCManualProperty@CPropertyBag@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCManualProperty@CPropertyBag@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,CPropertyBag::CManualProperty,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,CPropertyBag::CManualProperty>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CPropertyBag::CManualProperty,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,CPropertyBag::CManualProperty>>,0>>(void)
0x18008de1d  nop
0x18008de1e  cmp     qword ptr [rsi+490h], 8
0x18008de26  jb      short loc_18008DE34
0x18008de28  mov     rcx, [rsi+478h]; Block
0x18008de2f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008de34  mov     qword ptr [rsi+490h], 7
0x18008de3f  mov     [rsi+488h], r12
0x18008de46  mov     [rsi+478h], r12w
0x18008de4e  lea     rcx, [rsi+350h]; this
0x18008de55  call    ??1CFsrmFileStream@@QEAA@XZ; CFsrmFileStream::~CFsrmFileStream(void)
0x18008de5a  nop
0x18008de5b  lea     rcx, [rsi+228h]; this
0x18008de62  call    ??1CFsrmFileStream@@QEAA@XZ; CFsrmFileStream::~CFsrmFileStream(void)
0x18008de67  nop
0x18008de68  lea     rbx, [rsi+218h]
0x18008de6f  mov     [rbp+arg_8], rbx
0x18008de73  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18008de7a  mov     [rbx], rax
0x18008de7d  mov     rcx, [rbx+8]; hObject
0x18008de81  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008de85  cmp     rcx, rdi
0x18008de88  jz      short loc_18008DE90
0x18008de8a  call    cs:__imp_CloseHandle
0x18008de90  mov     [rbx+8], rdi
0x18008de94  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18008de9b  mov     [rbx], rax
0x18008de9e  mov     [rbx+8], rdi
0x18008dea2  mov     [rbp+arg_8], r13
0x18008dea6  mov     rcx, r13
0x18008dea9  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@V?$CComObject@VCScanRuleCollection@@@ATL@@@ATL@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@V?$CComObject@VCScanRuleCollection@@@ATL@@@ATL@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CScanRuleCollection>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CScanRuleCollection>>>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CScanRuleCollection>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CScanRuleCollection>>>>>,0>>(void)
0x18008deae  nop
0x18008deaf  lea     rcx, [rsi+58h]; this
0x18008deb3  mov     [rbp+arg_10], rcx
0x18008deb7  lea     rax, ??_7CPropertyBagFields@@6B@; const CPropertyBagFields::`vftable'
0x18008debe  mov     [rcx], rax
0x18008dec1  call    ??1CPropertyBagFieldsContextual@@MEAA@XZ; CPropertyBagFieldsContextual::~CPropertyBagFieldsContextual(void)
0x18008dec6  nop
0x18008dec7  mov     rbx, [rsi+50h]
0x18008decb  test    rbx, rbx
0x18008dece  jz      short loc_18008DEEB
0x18008ded0  mov     eax, edi
0x18008ded2  lock xadd [rbx], eax
0x18008ded6  add     eax, edi
0x18008ded8  jnz     short loc_18008DEEB
0x18008deda  mov     rcx, rbx; this
0x18008dedd  call    ??1CPipelineConfiguration@@QEAA@XZ; CPipelineConfiguration::~CPipelineConfiguration(void)
0x18008dee2  mov     rcx, rbx; Block
0x18008dee5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008deea  nop
0x18008deeb  lea     rax, [rsi+18h]
0x18008deef  mov     [rbp+arg_8], rax
0x18008def3  lea     rcx, [rax+8]; lpCriticalSection
0x18008def7  mov     [rbp+arg_10], rcx
0x18008defb  cmp     [rcx+28h], r12b
0x18008deff  jz      short loc_18008DF0C
0x18008df01  mov     [rcx+28h], r12b
0x18008df05  call    cs:__imp_DeleteCriticalSection
0x18008df0b  nop
0x18008df0c  mov     rbx, [rsp+50h+arg_18]
0x18008df14  add     rsp, 50h
0x18008df18  pop     r15
0x18008df1a  pop     r14
0x18008df1c  pop     r13
0x18008df1e  pop     r12
0x18008df20  pop     rdi
0x18008df21  pop     rsi
0x18008df22  pop     rbp
0x18008df23  retn
```
