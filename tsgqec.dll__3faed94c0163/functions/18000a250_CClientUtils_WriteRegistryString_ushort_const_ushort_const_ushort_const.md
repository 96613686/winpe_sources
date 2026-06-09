# CClientUtils::WriteRegistryString(ushort const *,ushort const *,ushort const *)

- ea: `0x18000a250`
- end: `0x18000a41a`
- name: `?WriteRegistryString@CClientUtils@@UEAAHPEBG00@Z`
- size: `458`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x18000594c`
- `0x180009d6c`
- `0x18000a250`
- `0x18000a508`
- `0x18000a8ac`
- `0x18000aac4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000a401`
- `ADVAPI32!RegCloseKey` at `0x18000a401`

## string_xrefs

- `0x18000a2c6`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::WriteRegistryString(
        CClientUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4)
{
  __int64 v7; // rdi
  int AppContainerRegistryLocation; // eax
  char v9; // si
  unsigned int v10; // ebx
  int CurrentThreadActivityIdPrefix; // eax
  __int64 v12; // rax
  HKEY hKey; // [rsp+30h] [rbp-58h] BYREF

  hKey = 0;
  v7 = -1;
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
          24,
          (unsigned int)WPP_46feef82db693a9214302820d1cc2cac_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v9);
      }
      goto LABEL_20;
    }
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)&a4[2 * v12] );
    v10 = CClientUtils::WriteRegistryEntry(hKey, a2, a3, a4, 2 * (int)v12 + 2, 1u);
    if ( v10 )
      goto LABEL_20;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3);
    }
  }
  do
    ++v7;
  while ( *(_WORD *)&a4[2 * v7] );
  v10 = CClientUtils::WriteRegistryEntry(HKEY_CURRENT_USER, a2, a3, a4, 2 * (int)v7 + 2, 1u);
  if ( !v10
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3);
  }
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x18000a250  push    rbx
0x18000a252  push    rbp
0x18000a253  push    rsi
0x18000a254  push    rdi
0x18000a255  push    r12
0x18000a257  push    r13
0x18000a259  push    r14
0x18000a25b  push    r15
0x18000a25d  sub     rsp, 48h
0x18000a261  xor     r12d, r12d
0x18000a264  mov     rbp, r9
0x18000a267  mov     [rsp+88h+hKey], r12
0x18000a26c  mov     r14, r8
0x18000a26f  mov     r15, rdx
0x18000a272  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x18000a277  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a27b  lea     r13, WPP_GLOBAL_Control
0x18000a282  test    eax, eax
0x18000a284  jz      loc_18000A37A
0x18000a28a  lea     rcx, [rsp+88h+hKey]; HKEY *
0x18000a28f  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x18000a294  mov     esi, eax
0x18000a296  test    eax, eax
0x18000a298  jns     short loc_18000A2F8
0x18000a29a  mov     ebx, r12d
0x18000a29d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2a4  cmp     rcx, r13
0x18000a2a7  jz      loc_18000A3F7
0x18000a2ad  test    byte ptr [rcx+1Ch], 8
0x18000a2b1  jz      loc_18000A3F7
0x18000a2b7  cmp     byte ptr [rcx+19h], 2
0x18000a2bb  jb      loc_18000A3F7
0x18000a2c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a2c6  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x18000a2cd  mov     [rsp+88h+dwType], esi
0x18000a2d1  mov     qword ptr [rsp+88h+cbData], rcx
0x18000a2d6  lea     edx, [rdi+19h]
0x18000a2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2e0  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x18000a2e7  mov     r9d, eax
0x18000a2ea  mov     rcx, [rcx+10h]
0x18000a2ee  call    WPP_SF_DsD
0x18000a2f3  jmp     loc_18000A3F7
0x18000a2f8  mov     rax, rdi
0x18000a2fb  inc     rax
0x18000a2fe  cmp     [rbp+rax*2+0], r12w
0x18000a304  jnz     short loc_18000A2FB
0x18000a306  mov     rcx, [rsp+88h+hKey]; hKey
0x18000a30b  lea     eax, ds:2[rax*2]
0x18000a312  mov     [rsp+88h+dwType], 1; dwType
0x18000a31a  mov     r9, rbp; lpData
0x18000a31d  mov     r8, r14; unsigned __int16 *
0x18000a320  mov     [rsp+88h+cbData], eax; cbData
0x18000a324  mov     rdx, r15; unsigned __int16 *
0x18000a327  call    ?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z; CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)
0x18000a32c  mov     ebx, eax
0x18000a32e  test    eax, eax
0x18000a330  jnz     loc_18000A3F7
0x18000a336  mov     rax, cs:WPP_GLOBAL_Control
0x18000a33d  cmp     rax, r13
0x18000a340  jz      short loc_18000A37A
0x18000a342  test    byte ptr [rax+1Ch], 1
0x18000a346  jz      short loc_18000A37A
0x18000a348  cmp     byte ptr [rax+19h], 4
0x18000a34c  jb      short loc_18000A37A
0x18000a34e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a353  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a35a  lea     edx, [rbx+19h]
0x18000a35d  mov     qword ptr [rsp+88h+dwType], r14; __int64
0x18000a362  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x18000a369  mov     r9d, eax
0x18000a36c  mov     qword ptr [rsp+88h+cbData], r15; __int64
0x18000a371  mov     rcx, [rcx+10h]; LoggerHandle
0x18000a375  call    WPP_SF_DSS
0x18000a37a  inc     rdi
0x18000a37d  cmp     [rbp+rdi*2+0], r12w
0x18000a383  jnz     short loc_18000A37A
0x18000a385  lea     eax, ds:2[rdi*2]
0x18000a38c  mov     [rsp+88h+dwType], 1; dwType
0x18000a394  mov     r9, rbp; lpData
0x18000a397  mov     [rsp+88h+cbData], eax; cbData
0x18000a39b  mov     r8, r14; unsigned __int16 *
0x18000a39e  mov     rdx, r15; unsigned __int16 *
0x18000a3a1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000a3a8  call    ?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z; CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)
0x18000a3ad  mov     ebx, eax
0x18000a3af  test    eax, eax
0x18000a3b1  jnz     short loc_18000A3F7
0x18000a3b3  mov     rax, cs:WPP_GLOBAL_Control
0x18000a3ba  cmp     rax, r13
0x18000a3bd  jz      short loc_18000A3F7
0x18000a3bf  test    byte ptr [rax+1Ch], 1
0x18000a3c3  jz      short loc_18000A3F7
0x18000a3c5  cmp     byte ptr [rax+19h], 4
0x18000a3c9  jb      short loc_18000A3F7
0x18000a3cb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3d7  lea     edx, [rbx+1Ah]
0x18000a3da  mov     qword ptr [rsp+88h+dwType], r14; __int64
0x18000a3df  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x18000a3e6  mov     r9d, eax
0x18000a3e9  mov     qword ptr [rsp+88h+cbData], r15; __int64
0x18000a3ee  mov     rcx, [rcx+10h]; LoggerHandle
0x18000a3f2  call    WPP_SF_DSS
0x18000a3f7  mov     rcx, [rsp+88h+hKey]; hKey
0x18000a3fc  test    rcx, rcx
0x18000a3ff  jz      short loc_18000A407
0x18000a401  call    cs:__imp_RegCloseKey
0x18000a407  mov     eax, ebx
0x18000a409  add     rsp, 48h
0x18000a40d  pop     r15
0x18000a40f  pop     r14
0x18000a411  pop     r13
0x18000a413  pop     r12
0x18000a415  pop     rdi
0x18000a416  pop     rsi
0x18000a417  pop     rbp
0x18000a418  pop     rbx
0x18000a419  retn
```
