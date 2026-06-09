# CWcnNetworkProfileLoaderElevated::LoadProfilesFromWlan(ulong,IWcnElevationHelper *)

- ea: `0x18002d050`
- end: `0x18002d536`
- name: `?LoadProfilesFromWlan@CWcnNetworkProfileLoaderElevated@@AEAAJKPEAUIWcnElevationHelper@@@Z`
- size: `1254`
- prototype: `__int64 __fastcall(CWcnNetworkProfileLoaderElevated *__hidden this, unsigned int, struct IWcnElevationHelper *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002d540`

## callees

- `0x180004b84`
- `0x18000d630`
- `0x18000e0a0`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18002b988`
- `0x18002d050`
- `0x18002da8c`
- `0x18002dbb8`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002d2d1`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d2d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d38f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d399`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d44a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d454`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d38f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d399`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d44a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d454`
- `wlanapi!WlanCloseHandle` at `0x18002d4d4`
- `wlanapi!WlanCloseHandle` at `0x18002d4d4`
- `wlanapi!WlanOpenHandle` at `0x18002d0c9`
- `wlanapi!WlanOpenHandle` at `0x18002d0c9`
- `wlanapi!WlanQueryInterface` at `0x18002d1e8`
- `wlanapi!WlanQueryInterface` at `0x18002d1e8`
- `wlanapi!WlanGetProfileList` at `0x18002d238`
- `wlanapi!WlanGetProfileList` at `0x18002d238`
- `wlanapi!WlanEnumInterfaces` at `0x18002d131`
- `wlanapi!WlanEnumInterfaces` at `0x18002d131`
- `wlanapi!WlanFreeMemory` at `0x18002d476`
- `wlanapi!WlanFreeMemory` at `0x18002d485`
- `wlanapi!WlanFreeMemory` at `0x18002d4bc`
- `wlanapi!WlanFreeMemory` at `0x18002d476`
- `wlanapi!WlanFreeMemory` at `0x18002d485`
- `wlanapi!WlanFreeMemory` at `0x18002d4bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWcnNetworkProfileLoaderElevated::LoadProfilesFromWlan(
        CWcnNetworkProfileLoaderElevated *this,
        int a2,
        struct IWcnElevationHelper *a3)
{
  signed int v3; // edi
  const char *Indent; // rax
  __int64 v5; // r10
  signed int v6; // eax
  unsigned int v7; // edi
  _QWORD *v8; // r10
  __int64 v9; // rdx
  PWLAN_INTERFACE_INFO_LIST v10; // rsi
  unsigned int v11; // edi
  char v12; // r15
  bool v13; // r13
  DWORD v14; // r14d
  const GUID *p_InterfaceGuid; // r12
  __int64 v16; // rax
  OLECHAR *v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // r10
  int v20; // edx
  int v21; // r8d
  char v22; // r11
  DWORD v23; // r12d
  PWLAN_PROFILE_INFO_LIST v24; // rdx
  const OLECHAR *strProfileName; // r14
  unsigned int v26; // eax
  __int64 v27; // r10
  char v28; // r11
  __int16 v29; // dx
  char *v30; // r8
  int v31; // eax
  int v32; // ecx
  int v33; // eax
  unsigned int v34; // eax
  __int64 v35; // r10
  DWORD v37; // [rsp+48h] [rbp-49h]
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+50h] [rbp-41h] BYREF
  BOOL v39; // [rsp+58h] [rbp-39h]
  PVOID pMemory; // [rsp+60h] [rbp-31h] BYREF
  void *phClientHandle; // [rsp+68h] [rbp-29h] BYREF
  __int64 v42; // [rsp+70h] [rbp-21h]
  BSTR bstrString; // [rsp+78h] [rbp-19h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+80h] [rbp-11h] BYREF
  DWORD pdwDataSize; // [rsp+84h] [rbp-Dh] BYREF
  PWLAN_PROFILE_INFO_LIST ppProfileList; // [rsp+88h] [rbp-9h] BYREF
  OLECHAR *v47; // [rsp+90h] [rbp-1h]
  GUID InterfaceGuid; // [rsp+98h] [rbp+7h] BYREF
  char v52; // [rsp+110h] [rbp+7Fh]

  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  ppInterfaceList = 0;
  v3 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 17, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, Indent);
  }
  v6 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    else
      v7 = v6;
    v3 = v7 | 0x80000000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 18;
LABEL_11:
      WPP_SF_Dd(v8[2], v9, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, (unsigned int)v6, v3);
      v10 = ppInterfaceList;
      v8 = WPP_GLOBAL_Control;
      goto LABEL_61;
    }
    goto LABEL_19;
  }
  v6 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList);
  if ( v6 )
  {
    if ( v6 > 0 )
      v11 = (unsigned __int16)v6 | 0x80070000;
    else
      v11 = v6;
    v3 = v11 | 0x80000000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 19;
      goto LABEL_11;
    }
LABEL_19:
    v10 = ppInterfaceList;
    goto LABEL_61;
  }
  v12 = 0;
  v52 = 0;
  v13 = 0;
  v14 = 0;
  v37 = 0;
  v10 = ppInterfaceList;
  v8 = WPP_GLOBAL_Control;
  if ( !ppInterfaceList->dwNumberOfItems )
    goto LABEL_61;
  while ( !v13 )
  {
    v42 = 532LL * v14;
    p_InterfaceGuid = &v10->InterfaceInfo[(unsigned __int64)v42 / 0x214].InterfaceGuid;
    ppProfileList = 0;
    pMemory = 0;
    v39 = 0;
    pdwDataSize = 0;
    if ( !WlanQueryInterface(
            phClientHandle,
            p_InterfaceGuid,
            wlan_intf_opcode_current_connection,
            0,
            &pdwDataSize,
            &pMemory,
            0)
      && *(_DWORD *)pMemory == 1
      && (*((_DWORD *)pMemory + 1) & 0xFFFFFFFB) == 0 )
    {
      *((_WORD *)pMemory + 259) = 0;
      v16 = -1;
      do
        ++v16;
      while ( *((_WORD *)pMemory + v16 + 4) );
      v39 = v16 != 0;
    }
    v17 = 0;
    if ( WlanGetProfileList(phClientHandle, p_InterfaceGuid, 0, &ppProfileList) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        goto LABEL_58;
      v18 = (unsigned int)GetIndent(0);
      WPP_SF_sS_guid_D(
        *(_QWORD *)(v19 + 16),
        v20,
        v21,
        v18,
        (__int64)v10->InterfaceInfo[(unsigned __int64)v42 / 0x214].strInterfaceDescription,
        (__int64)p_InterfaceGuid,
        v22);
    }
    else
    {
      v23 = 0;
      v24 = ppProfileList;
      if ( ppProfileList->dwNumberOfItems )
      {
        do
        {
          if ( v13 )
            break;
          strProfileName = v24->ProfileInfo[v23].strProfileName;
          if ( strProfileName )
          {
            v17 = SysAllocString(strProfileName);
            v47 = v17;
            if ( !v17 )
              ATL::AtlThrowImpl(-2147024882);
          }
          else
          {
            v47 = 0;
          }
          bstrString = 0;
          InterfaceGuid = v10->InterfaceInfo[(unsigned __int64)v42 / 0x214].InterfaceGuid;
          if ( (*(int (__fastcall **)(struct IWcnElevationHelper *, GUID *, OLECHAR *, bool, BSTR *))(*(_QWORD *)a3 + 24LL))(
                 a3,
                 &InterfaceGuid,
                 v17,
                 (a2 & 0x10000) == 0,
                 &bstrString) >= 0 )
          {
            v29 = (a2 & 0x10000) != 0;
            if ( v39 )
            {
              v30 = (char *)((_BYTE *)pMemory + 8 - (_BYTE *)strProfileName);
              do
              {
                v31 = *(unsigned __int16 *)&v30[(_QWORD)strProfileName];
                v32 = *strProfileName - v31;
                if ( v32 )
                  break;
                ++strProfileName;
              }
              while ( v31 );
              if ( !v32 )
                v29 |= 0x40u;
            }
            v33 = CWcnNetworkProfileLoader::AddProfileToList(
                    this,
                    v29,
                    bstrString,
                    v10->InterfaceInfo[(unsigned __int64)v42 / 0x214].strInterfaceDescription,
                    0);
            if ( v33 < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                22,
                WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids,
                (unsigned int)v33);
            }
            v12 = 1;
            v52 = 1;
            v13 = (a2 & 0x20000) != 0;
            SysFreeString(bstrString);
            SysFreeString(v17);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              v26 = (unsigned int)GetIndent(0);
              WPP_SF_sSS_guid_d(
                *(_QWORD *)(v27 + 16),
                (_DWORD)v10 + v42 + 24,
                v42,
                v26,
                (__int64)strProfileName,
                (__int64)v10->InterfaceInfo[(unsigned __int64)v42 / 0x214].strInterfaceDescription,
                (__int64)&v10->InterfaceInfo[(unsigned __int64)v42 / 0x214],
                v28);
            }
            SysFreeString(bstrString);
            SysFreeString(v17);
            v12 = v52;
          }
          ++v23;
          v24 = ppProfileList;
          v17 = 0;
        }
        while ( v23 < ppProfileList->dwNumberOfItems );
        v14 = v37;
      }
      WlanFreeMemory(v24);
      if ( pMemory )
        WlanFreeMemory(pMemory);
    }
    v8 = WPP_GLOBAL_Control;
LABEL_58:
    v37 = ++v14;
    v10 = ppInterfaceList;
    if ( v14 >= ppInterfaceList->dwNumberOfItems )
      break;
  }
  if ( v12 )
    v3 = 0;
LABEL_61:
  if ( v10 )
  {
    WlanFreeMemory(v10);
    v8 = WPP_GLOBAL_Control;
  }
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (v3 < 0 || *((_BYTE *)v8 + 25) >= 6u) )
  {
    v34 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v35 + 16), 23, (unsigned int)WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, v34, v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002d050  mov     rax, rsp
0x18002d053  mov     [rax+18h], r8
0x18002d057  mov     [rax+10h], edx
0x18002d05a  mov     [rax+8], rcx
0x18002d05e  push    rbp
0x18002d05f  push    rbx
0x18002d060  push    rsi
0x18002d061  push    rdi
0x18002d062  push    r12
0x18002d064  push    r13
0x18002d066  push    r14
0x18002d068  push    r15
0x18002d06a  lea     rbp, [rax-5Fh]
0x18002d06e  sub     rsp, 0A8h
0x18002d075  xor     ebx, ebx
0x18002d077  mov     [rbp+57h+phClientHandle], rbx
0x18002d07b  mov     [rbp+57h+pdwNegotiatedVersion], ebx
0x18002d07e  mov     [rbp+57h+ppInterfaceList], rbx
0x18002d082  lea     r14, WPP_GLOBAL_Control
0x18002d089  lea     edi, [rbx+1]
0x18002d08c  mov     r10, cs:WPP_GLOBAL_Control
0x18002d093  cmp     r10, r14
0x18002d096  jz      short loc_18002D0BC
0x18002d098  cmp     byte ptr [r10+19h], 6
0x18002d09d  jb      short loc_18002D0BC
0x18002d09f  mov     ecx, edi; int
0x18002d0a1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002d0a6  lea     edx, [rbx+11h]
0x18002d0a9  mov     r9, rax
0x18002d0ac  lea     r8, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids
0x18002d0b3  mov     rcx, [r10+10h]
0x18002d0b7  call    WPP_SF_s
0x18002d0bc  lea     r9, [rbp+57h+phClientHandle]; phClientHandle
0x18002d0c0  lea     r8, [rbp+57h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18002d0c4  xor     edx, edx; pReserved
0x18002d0c6  lea     ecx, [rdx+2]; dwClientVersion
0x18002d0c9  call    cs:__imp_WlanOpenHandle
0x18002d0cf  test    eax, eax
0x18002d0d1  jz      short loc_18002D127
0x18002d0d3  jg      short loc_18002D0D9
0x18002d0d5  mov     edi, eax
0x18002d0d7  jmp     short loc_18002D0E2
0x18002d0d9  movzx   edi, ax
0x18002d0dc  or      edi, 80070000h
0x18002d0e2  or      edi, 80000000h
0x18002d0e8  mov     r10, cs:WPP_GLOBAL_Control
0x18002d0ef  cmp     r10, r14
0x18002d0f2  jz      short loc_18002D16A
0x18002d0f4  cmp     byte ptr [r10+19h], 2
0x18002d0f9  jb      short loc_18002D16A
0x18002d0fb  mov     edx, 12h
0x18002d100  mov     dword ptr [rsp+0E0h+pdwDataSize], edi
0x18002d104  mov     r9d, eax
0x18002d107  lea     r8, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids
0x18002d10e  mov     rcx, [r10+10h]
0x18002d112  call    WPP_SF_Dd
0x18002d117  mov     rsi, [rbp+57h+ppInterfaceList]
0x18002d11b  mov     r10, cs:WPP_GLOBAL_Control
0x18002d122  jmp     loc_18002D4B4
0x18002d127  lea     r8, [rbp+57h+ppInterfaceList]; ppInterfaceList
0x18002d12b  xor     edx, edx; pReserved
0x18002d12d  mov     rcx, [rbp+57h+phClientHandle]; hClientHandle
0x18002d131  call    cs:__imp_WlanEnumInterfaces
0x18002d137  test    eax, eax
0x18002d139  jz      short loc_18002D173
0x18002d13b  jg      short loc_18002D141
0x18002d13d  mov     edi, eax
0x18002d13f  jmp     short loc_18002D14A
0x18002d141  movzx   edi, ax
0x18002d144  or      edi, 80070000h
0x18002d14a  or      edi, 80000000h
0x18002d150  mov     r10, cs:WPP_GLOBAL_Control
0x18002d157  cmp     r10, r14
0x18002d15a  jz      short loc_18002D16A
0x18002d15c  cmp     byte ptr [r10+19h], 2
0x18002d161  jb      short loc_18002D16A
0x18002d163  mov     edx, 13h
0x18002d168  jmp     short loc_18002D100
0x18002d16a  mov     rsi, [rbp+57h+ppInterfaceList]
0x18002d16e  jmp     loc_18002D4B4
0x18002d173  mov     r15b, bl
0x18002d176  mov     [rbp+57h+arg_18], bl
0x18002d179  mov     r13b, bl
0x18002d17c  mov     r14d, ebx
0x18002d17f  mov     [rbp+57h+var_A0], ebx
0x18002d182  mov     rsi, [rbp+57h+ppInterfaceList]
0x18002d186  mov     r10, cs:WPP_GLOBAL_Control
0x18002d18d  cmp     [rsi], ebx
0x18002d18f  jbe     loc_18002D4AD
0x18002d195  test    r13b, r13b
0x18002d198  jnz     loc_18002D4A6
0x18002d19e  mov     eax, r14d
0x18002d1a1  imul    rax, 214h
0x18002d1a8  mov     [rbp+57h+var_78], rax
0x18002d1ac  lea     r12, [rax+8]
0x18002d1b0  add     r12, rsi
0x18002d1b3  mov     [rbp+57h+ppProfileList], rbx
0x18002d1b7  mov     [rbp+57h+pMemory], rbx
0x18002d1bb  mov     [rbp+57h+var_90], ebx
0x18002d1be  xor     edx, edx
0x18002d1c0  mov     [rbp+57h+var_64], edx
0x18002d1c3  mov     [rsp+0E0h+pWlanOpcodeValueType], rdx; pWlanOpcodeValueType
0x18002d1c8  lea     rax, [rbp+57h+pMemory]
0x18002d1cc  mov     [rsp+0E0h+ppData], rax; ppData
0x18002d1d1  lea     rax, [rbp+57h+var_64]
0x18002d1d5  mov     [rsp+0E0h+pdwDataSize], rax; pdwDataSize
0x18002d1da  xor     r9d, r9d; pReserved
0x18002d1dd  lea     r8d, [rdx+7]; OpCode
0x18002d1e1  mov     rdx, r12; pInterfaceGuid
0x18002d1e4  mov     rcx, [rbp+57h+phClientHandle]; hClientHandle
0x18002d1e8  call    cs:__imp_WlanQueryInterface
0x18002d1ee  xor     edx, edx
0x18002d1f0  test    eax, eax
0x18002d1f2  jnz     short loc_18002D22A
0x18002d1f4  mov     rcx, [rbp+57h+pMemory]
0x18002d1f8  cmp     [rcx], edi
0x18002d1fa  jnz     short loc_18002D22A
0x18002d1fc  test    dword ptr [rcx+4], 0FFFFFFFBh
0x18002d203  jnz     short loc_18002D22A
0x18002d205  mov     [rcx+206h], dx
0x18002d20c  mov     rcx, [rbp+57h+pMemory]
0x18002d210  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d214  inc     rax
0x18002d217  cmp     [rcx+rax*2+8], dx
0x18002d21c  jnz     short loc_18002D214
0x18002d21e  movzx   ebx, bl
0x18002d221  test    rax, rax
0x18002d224  cmovnz  ebx, edi
0x18002d227  mov     [rbp+57h+var_90], ebx
0x18002d22a  lea     r9, [rbp+57h+ppProfileList]; ppProfileList
0x18002d22e  xor     r8d, r8d; pReserved
0x18002d231  mov     rdx, r12; pInterfaceGuid
0x18002d234  mov     rcx, [rbp+57h+phClientHandle]; hClientHandle
0x18002d238  call    cs:__imp_WlanGetProfileList
0x18002d23e  mov     r11d, eax
0x18002d241  xor     ebx, ebx
0x18002d243  test    eax, eax
0x18002d245  jz      short loc_18002D29B
0x18002d247  mov     r10, cs:WPP_GLOBAL_Control
0x18002d24e  lea     rax, WPP_GLOBAL_Control
0x18002d255  cmp     r10, rax
0x18002d258  jz      loc_18002D492
0x18002d25e  cmp     byte ptr [r10+19h], 3
0x18002d263  jb      loc_18002D492
0x18002d269  xor     ecx, ecx; int
0x18002d26b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002d270  mov     rcx, [rbp+57h+var_78]
0x18002d274  add     rcx, 18h
0x18002d278  add     rcx, rsi
0x18002d27b  mov     dword ptr [rsp+0E0h+pWlanOpcodeValueType], r11d
0x18002d280  mov     [rsp+0E0h+ppData], r12
0x18002d285  mov     [rsp+0E0h+pdwDataSize], rcx
0x18002d28a  mov     r9, rax
0x18002d28d  mov     rcx, [r10+10h]
0x18002d291  call    WPP_SF_sS_guid_D
0x18002d296  jmp     loc_18002D48B
0x18002d29b  mov     r12d, ebx
0x18002d29e  mov     rdx, [rbp+57h+ppProfileList]
0x18002d2a2  cmp     [rdx], ebx
0x18002d2a4  jbe     loc_18002D473
0x18002d2aa  test    r13b, r13b
0x18002d2ad  jnz     loc_18002D46F
0x18002d2b3  mov     eax, r12d
0x18002d2b6  imul    r14, rax, 204h
0x18002d2bd  add     r14, 8
0x18002d2c1  add     r14, rdx
0x18002d2c4  jnz     short loc_18002D2CE
0x18002d2c6  mov     [rbp+57h+var_58], rbx
0x18002d2ca  xor     edx, edx
0x18002d2cc  jmp     short loc_18002D2E9
0x18002d2ce  mov     rcx, r14; psz
0x18002d2d1  call    cs:__imp_SysAllocString
0x18002d2d7  mov     rbx, rax
0x18002d2da  mov     [rbp+57h+var_58], rax
0x18002d2de  xor     edx, edx
0x18002d2e0  test    rax, rax
0x18002d2e3  jz      loc_18002D52B
0x18002d2e9  mov     [rbp+57h+bstrString], rdx
0x18002d2ed  mov     r15d, [rbp+57h+arg_8]
0x18002d2f1  and     r15d, 10000h
0x18002d2f8  mov     rax, [rbp+57h+var_78]
0x18002d2fc  movups  xmm0, xmmword ptr [rax+rsi+8]
0x18002d301  movdqu  [rbp+57h+var_50], xmm0
0x18002d306  mov     rcx, [rbp+57h+arg_10]
0x18002d30a  mov     rax, [rcx]
0x18002d30d  mov     r9d, edx
0x18002d310  setz    r9b
0x18002d314  lea     rdx, [rbp+57h+bstrString]
0x18002d318  mov     [rsp+0E0h+pdwDataSize], rdx
0x18002d31d  mov     r8, rbx
0x18002d320  lea     rdx, [rbp+57h+var_50]
0x18002d324  mov     rax, [rax+18h]
0x18002d328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d32d  mov     r11d, eax
0x18002d330  xor     r10d, r10d
0x18002d333  test    eax, eax
0x18002d335  jns     short loc_18002D3A8
0x18002d337  mov     r10, cs:WPP_GLOBAL_Control
0x18002d33e  lea     rax, WPP_GLOBAL_Control
0x18002d345  cmp     r10, rax
0x18002d348  jz      short loc_18002D38B
0x18002d34a  cmp     byte ptr [r10+19h], 3
0x18002d34f  jb      short loc_18002D38B
0x18002d351  xor     ecx, ecx; int
0x18002d353  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002d358  mov     r8, [rbp+57h+var_78]
0x18002d35c  lea     rdx, [r8+18h]
0x18002d360  add     rdx, rsi
0x18002d363  mov     [rsp+38h], r11d
0x18002d368  lea     rcx, [r8+8]
0x18002d36c  add     rcx, rsi
0x18002d36f  mov     [rsp+0E0h+pWlanOpcodeValueType], rcx
0x18002d374  mov     [rsp+0E0h+ppData], rdx
0x18002d379  mov     [rsp+0E0h+pdwDataSize], r14
0x18002d37e  mov     r9, rax
0x18002d381  mov     rcx, [r10+10h]
0x18002d385  call    WPP_SF_sSS_guid_d
0x18002d38a  nop
0x18002d38b  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002d38f  call    cs:__imp_SysFreeString
0x18002d395  nop
0x18002d396  mov     rcx, rbx; bstrString
0x18002d399  call    cs:__imp_SysFreeString
0x18002d39f  mov     r15b, [rbp+57h+arg_18]
0x18002d3a3  jmp     loc_18002D45A
0x18002d3a8  mov     edx, r10d
0x18002d3ab  test    r15d, r15d
0x18002d3ae  setnz   dl
0x18002d3b1  cmp     byte ptr [rbp+57h+var_90], r10b
0x18002d3b5  jz      short loc_18002D3DE
0x18002d3b7  mov     r8, [rbp+57h+pMemory]
0x18002d3bb  add     r8, 8
0x18002d3bf  sub     r8, r14
0x18002d3c2  movzx   ecx, word ptr [r14]
0x18002d3c6  movzx   eax, word ptr [r14+r8]
0x18002d3cb  sub     ecx, eax
0x18002d3cd  jnz     short loc_18002D3D7
0x18002d3cf  add     r14, 2
0x18002d3d3  test    eax, eax
0x18002d3d5  jnz     short loc_18002D3C2
0x18002d3d7  test    ecx, ecx
0x18002d3d9  jnz     short loc_18002D3DE
0x18002d3db  or      edx, 40h
0x18002d3de  mov     r9, [rbp+57h+var_78]
0x18002d3e2  add     r9, 18h
0x18002d3e6  add     r9, rsi
0x18002d3e9  mov     dword ptr [rsp+0E0h+pdwDataSize], r10d
0x18002d3ee  mov     r8, [rbp+57h+bstrString]
0x18002d3f2  mov     rcx, [rbp+57h+arg_0]
0x18002d3f6  call    ?AddProfileToList@CWcnNetworkProfileLoader@@IEAAJKPEBG0W4tagWCN_NETPROFILE_SOURCE@@@Z; CWcnNetworkProfileLoader::AddProfileToList(ulong,ushort const *,ushort const *,tagWCN_NETPROFILE_SOURCE)
0x18002d3fb  test    eax, eax
0x18002d3fd  jns     short loc_18002D430
0x18002d3ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d406  lea     rdx, WPP_GLOBAL_Control
0x18002d40d  cmp     rcx, rdx
0x18002d410  jz      short loc_18002D430
0x18002d412  cmp     byte ptr [rcx+19h], 3
0x18002d416  jb      short loc_18002D430
0x18002d418  mov     edx, 16h
0x18002d41d  mov     r9d, eax
0x18002d420  lea     r8, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids
0x18002d427  mov     rcx, [rcx+10h]
0x18002d42b  call    WPP_SF_d
0x18002d430  mov     r15b, dil
0x18002d433  mov     [rbp+57h+arg_18], dil
0x18002d437  test    [rbp+57h+arg_8], 20000h
0x18002d43e  movzx   r13d, r13b
0x18002d442  cmovnz  r13d, edi
0x18002d446  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002d44a  call    cs:__imp_SysFreeString
0x18002d450  nop
0x18002d451  mov     rcx, rbx; bstrString
0x18002d454  call    cs:__imp_SysFreeString
0x18002d45a  add     r12d, edi
0x18002d45d  mov     rdx, [rbp+57h+ppProfileList]
0x18002d461  cmp     r12d, [rdx]
0x18002d464  mov     ebx, 0
0x18002d469  jb      loc_18002D2AA
0x18002d46f  mov     r14d, [rbp+57h+var_A0]
0x18002d473  mov     rcx, rdx; pMemory
0x18002d476  call    cs:__imp_WlanFreeMemory
0x18002d47c  mov     rcx, [rbp+57h+pMemory]; pMemory
0x18002d480  test    rcx, rcx
0x18002d483  jz      short loc_18002D48B
0x18002d485  call    cs:__imp_WlanFreeMemory
0x18002d48b  mov     r10, cs:WPP_GLOBAL_Control
0x18002d492  add     r14d, edi
0x18002d495  mov     [rbp+57h+var_A0], r14d
0x18002d499  mov     rsi, [rbp+57h+ppInterfaceList]
0x18002d49d  cmp     r14d, [rsi]
0x18002d4a0  jb      loc_18002D195
0x18002d4a6  test    r15b, r15b
0x18002d4a9  jz      short loc_18002D4AD
0x18002d4ab  mov     edi, ebx
0x18002d4ad  lea     r14, WPP_GLOBAL_Control
0x18002d4b4  test    rsi, rsi
0x18002d4b7  jz      short loc_18002D4C9
0x18002d4b9  mov     rcx, rsi; pMemory
0x18002d4bc  call    cs:__imp_WlanFreeMemory
0x18002d4c2  mov     r10, cs:WPP_GLOBAL_Control
  ... truncated ...
```
