# CClientUtils::StealthReadRegistryString(ushort const *,ushort const *,ushort *,int,UT_REGREAD_LOCATION)

- ea: `0x180009960`
- end: `0x180009bb5`
- name: `?StealthReadRegistryString@CClientUtils@@UEAAHPEBG0PEAGHW4UT_REGREAD_LOCATION@@@Z`
- size: `597`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int, enum UT_REGREAD_LOCATION)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x1800053ac`
- `0x18000594c`
- `0x180008bc0`
- `0x1800095c8`
- `0x180009960`
- `0x18000a8ac`
- `0x18000aac4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180009b9e`
- `ADVAPI32!RegCloseKey` at `0x180009b9e`

## string_xrefs

- `0x1800099ea`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::StealthReadRegistryString(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        BYTE *a4,
        DWORD a5,
        int a6)
{
  unsigned int RegistryEntry; // ebx
  int v7; // esi
  int AppContainerRegistryLocation; // eax
  char v12; // di
  int CurrentThreadActivityIdPrefix; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  HKEY hKey; // [rsp+40h] [rbp-48h] BYREF

  RegistryEntry = 0;
  v7 = 0;
  hKey = 0;
  if ( (a6 & 0xFFFFFFFD) != 0 )
    goto LABEL_17;
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
          33,
          (unsigned int)WPP_46feef82db693a9214302820d1cc2cac_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v12);
      }
      goto LABEL_26;
    }
    if ( (unsigned int)CClientUtils::RegistryEntryExists(hKey, a2, (char *)a3) )
    {
      RegistryEntry = CClientUtils::ReadRegistryEntry(hKey, a2, a3, a4, a5, 1, 0, 0);
      if ( RegistryEntry )
        goto LABEL_26;
    }
  }
  if ( (unsigned int)CClientUtils::RegistryEntryExists(HKEY_CURRENT_USER, a2, (char *)a3) )
  {
    RegistryEntry = CClientUtils::ReadRegistryEntry(HKEY_CURRENT_USER, a2, a3, a4, a5, 1, 0, 0);
    if ( RegistryEntry )
      goto LABEL_17;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v14);
    }
  }
  v7 = 1;
LABEL_17:
  if ( a6 == 1 || a6 == 2 && v7 )
  {
    if ( (unsigned int)CClientUtils::RegistryEntryExists(HKEY_LOCAL_MACHINE, a2, (char *)a3) )
    {
      RegistryEntry = CClientUtils::ReadRegistryEntry(HKEY_LOCAL_MACHINE, a2, a3, a4, a5, 1, 0, 0);
      if ( !RegistryEntry
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v15);
      }
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
0x180009960  push    rbx
0x180009962  push    rbp
0x180009963  push    rsi
0x180009964  push    rdi
0x180009965  push    r12
0x180009967  push    r13
0x180009969  push    r14
0x18000996b  sub     rsp, 50h
0x18000996f  mov     r13d, [rsp+88h+arg_20]
0x180009977  xor     ebx, ebx
0x180009979  xor     esi, esi
0x18000997b  mov     [rsp+88h+hKey], rbx
0x180009980  test    [rsp+88h+arg_28], 0FFFFFFFDh
0x18000998b  mov     r12, r9
0x18000998e  mov     rbp, r8
0x180009991  mov     r14, rdx
0x180009994  lea     edi, [rbx+1]
0x180009997  jnz     loc_180009AEA
0x18000999d  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1800099a2  test    eax, eax
0x1800099a4  jz      loc_180009A64
0x1800099aa  lea     rcx, [rsp+88h+hKey]; HKEY *
0x1800099af  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1800099b4  mov     edi, eax
0x1800099b6  test    eax, eax
0x1800099b8  jns     short loc_180009A1C
0x1800099ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099c1  lea     rax, WPP_GLOBAL_Control
0x1800099c8  cmp     rcx, rax
0x1800099cb  jz      loc_180009B94
0x1800099d1  test    byte ptr [rcx+1Ch], 8
0x1800099d5  jz      loc_180009B94
0x1800099db  cmp     byte ptr [rcx+19h], 2
0x1800099df  jb      loc_180009B94
0x1800099e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800099ea  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x1800099f1  mov     dword ptr [rsp+88h+var_60], edi
0x1800099f5  mov     qword ptr [rsp+88h+var_68], rcx
0x1800099fa  lea     edx, [rbx+21h]
0x1800099fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a04  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009a0b  mov     r9d, eax
0x180009a0e  mov     rcx, [rcx+10h]
0x180009a12  call    WPP_SF_DsD
0x180009a17  jmp     loc_180009B94
0x180009a1c  mov     rcx, [rsp+88h+hKey]; hKey
0x180009a21  mov     r8, rbp; unsigned __int16 *
0x180009a24  mov     rdx, r14; unsigned __int16 *
0x180009a27  call    ?RegistryEntryExists@CClientUtils@@KAHPEAUHKEY__@@PEBG1@Z; CClientUtils::RegistryEntryExists(HKEY__ *,ushort const *,ushort const *)
0x180009a2c  mov     edi, 1
0x180009a31  test    eax, eax
0x180009a33  jz      short loc_180009A64
0x180009a35  mov     rcx, [rsp+88h+hKey]; hKey
0x180009a3a  mov     r9, r12; lpData
0x180009a3d  mov     [rsp+88h+var_50], ebx; int
0x180009a41  mov     r8, rbp; unsigned __int16 *
0x180009a44  mov     [rsp+88h+var_58], rbx; unsigned int *
0x180009a49  mov     rdx, r14; unsigned __int16 *
0x180009a4c  mov     dword ptr [rsp+88h+var_60], edi; char
0x180009a50  mov     [rsp+88h+var_68], r13d; int
0x180009a55  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180009a5a  mov     ebx, eax
0x180009a5c  test    eax, eax
0x180009a5e  jnz     loc_180009B94
0x180009a64  mov     r8, rbp; unsigned __int16 *
0x180009a67  mov     rdx, r14; unsigned __int16 *
0x180009a6a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009a71  call    ?RegistryEntryExists@CClientUtils@@KAHPEAUHKEY__@@PEBG1@Z; CClientUtils::RegistryEntryExists(HKEY__ *,ushort const *,ushort const *)
0x180009a76  test    eax, eax
0x180009a78  jz      short loc_180009AE8
0x180009a7a  mov     [rsp+88h+var_50], esi; int
0x180009a7e  mov     r9, r12; lpData
0x180009a81  mov     [rsp+88h+var_58], rsi; unsigned int *
0x180009a86  mov     r8, rbp; unsigned __int16 *
0x180009a89  mov     dword ptr [rsp+88h+var_60], edi; char
0x180009a8d  mov     rdx, r14; unsigned __int16 *
0x180009a90  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009a97  mov     [rsp+88h+var_68], r13d; int
0x180009a9c  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180009aa1  mov     ebx, eax
0x180009aa3  test    eax, eax
0x180009aa5  jnz     short loc_180009AEA
0x180009aa7  mov     rax, cs:WPP_GLOBAL_Control
0x180009aae  lea     rcx, WPP_GLOBAL_Control
0x180009ab5  cmp     rax, rcx
0x180009ab8  jz      short loc_180009AE8
0x180009aba  test    [rax+1Ch], dil
0x180009abe  jz      short loc_180009AE8
0x180009ac0  cmp     byte ptr [rax+19h], 4
0x180009ac4  jb      short loc_180009AE8
0x180009ac6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ad2  lea     edx, [rbx+22h]
0x180009ad5  mov     r9d, eax
0x180009ad8  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009adf  mov     rcx, [rcx+10h]
0x180009ae3  call    WPP_SF_D
0x180009ae8  mov     esi, edi
0x180009aea  cmp     [rsp+88h+arg_28], edi
0x180009af1  jz      short loc_180009B09
0x180009af3  cmp     [rsp+88h+arg_28], 2
0x180009afb  jnz     loc_180009B94
0x180009b01  test    esi, esi
0x180009b03  jz      loc_180009B94
0x180009b09  mov     rsi, 0FFFFFFFF80000002h
0x180009b10  mov     r8, rbp; unsigned __int16 *
0x180009b13  mov     rcx, rsi; hKey
0x180009b16  mov     rdx, r14; unsigned __int16 *
0x180009b19  call    ?RegistryEntryExists@CClientUtils@@KAHPEAUHKEY__@@PEBG1@Z; CClientUtils::RegistryEntryExists(HKEY__ *,ushort const *,ushort const *)
0x180009b1e  test    eax, eax
0x180009b20  jz      short loc_180009B94
0x180009b22  mov     [rsp+88h+var_50], 0; int
0x180009b2a  mov     r9, r12; lpData
0x180009b2d  mov     [rsp+88h+var_58], 0; unsigned int *
0x180009b36  mov     r8, rbp; unsigned __int16 *
0x180009b39  mov     dword ptr [rsp+88h+var_60], edi; char
0x180009b3d  mov     rdx, r14; unsigned __int16 *
0x180009b40  mov     rcx, rsi; hKey
0x180009b43  mov     [rsp+88h+var_68], r13d; int
0x180009b48  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180009b4d  mov     ebx, eax
0x180009b4f  test    eax, eax
0x180009b51  jnz     short loc_180009B94
0x180009b53  mov     rax, cs:WPP_GLOBAL_Control
0x180009b5a  lea     rcx, WPP_GLOBAL_Control
0x180009b61  cmp     rax, rcx
0x180009b64  jz      short loc_180009B94
0x180009b66  test    [rax+1Ch], dil
0x180009b6a  jz      short loc_180009B94
0x180009b6c  cmp     byte ptr [rax+19h], 4
0x180009b70  jb      short loc_180009B94
0x180009b72  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009b77  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b7e  lea     edx, [rbx+23h]
0x180009b81  mov     r9d, eax
0x180009b84  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009b8b  mov     rcx, [rcx+10h]
0x180009b8f  call    WPP_SF_D
0x180009b94  mov     rcx, [rsp+88h+hKey]; hKey
0x180009b99  test    rcx, rcx
0x180009b9c  jz      short loc_180009BA4
0x180009b9e  call    cs:__imp_RegCloseKey
0x180009ba4  mov     eax, ebx
0x180009ba6  add     rsp, 50h
0x180009baa  pop     r14
0x180009bac  pop     r13
0x180009bae  pop     r12
0x180009bb0  pop     rdi
0x180009bb1  pop     rsi
0x180009bb2  pop     rbp
0x180009bb3  pop     rbx
0x180009bb4  retn
```
