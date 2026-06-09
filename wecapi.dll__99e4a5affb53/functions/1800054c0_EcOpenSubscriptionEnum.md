# EcOpenSubscriptionEnum

- ea: `0x1800054c0`
- end: `0x18000570d`
- name: `EcOpenSubscriptionEnum`
- size: `589`
- prototype: `EC_HANDLE __stdcall(DWORD Flags)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x18000262c`
- `0x1800027ac`
- `0x180003178`
- `0x180003a2c`
- `0x1800054c0`
- `0x18000a6b0`
- `0x18000d010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180005528`
- `RPCRT4!NdrClientCall3` at `0x180005528`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005627`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005627`

## pseudocode

```c
EC_HANDLE __stdcall EcOpenSubscriptionEnum(DWORD Flags)
{
  DWORD v1; // r14d
  unsigned int Pointer; // ebx
  unsigned __int16 **v3; // r15
  unsigned int v4; // r12d
  SubscriptionNameEnumerator *v5; // rax
  __int64 v6; // rcx
  SubscriptionNameEnumerator *v7; // rbx
  volatile signed __int32 *v8; // rdi
  unsigned __int64 v9; // rsi
  wmi::Exception *v11; // [rsp+40h] [rbp-D8h] BYREF
  char v12; // [rsp+48h] [rbp-D0h]
  void (*v13)(unsigned int, unsigned __int16 **, bool); // [rsp+50h] [rbp-C8h]
  unsigned int v14; // [rsp+58h] [rbp-C0h]
  unsigned __int16 **v15; // [rsp+60h] [rbp-B8h]
  char v16; // [rsp+68h] [rbp-B0h]
  _BYTE pExceptionObject[56]; // [rsp+70h] [rbp-A8h] BYREF
  _BYTE v18[112]; // [rsp+A8h] [rbp-70h] BYREF
  unsigned int v19; // [rsp+120h] [rbp+8h] BYREF
  SubscriptionNameEnumerator *v20; // [rsp+128h] [rbp+10h] BYREF
  unsigned __int16 **v21; // [rsp+130h] [rbp+18h] BYREF
  SubscriptionNameEnumerator *v22; // [rsp+138h] [rbp+20h]

  try
  {
    v1 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
        122);
      throw (wmi::GenericException *)pExceptionObject;
    }
    v21 = 0;
    v19 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0,
                              0,
                              g_bindingHandle,
                              0,
                              &v19,
                              &v21).Pointer;
    if ( Pointer )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, Pointer);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)v18,
        Pointer,
        "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
        134);
      throw (wmi::GenericException *)v18;
    }
    v3 = v21;
    v4 = v19;
    v12 = 0;
    v13 = CleanupStringVector;
    v14 = v19;
    v15 = v21;
    v16 = 0;
    v22 = 0;
    v5 = (SubscriptionNameEnumerator *)operator new(0x38u);
    v20 = v5;
    if ( v5 )
      v7 = SubscriptionNameEnumerator::SubscriptionNameEnumerator(v5, v21, v19);
    else
      v7 = 0;
    v8 = (volatile signed __int32 *)((char *)v7 + 8);
    if ( v7 )
      _InterlockedIncrement(v8);
    v22 = v7;
    v20 = v7;
    if ( v7 )
      _InterlockedIncrement(v8);
    v9 = (unsigned int)ObjectTable<wmi::AutoRef<Object>>::Insert(v6, &v20);
    if ( v7 && _InterlockedExchangeAdd(v8, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(SubscriptionNameEnumerator *, __int64))v7)(v7, 1);
    CleanupStringVector(v4, v3, 0);
  }
  catch ( wmi::Exception *v11 )
  {
    v19 = (**(__int64 (__fastcall ***)(wmi::Exception *))v11)(v11);
    v20 = 0;
    v1 = v19;
    v9 = 0;
  }
  v1 = 0;
  if ( Flags )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, 87);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0x57u,
      "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
      122);
    throw (wmi::GenericException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800054c0  push    rbx
0x1800054c2  push    rsi
0x1800054c3  push    rdi
0x1800054c4  push    r12
0x1800054c6  push    r14
0x1800054c8  push    r15
0x1800054ca  sub     rsp, 0E8h
0x1800054d1  xor     r14d, r14d
0x1800054d4  test    ecx, ecx
0x1800054d6  jnz     loc_180005641
0x1800054dc  mov     [rsp+118h+arg_10], 0
0x1800054e8  mov     [rsp+118h+arg_0], 0
0x1800054f3  lea     rax, [rsp+118h+arg_10]
0x1800054fb  mov     [rsp+118h+var_E8], rax
0x180005500  lea     rax, [rsp+118h+arg_0]
0x180005508  mov     [rsp+118h+var_F0], rax
0x18000550d  mov     [rsp+118h+var_F8], 0
0x180005515  mov     r9, cs:?g_bindingHandle@@3PEAXEA; void * g_bindingHandle
0x18000551c  xor     r8d, r8d; pReturnValue
0x18000551f  xor     edx, edx; nProcNum
0x180005521  lea     rcx, pProxyInfo; pProxyInfo
0x180005528  call    cs:__imp_NdrClientCall3
0x18000552e  mov     rbx, rax
0x180005531  test    ebx, ebx
0x180005533  jnz     loc_1800056A4
0x180005539  mov     r15, [rsp+118h+arg_10]
0x180005541  mov     r12d, [rsp+118h+arg_0]
0x180005549  mov     [rsp+118h+var_D0], 0
0x18000554e  lea     rax, ?CleanupStringVector@@YAXKPEAPEAG_N@Z; CleanupStringVector(ulong,ushort * *,bool)
0x180005555  mov     [rsp+118h+var_C8], rax
0x18000555a  mov     [rsp+118h+var_C0], r12d
0x18000555f  mov     [rsp+118h+var_B8], r15
0x180005564  mov     [rsp+118h+var_B0], 0
0x180005569  mov     [rsp+118h+arg_18], 0
0x180005575  mov     ecx, 38h ; '8'; dwBytes
0x18000557a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000557f  mov     [rsp+118h+arg_8], rax
0x180005587  test    rax, rax
0x18000558a  jz      short loc_1800055A9
0x18000558c  mov     r8d, [rsp+118h+arg_0]; unsigned int
0x180005594  mov     rdx, [rsp+118h+arg_10]; unsigned __int16 **
0x18000559c  mov     rcx, rax; this
0x18000559f  call    ??0SubscriptionNameEnumerator@@QEAA@PEAPEAGK@Z; SubscriptionNameEnumerator::SubscriptionNameEnumerator(ushort * *,ulong)
0x1800055a4  mov     rbx, rax
0x1800055a7  jmp     short loc_1800055AB
0x1800055a9  xor     ebx, ebx
0x1800055ab  lea     rdi, [rbx+8]
0x1800055af  test    rbx, rbx
0x1800055b2  jz      short loc_1800055B7
0x1800055b4  lock inc dword ptr [rdi]
0x1800055b7  mov     [rsp+118h+arg_18], rbx
0x1800055bf  mov     [rsp+118h+arg_8], rbx
0x1800055c7  test    rbx, rbx
0x1800055ca  jz      short loc_1800055CF
0x1800055cc  lock inc dword ptr [rdi]
0x1800055cf  lea     rdx, [rsp+118h+arg_8]
0x1800055d7  call    ?Insert@?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@QEAAKV?$AutoRef@VObject@@@wmi@@@Z; ObjectTable<wmi::AutoRef<Object>>::Insert(wmi::AutoRef<Object>)
0x1800055dc  mov     esi, eax
0x1800055de  test    rbx, rbx
0x1800055e1  jz      short loc_180005603
0x1800055e3  or      eax, 0FFFFFFFFh
0x1800055e6  lock xadd [rdi], eax
0x1800055ea  cmp     eax, 1
0x1800055ed  jnz     short loc_180005603
0x1800055ef  mov     rax, [rbx]
0x1800055f2  mov     edx, 1
0x1800055f7  mov     rcx, rbx
0x1800055fa  mov     rax, [rax]
0x1800055fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005602  nop
0x180005603  xor     r8d, r8d; bool
0x180005606  mov     rdx, r15; unsigned __int16 **
0x180005609  mov     ecx, r12d; unsigned int
0x18000560c  call    ?CleanupStringVector@@YAXKPEAPEAG_N@Z; CleanupStringVector(ulong,ushort * *,bool)
0x180005611  nop
0x180005612  jmp     short loc_180005624
0x180005614  mov     r14d, [rsp+118h+arg_0]
0x18000561c  mov     rsi, [rsp+118h+arg_8]
0x180005624  mov     ecx, r14d; dwErrCode
0x180005627  call    cs:__imp_SetLastError
0x18000562d  mov     rax, rsi
0x180005630  add     rsp, 0E8h
0x180005637  pop     r15
0x180005639  pop     r14
0x18000563b  pop     r12
0x18000563d  pop     rdi
0x18000563e  pop     rsi
0x18000563f  pop     rbx
0x180005640  retn
0x180005641  lea     rax, WPP_GLOBAL_Control
0x180005648  mov     rcx, cs:WPP_GLOBAL_Control
0x18000564f  cmp     rcx, rax
0x180005652  jz      short loc_180005678
0x180005654  test    byte ptr [rcx+1Ch], 1
0x180005658  jz      short loc_180005678
0x18000565a  cmp     byte ptr [rcx+19h], 2
0x18000565e  jb      short loc_180005678
0x180005660  lea     edx, [r14+0Ch]
0x180005664  lea     r9d, [r14+57h]
0x180005668  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x18000566f  mov     rcx, [rcx+10h]
0x180005673  call    WPP_SF_D
0x180005678  mov     r9d, 7Ah ; 'z'; int
0x18000567e  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x180005685  lea     edx, [r9-23h]; unsigned int
0x180005689  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18000568e  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x180005693  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000569a  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18000569f  call    _CxxThrowException_0
0x1800056a4  lea     rax, WPP_GLOBAL_Control
0x1800056ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056b2  cmp     rcx, rax
0x1800056b5  jz      short loc_1800056DB
0x1800056b7  test    byte ptr [rcx+1Ch], 1
0x1800056bb  jz      short loc_1800056DB
0x1800056bd  cmp     byte ptr [rcx+19h], 2
0x1800056c1  jb      short loc_1800056DB
0x1800056c3  mov     edx, 0Dh
0x1800056c8  mov     r9d, ebx
0x1800056cb  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x1800056d2  mov     rcx, [rcx+10h]
0x1800056d6  call    WPP_SF_D
0x1800056db  mov     r9d, 86h; int
0x1800056e1  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x1800056e8  mov     edx, ebx; unsigned int
0x1800056ea  lea     rcx, [rsp+118h+var_70]; this
0x1800056f2  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x1800056f7  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800056fe  lea     rcx, [rsp+118h+var_70]; pExceptionObject
0x180005706  call    _CxxThrowException_0
```
