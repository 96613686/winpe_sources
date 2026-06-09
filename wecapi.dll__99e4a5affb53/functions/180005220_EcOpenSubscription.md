# EcOpenSubscription

- ea: `0x180005220`
- end: `0x1800054b9`
- name: `EcOpenSubscription`
- size: `665`
- prototype: `EC_HANDLE __stdcall(LPCWSTR SubscriptionName, DWORD AccessMask, DWORD Flags)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x18000262c`
- `0x1800027ac`
- `0x180003a2c`
- `0x180005220`
- `0x180005f18`
- `0x18000d010`

## import_xrefs

- `msvcrt!iswalnum` at `0x180005251`
- `msvcrt!iswalnum` at `0x180005251`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005301`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005301`

## pseudocode

```c
EC_HANDLE __stdcall EcOpenSubscription(LPCWSTR SubscriptionName, DWORD AccessMask, DWORD Flags)
{
  DWORD v6; // esi
  Subscription *v7; // rax
  __int64 v8; // rcx
  Subscription *v9; // rbx
  unsigned __int64 v10; // rdi
  wmi::Exception *v12; // [rsp+28h] [rbp-100h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE v14[56]; // [rsp+68h] [rbp-C0h] BYREF
  _BYTE v15[56]; // [rsp+A0h] [rbp-88h] BYREF
  _BYTE v16[80]; // [rsp+D8h] [rbp-50h] BYREF
  DWORD v17; // [rsp+140h] [rbp+18h]
  Subscription *v18; // [rsp+148h] [rbp+20h] BYREF

  try
  {
    v6 = 0;
    if ( Flags >= 3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
        209);
      throw (wmi::GenericException *)pExceptionObject;
    }
    if ( !SubscriptionName )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)v14,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
        211);
      throw (wmi::GenericException *)v14;
    }
    if ( !iswalnum(*SubscriptionName) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)v15,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
        213);
      throw (wmi::GenericException *)v15;
    }
    if ( (AccessMask & 0xFFFFFFFC) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)v16,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
        216);
      throw (wmi::GenericException *)v16;
    }
    v7 = (Subscription *)operator new(0x70u);
    v18 = v7;
    if ( v7 )
      v9 = Subscription::Subscription(v7, (unsigned __int16 *)SubscriptionName, AccessMask, Flags);
    else
      v9 = 0;
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
    v18 = v9;
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
    v10 = (unsigned int)ObjectTable<wmi::AutoRef<Object>>::Insert(v8, &v18);
    *((_QWORD *)v9 + 12) = v10;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(Subscription *, __int64))v9)(v9, 1);
  }
  catch ( wmi::Exception *v12 )
  {
    v17 = (**(__int64 (__fastcall ***)(wmi::Exception *))v12)(v12);
    v18 = 0;
    v6 = v17;
    v10 = 0;
  }
  v6 = 0;
  if ( Flags >= 3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, 87);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0x57u,
      "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
      209);
    throw (wmi::GenericException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180005220  mov     [rsp+arg_0], rbx
0x180005225  push    rsi
0x180005226  push    rdi
0x180005227  push    r14
0x180005229  sub     rsp, 110h
0x180005230  mov     edi, r8d
0x180005233  mov     r14d, edx
0x180005236  mov     rbx, rcx
0x180005239  xor     esi, esi
0x18000523b  cmp     r8d, 3
0x18000523f  jnb     loc_18000531E
0x180005245  test    rbx, rbx
0x180005248  jz      loc_180005380
0x18000524e  movzx   ecx, word ptr [rcx]; C
0x180005251  call    cs:__imp_iswalnum
0x180005257  test    eax, eax
0x180005259  jz      loc_1800053E2
0x18000525f  test    r14d, 0FFFFFFFCh
0x180005266  jnz     loc_18000544C
0x18000526c  mov     ecx, 70h ; 'p'; dwBytes
0x180005271  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005276  mov     [rsp+128h+arg_18], rax
0x18000527e  test    rax, rax
0x180005281  jz      short loc_180005299
0x180005283  mov     r9d, edi; unsigned int
0x180005286  mov     r8d, r14d; unsigned int
0x180005289  mov     rdx, rbx; unsigned __int16 *
0x18000528c  mov     rcx, rax; this
0x18000528f  call    ??0Subscription@@QEAA@PEBGKK@Z; Subscription::Subscription(ushort const *,ulong,ulong)
0x180005294  mov     rbx, rax
0x180005297  jmp     short loc_18000529B
0x180005299  xor     ebx, ebx
0x18000529b  mov     [rsp+128h+var_108], rbx
0x1800052a0  test    rbx, rbx
0x1800052a3  jz      short loc_1800052A9
0x1800052a5  lock inc dword ptr [rbx+8]
0x1800052a9  mov     [rsp+128h+arg_18], rbx
0x1800052b1  test    rbx, rbx
0x1800052b4  jz      short loc_1800052BA
0x1800052b6  lock inc dword ptr [rbx+8]
0x1800052ba  lea     rdx, [rsp+128h+arg_18]
0x1800052c2  call    ?Insert@?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@QEAAKV?$AutoRef@VObject@@@wmi@@@Z; ObjectTable<wmi::AutoRef<Object>>::Insert(wmi::AutoRef<Object>)
0x1800052c7  mov     edi, eax
0x1800052c9  mov     [rbx+60h], rdi
0x1800052cd  or      eax, 0FFFFFFFFh
0x1800052d0  lock xadd [rbx+8], eax
0x1800052d5  cmp     eax, 1
0x1800052d8  jnz     short loc_1800052EE
0x1800052da  mov     rax, [rbx]
0x1800052dd  mov     edx, 1
0x1800052e2  mov     rcx, rbx
0x1800052e5  mov     rax, [rax]
0x1800052e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ed  nop
0x1800052ee  jmp     short loc_1800052FF
0x1800052f0  mov     esi, [rsp+128h+arg_10]
0x1800052f7  mov     rdi, [rsp+128h+arg_18]
0x1800052ff  mov     ecx, esi; dwErrCode
0x180005301  call    cs:__imp_SetLastError
0x180005307  mov     rax, rdi
0x18000530a  mov     rbx, [rsp+128h+arg_0]
0x180005312  add     rsp, 110h
0x180005319  pop     r14
0x18000531b  pop     rdi
0x18000531c  pop     rsi
0x18000531d  retn
0x18000531e  lea     rax, WPP_GLOBAL_Control
0x180005325  mov     rcx, cs:WPP_GLOBAL_Control
0x18000532c  cmp     rcx, rax
0x18000532f  jz      short loc_180005354
0x180005331  test    byte ptr [rcx+1Ch], 1
0x180005335  jz      short loc_180005354
0x180005337  cmp     byte ptr [rcx+19h], 2
0x18000533b  jb      short loc_180005354
0x18000533d  lea     edx, [rsi+10h]
0x180005340  lea     r9d, [rsi+57h]
0x180005344  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x18000534b  mov     rcx, [rcx+10h]
0x18000534f  call    WPP_SF_D
0x180005354  mov     r9d, 0D1h; int
0x18000535a  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x180005361  lea     edx, [r9-7Ah]; unsigned int
0x180005365  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18000536a  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000536f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180005376  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18000537b  call    _CxxThrowException_0
0x180005380  lea     rax, WPP_GLOBAL_Control
0x180005387  mov     rcx, cs:WPP_GLOBAL_Control
0x18000538e  cmp     rcx, rax
0x180005391  jz      short loc_1800053B6
0x180005393  test    byte ptr [rcx+1Ch], 1
0x180005397  jz      short loc_1800053B6
0x180005399  cmp     byte ptr [rcx+19h], 2
0x18000539d  jb      short loc_1800053B6
0x18000539f  lea     edx, [rbx+11h]
0x1800053a2  lea     r9d, [rbx+57h]
0x1800053a6  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x1800053ad  mov     rcx, [rcx+10h]
0x1800053b1  call    WPP_SF_D
0x1800053b6  mov     r9d, 0D3h; int
0x1800053bc  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x1800053c3  lea     edx, [r9-7Ch]; unsigned int
0x1800053c7  lea     rcx, [rsp+128h+var_C0]; this
0x1800053cc  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x1800053d1  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800053d8  lea     rcx, [rsp+128h+var_C0]; pExceptionObject
0x1800053dd  call    _CxxThrowException_0
0x1800053e2  lea     rax, WPP_GLOBAL_Control
0x1800053e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053f0  cmp     rcx, rax
0x1800053f3  jz      short loc_18000541A
0x1800053f5  test    byte ptr [rcx+1Ch], 1
0x1800053f9  jz      short loc_18000541A
0x1800053fb  cmp     byte ptr [rcx+19h], 2
0x1800053ff  jb      short loc_18000541A
0x180005401  mov     edx, 12h
0x180005406  lea     r9d, [rdx+45h]
0x18000540a  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x180005411  mov     rcx, [rcx+10h]
0x180005415  call    WPP_SF_D
0x18000541a  mov     r9d, 0D5h; int
0x180005420  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x180005427  lea     edx, [r9-7Eh]; unsigned int
0x18000542b  lea     rcx, [rsp+128h+var_88]; this
0x180005433  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x180005438  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000543f  lea     rcx, [rsp+128h+var_88]; pExceptionObject
0x180005447  call    _CxxThrowException_0
0x18000544c  lea     rax, WPP_GLOBAL_Control
0x180005453  mov     rcx, cs:WPP_GLOBAL_Control
0x18000545a  cmp     rcx, rax
0x18000545d  jz      short loc_180005484
0x18000545f  test    byte ptr [rcx+1Ch], 1
0x180005463  jz      short loc_180005484
0x180005465  cmp     byte ptr [rcx+19h], 2
0x180005469  jb      short loc_180005484
0x18000546b  mov     edx, 13h
0x180005470  lea     r9d, [rdx+44h]
0x180005474  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x18000547b  mov     rcx, [rcx+10h]
0x18000547f  call    WPP_SF_D
0x180005484  mov     r9d, 0D8h; int
0x18000548a  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x180005491  mov     edx, 57h ; 'W'; unsigned int
0x180005496  lea     rcx, [rsp+128h+var_50]; this
0x18000549e  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x1800054a3  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800054aa  lea     rcx, [rsp+128h+var_50]; pExceptionObject
0x1800054b2  call    _CxxThrowException_0
```
