# GetStandardInstances(CFlexArray *,ulong)

- ea: `0x18007bbec`
- end: `0x18007befe`
- name: `?GetStandardInstances@@YAJPEAVCFlexArray@@K@Z`
- size: `786`
- prototype: `__int64 __fastcall(struct CFlexArray *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180093610`

## callees

- `0x18000b140`
- `0x18006a8f4`
- `0x180075eb4`
- `0x18007bbec`
- `0x18008201c`
- `0x180085c70`
- `0x180093b70`
- `0x180093be8`
- `0x1800bad28`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18007bc03`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18007bc9a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18007bd6f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18007be06`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18007bc03`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18007bc9a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18007bd6f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18007be06`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18007bd18`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18007be79`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18007bd18`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18007be79`
- `wbemcomn!GetMemLogObject` at `0x18007bc27`
- `wbemcomn!GetMemLogObject` at `0x18007bcbe`
- `wbemcomn!GetMemLogObject` at `0x18007bd22`
- `wbemcomn!GetMemLogObject` at `0x18007bd93`
- `wbemcomn!GetMemLogObject` at `0x18007be2a`
- `wbemcomn!GetMemLogObject` at `0x18007be83`
- `wbemcomn!GetMemLogObject` at `0x18007bc27`
- `wbemcomn!GetMemLogObject` at `0x18007bcbe`
- `wbemcomn!GetMemLogObject` at `0x18007bd22`
- `wbemcomn!GetMemLogObject` at `0x18007bd93`
- `wbemcomn!GetMemLogObject` at `0x18007be2a`
- `wbemcomn!GetMemLogObject` at `0x18007be83`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007bc37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007bcce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007bd32`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007bda3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007be3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007be93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007bc37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007bcce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007bd32`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007bda3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007be3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007be93`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetStandardInstances(struct CFlexArray *a1)
{
  CProviderClass *v2; // rax
  CProviderClass *FiringClass; // rbx
  CMemoryLog *v4; // rax
  unsigned int v5; // ebx
  CProviderClass *v6; // rax
  CSystemConfigInstance *v7; // rdi
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v9; // rcx
  __int64 v10; // rdx
  CMemoryLog *v11; // rax
  CProviderClass *v12; // rax
  CProviderClass *v13; // rbx
  CMemoryLog *v14; // rax
  CThisNamespaceInstance *v15; // rax
  CThisNamespaceInstance *v16; // rdi
  CMemoryLog *v17; // rax
  CClientCnt *v18; // rcx
  __int64 v19; // rdx
  CMemoryLog *v20; // rax
  CProviderClass *v22; // [rsp+50h] [rbp+18h] BYREF
  CProviderClass *v23; // [rsp+58h] [rbp+20h] BYREF

  v2 = (CProviderClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
  v22 = v2;
  if ( v2 )
    FiringClass = CTimerNextFiringClass::CTimerNextFiringClass(v2);
  else
    FiringClass = 0;
  if ( FiringClass )
  {
    v22 = FiringClass;
    CSystemConfigClass::Init(FiringClass);
    v6 = (CProviderClass *)CWin32DefaultArena::WbemMemAlloc(0x2A0u);
    v23 = v6;
    if ( v6 )
      v7 = CThisNamespaceInstance::CThisNamespaceInstance(v6);
    else
      v7 = 0;
    if ( !v7 )
    {
      MemLogObject = GetMemLogObject();
      v5 = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v10 = 104;
      goto LABEL_30;
    }
    CSystemConfigInstance::Init(v7, FiringClass);
    if ( CFlexArray::Add(a1, v7) )
    {
      v11 = GetMemLogObject();
      v5 = -2147217402;
      CMemoryLog::Write(v11, -2147217402);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v10 = 105;
      goto LABEL_30;
    }
    v12 = (CProviderClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
    v23 = v12;
    if ( v12 )
      v13 = CTimerNextFiringClass::CTimerNextFiringClass(v12);
    else
      v13 = 0;
    if ( !v13 )
    {
      v14 = GetMemLogObject();
      v5 = -2147217402;
      CMemoryLog::Write(v14, -2147217402);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v10 = 106;
LABEL_30:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_613266cfc38534b959e7b6275148614d_Traceguids, 2147749894LL);
LABEL_47:
      CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(&v22);
      return v5;
    }
    v23 = v13;
    CThisNamespaceClass::Init(v13);
    v15 = (CThisNamespaceInstance *)CWin32DefaultArena::WbemMemAlloc(0x2A0u);
    if ( v15 )
      v16 = CThisNamespaceInstance::CThisNamespaceInstance(v15);
    else
      v16 = 0;
    if ( v16 )
    {
      CThisNamespaceInstance::Init(v16, v13);
      if ( !CFlexArray::Add(a1, v16) )
      {
        v5 = 0;
        goto LABEL_46;
      }
      v20 = GetMemLogObject();
      v5 = -2147217402;
      CMemoryLog::Write(v20, -2147217402);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v19 = 108;
    }
    else
    {
      v17 = GetMemLogObject();
      v5 = -2147217402;
      CMemoryLog::Write(v17, -2147217402);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v19 = 107;
    }
    WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_613266cfc38534b959e7b6275148614d_Traceguids, 2147749894LL);
LABEL_46:
    CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(&v23);
    goto LABEL_47;
  }
  v4 = GetMemLogObject();
  v5 = -2147217402;
  CMemoryLog::Write(v4, -2147217402);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_613266cfc38534b959e7b6275148614d_Traceguids, 2147749894LL);
  }
  return v5;
}

```

## disassembly

```asm
0x18007bbec  mov     [rsp+arg_0], rbx
0x18007bbf1  mov     [rsp+arg_8], rsi
0x18007bbf6  push    rdi
0x18007bbf7  sub     rsp, 30h
0x18007bbfb  mov     rsi, rcx
0x18007bbfe  mov     ecx, 360h
0x18007bc03  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18007bc09  mov     [rsp+38h+arg_10], rax
0x18007bc0e  test    rax, rax
0x18007bc11  jz      short loc_18007BC20
0x18007bc13  mov     rcx, rax; this
0x18007bc16  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x18007bc1b  mov     rbx, rax
0x18007bc1e  jmp     short loc_18007BC22
0x18007bc20  xor     ebx, ebx
0x18007bc22  test    rbx, rbx
0x18007bc25  jnz     short loc_18007BC88
0x18007bc27  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007bc2d  mov     ebx, 80041006h
0x18007bc32  mov     edx, ebx
0x18007bc34  mov     rcx, rax
0x18007bc37  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007bc3d  lea     rax, WPP_GLOBAL_Control
0x18007bc44  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bc4b  cmp     rcx, rax
0x18007bc4e  jz      loc_18007BEEC
0x18007bc54  test    byte ptr [rcx+1Ch], 1
0x18007bc58  jz      loc_18007BEEC
0x18007bc5e  cmp     byte ptr [rcx+19h], 2
0x18007bc62  jb      loc_18007BEEC
0x18007bc68  mov     edx, 67h ; 'g'
0x18007bc6d  mov     r9d, 80041006h
0x18007bc73  lea     r8, WPP_613266cfc38534b959e7b6275148614d_Traceguids
0x18007bc7a  mov     rcx, [rcx+10h]
0x18007bc7e  call    WPP_SF_d
0x18007bc83  jmp     loc_18007BEEC
0x18007bc88  mov     [rsp+38h+arg_10], rbx
0x18007bc8d  mov     rcx, rbx; this
0x18007bc90  call    ?Init@CSystemConfigClass@@QEAAXXZ; CSystemConfigClass::Init(void)
0x18007bc95  mov     ecx, 2A0h
0x18007bc9a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18007bca0  mov     [rsp+38h+arg_18], rax
0x18007bca5  test    rax, rax
0x18007bca8  jz      short loc_18007BCB7
0x18007bcaa  mov     rcx, rax; this
0x18007bcad  call    ??0CThisNamespaceInstance@@QEAA@XZ; CThisNamespaceInstance::CThisNamespaceInstance(void)
0x18007bcb2  mov     rdi, rax
0x18007bcb5  jmp     short loc_18007BCB9
0x18007bcb7  xor     edi, edi
0x18007bcb9  test    rdi, rdi
0x18007bcbc  jnz     short loc_18007BD07
0x18007bcbe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007bcc4  mov     ebx, 80041006h
0x18007bcc9  mov     edx, ebx
0x18007bccb  mov     rcx, rax
0x18007bcce  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007bcd4  lea     rax, WPP_GLOBAL_Control
0x18007bcdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bce2  cmp     rcx, rax
0x18007bce5  jz      loc_18007BEE2
0x18007bceb  test    byte ptr [rcx+1Ch], 1
0x18007bcef  jz      loc_18007BEE2
0x18007bcf5  cmp     byte ptr [rcx+19h], 2
0x18007bcf9  jb      loc_18007BEE2
0x18007bcff  lea     edx, [rdi+68h]
0x18007bd02  jmp     loc_18007BDD9
0x18007bd07  mov     rdx, rbx; struct CSystemConfigClass *
0x18007bd0a  mov     rcx, rdi; this
0x18007bd0d  call    ?Init@CSystemConfigInstance@@QEAAXPEAVCSystemConfigClass@@@Z; CSystemConfigInstance::Init(CSystemConfigClass *)
0x18007bd12  mov     rdx, rdi
0x18007bd15  mov     rcx, rsi
0x18007bd18  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x18007bd1e  test    eax, eax
0x18007bd20  jz      short loc_18007BD6A
0x18007bd22  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007bd28  mov     ebx, 80041006h
0x18007bd2d  mov     edx, ebx
0x18007bd2f  mov     rcx, rax
0x18007bd32  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007bd38  lea     rax, WPP_GLOBAL_Control
0x18007bd3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bd46  cmp     rcx, rax
0x18007bd49  jz      loc_18007BEE2
0x18007bd4f  test    byte ptr [rcx+1Ch], 1
0x18007bd53  jz      loc_18007BEE2
0x18007bd59  cmp     byte ptr [rcx+19h], 2
0x18007bd5d  jb      loc_18007BEE2
0x18007bd63  mov     edx, 69h ; 'i'
0x18007bd68  jmp     short loc_18007BDD9
0x18007bd6a  mov     ecx, 360h
0x18007bd6f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18007bd75  mov     [rsp+38h+arg_18], rax
0x18007bd7a  test    rax, rax
0x18007bd7d  jz      short loc_18007BD8C
0x18007bd7f  mov     rcx, rax; this
0x18007bd82  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x18007bd87  mov     rbx, rax
0x18007bd8a  jmp     short loc_18007BD8E
0x18007bd8c  xor     ebx, ebx
0x18007bd8e  test    rbx, rbx
0x18007bd91  jnz     short loc_18007BDF4
0x18007bd93  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007bd99  mov     ebx, 80041006h
0x18007bd9e  mov     edx, ebx
0x18007bda0  mov     rcx, rax
0x18007bda3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007bda9  lea     rax, WPP_GLOBAL_Control
0x18007bdb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bdb7  cmp     rcx, rax
0x18007bdba  jz      loc_18007BEE2
0x18007bdc0  test    byte ptr [rcx+1Ch], 1
0x18007bdc4  jz      loc_18007BEE2
0x18007bdca  cmp     byte ptr [rcx+19h], 2
0x18007bdce  jb      loc_18007BEE2
0x18007bdd4  mov     edx, 6Ah ; 'j'
0x18007bdd9  mov     r9d, 80041006h
0x18007bddf  lea     r8, WPP_613266cfc38534b959e7b6275148614d_Traceguids
0x18007bde6  mov     rcx, [rcx+10h]
0x18007bdea  call    WPP_SF_d
0x18007bdef  jmp     loc_18007BEE2
0x18007bdf4  mov     [rsp+38h+arg_18], rbx
0x18007bdf9  mov     rcx, rbx; this
0x18007bdfc  call    ?Init@CThisNamespaceClass@@QEAAXXZ; CThisNamespaceClass::Init(void)
0x18007be01  mov     ecx, 2A0h
0x18007be06  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18007be0c  mov     [rsp+38h+var_18], rax
0x18007be11  test    rax, rax
0x18007be14  jz      short loc_18007BE23
0x18007be16  mov     rcx, rax; this
0x18007be19  call    ??0CThisNamespaceInstance@@QEAA@XZ; CThisNamespaceInstance::CThisNamespaceInstance(void)
0x18007be1e  mov     rdi, rax
0x18007be21  jmp     short loc_18007BE25
0x18007be23  xor     edi, edi
0x18007be25  test    rdi, rdi
0x18007be28  jnz     short loc_18007BE68
0x18007be2a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007be30  mov     ebx, 80041006h
0x18007be35  mov     edx, ebx
0x18007be37  mov     rcx, rax
0x18007be3a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007be40  lea     rax, WPP_GLOBAL_Control
0x18007be47  mov     rcx, cs:WPP_GLOBAL_Control
0x18007be4e  cmp     rcx, rax
0x18007be51  jz      loc_18007BED7
0x18007be57  test    byte ptr [rcx+1Ch], 1
0x18007be5b  jz      short loc_18007BED7
0x18007be5d  cmp     byte ptr [rcx+19h], 2
0x18007be61  jb      short loc_18007BED7
0x18007be63  lea     edx, [rdi+6Bh]
0x18007be66  jmp     short loc_18007BEBD
0x18007be68  mov     rdx, rbx; struct CThisNamespaceClass *
0x18007be6b  mov     rcx, rdi; this
0x18007be6e  call    ?Init@CThisNamespaceInstance@@QEAAXPEAVCThisNamespaceClass@@@Z; CThisNamespaceInstance::Init(CThisNamespaceClass *)
0x18007be73  mov     rdx, rdi
0x18007be76  mov     rcx, rsi
0x18007be79  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x18007be7f  test    eax, eax
0x18007be81  jz      short loc_18007BED5
0x18007be83  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007be89  mov     ebx, 80041006h
0x18007be8e  mov     edx, ebx
0x18007be90  mov     rcx, rax
0x18007be93  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007be99  lea     rax, WPP_GLOBAL_Control
0x18007bea0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bea7  cmp     rcx, rax
0x18007beaa  jz      short loc_18007BED7
0x18007beac  test    byte ptr [rcx+1Ch], 1
0x18007beb0  jz      short loc_18007BED7
0x18007beb2  cmp     byte ptr [rcx+19h], 2
0x18007beb6  jb      short loc_18007BED7
0x18007beb8  mov     edx, 6Ch ; 'l'
0x18007bebd  mov     r9d, 80041006h
0x18007bec3  lea     r8, WPP_613266cfc38534b959e7b6275148614d_Traceguids
0x18007beca  mov     rcx, [rcx+10h]
0x18007bece  call    WPP_SF_d
0x18007bed3  jmp     short loc_18007BED7
0x18007bed5  xor     ebx, ebx
0x18007bed7  lea     rcx, [rsp+38h+arg_18]
0x18007bedc  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x18007bee1  nop
0x18007bee2  lea     rcx, [rsp+38h+arg_10]
0x18007bee7  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x18007beec  mov     eax, ebx
0x18007beee  mov     rbx, [rsp+38h+arg_0]
0x18007bef3  mov     rsi, [rsp+38h+arg_8]
0x18007bef8  add     rsp, 30h
0x18007befc  pop     rdi
0x18007befd  retn
```
