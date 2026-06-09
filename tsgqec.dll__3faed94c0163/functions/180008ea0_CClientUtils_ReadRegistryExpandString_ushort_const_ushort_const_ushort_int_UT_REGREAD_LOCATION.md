# CClientUtils::ReadRegistryExpandString(ushort const *,ushort const *,ushort * *,int *,UT_REGREAD_LOCATION)

- ea: `0x180008ea0`
- end: `0x180009161`
- name: `?ReadRegistryExpandString@CClientUtils@@UEAAHPEBG0PEAPEAGPEAHW4UT_REGREAD_LOCATION@@@Z`
- size: `705`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, int *, enum UT_REGREAD_LOCATION)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x1800053ac`
- `0x18000594c`
- `0x180008bc0`
- `0x180008ea0`
- `0x18000a8ac`
- `0x18000aac4`
- `0x18000aea0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800090a9`
- `ADVAPI32!RegCloseKey` at `0x1800090a9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180009058`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180009085`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180009058`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180009085`
- `KERNEL32!LocalAlloc` at `0x18000906b`
- `KERNEL32!LocalAlloc` at `0x18000906b`

## string_xrefs

- `0x180008f44`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::ReadRegistryExpandString(
        __int64 a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        WCHAR **a4,
        _DWORD *a5,
        int a6)
{
  unsigned int RegistryEntry; // ebx
  int v7; // esi
  int AppContainerRegistryLocation; // eax
  char v12; // di
  int CurrentThreadActivityIdPrefix; // eax
  unsigned int v14; // eax
  DWORD v15; // edi
  WCHAR *v16; // rax
  unsigned int v18; // eax
  HKEY hKey; // [rsp+40h] [rbp-268h] BYREF
  WCHAR Src[264]; // [rsp+50h] [rbp-258h] BYREF

  RegistryEntry = 0;
  v7 = 0;
  hKey = 0;
  if ( (a6 & 0xFFFFFFFD) == 0 )
  {
    if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
    {
      AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
      v12 = AppContainerRegistryLocation;
      if ( AppContainerRegistryLocation < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_46feef82db693a9214302820d1cc2cac_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"Unable to get AppContainer registry location.",
            v12);
        }
        goto LABEL_22;
      }
      RegistryEntry = CClientUtils::ReadRegistryEntry(hKey, a2, a3, (LPBYTE)Src, 0x208u, 2, 0, 0);
      if ( RegistryEntry )
        goto LABEL_22;
    }
    RegistryEntry = CClientUtils::ReadRegistryEntry(HKEY_CURRENT_USER, a2, a3, (LPBYTE)Src, 0x208u, 2, 0, 0);
    if ( !RegistryEntry )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v14);
      }
      v7 = 1;
    }
  }
  if ( a6 != 1 && (a6 != 2 || !v7) )
  {
    if ( !RegistryEntry )
      goto LABEL_22;
    goto LABEL_19;
  }
  RegistryEntry = CClientUtils::ReadRegistryEntry(HKEY_LOCAL_MACHINE, a2, a3, (LPBYTE)Src, 0x208u, 2, 0, 0);
  if ( RegistryEntry )
  {
LABEL_19:
    v15 = ExpandEnvironmentStringsW(Src, 0, 0);
    v16 = (WCHAR *)LocalAlloc(0x40u, 2LL * (v15 + 1));
    *a4 = v16;
    if ( v16 && ExpandEnvironmentStringsW(Src, v16, v15) )
    {
      RegistryEntry = 1;
      *a5 = 2 * v15 + 2;
    }
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v18 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v18);
  }
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  return RegistryEntry;
}

```

## disassembly

```asm
0x180008ea0  push    rbx
0x180008ea2  push    rsi
0x180008ea3  push    rdi
0x180008ea4  push    r12
0x180008ea6  push    r13
0x180008ea8  push    r14
0x180008eaa  push    r15
0x180008eac  sub     rsp, 270h
0x180008eb3  mov     rax, cs:__security_cookie
0x180008eba  xor     rax, rsp
0x180008ebd  mov     [rsp+2A8h+var_48], rax
0x180008ec5  mov     r12, [rsp+2A8h+arg_20]
0x180008ecd  lea     rdi, WPP_GLOBAL_Control
0x180008ed4  xor     ebx, ebx
0x180008ed6  xor     esi, esi
0x180008ed8  test    [rsp+2A8h+arg_28], 0FFFFFFFDh
0x180008ee3  mov     r13, r9
0x180008ee6  mov     r15, r8
0x180008ee9  mov     [rsp+2A8h+hKey], rbx
0x180008eee  mov     r14, rdx
0x180008ef1  jnz     loc_18000902A
0x180008ef7  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x180008efc  test    eax, eax
0x180008efe  jz      loc_180008FB5
0x180008f04  lea     rcx, [rsp+2A8h+hKey]; HKEY *
0x180008f09  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x180008f0e  mov     edi, eax
0x180008f10  test    eax, eax
0x180008f12  jns     short loc_180008F76
0x180008f14  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f1b  lea     rax, WPP_GLOBAL_Control
0x180008f22  cmp     rcx, rax
0x180008f25  jz      loc_18000909F
0x180008f2b  test    byte ptr [rcx+1Ch], 8
0x180008f2f  jz      loc_18000909F
0x180008f35  cmp     byte ptr [rcx+19h], 2
0x180008f39  jb      loc_18000909F
0x180008f3f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008f44  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x180008f4b  mov     dword ptr [rsp+2A8h+var_280], edi
0x180008f4f  mov     qword ptr [rsp+2A8h+var_288], rcx
0x180008f54  lea     edx, [rbx+0Dh]
0x180008f57  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f5e  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180008f65  mov     r9d, eax
0x180008f68  mov     rcx, [rcx+10h]
0x180008f6c  call    WPP_SF_DsD
0x180008f71  jmp     loc_18000909F
0x180008f76  mov     rcx, [rsp+2A8h+hKey]; hKey
0x180008f7b  lea     r9, [rsp+2A8h+Src]; lpData
0x180008f80  mov     [rsp+2A8h+var_270], ebx; int
0x180008f84  mov     r8, r15; unsigned __int16 *
0x180008f87  mov     [rsp+2A8h+var_278], rbx; unsigned int *
0x180008f8c  mov     rdx, r14; unsigned __int16 *
0x180008f8f  mov     dword ptr [rsp+2A8h+var_280], 2; char
0x180008f97  mov     [rsp+2A8h+var_288], 208h; int
0x180008f9f  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180008fa4  mov     ebx, eax
0x180008fa6  test    eax, eax
0x180008fa8  jnz     loc_18000909F
0x180008fae  lea     rdi, WPP_GLOBAL_Control
0x180008fb5  mov     [rsp+2A8h+var_270], esi; int
0x180008fb9  lea     r9, [rsp+2A8h+Src]; lpData
0x180008fbe  mov     [rsp+2A8h+var_278], rsi; unsigned int *
0x180008fc3  mov     r8, r15; unsigned __int16 *
0x180008fc6  mov     dword ptr [rsp+2A8h+var_280], 2; char
0x180008fce  mov     rdx, r14; unsigned __int16 *
0x180008fd1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180008fd8  mov     [rsp+2A8h+var_288], 208h; int
0x180008fe0  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180008fe5  mov     ebx, eax
0x180008fe7  test    eax, eax
0x180008fe9  jnz     short loc_18000902A
0x180008feb  mov     rax, cs:WPP_GLOBAL_Control
0x180008ff2  cmp     rax, rdi
0x180008ff5  jz      short loc_180009025
0x180008ff7  test    byte ptr [rax+1Ch], 1
0x180008ffb  jz      short loc_180009025
0x180008ffd  cmp     byte ptr [rax+19h], 4
0x180009001  jb      short loc_180009025
0x180009003  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009008  mov     rcx, cs:WPP_GLOBAL_Control
0x18000900f  lea     edx, [rbx+0Eh]
0x180009012  mov     r9d, eax
0x180009015  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x18000901c  mov     rcx, [rcx+10h]
0x180009020  call    WPP_SF_D
0x180009025  mov     esi, 1
0x18000902a  cmp     [rsp+2A8h+arg_28], 1
0x180009032  jz      loc_1800090D4
0x180009038  cmp     [rsp+2A8h+arg_28], 2
0x180009040  jnz     short loc_18000904A
0x180009042  test    esi, esi
0x180009044  jnz     loc_1800090D4
0x18000904a  test    ebx, ebx
0x18000904c  jz      short loc_18000909F
0x18000904e  xor     r8d, r8d; nSize
0x180009051  lea     rcx, [rsp+2A8h+Src]; lpSrc
0x180009056  xor     edx, edx; lpDst
0x180009058  call    cs:__imp_ExpandEnvironmentStringsW
0x18000905e  mov     ecx, 40h ; '@'; uFlags
0x180009063  mov     edi, eax
0x180009065  lea     edx, [rax+1]
0x180009068  add     rdx, rdx; uBytes
0x18000906b  call    cs:__imp_LocalAlloc
0x180009071  mov     [r13+0], rax
0x180009075  test    rax, rax
0x180009078  jz      short loc_18000909F
0x18000907a  mov     r8d, edi; nSize
0x18000907d  lea     rcx, [rsp+2A8h+Src]; lpSrc
0x180009082  mov     rdx, rax; lpDst
0x180009085  call    cs:__imp_ExpandEnvironmentStringsW
0x18000908b  test    eax, eax
0x18000908d  jz      short loc_18000909F
0x18000908f  lea     eax, ds:2[rdi*2]
0x180009096  mov     ebx, 1
0x18000909b  mov     [r12], eax
0x18000909f  mov     rcx, [rsp+2A8h+hKey]; hKey
0x1800090a4  test    rcx, rcx
0x1800090a7  jz      short loc_1800090AF
0x1800090a9  call    cs:__imp_RegCloseKey
0x1800090af  mov     eax, ebx
0x1800090b1  mov     rcx, [rsp+2A8h+var_48]
0x1800090b9  xor     rcx, rsp; StackCookie
0x1800090bc  call    __security_check_cookie
0x1800090c1  add     rsp, 270h
0x1800090c8  pop     r15
0x1800090ca  pop     r14
0x1800090cc  pop     r13
0x1800090ce  pop     r12
0x1800090d0  pop     rdi
0x1800090d1  pop     rsi
0x1800090d2  pop     rbx
0x1800090d3  retn
0x1800090d4  mov     [rsp+2A8h+var_270], 0; int
0x1800090dc  lea     r9, [rsp+2A8h+Src]; lpData
0x1800090e1  mov     [rsp+2A8h+var_278], 0; unsigned int *
0x1800090ea  mov     r8, r15; unsigned __int16 *
0x1800090ed  mov     dword ptr [rsp+2A8h+var_280], 2; char
0x1800090f5  mov     rdx, r14; unsigned __int16 *
0x1800090f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800090ff  mov     [rsp+2A8h+var_288], 208h; int
0x180009107  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x18000910c  mov     ebx, eax
0x18000910e  test    eax, eax
0x180009110  jnz     loc_18000904E
0x180009116  mov     rax, cs:WPP_GLOBAL_Control
0x18000911d  cmp     rax, rdi
0x180009120  jz      loc_18000909F
0x180009126  test    byte ptr [rax+1Ch], 1
0x18000912a  jz      loc_18000909F
0x180009130  cmp     byte ptr [rax+19h], 4
0x180009134  jb      loc_18000909F
0x18000913a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000913f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009146  lea     edx, [rbx+0Fh]
0x180009149  mov     r9d, eax
0x18000914c  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009153  mov     rcx, [rcx+10h]
0x180009157  call    WPP_SF_D
0x18000915c  jmp     loc_18000909F
```
