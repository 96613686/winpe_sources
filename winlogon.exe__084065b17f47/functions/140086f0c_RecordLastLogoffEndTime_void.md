# RecordLastLogoffEndTime(void)

- ea: `0x140086f0c`
- end: `0x14008712e`
- name: `?RecordLastLogoffEndTime@@YAXXZ`
- size: `546`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400877f0`

## callees

- `0x140031890`
- `0x140039638`
- `0x140041c34`
- `0x140044800`
- `0x14004eb98`
- `0x140053720`
- `0x14005f3c4`
- `0x140086f0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140086ff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140086ff9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140087059`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140087059`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140086f90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140086f90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14008710c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14008710c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140086fef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140086fef`

## pseudocode

```c
void __fastcall RecordLastLogoffEndTime(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  LSTATUS v4; // eax
  CUser *v5; // rcx
  int v6; // edx
  const WCHAR *v7; // r9
  LSTATUS v8; // eax
  int v9; // r9d
  __int64 cbData; // [rsp+28h] [rbp-38h]
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-20h] BYREF
  __int128 v14; // [rsp+48h] [rbp-18h] BYREF

  hKey = 0;
  PerformanceCount.QuadPart = 0;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_ea968c137b9e31d540c842f1a896af1c_Traceguids, a4);
  }
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
         0,
         0x20006u,
         &hKey);
  if ( !v4 )
  {
    if ( QueryPerformanceCounter(&PerformanceCount) )
    {
      v8 = RegSetValueExW(hKey, L"LastLogOffEndTimePerfCounter", 0, 0xBu, (const BYTE *)&PerformanceCount, 8u);
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LODWORD(cbData) = v8;
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            62,
            (unsigned int)WPP_ea968c137b9e31d540c842f1a896af1c_Traceguids,
            (unsigned int)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            (__int64)L"LastLogOffEndTimePerfCounter",
            cbData);
        }
      }
      else
      {
        v14 = 0;
        WLGetTSActivityId(&v14);
        if ( (unsigned int)dword_1400CF778 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
        {
          v13 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1400CF778,
            (unsigned int)byte_1400BD7DD,
            (unsigned int)&v14,
            v9,
            (__int64)&v13);
        }
      }
      goto LABEL_24;
    }
    LOBYTE(v4) = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_24:
      if ( hKey )
        RegCloseKey(hKey);
      return;
    }
    v6 = 61;
    v7 = L"LastLogOffEndTimePerfCounter";
LABEL_10:
    WPP_SF_SD(*((_QWORD *)v5 + 2), v6, (unsigned int)WPP_ea968c137b9e31d540c842f1a896af1c_Traceguids, (_DWORD)v7, v4);
    goto LABEL_24;
  }
  hKey = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 60;
    v7 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon";
    goto LABEL_10;
  }
}

```

## disassembly

```asm
0x140086f0c  mov     [rsp-8+arg_0], rbx
0x140086f11  mov     [rsp-8+arg_8], r14
0x140086f16  push    rbp
0x140086f17  mov     rbp, rsp
0x140086f1a  sub     rsp, 60h
0x140086f1e  mov     rax, cs:__security_cookie
0x140086f25  xor     rax, rsp
0x140086f28  mov     [rbp+var_8], rax
0x140086f2c  mov     [rbp+hKey], 0
0x140086f34  mov     qword ptr [rbp+PerformanceCount], 0
0x140086f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140086f43  lea     r14, WPP_GLOBAL_Control
0x140086f4a  cmp     rcx, r14
0x140086f4d  jz      short loc_140086F70
0x140086f4f  test    byte ptr [rcx+1Ch], 1
0x140086f53  jz      short loc_140086F70
0x140086f55  cmp     byte ptr [rcx+19h], 5
0x140086f59  jb      short loc_140086F70
0x140086f5b  mov     rcx, [rcx+10h]
0x140086f5f  lea     r8, WPP_ea968c137b9e31d540c842f1a896af1c_Traceguids
0x140086f66  mov     edx, 3Bh ; ';'
0x140086f6b  call    WPP_SF_
0x140086f70  lea     rax, [rbp+hKey]
0x140086f74  mov     r9d, 20006h; samDesired
0x140086f7a  xor     r8d, r8d; ulOptions
0x140086f7d  mov     [rsp+60h+phkResult], rax; phkResult
0x140086f82  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x140086f89  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140086f90  call    cs:__imp_RegOpenKeyExW
0x140086f96  test    eax, eax
0x140086f98  jz      short loc_140086FEB
0x140086f9a  mov     [rbp+hKey], 0
0x140086fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x140086fa9  cmp     rcx, r14
0x140086fac  jz      loc_140087112
0x140086fb2  test    byte ptr [rcx+1Ch], 1
0x140086fb6  jz      loc_140087112
0x140086fbc  cmp     byte ptr [rcx+19h], 2
0x140086fc0  jb      loc_140087112
0x140086fc6  mov     edx, 3Ch ; '<'
0x140086fcb  lea     r9, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x140086fd2  mov     rcx, [rcx+10h]
0x140086fd6  lea     r8, WPP_ea968c137b9e31d540c842f1a896af1c_Traceguids
0x140086fdd  mov     dword ptr [rsp+60h+phkResult], eax
0x140086fe1  call    WPP_SF_SD
0x140086fe6  jmp     loc_140087103
0x140086feb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140086fef  call    cs:__imp_QueryPerformanceCounter
0x140086ff5  test    eax, eax
0x140086ff7  jnz     short loc_140087031
0x140086ff9  call    cs:__imp_GetLastError
0x140086fff  mov     rcx, cs:WPP_GLOBAL_Control
0x140087006  cmp     rcx, r14
0x140087009  jz      loc_140087103
0x14008700f  test    byte ptr [rcx+1Ch], 1
0x140087013  jz      loc_140087103
0x140087019  cmp     byte ptr [rcx+19h], 2
0x14008701d  jb      loc_140087103
0x140087023  mov     edx, 3Dh ; '='
0x140087028  lea     r9, aLastlogoffendt; "LastLogOffEndTimePerfCounter"
0x14008702f  jmp     short loc_140086FD2
0x140087031  mov     rcx, [rbp+hKey]; hKey
0x140087035  lea     rax, [rbp+PerformanceCount]
0x140087039  lea     rbx, aLastlogoffendt; "LastLogOffEndTimePerfCounter"
0x140087040  mov     dword ptr [rsp+60h+cbData], 8; cbData
0x140087048  mov     rdx, rbx; lpValueName
0x14008704b  mov     [rsp+60h+phkResult], rax; lpData
0x140087050  mov     r9d, 0Bh; dwType
0x140087056  xor     r8d, r8d; Reserved
0x140087059  call    cs:__imp_RegSetValueExW
0x14008705f  test    eax, eax
0x140087061  jnz     short loc_1400870C6
0x140087063  xorps   xmm0, xmm0
0x140087066  lea     rcx, [rbp+var_18]
0x14008706a  movups  [rbp+var_18], xmm0
0x14008706e  call    WLGetTSActivityId
0x140087073  mov     eax, cs:dword_1400CF778
0x140087079  cmp     eax, 5
0x14008707c  jbe     loc_140087103
0x140087082  mov     rdx, 400000000000h
0x14008708c  lea     rcx, dword_1400CF778
0x140087093  call    _tlgKeywordOn
0x140087098  test    al, al
0x14008709a  jz      short loc_140087103
0x14008709c  lea     rax, [rbp+var_20]
0x1400870a0  mov     [rbp+var_20], 1000000h
0x1400870a8  lea     r8, [rbp+var_18]
0x1400870ac  mov     [rsp+60h+phkResult], rax
0x1400870b1  lea     rdx, byte_1400BD7DD
0x1400870b8  lea     rcx, dword_1400CF778
0x1400870bf  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1400870c4  jmp     short loc_140087103
0x1400870c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400870cd  cmp     rcx, r14
0x1400870d0  jz      short loc_140087103
0x1400870d2  test    byte ptr [rcx+1Ch], 1
0x1400870d6  jz      short loc_140087103
0x1400870d8  cmp     byte ptr [rcx+19h], 2
0x1400870dc  jb      short loc_140087103
0x1400870de  mov     rcx, [rcx+10h]
0x1400870e2  lea     r9, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400870e9  mov     dword ptr [rsp+60h+cbData], eax
0x1400870ed  lea     r8, WPP_ea968c137b9e31d540c842f1a896af1c_Traceguids
0x1400870f4  mov     edx, 3Eh ; '>'
0x1400870f9  mov     [rsp+60h+phkResult], rbx
0x1400870fe  call    WPP_SF_SSD
0x140087103  mov     rcx, [rbp+hKey]; hKey
0x140087107  test    rcx, rcx
0x14008710a  jz      short loc_140087112
0x14008710c  call    cs:__imp_RegCloseKey
0x140087112  mov     rcx, [rbp+var_8]
0x140087116  xor     rcx, rsp; StackCookie
0x140087119  call    __security_check_cookie
0x14008711e  mov     rbx, [rsp+60h+arg_0]
0x140087123  mov     r14, [rsp+60h+arg_8]
0x140087128  add     rsp, 60h
0x14008712c  pop     rbp
0x14008712d  retn
```
