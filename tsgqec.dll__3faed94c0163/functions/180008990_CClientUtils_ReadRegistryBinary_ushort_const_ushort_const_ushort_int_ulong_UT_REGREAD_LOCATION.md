# CClientUtils::ReadRegistryBinary(ushort const *,ushort const *,ushort *,int,ulong *,UT_REGREAD_LOCATION)

- ea: `0x180008990`
- end: `0x180008bba`
- name: `?ReadRegistryBinary@CClientUtils@@UEAAHPEBG0PEAGHPEAKW4UT_REGREAD_LOCATION@@@Z`
- size: `554`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int, unsigned int *, enum UT_REGREAD_LOCATION)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x1800053ac`
- `0x18000594c`
- `0x180008990`
- `0x180008bc0`
- `0x18000a8ac`
- `0x18000aac4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180008ba2`
- `ADVAPI32!RegCloseKey` at `0x180008ba2`

## string_xrefs

- `0x180008a18`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::ReadRegistryBinary(
        __int64 a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4,
        DWORD a5,
        unsigned int *a6,
        int a7)
{
  unsigned int RegistryEntry; // ebx
  int v8; // esi
  int AppContainerRegistryLocation; // eax
  char v13; // di
  int CurrentThreadActivityIdPrefix; // eax
  DWORD v15; // edi
  unsigned int v16; // eax
  unsigned int v17; // eax
  HKEY hKey; // [rsp+40h] [rbp-48h] BYREF

  RegistryEntry = 0;
  v8 = 0;
  hKey = 0;
  if ( (a7 & 0xFFFFFFFD) != 0 )
  {
    v15 = a5;
  }
  else
  {
    if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
    {
      AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
      v13 = AppContainerRegistryLocation;
      if ( AppContainerRegistryLocation < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)WPP_46feef82db693a9214302820d1cc2cac_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"Unable to get AppContainer registry location.",
            v13);
        }
        goto LABEL_26;
      }
      v15 = a5;
      RegistryEntry = CClientUtils::ReadRegistryEntry(hKey, a2, a3, a4, a5, 3, a6, 0);
      if ( RegistryEntry )
        goto LABEL_26;
    }
    else
    {
      v15 = a5;
    }
    RegistryEntry = CClientUtils::ReadRegistryEntry(HKEY_CURRENT_USER, a2, a3, a4, v15, 3, a6, 0);
    if ( !RegistryEntry )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v16);
      }
      v8 = 1;
    }
  }
  if ( a7 == 1 || a7 == 2 && v8 )
  {
    RegistryEntry = CClientUtils::ReadRegistryEntry(HKEY_LOCAL_MACHINE, a2, a3, a4, v15, 3, a6, 0);
    if ( !RegistryEntry
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v17);
    }
  }
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
  return RegistryEntry;
}

```

## disassembly

```asm
0x180008990  push    rbx
0x180008992  push    rsi
0x180008993  push    rdi
0x180008994  push    r12
0x180008996  push    r13
0x180008998  push    r14
0x18000899a  push    r15
0x18000899c  sub     rsp, 50h
0x1800089a0  mov     r13, [rsp+88h+arg_28]
0x1800089a8  xor     ebx, ebx
0x1800089aa  xor     esi, esi
0x1800089ac  mov     [rsp+88h+hKey], rbx
0x1800089b1  test    [rsp+88h+arg_30], 0FFFFFFFDh
0x1800089bc  mov     r14, r9
0x1800089bf  mov     r15, r8
0x1800089c2  mov     r12, rdx
0x1800089c5  jnz     loc_180008B04
0x1800089cb  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1800089d0  test    eax, eax
0x1800089d2  jz      loc_180008A85
0x1800089d8  lea     rcx, [rsp+88h+hKey]; HKEY *
0x1800089dd  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1800089e2  mov     edi, eax
0x1800089e4  test    eax, eax
0x1800089e6  jns     short loc_180008A4A
0x1800089e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089ef  lea     rax, WPP_GLOBAL_Control
0x1800089f6  cmp     rcx, rax
0x1800089f9  jz      loc_180008B98
0x1800089ff  test    byte ptr [rcx+1Ch], 8
0x180008a03  jz      loc_180008B98
0x180008a09  cmp     byte ptr [rcx+19h], 2
0x180008a0d  jb      loc_180008B98
0x180008a13  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008a18  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x180008a1f  mov     dword ptr [rsp+88h+var_60], edi
0x180008a23  mov     qword ptr [rsp+88h+var_68], rcx
0x180008a28  lea     edx, [rbx+15h]
0x180008a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a32  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180008a39  mov     r9d, eax
0x180008a3c  mov     rcx, [rcx+10h]
0x180008a40  call    WPP_SF_DsD
0x180008a45  jmp     loc_180008B98
0x180008a4a  mov     edi, [rsp+88h+arg_20]
0x180008a51  mov     r9, r14; lpData
0x180008a54  mov     rcx, [rsp+88h+hKey]; hKey
0x180008a59  mov     r8, r15; unsigned __int16 *
0x180008a5c  mov     [rsp+88h+var_50], ebx; int
0x180008a60  mov     rdx, r12; unsigned __int16 *
0x180008a63  mov     [rsp+88h+var_58], r13; unsigned int *
0x180008a68  mov     dword ptr [rsp+88h+var_60], 3; char
0x180008a70  mov     [rsp+88h+var_68], edi; int
0x180008a74  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180008a79  mov     ebx, eax
0x180008a7b  test    eax, eax
0x180008a7d  jnz     loc_180008B98
0x180008a83  jmp     short loc_180008A8C
0x180008a85  mov     edi, [rsp+88h+arg_20]
0x180008a8c  mov     [rsp+88h+var_50], esi; int
0x180008a90  mov     r9, r14; lpData
0x180008a93  mov     [rsp+88h+var_58], r13; unsigned int *
0x180008a98  mov     r8, r15; unsigned __int16 *
0x180008a9b  mov     dword ptr [rsp+88h+var_60], 3; char
0x180008aa3  mov     rdx, r12; unsigned __int16 *
0x180008aa6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180008aad  mov     [rsp+88h+var_68], edi; int
0x180008ab1  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180008ab6  mov     ebx, eax
0x180008ab8  test    eax, eax
0x180008aba  jnz     short loc_180008B0B
0x180008abc  mov     rax, cs:WPP_GLOBAL_Control
0x180008ac3  lea     rcx, WPP_GLOBAL_Control
0x180008aca  cmp     rax, rcx
0x180008acd  jz      short loc_180008AFD
0x180008acf  test    byte ptr [rax+1Ch], 1
0x180008ad3  jz      short loc_180008AFD
0x180008ad5  cmp     byte ptr [rax+19h], 4
0x180008ad9  jb      short loc_180008AFD
0x180008adb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ae7  lea     edx, [rbx+16h]
0x180008aea  mov     r9d, eax
0x180008aed  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180008af4  mov     rcx, [rcx+10h]
0x180008af8  call    WPP_SF_D
0x180008afd  mov     esi, 1
0x180008b02  jmp     short loc_180008B0B
0x180008b04  mov     edi, [rsp+88h+arg_20]
0x180008b0b  cmp     [rsp+88h+arg_30], 1
0x180008b13  jz      short loc_180008B23
0x180008b15  cmp     [rsp+88h+arg_30], 2
0x180008b1d  jnz     short loc_180008B98
0x180008b1f  test    esi, esi
0x180008b21  jz      short loc_180008B98
0x180008b23  mov     [rsp+88h+var_50], 0; int
0x180008b2b  mov     r9, r14; lpData
0x180008b2e  mov     [rsp+88h+var_58], r13; unsigned int *
0x180008b33  mov     r8, r15; unsigned __int16 *
0x180008b36  mov     dword ptr [rsp+88h+var_60], 3; char
0x180008b3e  mov     rdx, r12; unsigned __int16 *
0x180008b41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008b48  mov     [rsp+88h+var_68], edi; int
0x180008b4c  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180008b51  mov     ebx, eax
0x180008b53  test    eax, eax
0x180008b55  jnz     short loc_180008B98
0x180008b57  mov     rax, cs:WPP_GLOBAL_Control
0x180008b5e  lea     rcx, WPP_GLOBAL_Control
0x180008b65  cmp     rax, rcx
0x180008b68  jz      short loc_180008B98
0x180008b6a  test    byte ptr [rax+1Ch], 1
0x180008b6e  jz      short loc_180008B98
0x180008b70  cmp     byte ptr [rax+19h], 4
0x180008b74  jb      short loc_180008B98
0x180008b76  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b82  lea     edx, [rbx+17h]
0x180008b85  mov     r9d, eax
0x180008b88  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180008b8f  mov     rcx, [rcx+10h]
0x180008b93  call    WPP_SF_D
0x180008b98  mov     rcx, [rsp+88h+hKey]; hKey
0x180008b9d  test    rcx, rcx
0x180008ba0  jz      short loc_180008BA8
0x180008ba2  call    cs:__imp_RegCloseKey
0x180008ba8  mov     eax, ebx
0x180008baa  add     rsp, 50h
0x180008bae  pop     r15
0x180008bb0  pop     r14
0x180008bb2  pop     r13
0x180008bb4  pop     r12
0x180008bb6  pop     rdi
0x180008bb7  pop     rsi
0x180008bb8  pop     rbx
0x180008bb9  retn
```
