# CIEBrowserModeFilter::Init(void)

- ea: `0x180076560`
- end: `0x1800768bb`
- name: `?Init@CIEBrowserModeFilter@@EEAAJXZ`
- size: `859`
- prototype: `__int64 __fastcall(CIEBrowserModeFilter *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007629c`

## callees

- `0x180076560`
- `0x1800768c4`
- `0x18007692c`
- `0x180098384`
- `0x1800ac8c8`
- `0x1800ac8d4`
- `0x1800b1ee0`
- `0x1800b3874`
- `0x1800b4df4`
- `0x1800b4eec`
- `0x1800b4fe4`
- `0x1801285fe`
- `0x180128660`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18007669a`
- `msvcrt!wcscat_s` at `0x1800766ba`
- `msvcrt!wcscat_s` at `0x18007669a`
- `msvcrt!wcscat_s` at `0x1800766ba`
- `msvcrt!wcscpy_s` at `0x180076670`
- `msvcrt!wcscpy_s` at `0x180076670`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x180076723`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x180076723`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x18007660e`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x18007660e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180076597`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800765aa`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800765bf`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007674a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007675f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180076798`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800767fc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180076811`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180076597`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800765aa`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800765bf`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007674a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007675f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180076798`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800767fc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180076811`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x180076681`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x180076681`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180076621`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800766db`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180076621`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800766db`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007684c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007684c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076878`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076862`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076862`

## pseudocode

```c
__int64 __fastcall CIEBrowserModeFilter::Init(CIEBrowserModeFilter *this)
{
  unsigned int NewVersionXML; // ebx
  char Bool; // bl
  bool v4; // si
  unsigned __int16 *v5; // rbx
  const wchar_t *String; // rax
  wchar_t *p_Destination; // r8
  bool v8; // si
  bool v9; // zf
  signed int LastError; // eax
  unsigned int v12[4]; // [rsp+20h] [rbp-258h] BYREF
  wchar_t Destination; // [rsp+30h] [rbp-248h] BYREF
  _BYTE v14[558]; // [rsp+32h] [rbp-246h] BYREF

  NewVersionXML = 0;
  if ( *((_BYTE *)this + 32) )
    return NewVersionXML;
  Bool = IEConfiguration_GetBool(268435519);
  v4 = ((unsigned __int8)IEConfiguration_GetBool(268435482) || (unsigned __int8)IEConfiguration_GetBool(268435481))
    && !Bool;
  if ( *((_DWORD *)this + 14) )
    goto LABEL_12;
  if ( v4 )
  {
    v5 = (unsigned __int16 *)operator new[](0x230u);
    *v5 = 0;
    IsoPrefixUserQualifierToName(v5, 0x118u, **((const unsigned __int16 ***)this + 66));
    *((_QWORD *)this + 6) = CreateMutexW(0, 0, v5);
    operator delete[](v5);
    goto LABEL_14;
  }
  if ( !Bool )
  {
LABEL_12:
    p_Destination = (wchar_t *)**((_QWORD **)this + 66);
  }
  else
  {
    Destination = 0;
    memset_0(v14, 0, sizeof(v14));
    wcscpy_s(&Destination, 0x118u, L"Local\\");
    String = (const wchar_t *)IEConfiguration_GetString(268435499);
    wcscat_s(&Destination, 0x118u, String);
    wcscat_s(&Destination, 0x118u, **((const wchar_t ***)this + 66));
    p_Destination = &Destination;
  }
  *((_QWORD *)this + 6) = CreateMutexW(0, 0, p_Destination);
LABEL_14:
  if ( *((_QWORD *)this + 6) )
  {
    if ( v4 && !*((_DWORD *)this + 14) && GetLastError() != 183 )
      SetWindowsHandleAccess(*((void **)this + 6), 0x114Fu, 0x801F0003);
    v12[0] = CIEBrowserModeFilter::lock(this);
    NewVersionXML = v12[0];
    if ( v12[0] )
      goto LABEL_44;
    if ( (unsigned __int8)IEConfiguration_GetBool(536870925) && !(unsigned __int8)IEConfiguration_GetBool(268435500) )
      goto LABEL_40;
    v8 = CIEBrowserModeFilter::MustUpgradeCacheContainers(this) || !CIEBrowserModeFilter::isCacheVersionCurrent(this);
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870913) || v8 )
    {
      NewVersionXML = CIEBrowserModeFilter::initializeUrlCache(this);
      v12[0] = NewVersionXML;
    }
    if ( NewVersionXML )
      goto LABEL_43;
    if ( !IsValidContextToUpdateFilter() || !v8 )
      goto LABEL_40;
    if ( (unsigned __int8)CIEBrowserModeFilter::CallElevationBrokerIfAppropriate(this, v12, 6) )
    {
      NewVersionXML = v12[0];
    }
    else
    {
      NewVersionXML = CIEBrowserModeFilter::loadNewVersionXML(this);
      if ( NewVersionXML == -2147024894
        && (unsigned __int8)IEConfiguration_GetBool(268435519)
        && (unsigned __int8)IEConfiguration_GetBool(536870923) )
      {
        NewVersionXML = 0;
      }
    }
    v9 = NewVersionXML == 0;
    if ( (NewVersionXML & 0x80000000) == 0 )
    {
LABEL_40:
      NewVersionXML = CIEBrowserModeFilter::readCacheVersionFromRegistry(
                        this,
                        (unsigned int *)this + 9,
                        (unsigned int *)this + 10);
      v9 = NewVersionXML == 0;
    }
    if ( v9 )
      *((_BYTE *)this + 32) = 1;
LABEL_43:
    ReleaseMutex(*((HANDLE *)this + 6));
LABEL_44:
    if ( !*((_BYTE *)this + 32) )
    {
      CloseHandle(*((HANDLE *)this + 6));
      *((_QWORD *)this + 6) = 0;
    }
    return NewVersionXML;
  }
  LastError = GetLastError();
  NewVersionXML = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return NewVersionXML;
}

```

## disassembly

```asm
0x180076560  mov     [rsp+arg_8], rbx
0x180076565  mov     [rsp+arg_10], rsi
0x18007656a  push    rdi
0x18007656b  sub     rsp, 270h
0x180076572  mov     rax, cs:__security_cookie
0x180076579  xor     rax, rsp
0x18007657c  mov     [rsp+278h+var_18], rax
0x180076584  xor     ebx, ebx
0x180076586  mov     rdi, rcx
0x180076589  cmp     [rcx+20h], bl
0x18007658c  jnz     loc_180076893
0x180076592  mov     ecx, 1000003Fh
0x180076597  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18007659e  nop     dword ptr [rax+rax+00h]
0x1800765a3  mov     ecx, 1000001Ah
0x1800765a8  mov     bl, al
0x1800765aa  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800765b1  nop     dword ptr [rax+rax+00h]
0x1800765b6  test    al, al
0x1800765b8  jnz     short loc_1800765CF
0x1800765ba  mov     ecx, 10000019h
0x1800765bf  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800765c6  nop     dword ptr [rax+rax+00h]
0x1800765cb  test    al, al
0x1800765cd  jz      short loc_1800765D8
0x1800765cf  test    bl, bl
0x1800765d1  jnz     short loc_1800765D8
0x1800765d3  mov     sil, 1
0x1800765d6  jmp     short loc_1800765DB
0x1800765d8  xor     sil, sil
0x1800765db  cmp     dword ptr [rdi+38h], 0
0x1800765df  jnz     loc_1800766CD
0x1800765e5  test    sil, sil
0x1800765e8  jz      short loc_18007663E
0x1800765ea  mov     ecx, 230h; unsigned __int64
0x1800765ef  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800765f4  mov     rbx, rax
0x1800765f7  mov     edx, 118h
0x1800765fc  xor     eax, eax
0x1800765fe  mov     rcx, rbx
0x180076601  mov     [rbx], ax
0x180076604  mov     r8, [rdi+210h]
0x18007660b  mov     r8, [r8]
0x18007660e  call    cs:__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z; IsoPrefixUserQualifierToName(ushort *,ulong,ushort const *)
0x180076615  nop     dword ptr [rax+rax+00h]
0x18007661a  mov     r8, rbx; lpName
0x18007661d  xor     edx, edx; bInitialOwner
0x18007661f  xor     ecx, ecx; lpMutexAttributes
0x180076621  call    cs:__imp_CreateMutexW
0x180076628  nop     dword ptr [rax+rax+00h]
0x18007662d  mov     rcx, rbx; void *
0x180076630  mov     [rdi+30h], rax
0x180076634  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180076639  jmp     loc_1800766EB
0x18007663e  test    bl, bl
0x180076640  jz      loc_1800766CD
0x180076646  xor     eax, eax
0x180076648  lea     rcx, [rsp+278h+var_246]; void *
0x18007664d  xor     edx, edx; Val
0x18007664f  mov     [rsp+278h+Destination], ax
0x180076654  mov     r8d, 22Eh; Size
0x18007665a  call    memset_0
0x18007665f  lea     r8, aLocal_0; "Local\\"
0x180076666  mov     edx, 118h; SizeInWords
0x18007666b  lea     rcx, [rsp+278h+Destination]; Destination
0x180076670  call    cs:__imp_wcscpy_s
0x180076677  nop     dword ptr [rax+rax+00h]
0x18007667c  mov     ecx, 1000002Bh
0x180076681  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x180076688  nop     dword ptr [rax+rax+00h]
0x18007668d  mov     edx, 118h; SizeInWords
0x180076692  lea     rcx, [rsp+278h+Destination]; Destination
0x180076697  mov     r8, rax; Source
0x18007669a  call    cs:__imp_wcscat_s
0x1800766a1  nop     dword ptr [rax+rax+00h]
0x1800766a6  mov     r8, [rdi+210h]
0x1800766ad  lea     rcx, [rsp+278h+Destination]; Destination
0x1800766b2  mov     edx, 118h; SizeInWords
0x1800766b7  mov     r8, [r8]; Source
0x1800766ba  call    cs:__imp_wcscat_s
0x1800766c1  nop     dword ptr [rax+rax+00h]
0x1800766c6  lea     r8, [rsp+278h+Destination]
0x1800766cb  jmp     short loc_1800766D7
0x1800766cd  mov     r8, [rdi+210h]
0x1800766d4  mov     r8, [r8]; lpName
0x1800766d7  xor     edx, edx; bInitialOwner
0x1800766d9  xor     ecx, ecx; lpMutexAttributes
0x1800766db  call    cs:__imp_CreateMutexW
0x1800766e2  nop     dword ptr [rax+rax+00h]
0x1800766e7  mov     [rdi+30h], rax
0x1800766eb  cmp     qword ptr [rdi+30h], 0
0x1800766f0  jz      loc_180076878
0x1800766f6  test    sil, sil
0x1800766f9  jz      short loc_18007672F
0x1800766fb  cmp     dword ptr [rdi+38h], 0
0x1800766ff  jnz     short loc_18007672F
0x180076701  call    cs:__imp_GetLastError
0x180076708  nop     dword ptr [rax+rax+00h]
0x18007670d  cmp     eax, 0B7h
0x180076712  jz      short loc_18007672F
0x180076714  mov     rcx, [rdi+30h]
0x180076718  mov     edx, 114Fh
0x18007671d  mov     r8d, 801F0003h
0x180076723  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x18007672a  nop     dword ptr [rax+rax+00h]
0x18007672f  mov     rcx, rdi; this
0x180076732  call    ?lock@CIEBrowserModeFilter@@AEAAJXZ; CIEBrowserModeFilter::lock(void)
0x180076737  mov     [rsp+278h+var_258], eax
0x18007673b  mov     ebx, eax
0x18007673d  test    eax, eax
0x18007673f  jnz     loc_180076858
0x180076745  mov     ecx, 2000000Dh
0x18007674a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180076751  nop     dword ptr [rax+rax+00h]
0x180076756  test    al, al
0x180076758  jz      short loc_180076773
0x18007675a  mov     ecx, 1000002Ch
0x18007675f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180076766  nop     dword ptr [rax+rax+00h]
0x18007676b  test    al, al
0x18007676d  jz      loc_18007682E
0x180076773  mov     rcx, rdi; this
0x180076776  call    ?MustUpgradeCacheContainers@CIEBrowserModeFilter@@AEAA_NXZ; CIEBrowserModeFilter::MustUpgradeCacheContainers(void)
0x18007677b  test    al, al
0x18007677d  jnz     short loc_180076790
0x18007677f  mov     rcx, rdi; this
0x180076782  call    ?isCacheVersionCurrent@CIEBrowserModeFilter@@AEAA_NXZ; CIEBrowserModeFilter::isCacheVersionCurrent(void)
0x180076787  test    al, al
0x180076789  jz      short loc_180076790
0x18007678b  xor     sil, sil
0x18007678e  jmp     short loc_180076793
0x180076790  mov     sil, 1
0x180076793  mov     ecx, 20000001h
0x180076798  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18007679f  nop     dword ptr [rax+rax+00h]
0x1800767a4  test    al, al
0x1800767a6  jz      short loc_1800767AD
0x1800767a8  test    sil, sil
0x1800767ab  jz      short loc_1800767BB
0x1800767ad  mov     rcx, rdi; this
0x1800767b0  call    ?initializeUrlCache@CIEBrowserModeFilter@@AEAAJXZ; CIEBrowserModeFilter::initializeUrlCache(void)
0x1800767b5  mov     ebx, eax
0x1800767b7  mov     [rsp+278h+var_258], eax
0x1800767bb  test    ebx, ebx
0x1800767bd  jnz     loc_180076848
0x1800767c3  call    ?IsValidContextToUpdateFilter@@YA_NXZ; IsValidContextToUpdateFilter(void)
0x1800767c8  test    al, al
0x1800767ca  jz      short loc_18007682E
0x1800767cc  test    sil, sil
0x1800767cf  jz      short loc_18007682E
0x1800767d1  lea     r8d, [rbx+6]
0x1800767d5  mov     rcx, rdi
0x1800767d8  lea     rdx, [rsp+278h+var_258]
0x1800767dd  call    ?CallElevationBrokerIfAppropriate@CIEBrowserModeFilter@@AEAA_NPEAJW4_BROWSERBROKER_CVLISTACTION@@@Z; CIEBrowserModeFilter::CallElevationBrokerIfAppropriate(long *,_BROWSERBROKER_CVLISTACTION)
0x1800767e2  test    al, al
0x1800767e4  jnz     short loc_180076826
0x1800767e6  mov     rcx, rdi; this
0x1800767e9  call    ?loadNewVersionXML@CIEBrowserModeFilter@@AEAAJXZ; CIEBrowserModeFilter::loadNewVersionXML(void)
0x1800767ee  mov     ebx, eax
0x1800767f0  cmp     eax, 80070002h
0x1800767f5  jnz     short loc_18007682A
0x1800767f7  mov     ecx, 1000003Fh
0x1800767fc  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180076803  nop     dword ptr [rax+rax+00h]
0x180076808  test    al, al
0x18007680a  jz      short loc_18007682A
0x18007680c  mov     ecx, 2000000Bh
0x180076811  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180076818  nop     dword ptr [rax+rax+00h]
0x18007681d  xor     ecx, ecx
0x18007681f  test    al, al
0x180076821  cmovnz  ebx, ecx
0x180076824  jmp     short loc_18007682A
0x180076826  mov     ebx, [rsp+278h+var_258]
0x18007682a  test    ebx, ebx
0x18007682c  js      short loc_180076842
0x18007682e  lea     r8, [rdi+28h]; unsigned int *
0x180076832  mov     rcx, rdi; this
0x180076835  lea     rdx, [rdi+24h]; unsigned int *
0x180076839  call    ?readCacheVersionFromRegistry@CIEBrowserModeFilter@@AEAAJPEAK0@Z; CIEBrowserModeFilter::readCacheVersionFromRegistry(ulong *,ulong *)
0x18007683e  mov     ebx, eax
0x180076840  test    eax, eax
0x180076842  jnz     short loc_180076848
0x180076844  mov     byte ptr [rdi+20h], 1
0x180076848  mov     rcx, [rdi+30h]; hMutex
0x18007684c  call    cs:__imp_ReleaseMutex
0x180076853  nop     dword ptr [rax+rax+00h]
0x180076858  cmp     byte ptr [rdi+20h], 0
0x18007685c  jnz     short loc_180076893
0x18007685e  mov     rcx, [rdi+30h]; hObject
0x180076862  call    cs:__imp_CloseHandle
0x180076869  nop     dword ptr [rax+rax+00h]
0x18007686e  mov     qword ptr [rdi+30h], 0
0x180076876  jmp     short loc_180076893
0x180076878  call    cs:__imp_GetLastError
0x18007687f  nop     dword ptr [rax+rax+00h]
0x180076884  mov     ebx, eax
0x180076886  test    eax, eax
0x180076888  jle     short loc_180076893
0x18007688a  movzx   ebx, ax
0x18007688d  or      ebx, 80070000h
0x180076893  mov     eax, ebx
0x180076895  mov     rcx, [rsp+278h+var_18]
0x18007689d  xor     rcx, rsp; StackCookie
0x1800768a0  call    __security_check_cookie
0x1800768a5  lea     r11, [rsp+278h+var_8]
0x1800768ad  mov     rbx, [r11+18h]
0x1800768b1  mov     rsi, [r11+20h]
0x1800768b5  mov     rsp, r11
0x1800768b8  pop     rdi
0x1800768b9  retn
```
