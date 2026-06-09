# CWbemNamespace::InternalGetClass(ushort const *,IWbemClassObject * *)

- ea: `0x180044ab0`
- end: `0x180044e2a`
- name: `?InternalGetClass@CWbemNamespace@@UEAAJPEBGPEAPEAUIWbemClassObject@@@Z`
- size: `890`
- prototype: `int(CWbemNamespace *__hidden this, const unsigned __int16 *, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009ee28`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18003d050`
- `0x180044658`
- `0x180044ab0`
- `0x18005fbbc`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?CreateInst@CWbemCallSecurity@@SAPEAVIWbemCallSecurity@@K@Z` at `0x180044c26`
- `wbemcomn!?CreateInst@CWbemCallSecurity@@SAPEAVIWbemCallSecurity@@K@Z` at `0x180044c26`
- `wbemcomn!GetMemLogObject` at `0x180044c38`
- `wbemcomn!GetMemLogObject` at `0x180044c9e`
- `wbemcomn!GetMemLogObject` at `0x180044d12`
- `wbemcomn!GetMemLogObject` at `0x180044d56`
- `wbemcomn!GetMemLogObject` at `0x180044dec`
- `wbemcomn!GetMemLogObject` at `0x180044c38`
- `wbemcomn!GetMemLogObject` at `0x180044c9e`
- `wbemcomn!GetMemLogObject` at `0x180044d12`
- `wbemcomn!GetMemLogObject` at `0x180044d56`
- `wbemcomn!GetMemLogObject` at `0x180044dec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044c48`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044cae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044d1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044d61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044df7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044c48`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044cae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044d1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044d61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044df7`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180044bdc`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180044d46`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180044bdc`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180044d46`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180044b40`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180044b40`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemNamespace::InternalGetClass(
        CWbemNamespace *this,
        const unsigned __int16 *a2,
        struct IWbemClassObject **a3)
{
  CWbemNamespace *v6; // r14
  struct CWbemRequest *CurrentRequest; // rax
  struct IWbemContext *NewContext; // rsi
  IUnknown *Inst; // rdi
  IUnknown *v10; // r15
  HRESULT ObjectByPath; // ebx
  CMemoryLog *v13; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v15; // rax
  CClientCnt *v16; // rcx
  CMemoryLog *v17; // rax
  __int64 v18; // rdx
  CMemoryLog *v19; // rax
  void *ppInterface; // [rsp+30h] [rbp-38h] BYREF
  IUnknown *pNewObject; // [rsp+38h] [rbp-30h] BYREF
  IUnknown *ppOldObject[2]; // [rsp+40h] [rbp-28h] BYREF
  struct IWbemContext *v23; // [rsp+50h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 460, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
  }
  if ( !g_bDontAllowNewConnections )
  {
    v6 = (CWbemNamespace *)((char *)this - 8);
    if ( !*((_DWORD *)this + 5) )
    {
      CurrentRequest = CWbemQueue::GetCurrentRequest();
      if ( CurrentRequest )
      {
        NewContext = (struct IWbemContext *)*((_QWORD *)CurrentRequest + 5);
        ((void (__fastcall *)(struct IWbemContext *))NewContext->lpVtbl->AddRef)(NewContext);
      }
      else
      {
        NewContext = ConfigMgr::GetNewContext();
        if ( !NewContext )
        {
          MemLogObject = GetMemLogObject();
          ObjectByPath = -2147217402;
          CMemoryLog::Write(MemLogObject, -2147217402);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              461,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              2147749894LL);
          }
          return (unsigned int)ObjectByPath;
        }
      }
      v23 = NewContext;
      ppInterface = 0;
      pNewObject = 0;
      if ( CoGetCallContext(&IID_IServerSecurity, &ppInterface) < 0 )
      {
        Inst = (IUnknown *)CWbemCallSecurity::CreateInst(0);
        if ( !Inst )
        {
          v13 = GetMemLogObject();
          ObjectByPath = -2147217402;
          CMemoryLog::Write(v13, -2147217402);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              462,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              2147749894LL);
          }
          goto LABEL_17;
        }
      }
      else
      {
        Inst = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
      }
      if ( !Inst )
        goto LABEL_10;
      ObjectByPath = ((__int64 (__fastcall *)(IUnknown *, __int64))Inst->lpVtbl[3].QueryInterface)(Inst, 1);
      if ( ObjectByPath >= 0 )
      {
        ObjectByPath = CoSwitchCallContext(Inst, &pNewObject);
        if ( ObjectByPath >= 0 )
        {
LABEL_10:
          LODWORD(ppOldObject[0]) = Inst != 0;
          v10 = pNewObject;
          ppOldObject[1] = pNewObject;
          ObjectByPath = CWbemNamespace::Exec_GetObjectByPath(v6, a2, 0, NewContext, a3, 0);
          if ( ObjectByPath < 0 )
          {
            v19 = GetMemLogObject();
            CMemoryLog::Write(v19, ObjectByPath);
          }
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              465,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)ObjectByPath);
          }
          if ( !Inst )
            goto LABEL_17;
          ppOldObject[0] = 0;
          CoSwitchCallContext(v10, ppOldObject);
LABEL_16:
          ((void (__fastcall *)(IUnknown *))Inst->lpVtbl->Release)(Inst);
LABEL_17:
          ((void (__fastcall *)(struct IWbemContext *))NewContext->lpVtbl->Release)(NewContext);
          v23 = 0;
          return (unsigned int)ObjectByPath;
        }
        v17 = GetMemLogObject();
        CMemoryLog::Write(v17, ObjectByPath);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_16;
        }
        v18 = 464;
      }
      else
      {
        v15 = GetMemLogObject();
        CMemoryLog::Write(v15, ObjectByPath);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_16;
        }
        v18 = 463;
      }
      WPP_SF_d(*((_QWORD *)v16 + 2), v18, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)ObjectByPath);
      goto LABEL_16;
    }
  }
  return 2147749939LL;
}

```

## disassembly

```asm
0x180044ab0  push    rbp
0x180044ab2  push    rbx
0x180044ab3  push    rsi
0x180044ab4  push    rdi
0x180044ab5  push    r12
0x180044ab7  push    r13
0x180044ab9  push    r14
0x180044abb  push    r15
0x180044abd  mov     rbp, rsp
0x180044ac0  sub     rsp, 68h
0x180044ac4  mov     r13, r8
0x180044ac7  mov     r12, rdx
0x180044aca  mov     rbx, rcx
0x180044acd  lea     rdi, WPP_GLOBAL_Control
0x180044ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180044adb  cmp     rcx, rdi
0x180044ade  jz      short loc_180044AEA
0x180044ae0  test    byte ptr [rcx+1Ch], 1
0x180044ae4  jnz     loc_180044DAA
0x180044aea  xor     r15d, r15d
0x180044aed  cmp     cs:?g_bDontAllowNewConnections@@3HA, r15d; int g_bDontAllowNewConnections
0x180044af4  jnz     loc_180044DA0
0x180044afa  lea     r14, [rbx-8]
0x180044afe  cmp     [r14+1Ch], r15d
0x180044b02  jnz     loc_180044DA0
0x180044b08  call    ?GetCurrentRequest@CWbemQueue@@SAPEAVCWbemRequest@@XZ; CWbemQueue::GetCurrentRequest(void)
0x180044b0d  test    rax, rax
0x180044b10  jz      loc_180044C8D
0x180044b16  mov     rsi, [rax+28h]
0x180044b1a  mov     rax, [rsi]
0x180044b1d  mov     rcx, rsi
0x180044b20  mov     rax, [rax+8]
0x180044b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b29  mov     [rbp+var_18], rsi
0x180044b2d  mov     [rbp+ppInterface], r15
0x180044b31  mov     [rbp+pNewObject], r15
0x180044b35  lea     rdx, [rbp+ppInterface]; ppInterface
0x180044b39  lea     rcx, IID_IServerSecurity; riid
0x180044b40  call    cs:__imp_CoGetCallContext
0x180044b46  test    eax, eax
0x180044b48  js      loc_180044C24
0x180044b4e  mov     rdi, r15
0x180044b51  mov     rcx, [rbp+ppInterface]
0x180044b55  mov     rax, [rcx]
0x180044b58  mov     rax, [rax+10h]
0x180044b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b61  mov     [rbp+arg_18], rdi
0x180044b65  test    rdi, rdi
0x180044b68  jnz     loc_180044CF8
0x180044b6e  mov     eax, r15d
0x180044b71  test    rdi, rdi
0x180044b74  setnz   al
0x180044b77  mov     dword ptr [rbp+ppOldObject], eax
0x180044b7a  mov     r15, [rbp+pNewObject]
0x180044b7e  mov     [rbp+var_20], r15
0x180044b82  mov     [rsp+68h+var_40], 0; struct IWbemClassObject **
0x180044b8b  mov     [rsp+68h+var_48], r13; struct IWbemClassObject **
0x180044b90  mov     r9, rsi; struct IWbemContext *
0x180044b93  xor     r8d, r8d; int
0x180044b96  mov     rdx, r12; unsigned __int16 *
0x180044b99  mov     rcx, r14; this
0x180044b9c  call    ?Exec_GetObjectByPath@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@2@Z; CWbemNamespace::Exec_GetObjectByPath(ushort const *,long,IWbemContext *,IWbemClassObject * *,IWbemClassObject * *)
0x180044ba1  mov     ebx, eax
0x180044ba3  test    eax, eax
0x180044ba5  js      loc_180044DEC
0x180044bab  mov     rcx, cs:WPP_GLOBAL_Control
0x180044bb2  lea     rax, WPP_GLOBAL_Control
0x180044bb9  cmp     rcx, rax
0x180044bbc  jz      short loc_180044BC8
0x180044bbe  test    byte ptr [rcx+1Ch], 1
0x180044bc2  jnz     loc_180044E02
0x180044bc8  test    rdi, rdi
0x180044bcb  jz      short loc_180044BE3
0x180044bcd  mov     [rbp+ppOldObject], 0
0x180044bd5  lea     rdx, [rbp+ppOldObject]; ppOldObject
0x180044bd9  mov     rcx, r15; pNewObject
0x180044bdc  call    cs:__imp_CoSwitchCallContext
0x180044be2  nop
0x180044be3  xor     r15d, r15d
0x180044be6  test    rdi, rdi
0x180044be9  jz      short loc_180044BFA
0x180044beb  mov     rax, [rdi]
0x180044bee  mov     rcx, rdi
0x180044bf1  mov     rax, [rax+10h]
0x180044bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bfa  mov     [rbp+arg_18], r15
0x180044bfe  mov     rax, [rsi]
0x180044c01  mov     rcx, rsi
0x180044c04  mov     rax, [rax+10h]
0x180044c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c0d  mov     [rbp+var_18], r15
0x180044c11  mov     eax, ebx
0x180044c13  add     rsp, 68h
0x180044c17  pop     r15
0x180044c19  pop     r14
0x180044c1b  pop     r13
0x180044c1d  pop     r12
0x180044c1f  pop     rdi
0x180044c20  pop     rsi
0x180044c21  pop     rbx
0x180044c22  pop     rbp
0x180044c23  retn
0x180044c24  xor     ecx, ecx
0x180044c26  call    cs:__imp_?CreateInst@CWbemCallSecurity@@SAPEAVIWbemCallSecurity@@K@Z; CWbemCallSecurity::CreateInst(ulong)
0x180044c2c  mov     rdi, rax
0x180044c2f  test    rax, rax
0x180044c32  jnz     loc_180044B61
0x180044c38  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180044c3e  mov     ebx, 80041006h
0x180044c43  mov     edx, ebx
0x180044c45  mov     rcx, rax
0x180044c48  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180044c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180044c55  lea     rax, WPP_GLOBAL_Control
0x180044c5c  cmp     rcx, rax
0x180044c5f  jz      short loc_180044BFE
0x180044c61  test    byte ptr [rcx+1Ch], 1
0x180044c65  jz      short loc_180044BFE
0x180044c67  cmp     byte ptr [rcx+19h], 2
0x180044c6b  jb      short loc_180044BFE
0x180044c6d  mov     edx, 1CEh
0x180044c72  mov     r9d, 80041006h
0x180044c78  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180044c7f  mov     rcx, [rcx+10h]
0x180044c83  call    WPP_SF_d
0x180044c88  jmp     loc_180044BFE
0x180044c8d  call    ?GetNewContext@ConfigMgr@@SAPEAUIWbemContext@@XZ; ConfigMgr::GetNewContext(void)
0x180044c92  mov     rsi, rax
0x180044c95  test    rax, rax
0x180044c98  jnz     loc_180044B29
0x180044c9e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180044ca4  mov     ebx, 80041006h
0x180044ca9  mov     edx, ebx
0x180044cab  mov     rcx, rax
0x180044cae  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180044cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180044cbb  cmp     rcx, rdi
0x180044cbe  jz      loc_180044C11
0x180044cc4  test    byte ptr [rcx+1Ch], 1
0x180044cc8  jz      loc_180044C11
0x180044cce  cmp     byte ptr [rcx+19h], 2
0x180044cd2  jb      loc_180044C11
0x180044cd8  mov     edx, 1CDh
0x180044cdd  mov     r9d, 80041006h
0x180044ce3  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180044cea  mov     rcx, [rcx+10h]
0x180044cee  call    WPP_SF_d
0x180044cf3  jmp     loc_180044C11
0x180044cf8  mov     rax, [rdi]
0x180044cfb  mov     edx, 1
0x180044d00  mov     rcx, rdi
0x180044d03  mov     rax, [rax+48h]
0x180044d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d0c  mov     ebx, eax
0x180044d0e  test    eax, eax
0x180044d10  jns     short loc_180044D3F
0x180044d12  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180044d18  mov     edx, ebx
0x180044d1a  mov     rcx, rax
0x180044d1d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180044d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180044d2a  lea     rax, WPP_GLOBAL_Control
0x180044d31  cmp     rcx, rax
0x180044d34  jnz     loc_180044DD1
0x180044d3a  jmp     loc_180044BEB
0x180044d3f  lea     rdx, [rbp+pNewObject]; ppOldObject
0x180044d43  mov     rcx, rdi; pNewObject
0x180044d46  call    cs:__imp_CoSwitchCallContext
0x180044d4c  mov     ebx, eax
0x180044d4e  test    eax, eax
0x180044d50  jns     loc_180044B6E
0x180044d56  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180044d5c  mov     edx, ebx
0x180044d5e  mov     rcx, rax
0x180044d61  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180044d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180044d6e  lea     rax, WPP_GLOBAL_Control
0x180044d75  cmp     rcx, rax
0x180044d78  jz      short loc_180044D3A
0x180044d7a  test    byte ptr [rcx+1Ch], 1
0x180044d7e  jz      short loc_180044D3A
0x180044d80  cmp     byte ptr [rcx+19h], 2
0x180044d84  jb      short loc_180044D3A
0x180044d86  mov     edx, 1D0h
0x180044d8b  mov     r9d, ebx
0x180044d8e  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180044d95  mov     rcx, [rcx+10h]
0x180044d99  call    WPP_SF_d
0x180044d9e  jmp     short loc_180044D3A
0x180044da0  mov     eax, 80041033h
0x180044da5  jmp     loc_180044C13
0x180044daa  cmp     byte ptr [rcx+19h], 5
0x180044dae  jb      loc_180044AEA
0x180044db4  mov     edx, 1CCh
0x180044db9  mov     r9, r12
0x180044dbc  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180044dc3  mov     rcx, [rcx+10h]
0x180044dc7  call    WPP_SF_S
0x180044dcc  jmp     loc_180044AEA
0x180044dd1  test    byte ptr [rcx+1Ch], 1
0x180044dd5  jz      loc_180044D3A
0x180044ddb  cmp     byte ptr [rcx+19h], 2
0x180044ddf  jb      loc_180044D3A
0x180044de5  mov     edx, 1CFh
0x180044dea  jmp     short loc_180044D8B
0x180044dec  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180044df2  mov     edx, ebx
0x180044df4  mov     rcx, rax
0x180044df7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180044dfd  jmp     loc_180044BAB
0x180044e02  cmp     byte ptr [rcx+19h], 2
0x180044e06  jb      loc_180044BC8
0x180044e0c  mov     edx, 1D1h
0x180044e11  mov     r9d, ebx
0x180044e14  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180044e1b  mov     rcx, [rcx+10h]
0x180044e1f  call    WPP_SF_d
0x180044e24  jmp     loc_180044BC8
```
