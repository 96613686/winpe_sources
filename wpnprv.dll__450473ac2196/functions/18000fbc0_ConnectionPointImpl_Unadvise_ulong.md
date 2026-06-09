# ConnectionPointImpl::Unadvise(ulong)

- ea: `0x18000fbc0`
- end: `0x18000fdd4`
- name: `?Unadvise@ConnectionPointImpl@@UEAAJK@Z`
- size: `532`
- prototype: `__int64 __fastcall(ConnectionPointImpl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000fbc0`
- `0x18000fddc`
- `0x18000fe54`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fcf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fd8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fcf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fd8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fc26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fc26`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18000fce2`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18000fce2`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000fc55`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000fc55`

## string_xrefs

- `0x18000fc96`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionpointimpl.cpp`
- `0x18000fd4f`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionpointimpl.cpp`

## pseudocode

```c
__int64 __fastcall ConnectionPointImpl::Unadvise(ConnectionPointImpl *this, unsigned int a2)
{
  __int64 v4; // rsi
  HRESULT ApartmentType; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  APTTYPE pAptType; // [rsp+50h] [rbp+8h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_38e46b42a633320096f95707e4b470ab_Traceguids, a2);
  }
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !*((_DWORD *)this + 18) || *((_DWORD *)this + 18) != a2 )
  {
    v6 = -2147467261;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_38e46b42a633320096f95707e4b470ab_Traceguids, 2147500035LL);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionpointimpl.cpp",
      (const char *)0x80004003LL,
      v11);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_28;
    v8 = 32;
    v9 = 2147500035LL;
    goto LABEL_27;
  }
  v4 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  v6 = ApartmentType;
  if ( ApartmentType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_38e46b42a633320096f95707e4b470ab_Traceguids,
        (unsigned int)ApartmentType);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionpointimpl.cpp",
      (const char *)v6,
      v11);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_28;
    v8 = 34;
    v9 = v6;
LABEL_27:
    WPP_SF_d(v7[2], v8, &WPP_38e46b42a633320096f95707e4b470ab_Traceguids, v9);
LABEL_28:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    goto LABEL_29;
  }
  while ( pAptType == APTTYPE_MTA && *((int *)this + 22) > 0 )
    SleepConditionVariableCS((PCONDITION_VARIABLE)this + 10, (PCRITICAL_SECTION)((char *)this + 16), 0xFFFFFFFF);
  *((_DWORD *)this + 18) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
LABEL_29:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_38e46b42a633320096f95707e4b470ab_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18000fbc0  mov     [rsp+arg_8], rbx
0x18000fbc5  push    rbp
0x18000fbc6  push    rsi
0x18000fbc7  push    rdi
0x18000fbc8  push    r12
0x18000fbca  push    r13; int
0x18000fbcc  sub     rsp, 20h
0x18000fbd0  mov     ebx, edx
0x18000fbd2  mov     rdi, rcx
0x18000fbd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbdc  lea     r12, WPP_GLOBAL_Control
0x18000fbe3  lea     r13, WPP_38e46b42a633320096f95707e4b470ab_Traceguids
0x18000fbea  cmp     rcx, r12
0x18000fbed  jz      short loc_18000FC0F
0x18000fbef  test    byte ptr [rcx+1Ch], 1
0x18000fbf3  jz      short loc_18000FC0F
0x18000fbf5  cmp     byte ptr [rcx+19h], 6
0x18000fbf9  jb      short loc_18000FC0F
0x18000fbfb  mov     rcx, [rcx+10h]
0x18000fbff  mov     edx, 1Eh
0x18000fc04  mov     r9d, ebx
0x18000fc07  mov     r8, r13
0x18000fc0a  call    WPP_SF_d
0x18000fc0f  lea     rbp, [rdi+10h]
0x18000fc13  mov     [rsp+48h+pAptType], 0
0x18000fc1b  mov     rcx, rbp; lpCriticalSection
0x18000fc1e  mov     [rsp+48h+pAptQualifier], 0
0x18000fc26  call    cs:__imp_EnterCriticalSection
0x18000fc2c  cmp     dword ptr [rdi+48h], 0
0x18000fc30  jz      loc_18000FD19
0x18000fc36  cmp     [rdi+48h], ebx
0x18000fc39  jnz     loc_18000FD19
0x18000fc3f  mov     rsi, [rdi+40h]
0x18000fc43  lea     rdx, [rsp+48h+pAptQualifier]; pAptQualifier
0x18000fc48  lea     rcx, [rsp+48h+pAptType]; pAptType
0x18000fc4d  mov     qword ptr [rdi+40h], 0
0x18000fc55  call    cs:__imp_CoGetApartmentType
0x18000fc5b  mov     ebx, eax
0x18000fc5d  test    eax, eax
0x18000fc5f  jns     loc_18000FCE8
0x18000fc65  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc6c  cmp     rcx, r12
0x18000fc6f  jz      short loc_18000FC91
0x18000fc71  test    byte ptr [rcx+1Ch], 1
0x18000fc75  jz      short loc_18000FC91
0x18000fc77  cmp     byte ptr [rcx+19h], 2
0x18000fc7b  jb      short loc_18000FC91
0x18000fc7d  mov     rcx, [rcx+10h]
0x18000fc81  mov     edx, 21h ; '!'
0x18000fc86  mov     r9d, eax
0x18000fc89  mov     r8, r13
0x18000fc8c  call    WPP_SF_d
0x18000fc91  mov     rcx, [rsp+48h]; this
0x18000fc96  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000fc9d  mov     r9d, ebx; char *
0x18000fca0  mov     edx, 0FDh; void *
0x18000fca5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fcaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcb1  cmp     rcx, r12
0x18000fcb4  jz      loc_18000FD8C
0x18000fcba  test    byte ptr [rcx+1Ch], 80h
0x18000fcbe  jz      loc_18000FD8C
0x18000fcc4  mov     edx, 22h ; '"'
0x18000fcc9  mov     r9d, ebx
0x18000fccc  jmp     loc_18000FD80
0x18000fcd1  cmp     dword ptr [rdi+58h], 0
0x18000fcd5  jle     short loc_18000FCEF
0x18000fcd7  lea     rcx, [rdi+50h]; ConditionVariable
0x18000fcdb  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18000fcdf  mov     rdx, rbp; CriticalSection
0x18000fce2  call    cs:__imp_SleepConditionVariableCS
0x18000fce8  cmp     [rsp+48h+pAptType], 1
0x18000fced  jz      short loc_18000FCD1
0x18000fcef  mov     rcx, rbp; lpCriticalSection
0x18000fcf2  mov     dword ptr [rdi+48h], 0
0x18000fcf9  call    cs:__imp_LeaveCriticalSection
0x18000fcff  test    rsi, rsi
0x18000fd02  jz      loc_18000FD95
0x18000fd08  mov     rax, [rsi]
0x18000fd0b  mov     rcx, rsi
0x18000fd0e  mov     rax, [rax+10h]
0x18000fd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd17  jmp     short loc_18000FD95
0x18000fd19  mov     ebx, 80004003h
0x18000fd1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd25  cmp     rcx, r12
0x18000fd28  jz      short loc_18000FD4A
0x18000fd2a  test    byte ptr [rcx+1Ch], 1
0x18000fd2e  jz      short loc_18000FD4A
0x18000fd30  cmp     byte ptr [rcx+19h], 2
0x18000fd34  jb      short loc_18000FD4A
0x18000fd36  mov     rcx, [rcx+10h]
0x18000fd3a  mov     edx, 1Fh
0x18000fd3f  mov     r9d, ebx
0x18000fd42  mov     r8, r13
0x18000fd45  call    WPP_SF_d
0x18000fd4a  mov     rcx, [rsp+48h]; this
0x18000fd4f  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000fd56  mov     r9d, ebx; char *
0x18000fd59  mov     edx, 0F4h; void *
0x18000fd5e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fd63  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd6a  cmp     rcx, r12
0x18000fd6d  jz      short loc_18000FD8C
0x18000fd6f  test    byte ptr [rcx+1Ch], 80h
0x18000fd73  jz      short loc_18000FD8C
0x18000fd75  mov     edx, 20h ; ' '
0x18000fd7a  mov     r9d, 80004003h
0x18000fd80  mov     rcx, [rcx+10h]
0x18000fd84  mov     r8, r13
0x18000fd87  call    WPP_SF_d
0x18000fd8c  mov     rcx, rbp; lpCriticalSection
0x18000fd8f  call    cs:__imp_LeaveCriticalSection
0x18000fd95  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd9c  cmp     rcx, r12
0x18000fd9f  jz      short loc_18000FDC1
0x18000fda1  test    byte ptr [rcx+1Ch], 1
0x18000fda5  jz      short loc_18000FDC1
0x18000fda7  cmp     byte ptr [rcx+19h], 6
0x18000fdab  jb      short loc_18000FDC1
0x18000fdad  mov     rcx, [rcx+10h]
0x18000fdb1  mov     edx, 23h ; '#'
0x18000fdb6  mov     r9d, ebx
0x18000fdb9  mov     r8, r13
0x18000fdbc  call    WPP_SF_d
0x18000fdc1  mov     eax, ebx
0x18000fdc3  mov     rbx, [rsp+48h+arg_8]
0x18000fdc8  add     rsp, 20h
0x18000fdcc  pop     r13
0x18000fdce  pop     r12
0x18000fdd0  pop     rdi
0x18000fdd1  pop     rsi
0x18000fdd2  pop     rbp
0x18000fdd3  retn
```
