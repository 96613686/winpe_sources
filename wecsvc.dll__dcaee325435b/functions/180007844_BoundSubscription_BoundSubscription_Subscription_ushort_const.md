# BoundSubscription::BoundSubscription(Subscription &,ushort const *)

- ea: `0x180007844`
- end: `0x180007b5b`
- name: `??0BoundSubscription@@QEAA@AEAVSubscription@@PEBG@Z`
- size: `791`
- prototype: `BoundSubscription *__fastcall(BoundSubscription *__hidden this, struct Subscription *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180009170`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003be8`
- `0x18000669c`
- `0x180007844`
- `0x180007e10`
- `0x18000e01c`
- `0x180012424`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800079e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800079e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007889`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007889`

## string_xrefs

- `0x180007a49`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BoundSubscription *__fastcall BoundSubscription::BoundSubscription(
        BoundSubscription *this,
        struct Subscription *a2,
        const unsigned __int16 *a3)
{
  unsigned int *v6; // rsi
  unsigned int *v7; // r14
  _DWORD *v8; // rbx
  HANDLE EventW; // rax
  DWORD LastError; // ebx
  unsigned int v11; // eax
  _BYTE v13[16]; // [rsp+20h] [rbp-58h] BYREF
  HKEY v14; // [rsp+30h] [rbp-48h]
  void **pExceptionObject; // [rsp+38h] [rbp-40h] BYREF
  char v16; // [rsp+40h] [rbp-38h]
  const char *v17; // [rsp+48h] [rbp-30h]
  __int64 v18; // [rsp+50h] [rbp-28h]
  __int64 v19; // [rsp+58h] [rbp-20h]
  DWORD v20; // [rsp+60h] [rbp-18h]
  int v21; // [rsp+64h] [rbp-14h]
  int v22; // [rsp+68h] [rbp-10h]

  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &BoundSubscription::`vftable';
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 16), 0, 0);
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = a2;
  *((_QWORD *)this + 12) = 7;
  *((_QWORD *)this + 11) = 0;
  *((_WORD *)this + 36) = 0;
  *((_QWORD *)this + 16) = 7;
  *((_QWORD *)this + 15) = 0;
  *((_WORD *)this + 52) = 0;
  *((_QWORD *)this + 20) = 7;
  *((_QWORD *)this + 19) = 0;
  *((_WORD *)this + 68) = 0;
  *((_DWORD *)this + 42) = 1;
  *((_DWORD *)this + 45) = 0;
  *((_QWORD *)this + 26) = 7;
  *((_QWORD *)this + 25) = 0;
  *((_WORD *)this + 92) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_DWORD *)this + 62) = 0;
  v6 = (unsigned int *)((char *)this + 256);
  *((_DWORD *)this + 64) = 3600000;
  v7 = (unsigned int *)((char *)this + 260);
  *((_DWORD *)this + 65) = 300000;
  *((_DWORD *)this + 66) = 72;
  *((_QWORD *)this + 34) = 0;
  v8 = (_DWORD *)((char *)this + 280);
  *((_DWORD *)this + 70) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 96) = 0;
  *((_QWORD *)this + 53) = 7;
  *((_QWORD *)this + 52) = 0;
  *((_WORD *)this + 200) = 0;
  *((_QWORD *)this + 57) = 7;
  *((_QWORD *)this + 56) = 0;
  *((_WORD *)this + 216) = 0;
  *((_QWORD *)this + 61) = 7;
  *((_QWORD *)this + 60) = 0;
  *((_WORD *)this + 232) = 0;
  *((_DWORD *)this + 124) = 0;
  if ( a3 )
    std::wstring::assign((char *)this + 72, a3);
  NormalizeLocalComputerName(a3, (char *)this + 104);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 29) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
    }
    v16 = 0;
    v17 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v18 = 0;
    v19 = 0;
    v20 = LastError;
    v21 = -1;
    v22 = 1140;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  *((_QWORD *)this + 38) = 0;
  *(_OWORD *)((char *)this + 328) = 0;
  *(_OWORD *)((char *)this + 344) = 0;
  *(_QWORD *)((char *)this + 388) = 0;
  *((_DWORD *)this + 99) = 0;
  *(_QWORD *)((char *)this + 500) = 0;
  SubscriptionGlobalsReader::SubscriptionGlobalsReader((SubscriptionGlobalsReader *)v13);
  RegReadDWORDValue(v14, L"RetryInterval", (unsigned int *)this + 64);
  RegReadDWORDValue(v14, L"RetryIntervalStart", (unsigned int *)this + 65);
  v11 = 1000;
  if ( *v7 >= 0x3E8 )
    v11 = *v7;
  else
    *v7 = 1000;
  if ( *v6 < v11 )
    *v6 = v11;
  *((_DWORD *)this + 63) = v11;
  RegReadDWORDValue(v14, L"RetryCount", (unsigned int *)this + 66);
  RegReadDWORDValue(v14, L"InactiveESCleanupMaxMinute", (unsigned int *)this + 70);
  if ( *v8 > 0x1179Eu )
    *v8 = 71582;
  *((_DWORD *)this + 71) = 0;
  ConfigBase::~ConfigBase((ConfigBase *)v13);
  return this;
}

```

## disassembly

```asm
0x180007844  mov     [rsp-40h+arg_0], rcx
0x180007849  push    rbp
0x18000784a  push    rbx
0x18000784b  push    rsi
0x18000784c  push    rdi
0x18000784d  push    r12
0x18000784f  push    r13
0x180007851  push    r14
0x180007853  push    r15
0x180007855  mov     rbp, rsp
0x180007858  sub     rsp, 78h
0x18000785c  mov     r15, r8
0x18000785f  mov     rbx, rdx
0x180007862  mov     rdi, rcx
0x180007865  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x18000786c  mov     [rcx], rax
0x18000786f  xor     r12d, r12d
0x180007872  mov     [rcx+8], r12d
0x180007876  lea     rax, ??_7BoundSubscription@@6B@; const BoundSubscription::`vftable'
0x18000787d  mov     [rcx], rax
0x180007880  add     rcx, 10h; lpCriticalSection
0x180007884  xor     r8d, r8d; Flags
0x180007887  xor     edx, edx; dwSpinCount
0x180007889  call    cs:__imp_InitializeCriticalSectionEx
0x18000788f  nop
0x180007890  xor     r8d, r8d
0x180007893  mov     [rdi+38h], r8d
0x180007897  mov     [rdi+40h], rbx
0x18000789b  lea     rcx, [rdi+48h]
0x18000789f  lea     edx, [r12+7]
0x1800078a4  mov     [rcx+18h], rdx
0x1800078a8  mov     [rcx+10h], r8
0x1800078ac  mov     [rcx], r8w
0x1800078b0  mov     [rdi+80h], rdx
0x1800078b7  mov     [rdi+78h], r8
0x1800078bb  mov     [rdi+68h], r8w
0x1800078c0  mov     [rdi+0A0h], rdx
0x1800078c7  mov     [rdi+98h], r8
0x1800078ce  mov     [rdi+88h], r8w
0x1800078d6  mov     dword ptr [rdi+0A8h], 1
0x1800078e0  mov     [rdi+0B4h], r8d
0x1800078e7  mov     [rdi+0D0h], rdx
0x1800078ee  mov     [rdi+0C8h], r8
0x1800078f5  mov     [rdi+0B8h], r8w
0x1800078fd  mov     [rdi+0D8h], r8
0x180007904  mov     [rdi+0E0h], r8
0x18000790b  mov     [rdi+0E8h], r8
0x180007912  mov     [rdi+0F0h], r8
0x180007919  mov     [rdi+0F8h], r8d
0x180007920  lea     rsi, [rdi+100h]
0x180007927  mov     dword ptr [rsi], 36EE80h
0x18000792d  lea     r14, [rdi+104h]
0x180007934  mov     dword ptr [r14], 493E0h
0x18000793b  lea     r13, [rdi+108h]
0x180007942  mov     dword ptr [r13+0], 48h ; 'H'
0x18000794a  mov     [rdi+110h], r8
0x180007951  lea     rbx, [rdi+118h]
0x180007958  mov     [rbx], r8d
0x18000795b  mov     [rdi+120h], r8
0x180007962  mov     [rdi+128h], r8
0x180007969  mov     [rdi+178h], r8
0x180007970  mov     [rdi+180h], r8d
0x180007977  mov     [rdi+1A8h], rdx
0x18000797e  mov     [rdi+1A0h], r8
0x180007985  mov     [rdi+190h], r8w
0x18000798d  mov     [rdi+1C8h], rdx
0x180007994  mov     [rdi+1C0h], r8
0x18000799b  mov     [rdi+1B0h], r8w
0x1800079a3  mov     [rdi+1E8h], rdx
0x1800079aa  mov     [rdi+1E0h], r8
0x1800079b1  mov     [rdi+1D0h], r8w
0x1800079b9  mov     [rdi+1F0h], r8d
0x1800079c0  test    r15, r15
0x1800079c3  jz      short loc_1800079CD
0x1800079c5  mov     rdx, r15
0x1800079c8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800079cd  lea     rdx, [rdi+68h]
0x1800079d1  mov     rcx, r15
0x1800079d4  call    NormalizeLocalComputerName
0x1800079d9  xor     r9d, r9d; lpName
0x1800079dc  xor     r8d, r8d; bInitialState
0x1800079df  xor     edx, edx; bManualReset
0x1800079e1  xor     ecx, ecx; lpEventAttributes
0x1800079e3  call    cs:__imp_CreateEventW
0x1800079e9  mov     [rdi+0E8h], rax
0x1800079f0  xor     r12d, r12d
0x1800079f3  test    rax, rax
0x1800079f6  jnz     loc_180007A89
0x1800079fc  call    cs:__imp_GetLastError
0x180007a02  mov     ebx, eax
0x180007a04  mov     eax, 507h
0x180007a09  test    ebx, ebx
0x180007a0b  cmovz   ebx, eax
0x180007a0e  lea     rax, WPP_GLOBAL_Control
0x180007a15  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a1c  cmp     rcx, rax
0x180007a1f  jz      short loc_180007A45
0x180007a21  test    byte ptr [rcx+1Ch], 10h
0x180007a25  jz      short loc_180007A45
0x180007a27  cmp     byte ptr [rcx+19h], 2
0x180007a2b  jb      short loc_180007A45
0x180007a2d  lea     edx, [r12+1Fh]
0x180007a32  mov     r9d, ebx
0x180007a35  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x180007a3c  mov     rcx, [rcx+10h]
0x180007a40  call    WPP_SF_D
0x180007a45  mov     [rbp+var_38], r12b
0x180007a49  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x180007a50  mov     [rbp+var_30], rax
0x180007a54  mov     [rbp+var_28], r12
0x180007a58  mov     [rbp+var_20], r12
0x180007a5c  mov     [rbp+var_18], ebx
0x180007a5f  mov     [rbp+var_14], 0FFFFFFFFh
0x180007a66  mov     [rbp+var_10], 474h
0x180007a6d  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180007a74  mov     [rbp+pExceptionObject], rax
0x180007a78  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180007a7f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007a83  call    _CxxThrowException_0
0x180007a89  xor     eax, eax
0x180007a8b  mov     [rdi+130h], rax
0x180007a92  xorps   xmm0, xmm0
0x180007a95  movups  xmmword ptr [rdi+148h], xmm0
0x180007a9c  movups  xmmword ptr [rdi+158h], xmm0
0x180007aa3  mov     [rdi+184h], rax
0x180007aaa  mov     [rdi+18Ch], eax
0x180007ab0  mov     [rdi+1F4h], rax
0x180007ab7  lea     rcx, [rbp+var_58]; this
0x180007abb  call    ??0SubscriptionGlobalsReader@@QEAA@XZ; SubscriptionGlobalsReader::SubscriptionGlobalsReader(void)
0x180007ac0  nop
0x180007ac1  mov     r8, rsi; unsigned int *
0x180007ac4  lea     rdx, aRetryinterval; "RetryInterval"
0x180007acb  mov     rcx, [rbp+var_48]; HKEY
0x180007acf  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180007ad4  mov     r8, r14; unsigned int *
0x180007ad7  lea     rdx, aRetryintervals; "RetryIntervalStart"
0x180007ade  mov     rcx, [rbp+var_48]; HKEY
0x180007ae2  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180007ae7  mov     eax, 3E8h
0x180007aec  cmp     [r14], eax
0x180007aef  jnb     short loc_180007AF6
0x180007af1  mov     [r14], eax
0x180007af4  jmp     short loc_180007AF9
0x180007af6  mov     eax, [r14]
0x180007af9  cmp     [rsi], eax
0x180007afb  jnb     short loc_180007AFF
0x180007afd  mov     [rsi], eax
0x180007aff  mov     [rdi+0FCh], eax
0x180007b05  mov     r8, r13; unsigned int *
0x180007b08  lea     rdx, aRetrycount; "RetryCount"
0x180007b0f  mov     rcx, [rbp+var_48]; HKEY
0x180007b13  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180007b18  mov     r8, rbx; unsigned int *
0x180007b1b  lea     rdx, aInactiveesclea; "InactiveESCleanupMaxMinute"
0x180007b22  mov     rcx, [rbp+var_48]; HKEY
0x180007b26  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180007b2b  mov     eax, 1179Eh
0x180007b30  cmp     [rbx], eax
0x180007b32  jbe     short loc_180007B36
0x180007b34  mov     [rbx], eax
0x180007b36  mov     [rdi+11Ch], r12d
0x180007b3d  lea     rcx, [rbp+var_58]; this
0x180007b41  call    ??1ConfigBase@@UEAA@XZ; ConfigBase::~ConfigBase(void)
0x180007b46  nop
0x180007b47  mov     rax, rdi
0x180007b4a  add     rsp, 78h
0x180007b4e  pop     r15
0x180007b50  pop     r14
0x180007b52  pop     r13
0x180007b54  pop     r12
0x180007b56  pop     rdi
0x180007b57  pop     rsi
0x180007b58  pop     rbx
0x180007b59  pop     rbp
0x180007b5a  retn
```
