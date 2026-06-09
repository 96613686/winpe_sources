# SampReadComputerAccountReuseAllowListSetting(HKEY__ *)

- ea: `0x1800874a0`
- end: `0x180087789`
- name: `?SampReadComputerAccountReuseAllowListSetting@@YAXPEAUHKEY__@@@Z`
- size: `745`
- prototype: `void __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180086ff0`

## callees

- `0x180037284`
- `0x1800372ac`
- `0x18004d9c0`
- `0x180079238`
- `0x1800874a0`
- `0x18008deb8`
- `0x1800b03d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800875ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800875ab`
- `ntdll!RtlLeaveCriticalSection` at `0x1800875df`
- `ntdll!RtlLeaveCriticalSection` at `0x1800876e3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800875df`
- `ntdll!RtlLeaveCriticalSection` at `0x1800876e3`
- `ntdll!RtlEnterCriticalSection` at `0x180087531`
- `ntdll!RtlEnterCriticalSection` at `0x180087531`
- `ntdll!RtlInitUnicodeString` at `0x1800876f1`
- `ntdll!RtlInitUnicodeString` at `0x1800876f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087654`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087654`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800876b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800876cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180087763`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008776c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800876b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800876cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180087763`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008776c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800875a1`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800875a1`

## string_xrefs

- `0x1800874c7`: `ComputerAccountReuseAllowList`

## pseudocode

```c
void __fastcall SampReadComputerAccountReuseAllowListSetting(HKEY a1)
{
  WCHAR *v1; // r15
  unsigned int RegistryString; // eax
  WCHAR *lpString2; // rbp
  const WCHAR *v4; // r8
  __int64 v5; // r14
  int v6; // eax
  DWORD LastError; // eax
  SIZE_T v8; // rdx
  unsigned int v9; // r14d
  unsigned __int16 *v10; // rax
  int v11; // eax
  __int64 v12; // r9
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF
  LPCWCH SourceString; // [rsp+80h] [rbp+8h] BYREF

  SourceString = 0;
  v1 = 0;
  DestinationString = 0;
  RegistryString = SampGetRegistryString(ghSamKey, L"ComputerAccountReuseAllowList", (unsigned __int16 **)&SourceString);
  lpString2 = (WCHAR *)SourceString;
  if ( RegistryString || !*SourceString )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 212, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
    }
  }
  else
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_S(WPP_GLOBAL_Control[3].Buffer, 213, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SourceString);
    }
    RtlEnterCriticalSection(&gcsComputerAccountReuseAllowListLock);
    v4 = SampComputerAccountReuseAllowListSDDL;
    v5 = -1;
    if ( SampComputerAccountReuseAllowListSDDL )
    {
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
      {
        WPP_SF_S(
          WPP_GLOBAL_Control[3].Buffer,
          214,
          WPP_6405431812663459a7a3c2922bf567cd_Traceguids,
          SampComputerAccountReuseAllowListSDDL);
        v4 = SampComputerAccountReuseAllowListSDDL;
      }
      v6 = CompareStringEx(&Annotation, 1u, v4, -1, lpString2, -1, 0, 0, 0);
      if ( !v6 )
      {
        LastError = GetLastError();
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 3u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 215, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, LastError);
        }
LABEL_14:
        RtlLeaveCriticalSection(&gcsComputerAccountReuseAllowListLock);
        goto LABEL_36;
      }
      if ( v6 == 2 )
      {
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 216, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
        }
        goto LABEL_14;
      }
    }
    else if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
           && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 217, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
    }
    do
      ++v5;
    while ( lpString2[v5] );
    v8 = 2LL * (unsigned int)(v5 + 1);
    v9 = v5 + 1;
    v10 = (unsigned __int16 *)LocalAlloc(0x40u, v8);
    v1 = v10;
    if ( !v10 )
      goto LABEL_14;
    v11 = RtlStringCchCopyW(v10, v9, lpString2);
    if ( v11 < 0 )
    {
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 218, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v11);
      }
      goto LABEL_14;
    }
    LocalFree((HLOCAL)SampComputerAccountReuseAllowListSDDL);
    SampComputerAccountReuseAllowListSDDL = v1;
    v1 = 0;
    if ( SampComputerAccountReuseAllowListSD )
    {
      LocalFree(SampComputerAccountReuseAllowListSD);
      SampComputerAccountReuseAllowListSD = 0;
    }
    RtlLeaveCriticalSection(&gcsComputerAccountReuseAllowListLock);
    RtlInitUnicodeString(&DestinationString, lpString2);
    SampWriteEventLog(SAMMSG_COMPUTER_ACCOUNT_REUSE_ALLOW_LIST_SD, L"u", &DestinationString, v12);
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_S(WPP_GLOBAL_Control[3].Buffer, 219, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, lpString2);
    }
  }
LABEL_36:
  LocalFree(v1);
  LocalFree(lpString2);
}

```

## disassembly

```asm
0x1800874a0  mov     rax, rsp
0x1800874a3  mov     [rax+10h], rbp
0x1800874a7  mov     [rax+18h], rsi
0x1800874ab  mov     [rax+8], rcx
0x1800874af  push    r12
0x1800874b1  push    r14
0x1800874b3  push    r15
0x1800874b5  sub     rsp, 60h
0x1800874b9  mov     rcx, cs:?ghSamKey@@3PEAUHKEY__@@EA; hKey
0x1800874c0  lea     r8, [rax+8]; unsigned __int16 **
0x1800874c4  xor     r12d, r12d
0x1800874c7  lea     rdx, aComputeraccoun; "ComputerAccountReuseAllowList"
0x1800874ce  xorps   xmm0, xmm0
0x1800874d1  mov     [rax+8], r12
0x1800874d5  mov     r15d, r12d
0x1800874d8  movups  xmmword ptr [rax-28h], xmm0
0x1800874dc  call    ?SampGetRegistryString@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; SampGetRegistryString(HKEY__ *,ushort const *,ushort * *)
0x1800874e1  mov     rbp, [rsp+78h+SourceString]
0x1800874e9  test    eax, eax
0x1800874eb  jnz     loc_180087738
0x1800874f1  cmp     r12w, [rbp+0]
0x1800874f6  jz      loc_180087738
0x1800874fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180087503  lea     rsi, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18008750a  test    byte ptr [rcx+44h], 20h
0x18008750e  jz      short loc_18008752A
0x180087510  cmp     byte ptr [rcx+41h], 4
0x180087514  jb      short loc_18008752A
0x180087516  mov     rcx, [rcx+38h]
0x18008751a  mov     edx, 0D5h
0x18008751f  mov     r9, rbp
0x180087522  mov     r8, rsi
0x180087525  call    WPP_SF_S
0x18008752a  lea     rcx, ?gcsComputerAccountReuseAllowListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180087531  call    cs:__imp_RtlEnterCriticalSection
0x180087537  mov     r8, cs:?SampComputerAccountReuseAllowListSDDL@@3PEAGEA; ushort * SampComputerAccountReuseAllowListSDDL
0x18008753e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180087542  test    r8, r8
0x180087545  jz      loc_180087615
0x18008754b  mov     rcx, cs:WPP_GLOBAL_Control
0x180087552  test    byte ptr [rcx+44h], 20h
0x180087556  jz      short loc_180087579
0x180087558  cmp     byte ptr [rcx+41h], 4
0x18008755c  jb      short loc_180087579
0x18008755e  mov     rcx, [rcx+38h]
0x180087562  mov     r9, r8
0x180087565  mov     r8, rsi
0x180087568  mov     edx, 0D6h
0x18008756d  call    WPP_SF_S
0x180087572  mov     r8, cs:?SampComputerAccountReuseAllowListSDDL@@3PEAGEA; lpString1
0x180087579  mov     [rsp+78h+lParam], r12; lParam
0x18008757e  lea     rcx, Annotation; lpLocaleName
0x180087585  mov     [rsp+78h+lpReserved], r12; lpReserved
0x18008758a  mov     r9d, r14d; cchCount1
0x18008758d  mov     [rsp+78h+lpVersionInformation], r12; lpVersionInformation
0x180087592  mov     edx, 1; dwCmpFlags
0x180087597  mov     [rsp+78h+cchCount2], r14d; cchCount2
0x18008759c  mov     [rsp+78h+lpString2], rbp; lpString2
0x1800875a1  call    cs:__imp_CompareStringEx
0x1800875a7  test    eax, eax
0x1800875a9  jnz     short loc_1800875EA
0x1800875ab  call    cs:__imp_GetLastError
0x1800875b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800875b8  test    byte ptr [rcx+44h], 20h
0x1800875bc  jz      short loc_1800875D8
0x1800875be  cmp     byte ptr [rcx+41h], 3
0x1800875c2  jb      short loc_1800875D8
0x1800875c4  mov     rcx, [rcx+38h]
0x1800875c8  mov     edx, 0D7h
0x1800875cd  mov     r9d, eax
0x1800875d0  mov     r8, rsi
0x1800875d3  call    WPP_SF_d
0x1800875d8  lea     rcx, ?gcsComputerAccountReuseAllowListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800875df  call    cs:__imp_RtlLeaveCriticalSection
0x1800875e5  jmp     loc_180087760
0x1800875ea  cmp     eax, 2
0x1800875ed  jnz     short loc_180087639
0x1800875ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800875f6  test    byte ptr [rcx+44h], 20h
0x1800875fa  jz      short loc_1800875D8
0x1800875fc  cmp     byte ptr [rcx+41h], 4
0x180087600  jb      short loc_1800875D8
0x180087602  mov     rcx, [rcx+38h]
0x180087606  mov     edx, 0D8h
0x18008760b  mov     r8, rsi
0x18008760e  call    WPP_SF_
0x180087613  jmp     short loc_1800875D8
0x180087615  mov     rcx, cs:WPP_GLOBAL_Control
0x18008761c  test    byte ptr [rcx+44h], 20h
0x180087620  jz      short loc_180087639
0x180087622  cmp     byte ptr [rcx+41h], 4
0x180087626  jb      short loc_180087639
0x180087628  mov     rcx, [rcx+38h]
0x18008762c  mov     edx, 0D9h
0x180087631  mov     r8, rsi
0x180087634  call    WPP_SF_
0x180087639  inc     r14
0x18008763c  cmp     [rbp+r14*2+0], r12w
0x180087642  jnz     short loc_180087639
0x180087644  lea     eax, [r14+1]
0x180087648  mov     ecx, 40h ; '@'; uFlags
0x18008764d  lea     rdx, [rax+rax]; uBytes
0x180087651  mov     r14d, eax
0x180087654  call    cs:__imp_LocalAlloc
0x18008765a  mov     r15, rax
0x18008765d  test    rax, rax
0x180087660  jz      loc_1800875D8
0x180087666  mov     r8, rbp; unsigned __int16 *
0x180087669  mov     edx, r14d; unsigned __int64
0x18008766c  mov     rcx, rax; unsigned __int16 *
0x18008766f  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180087674  test    eax, eax
0x180087676  jns     short loc_1800876AC
0x180087678  mov     rcx, cs:WPP_GLOBAL_Control
0x18008767f  test    byte ptr [rcx+44h], 20h
0x180087683  jz      loc_1800875D8
0x180087689  cmp     byte ptr [rcx+41h], 2
0x18008768d  jb      loc_1800875D8
0x180087693  mov     rcx, [rcx+38h]
0x180087697  mov     edx, 0DAh
0x18008769c  mov     r9d, eax
0x18008769f  mov     r8, rsi
0x1800876a2  call    WPP_SF_d
0x1800876a7  jmp     loc_1800875D8
0x1800876ac  mov     rcx, cs:?SampComputerAccountReuseAllowListSDDL@@3PEAGEA; hMem
0x1800876b3  call    cs:__imp_LocalFree
0x1800876b9  mov     rcx, cs:?SampComputerAccountReuseAllowListSD@@3PEAXEA; hMem
0x1800876c0  mov     cs:?SampComputerAccountReuseAllowListSDDL@@3PEAGEA, r15; ushort * SampComputerAccountReuseAllowListSDDL
0x1800876c7  mov     r15, r12
0x1800876ca  test    rcx, rcx
0x1800876cd  jz      short loc_1800876DC
0x1800876cf  call    cs:__imp_LocalFree
0x1800876d5  mov     cs:?SampComputerAccountReuseAllowListSD@@3PEAXEA, r12; void * SampComputerAccountReuseAllowListSD
0x1800876dc  lea     rcx, ?gcsComputerAccountReuseAllowListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800876e3  call    cs:__imp_RtlLeaveCriticalSection
0x1800876e9  mov     rdx, rbp; SourceString
0x1800876ec  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800876f1  call    cs:__imp_RtlInitUnicodeString
0x1800876f7  lea     r8, [rsp+78h+DestinationString]
0x1800876fc  lea     rdx, aU; "u"
0x180087703  lea     rcx, SAMMSG_COMPUTER_ACCOUNT_REUSE_ALLOW_LIST_SD
0x18008770a  call    SampWriteEventLog
0x18008770f  mov     rcx, cs:WPP_GLOBAL_Control
0x180087716  test    byte ptr [rcx+44h], 20h
0x18008771a  jz      short loc_180087760
0x18008771c  cmp     byte ptr [rcx+41h], 4
0x180087720  jb      short loc_180087760
0x180087722  mov     rcx, [rcx+38h]
0x180087726  mov     edx, 0DBh
0x18008772b  mov     r9, rbp
0x18008772e  mov     r8, rsi
0x180087731  call    WPP_SF_S
0x180087736  jmp     short loc_180087760
0x180087738  mov     rcx, cs:WPP_GLOBAL_Control
0x18008773f  test    byte ptr [rcx+44h], 20h
0x180087743  jz      short loc_180087760
0x180087745  cmp     byte ptr [rcx+41h], 4
0x180087749  jb      short loc_180087760
0x18008774b  mov     rcx, [rcx+38h]
0x18008774f  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180087756  mov     edx, 0D4h
0x18008775b  call    WPP_SF_
0x180087760  mov     rcx, r15; hMem
0x180087763  call    cs:__imp_LocalFree
0x180087769  mov     rcx, rbp; hMem
0x18008776c  call    cs:__imp_LocalFree
0x180087772  lea     r11, [rsp+78h+var_18]
0x180087777  mov     rbp, [r11+28h]
0x18008777b  mov     rsi, [r11+30h]
0x18008777f  mov     rsp, r11
0x180087782  pop     r15
0x180087784  pop     r14
0x180087786  pop     r12
0x180087788  retn
```
