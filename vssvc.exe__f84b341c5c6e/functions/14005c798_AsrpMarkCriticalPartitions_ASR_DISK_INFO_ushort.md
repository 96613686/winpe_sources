# AsrpMarkCriticalPartitions(_ASR_DISK_INFO *,ushort * *)

- ea: `0x14005c798`
- end: `0x14005cd41`
- name: `?AsrpMarkCriticalPartitions@@YAHPEAU_ASR_DISK_INFO@@PEAPEAG@Z`
- size: `1449`
- prototype: `__int64 __fastcall(struct _ASR_DISK_INFO *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400768c4`

## callees

- `0x140021ca0`
- `0x140021f14`
- `0x1400235a8`
- `0x14003b0c0`
- `0x14005a294`
- `0x14005ab34`
- `0x14005c798`
- `0x1400d257c`
- `0x1400d26c8`
- `0x1400d6f4c`
- `0x1400d7878`
- `0x1400d7a34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005c8cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005c8cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c9a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005caf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cb17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cb31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cb53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cc43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cc5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c9a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005caf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cb17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cb31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cb53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cc43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cc5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005c89d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005c8a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005c8af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005c8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005cadb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005cb7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005cca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005c89d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005c8a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005c8af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005c8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005cadb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005cb7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005cca2`

## pseudocode

```c
__int64 __fastcall AsrpMarkCriticalPartitions(struct _STORAGE_DEPENDENCY_INFO *a1, unsigned __int16 **a2)
{
  unsigned __int16 **v2; // r12
  struct _STORAGE_DEPENDENCY_INFO *v3; // r13
  int v4; // r8d
  unsigned __int16 *v5; // rsi
  unsigned __int16 *i; // rbx
  __int64 v7; // rax
  unsigned int v8; // r14d
  DWORD LastError; // ebx
  DWORD v10; // eax
  void *v11; // rdi
  unsigned __int16 *v13; // rax
  unsigned __int16 *j; // r15
  struct _STORAGE_DEPENDENCY_INFO *v15; // rbx
  unsigned int k; // esi
  PWSTR DependencyDeviceName; // r13
  char v18; // al
  __int64 v19; // rax
  struct _ASR_VIRTUAL_DISK_INFO *v20; // rdx
  unsigned int m; // ebx
  __int64 v22; // rsi
  LPVOID v23; // rcx
  unsigned __int16 *n; // rbx
  __int64 v25; // rax
  DWORD v26; // eax
  DWORD v27; // eax
  unsigned __int16 *v28; // rbx
  void *v29; // rcx
  int DeviceDependencyInformation; // eax
  char v31; // al
  __int64 v32; // rax
  DWORD v33; // eax
  struct _ASR_VIRTUAL_DISK_INFO *v34; // [rsp+30h] [rbp-28h] BYREF
  LPVOID v35; // [rsp+38h] [rbp-20h]
  LPVOID pv; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 *v37; // [rsp+48h] [rbp-10h] BYREF
  struct _STORAGE_DEPENDENCY_INFO *v38; // [rsp+A0h] [rbp+48h] BYREF
  unsigned __int16 **v39; // [rsp+A8h] [rbp+50h]
  LPVOID v40; // [rsp+B0h] [rbp+58h]
  unsigned __int16 *v41; // [rsp+B8h] [rbp+60h] BYREF

  v39 = a2;
  v38 = a1;
  v2 = a2;
  v3 = a1;
  TraceFunctionEnter(L"AsrpMarkCriticalPartitions");
  v41 = 0;
  v40 = 0;
  v5 = 0;
  v37 = 0;
  pv = 0;
  v35 = 0;
  v34 = 0;
  if ( !v3 )
  {
    v8 = 0;
    LastError = 87;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        100,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        87,
        "pDiskList");
    }
    goto LABEL_13;
  }
  if ( !v2 )
  {
    v8 = 0;
    LastError = 87;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        101,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        87,
        "ppmwszCriticalVolumeList");
    }
    goto LABEL_13;
  }
  for ( i = *v2; *i; i += v7 + 1 )
  {
    if ( !MwszStringAppend(&v41, i) )
    {
      v8 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v10 = GetLastError();
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          102,
          (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
          v10,
          "MwszStringAppend( &mwszCurrentCriticalVolList, pwszCurVolume )");
      }
      goto LABEL_12;
    }
    v7 = -1;
    do
      ++v7;
    while ( i[v7] );
  }
  v13 = v41;
  v8 = 1;
LABEL_16:
  v41 = v13;
  if ( v13 && *v13 )
  {
    for ( j = v13; *j; j += v19 + 1 )
    {
      v15 = v3;
      do
      {
        for ( k = 0; k < *(_DWORD *)(*(_QWORD *)&v15->Version2Entries[0].VirtualStorageType.DeviceId + 4LL); ++k )
        {
          DependencyDeviceName = v15->Version2Entries[0].DependencyDeviceName;
          if ( (unsigned int)MwszStringExist(*(unsigned __int16 **)&DependencyDeviceName[12 * k], j, v4)
            || DependencyDeviceName[12 * k + 6] )
          {
            *(_DWORD *)&DependencyDeviceName[12 * k + 8] = 1;
          }
        }
        v15 = *(struct _STORAGE_DEPENDENCY_INFO **)&v15->Version;
      }
      while ( v15 );
      AsrFreeVirtualDiskInfo(&v34);
      if ( (unsigned int)AsrVhd::DiskBuildVhdInfo(j, 0, &v34) )
      {
        v20 = v34;
        if ( v34 )
        {
          for ( m = 0; m < *((_DWORD *)v20 + 2); ++m )
          {
            if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
            {
              WPP_SF_SSS(
                *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
                *(_QWORD *)v20,
                32 * m,
                (_DWORD)j,
                *(_QWORD *)(32LL * m + *(_QWORD *)v20),
                *(_QWORD *)(32LL * m + *(_QWORD *)v20 + 8));
              v20 = v34;
            }
            v22 = 32LL * m;
            if ( !(unsigned int)MwszStringExist(
                                  (unsigned __int16 *)pv,
                                  *(unsigned __int16 **)(v22 + *(_QWORD *)v20),
                                  v4)
              && !(unsigned int)MwszStringExist(*v39, *(unsigned __int16 **)(v22 + *(_QWORD *)v34), v4)
              && !MwszStringAppend((unsigned __int16 **)&pv, *(unsigned __int16 **)(v22 + *(_QWORD *)v34)) )
            {
              v8 = 0;
              LastError = GetLastError();
              if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
              {
                v26 = GetLastError();
                WPP_SF_Ds(
                  *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
                  105,
                  (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
                  v26,
                  "MwszStringAppend( &mwszMoreCriticalVolList, pVirtualDiskInfo->m_rgVhdFileInfo[iVhd].m_wszVolumeUniqueName )");
              }
              goto LABEL_12;
            }
            v20 = v34;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
             && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x400000000LL) != 0 )
      {
        v18 = GetLastError();
        WPP_SF_SD(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          103,
          (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
          (_DWORD)j,
          v18);
      }
      v19 = -1;
      do
        ++v19;
      while ( j[v19] );
      v3 = v38;
    }
    v23 = pv;
    v2 = v39;
    for ( n = (unsigned __int16 *)pv; ; n += v25 + 1 )
    {
      if ( !v23 || !*n )
      {
        CoTaskMemFree(v41);
        v13 = (unsigned __int16 *)pv;
        pv = 0;
        goto LABEL_16;
      }
      if ( !MwszStringAppend(v2, n) )
        break;
      v25 = -1;
      do
        ++v25;
      while ( n[v25] );
      v23 = pv;
    }
    v8 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v27 = GetLastError();
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        106,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        v27,
        "MwszStringAppend( ppmwszCriticalVolumeList, pwszCurVolume )");
    }
LABEL_12:
    v5 = v41;
LABEL_13:
    v11 = v40;
    goto LABEL_14;
  }
  v28 = *v2;
  v29 = v35;
  while ( 1 )
  {
    if ( !*v28 )
    {
      LastError = 0;
      CoTaskMemFree(*v2);
      v11 = 0;
      *v2 = v37;
      goto LABEL_77;
    }
    CoTaskMemFree(v29);
    v38 = 0;
    DeviceDependencyInformation = AsrVhd::GetDeviceDependencyInformation(
                                    v28,
                                    1u,
                                    STORAGE_DEPENDENCY_INFO_VERSION_1,
                                    &v38);
    v29 = v38;
    v35 = v38;
    if ( DeviceDependencyInformation )
      break;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x400000000LL) != 0 )
    {
      v31 = GetLastError();
      WPP_SF_SD(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        107,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        (_DWORD)v28,
        v31);
      goto LABEL_69;
    }
LABEL_70:
    v32 = -1;
    do
      ++v32;
    while ( v28[v32] );
    v28 += v32 + 1;
  }
  if ( v38 )
  {
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
    {
      WPP_SF_S(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        108,
        WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        v28);
    }
    goto LABEL_69;
  }
  if ( MwszStringAppend(&v37, v28) )
  {
LABEL_69:
    v29 = v35;
    goto LABEL_70;
  }
  v8 = 0;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    v33 = GetLastError();
    WPP_SF_Ds(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      109,
      (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
      v33,
      "MwszStringAppend( &mwszFinalCriticalVolList, pwszCurVolume )");
  }
  v11 = v37;
LABEL_77:
  v5 = v41;
LABEL_14:
  AsrFreeVirtualDiskInfo(&v34);
  CoTaskMemFree(pv);
  CoTaskMemFree(v5);
  CoTaskMemFree(v11);
  CoTaskMemFree(v35);
  TraceFunctionExit(L"AsrpMarkCriticalPartitions");
  SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x14005c798  mov     [rsp-40h+arg_8], rdx
0x14005c79d  mov     [rsp-40h+arg_0], rcx
0x14005c7a2  push    rbp
0x14005c7a3  push    rbx
0x14005c7a4  push    rsi
0x14005c7a5  push    rdi
0x14005c7a6  push    r12
0x14005c7a8  push    r13
0x14005c7aa  push    r14
0x14005c7ac  push    r15
0x14005c7ae  mov     rbp, rsp
0x14005c7b1  sub     rsp, 58h
0x14005c7b5  mov     r12, rdx
0x14005c7b8  mov     r13, rcx
0x14005c7bb  lea     rcx, aAsrpmarkcritic_1; "AsrpMarkCriticalPartitions"
0x14005c7c2  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x14005c7c7  xor     r15d, r15d
0x14005c7ca  mov     [rbp+arg_18], r15
0x14005c7ce  mov     eax, r15d
0x14005c7d1  mov     [rbp+arg_10], rax
0x14005c7d5  mov     esi, r15d
0x14005c7d8  mov     [rbp+var_10], rax
0x14005c7dc  mov     [rbp+pv], r15
0x14005c7e0  mov     [rbp+var_20], r15
0x14005c7e4  mov     [rbp+var_28], r15
0x14005c7e8  test    r13, r13
0x14005c7eb  jz      loc_14005CD07
0x14005c7f1  test    r12, r12
0x14005c7f4  jz      loc_14005CCB5
0x14005c7fa  mov     rbx, [r12]
0x14005c7fe  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14005c802  cmp     [rbx], r15w
0x14005c806  jz      loc_14005C8E7
0x14005c80c  mov     rdx, rbx; unsigned __int16 *
0x14005c80f  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x14005c813  call    ?MwszStringAppend@@YAHPEAPEAGPEAG@Z; MwszStringAppend(ushort * *,ushort *)
0x14005c818  test    eax, eax
0x14005c81a  jz      short loc_14005C833
0x14005c81c  mov     rax, rsi
0x14005c81f  inc     rax
0x14005c822  cmp     [rbx+rax*2], r15w
0x14005c827  jnz     short loc_14005C81F
0x14005c829  lea     rbx, [rbx+rax*2]
0x14005c82d  add     rbx, 2
0x14005c831  jmp     short loc_14005C802
0x14005c833  mov     r14d, r15d
0x14005c836  call    cs:__imp_GetLastError
0x14005c83c  mov     ebx, eax
0x14005c83e  mov     rax, cs:WPP_GLOBAL_Control
0x14005c845  lea     rdi, WPP_GLOBAL_Control
0x14005c84c  cmp     rax, rdi
0x14005c84f  jz      short loc_14005C888
0x14005c851  test    byte ptr [rax+1Ch], 8
0x14005c855  jz      short loc_14005C888
0x14005c857  call    cs:__imp_GetLastError
0x14005c85d  mov     edx, 66h ; 'f'
0x14005c862  lea     rcx, aMwszstringappe_4; "MwszStringAppend( &mwszCurrentCriticalV"...
0x14005c869  mov     [rsp+58h+var_38], rcx
0x14005c86e  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x14005c875  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c87c  mov     r9d, eax
0x14005c87f  mov     rcx, [rcx+10h]
0x14005c883  call    WPP_SF_Ds
0x14005c888  mov     rsi, [rbp+arg_18]
0x14005c88c  mov     rdi, [rbp+arg_10]
0x14005c890  lea     rcx, [rbp+var_28]; struct _ASR_VIRTUAL_DISK_INFO **
0x14005c894  call    ?AsrFreeVirtualDiskInfo@@YAXPEAPEAU_ASR_VIRTUAL_DISK_INFO@@@Z; AsrFreeVirtualDiskInfo(_ASR_VIRTUAL_DISK_INFO * *)
0x14005c899  mov     rcx, [rbp+pv]; pv
0x14005c89d  call    cs:__imp_CoTaskMemFree
0x14005c8a3  mov     rcx, rsi; pv
0x14005c8a6  call    cs:__imp_CoTaskMemFree
0x14005c8ac  mov     rcx, rdi; pv
0x14005c8af  call    cs:__imp_CoTaskMemFree
0x14005c8b5  mov     rcx, [rbp+var_20]; pv
0x14005c8b9  call    cs:__imp_CoTaskMemFree
0x14005c8bf  lea     rcx, aAsrpmarkcritic_1; "AsrpMarkCriticalPartitions"
0x14005c8c6  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x14005c8cb  mov     ecx, ebx; dwErrCode
0x14005c8cd  call    cs:__imp_SetLastError
0x14005c8d3  mov     eax, r14d
0x14005c8d6  add     rsp, 58h
0x14005c8da  pop     r15
0x14005c8dc  pop     r14
0x14005c8de  pop     r13
0x14005c8e0  pop     r12
0x14005c8e2  pop     rdi
0x14005c8e3  pop     rsi
0x14005c8e4  pop     rbx
0x14005c8e5  pop     rbp
0x14005c8e6  retn
0x14005c8e7  mov     rax, [rbp+arg_18]
0x14005c8eb  lea     rdi, WPP_GLOBAL_Control
0x14005c8f2  mov     r14d, 1
0x14005c8f8  mov     [rbp+arg_18], rax
0x14005c8fc  test    rax, rax
0x14005c8ff  jz      loc_14005CB6A
0x14005c905  cmp     [rax], r15w
0x14005c909  jz      loc_14005CB6A
0x14005c90f  mov     r15, rax
0x14005c912  xor     r12d, r12d
0x14005c915  cmp     [r15], r12w
0x14005c919  jz      loc_14005CA94
0x14005c91f  mov     rbx, r13
0x14005c922  xor     edi, edi
0x14005c924  mov     rax, [rbx+10h]
0x14005c928  mov     esi, edi
0x14005c92a  cmp     [rax+4], edi
0x14005c92d  jbe     short loc_14005C963
0x14005c92f  mov     r13, [rbx+28h]
0x14005c933  mov     rdx, r15; unsigned __int16 *
0x14005c936  mov     eax, esi
0x14005c938  lea     r12, [rax+rax*2]
0x14005c93c  mov     rcx, [r13+r12*8+0]; unsigned __int16 *
0x14005c941  call    ?MwszStringExist@@YAHPEAG0H@Z; MwszStringExist(ushort *,ushort *,int)
0x14005c946  test    eax, eax
0x14005c948  jnz     short loc_14005C952
0x14005c94a  cmp     [r13+r12*8+0Ch], di
0x14005c950  jz      short loc_14005C957
0x14005c952  mov     [r13+r12*8+10h], r14d
0x14005c957  mov     rax, [rbx+10h]
0x14005c95b  add     esi, r14d
0x14005c95e  cmp     esi, [rax+4]
0x14005c961  jb      short loc_14005C92F
0x14005c963  mov     rbx, [rbx]
0x14005c966  test    rbx, rbx
0x14005c969  jnz     short loc_14005C924
0x14005c96b  lea     rcx, [rbp+var_28]; struct _ASR_VIRTUAL_DISK_INFO **
0x14005c96f  lea     rdi, WPP_GLOBAL_Control
0x14005c976  call    ?AsrFreeVirtualDiskInfo@@YAXPEAPEAU_ASR_VIRTUAL_DISK_INFO@@@Z; AsrFreeVirtualDiskInfo(_ASR_VIRTUAL_DISK_INFO * *)
0x14005c97b  lea     r8, [rbp+var_28]; struct _ASR_VIRTUAL_DISK_INFO **
0x14005c97f  xor     edx, edx; unsigned int
0x14005c981  mov     rcx, r15; unsigned __int16 *
0x14005c984  call    ?DiskBuildVhdInfo@AsrVhd@@SAHPEBGKPEAPEAU_ASR_VIRTUAL_DISK_INFO@@@Z; AsrVhd::DiskBuildVhdInfo(ushort const *,ulong,_ASR_VIRTUAL_DISK_INFO * *)
0x14005c989  xor     r12d, r12d
0x14005c98c  test    eax, eax
0x14005c98e  jnz     short loc_14005C9EB
0x14005c990  mov     rax, cs:WPP_GLOBAL_Control
0x14005c997  cmp     rax, rdi
0x14005c99a  jz      short loc_14005C9C9
0x14005c99c  test    byte ptr [rax+1Ch], 4
0x14005c9a0  jz      short loc_14005C9C9
0x14005c9a2  call    cs:__imp_GetLastError
0x14005c9a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c9af  lea     edx, [rbx+67h]
0x14005c9b2  mov     r9, r15
0x14005c9b5  mov     dword ptr [rsp+58h+var_38], eax
0x14005c9b9  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x14005c9c0  mov     rcx, [rcx+10h]
0x14005c9c4  call    WPP_SF_SD
0x14005c9c9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14005c9cd  mov     rax, rsi
0x14005c9d0  inc     rax
0x14005c9d3  cmp     [r15+rax*2], r12w
0x14005c9d8  jnz     short loc_14005C9D0
0x14005c9da  mov     r13, [rbp+arg_0]
0x14005c9de  lea     r15, [r15+rax*2]
0x14005c9e2  add     r15, 2
0x14005c9e6  jmp     loc_14005C915
0x14005c9eb  mov     rdx, [rbp+var_28]
0x14005c9ef  test    rdx, rdx
0x14005c9f2  jz      short loc_14005C9C9
0x14005c9f4  mov     ebx, r12d
0x14005c9f7  cmp     ebx, [rdx+8]
0x14005c9fa  jnb     short loc_14005C9C9
0x14005c9fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ca03  cmp     rcx, rdi
0x14005ca06  jz      short loc_14005CA3B
0x14005ca08  test    byte ptr [rcx+1Ch], 2
0x14005ca0c  jz      short loc_14005CA3B
0x14005ca0e  mov     rdx, [rdx]
0x14005ca11  mov     r9, r15
0x14005ca14  mov     rcx, [rcx+10h]
0x14005ca18  mov     r8d, ebx
0x14005ca1b  shl     r8, 5
0x14005ca1f  mov     rax, [r8+rdx+8]
0x14005ca24  mov     [rsp+58h+var_30], rax
0x14005ca29  mov     rax, [r8+rdx]
0x14005ca2d  mov     [rsp+58h+var_38], rax
0x14005ca32  call    WPP_SF_SSS
0x14005ca37  mov     rdx, [rbp+var_28]
0x14005ca3b  mov     rdx, [rdx]
0x14005ca3e  mov     rcx, [rbp+pv]; unsigned __int16 *
0x14005ca42  mov     esi, ebx
0x14005ca44  shl     rsi, 5
0x14005ca48  mov     rdx, [rsi+rdx]; unsigned __int16 *
0x14005ca4c  call    ?MwszStringExist@@YAHPEAG0H@Z; MwszStringExist(ushort *,ushort *,int)
0x14005ca51  test    eax, eax
0x14005ca53  jnz     short loc_14005CA88
0x14005ca55  mov     rax, [rbp+var_28]
0x14005ca59  mov     rdx, [rax]
0x14005ca5c  mov     rax, [rbp+arg_8]
0x14005ca60  mov     rdx, [rsi+rdx]; unsigned __int16 *
0x14005ca64  mov     rcx, [rax]; unsigned __int16 *
0x14005ca67  call    ?MwszStringExist@@YAHPEAG0H@Z; MwszStringExist(ushort *,ushort *,int)
0x14005ca6c  test    eax, eax
0x14005ca6e  jnz     short loc_14005CA88
0x14005ca70  mov     rax, [rbp+var_28]
0x14005ca74  lea     rcx, [rbp+pv]; unsigned __int16 **
0x14005ca78  mov     rdx, [rax]
0x14005ca7b  mov     rdx, [rsi+rdx]; unsigned __int16 *
0x14005ca7f  call    ?MwszStringAppend@@YAHPEAPEAGPEAG@Z; MwszStringAppend(ushort * *,ushort *)
0x14005ca84  test    eax, eax
0x14005ca86  jz      short loc_14005CAF2
0x14005ca88  mov     rdx, [rbp+var_28]
0x14005ca8c  add     ebx, r14d
0x14005ca8f  jmp     loc_14005C9F7
0x14005ca94  mov     rcx, [rbp+pv]
0x14005ca98  xor     r15d, r15d
0x14005ca9b  mov     r12, [rbp+arg_8]
0x14005ca9f  mov     rbx, rcx
0x14005caa2  test    rcx, rcx
0x14005caa5  jz      short loc_14005CAD7
0x14005caa7  cmp     [rbx], r15w
0x14005caab  jz      short loc_14005CAD7
0x14005caad  mov     rdx, rbx; unsigned __int16 *
0x14005cab0  mov     rcx, r12; unsigned __int16 **
0x14005cab3  call    ?MwszStringAppend@@YAHPEAPEAGPEAG@Z; MwszStringAppend(ushort * *,ushort *)
0x14005cab8  test    eax, eax
0x14005caba  jz      short loc_14005CB2E
0x14005cabc  mov     rax, rsi
0x14005cabf  inc     rax
0x14005cac2  cmp     [rbx+rax*2], r15w
0x14005cac7  jnz     short loc_14005CABF
0x14005cac9  mov     rcx, [rbp+pv]
0x14005cacd  lea     rbx, [rbx+rax*2]
0x14005cad1  add     rbx, 2
0x14005cad5  jmp     short loc_14005CAA2
0x14005cad7  mov     rcx, [rbp+arg_18]; pv
0x14005cadb  call    cs:__imp_CoTaskMemFree
0x14005cae1  mov     rax, [rbp+pv]
0x14005cae5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14005cae9  mov     [rbp+pv], r15
0x14005caed  jmp     loc_14005C8F8
0x14005caf2  mov     r14d, r12d
0x14005caf5  call    cs:__imp_GetLastError
0x14005cafb  mov     ebx, eax
0x14005cafd  mov     rax, cs:WPP_GLOBAL_Control
0x14005cb04  cmp     rax, rdi
0x14005cb07  jz      loc_14005C888
0x14005cb0d  test    byte ptr [rax+1Ch], 8
0x14005cb11  jz      loc_14005C888
0x14005cb17  call    cs:__imp_GetLastError
0x14005cb1d  mov     edx, 69h ; 'i'
0x14005cb22  lea     rcx, aMwszstringappe_1; "MwszStringAppend( &mwszMoreCriticalVolL"...
0x14005cb29  jmp     loc_14005C869
0x14005cb2e  mov     r14d, r15d
0x14005cb31  call    cs:__imp_GetLastError
0x14005cb37  mov     ebx, eax
0x14005cb39  mov     rax, cs:WPP_GLOBAL_Control
0x14005cb40  cmp     rax, rdi
0x14005cb43  jz      loc_14005C888
0x14005cb49  test    byte ptr [rax+1Ch], 8
0x14005cb4d  jz      loc_14005C888
0x14005cb53  call    cs:__imp_GetLastError
0x14005cb59  mov     edx, 6Ah ; 'j'
0x14005cb5e  lea     rcx, aMwszstringappe_6; "MwszStringAppend( ppmwszCriticalVolumeL"...
0x14005cb65  jmp     loc_14005C869
0x14005cb6a  mov     rbx, [r12]
0x14005cb6e  mov     rcx, [rbp+var_20]; pv
0x14005cb72  cmp     [rbx], r15w
0x14005cb76  jz      loc_14005CC9B
0x14005cb7c  call    cs:__imp_CoTaskMemFree
0x14005cb82  lea     r9, [rbp+arg_0]; struct _STORAGE_DEPENDENCY_INFO **
0x14005cb86  mov     [rbp+arg_0], r15
0x14005cb8a  mov     r8d, r14d; enum _STORAGE_DEPENDENCY_INFO_VERSION
0x14005cb8d  mov     dl, r14b; unsigned __int8
0x14005cb90  mov     rcx, rbx; lpFileName
0x14005cb93  call    ?GetDeviceDependencyInformation@AsrVhd@@SAHPEBGEW4_STORAGE_DEPENDENCY_INFO_VERSION@@PEAPEAU_STORAGE_DEPENDENCY_INFO@@@Z; AsrVhd::GetDeviceDependencyInformation(ushort const *,uchar,_STORAGE_DEPENDENCY_INFO_VERSION,_STORAGE_DEPENDENCY_INFO * *)
0x14005cb98  mov     rcx, [rbp+arg_0]
0x14005cb9c  mov     [rbp+var_20], rcx
0x14005cba0  test    eax, eax
0x14005cba2  jnz     short loc_14005CBE1
0x14005cba4  mov     rax, cs:WPP_GLOBAL_Control
0x14005cbab  cmp     rax, rdi
0x14005cbae  jz      short loc_14005CC26
0x14005cbb0  test    byte ptr [rax+1Ch], 4
0x14005cbb4  jz      short loc_14005CC26
0x14005cbb6  call    cs:__imp_GetLastError
0x14005cbbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cbc3  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x14005cbca  mov     edx, 6Bh ; 'k'
0x14005cbcf  mov     dword ptr [rsp+58h+var_38], eax
0x14005cbd3  mov     r9, rbx
0x14005cbd6  mov     rcx, [rcx+10h]
0x14005cbda  call    WPP_SF_SD
0x14005cbdf  jmp     short loc_14005CC22
0x14005cbe1  test    rcx, rcx
0x14005cbe4  jz      short loc_14005CC12
0x14005cbe6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cbed  cmp     rcx, rdi
0x14005cbf0  jz      short loc_14005CC22
0x14005cbf2  test    byte ptr [rcx+1Ch], 2
0x14005cbf6  jz      short loc_14005CC22
0x14005cbf8  mov     rcx, [rcx+10h]
0x14005cbfc  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x14005cc03  mov     edx, 6Ch ; 'l'
0x14005cc08  mov     r9, rbx
0x14005cc0b  call    WPP_SF_S
0x14005cc10  jmp     short loc_14005CC22
0x14005cc12  mov     rdx, rbx; unsigned __int16 *
  ... truncated ...
```
