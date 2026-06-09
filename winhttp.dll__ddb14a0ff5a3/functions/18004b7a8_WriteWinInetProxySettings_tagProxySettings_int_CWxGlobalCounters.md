# WriteWinInetProxySettings(tagProxySettings *,int,CWxGlobalCounters *)

- ea: `0x18004b7a8`
- end: `0x18004bb50`
- name: `?WriteWinInetProxySettings@@YAJPEAUtagProxySettings@@HPEAVCWxGlobalCounters@@@Z`
- size: `936`
- prototype: `__int64 __fastcall(struct tagProxySettings *, unsigned __int16 *, struct CWxGlobalCounters *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800219f0`
- `0x18004b128`

## callees

- `0x18001b480`
- `0x18001fb30`
- `0x180021320`
- `0x18004b358`
- `0x18004b7a8`
- `0x18004bb58`
- `0x18004c590`
- `0x180063190`
- `0x18008fd30`
- `0x18009a970`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800cf58c`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004bb0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004bb0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004b841`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004b841`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004badb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004badb`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18004ba05`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18004ba4b`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18004ba86`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18004ba05`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18004ba4b`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18004ba86`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18004b8a2`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18004b8a2`

## pseudocode

```c
__int64 __fastcall WriteWinInetProxySettings(
        struct tagProxySettings *a1,
        unsigned __int16 *a2,
        struct CWxGlobalCounters *a3)
{
  int v3; // r13d
  const WCHAR *v5; // rcx
  signed int v6; // edi
  HKEY WinInetBaseProxyKey; // r15
  int v8; // eax
  bool v9; // sf
  int v10; // eax
  unsigned int v12; // r8d
  unsigned __int16 v13; // r12
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // r8
  const unsigned __int16 *lpString2; // [rsp+20h] [rbp-59h]
  PCNZCH lpString1; // [rsp+40h] [rbp-39h]
  struct CWxGlobalCounters *v21; // [rsp+48h] [rbp-31h]
  int v22; // [rsp+50h] [rbp-29h] BYREF
  int v23; // [rsp+54h] [rbp-25h]
  int v24; // [rsp+58h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-19h] BYREF
  int v26; // [rsp+68h] [rbp-11h]
  __int64 v27; // [rsp+6Ch] [rbp-Dh]
  int v28; // [rsp+74h] [rbp-5h]
  __int64 v29; // [rsp+78h] [rbp-1h]
  __int64 v30; // [rsp+80h] [rbp+7h]
  __int64 v31; // [rsp+88h] [rbp+Fh]

  v21 = a3;
  v23 = 0;
  v3 = (int)a2;
  v26 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 1;
  phkResult = 0;
  v30 = 0;
  v31 = 0;
  v24 = 0;
  v22 = 0;
  lpString1 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    LODWORD(lpString2) = (_DWORD)a2;
    WPP_SF_qD(1029, 66, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, a1);
  }
  AcquireSRWLockExclusive(&g_srwProxyReg);
  v5 = (const WCHAR *)*((_QWORD *)a1 + 2);
  if ( v5 )
  {
    if ( *v5 )
    {
      v6 = WxNewStringWtoACchCp<WxHeapAllocator>(v5);
      if ( v6 < 0 )
      {
        v23 = 2834;
        goto LABEL_43;
      }
    }
  }
  WinInetBaseProxyKey = FindWinInetBaseProxyKey(3u);
  if ( !WinInetBaseProxyKey )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_(1029, 67, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
    v6 = -2147024894;
    v23 = 2860;
    goto LABEL_43;
  }
  v8 = CRegBlob::Init(&phkResult, WinInetBaseProxyKey, 0, 0, lpString2, "DefaultConnectionSettings", 0, 0);
  v6 = v8;
  if ( v8 == 2 )
    goto LABEL_23;
  v9 = v8 < 0;
  if ( v8 > 0 )
  {
    v6 = (unsigned __int16)v8 | 0x80070000;
    v9 = 1;
  }
  if ( !v9 )
  {
    CRegBlob::ReadBytes((CRegBlob *)&phkResult, &v22, 4u);
    CRegBlob::ReadBytes((CRegBlob *)&phkResult, &v24, 4u);
    v10 = v24;
    if ( !v24 )
      v10 = 1;
    if ( v10 != *((_DWORD *)a1 + 2) )
    {
      if ( !v3 && v22 == 70 )
      {
        v6 = -2147024883;
        v23 = 2909;
        goto LABEL_40;
      }
      *((_DWORD *)a1 + 2) = v10;
    }
LABEL_23:
    if ( (*((_DWORD *)a1 + 2))++ == -1 )
      *((_DWORD *)a1 + 2) = 1;
    WriteETWProxyEvent(a1);
    if ( GlobalIs64BitOs && WinInetBaseProxyKey == HKEY_LOCAL_MACHINE )
    {
      v6 = WriteWinInetProxySettingsHelper(a1, 0x100u, v12, HKEY_LOCAL_MACHINE, "DefaultConnectionSettings", v21);
      if ( v6 < 0 )
      {
        v23 = 2967;
        goto LABEL_43;
      }
      v13 = Wow64SetThreadDefaultGuestMachine(332);
      v6 = WriteWinInetProxySettingsHelper(a1, 0x200u, v14, HKEY_LOCAL_MACHINE, "DefaultConnectionSettings", v21);
      if ( v6 >= 0 )
      {
        if ( GlobalIsArm64 )
        {
          Wow64SetThreadDefaultGuestMachine(452);
          v6 = WriteWinInetProxySettingsHelper(a1, 0x200u, v15, HKEY_LOCAL_MACHINE, "DefaultConnectionSettings", v21);
          if ( v6 < 0 )
            v23 = 2987;
        }
      }
      else
      {
        v23 = 2977;
      }
      if ( v13 )
        Wow64SetThreadDefaultGuestMachine(v13);
    }
    else
    {
      v6 = WriteWinInetProxySettingsHelper(a1, 0, v12, WinInetBaseProxyKey, "DefaultConnectionSettings", v21);
      if ( v6 < 0 )
      {
        v23 = 2952;
        goto LABEL_40;
      }
      v6 = 0;
    }
    WxProxyConfigChangeNotification();
    goto LABEL_40;
  }
  v23 = 2876;
LABEL_40:
  if ( (unsigned __int64)WinInetBaseProxyKey <= 0xFFFFFFFF80000000uLL
    || (unsigned __int64)WinInetBaseProxyKey + 2147483645 <= 0x7FFFFFFB )
  {
    RegCloseKey(WinInetBaseProxyKey);
  }
LABEL_43:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 68, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, (unsigned int)v6, lpString2);
  ReleaseSRWLockExclusive(&g_srwProxyReg);
  CRegBlob::~CRegBlob((CRegBlob *)&phkResult, v16, v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004b7a8  mov     [rsp-8+arg_8], rbx
0x18004b7ad  push    rbp
0x18004b7ae  push    rsi
0x18004b7af  push    rdi
0x18004b7b0  push    r12
0x18004b7b2  push    r13
0x18004b7b4  push    r14
0x18004b7b6  push    r15
0x18004b7b8  lea     rbp, [rsp-27h]
0x18004b7bd  sub     rsp, 0A0h
0x18004b7c4  mov     rax, cs:__security_cookie
0x18004b7cb  xor     rax, rsp
0x18004b7ce  mov     [rbp+57h+var_40], rax
0x18004b7d2  xor     r12d, r12d
0x18004b7d5  mov     [rbp+57h+var_88], r8
0x18004b7d9  mov     ebx, r12d
0x18004b7dc  mov     [rbp+57h+var_7C], r12d
0x18004b7e0  mov     r13d, edx
0x18004b7e3  mov     [rbp+57h+var_68], r12d
0x18004b7e7  mov     rsi, rcx
0x18004b7ea  mov     [rbp+57h+var_58], r12
0x18004b7ee  lea     r15d, [r12+1]
0x18004b7f3  mov     [rbp+57h+var_5C], r12d
0x18004b7f7  mov     [rbp+57h+var_64], r15
0x18004b7fb  mov     [rbp+57h+phkResult], r12
0x18004b7ff  mov     [rbp+57h+var_50], r12
0x18004b803  mov     [rbp+57h+var_48], r12
0x18004b807  mov     [rbp+57h+var_78], r12d
0x18004b80b  mov     [rbp+57h+var_80], r12d
0x18004b80f  mov     [rbp+57h+lpString1], rbx
0x18004b813  test    byte ptr cs:xmmword_180107A60, 20h
0x18004b81a  jz      short loc_18004B83A
0x18004b81c  lea     edx, [r12+42h]
0x18004b821  mov     dword ptr [rsp+0D0h+lpString2], r13d; unsigned __int16 *
0x18004b826  mov     ecx, 405h
0x18004b82b  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x18004b832  mov     r9, rsi
0x18004b835  call    WPP_SF_qD
0x18004b83a  lea     rcx, ?g_srwProxyReg@@3VWxSrw@@A; SRWLock
0x18004b841  call    cs:__imp_AcquireSRWLockExclusive
0x18004b847  mov     rcx, [rsi+10h]; lpWideCharStr
0x18004b84b  test    rcx, rcx
0x18004b84e  jz      short loc_18004B8AF
0x18004b850  cmp     [rcx], r12w
0x18004b854  jz      short loc_18004B8AF
0x18004b856  lea     r9, [rbp+57h+lpString1]
0x18004b85a  call    ??$WxNewStringWtoACchCp@VWxHeapAllocator@@@@YAJPEBGKKPEAPEAD@Z; WxNewStringWtoACchCp<WxHeapAllocator>(ushort const *,ulong,ulong,char * *)
0x18004b85f  mov     rbx, [rbp+57h+lpString1]
0x18004b863  mov     edi, eax
0x18004b865  test    eax, eax
0x18004b867  jns     short loc_18004B875
0x18004b869  mov     [rbp+57h+var_7C], 0B12h
0x18004b870  jmp     loc_18004BAE1
0x18004b875  mov     r14, rbx
0x18004b878  test    rbx, rbx
0x18004b87b  jz      short loc_18004B8AF
0x18004b87d  cmp     [rbx], r12b
0x18004b880  jz      short loc_18004B8AF
0x18004b882  or      r9d, 0FFFFFFFFh; cchCount1
0x18004b886  lea     rax, aDefaultconnect_0; "DefaultConnectionSettings"
0x18004b88d  mov     [rsp+0D0h+cchCount2], r9d; cchCount2
0x18004b892  mov     r8, rbx; lpString1
0x18004b895  mov     edx, r15d; dwCmpFlags
0x18004b898  mov     [rsp+0D0h+lpString2], rax; lpString2
0x18004b89d  mov     ecx, 7Fh; Locale
0x18004b8a2  call    cs:__imp_CompareStringA
0x18004b8a8  cmp     eax, 2
0x18004b8ab  jz      short loc_18004B8B6
0x18004b8ad  jmp     short loc_18004B8B9
0x18004b8af  lea     r14, aDefaultconnect_0; "DefaultConnectionSettings"
0x18004b8b6  mov     r12d, r15d
0x18004b8b9  mov     ecx, 3; samDesired
0x18004b8be  call    ?FindWinInetBaseProxyKey@@YAPEAUHKEY__@@K@Z; FindWinInetBaseProxyKey(ulong)
0x18004b8c3  mov     r15, rax
0x18004b8c6  xor     eax, eax
0x18004b8c8  test    r15, r15
0x18004b8cb  jnz     short loc_18004B8FB
0x18004b8cd  test    byte ptr cs:xmmword_180107A60, 20h
0x18004b8d4  jz      short loc_18004B8EA
0x18004b8d6  lea     edx, [rax+43h]
0x18004b8d9  mov     ecx, 405h
0x18004b8de  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x18004b8e5  call    WPP_SF_
0x18004b8ea  mov     edi, 80070002h
0x18004b8ef  mov     [rbp+57h+var_7C], 0B2Ch
0x18004b8f6  jmp     loc_18004BAE1
0x18004b8fb  mov     [rsp+0D0h+var_98], rax; int *
0x18004b900  lea     rcx, [rbp+57h+phkResult]; phkResult
0x18004b904  mov     [rsp+0D0h+var_A0], rax; struct _FILETIME *
0x18004b909  xor     r9d, r9d; unsigned int
0x18004b90c  xor     r8d, r8d; HKEY
0x18004b90f  mov     qword ptr [rsp+0D0h+cchCount2], r14; lpValueName
0x18004b914  mov     rdx, r15; hKey
0x18004b917  call    ?Init@CRegBlob@@QEAAKPEAUHKEY__@@0KPEBGPEBDPEAU_FILETIME@@PEAH@Z; CRegBlob::Init(HKEY__ *,HKEY__ *,ulong,ushort const *,char const *,_FILETIME *,int *)
0x18004b91c  mov     edi, eax
0x18004b91e  cmp     eax, 2
0x18004b921  jz      short loc_18004B996
0x18004b923  test    eax, eax
0x18004b925  jle     short loc_18004B932
0x18004b927  movzx   edi, di
0x18004b92a  or      edi, 80070000h
0x18004b930  test    edi, edi
0x18004b932  jns     short loc_18004B940
0x18004b934  mov     [rbp+57h+var_7C], 0B3Ch
0x18004b93b  jmp     loc_18004BAC0
0x18004b940  mov     edi, 4
0x18004b945  lea     rdx, [rbp+57h+var_80]; void *
0x18004b949  mov     r8d, edi; unsigned int
0x18004b94c  lea     rcx, [rbp+57h+phkResult]; this
0x18004b950  call    ?ReadBytes@CRegBlob@@QEAAKPEAXK@Z; CRegBlob::ReadBytes(void *,ulong)
0x18004b955  mov     r8d, edi; unsigned int
0x18004b958  lea     rdx, [rbp+57h+var_78]; void *
0x18004b95c  lea     rcx, [rbp+57h+phkResult]; this
0x18004b960  call    ?ReadBytes@CRegBlob@@QEAAKPEAXK@Z; CRegBlob::ReadBytes(void *,ulong)
0x18004b965  mov     eax, [rbp+57h+var_78]
0x18004b968  lea     edx, [rdi-3]
0x18004b96b  test    eax, eax
0x18004b96d  cmovz   eax, edx
0x18004b970  cmp     eax, [rsi+8]
0x18004b973  jz      short loc_18004B99B
0x18004b975  test    r13d, r13d
0x18004b978  jnz     short loc_18004B991
0x18004b97a  cmp     [rbp+57h+var_80], 46h ; 'F'
0x18004b97e  jnz     short loc_18004B991
0x18004b980  mov     edi, 8007000Dh
0x18004b985  mov     [rbp+57h+var_7C], 0B5Dh
0x18004b98c  jmp     loc_18004BAC0
0x18004b991  mov     [rsi+8], eax
0x18004b994  jmp     short loc_18004B99B
0x18004b996  mov     edx, 1
0x18004b99b  add     [rsi+8], edx
0x18004b99e  jnz     short loc_18004B9A3
0x18004b9a0  mov     [rsi+8], edx
0x18004b9a3  test    r12d, r12d
0x18004b9a6  jz      short loc_18004B9B0
0x18004b9a8  mov     rcx, rsi; struct tagProxySettings *
0x18004b9ab  call    ?WriteETWProxyEvent@@YAKPEBUtagProxySettings@@@Z; WriteETWProxyEvent(tagProxySettings const *)
0x18004b9b0  xor     r12d, r12d
0x18004b9b3  cmp     cs:?GlobalIs64BitOs@@3HA, r12d; int GlobalIs64BitOs
0x18004b9ba  jz      loc_18004BA8E
0x18004b9c0  mov     rax, 0FFFFFFFF80000002h
0x18004b9c7  cmp     r15, rax
0x18004b9ca  jnz     loc_18004BA8E
0x18004b9d0  mov     r13, [rbp+57h+var_88]
0x18004b9d4  mov     r9, rax; HKEY
0x18004b9d7  mov     qword ptr [rsp+0D0h+cchCount2], r13; struct CWxGlobalCounters *
0x18004b9dc  mov     edx, 100h; unsigned int
0x18004b9e1  mov     rcx, rsi; struct tagProxySettings *
0x18004b9e4  mov     [rsp+0D0h+lpString2], r14; char *
0x18004b9e9  call    ?WriteWinInetProxySettingsHelper@@YAJPEAUtagProxySettings@@KKPEAUHKEY__@@PEBDPEAVCWxGlobalCounters@@@Z; WriteWinInetProxySettingsHelper(tagProxySettings *,ulong,ulong,HKEY__ *,char const *,CWxGlobalCounters *)
0x18004b9ee  mov     edi, eax
0x18004b9f0  test    eax, eax
0x18004b9f2  jns     short loc_18004BA00
0x18004b9f4  mov     [rbp+57h+var_7C], 0B97h
0x18004b9fb  jmp     loc_18004BAE1
0x18004ba00  mov     ecx, 14Ch
0x18004ba05  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18004ba0b  mov     edx, 200h; unsigned int
0x18004ba10  mov     qword ptr [rsp+0D0h+cchCount2], r13; struct CWxGlobalCounters *
0x18004ba15  mov     r9, 0FFFFFFFF80000002h; HKEY
0x18004ba1c  mov     [rsp+0D0h+lpString2], r14; char *
0x18004ba21  mov     rcx, rsi; struct tagProxySettings *
0x18004ba24  movzx   r12d, ax
0x18004ba28  call    ?WriteWinInetProxySettingsHelper@@YAJPEAUtagProxySettings@@KKPEAUHKEY__@@PEBDPEAVCWxGlobalCounters@@@Z; WriteWinInetProxySettingsHelper(tagProxySettings *,ulong,ulong,HKEY__ *,char const *,CWxGlobalCounters *)
0x18004ba2d  mov     edi, eax
0x18004ba2f  xor     eax, eax
0x18004ba31  test    edi, edi
0x18004ba33  jns     short loc_18004BA3E
0x18004ba35  mov     [rbp+57h+var_7C], 0BA1h
0x18004ba3c  jmp     short loc_18004BA7C
0x18004ba3e  cmp     cs:?GlobalIsArm64@@3HA, eax; int GlobalIsArm64
0x18004ba44  jz      short loc_18004BA7C
0x18004ba46  mov     ecx, 1C4h
0x18004ba4b  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18004ba51  mov     edx, 200h; unsigned int
0x18004ba56  mov     qword ptr [rsp+0D0h+cchCount2], r13; struct CWxGlobalCounters *
0x18004ba5b  mov     r9, 0FFFFFFFF80000002h; HKEY
0x18004ba62  mov     [rsp+0D0h+lpString2], r14; char *
0x18004ba67  mov     rcx, rsi; struct tagProxySettings *
0x18004ba6a  call    ?WriteWinInetProxySettingsHelper@@YAJPEAUtagProxySettings@@KKPEAUHKEY__@@PEBDPEAVCWxGlobalCounters@@@Z; WriteWinInetProxySettingsHelper(tagProxySettings *,ulong,ulong,HKEY__ *,char const *,CWxGlobalCounters *)
0x18004ba6f  mov     edi, eax
0x18004ba71  test    eax, eax
0x18004ba73  jns     short loc_18004BA7C
0x18004ba75  mov     [rbp+57h+var_7C], 0BABh
0x18004ba7c  test    r12w, r12w
0x18004ba80  jz      short loc_18004BABB
0x18004ba82  movzx   ecx, r12w
0x18004ba86  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18004ba8c  jmp     short loc_18004BABB
0x18004ba8e  mov     rax, [rbp+57h+var_88]
0x18004ba92  mov     r9, r15; HKEY
0x18004ba95  mov     qword ptr [rsp+0D0h+cchCount2], rax; struct CWxGlobalCounters *
0x18004ba9a  xor     edx, edx; unsigned int
0x18004ba9c  mov     rcx, rsi; struct tagProxySettings *
0x18004ba9f  mov     [rsp+0D0h+lpString2], r14; char *
0x18004baa4  call    ?WriteWinInetProxySettingsHelper@@YAJPEAUtagProxySettings@@KKPEAUHKEY__@@PEBDPEAVCWxGlobalCounters@@@Z; WriteWinInetProxySettingsHelper(tagProxySettings *,ulong,ulong,HKEY__ *,char const *,CWxGlobalCounters *)
0x18004baa9  mov     edi, eax
0x18004baab  test    eax, eax
0x18004baad  jns     short loc_18004BAB8
0x18004baaf  mov     [rbp+57h+var_7C], 0B88h
0x18004bab6  jmp     short loc_18004BAC0
0x18004bab8  mov     edi, r12d
0x18004babb  call    ?WxProxyConfigChangeNotification@@YAKXZ; WxProxyConfigChangeNotification(void)
0x18004bac0  cmp     r15, 0FFFFFFFF80000000h
0x18004bac7  jbe     short loc_18004BAD8
0x18004bac9  lea     rax, [r15+7FFFFFFDh]
0x18004bad0  cmp     rax, 7FFFFFFBh
0x18004bad6  ja      short loc_18004BAE1
0x18004bad8  mov     rcx, r15; hKey
0x18004badb  call    cs:__imp_RegCloseKey
0x18004bae1  test    byte ptr cs:xmmword_180107A60, 20h
0x18004bae8  jz      short loc_18004BB03
0x18004baea  mov     edx, 44h ; 'D'
0x18004baef  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x18004baf6  mov     ecx, 405h
0x18004bafb  mov     r9d, edi
0x18004bafe  call    WPP_SF_d
0x18004bb03  lea     rcx, ?g_srwProxyReg@@3VWxSrw@@A; SRWLock
0x18004bb0a  call    cs:__imp_ReleaseSRWLockExclusive
0x18004bb10  test    rbx, rbx
0x18004bb13  jz      short loc_18004BB1E
0x18004bb15  lea     rcx, [rbp+57h+lpString1]
0x18004bb19  call    WxFreeHeapEx
0x18004bb1e  lea     rcx, [rbp+57h+phkResult]; this
0x18004bb22  call    ??1CRegBlob@@QEAA@XZ; CRegBlob::~CRegBlob(void)
0x18004bb27  mov     eax, edi
0x18004bb29  mov     rcx, [rbp+57h+var_40]
0x18004bb2d  xor     rcx, rsp; StackCookie
0x18004bb30  call    __security_check_cookie
0x18004bb35  mov     rbx, [rsp+0D0h+arg_8]
0x18004bb3d  add     rsp, 0A0h
0x18004bb44  pop     r15
0x18004bb46  pop     r14
0x18004bb48  pop     r13
0x18004bb4a  pop     r12
0x18004bb4c  pop     rdi
0x18004bb4d  pop     rsi
0x18004bb4e  pop     rbp
0x18004bb4f  retn
```
