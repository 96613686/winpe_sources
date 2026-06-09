# CClientUtils::WriteRegistryInt(ushort const *,ushort const *,int)

- ea: `0x18000a090`
- end: `0x18000a23f`
- name: `?WriteRegistryInt@CClientUtils@@UEAAHPEBG0H@Z`
- size: `431`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x18000594c`
- `0x180009d6c`
- `0x18000a090`
- `0x18000a508`
- `0x18000a8ac`
- `0x18000aac4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000a224`
- `ADVAPI32!RegCloseKey` at `0x18000a224`

## string_xrefs

- `0x18000a104`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::WriteRegistryInt(
        CClientUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int AppContainerRegistryLocation; // eax
  char v7; // di
  unsigned int v8; // ebx
  int CurrentThreadActivityIdPrefix; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
  {
    AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
    v7 = AppContainerRegistryLocation;
    if ( AppContainerRegistryLocation < 0 )
    {
      v8 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)WPP_46feef82db693a9214302820d1cc2cac_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v7);
      }
      goto LABEL_17;
    }
    v8 = CClientUtils::WriteRegistryEntry(hKey, a2, a3, (BYTE *)&Data, 4u, 4u);
    if ( v8 )
      goto LABEL_17;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3);
    }
  }
  v8 = CClientUtils::WriteRegistryEntry(HKEY_CURRENT_USER, a2, a3, (BYTE *)&Data, 4u, 4u);
  if ( !v8
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
  return v8;
}

```

## disassembly

```asm
0x18000a090  mov     rax, rsp
0x18000a093  mov     [rax+8], rbx
0x18000a097  mov     [rax+10h], rbp
0x18000a09b  mov     [rax+20h], r9d
0x18000a09f  push    rsi
0x18000a0a0  push    rdi
0x18000a0a1  push    r15
0x18000a0a3  sub     rsp, 40h
0x18000a0a7  mov     rsi, r8
0x18000a0aa  mov     qword ptr [rax-28h], 0
0x18000a0b2  mov     rbp, rdx
0x18000a0b5  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x18000a0ba  lea     r15, WPP_GLOBAL_Control
0x18000a0c1  test    eax, eax
0x18000a0c3  jz      loc_18000A1A9
0x18000a0c9  lea     rcx, [rsp+58h+hKey]; HKEY *
0x18000a0ce  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x18000a0d3  mov     edi, eax
0x18000a0d5  test    eax, eax
0x18000a0d7  jns     short loc_18000A136
0x18000a0d9  xor     ebx, ebx
0x18000a0db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0e2  cmp     rcx, r15
0x18000a0e5  jz      loc_18000A21A
0x18000a0eb  test    byte ptr [rcx+1Ch], 8
0x18000a0ef  jz      loc_18000A21A
0x18000a0f5  cmp     byte ptr [rcx+19h], 2
0x18000a0f9  jb      loc_18000A21A
0x18000a0ff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a104  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x18000a10b  mov     [rsp+58h+dwType], edi
0x18000a10f  mov     qword ptr [rsp+58h+cbData], rcx
0x18000a114  lea     edx, [rbx+1Bh]
0x18000a117  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a11e  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x18000a125  mov     r9d, eax
0x18000a128  mov     rcx, [rcx+10h]
0x18000a12c  call    WPP_SF_DsD
0x18000a131  jmp     loc_18000A21A
0x18000a136  mov     rcx, [rsp+58h+hKey]; hKey
0x18000a13b  lea     r9, [rsp+58h+Data]; lpData
0x18000a140  mov     [rsp+58h+dwType], 4; dwType
0x18000a148  mov     r8, rsi; unsigned __int16 *
0x18000a14b  mov     rdx, rbp; unsigned __int16 *
0x18000a14e  mov     [rsp+58h+cbData], 4; cbData
0x18000a156  call    ?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z; CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)
0x18000a15b  mov     ebx, eax
0x18000a15d  test    eax, eax
0x18000a15f  jnz     loc_18000A21A
0x18000a165  mov     rax, cs:WPP_GLOBAL_Control
0x18000a16c  cmp     rax, r15
0x18000a16f  jz      short loc_18000A1A9
0x18000a171  test    byte ptr [rax+1Ch], 1
0x18000a175  jz      short loc_18000A1A9
0x18000a177  cmp     byte ptr [rax+19h], 4
0x18000a17b  jb      short loc_18000A1A9
0x18000a17d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a182  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a189  lea     edx, [rbx+1Ch]
0x18000a18c  mov     qword ptr [rsp+58h+dwType], rsi; __int64
0x18000a191  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x18000a198  mov     r9d, eax
0x18000a19b  mov     qword ptr [rsp+58h+cbData], rbp; __int64
0x18000a1a0  mov     rcx, [rcx+10h]; LoggerHandle
0x18000a1a4  call    WPP_SF_DSS
0x18000a1a9  mov     [rsp+58h+dwType], 4; dwType
0x18000a1b1  lea     r9, [rsp+58h+Data]; lpData
0x18000a1b6  mov     r8, rsi; unsigned __int16 *
0x18000a1b9  mov     [rsp+58h+cbData], 4; cbData
0x18000a1c1  mov     rdx, rbp; unsigned __int16 *
0x18000a1c4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000a1cb  call    ?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z; CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)
0x18000a1d0  mov     ebx, eax
0x18000a1d2  test    eax, eax
0x18000a1d4  jnz     short loc_18000A21A
0x18000a1d6  mov     rax, cs:WPP_GLOBAL_Control
0x18000a1dd  cmp     rax, r15
0x18000a1e0  jz      short loc_18000A21A
0x18000a1e2  test    byte ptr [rax+1Ch], 1
0x18000a1e6  jz      short loc_18000A21A
0x18000a1e8  cmp     byte ptr [rax+19h], 4
0x18000a1ec  jb      short loc_18000A21A
0x18000a1ee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a1f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1fa  lea     edx, [rbx+1Dh]
0x18000a1fd  mov     qword ptr [rsp+58h+dwType], rsi; __int64
0x18000a202  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x18000a209  mov     r9d, eax
0x18000a20c  mov     qword ptr [rsp+58h+cbData], rbp; __int64
0x18000a211  mov     rcx, [rcx+10h]; LoggerHandle
0x18000a215  call    WPP_SF_DSS
0x18000a21a  mov     rcx, [rsp+58h+hKey]; hKey
0x18000a21f  test    rcx, rcx
0x18000a222  jz      short loc_18000A22A
0x18000a224  call    cs:__imp_RegCloseKey
0x18000a22a  mov     rbp, [rsp+58h+arg_8]
0x18000a22f  mov     eax, ebx
0x18000a231  mov     rbx, [rsp+58h+arg_0]
0x18000a236  add     rsp, 40h
0x18000a23a  pop     r15
0x18000a23c  pop     rdi
0x18000a23d  pop     rsi
0x18000a23e  retn
```
