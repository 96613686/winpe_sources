# CDynPropsSink::Indicate(long,IWbemClassObject * *)

- ea: `0x18004e910`
- end: `0x18004ee20`
- name: `?Indicate@CDynPropsSink@@UEAAJJPEAPEAUIWbemClassObject@@@Z`
- size: `1296`
- prototype: `__int64 __fastcall(CDynPropsSink *__hidden this, int, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000aa90`
- `0x18000b140`
- `0x18003cfe0`
- `0x18004e910`
- `0x180057e78`
- `0x180087094`
- `0x180089ccc`
- `0x18008da00`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18004ec6e`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18004ec6e`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18004e984`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18004e984`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004eae8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004eb9a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004ebce`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004eda1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004edf2`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004eae8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004eb9a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004ebce`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004eda1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004edf2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004e962`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004e962`
- `wbemcomn!GetMemLogObject` at `0x18004eb55`
- `wbemcomn!GetMemLogObject` at `0x18004ec0f`
- `wbemcomn!GetMemLogObject` at `0x18004eca7`
- `wbemcomn!GetMemLogObject` at `0x18004ed49`
- `wbemcomn!GetMemLogObject` at `0x18004ee09`
- `wbemcomn!GetMemLogObject` at `0x18004eb55`
- `wbemcomn!GetMemLogObject` at `0x18004ec0f`
- `wbemcomn!GetMemLogObject` at `0x18004eca7`
- `wbemcomn!GetMemLogObject` at `0x18004ed49`
- `wbemcomn!GetMemLogObject` at `0x18004ee09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004eb61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ec1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ecb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ed55`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ee14`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004eb61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ec1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ecb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ed55`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ee14`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18004ea28`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18004ea28`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDynPropsSink::Indicate(CDynPropsSink *this, int a2, struct IWbemClassObject **a3)
{
  unsigned __int64 v4; // r15
  void *v5; // rax
  unsigned int v6; // r14d
  unsigned int v7; // esi
  __int64 v8; // rbx
  struct IWbemClassObject *v9; // r12
  void *v10; // rdi
  void *v11; // rbx
  int v12; // eax
  int v13; // r14d
  int v14; // edi
  CMemoryLog *v16; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v18; // rax
  int v19; // r15d
  CMemoryLog *v20; // rax
  int v21; // esi
  CMemoryLog *v22; // rax
  void *v23; // [rsp+30h] [rbp-30h] BYREF
  void *ppInterface; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v25[32]; // [rsp+40h] [rbp-20h] BYREF
  int v27; // [rsp+A8h] [rbp+48h]
  void *v28; // [rsp+B8h] [rbp+58h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids, this, a2);
  }
  v5 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v4, 8u));
  std::unique_ptr<IWbemClassObject * [0]>::unique_ptr<IWbemClassObject * [0]>(&v23, (__int64)v5);
  if ( !v23 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids, 2147749894LL);
    }
    std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(&v23);
    return 2147749894LL;
  }
  CVar::CVar((CVar *)v25);
  v6 = 0;
  v27 = 0;
  v7 = 0;
  v8 = 0;
  if ( (int)v4 <= 0 )
  {
LABEL_45:
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids, v6);
    }
    goto LABEL_29;
  }
  do
  {
    v9 = a3[v8];
    if ( ((unsigned int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _BYTE *, _QWORD, _QWORD))v9->lpVtbl[4].SpawnDerivedClass)(
           v9,
           L"DYNPROPS",
           v25,
           0,
           0)
      || CVar::GetBool((CVar *)v25) != -1 )
    {
      *(_QWORD *)std::unique_ptr<IWbemClassObject * [0]>::operator[](&v23, (int)v7++) = a3[v8];
    }
    else if ( (int)CPointerArray<IWbemClassObject,CReferenceManager<IWbemClassObject>,CFlexArray>::Add(
                     (char *)this + 48,
                     v9) < 0 )
    {
      v27 = -2147217402;
    }
    v8 = (unsigned int)(v8 + 1);
  }
  while ( (int)v8 < (int)v4 );
  v10 = v23;
  if ( !v7 )
  {
    v6 = v27;
    if ( v27 < 0 )
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, v27);
    }
    goto LABEL_45;
  }
  ppInterface = 0;
  v6 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  v11 = ppInterface;
  v28 = ppInterface;
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147417833 )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, v6);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids, v6);
    }
    if ( v11 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    v28 = 0;
LABEL_29:
    CVar::~CVar((CVar *)v25);
    std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(&v23);
    return v6;
  }
  if ( ppInterface )
  {
    v12 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface);
    v13 = v12;
    if ( ppInterface )
    {
      if ( v12 )
      {
        v19 = (*(__int64 (**)(void))(*(_QWORD *)ppInterface + 40LL))();
        if ( v19 < 0 )
        {
          v20 = GetMemLogObject();
          CMemoryLog::Write(v20, v19);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              66,
              WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids,
              (unsigned int)v19);
          }
          CReleaseMe::release((CReleaseMe *)&v28);
          CVar::~CVar((CVar *)v25);
          std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(&v23);
          return (unsigned int)v19;
        }
      }
    }
  }
  else
  {
    v13 = 0;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)this + 3) + 24LL))(
          *((_QWORD *)this + 3),
          v7,
          v10);
  if ( v13
    && ppInterface
    && (v21 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface), v21 < 0) )
  {
    CReleaseMe::release((CReleaseMe *)&v28);
    CVar::~CVar((CVar *)v25);
    std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(&v23);
    return (unsigned int)v21;
  }
  else if ( v14 == -2147217358 )
  {
    if ( v11 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    v28 = 0;
    CVar::~CVar((CVar *)v25);
    std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(&v23);
    return 2147749938LL;
  }
  else
  {
    if ( v14 < 0 )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, v14);
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids,
        (unsigned int)v14);
    }
    if ( v11 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    v28 = 0;
    CVar::~CVar((CVar *)v25);
    std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(&v23);
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x18004e910  mov     [rsp-38h+arg_10], rbx
0x18004e915  mov     [rsp-38h+arg_0], rcx
0x18004e91a  push    rbp
0x18004e91b  push    rsi
0x18004e91c  push    rdi
0x18004e91d  push    r12
0x18004e91f  push    r13
0x18004e921  push    r14
0x18004e923  push    r15
0x18004e925  mov     rbp, rsp
0x18004e928  sub     rsp, 60h
0x18004e92c  mov     r13, r8
0x18004e92f  movsxd  r15, edx
0x18004e932  mov     rax, rcx
0x18004e935  lea     rbx, WPP_GLOBAL_Control
0x18004e93c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e943  cmp     rcx, rbx
0x18004e946  jnz     loc_18004EB12
0x18004e94c  mov     eax, 8
0x18004e951  mul     r15
0x18004e954  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004e95b  cmovb   rax, rcx
0x18004e95f  mov     rcx, rax
0x18004e962  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004e968  mov     rdx, rax
0x18004e96b  lea     rcx, [rbp+var_30]
0x18004e96f  call    ??0?$unique_ptr@$$BY0A@PEAUIWbemClassObject@@U?$default_delete@$$BY0A@PEAUIWbemClassObject@@@std@@@std@@QEAA@PEAPEAUIWbemClassObject@@@Z; std::unique_ptr<IWbemClassObject * [0]>::unique_ptr<IWbemClassObject * [0]>(IWbemClassObject * *)
0x18004e974  nop
0x18004e975  cmp     [rbp+var_30], 0
0x18004e97a  jz      loc_18004EC0F
0x18004e980  lea     rcx, [rbp+var_20]
0x18004e984  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18004e98a  nop
0x18004e98b  xor     r14d, r14d
0x18004e98e  mov     [rbp+arg_8], r14d
0x18004e992  xor     esi, esi
0x18004e994  xor     ebx, ebx
0x18004e996  test    r15d, r15d
0x18004e999  jle     loc_18004ECB9
0x18004e99f  mov     rdi, [rbp+arg_0]
0x18004e9a3  nop     dword ptr [rax+00h]
0x18004e9a7  nop     word ptr [rax+rax+00000000h]
0x18004e9b0  lea     r14, ds:0[rbx*8]
0x18004e9b8  mov     r12, [r14+r13]
0x18004e9bc  mov     rax, [r12]
0x18004e9c0  mov     [rsp+60h+var_40], 0
0x18004e9c9  xor     r9d, r9d
0x18004e9cc  lea     r8, [rbp+var_20]
0x18004e9d0  lea     rdx, aDynprops; "DYNPROPS"
0x18004e9d7  mov     rcx, r12
0x18004e9da  mov     rax, [rax+3D0h]
0x18004e9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9e6  test    eax, eax
0x18004e9e8  jz      loc_18004EC6A
0x18004e9ee  movsxd  rdx, esi
0x18004e9f1  lea     rcx, [rbp+var_30]
0x18004e9f5  call    ??A?$unique_ptr@$$BY0A@PEAUIWbemClassObject@@U?$default_delete@$$BY0A@PEAUIWbemClassObject@@@std@@@std@@QEBAAEAPEAUIWbemClassObject@@_K@Z; std::unique_ptr<IWbemClassObject * [0]>::operator[](unsigned __int64)
0x18004e9fa  mov     rcx, [r14+r13]
0x18004e9fe  mov     [rax], rcx
0x18004ea01  inc     esi
0x18004ea03  inc     ebx
0x18004ea05  cmp     ebx, r15d
0x18004ea08  jl      short loc_18004E9B0
0x18004ea0a  test    esi, esi
0x18004ea0c  mov     rdi, [rbp+var_30]
0x18004ea10  jz      loc_18004EC9E
0x18004ea16  xor     r12d, r12d
0x18004ea19  mov     [rbp+ppInterface], r12
0x18004ea1d  lea     rdx, [rbp+ppInterface]; ppInterface
0x18004ea21  lea     rcx, IID_IServerSecurity; riid
0x18004ea28  call    cs:__imp_CoGetCallContext
0x18004ea2e  mov     r14d, eax
0x18004ea31  mov     rbx, [rbp+ppInterface]
0x18004ea35  mov     [rbp+arg_18], rbx
0x18004ea39  mov     eax, 80000000h
0x18004ea3e  lea     ecx, [r14+rax]
0x18004ea42  test    eax, ecx
0x18004ea44  jz      loc_18004EB48
0x18004ea4a  mov     rcx, [rbp+ppInterface]
0x18004ea4e  test    rcx, rcx
0x18004ea51  jz      loc_18004EDB9
0x18004ea57  mov     rax, [rcx]
0x18004ea5a  mov     rax, [rax+30h]
0x18004ea5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea63  mov     r14d, eax
0x18004ea66  mov     rcx, [rbp+ppInterface]
0x18004ea6a  test    rcx, rcx
0x18004ea6d  jz      short loc_18004EA77
0x18004ea6f  test    eax, eax
0x18004ea71  jnz     loc_18004ED32
0x18004ea77  mov     rax, [rbp+arg_0]
0x18004ea7b  mov     rcx, [rax+18h]
0x18004ea7f  mov     rax, [rcx]
0x18004ea82  mov     r8, rdi
0x18004ea85  mov     edx, esi
0x18004ea87  mov     rax, [rax+18h]
0x18004ea8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea90  mov     edi, eax
0x18004ea92  test    r14d, r14d
0x18004ea95  jnz     loc_18004EDC1
0x18004ea9b  cmp     edi, 80041032h
0x18004eaa1  jz      loc_18004EBB2
0x18004eaa7  test    edi, edi
0x18004eaa9  js      loc_18004EE09
0x18004eaaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eab6  lea     rax, WPP_GLOBAL_Control
0x18004eabd  cmp     rcx, rax
0x18004eac0  jz      short loc_18004EACC
0x18004eac2  test    byte ptr [rcx+1Ch], 1
0x18004eac6  jnz     loc_18004EBE8
0x18004eacc  test    rbx, rbx
0x18004eacf  jz      short loc_18004EAE0
0x18004ead1  mov     rax, [rbx]
0x18004ead4  mov     rcx, rbx
0x18004ead7  mov     rax, [rax+10h]
0x18004eadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eae0  mov     [rbp+arg_18], r12
0x18004eae4  lea     rcx, [rbp+var_20]
0x18004eae8  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18004eaee  nop
0x18004eaef  lea     rcx, [rbp+var_30]
0x18004eaf3  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18004eaf8  mov     eax, edi
0x18004eafa  mov     rbx, [rsp+60h+arg_10]
0x18004eb02  add     rsp, 60h
0x18004eb06  pop     r15
0x18004eb08  pop     r14
0x18004eb0a  pop     r13
0x18004eb0c  pop     r12
0x18004eb0e  pop     rdi
0x18004eb0f  pop     rsi
0x18004eb10  pop     rbp
0x18004eb11  retn
0x18004eb12  test    byte ptr [rcx+1Ch], 1
0x18004eb16  jz      loc_18004E94C
0x18004eb1c  cmp     byte ptr [rcx+19h], 5
0x18004eb20  jb      loc_18004E94C
0x18004eb26  mov     edx, 3Eh ; '>'
0x18004eb2b  mov     dword ptr [rsp+60h+var_40], r15d
0x18004eb30  mov     r9, rax
0x18004eb33  lea     r8, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids
0x18004eb3a  mov     rcx, [rcx+10h]
0x18004eb3e  call    WPP_SF_qd
0x18004eb43  jmp     loc_18004E94C
0x18004eb48  cmp     r14d, 80010117h
0x18004eb4f  jz      loc_18004EA4A
0x18004eb55  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004eb5b  mov     edx, r14d
0x18004eb5e  mov     rcx, rax
0x18004eb61  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004eb67  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eb6e  lea     rax, WPP_GLOBAL_Control
0x18004eb75  cmp     rcx, rax
0x18004eb78  jnz     loc_18004ED01
0x18004eb7e  test    rbx, rbx
0x18004eb81  jz      short loc_18004EB92
0x18004eb83  mov     rax, [rbx]
0x18004eb86  mov     rcx, rbx
0x18004eb89  mov     rax, [rax+10h]
0x18004eb8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb92  mov     [rbp+arg_18], r12
0x18004eb96  lea     rcx, [rbp+var_20]
0x18004eb9a  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18004eba0  nop
0x18004eba1  lea     rcx, [rbp+var_30]
0x18004eba5  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18004ebaa  mov     eax, r14d
0x18004ebad  jmp     loc_18004EAFA
0x18004ebb2  test    rbx, rbx
0x18004ebb5  jz      short loc_18004EBC6
0x18004ebb7  mov     rcx, [rbx]
0x18004ebba  mov     rax, [rcx+10h]
0x18004ebbe  mov     rcx, rbx
0x18004ebc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ebc6  mov     [rbp+arg_18], r12
0x18004ebca  lea     rcx, [rbp+var_20]
0x18004ebce  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18004ebd4  nop
0x18004ebd5  lea     rcx, [rbp+var_30]
0x18004ebd9  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18004ebde  mov     eax, 80041032h
0x18004ebe3  jmp     loc_18004EAFA
0x18004ebe8  cmp     byte ptr [rcx+19h], 2
0x18004ebec  jb      loc_18004EACC
0x18004ebf2  mov     edx, 43h ; 'C'
0x18004ebf7  mov     r9d, edi
0x18004ebfa  lea     r8, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids
0x18004ec01  mov     rcx, [rcx+10h]
0x18004ec05  call    WPP_SF_d
0x18004ec0a  jmp     loc_18004EACC
0x18004ec0f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004ec15  mov     edx, 80041006h
0x18004ec1a  mov     rcx, rax
0x18004ec1d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004ec23  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ec2a  cmp     rcx, rbx
0x18004ec2d  jz      short loc_18004EC57
0x18004ec2f  test    byte ptr [rcx+1Ch], 1
0x18004ec33  jz      short loc_18004EC57
0x18004ec35  cmp     byte ptr [rcx+19h], 2
0x18004ec39  jb      short loc_18004EC57
0x18004ec3b  mov     edx, 3Fh ; '?'
0x18004ec40  mov     r9d, 80041006h
0x18004ec46  lea     r8, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids
0x18004ec4d  mov     rcx, [rcx+10h]
0x18004ec51  call    WPP_SF_d
0x18004ec56  nop
0x18004ec57  lea     rcx, [rbp+var_30]
0x18004ec5b  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18004ec60  mov     eax, 80041006h
0x18004ec65  jmp     loc_18004EAFA
0x18004ec6a  lea     rcx, [rbp+var_20]
0x18004ec6e  call    cs:__imp_?GetBool@CVar@@QEAAFXZ; CVar::GetBool(void)
0x18004ec74  cmp     ax, 0FFFFh
0x18004ec78  jnz     loc_18004E9EE
0x18004ec7e  lea     rcx, [rdi+30h]
0x18004ec82  mov     rdx, r12
0x18004ec85  call    ?Add@?$CPointerArray@UIWbemClassObject@@V?$CReferenceManager@UIWbemClassObject@@@@VCFlexArray@@@@QEAAHPEAUIWbemClassObject@@@Z; CPointerArray<IWbemClassObject,CReferenceManager<IWbemClassObject>,CFlexArray>::Add(IWbemClassObject *)
0x18004ec8a  test    eax, eax
0x18004ec8c  jns     loc_18004EA03
0x18004ec92  mov     [rbp+arg_8], 80041006h
0x18004ec99  jmp     loc_18004EA03
0x18004ec9e  mov     r14d, [rbp+arg_8]
0x18004eca2  test    r14d, r14d
0x18004eca5  jns     short loc_18004ECB9
0x18004eca7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004ecad  mov     edx, r14d
0x18004ecb0  mov     rcx, rax
0x18004ecb3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004ecb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ecc0  lea     rax, WPP_GLOBAL_Control
0x18004ecc7  cmp     rcx, rax
0x18004ecca  jz      loc_18004EB96
0x18004ecd0  test    byte ptr [rcx+1Ch], 1
0x18004ecd4  jz      loc_18004EB96
0x18004ecda  cmp     byte ptr [rcx+19h], 2
0x18004ecde  jb      loc_18004EB96
0x18004ece4  mov     edx, 40h ; '@'
0x18004ece9  mov     r9d, r14d
0x18004ecec  lea     r8, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids
0x18004ecf3  mov     rcx, [rcx+10h]
0x18004ecf7  call    WPP_SF_d
0x18004ecfc  jmp     loc_18004EB96
0x18004ed01  test    byte ptr [rcx+1Ch], 1
0x18004ed05  jz      loc_18004EB7E
0x18004ed0b  cmp     byte ptr [rcx+19h], 2
0x18004ed0f  jb      loc_18004EB7E
0x18004ed15  mov     edx, 41h ; 'A'
0x18004ed1a  mov     r9d, r14d
0x18004ed1d  lea     r8, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids
0x18004ed24  mov     rcx, [rcx+10h]
0x18004ed28  call    WPP_SF_d
0x18004ed2d  jmp     loc_18004EB7E
0x18004ed32  mov     rdx, [rcx]
0x18004ed35  mov     rax, [rdx+28h]
0x18004ed39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed3e  mov     r15d, eax
0x18004ed41  test    eax, eax
0x18004ed43  jns     loc_18004EA77
0x18004ed49  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004ed4f  mov     edx, r15d
0x18004ed52  mov     rcx, rax
0x18004ed55  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004ed5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ed62  lea     rax, WPP_GLOBAL_Control
0x18004ed69  cmp     rcx, rax
0x18004ed6c  jz      short loc_18004ED93
0x18004ed6e  test    byte ptr [rcx+1Ch], 1
0x18004ed72  jz      short loc_18004ED93
0x18004ed74  cmp     byte ptr [rcx+19h], 2
0x18004ed78  jb      short loc_18004ED93
0x18004ed7a  mov     edx, 42h ; 'B'
0x18004ed7f  mov     r9d, r15d
0x18004ed82  lea     r8, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids
0x18004ed89  mov     rcx, [rcx+10h]
0x18004ed8d  call    WPP_SF_d
0x18004ed92  nop
0x18004ed93  lea     rcx, [rbp+arg_18]; this
0x18004ed97  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18004ed9c  nop
0x18004ed9d  lea     rcx, [rbp+var_20]
0x18004eda1  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18004eda7  nop
0x18004eda8  lea     rcx, [rbp+var_30]
0x18004edac  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18004edb1  mov     eax, r15d
0x18004edb4  jmp     loc_18004EAFA
0x18004edb9  mov     r14d, r12d
0x18004edbc  jmp     loc_18004EA77
0x18004edc1  mov     rcx, [rbp+ppInterface]
0x18004edc5  test    rcx, rcx
0x18004edc8  jz      loc_18004EA9B
0x18004edce  mov     rdx, [rcx]
0x18004edd1  mov     rax, [rdx+20h]
0x18004edd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edda  mov     esi, eax
0x18004eddc  test    eax, eax
0x18004edde  jns     loc_18004EA9B
0x18004ede4  lea     rcx, [rbp+arg_18]; this
0x18004ede8  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
  ... truncated ...
```
