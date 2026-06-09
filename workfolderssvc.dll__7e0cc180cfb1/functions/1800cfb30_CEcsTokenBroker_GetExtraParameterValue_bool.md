# CEcsTokenBroker::GetExtraParameterValue(bool)

- ea: `0x1800cfb30`
- end: `0x1800cfce5`
- name: `?GetExtraParameterValue@CEcsTokenBroker@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800ce8cc`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180009384`
- `0x180011314`
- `0x180015150`
- `0x1800158d4`
- `0x180023c90`
- `0x18002d664`
- `0x180047d84`
- `0x180047db0`
- `0x1800cfb30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800cfcad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800cfcad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cfc7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cfc7a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800cfbfb`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800cfbfb`

## string_xrefs

- `0x1800cfbc4`: `CEcsTokenBroker::GetExtraParameterValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CEcsTokenBroker::GetExtraParameterValue(__int64 a1, char a2)
{
  _BYTE *v4; // rax
  char v5; // cl
  HRESULT v6; // eax
  __int64 v7; // rax
  HRESULT pExceptionObject; // [rsp+24h] [rbp-15h] BYREF
  HRESULT v10; // [rsp+28h] [rbp-11h] BYREF
  int v11; // [rsp+2Ch] [rbp-Dh]
  char v12; // [rsp+30h] [rbp-9h]
  const char *v13; // [rsp+38h] [rbp-1h]
  __int64 v14; // [rsp+40h] [rbp+7h]
  __int64 v15; // [rsp+48h] [rbp+Fh]
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+17h] BYREF
  char v17; // [rsp+58h] [rbp+1Fh]
  GUID pguid; // [rsp+70h] [rbp+37h] BYREF

  v15 = a1;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, &WPP_8c5b6bd21cdc370d89616d2bd57ae836_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 2) != 0 && v4[65] >= 6u )
  {
    v5 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v5 = 0;
LABEL_9:
  v10 = 0;
  v11 = 423;
  v12 = v5;
  v13 = "CEcsTokenBroker::GetExtraParameterValue";
  v14 = 0;
  std::wstring::wstring(a1);
  if ( a2 )
  {
    pguid = 0;
    v6 = CoCreateGuid(&pguid);
    v10 = v6;
    if ( v6 < 0 )
    {
      HIWORD(v11) = 430;
      pExceptionObject = v6;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v11) = 430;
    v7 = CEcsGuid::ToString(&SRWLock, &pguid);
    std::wstring::operator=(a1, v7);
    std::wstring::~wstring(&SRWLock);
    CEcsExclusiveLock<CEcsSrwLock>::CEcsExclusiveLock<CEcsSrwLock>(&SRWLock, &CEcsTokenBroker::s_srwLock);
    std::wstring::operator=(CEcsTokenBroker::s_strExtraParamValue, a1);
    if ( v17 )
    {
      ReleaseSRWLockExclusive(SRWLock);
LABEL_16:
      v17 = 0;
    }
  }
  else
  {
    CEcsSharedLock<CEcsSrwLock>::CEcsSharedLock<CEcsSrwLock>(&SRWLock, &CEcsTokenBroker::s_srwLock);
    std::wstring::operator=(a1, CEcsTokenBroker::s_strExtraParamValue);
    if ( v17 )
    {
      ReleaseSRWLockShared(SRWLock);
      goto LABEL_16;
    }
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v10);
  return a1;
}

```

## disassembly

```asm
0x1800cfb30  mov     [rsp-8+arg_8], rbx
0x1800cfb35  mov     [rsp-8+arg_10], rdi
0x1800cfb3a  push    rbp
0x1800cfb3b  lea     rbp, [rsp-57h]
0x1800cfb40  sub     rsp, 90h
0x1800cfb47  mov     rax, cs:__security_cookie
0x1800cfb4e  xor     rax, rsp
0x1800cfb51  mov     [rbp+57h+var_10], rax
0x1800cfb55  mov     dil, dl
0x1800cfb58  mov     rbx, rcx
0x1800cfb5b  mov     [rbp+57h+var_48], rcx
0x1800cfb5f  mov     [rbp+57h+var_70], 0
0x1800cfb66  lea     rcx, WPP_GLOBAL_Control
0x1800cfb6d  mov     rax, cs:WPP_GLOBAL_Control
0x1800cfb74  cmp     rax, rcx
0x1800cfb77  jz      short loc_1800CFBA1
0x1800cfb79  test    byte ptr [rax+44h], 2
0x1800cfb7d  jz      short loc_1800CFBB1
0x1800cfb7f  cmp     byte ptr [rax+41h], 6
0x1800cfb83  jb      short loc_1800CFBA1
0x1800cfb85  mov     edx, 1Ah
0x1800cfb8a  lea     r8, WPP_8c5b6bd21cdc370d89616d2bd57ae836_Traceguids
0x1800cfb91  mov     rcx, [rax+38h]
0x1800cfb95  call    WPP_SF_
0x1800cfb9a  mov     rax, cs:WPP_GLOBAL_Control
0x1800cfba1  test    byte ptr [rax+44h], 2
0x1800cfba5  jz      short loc_1800CFBB1
0x1800cfba7  cmp     byte ptr [rax+41h], 6
0x1800cfbab  jb      short loc_1800CFBB1
0x1800cfbad  mov     cl, 1
0x1800cfbaf  jmp     short loc_1800CFBB3
0x1800cfbb1  xor     cl, cl
0x1800cfbb3  mov     [rbp+57h+var_68], 0
0x1800cfbba  mov     [rbp+57h+var_64], 1A7h
0x1800cfbc1  mov     [rbp+57h+var_60], cl
0x1800cfbc4  lea     rax, aCecstokenbroke; "CEcsTokenBroker::GetExtraParameterValue"
0x1800cfbcb  mov     [rbp+57h+var_58], rax
0x1800cfbcf  mov     [rbp+57h+var_50], 0
0x1800cfbd7  mov     rcx, rbx
0x1800cfbda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cfbdf  mov     [rbp+57h+var_70], 1
0x1800cfbe6  test    dil, dil
0x1800cfbe9  jz      loc_1800CFC82
0x1800cfbef  xorps   xmm0, xmm0
0x1800cfbf2  movdqa  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800cfbf7  lea     rcx, [rbp+57h+pguid]; pguid
0x1800cfbfb  call    cs:__imp_CoCreateGuid
0x1800cfc01  mov     [rbp+57h+var_68], eax
0x1800cfc04  mov     [rbp+57h+var_68], eax
0x1800cfc07  mov     ecx, 1AEh
0x1800cfc0c  test    eax, eax
0x1800cfc0e  jns     short loc_1800CFC28
0x1800cfc10  mov     word ptr [rbp+57h+var_64+2], cx
0x1800cfc14  mov     [rbp+57h+pExceptionObject], eax
0x1800cfc17  lea     rdx, _TI1J; pThrowInfo
0x1800cfc1e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800cfc22  call    _CxxThrowException_0
0x1800cfc28  mov     word ptr [rbp+57h+var_64], cx
0x1800cfc2c  lea     rdx, [rbp+57h+pguid]
0x1800cfc30  lea     rcx, [rbp+57h+SRWLock]
0x1800cfc34  call    ?ToString@CEcsGuid@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; CEcsGuid::ToString(_GUID const &)
0x1800cfc39  nop
0x1800cfc3a  mov     rdx, rax
0x1800cfc3d  mov     rcx, rbx
0x1800cfc40  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cfc45  nop
0x1800cfc46  lea     rcx, [rbp+57h+SRWLock]
0x1800cfc4a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cfc4f  lea     rdx, ?s_srwLock@CEcsTokenBroker@@0VCEcsSrwLock@@A; CEcsSrwLock CEcsTokenBroker::s_srwLock
0x1800cfc56  lea     rcx, [rbp+57h+SRWLock]
0x1800cfc5a  call    ??0?$CEcsExclusiveLock@VCEcsSrwLock@@@@QEAA@AEAVCEcsSrwLock@@_N@Z; CEcsExclusiveLock<CEcsSrwLock>::CEcsExclusiveLock<CEcsSrwLock>(CEcsSrwLock &,bool)
0x1800cfc5f  nop
0x1800cfc60  mov     rdx, rbx
0x1800cfc63  lea     rcx, ?s_strExtraParamValue@CEcsTokenBroker@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CEcsTokenBroker::s_strExtraParamValue
0x1800cfc6a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800cfc6f  nop
0x1800cfc70  cmp     [rbp+57h+var_38], 0
0x1800cfc74  jz      short loc_1800CFCB7
0x1800cfc76  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800cfc7a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cfc80  jmp     short loc_1800CFCB3
0x1800cfc82  lea     rdx, ?s_srwLock@CEcsTokenBroker@@0VCEcsSrwLock@@A; CEcsSrwLock CEcsTokenBroker::s_srwLock
0x1800cfc89  lea     rcx, [rbp+57h+SRWLock]
0x1800cfc8d  call    ??0?$CEcsSharedLock@VCEcsSrwLock@@@@QEAA@AEAVCEcsSrwLock@@_N@Z; CEcsSharedLock<CEcsSrwLock>::CEcsSharedLock<CEcsSrwLock>(CEcsSrwLock &,bool)
0x1800cfc92  nop
0x1800cfc93  lea     rdx, ?s_strExtraParamValue@CEcsTokenBroker@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CEcsTokenBroker::s_strExtraParamValue
0x1800cfc9a  mov     rcx, rbx
0x1800cfc9d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800cfca2  nop
0x1800cfca3  cmp     [rbp+57h+var_38], 0
0x1800cfca7  jz      short loc_1800CFCB7
0x1800cfca9  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800cfcad  call    cs:__imp_ReleaseSRWLockShared
0x1800cfcb3  mov     [rbp+57h+var_38], 0
0x1800cfcb7  lea     rcx, [rbp+57h+var_68]; this
0x1800cfcbb  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800cfcc0  mov     rax, rbx
0x1800cfcc3  mov     rcx, [rbp+57h+var_10]
0x1800cfcc7  xor     rcx, rsp; StackCookie
0x1800cfcca  call    __security_check_cookie
0x1800cfccf  lea     r11, [rsp+90h+var_s0]
0x1800cfcd7  mov     rbx, [r11+18h]
0x1800cfcdb  mov     rdi, [r11+20h]
0x1800cfcdf  mov     rsp, r11
0x1800cfce2  pop     rbp
0x1800cfce3  retn
```
