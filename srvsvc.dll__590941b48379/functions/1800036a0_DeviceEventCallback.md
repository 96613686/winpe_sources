# DeviceEventCallback

- ea: `0x1800036a0`
- end: `0x180003af7`
- name: `DeviceEventCallback`
- size: `1111`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800036a0`
- `0x180003b00`
- `0x18000a220`
- `0x18000b940`
- `0x18001d230`
- `0x180020dc0`
- `0x180020de8`
- `0x18002dbfc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800038f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800039cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800038f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800039cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003835`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003aec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003835`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003aec`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180003a88`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180003a88`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003889`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003a75`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003889`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003a75`
- `ntdll!RtlReleaseResource` at `0x18000381c`
- `ntdll!RtlReleaseResource` at `0x18000389f`
- `ntdll!RtlReleaseResource` at `0x18000381c`
- `ntdll!RtlReleaseResource` at `0x18000389f`

## pseudocode

```c
__int64 __fastcall DeviceEventCallback(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v7; // rax
  _QWORD *v8; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // rax
  _QWORD *v16; // r14
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  size_t v19; // rbx
  wchar_t *v20; // rax
  int v21; // eax
  void *v22; // rcx
  size_t pcchLength[3]; // [rsp+20h] [rbp-18h] BYREF

  pcchLength[0] = 0;
  if ( !a3 )
  {
    if ( SsVolumeResourceInitialized )
    {
      RtlAcquireResourceExclusive(&SsVolumeResource, 1u);
      SsRegisterVolumeChange((LPCWSTR)(a4 + 24));
      RtlReleaseResource(&SsVolumeResource);
      return 0;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return 0;
    }
    v14 = 39;
LABEL_28:
    WPP_SF_(v13[2], v14, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids);
    return 0;
  }
  if ( ((a3 - 1) & 0xFFFFFFFB) == 0 )
  {
    if ( !SsVolumeResourceInitialized )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        return 0;
      }
      v14 = 40;
      goto LABEL_28;
    }
    v15 = LocalAlloc(0x40u, 0x10u);
    v16 = v15;
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids);
      }
      return 0;
    }
    *(_OWORD *)v15 = 0;
    if ( a3 == 1 )
    {
      *(_WORD *)v15 = 2;
      if ( StringCchLengthW((STRSAFE_PCNZWCH)(a4 + 24), 0x7FFFFFFFu, pcchLength) < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_30;
        }
        v18 = 42;
        goto LABEL_54;
      }
      v19 = pcchLength[0];
      v20 = (wchar_t *)LocalAlloc(0x40u, 2 * pcchLength[0] + 2);
      v16[1] = v20;
      if ( !v20 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_30;
        }
        v18 = 43;
        goto LABEL_54;
      }
      if ( StringCchCopyW(v20, v19 + 1, (STRSAFE_LPCWSTR)(a4 + 24)) < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_30;
        }
        v18 = 44;
LABEL_54:
        WPP_SF_(v17[2], v18, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids);
        goto LABEL_30;
      }
    }
    else
    {
      *(_WORD *)v15 = 1;
      v15[1] = a1;
      v21 = DiscoverDrives();
      AlreadyAddedBitMask &= v21;
      DiskConfiguration = v21;
    }
    RtlAcquireResourceExclusive(&SsVolumeResource, 1u);
    if ( TrySubmitThreadpoolCallback(SsDeferredUnregisterVolumeChange, v16, 0) )
    {
      v16 = 0;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids);
    }
    RtlReleaseResource(&SsVolumeResource);
    if ( !v16 )
      return 0;
LABEL_30:
    if ( *(_WORD *)v16 == 2 )
    {
      v22 = (void *)v16[1];
      if ( v22 )
        LocalFree(v22);
    }
    LocalFree(v16);
    return 0;
  }
  if ( a3 == 6 )
  {
    v7 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1;
    if ( !v7 )
      v7 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4;
    if ( v7 )
    {
      v11 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_IO_VOLUME_NAME_CHANGE.Data1;
      if ( !v11 )
        v11 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_IO_VOLUME_NAME_CHANGE.Data4;
      if ( v11 )
      {
        v12 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1;
        if ( !v12 )
          v12 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data4;
        if ( !v12 )
        {
          SsUpdateShares();
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = 48;
            goto LABEL_22;
          }
        }
      }
      else
      {
        SsUpdateShares();
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 47;
          goto LABEL_22;
        }
      }
    }
    else
    {
      SsUpdateShares();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 46;
LABEL_22:
        WPP_SF_d(v8[2], v10, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids, (unsigned int)DiskConfiguration);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800036a0  mov     [rsp+arg_8], rbx
0x1800036a5  mov     [rsp+arg_10], rsi
0x1800036aa  push    rdi
0x1800036ab  sub     rsp, 30h
0x1800036af  mov     [rsp+38h+pcchLength], 0
0x1800036b8  mov     rdi, r9
0x1800036bb  mov     ebx, r8d
0x1800036be  mov     rsi, rcx
0x1800036c1  test    r8d, r8d
0x1800036c4  jz      loc_180003845
0x1800036ca  lea     eax, [r8-1]
0x1800036ce  test    eax, 0FFFFFFFBh
0x1800036d3  jz      loc_1800037C3
0x1800036d9  cmp     ebx, 6
0x1800036dc  jnz     short loc_180003713
0x1800036de  mov     rax, [r9+8]
0x1800036e2  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x1800036e9  jnz     short loc_1800036F6
0x1800036eb  mov     rax, [r9+10h]
0x1800036ef  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x1800036f6  test    rax, rax
0x1800036f9  jnz     short loc_180003738
0x1800036fb  call    SsUpdateShares
0x180003700  mov     rcx, cs:WPP_GLOBAL_Control
0x180003707  lea     rax, WPP_GLOBAL_Control
0x18000370e  cmp     rcx, rax
0x180003711  jnz     short loc_180003725
0x180003713  mov     rbx, [rsp+38h+arg_8]
0x180003718  xor     eax, eax
0x18000371a  mov     rsi, [rsp+38h+arg_10]
0x18000371f  add     rsp, 30h
0x180003723  pop     rdi
0x180003724  retn
0x180003725  test    byte ptr [rcx+1Ch], 1
0x180003729  jz      short loc_180003713
0x18000372b  cmp     byte ptr [rcx+19h], 2
0x18000372f  jb      short loc_180003713
0x180003731  mov     edx, 2Eh ; '.'
0x180003736  jmp     short loc_1800037A7
0x180003738  mov     rax, [r9+8]
0x18000373c  sub     rax, qword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data1
0x180003743  jnz     short loc_180003750
0x180003745  mov     rax, [r9+10h]
0x180003749  sub     rax, qword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data4
0x180003750  test    rax, rax
0x180003753  jz      loc_1800038AA
0x180003759  mov     rax, [r9+8]
0x18000375d  sub     rax, qword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1
0x180003764  jnz     short loc_180003771
0x180003766  mov     rax, [r9+10h]
0x18000376a  sub     rax, qword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data4
0x180003771  test    rax, rax
0x180003774  jnz     short loc_180003713
0x180003776  call    SsUpdateShares
0x18000377b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003782  lea     rax, WPP_GLOBAL_Control
0x180003789  cmp     rcx, rax
0x18000378c  jz      short loc_180003713
0x18000378e  test    byte ptr [rcx+1Ch], 1
0x180003792  jz      loc_180003713
0x180003798  cmp     byte ptr [rcx+19h], 2
0x18000379c  jb      loc_180003713
0x1800037a2  mov     edx, 30h ; '0'
0x1800037a7  mov     r9d, cs:DiskConfiguration
0x1800037ae  lea     r8, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids
0x1800037b5  mov     rcx, [rcx+10h]
0x1800037b9  call    WPP_SF_d
0x1800037be  jmp     loc_180003713
0x1800037c3  cmp     cs:SsVolumeResourceInitialized, 0
0x1800037ca  jnz     loc_1800038E4
0x1800037d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037d7  lea     rax, WPP_GLOBAL_Control
0x1800037de  cmp     rcx, rax
0x1800037e1  jz      loc_180003713
0x1800037e7  test    byte ptr [rcx+1Ch], 1
0x1800037eb  jz      loc_180003713
0x1800037f1  cmp     byte ptr [rcx+19h], 1
0x1800037f5  jb      loc_180003713
0x1800037fb  mov     edx, 28h ; '('
0x180003800  mov     rcx, [rcx+10h]
0x180003804  lea     r8, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids
0x18000380b  call    WPP_SF_
0x180003810  jmp     loc_180003713
0x180003815  lea     rcx, SsVolumeResource; Resource
0x18000381c  call    cs:__imp_RtlReleaseResource
0x180003822  test    r14, r14
0x180003825  jz      short loc_18000383B
0x180003827  cmp     word ptr [r14], 2
0x18000382c  jz      loc_180003ADF
0x180003832  mov     rcx, r14; hMem
0x180003835  call    cs:__imp_LocalFree
0x18000383b  mov     r14, [rsp+38h+arg_0]
0x180003840  jmp     loc_180003713
0x180003845  cmp     cs:SsVolumeResourceInitialized, 0
0x18000384c  jnz     short loc_180003880
0x18000384e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003855  lea     rax, WPP_GLOBAL_Control
0x18000385c  cmp     rcx, rax
0x18000385f  jz      loc_180003713
0x180003865  test    byte ptr [rcx+1Ch], 1
0x180003869  jz      loc_180003713
0x18000386f  cmp     byte ptr [rcx+19h], 1
0x180003873  jb      loc_180003713
0x180003879  mov     edx, 27h ; '''
0x18000387e  jmp     short loc_180003800
0x180003880  mov     dl, 1; Wait
0x180003882  lea     rcx, SsVolumeResource; Resource
0x180003889  call    cs:__imp_RtlAcquireResourceExclusive
0x18000388f  lea     rcx, [rdi+18h]; lpFileName
0x180003893  call    SsRegisterVolumeChange
0x180003898  lea     rcx, SsVolumeResource; Resource
0x18000389f  call    cs:__imp_RtlReleaseResource
0x1800038a5  jmp     loc_180003713
0x1800038aa  call    SsUpdateShares
0x1800038af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038b6  lea     rax, WPP_GLOBAL_Control
0x1800038bd  cmp     rcx, rax
0x1800038c0  jz      loc_180003713
0x1800038c6  test    byte ptr [rcx+1Ch], 1
0x1800038ca  jz      loc_180003713
0x1800038d0  cmp     byte ptr [rcx+19h], 2
0x1800038d4  jb      loc_180003713
0x1800038da  mov     edx, 2Fh ; '/'
0x1800038df  jmp     loc_1800037A7
0x1800038e4  mov     edx, 10h; uBytes
0x1800038e9  mov     [rsp+38h+arg_0], r14
0x1800038ee  mov     ecx, 40h ; '@'; uFlags
0x1800038f3  call    cs:__imp_LocalAlloc
0x1800038f9  mov     r14, rax
0x1800038fc  test    rax, rax
0x1800038ff  jnz     short loc_180003946
0x180003901  mov     rcx, cs:WPP_GLOBAL_Control
0x180003908  lea     rax, WPP_GLOBAL_Control
0x18000390f  cmp     rcx, rax
0x180003912  jz      loc_18000383B
0x180003918  test    byte ptr [rcx+1Ch], 1
0x18000391c  jz      loc_18000383B
0x180003922  cmp     byte ptr [rcx+19h], 1
0x180003926  jb      loc_18000383B
0x18000392c  mov     rcx, [rcx+10h]
0x180003930  lea     r8, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids
0x180003937  mov     edx, 29h ; ')'
0x18000393c  call    WPP_SF_
0x180003941  jmp     loc_18000383B
0x180003946  xorps   xmm0, xmm0
0x180003949  movups  xmmword ptr [rax], xmm0
0x18000394c  cmp     ebx, 1
0x18000394f  jnz     loc_180003A52
0x180003955  lea     r8, [rsp+38h+pcchLength]; pcchLength
0x18000395a  mov     word ptr [rax], 2
0x18000395f  mov     edx, 7FFFFFFFh; cchMax
0x180003964  lea     rcx, [rdi+18h]; psz
0x180003968  call    StringCchLengthW
0x18000396d  test    eax, eax
0x18000396f  jns     short loc_1800039BB
0x180003971  mov     rcx, cs:WPP_GLOBAL_Control
0x180003978  lea     rax, WPP_GLOBAL_Control
0x18000397f  cmp     rcx, rax
0x180003982  jz      loc_180003827
0x180003988  test    [rcx+1Ch], bl
0x18000398b  jz      loc_180003827
0x180003991  cmp     [rcx+19h], bl
0x180003994  jb      loc_180003827
0x18000399a  mov     edx, 2Ah ; '*'
0x18000399f  jmp     short loc_1800039A6
0x1800039a1  mov     edx, 2Ch ; ','
0x1800039a6  mov     rcx, [rcx+10h]
0x1800039aa  lea     r8, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids
0x1800039b1  call    WPP_SF_
0x1800039b6  jmp     loc_180003827
0x1800039bb  mov     rbx, [rsp+38h+pcchLength]
0x1800039c0  mov     ecx, 40h ; '@'; uFlags
0x1800039c5  lea     rdx, ds:2[rbx*2]; uBytes
0x1800039cd  call    cs:__imp_LocalAlloc
0x1800039d3  mov     [r14+8], rax
0x1800039d7  test    rax, rax
0x1800039da  jnz     short loc_180003A0E
0x1800039dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039e3  lea     rax, WPP_GLOBAL_Control
0x1800039ea  cmp     rcx, rax
0x1800039ed  jz      loc_180003827
0x1800039f3  test    byte ptr [rcx+1Ch], 1
0x1800039f7  jz      loc_180003827
0x1800039fd  cmp     byte ptr [rcx+19h], 1
0x180003a01  jb      loc_180003827
0x180003a07  mov     edx, 2Bh ; '+'
0x180003a0c  jmp     short loc_1800039A6
0x180003a0e  lea     rdx, [rbx+1]; cchDest
0x180003a12  mov     rcx, rax; pszDest
0x180003a15  lea     r8, [rdi+18h]; pszSrc
0x180003a19  call    StringCchCopyW
0x180003a1e  test    eax, eax
0x180003a20  jns     short loc_180003A6C
0x180003a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a29  lea     rax, WPP_GLOBAL_Control
0x180003a30  cmp     rcx, rax
0x180003a33  jz      loc_180003827
0x180003a39  test    byte ptr [rcx+1Ch], 1
0x180003a3d  jz      loc_180003827
0x180003a43  cmp     byte ptr [rcx+19h], 1
0x180003a47  jb      loc_180003827
0x180003a4d  jmp     loc_1800039A1
0x180003a52  mov     word ptr [rax], 1
0x180003a57  mov     [rax+8], rsi
0x180003a5b  call    DiscoverDrives
0x180003a60  and     cs:AlreadyAddedBitMask, eax
0x180003a66  mov     cs:DiskConfiguration, eax
0x180003a6c  mov     dl, 1; Wait
0x180003a6e  lea     rcx, SsVolumeResource; Resource
0x180003a75  call    cs:__imp_RtlAcquireResourceExclusive
0x180003a7b  xor     r8d, r8d; pcbe
0x180003a7e  lea     rcx, SsDeferredUnregisterVolumeChange; pfns
0x180003a85  mov     rdx, r14; pv
0x180003a88  call    cs:__imp_TrySubmitThreadpoolCallback
0x180003a8e  test    eax, eax
0x180003a90  jnz     short loc_180003AD7
0x180003a92  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a99  lea     rax, WPP_GLOBAL_Control
0x180003aa0  cmp     rcx, rax
0x180003aa3  jz      loc_180003815
0x180003aa9  test    byte ptr [rcx+1Ch], 1
0x180003aad  jz      loc_180003815
0x180003ab3  cmp     byte ptr [rcx+19h], 1
0x180003ab7  jb      loc_180003815
0x180003abd  mov     rcx, [rcx+10h]
0x180003ac1  lea     r8, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids
0x180003ac8  mov     edx, 2Dh ; '-'
0x180003acd  call    WPP_SF_
0x180003ad2  jmp     loc_180003815
0x180003ad7  xor     r14d, r14d
0x180003ada  jmp     loc_180003815
0x180003adf  mov     rcx, [r14+8]; hMem
0x180003ae3  test    rcx, rcx
0x180003ae6  jz      loc_180003832
0x180003aec  call    cs:__imp_LocalFree
0x180003af2  jmp     loc_180003832
```
