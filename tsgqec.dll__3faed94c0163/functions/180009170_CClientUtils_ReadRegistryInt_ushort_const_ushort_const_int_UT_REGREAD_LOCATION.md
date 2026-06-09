# CClientUtils::ReadRegistryInt(ushort const *,ushort const *,int *,UT_REGREAD_LOCATION)

- ea: `0x180009170`
- end: `0x180009375`
- name: `?ReadRegistryInt@CClientUtils@@UEAAHPEBG0PEAHW4UT_REGREAD_LOCATION@@@Z`
- size: `517`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, int *, enum UT_REGREAD_LOCATION)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x1800053ac`
- `0x18000594c`
- `0x180008bc0`
- `0x180009170`
- `0x18000a8ac`
- `0x18000aac4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000935f`
- `ADVAPI32!RegCloseKey` at `0x18000935f`

## string_xrefs

- `0x1800091f1`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::ReadRegistryInt(
        __int64 a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4,
        int a5)
{
  unsigned int RegistryEntry; // ebx
  int v6; // esi
  int AppContainerRegistryLocation; // eax
  char v11; // di
  int CurrentThreadActivityIdPrefix; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  HKEY hKey; // [rsp+40h] [rbp-48h] BYREF

  RegistryEntry = 0;
  v6 = 0;
  hKey = 0;
  if ( (a5 & 0xFFFFFFFD) == 0 )
  {
    if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
    {
      AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
      v11 = AppContainerRegistryLocation;
      if ( AppContainerRegistryLocation < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)WPP_46feef82db693a9214302820d1cc2cac_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"Unable to get AppContainer registry location.",
            v11);
        }
        goto LABEL_23;
      }
      RegistryEntry = CClientUtils::ReadRegistryEntry(hKey, a2, a3, a4, 4u, 4, 0, 0);
      if ( RegistryEntry )
        goto LABEL_23;
    }
    RegistryEntry = CClientUtils::ReadRegistryEntry(HKEY_CURRENT_USER, a2, a3, a4, 4u, 4, 0, 0);
    if ( !RegistryEntry )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v13);
      }
      v6 = 1;
    }
  }
  if ( a5 == 1 || a5 == 2 && v6 )
  {
    RegistryEntry = CClientUtils::ReadRegistryEntry(HKEY_LOCAL_MACHINE, a2, a3, a4, 4u, 4, 0, 0);
    if ( !RegistryEntry
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v14);
    }
  }
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  return RegistryEntry;
}

```

## disassembly

```asm
0x180009170  push    rbx
0x180009172  push    rsi
0x180009173  push    rdi
0x180009174  push    r12
0x180009176  push    r14
0x180009178  push    r15
0x18000917a  sub     rsp, 58h
0x18000917e  xor     ebx, ebx
0x180009180  xor     esi, esi
0x180009182  test    [rsp+88h+arg_20], 0FFFFFFFDh
0x18000918d  mov     r14, r9
0x180009190  mov     r15, r8
0x180009193  mov     [rsp+88h+hKey], rbx
0x180009198  mov     r12, rdx
0x18000919b  lea     edi, [rbx+4]
0x18000919e  jnz     loc_1800092C8
0x1800091a4  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1800091a9  test    eax, eax
0x1800091ab  jz      loc_180009256
0x1800091b1  lea     rcx, [rsp+88h+hKey]; HKEY *
0x1800091b6  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1800091bb  mov     edi, eax
0x1800091bd  test    eax, eax
0x1800091bf  jns     short loc_180009223
0x1800091c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091c8  lea     rax, WPP_GLOBAL_Control
0x1800091cf  cmp     rcx, rax
0x1800091d2  jz      loc_180009355
0x1800091d8  test    byte ptr [rcx+1Ch], 8
0x1800091dc  jz      loc_180009355
0x1800091e2  cmp     byte ptr [rcx+19h], 2
0x1800091e6  jb      loc_180009355
0x1800091ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800091f1  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x1800091f8  mov     dword ptr [rsp+88h+var_60], edi
0x1800091fc  mov     qword ptr [rsp+88h+var_68], rcx
0x180009201  lea     edx, [rbx+12h]
0x180009204  mov     rcx, cs:WPP_GLOBAL_Control
0x18000920b  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009212  mov     r9d, eax
0x180009215  mov     rcx, [rcx+10h]
0x180009219  call    WPP_SF_DsD
0x18000921e  jmp     loc_180009355
0x180009223  mov     rcx, [rsp+88h+hKey]; hKey
0x180009228  mov     edi, 4
0x18000922d  mov     [rsp+88h+var_50], ebx; int
0x180009231  mov     r9, r14; lpData
0x180009234  mov     [rsp+88h+var_58], rbx; unsigned int *
0x180009239  mov     r8, r15; unsigned __int16 *
0x18000923c  mov     dword ptr [rsp+88h+var_60], edi; char
0x180009240  mov     rdx, r12; unsigned __int16 *
0x180009243  mov     [rsp+88h+var_68], edi; int
0x180009247  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x18000924c  mov     ebx, eax
0x18000924e  test    eax, eax
0x180009250  jnz     loc_180009355
0x180009256  mov     [rsp+88h+var_50], esi; int
0x18000925a  mov     r9, r14; lpData
0x18000925d  mov     [rsp+88h+var_58], rsi; unsigned int *
0x180009262  mov     r8, r15; unsigned __int16 *
0x180009265  mov     dword ptr [rsp+88h+var_60], edi; char
0x180009269  mov     rdx, r12; unsigned __int16 *
0x18000926c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009273  mov     [rsp+88h+var_68], edi; int
0x180009277  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x18000927c  mov     ebx, eax
0x18000927e  test    eax, eax
0x180009280  jnz     short loc_1800092C8
0x180009282  mov     rax, cs:WPP_GLOBAL_Control
0x180009289  lea     rcx, WPP_GLOBAL_Control
0x180009290  cmp     rax, rcx
0x180009293  jz      short loc_1800092C3
0x180009295  test    byte ptr [rax+1Ch], 1
0x180009299  jz      short loc_1800092C3
0x18000929b  cmp     [rax+19h], dil
0x18000929f  jb      short loc_1800092C3
0x1800092a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800092a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092ad  lea     edx, [rbx+13h]
0x1800092b0  mov     r9d, eax
0x1800092b3  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x1800092ba  mov     rcx, [rcx+10h]
0x1800092be  call    WPP_SF_D
0x1800092c3  mov     esi, 1
0x1800092c8  cmp     [rsp+88h+arg_20], 1
0x1800092d0  jz      short loc_1800092E0
0x1800092d2  cmp     [rsp+88h+arg_20], 2
0x1800092da  jnz     short loc_180009355
0x1800092dc  test    esi, esi
0x1800092de  jz      short loc_180009355
0x1800092e0  mov     [rsp+88h+var_50], 0; int
0x1800092e8  mov     r9, r14; lpData
0x1800092eb  mov     [rsp+88h+var_58], 0; unsigned int *
0x1800092f4  mov     r8, r15; unsigned __int16 *
0x1800092f7  mov     dword ptr [rsp+88h+var_60], edi; char
0x1800092fb  mov     rdx, r12; unsigned __int16 *
0x1800092fe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009305  mov     [rsp+88h+var_68], edi; int
0x180009309  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x18000930e  mov     ebx, eax
0x180009310  test    eax, eax
0x180009312  jnz     short loc_180009355
0x180009314  mov     rax, cs:WPP_GLOBAL_Control
0x18000931b  lea     rcx, WPP_GLOBAL_Control
0x180009322  cmp     rax, rcx
0x180009325  jz      short loc_180009355
0x180009327  test    byte ptr [rax+1Ch], 1
0x18000932b  jz      short loc_180009355
0x18000932d  cmp     [rax+19h], dil
0x180009331  jb      short loc_180009355
0x180009333  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009338  mov     rcx, cs:WPP_GLOBAL_Control
0x18000933f  lea     edx, [rbx+14h]
0x180009342  mov     r9d, eax
0x180009345  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x18000934c  mov     rcx, [rcx+10h]
0x180009350  call    WPP_SF_D
0x180009355  mov     rcx, [rsp+88h+hKey]; hKey
0x18000935a  test    rcx, rcx
0x18000935d  jz      short loc_180009365
0x18000935f  call    cs:__imp_RegCloseKey
0x180009365  mov     eax, ebx
0x180009367  add     rsp, 58h
0x18000936b  pop     r15
0x18000936d  pop     r14
0x18000936f  pop     r12
0x180009371  pop     rdi
0x180009372  pop     rsi
0x180009373  pop     rbx
0x180009374  retn
```
