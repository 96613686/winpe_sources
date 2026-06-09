# CClientUtils::ReadRegistryString(ushort const *,ushort const *,ushort *,int,UT_REGREAD_LOCATION,ulong *,int)

- ea: `0x180009380`
- end: `0x1800095c1`
- name: `?ReadRegistryString@CClientUtils@@UEAAHPEBG0PEAGHW4UT_REGREAD_LOCATION@@PEAKH@Z`
- size: `577`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int, enum UT_REGREAD_LOCATION, unsigned int *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x1800053ac`
- `0x18000594c`
- `0x180008bc0`
- `0x180009380`
- `0x18000a8ac`
- `0x18000aac4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800095a9`
- `ADVAPI32!RegCloseKey` at `0x1800095a9`

## string_xrefs

- `0x180009408`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::ReadRegistryString(
        __int64 a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4,
        DWORD a5,
        int a6,
        unsigned int *a7,
        int a8)
{
  unsigned int RegistryEntry; // ebx
  int v9; // esi
  int AppContainerRegistryLocation; // eax
  char v14; // di
  int CurrentThreadActivityIdPrefix; // eax
  unsigned int *v16; // rdi
  unsigned int v17; // eax
  unsigned int v18; // eax
  HKEY hKey; // [rsp+40h] [rbp-48h] BYREF

  RegistryEntry = 0;
  v9 = 0;
  hKey = 0;
  if ( (a6 & 0xFFFFFFFD) != 0 )
  {
    v16 = a7;
  }
  else
  {
    if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
    {
      AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
      v14 = AppContainerRegistryLocation;
      if ( AppContainerRegistryLocation < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            (unsigned int)WPP_46feef82db693a9214302820d1cc2cac_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"Unable to get AppContainer registry location.",
            v14);
        }
        goto LABEL_26;
      }
      v16 = a7;
      RegistryEntry = CClientUtils::ReadRegistryEntry(hKey, a2, a3, a4, a5, 1, a7, a8);
      if ( RegistryEntry )
        goto LABEL_26;
    }
    else
    {
      v16 = a7;
    }
    RegistryEntry = CClientUtils::ReadRegistryEntry(HKEY_CURRENT_USER, a2, a3, a4, a5, 1, v16, a8);
    if ( !RegistryEntry )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v17);
      }
      v9 = 1;
    }
  }
  if ( a6 == 1 || a6 == 2 && v9 )
  {
    RegistryEntry = CClientUtils::ReadRegistryEntry(HKEY_LOCAL_MACHINE, a2, a3, a4, a5, 1, v16, a8);
    if ( !RegistryEntry
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v18);
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
0x180009380  push    rbx
0x180009382  push    rsi
0x180009383  push    rdi
0x180009384  push    r12
0x180009386  push    r13
0x180009388  push    r14
0x18000938a  push    r15
0x18000938c  sub     rsp, 50h
0x180009390  mov     r13d, [rsp+88h+arg_38]
0x180009398  xor     ebx, ebx
0x18000939a  xor     esi, esi
0x18000939c  mov     [rsp+88h+hKey], rbx
0x1800093a1  test    [rsp+88h+arg_28], 0FFFFFFFDh
0x1800093ac  mov     r14, r9
0x1800093af  mov     r15, r8
0x1800093b2  mov     r12, rdx
0x1800093b5  jnz     loc_180009506
0x1800093bb  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1800093c0  test    eax, eax
0x1800093c2  jz      loc_18000947E
0x1800093c8  lea     rcx, [rsp+88h+hKey]; HKEY *
0x1800093cd  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1800093d2  mov     edi, eax
0x1800093d4  test    eax, eax
0x1800093d6  jns     short loc_18000943A
0x1800093d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093df  lea     rax, WPP_GLOBAL_Control
0x1800093e6  cmp     rcx, rax
0x1800093e9  jz      loc_18000959F
0x1800093ef  test    byte ptr [rcx+1Ch], 8
0x1800093f3  jz      loc_18000959F
0x1800093f9  cmp     byte ptr [rcx+19h], 2
0x1800093fd  jb      loc_18000959F
0x180009403  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009408  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x18000940f  mov     dword ptr [rsp+88h+var_60], edi
0x180009413  mov     qword ptr [rsp+88h+var_68], rcx
0x180009418  lea     edx, [rbx+0Ah]
0x18000941b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009422  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009429  mov     r9d, eax
0x18000942c  mov     rcx, [rcx+10h]
0x180009430  call    WPP_SF_DsD
0x180009435  jmp     loc_18000959F
0x18000943a  mov     eax, [rsp+88h+arg_20]
0x180009441  mov     r9, r14; lpData
0x180009444  mov     rdi, [rsp+88h+arg_30]
0x18000944c  mov     r8, r15; unsigned __int16 *
0x18000944f  mov     rcx, [rsp+88h+hKey]; hKey
0x180009454  mov     rdx, r12; unsigned __int16 *
0x180009457  mov     [rsp+88h+var_50], r13d; int
0x18000945c  mov     [rsp+88h+var_58], rdi; unsigned int *
0x180009461  mov     dword ptr [rsp+88h+var_60], 1; char
0x180009469  mov     [rsp+88h+var_68], eax; int
0x18000946d  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180009472  mov     ebx, eax
0x180009474  test    eax, eax
0x180009476  jnz     loc_18000959F
0x18000947c  jmp     short loc_180009486
0x18000947e  mov     rdi, [rsp+88h+arg_30]
0x180009486  mov     eax, [rsp+88h+arg_20]
0x18000948d  mov     r9, r14; lpData
0x180009490  mov     [rsp+88h+var_50], r13d; int
0x180009495  mov     r8, r15; unsigned __int16 *
0x180009498  mov     [rsp+88h+var_58], rdi; unsigned int *
0x18000949d  mov     rdx, r12; unsigned __int16 *
0x1800094a0  mov     dword ptr [rsp+88h+var_60], 1; char
0x1800094a8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800094af  mov     [rsp+88h+var_68], eax; int
0x1800094b3  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x1800094b8  mov     ebx, eax
0x1800094ba  test    eax, eax
0x1800094bc  jnz     short loc_18000950E
0x1800094be  mov     rax, cs:WPP_GLOBAL_Control
0x1800094c5  lea     rcx, WPP_GLOBAL_Control
0x1800094cc  cmp     rax, rcx
0x1800094cf  jz      short loc_1800094FF
0x1800094d1  test    byte ptr [rax+1Ch], 1
0x1800094d5  jz      short loc_1800094FF
0x1800094d7  cmp     byte ptr [rax+19h], 4
0x1800094db  jb      short loc_1800094FF
0x1800094dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800094e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094e9  lea     edx, [rbx+0Bh]
0x1800094ec  mov     r9d, eax
0x1800094ef  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x1800094f6  mov     rcx, [rcx+10h]
0x1800094fa  call    WPP_SF_D
0x1800094ff  mov     esi, 1
0x180009504  jmp     short loc_18000950E
0x180009506  mov     rdi, [rsp+88h+arg_30]
0x18000950e  cmp     [rsp+88h+arg_28], 1
0x180009516  jz      short loc_180009526
0x180009518  cmp     [rsp+88h+arg_28], 2
0x180009520  jnz     short loc_18000959F
0x180009522  test    esi, esi
0x180009524  jz      short loc_18000959F
0x180009526  mov     eax, [rsp+88h+arg_20]
0x18000952d  mov     r9, r14; lpData
0x180009530  mov     [rsp+88h+var_50], r13d; int
0x180009535  mov     r8, r15; unsigned __int16 *
0x180009538  mov     [rsp+88h+var_58], rdi; unsigned int *
0x18000953d  mov     rdx, r12; unsigned __int16 *
0x180009540  mov     dword ptr [rsp+88h+var_60], 1; char
0x180009548  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000954f  mov     [rsp+88h+var_68], eax; int
0x180009553  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180009558  mov     ebx, eax
0x18000955a  test    eax, eax
0x18000955c  jnz     short loc_18000959F
0x18000955e  mov     rax, cs:WPP_GLOBAL_Control
0x180009565  lea     rcx, WPP_GLOBAL_Control
0x18000956c  cmp     rax, rcx
0x18000956f  jz      short loc_18000959F
0x180009571  test    byte ptr [rax+1Ch], 1
0x180009575  jz      short loc_18000959F
0x180009577  cmp     byte ptr [rax+19h], 4
0x18000957b  jb      short loc_18000959F
0x18000957d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009582  mov     rcx, cs:WPP_GLOBAL_Control
0x180009589  lea     edx, [rbx+0Ch]
0x18000958c  mov     r9d, eax
0x18000958f  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009596  mov     rcx, [rcx+10h]
0x18000959a  call    WPP_SF_D
0x18000959f  mov     rcx, [rsp+88h+hKey]; hKey
0x1800095a4  test    rcx, rcx
0x1800095a7  jz      short loc_1800095AF
0x1800095a9  call    cs:__imp_RegCloseKey
0x1800095af  mov     eax, ebx
0x1800095b1  add     rsp, 50h
0x1800095b5  pop     r15
0x1800095b7  pop     r14
0x1800095b9  pop     r13
0x1800095bb  pop     r12
0x1800095bd  pop     rdi
0x1800095be  pop     rsi
0x1800095bf  pop     rbx
0x1800095c0  retn
```
