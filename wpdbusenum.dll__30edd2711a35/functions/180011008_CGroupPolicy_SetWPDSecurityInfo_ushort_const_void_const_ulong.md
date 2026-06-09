# CGroupPolicy::SetWPDSecurityInfo(ushort const *,void * const,ulong)

- ea: `0x180011008`
- end: `0x18001143e`
- name: `?SetWPDSecurityInfo@CGroupPolicy@@IEAAXPEBGQEAXK@Z`
- size: `1078`
- prototype: `void __fastcall(CGroupPolicy *this, const unsigned __int16 *, BYTE *, DEVPROPTYPE)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000f390`

## callees

- `0x1800074b4`
- `0x18000757c`
- `0x18000937c`
- `0x1800097d0`
- `0x180009be0`
- `0x18000a192`
- `0x18000e080`
- `0x18000e204`
- `0x180011008`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001135f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001135f`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800112eb`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800112eb`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x18001133e`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x18001133e`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_PropertyW` at `0x180011385`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_PropertyW` at `0x180011385`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x1800111cd`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x1800111cd`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x1800111ac`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x1800111ac`

## string_xrefs

- `0x1800110c4`: `pszVolumePath`

## pseudocode

```c
void __fastcall CGroupPolicy::SetWPDSecurityInfo(
        CGroupPolicy *this,
        const unsigned __int16 *a2,
        BYTE *a3,
        DEVPROPTYPE a4)
{
  __int64 v6; // rax
  int v7; // r12d
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // kr00_8
  unsigned int v10; // edx
  void *v11; // r15
  int DeviceInstanceIdFromInterfaceId; // eax
  unsigned __int64 v13; // rax
  WCHAR *v14; // rsi
  CPnPNotification *v15; // rcx
  __int64 v16; // rdx
  CONFIGRET Device_ID_ListW; // eax
  CONFIGRET v18; // edi
  CONFIGRET Device_ID_List_SizeW; // eax
  signed int v20; // eax
  unsigned __int64 v21; // rax
  CPnPNotification *v22; // rcx
  int v23; // edx
  WCHAR *v24; // rdi
  DEVPROPTYPE v25; // esi
  CONFIGRET v26; // eax
  signed int v27; // eax
  CONFIGRET v28; // eax
  CPnPNotification *v29; // rcx
  int v30; // edx
  __int64 v31; // rax
  ULONG BufferLen; // [rsp+30h] [rbp-D0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+34h] [rbp-CCh] BYREF
  DEVNODE pdnDevInst; // [rsp+38h] [rbp-C8h] BYREF
  ULONG PropertyBufferSize; // [rsp+3Ch] [rbp-C4h] BYREF
  WCHAR *v36; // [rsp+40h] [rbp-C0h]
  WCHAR pszFilter[200]; // [rsp+50h] [rbp-B0h] BYREF

  PropertyType = a4;
  memset_0(pszFilter, 0, sizeof(pszFilter));
  BufferLen = 1024;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = v6 + 1;
  v9 = (unsigned int)(v6 + 1);
  v8 = 2 * v9;
  if ( !is_mul_ok(v9, 2u) )
    v8 = -1;
  v11 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids,
        "pszVolumePath");
    return;
  }
  DeviceInstanceIdFromInterfaceId = GetDeviceInstanceIdFromInterfaceId(a2, v10, pszFilter);
  if ( DeviceInstanceIdFromInterfaceId < 0 )
  {
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids,
        (_DWORD)a2,
        DeviceInstanceIdFromInterfaceId);
    goto LABEL_55;
  }
  v13 = 2LL * BufferLen;
  if ( !is_mul_ok(BufferLen, 2u) )
    v13 = -1;
  v36 = (WCHAR *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v36;
  if ( !v36 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v16 = 21;
      goto LABEL_19;
    }
    goto LABEL_55;
  }
  do
  {
    Device_ID_ListW = CM_Get_Device_ID_ListW(pszFilter, v14, BufferLen, 0x120u);
    v18 = Device_ID_ListW;
    if ( Device_ID_ListW != 26 )
    {
      if ( HresultFromConfigRet(Device_ID_ListW) < 0 )
      {
        if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LOBYTE(v20) = HresultFromConfigRet(v18);
          v22 = WPP_GLOBAL_Control;
          v23 = 24;
          goto LABEL_31;
        }
LABEL_54:
        operator delete(v14);
        goto LABEL_55;
      }
      v24 = v14;
      if ( !*v14 )
        goto LABEL_54;
      v25 = PropertyType;
      while ( 1 )
      {
        pdnDevInst = 0;
        v26 = CM_Locate_DevNodeW(&pdnDevInst, v24, 0);
        v27 = HresultFromConfigRet(v26);
        if ( v27 < 0 )
        {
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          {
            goto LABEL_50;
          }
          v30 = 26;
        }
        else
        {
          PropertyType = 0;
          PropertyBufferSize = 2 * v7;
          memset_0(v11, 0, (unsigned int)(2 * v7));
          if ( CM_Get_DevNode_PropertyW(
                 pdnDevInst,
                 &DEVPKEY_WpdFs_VolumePath,
                 &PropertyType,
                 (PBYTE)v11,
                 &PropertyBufferSize,
                 0) )
          {
            goto LABEL_50;
          }
          if ( PropertyType != 18 )
            goto LABEL_50;
          if ( (unsigned int)_o__wcsicmp(a2, v11) )
            goto LABEL_50;
          v28 = CM_Set_DevNode_PropertyW(pdnDevInst, &DEVPKEY_Device_Security, 0x13u, a3, v25, 0);
          v27 = HresultFromConfigRet(v28);
          if ( v27 >= 0 )
            goto LABEL_50;
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          {
            goto LABEL_50;
          }
          v30 = 25;
        }
        WPP_SF_Sd(
          *((_QWORD *)v29 + 2),
          v30,
          (unsigned int)WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids,
          (_DWORD)v24,
          v27);
LABEL_50:
        v31 = -1;
        do
          ++v31;
        while ( v24[v31] );
        v24 += v31 + 1;
        if ( !*v24 )
        {
          v14 = v36;
          goto LABEL_54;
        }
      }
    }
    Device_ID_List_SizeW = CM_Get_Device_ID_List_SizeW(&BufferLen, pszFilter, 0x120u);
    v20 = HresultFromConfigRet(Device_ID_List_SizeW);
    if ( v20 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v23 = 22;
LABEL_31:
        WPP_SF_Sd(
          *((_QWORD *)v22 + 2),
          v23,
          (unsigned int)WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids,
          (_DWORD)a2,
          v20);
        goto LABEL_54;
      }
      goto LABEL_54;
    }
    operator delete(v14);
    v21 = 2LL * BufferLen;
    if ( !is_mul_ok(BufferLen, 2u) )
      v21 = -1;
    v36 = (WCHAR *)operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
    v14 = v36;
  }
  while ( v36 );
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v16 = 23;
LABEL_19:
    WPP_SF_s(*((_QWORD *)v15 + 2), v16, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids, "pszChildDeviceIdList");
  }
LABEL_55:
  operator delete(v11);
}

```

## disassembly

```asm
0x180011008  mov     [rsp-8+arg_0], rbx
0x18001100d  push    rbp
0x18001100e  push    rsi
0x18001100f  push    rdi
0x180011010  push    r12
0x180011012  push    r13
0x180011014  push    r14
0x180011016  push    r15
0x180011018  lea     rbp, [rsp-0F0h]
0x180011020  sub     rsp, 1F0h
0x180011027  mov     rax, cs:__security_cookie
0x18001102e  xor     rax, rsp
0x180011031  mov     [rbp+120h+var_40], rax
0x180011038  mov     r13, r8
0x18001103b  mov     [rsp+220h+PropertyType], r9d
0x180011040  mov     r14, rdx
0x180011043  lea     rcx, [rsp+220h+pszFilter]; void *
0x180011048  xor     edx, edx; Val
0x18001104a  mov     r8d, 190h; Size
0x180011050  call    memset_0
0x180011055  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011059  mov     [rsp+220h+BufferLen], 400h
0x180011061  mov     rax, rsi
0x180011064  xor     ebx, ebx
0x180011066  inc     rax
0x180011069  cmp     [r14+rax*2], bx
0x18001106e  jnz     short loc_180011066
0x180011070  lea     r12d, [rax+1]
0x180011074  mov     edi, 2
0x180011079  mov     ecx, r12d
0x18001107c  mov     eax, edi
0x18001107e  mul     rcx
0x180011081  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011088  cmovb   rax, rsi
0x18001108c  mov     rcx, rax; unsigned __int64
0x18001108f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180011094  mov     r15, rax
0x180011097  test    rax, rax
0x18001109a  jnz     short loc_1800110DC
0x18001109c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110a3  lea     rbx, WPP_GLOBAL_Control
0x1800110aa  cmp     rcx, rbx
0x1800110ad  jz      loc_180011414
0x1800110b3  test    [rcx+1Ch], dil
0x1800110b7  jz      loc_180011414
0x1800110bd  mov     rcx, [rcx+10h]
0x1800110c1  lea     edx, [rdi+11h]
0x1800110c4  lea     r9, aPszvolumepath; "pszVolumePath"
0x1800110cb  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x1800110d2  call    WPP_SF_s
0x1800110d7  jmp     loc_180011414
0x1800110dc  lea     r8, [rsp+220h+pszFilter]; unsigned __int16 *
0x1800110e1  mov     rcx, r14; unsigned __int16 *
0x1800110e4  call    ?GetDeviceInstanceIdFromInterfaceId@@YAJPEBGKPEAG@Z; GetDeviceInstanceIdFromInterfaceId(ushort const *,ulong,ushort *)
0x1800110e9  test    eax, eax
0x1800110eb  jns     short loc_18001112F
0x1800110ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110f4  lea     rbx, WPP_GLOBAL_Control
0x1800110fb  cmp     rcx, rbx
0x1800110fe  jz      loc_18001140C
0x180011104  test    [rcx+1Ch], dil
0x180011108  jz      loc_18001140C
0x18001110e  mov     rcx, [rcx+10h]
0x180011112  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x180011119  mov     edx, 14h
0x18001111e  mov     dword ptr [rsp+220h+PropertyBufferSize], eax
0x180011122  mov     r9, r14
0x180011125  call    WPP_SF_Sd
0x18001112a  jmp     loc_18001140C
0x18001112f  mov     ecx, [rsp+220h+BufferLen]
0x180011133  mov     rax, rdi
0x180011136  mul     rcx
0x180011139  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011140  cmovb   rax, rsi
0x180011144  mov     rcx, rax; unsigned __int64
0x180011147  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001114c  mov     [rsp+220h+var_1E0], rax
0x180011151  mov     rsi, rax
0x180011154  test    rax, rax
0x180011157  jnz     short loc_180011199
0x180011159  mov     rcx, cs:WPP_GLOBAL_Control
0x180011160  lea     rbx, WPP_GLOBAL_Control
0x180011167  cmp     rcx, rbx
0x18001116a  jz      loc_18001140C
0x180011170  test    [rcx+1Ch], dil
0x180011174  jz      loc_18001140C
0x18001117a  lea     edx, [rax+15h]
0x18001117d  mov     rcx, [rcx+10h]
0x180011181  lea     r9, aPszchilddevice; "pszChildDeviceIdList"
0x180011188  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x18001118f  call    WPP_SF_s
0x180011194  jmp     loc_18001140C
0x180011199  mov     r8d, [rsp+220h+BufferLen]; BufferLen
0x18001119e  lea     rcx, [rsp+220h+pszFilter]; pszFilter
0x1800111a3  mov     r9d, 120h; ulFlags
0x1800111a9  mov     rdx, rsi; Buffer
0x1800111ac  call    cs:__imp_CM_Get_Device_ID_ListW
0x1800111b2  mov     edi, eax
0x1800111b4  cmp     eax, 1Ah
0x1800111b7  jnz     loc_180011282
0x1800111bd  mov     r8d, 120h; ulFlags
0x1800111c3  lea     rdx, [rsp+220h+pszFilter]; pszFilter
0x1800111c8  lea     rcx, [rsp+220h+BufferLen]; pulLen
0x1800111cd  call    cs:__imp_CM_Get_Device_ID_List_SizeW
0x1800111d3  mov     ecx, eax; unsigned int
0x1800111d5  call    ?HresultFromConfigRet@@YAJK@Z; HresultFromConfigRet(ulong)
0x1800111da  test    eax, eax
0x1800111dc  js      short loc_180011240
0x1800111de  mov     rcx, rsi; Block
0x1800111e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800111e6  mov     ecx, [rsp+220h+BufferLen]
0x1800111ea  lea     eax, [rdi-18h]
0x1800111ed  mul     rcx
0x1800111f0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800111f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800111fe  cmovb   rax, rcx
0x180011202  mov     rcx, rax; unsigned __int64
0x180011205  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001120a  mov     [rsp+220h+var_1E0], rax
0x18001120f  mov     rsi, rax
0x180011212  test    rax, rax
0x180011215  jnz     short loc_180011199
0x180011217  mov     rcx, cs:WPP_GLOBAL_Control
0x18001121e  lea     rbx, WPP_GLOBAL_Control
0x180011225  cmp     rcx, rbx
0x180011228  jz      loc_18001140C
0x18001122e  test    byte ptr [rcx+1Ch], 2
0x180011232  jz      loc_18001140C
0x180011238  lea     edx, [rdi-3]
0x18001123b  jmp     loc_18001117D
0x180011240  mov     rcx, cs:WPP_GLOBAL_Control
0x180011247  lea     rbx, WPP_GLOBAL_Control
0x18001124e  cmp     rcx, rbx
0x180011251  jz      loc_180011404
0x180011257  test    byte ptr [rcx+1Ch], 2
0x18001125b  jz      loc_180011404
0x180011261  mov     edx, 16h
0x180011266  mov     rcx, [rcx+10h]
0x18001126a  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x180011271  mov     r9, r14
0x180011274  mov     dword ptr [rsp+220h+PropertyBufferSize], eax
0x180011278  call    WPP_SF_Sd
0x18001127d  jmp     loc_180011404
0x180011282  mov     ecx, edi; unsigned int
0x180011284  call    ?HresultFromConfigRet@@YAJK@Z; HresultFromConfigRet(ulong)
0x180011289  test    eax, eax
0x18001128b  jns     short loc_1800112C3
0x18001128d  mov     rax, cs:WPP_GLOBAL_Control
0x180011294  lea     rbx, WPP_GLOBAL_Control
0x18001129b  cmp     rax, rbx
0x18001129e  jz      loc_180011404
0x1800112a4  test    byte ptr [rax+1Ch], 2
0x1800112a8  jz      loc_180011404
0x1800112ae  mov     ecx, edi; unsigned int
0x1800112b0  call    ?HresultFromConfigRet@@YAJK@Z; HresultFromConfigRet(ulong)
0x1800112b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112bc  mov     edx, 18h
0x1800112c1  jmp     short loc_180011266
0x1800112c3  mov     rdi, rsi
0x1800112c6  cmp     [rsi], bx
0x1800112c9  jz      loc_180011404
0x1800112cf  mov     esi, [rsp+220h+PropertyType]
0x1800112d3  lea     rbx, WPP_GLOBAL_Control
0x1800112da  xor     edx, edx
0x1800112dc  mov     [rsp+220h+pdnDevInst], edx
0x1800112e0  lea     rcx, [rsp+220h+pdnDevInst]; pdnDevInst
0x1800112e5  mov     rdx, rdi; pDeviceID
0x1800112e8  xor     r8d, r8d; ulFlags
0x1800112eb  call    cs:__imp_CM_Locate_DevNodeW
0x1800112f1  mov     ecx, eax; unsigned int
0x1800112f3  call    ?HresultFromConfigRet@@YAJK@Z; HresultFromConfigRet(ulong)
0x1800112f8  xor     edx, edx; Val
0x1800112fa  test    eax, eax
0x1800112fc  js      loc_1800113B1
0x180011302  lea     eax, [r12+r12]
0x180011306  mov     [rsp+220h+PropertyType], edx
0x18001130a  mov     r8d, eax; Size
0x18001130d  mov     rcx, r15; void *
0x180011310  mov     [rsp+220h+var_1E4], eax
0x180011314  call    memset_0
0x180011319  mov     ecx, [rsp+220h+pdnDevInst]; dnDevInst
0x18001131d  lea     rax, [rsp+220h+var_1E4]
0x180011322  mov     [rsp+220h+ulFlags], 0; ulFlags
0x18001132a  lea     r8, [rsp+220h+PropertyType]; PropertyType
0x18001132f  mov     r9, r15; PropertyBuffer
0x180011332  mov     [rsp+220h+PropertyBufferSize], rax; PropertyBufferSize
0x180011337  lea     rdx, DEVPKEY_WpdFs_VolumePath; PropertyKey
0x18001133e  call    cs:__imp_CM_Get_DevNode_PropertyW
0x180011344  xor     edx, edx
0x180011346  test    eax, eax
0x180011348  jnz     loc_1800113E1
0x18001134e  cmp     [rsp+220h+PropertyType], 12h
0x180011353  jnz     loc_1800113E1
0x180011359  mov     rdx, r15
0x18001135c  mov     rcx, r14
0x18001135f  call    cs:__imp__o__wcsicmp
0x180011365  xor     edx, edx
0x180011367  test    eax, eax
0x180011369  jnz     short loc_1800113E1
0x18001136b  mov     ecx, [rsp+220h+pdnDevInst]; dnDevInst
0x18001136f  lea     r8d, [rdx+13h]; PropertyType
0x180011373  mov     [rsp+220h+ulFlags], edx; ulFlags
0x180011377  mov     r9, r13; PropertyBuffer
0x18001137a  lea     rdx, DEVPKEY_Device_Security; PropertyKey
0x180011381  mov     dword ptr [rsp+220h+PropertyBufferSize], esi; PropertyBufferSize
0x180011385  call    cs:__imp_CM_Set_DevNode_PropertyW
0x18001138b  mov     ecx, eax; unsigned int
0x18001138d  call    ?HresultFromConfigRet@@YAJK@Z; HresultFromConfigRet(ulong)
0x180011392  xor     edx, edx
0x180011394  test    eax, eax
0x180011396  jns     short loc_1800113E1
0x180011398  mov     rcx, cs:WPP_GLOBAL_Control
0x18001139f  cmp     rcx, rbx
0x1800113a2  jz      short loc_1800113E1
0x1800113a4  test    byte ptr [rcx+1Ch], 2
0x1800113a8  jz      short loc_1800113E1
0x1800113aa  mov     edx, 19h
0x1800113af  jmp     short loc_1800113C8
0x1800113b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113b8  cmp     rcx, rbx
0x1800113bb  jz      short loc_1800113E1
0x1800113bd  test    byte ptr [rcx+1Ch], 2
0x1800113c1  jz      short loc_1800113E1
0x1800113c3  mov     edx, 1Ah
0x1800113c8  mov     rcx, [rcx+10h]
0x1800113cc  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x1800113d3  mov     r9, rdi
0x1800113d6  mov     dword ptr [rsp+220h+PropertyBufferSize], eax
0x1800113da  call    WPP_SF_Sd
0x1800113df  xor     edx, edx
0x1800113e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800113e5  inc     rax
0x1800113e8  cmp     [rdi+rax*2], dx
0x1800113ec  jnz     short loc_1800113E5
0x1800113ee  lea     rdi, [rdi+rax*2]
0x1800113f2  add     rdi, 2
0x1800113f6  cmp     [rdi], dx
0x1800113f9  jnz     loc_1800112DC
0x1800113ff  mov     rsi, [rsp+220h+var_1E0]
0x180011404  mov     rcx, rsi; Block
0x180011407  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001140c  mov     rcx, r15; Block
0x18001140f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011414  mov     rcx, [rbp+120h+var_40]
0x18001141b  xor     rcx, rsp; StackCookie
0x18001141e  call    __security_check_cookie
0x180011423  mov     rbx, [rsp+220h+arg_0]
0x18001142b  add     rsp, 1F0h
0x180011432  pop     r15
0x180011434  pop     r14
0x180011436  pop     r13
0x180011438  pop     r12
0x18001143a  pop     rdi
0x18001143b  pop     rsi
0x18001143c  pop     rbp
0x18001143d  retn
```
