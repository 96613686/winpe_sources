# InterfaceMgr::AcquireCellularConnection(void)

- ea: `0x18000ffe4`
- end: `0x1800102a9`
- name: `?AcquireCellularConnection@InterfaceMgr@@AEAAJXZ`
- size: `709`
- prototype: `__int64 __fastcall(InterfaceMgr *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180010b9c`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18000d8e4`
- `0x18000ffe4`
- `0x1800229b8`
- `0x180023778`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001015c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001015c`
- `wcmapi!WcmOpenOnDemandRequestHandleByWwanProfileName` at `0x18001010e`
- `wcmapi!WcmOpenOnDemandRequestHandleByWwanProfileName` at `0x18001010e`
- `wcmapi!WcmFreeMemory` at `0x180010173`
- `wcmapi!WcmFreeMemory` at `0x180010173`
- `wcmapi!WcmStartOnDemandRequest` at `0x1800101d1`
- `wcmapi!WcmStartOnDemandRequest` at `0x1800101d1`
- `wcmapi!WcmQueryOnDemandRequestStateInfo` at `0x180010211`
- `wcmapi!WcmQueryOnDemandRequestStateInfo` at `0x180010211`

## pseudocode

```c
__int64 __fastcall InterfaceMgr::AcquireCellularConnection(InterfaceMgr *this)
{
  int TetheringProfileNameOrConnectInternetProfile; // eax
  signed int v3; // ebx
  TetheringServiceTelemetry *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  _QWORD *v7; // r14
  int v8; // eax
  TetheringServiceTelemetry *v9; // rcx
  __int64 v10; // rdx
  int v12; // eax
  int v13; // eax
  bool v14; // [rsp+70h] [rbp+40h] BYREF
  bool v15; // [rsp+78h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+50h] BYREF
  __int64 v17; // [rsp+88h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
  hMem = 0;
  v14 = 0;
  v17 = 0;
  TetheringProfileNameOrConnectInternetProfile = GetTetheringProfileNameOrConnectInternetProfile(
                                                   (const struct _GUID *)this + 4,
                                                   (unsigned __int16 **)&hMem,
                                                   (unsigned int *)this + 52,
                                                   &v14);
  v3 = TetheringProfileNameOrConnectInternetProfile;
  if ( TetheringProfileNameOrConnectInternetProfile >= 0 )
  {
    if ( !v14 )
      goto LABEL_26;
    v15 = 0;
    TetheringProfileNameOrConnectInternetProfile = IsInterfaceDataEnabled((const struct _GUID *)this + 4, &v15);
    v3 = TetheringProfileNameOrConnectInternetProfile;
    if ( TetheringProfileNameOrConnectInternetProfile >= 0 )
    {
      if ( v15 )
      {
        v7 = (_QWORD *)((char *)this + 48);
        v8 = WcmOpenOnDemandRequestHandleByWwanProfileName((char *)this + 64, hMem, (char *)this + 48);
        v3 = v8;
        if ( v8 > 0 )
          v3 = (unsigned __int16)v8 | 0x80070000;
        if ( v3 >= 0 )
        {
          v12 = WcmStartOnDemandRequest(*v7);
          v3 = v12;
          if ( v12 > 0 )
            v3 = (unsigned __int16)v12 | 0x80070000;
          if ( v3 >= 0 )
          {
            v13 = WcmQueryOnDemandRequestStateInfo(*v7, &v17);
            v3 = v13;
            if ( v13 > 0 )
              v3 = (unsigned __int16)v13 | 0x80070000;
            if ( v3 >= 0 )
            {
              if ( *(_DWORD *)(v17 + 548) == 3 )
              {
                *(_OWORD *)((char *)this + 172) = *(_OWORD *)v17;
              }
              else
              {
                v3 = -2095972349;
                if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
                }
              }
              goto LABEL_26;
            }
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_26;
            }
            v10 = 86;
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_26;
            }
            v10 = 85;
          }
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_26;
          }
          v10 = 84;
        }
        WPP_SF_d(*((_QWORD *)v9 + 2), v10, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, (unsigned int)v3);
        goto LABEL_26;
      }
      v3 = -2095972334;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 83;
        v6 = 2198994962LL;
        goto LABEL_9;
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 82;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 81;
LABEL_8:
      v6 = (unsigned int)TetheringProfileNameOrConnectInternetProfile;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, v6);
    }
  }
LABEL_26:
  LocalFree(hMem);
  hMem = 0;
  if ( v17 )
  {
    WcmFreeMemory();
    v17 = 0;
  }
  if ( v3 < 0 && v3 != -2095972334 && v3 != -2095972331 )
    v3 = -2095972349;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids,
      (unsigned int)v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ffe4  push    rbp
0x18000ffe6  push    rbx
0x18000ffe7  push    rsi
0x18000ffe8  push    rdi
0x18000ffe9  push    r12
0x18000ffeb  push    r13
0x18000ffed  push    r14
0x18000ffef  mov     rbp, rsp
0x18000fff2  sub     rsp, 30h
0x18000fff6  mov     rsi, rcx
0x18000fff9  mov     rcx, cs:WPP_GLOBAL_Control
0x180010000  lea     r12, WPP_GLOBAL_Control
0x180010007  lea     r13, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x18001000e  cmp     rcx, r12
0x180010011  jz      short loc_18001002A
0x180010013  test    byte ptr [rcx+1Ch], 8
0x180010017  jz      short loc_18001002A
0x180010019  mov     rcx, [rcx+10h]
0x18001001d  mov     edx, 50h ; 'P'
0x180010022  mov     r8, r13
0x180010025  call    WPP_SF_
0x18001002a  lea     rdi, [rsi+40h]
0x18001002e  mov     [rbp+hMem], 0
0x180010036  mov     rcx, rdi; struct _GUID *
0x180010039  mov     [rbp+arg_0], 0
0x18001003d  lea     r8, [rsi+0D0h]; unsigned int *
0x180010044  mov     [rbp+arg_18], 0
0x18001004c  lea     r9, [rbp+arg_0]; bool *
0x180010050  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x180010054  call    ?GetTetheringProfileNameOrConnectInternetProfile@@YAJPEBU_GUID@@PEAPEAGPEAKPEA_N@Z; GetTetheringProfileNameOrConnectInternetProfile(_GUID const *,ushort * *,ulong *,bool *)
0x180010059  mov     ebx, eax
0x18001005b  mov     r14d, 83120003h
0x180010061  test    eax, eax
0x180010063  jns     short loc_180010098
0x180010065  mov     rcx, cs:WPP_GLOBAL_Control
0x18001006c  cmp     rcx, r12
0x18001006f  jz      loc_180010158
0x180010075  test    byte ptr [rcx+1Ch], 1
0x180010079  jz      loc_180010158
0x18001007f  mov     edx, 51h ; 'Q'
0x180010084  mov     r9d, eax
0x180010087  mov     rcx, [rcx+10h]
0x18001008b  mov     r8, r13
0x18001008e  call    WPP_SF_d
0x180010093  jmp     loc_180010158
0x180010098  cmp     [rbp+arg_0], 0
0x18001009c  jz      loc_180010158
0x1800100a2  lea     rdx, [rbp+arg_8]; bool *
0x1800100a6  mov     [rbp+arg_8], 0
0x1800100aa  mov     rcx, rdi; struct _GUID *
0x1800100ad  call    ?IsInterfaceDataEnabled@@YAJPEBU_GUID@@PEA_N@Z; IsInterfaceDataEnabled(_GUID const *,bool *)
0x1800100b2  mov     ebx, eax
0x1800100b4  test    eax, eax
0x1800100b6  jns     short loc_1800100D9
0x1800100b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100bf  cmp     rcx, r12
0x1800100c2  jz      loc_180010158
0x1800100c8  test    byte ptr [rcx+1Ch], 1
0x1800100cc  jz      loc_180010158
0x1800100d2  mov     edx, 52h ; 'R'
0x1800100d7  jmp     short loc_180010084
0x1800100d9  cmp     [rbp+arg_8], 0
0x1800100dd  jnz     short loc_180010100
0x1800100df  mov     ebx, 83120012h
0x1800100e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100eb  cmp     rcx, r12
0x1800100ee  jz      short loc_180010158
0x1800100f0  test    byte ptr [rcx+1Ch], 1
0x1800100f4  jz      short loc_180010158
0x1800100f6  mov     edx, 53h ; 'S'
0x1800100fb  mov     r9d, ebx
0x1800100fe  jmp     short loc_180010087
0x180010100  mov     rdx, [rbp+hMem]
0x180010104  lea     r14, [rsi+30h]
0x180010108  mov     r8, r14
0x18001010b  mov     rcx, rdi
0x18001010e  call    cs:__imp_WcmOpenOnDemandRequestHandleByWwanProfileName
0x180010114  mov     ebx, eax
0x180010116  mov     edi, 80070000h
0x18001011b  test    eax, eax
0x18001011d  jle     short loc_180010124
0x18001011f  movzx   ebx, ax
0x180010122  or      ebx, edi
0x180010124  test    ebx, ebx
0x180010126  jns     loc_1800101CE
0x18001012c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010133  cmp     rcx, r12
0x180010136  jz      short loc_180010152
0x180010138  test    byte ptr [rcx+1Ch], 1
0x18001013c  jz      short loc_180010152
0x18001013e  mov     edx, 54h ; 'T'
0x180010143  mov     rcx, [rcx+10h]
0x180010147  mov     r9d, ebx
0x18001014a  mov     r8, r13
0x18001014d  call    WPP_SF_d
0x180010152  mov     r14d, 83120003h
0x180010158  mov     rcx, [rbp+hMem]; hMem
0x18001015c  call    cs:__imp_LocalFree
0x180010162  mov     rcx, [rbp+arg_18]
0x180010166  mov     [rbp+hMem], 0
0x18001016e  test    rcx, rcx
0x180010171  jz      short loc_180010181
0x180010173  call    cs:__imp_WcmFreeMemory
0x180010179  mov     [rbp+arg_18], 0
0x180010181  test    ebx, ebx
0x180010183  jns     short loc_180010197
0x180010185  cmp     ebx, 83120012h
0x18001018b  jz      short loc_180010197
0x18001018d  cmp     ebx, 83120015h
0x180010193  cmovnz  ebx, r14d
0x180010197  mov     rcx, cs:WPP_GLOBAL_Control
0x18001019e  cmp     rcx, r12
0x1800101a1  jz      short loc_1800101BD
0x1800101a3  test    byte ptr [rcx+1Ch], 8
0x1800101a7  jz      short loc_1800101BD
0x1800101a9  mov     rcx, [rcx+10h]
0x1800101ad  mov     edx, 58h ; 'X'
0x1800101b2  mov     r9d, ebx
0x1800101b5  mov     r8, r13
0x1800101b8  call    WPP_SF_d
0x1800101bd  mov     eax, ebx
0x1800101bf  add     rsp, 30h
0x1800101c3  pop     r14
0x1800101c5  pop     r13
0x1800101c7  pop     r12
0x1800101c9  pop     rdi
0x1800101ca  pop     rsi
0x1800101cb  pop     rbx
0x1800101cc  pop     rbp
0x1800101cd  retn
0x1800101ce  mov     rcx, [r14]
0x1800101d1  call    cs:__imp_WcmStartOnDemandRequest
0x1800101d7  mov     ebx, eax
0x1800101d9  test    eax, eax
0x1800101db  jle     short loc_1800101E2
0x1800101dd  movzx   ebx, ax
0x1800101e0  or      ebx, edi
0x1800101e2  test    ebx, ebx
0x1800101e4  jns     short loc_18001020A
0x1800101e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101ed  cmp     rcx, r12
0x1800101f0  jz      loc_180010152
0x1800101f6  test    byte ptr [rcx+1Ch], 1
0x1800101fa  jz      loc_180010152
0x180010200  mov     edx, 55h ; 'U'
0x180010205  jmp     loc_180010143
0x18001020a  mov     rcx, [r14]
0x18001020d  lea     rdx, [rbp+arg_18]
0x180010211  call    cs:__imp_WcmQueryOnDemandRequestStateInfo
0x180010217  mov     ebx, eax
0x180010219  test    eax, eax
0x18001021b  jle     short loc_180010222
0x18001021d  movzx   ebx, ax
0x180010220  or      ebx, edi
0x180010222  test    ebx, ebx
0x180010224  jns     short loc_18001024A
0x180010226  mov     rcx, cs:WPP_GLOBAL_Control
0x18001022d  cmp     rcx, r12
0x180010230  jz      loc_180010152
0x180010236  test    byte ptr [rcx+1Ch], 1
0x18001023a  jz      loc_180010152
0x180010240  mov     edx, 56h ; 'V'
0x180010245  jmp     loc_180010143
0x18001024a  mov     rax, [rbp+arg_18]
0x18001024e  mov     r14d, 83120003h
0x180010254  mov     r9d, [rax+224h]
0x18001025b  cmp     r9d, 3
0x18001025f  jz      short loc_180010299
0x180010261  mov     ebx, r14d
0x180010264  mov     rcx, cs:WPP_GLOBAL_Control
0x18001026b  cmp     rcx, r12
0x18001026e  jz      loc_180010158
0x180010274  test    byte ptr [rcx+1Ch], 1
0x180010278  jz      loc_180010158
0x18001027e  mov     rcx, [rcx+10h]
0x180010282  mov     edx, 57h ; 'W'
0x180010287  mov     r8, r13
0x18001028a  mov     [rsp+30h+var_10], r14d
0x18001028f  call    WPP_SF_dd
0x180010294  jmp     loc_180010158
0x180010299  movups  xmm0, xmmword ptr [rax]
0x18001029c  movdqu  xmmword ptr [rsi+0ACh], xmm0
0x1800102a4  jmp     loc_180010158
```
