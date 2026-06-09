# CWPDBus::IsValidWPDVolume(ushort const *)

- ea: `0x1800022c0`
- end: `0x1800027b1`
- name: `?IsValidWPDVolume@CWPDBus@@QEAAHPEBG@Z`
- size: `1265`
- prototype: `__int64 __fastcall(CWPDBus *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800018c0`
- `0x18000e260`

## callees

- `0x1800022c0`
- `0x180007f28`
- `0x1800097d0`
- `0x18000a192`
- `0x18000e080`
- `0x18000e53c`
- `0x18000e5d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000271f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000274e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000271f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000274e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002372`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002339`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002339`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800024a0`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800024a0`
- `ntdll!NtQueryVolumeInformationFile` at `0x180002367`
- `ntdll!NtQueryVolumeInformationFile` at `0x180002367`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180002544`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800025a8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180002544`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800025a8`

## pseudocode

```c
__int64 __fastcall CWPDBus::IsValidWPDVolume(CWPDBus *this, const unsigned __int16 *a2)
{
  unsigned int *v2; // r15
  unsigned int v4; // r14d
  HANDLE FileW; // rax
  void *v6; // rbx
  NTSTATUS v7; // edi
  CPnPNotification *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  WCHAR *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  const unsigned __int16 *v14; // r10
  WCHAR *v15; // rcx
  __int64 v16; // rdx
  WCHAR *v17; // rax
  __int64 v18; // rcx
  WCHAR *v19; // rax
  const wchar_t *v20; // rdx
  __int64 v21; // r8
  WCHAR *v22; // rcx
  UINT DriveTypeW; // eax
  UINT v24; // edi
  CPnPNotification *v25; // rcx
  __int64 v26; // rdx
  signed int LastError; // eax
  bool v28; // sf
  char v29; // al
  BYTE PropertyBuffer; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v32[3]; // [rsp+41h] [rbp-BFh] BYREF
  DEVPROPTYPE PropertyType; // [rsp+44h] [rbp-BCh] BYREF
  ULONG PropertyBufferSize; // [rsp+48h] [rbp-B8h] BYREF
  ULONG v35; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 FsInformation; // [rsp+50h] [rbp-B0h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR RootPathName[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = (unsigned int *)g_WPDBus;
  FsInformation = 0;
  v4 = 0;
  IoStatusBlock = 0;
  FileW = CreateFileW(a2, 0x80u, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v28 = LastError < 0;
    if ( LastError > 0 )
      v28 = 1;
    if ( v28
      && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v29 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids,
        (_DWORD)a2,
        v29);
    }
    return v4;
  }
  v7 = NtQueryVolumeInformationFile(FileW, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
  CloseHandle(v6);
  if ( v7 < 0 )
    return v4;
  if ( (_DWORD)FsInformation != 7 )
  {
    if ( (_DWORD)FsInformation == 2 )
    {
      if ( !*v2
        && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids, a2);
      }
      return *v2;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v9 = 26;
        goto LABEL_67;
      }
    }
    return v4;
  }
  if ( (FsInformation & 0x400000000LL) != 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v9 = 17;
LABEL_67:
      WPP_SF_S(*((_QWORD *)v8 + 2), v9, &WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids, a2);
      return v4;
    }
    return v4;
  }
  memset_0(RootPathName, 0, 0x20Au);
  v10 = 2147483646;
  v11 = RootPathName;
  v12 = 2147483646;
  v13 = 261;
  v14 = a2;
  do
  {
    if ( !v12 )
      break;
    if ( !*v14 )
      break;
    *v11++ = *v14++;
    --v12;
    --v13;
  }
  while ( v13 );
  v15 = v11 - 1;
  if ( v13 )
    v15 = v11;
  *v15 = 0;
  if ( v13 )
  {
    v16 = 261;
    v17 = RootPathName;
    do
    {
      if ( !*v17 )
        break;
      ++v17;
      --v16;
    }
    while ( v16 );
    v18 = 261 - v16;
    if ( v16 )
    {
      v19 = &RootPathName[v18];
      v20 = L"\\";
      v21 = 261 - v18;
      if ( 261 != v18 )
      {
        do
        {
          if ( !v10 )
            break;
          if ( !*v20 )
            break;
          *v19++ = *v20++;
          --v10;
          --v21;
        }
        while ( v21 );
      }
      v22 = v19 - 1;
      if ( v21 )
        v22 = v19;
      *v22 = 0;
      if ( v21 )
      {
        DriveTypeW = GetDriveTypeW(RootPathName);
        v24 = DriveTypeW;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            &WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids,
            DriveTypeW);
          v25 = WPP_GLOBAL_Control;
        }
        if ( v24 == 2 )
        {
          if ( v25 == (CPnPNotification *)&WPP_GLOBAL_Control || (*((_DWORD *)v25 + 7) & 0x100) == 0 )
            return (unsigned int)HasDriveLetter(RootPathName);
          v26 = 19;
LABEL_44:
          WPP_SF_S(*((_QWORD *)v25 + 2), v26, &WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids, a2);
          return (unsigned int)HasDriveLetter(RootPathName);
        }
      }
    }
  }
  PropertyType = 0;
  PropertyBuffer = 0;
  PropertyBufferSize = 1;
  if ( CM_Get_Device_Interface_PropertyW(
         a2,
         &DEVPKEY_Storage_Portable,
         &PropertyType,
         &PropertyBuffer,
         &PropertyBufferSize,
         0)
    || PropertyType != 17
    || PropertyBufferSize != 1 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v9 = 24;
      goto LABEL_67;
    }
    return v4;
  }
  if ( PropertyBuffer != 0xFF )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v9 = 23;
      goto LABEL_67;
    }
    return v4;
  }
  PropertyType = 0;
  v32[0] = 0;
  v35 = 1;
  if ( CM_Get_Device_Interface_PropertyW(a2, &DEVPKEY_Storage_System_Critical, &PropertyType, v32, &v35, 0)
    || PropertyType != 17
    || v35 != 1 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v9 = 22;
      goto LABEL_67;
    }
    return v4;
  }
  if ( !v32[0] )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      return (unsigned int)HasDriveLetter(RootPathName);
    }
    v26 = 20;
    goto LABEL_44;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    v9 = 21;
    goto LABEL_67;
  }
  return v4;
}

```

## disassembly

```asm
0x1800022c0  mov     [rsp-8+arg_0], rbx
0x1800022c5  mov     [rsp-8+arg_10], rsi
0x1800022ca  push    rbp
0x1800022cb  push    rdi
0x1800022cc  push    r12
0x1800022ce  push    r14
0x1800022d0  push    r15
0x1800022d2  lea     rbp, [rsp-190h]
0x1800022da  sub     rsp, 290h
0x1800022e1  mov     rax, cs:__security_cookie
0x1800022e8  xor     rax, rsp
0x1800022eb  mov     [rbp+1B0h+var_30], rax
0x1800022f2  mov     r15, cs:?g_WPDBus@@3PEAVCWPDBus@@EA; CWPDBus * g_WPDBus
0x1800022f9  mov     rsi, rdx
0x1800022fc  xor     r12d, r12d
0x1800022ff  mov     [rsp+2B0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x180002308  xorps   xmm0, xmm0
0x18000230b  mov     [rsp+2B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180002313  mov     rcx, rsi; lpFileName
0x180002316  mov     [rsp+2B0h+FsInformation], r12
0x18000231b  xor     r9d, r9d; lpSecurityAttributes
0x18000231e  mov     [rsp+2B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180002326  mov     edx, 80h; dwDesiredAccess
0x18000232b  mov     r8d, 3; dwShareMode
0x180002331  mov     r14d, r12d
0x180002334  movups  xmmword ptr [rsp+2B0h+IoStatusBlock], xmm0
0x180002339  call    cs:__imp_CreateFileW
0x18000233f  mov     rbx, rax
0x180002342  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002346  jz      loc_18000271F
0x18000234c  mov     r9d, 8; Length
0x180002352  mov     [rsp+2B0h+dwCreationDisposition], 4; FsInformationClass
0x18000235a  lea     r8, [rsp+2B0h+FsInformation]; FsInformation
0x18000235f  mov     rcx, rax; FileHandle
0x180002362  lea     rdx, [rsp+2B0h+IoStatusBlock]; IoStatusBlock
0x180002367  call    cs:__imp_NtQueryVolumeInformationFile
0x18000236d  mov     rcx, rbx; hObject
0x180002370  mov     edi, eax
0x180002372  call    cs:__imp_CloseHandle
0x180002378  test    edi, edi
0x18000237a  js      loc_180002783
0x180002380  mov     rax, [rsp+2B0h+FsInformation]
0x180002385  cmp     eax, 7
0x180002388  jnz     loc_18000269F
0x18000238e  mov     eax, dword ptr [rsp+2B0h+FsInformation+4]
0x180002392  test    al, 4
0x180002394  jz      short loc_1800023C4
0x180002396  mov     rcx, cs:WPP_GLOBAL_Control
0x18000239d  lea     rbx, WPP_GLOBAL_Control
0x1800023a4  cmp     rcx, rbx
0x1800023a7  jz      loc_180002783
0x1800023ad  test    dword ptr [rcx+1Ch], 100h
0x1800023b4  jz      loc_180002783
0x1800023ba  mov     edx, 11h
0x1800023bf  jmp     loc_18000270A
0x1800023c4  xor     edx, edx; Val
0x1800023c6  lea     rcx, [rsp+2B0h+RootPathName]; void *
0x1800023cb  mov     r8d, 20Ah; Size
0x1800023d1  call    memset_0
0x1800023d6  mov     r9d, 7FFFFFFEh
0x1800023dc  lea     rax, [rsp+2B0h+RootPathName]
0x1800023e1  mov     r8d, 105h
0x1800023e7  mov     ecx, r9d
0x1800023ea  mov     edx, r8d
0x1800023ed  mov     r10, rsi
0x1800023f0  test    rcx, rcx
0x1800023f3  jz      short loc_180002414
0x1800023f5  movzx   r11d, word ptr [r10]
0x1800023f9  test    r11w, r11w
0x1800023fd  jz      short loc_180002414
0x1800023ff  mov     [rax], r11w
0x180002403  add     r10, 2
0x180002407  add     rax, 2
0x18000240b  dec     rcx
0x18000240e  sub     rdx, 1
0x180002412  jnz     short loc_1800023F0
0x180002414  test    rdx, rdx
0x180002417  lea     rcx, [rax-2]
0x18000241b  cmovnz  rcx, rax
0x18000241f  mov     [rcx], r12w
0x180002423  jz      loc_180002508
0x180002429  mov     rdx, r8
0x18000242c  lea     rax, [rsp+2B0h+RootPathName]
0x180002431  cmp     [rax], r12w
0x180002435  jz      short loc_180002441
0x180002437  add     rax, 2
0x18000243b  sub     rdx, 1
0x18000243f  jnz     short loc_180002431
0x180002441  mov     rcx, r8
0x180002444  sub     rcx, rdx
0x180002447  test    rdx, rdx
0x18000244a  cmovz   rcx, r12
0x18000244e  jz      loc_180002508
0x180002454  lea     rax, [rsp+2B0h+RootPathName]
0x180002459  lea     rax, [rax+rcx*2]
0x18000245d  lea     rdx, asc_180017C30; "\\"
0x180002464  sub     r8, rcx
0x180002467  jz      short loc_18000248A
0x180002469  test    r9, r9
0x18000246c  jz      short loc_18000248A
0x18000246e  movzx   ecx, word ptr [rdx]
0x180002471  test    cx, cx
0x180002474  jz      short loc_18000248A
0x180002476  mov     [rax], cx
0x180002479  add     rdx, 2
0x18000247d  add     rax, 2
0x180002481  dec     r9
0x180002484  sub     r8, 1
0x180002488  jnz     short loc_180002469
0x18000248a  test    r8, r8
0x18000248d  lea     rcx, [rax-2]
0x180002491  cmovnz  rcx, rax
0x180002495  mov     [rcx], r12w
0x180002499  jz      short loc_180002508
0x18000249b  lea     rcx, [rsp+2B0h+RootPathName]; lpRootPathName
0x1800024a0  call    cs:__imp_GetDriveTypeW
0x1800024a6  mov     edi, eax
0x1800024a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024af  lea     rbx, WPP_GLOBAL_Control
0x1800024b6  cmp     rcx, rbx
0x1800024b9  jz      short loc_1800024E3
0x1800024bb  test    dword ptr [rcx+1Ch], 100h
0x1800024c2  jz      short loc_1800024E3
0x1800024c4  mov     rcx, [rcx+10h]
0x1800024c8  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x1800024cf  mov     edx, 12h
0x1800024d4  mov     r9d, eax
0x1800024d7  call    WPP_SF_d
0x1800024dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024e3  cmp     edi, 2
0x1800024e6  jnz     short loc_18000250F
0x1800024e8  cmp     rcx, rbx
0x1800024eb  jz      loc_1800025F4
0x1800024f1  test    dword ptr [rcx+1Ch], 100h
0x1800024f8  jz      loc_1800025F4
0x1800024fe  mov     edx, 13h
0x180002503  jmp     loc_1800025E1
0x180002508  lea     rbx, WPP_GLOBAL_Control
0x18000250f  lea     rax, [rsp+2B0h+PropertyBufferSize]
0x180002514  mov     [rsp+2B0h+dwFlagsAndAttributes], r12d; ulFlags
0x180002519  lea     r9, [rsp+2B0h+PropertyBuffer]; PropertyBuffer
0x18000251e  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax; PropertyBufferSize
0x180002523  lea     r8, [rsp+2B0h+PropertyType]; PropertyType
0x180002528  mov     [rsp+2B0h+PropertyType], r12d
0x18000252d  lea     rdx, DEVPKEY_Storage_Portable; PropertyKey
0x180002534  mov     [rsp+2B0h+PropertyBuffer], r12b
0x180002539  mov     rcx, rsi; pszDeviceInterface
0x18000253c  mov     [rsp+2B0h+PropertyBufferSize], 1
0x180002544  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x18000254a  test    eax, eax
0x18000254c  jnz     loc_18000267B
0x180002552  cmp     [rsp+2B0h+PropertyType], 11h
0x180002557  jnz     loc_18000267B
0x18000255d  cmp     [rsp+2B0h+PropertyBufferSize], 1
0x180002562  jnz     loc_18000267B
0x180002568  cmp     [rsp+2B0h+PropertyBuffer], 0FFh
0x18000256d  jnz     loc_180002654
0x180002573  lea     rax, [rsp+2B0h+var_264]
0x180002578  mov     [rsp+2B0h+dwFlagsAndAttributes], r12d; ulFlags
0x18000257d  lea     r9, [rsp+2B0h+var_26F]; PropertyBuffer
0x180002582  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax; PropertyBufferSize
0x180002587  lea     r8, [rsp+2B0h+PropertyType]; PropertyType
0x18000258c  mov     [rsp+2B0h+PropertyType], r12d
0x180002591  lea     rdx, DEVPKEY_Storage_System_Critical; PropertyKey
0x180002598  mov     [rsp+2B0h+var_26F], r12b
0x18000259d  mov     rcx, rsi; pszDeviceInterface
0x1800025a0  mov     [rsp+2B0h+var_264], 1
0x1800025a8  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1800025ae  test    eax, eax
0x1800025b0  jnz     short loc_18000262D
0x1800025b2  cmp     [rsp+2B0h+PropertyType], 11h
0x1800025b7  jnz     short loc_18000262D
0x1800025b9  cmp     [rsp+2B0h+var_264], 1
0x1800025be  jnz     short loc_18000262D
0x1800025c0  cmp     [rsp+2B0h+var_26F], r12b
0x1800025c5  jnz     short loc_180002606
0x1800025c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025ce  cmp     rcx, rbx
0x1800025d1  jz      short loc_1800025F4
0x1800025d3  test    dword ptr [rcx+1Ch], 100h
0x1800025da  jz      short loc_1800025F4
0x1800025dc  mov     edx, 14h
0x1800025e1  mov     rcx, [rcx+10h]
0x1800025e5  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x1800025ec  mov     r9, rsi
0x1800025ef  call    WPP_SF_S
0x1800025f4  lea     rcx, [rsp+2B0h+RootPathName]; lpszVolumeMountPoint
0x1800025f9  call    HasDriveLetter
0x1800025fe  mov     r14d, eax
0x180002601  jmp     loc_180002783
0x180002606  mov     rcx, cs:WPP_GLOBAL_Control
0x18000260d  cmp     rcx, rbx
0x180002610  jz      loc_180002783
0x180002616  test    dword ptr [rcx+1Ch], 100h
0x18000261d  jz      loc_180002783
0x180002623  mov     edx, 15h
0x180002628  jmp     loc_18000270A
0x18000262d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002634  cmp     rcx, rbx
0x180002637  jz      loc_180002783
0x18000263d  test    dword ptr [rcx+1Ch], 100h
0x180002644  jz      loc_180002783
0x18000264a  mov     edx, 16h
0x18000264f  jmp     loc_18000270A
0x180002654  mov     rcx, cs:WPP_GLOBAL_Control
0x18000265b  cmp     rcx, rbx
0x18000265e  jz      loc_180002783
0x180002664  test    dword ptr [rcx+1Ch], 100h
0x18000266b  jz      loc_180002783
0x180002671  mov     edx, 17h
0x180002676  jmp     loc_18000270A
0x18000267b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002682  cmp     rcx, rbx
0x180002685  jz      loc_180002783
0x18000268b  test    dword ptr [rcx+1Ch], 100h
0x180002692  jz      loc_180002783
0x180002698  mov     edx, 18h
0x18000269d  jmp     short loc_18000270A
0x18000269f  cmp     eax, 2
0x1800026a2  jnz     short loc_1800026E5
0x1800026a4  cmp     [r15], r12d
0x1800026a7  jnz     short loc_1800026DD
0x1800026a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026b0  lea     rbx, WPP_GLOBAL_Control
0x1800026b7  cmp     rcx, rbx
0x1800026ba  jz      short loc_1800026DD
0x1800026bc  test    dword ptr [rcx+1Ch], 100h
0x1800026c3  jz      short loc_1800026DD
0x1800026c5  mov     rcx, [rcx+10h]
0x1800026c9  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x1800026d0  mov     edx, 19h
0x1800026d5  mov     r9, rsi
0x1800026d8  call    WPP_SF_S
0x1800026dd  mov     r14d, [r15]
0x1800026e0  jmp     loc_180002783
0x1800026e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026ec  lea     rbx, WPP_GLOBAL_Control
0x1800026f3  cmp     rcx, rbx
0x1800026f6  jz      loc_180002783
0x1800026fc  test    dword ptr [rcx+1Ch], 100h
0x180002703  jz      short loc_180002783
0x180002705  mov     edx, 1Ah
0x18000270a  mov     rcx, [rcx+10h]
0x18000270e  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x180002715  mov     r9, rsi
0x180002718  call    WPP_SF_S
0x18000271d  jmp     short loc_180002783
0x18000271f  call    cs:__imp_GetLastError
0x180002725  test    eax, eax
0x180002727  jle     short loc_180002733
0x180002729  movzx   eax, ax
0x18000272c  or      eax, 80070000h
0x180002731  test    eax, eax
0x180002733  jns     short loc_180002783
0x180002735  mov     rax, cs:WPP_GLOBAL_Control
0x18000273c  lea     rbx, WPP_GLOBAL_Control
0x180002743  cmp     rax, rbx
0x180002746  jz      short loc_180002783
0x180002748  test    byte ptr [rax+1Ch], 4
0x18000274c  jz      short loc_180002783
0x18000274e  call    cs:__imp_GetLastError
0x180002754  test    eax, eax
0x180002756  jle     short loc_180002760
0x180002758  movzx   eax, ax
0x18000275b  or      eax, 80070000h
0x180002760  mov     rcx, cs:WPP_GLOBAL_Control
0x180002767  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x18000276e  mov     edx, 1Bh
0x180002773  mov     [rsp+2B0h+dwCreationDisposition], eax
0x180002777  mov     r9, rsi
0x18000277a  mov     rcx, [rcx+10h]
0x18000277e  call    WPP_SF_Sd
0x180002783  mov     eax, r14d
0x180002786  mov     rcx, [rbp+1B0h+var_30]
0x18000278d  xor     rcx, rsp; StackCookie
0x180002790  call    __security_check_cookie
0x180002795  lea     r11, [rsp+2B0h+var_20]
0x18000279d  mov     rbx, [r11+30h]
0x1800027a1  mov     rsi, [r11+40h]
0x1800027a5  mov     rsp, r11
0x1800027a8  pop     r15
0x1800027aa  pop     r14
0x1800027ac  pop     r12
0x1800027ae  pop     rdi
0x1800027af  pop     rbp
0x1800027b0  retn
```
