# CClientUtils::WriteRegistryBinary(ushort const *,ushort const *,ushort *,int)

- ea: `0x180009bc0`
- end: `0x180009d65`
- name: `?WriteRegistryBinary@CClientUtils@@UEAAHPEBG0PEAGH@Z`
- size: `421`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x18000594c`
- `0x180009bc0`
- `0x180009d6c`
- `0x18000a508`
- `0x18000a8ac`
- `0x18000aac4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180009d4e`
- `ADVAPI32!RegCloseKey` at `0x180009d4e`

## string_xrefs

- `0x180009c38`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::WriteRegistryBinary(
        CClientUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4,
        DWORD cbData)
{
  int AppContainerRegistryLocation; // eax
  char v9; // di
  unsigned int v10; // ebx
  int CurrentThreadActivityIdPrefix; // eax
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF

  hKey = 0;
  if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
  {
    AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
    v9 = AppContainerRegistryLocation;
    if ( AppContainerRegistryLocation < 0 )
    {
      v10 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)WPP_46feef82db693a9214302820d1cc2cac_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v9);
      }
      goto LABEL_17;
    }
    v10 = CClientUtils::WriteRegistryEntry(hKey, a2, a3, a4, cbData, 3u);
    if ( v10 )
      goto LABEL_17;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3);
    }
  }
  v10 = CClientUtils::WriteRegistryEntry(HKEY_CURRENT_USER, a2, a3, a4, cbData, 3u);
  if ( !v10
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3);
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x180009bc0  push    rbx
0x180009bc2  push    rbp
0x180009bc3  push    rsi
0x180009bc4  push    rdi
0x180009bc5  push    r12
0x180009bc7  push    r14
0x180009bc9  push    r15
0x180009bcb  sub     rsp, 40h
0x180009bcf  mov     r14, r9
0x180009bd2  mov     [rsp+78h+hKey], 0
0x180009bdb  mov     rsi, r8
0x180009bde  mov     rbp, rdx
0x180009be1  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x180009be6  mov     r15d, [rsp+78h+arg_20]
0x180009bee  lea     r12, WPP_GLOBAL_Control
0x180009bf5  test    eax, eax
0x180009bf7  jz      loc_180009CD8
0x180009bfd  lea     rcx, [rsp+78h+hKey]; HKEY *
0x180009c02  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x180009c07  mov     edi, eax
0x180009c09  test    eax, eax
0x180009c0b  jns     short loc_180009C6A
0x180009c0d  xor     ebx, ebx
0x180009c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c16  cmp     rcx, r12
0x180009c19  jz      loc_180009D44
0x180009c1f  test    byte ptr [rcx+1Ch], 8
0x180009c23  jz      loc_180009D44
0x180009c29  cmp     byte ptr [rcx+19h], 2
0x180009c2d  jb      loc_180009D44
0x180009c33  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009c38  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x180009c3f  mov     [rsp+78h+dwType], edi
0x180009c43  mov     qword ptr [rsp+78h+cbData], rcx
0x180009c48  lea     edx, [rbx+1Eh]
0x180009c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c52  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009c59  mov     r9d, eax
0x180009c5c  mov     rcx, [rcx+10h]
0x180009c60  call    WPP_SF_DsD
0x180009c65  jmp     loc_180009D44
0x180009c6a  mov     rcx, [rsp+78h+hKey]; hKey
0x180009c6f  mov     r9, r14; lpData
0x180009c72  mov     [rsp+78h+dwType], 3; dwType
0x180009c7a  mov     r8, rsi; unsigned __int16 *
0x180009c7d  mov     rdx, rbp; unsigned __int16 *
0x180009c80  mov     [rsp+78h+cbData], r15d; cbData
0x180009c85  call    ?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z; CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)
0x180009c8a  mov     ebx, eax
0x180009c8c  test    eax, eax
0x180009c8e  jnz     loc_180009D44
0x180009c94  mov     rax, cs:WPP_GLOBAL_Control
0x180009c9b  cmp     rax, r12
0x180009c9e  jz      short loc_180009CD8
0x180009ca0  test    byte ptr [rax+1Ch], 1
0x180009ca4  jz      short loc_180009CD8
0x180009ca6  cmp     byte ptr [rax+19h], 4
0x180009caa  jb      short loc_180009CD8
0x180009cac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cb8  lea     edx, [rbx+1Fh]
0x180009cbb  mov     qword ptr [rsp+78h+dwType], rsi; __int64
0x180009cc0  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009cc7  mov     r9d, eax
0x180009cca  mov     qword ptr [rsp+78h+cbData], rbp; __int64
0x180009ccf  mov     rcx, [rcx+10h]; LoggerHandle
0x180009cd3  call    WPP_SF_DSS
0x180009cd8  mov     [rsp+78h+dwType], 3; dwType
0x180009ce0  mov     r9, r14; lpData
0x180009ce3  mov     r8, rsi; unsigned __int16 *
0x180009ce6  mov     [rsp+78h+cbData], r15d; cbData
0x180009ceb  mov     rdx, rbp; unsigned __int16 *
0x180009cee  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009cf5  call    ?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z; CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)
0x180009cfa  mov     ebx, eax
0x180009cfc  test    eax, eax
0x180009cfe  jnz     short loc_180009D44
0x180009d00  mov     rax, cs:WPP_GLOBAL_Control
0x180009d07  cmp     rax, r12
0x180009d0a  jz      short loc_180009D44
0x180009d0c  test    byte ptr [rax+1Ch], 1
0x180009d10  jz      short loc_180009D44
0x180009d12  cmp     byte ptr [rax+19h], 4
0x180009d16  jb      short loc_180009D44
0x180009d18  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d24  lea     edx, [rbx+20h]
0x180009d27  mov     qword ptr [rsp+78h+dwType], rsi; __int64
0x180009d2c  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009d33  mov     r9d, eax
0x180009d36  mov     qword ptr [rsp+78h+cbData], rbp; __int64
0x180009d3b  mov     rcx, [rcx+10h]; LoggerHandle
0x180009d3f  call    WPP_SF_DSS
0x180009d44  mov     rcx, [rsp+78h+hKey]; hKey
0x180009d49  test    rcx, rcx
0x180009d4c  jz      short loc_180009D54
0x180009d4e  call    cs:__imp_RegCloseKey
0x180009d54  mov     eax, ebx
0x180009d56  add     rsp, 40h
0x180009d5a  pop     r15
0x180009d5c  pop     r14
0x180009d5e  pop     r12
0x180009d60  pop     rdi
0x180009d61  pop     rsi
0x180009d62  pop     rbp
0x180009d63  pop     rbx
0x180009d64  retn
```
