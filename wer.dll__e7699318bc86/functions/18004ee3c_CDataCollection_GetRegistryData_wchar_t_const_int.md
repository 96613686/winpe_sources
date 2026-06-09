# CDataCollection::GetRegistryData(wchar_t const *,int)

- ea: `0x18004ee3c`
- end: `0x18004f33e`
- name: `?GetRegistryData@CDataCollection@@QEAAJPEB_WH@Z`
- size: `1282`
- prototype: `int(CDataCollection *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800429c0`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x1800072cc`
- `0x180007e10`
- `0x180007e34`
- `0x18000c390`
- `0x180013730`
- `0x180014720`
- `0x1800179fc`
- `0x18001b678`
- `0x18001bbc4`
- `0x18001fe24`
- `0x18004ee3c`
- `0x180050db0`
- `0x18008af84`
- `0x18008b024`
- `0x18008b0dc`
- `0x18008d0f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f296`
- `ntdll!wcschr` at `0x18004f058`
- `ntdll!wcschr` at `0x18004f058`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004f073`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004f073`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f043`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f043`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004ef4e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004f1dc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004ef4e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004f1dc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004f2cf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004f2cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004efc0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004efc0`

## string_xrefs

- `0x18004f203`: `registry.txt`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDataCollection::GetRegistryData(CDataCollection *this, const wchar_t *a2, unsigned int a3)
{
  WCHAR **v5; // r14
  const WCHAR *v6; // rcx
  int TempFile; // eax
  int RegKeyData; // edi
  char *v9; // rbx
  HANDLE FileW; // rax
  int v11; // eax
  wchar_t *v12; // r15
  BOOL v13; // r15d
  __int64 v14; // rax
  unsigned int v15; // r13d
  int v16; // eax
  DWORD LastError; // eax
  WCHAR *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // rax
  HANDLE hFile; // [rsp+40h] [rbp-C0h] BYREF
  __int16 Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v26; // [rsp+50h] [rbp-B0h]
  DWORD v27; // [rsp+54h] [rbp-ACh] BYREF
  const wchar_t *v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h]
  _QWORD v30[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v31[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v32; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v33[24]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR FileName[264]; // [rsp+C0h] [rbp-40h] BYREF

  v26 = a3;
  hFile = 0;
  NumberOfBytesWritten = 0;
  Buffer[0] = -257;
  utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v30);
  v27 = 0;
  v31[0] = asc_1800B57E0;
  v31[1] = 7;
  FileName[0] = 0;
  v5 = (WCHAR **)((char *)this + 24);
  v6 = (const WCHAR *)*((_QWORD *)this + 3);
  if ( v6 == *((const WCHAR **)this + 4) )
  {
    TempFile = UtilGetTempFile(&hFile, 0, L".reg.txt", FileName);
    RegKeyData = TempFile;
    if ( TempFile < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          (unsigned int)TempFile);
      v9 = (char *)hFile;
      goto LABEL_49;
    }
    v9 = (char *)hFile;
    if ( WriteFile(hFile, Buffer, 2u, &NumberOfBytesWritten, 0) )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((char *)this + 24);
      goto LABEL_18;
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
LABEL_48:
    LastError = GetLastError();
    RegKeyData = ERROR_HR_FROM_WIN32(LastError);
    goto LABEL_49;
  }
  FileW = CreateFileW(v6, 0x40000000u, 1u, 0, 3u, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  v9 = (char *)hFile;
  if ( (unsigned __int64)hFile + 1 <= 1 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    goto LABEL_48;
  }
  v11 = UtilVerifyFilePath(*v5, hFile);
  RegKeyData = v11;
  if ( v11 >= 0 )
  {
    SetFilePointer(v9, 0, 0, 2u);
LABEL_18:
    while ( 1 )
    {
      v12 = wcschr(a2, 0x3Bu);
      if ( !v12 )
        break;
      if ( !WaitForSingleObject(*((HANDLE *)this + 2), 0) )
      {
        RegKeyData = -2145681407;
        goto LABEL_49;
      }
      v28 = a2;
      v29 = v12 - a2;
      v32 = *(_OWORD *)tlx::trim_view<wchar_t,utl::char_traits<wchar_t>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,0>(
                         v33,
                         &v28,
                         v31);
      if ( !(unsigned __int8)utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
                               v30,
                               &v32) )
      {
        RegKeyData = -2147024882;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
            2147942414LL);
      }
      a2 = v12 + 1;
    }
    v13 = 0;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v28 = a2;
    v29 = (2 * v14) >> 1;
    v32 = *(_OWORD *)tlx::trim_view<wchar_t,utl::char_traits<wchar_t>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,0>(
                       v33,
                       &v28,
                       v31);
    if ( !(unsigned __int8)utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
                             v30,
                             &v32) )
    {
      RegKeyData = -2147024882;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, 2147942414LL);
    }
    v15 = v26;
    while ( (_QWORD *)v30[0] != v30 )
    {
      RegKeyData = CDataCollection::GetRegKeyData(this, v30, v15, v9);
      if ( RegKeyData == -2145681407 )
        goto LABEL_49;
      if ( !v13 )
        v13 = RegKeyData >= 0;
      WriteFile(v9, L"\r\n\r\n", 8u, &v27, 0);
    }
    if ( v13 && !*((_DWORD *)this + 14) )
    {
      v16 = CReport::AddFile(*(CReport **)this, 5, 65537, *v5, L"registry.txt", 0);
      RegKeyData = v16;
      if ( v16 >= 0 )
      {
        *((_DWORD *)this + 14) = 1;
      }
      else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          (unsigned int)*v5,
          v16);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
      (unsigned int)v11);
  }
LABEL_49:
  if ( v9 != (char *)-1LL && v9 + 1 != (char *)1 )
  {
    tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, 0);
    if ( !*((_DWORD *)this + 14) )
    {
      if ( FileName[0] )
      {
        DeleteFileW(FileName);
        v18 = *v5;
        *((_QWORD *)this + 4) = *((_QWORD *)this + 3);
        *v18 = 0;
      }
    }
  }
  while ( 1 )
  {
    v19 = v30[0];
    if ( (_QWORD *)v30[0] == v30 )
      break;
    v20 = *(_QWORD **)(v30[0] + 8LL);
    v21 = *(_QWORD *)v30[0];
    *v20 = *(_QWORD *)v30[0];
    *(_QWORD *)(v21 + 8) = v20;
    utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_DeleteNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
      (__int64)v20,
      v19);
  }
  v30[2] = 0;
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return (unsigned int)RegKeyData;
}

```

## disassembly

```asm
0x18004ee3c  mov     [rsp-8+arg_10], rbx
0x18004ee41  push    rbp
0x18004ee42  push    rsi
0x18004ee43  push    rdi
0x18004ee44  push    r12
0x18004ee46  push    r13
0x18004ee48  push    r14
0x18004ee4a  push    r15
0x18004ee4c  lea     rbp, [rsp-1E0h]
0x18004ee54  sub     rsp, 2E0h
0x18004ee5b  mov     rax, cs:__security_cookie
0x18004ee62  xor     rax, rsp
0x18004ee65  mov     [rbp+210h+var_40], rax
0x18004ee6c  mov     [rsp+310h+var_2C0], r8d
0x18004ee71  mov     r13, rdx
0x18004ee74  mov     r12, rcx
0x18004ee77  xor     r15d, r15d
0x18004ee7a  mov     [rsp+310h+hFile], r15
0x18004ee7f  mov     [rsp+310h+NumberOfBytesWritten], r15d
0x18004ee84  mov     eax, 0FEFFh
0x18004ee89  mov     [rsp+310h+Buffer], ax
0x18004ee8e  lea     rcx, [rsp+310h+var_2A0]
0x18004ee93  call    ??0?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x18004ee98  nop
0x18004ee99  mov     [rsp+310h+var_2BC], r15d
0x18004ee9e  lea     rax, asc_1800B57E0; "\\ \r\n\t\v"
0x18004eea5  mov     [rbp+210h+var_288], rax
0x18004eea9  mov     [rbp+210h+var_280], 7
0x18004eeb1  mov     [rbp+210h+FileName], r15w
0x18004eeb6  lea     r14, [r12+18h]
0x18004eebb  mov     rcx, [r14]; lpFileName
0x18004eebe  cmp     rcx, [r14+8]
0x18004eec2  jnz     loc_18004EFA2
0x18004eec8  mov     [rsp+310h+var_2D8], r15d
0x18004eecd  mov     dword ptr [rsp+310h+hTemplateFile], 1
0x18004eed5  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], r15
0x18004eeda  lea     r9, [rbp+210h+FileName]
0x18004eede  lea     r8, aRegTxt; ".reg.txt"
0x18004eee5  xor     edx, edx
0x18004eee7  lea     rcx, [rsp+310h+hFile]
0x18004eeec  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18004eef1  mov     edi, eax
0x18004eef3  test    eax, eax
0x18004eef5  jns     short loc_18004EF31
0x18004eef7  lea     rsi, WPP_GLOBAL_Control
0x18004eefe  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef05  cmp     rcx, rsi
0x18004ef08  jz      short loc_18004EF27
0x18004ef0a  test    byte ptr [rcx+1Ch], 1
0x18004ef0e  jz      short loc_18004EF27
0x18004ef10  lea     edx, [r15+25h]
0x18004ef14  mov     r9d, eax
0x18004ef17  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18004ef1e  mov     rcx, [rcx+10h]
0x18004ef22  call    WPP_SF_d
0x18004ef27  mov     rbx, [rsp+310h+hFile]
0x18004ef2c  jmp     loc_18004F2A5
0x18004ef31  mov     [rsp+310h+lpOverlapped], r15; lpOverlapped
0x18004ef36  lea     r9, [rsp+310h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004ef3b  mov     r8d, 2; nNumberOfBytesToWrite
0x18004ef41  lea     rdx, [rsp+310h+Buffer]; lpBuffer
0x18004ef46  mov     rbx, [rsp+310h+hFile]
0x18004ef4b  mov     rcx, rbx; hFile
0x18004ef4e  call    cs:__imp_WriteFile
0x18004ef54  test    eax, eax
0x18004ef56  jnz     short loc_18004EF91
0x18004ef58  lea     rsi, WPP_GLOBAL_Control
0x18004ef5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef66  cmp     rcx, rsi
0x18004ef69  jz      loc_18004F296
0x18004ef6f  test    byte ptr [rcx+1Ch], 1
0x18004ef73  jz      loc_18004F296
0x18004ef79  lea     edx, [rax+26h]
0x18004ef7c  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18004ef83  mov     rcx, [rcx+10h]
0x18004ef87  call    WPP_SF_
0x18004ef8c  jmp     loc_18004F296
0x18004ef91  lea     rdx, [rbp+210h+FileName]
0x18004ef95  mov     rcx, r14
0x18004ef98  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18004ef9d  jmp     loc_18004F049
0x18004efa2  mov     [rsp+310h+hTemplateFile], r15; hTemplateFile
0x18004efa7  mov     [rsp+310h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18004efac  mov     dword ptr [rsp+310h+lpOverlapped], 3; dwCreationDisposition
0x18004efb4  xor     r9d, r9d; lpSecurityAttributes
0x18004efb7  mov     edx, 40000000h; dwDesiredAccess
0x18004efbc  lea     r8d, [r9+1]; dwShareMode
0x18004efc0  call    cs:__imp_CreateFileW
0x18004efc6  mov     rdx, rax
0x18004efc9  lea     rcx, [rsp+310h+hFile]
0x18004efce  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18004efd3  mov     rbx, [rsp+310h+hFile]
0x18004efd8  lea     rax, [rbx+1]
0x18004efdc  cmp     rax, 1
0x18004efe0  jbe     loc_18004F265
0x18004efe6  mov     rdx, rbx; void *
0x18004efe9  mov     rcx, [r14]; wchar_t *
0x18004efec  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18004eff1  mov     edi, eax
0x18004eff3  test    eax, eax
0x18004eff5  jns     short loc_18004F035
0x18004eff7  lea     rsi, WPP_GLOBAL_Control
0x18004effe  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f005  cmp     rcx, rsi
0x18004f008  jz      loc_18004F2A5
0x18004f00e  test    byte ptr [rcx+1Ch], 1
0x18004f012  jz      loc_18004F2A5
0x18004f018  mov     edx, 28h ; '('
0x18004f01d  mov     r9d, eax
0x18004f020  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18004f027  mov     rcx, [rcx+10h]
0x18004f02b  call    WPP_SF_d
0x18004f030  jmp     loc_18004F2A5
0x18004f035  mov     r9d, 2; dwMoveMethod
0x18004f03b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004f03e  xor     edx, edx; lDistanceToMove
0x18004f040  mov     rcx, rbx; hFile
0x18004f043  call    cs:__imp_SetFilePointer
0x18004f049  lea     rsi, WPP_GLOBAL_Control
0x18004f050  mov     edx, 3Bh ; ';'; Ch
0x18004f055  mov     rcx, r13; Str
0x18004f058  call    cs:__imp_wcschr
0x18004f05e  mov     r15, rax
0x18004f061  xor     ecx, ecx
0x18004f063  test    rax, rax
0x18004f066  jz      loc_18004F101
0x18004f06c  xor     edx, edx; dwMilliseconds
0x18004f06e  mov     rcx, [r12+10h]; hHandle
0x18004f073  call    cs:__imp_WaitForSingleObject
0x18004f079  test    eax, eax
0x18004f07b  jz      short loc_18004F0F7
0x18004f07d  mov     [rsp+310h+var_2B0], r13
0x18004f082  mov     rcx, r15
0x18004f085  sub     rcx, r13
0x18004f088  sar     rcx, 1
0x18004f08b  mov     [rsp+310h+var_2A8], rcx
0x18004f090  lea     r8, [rbp+210h+var_288]
0x18004f094  lea     rdx, [rsp+310h+var_2B0]
0x18004f099  lea     rcx, [rbp+210h+var_268]
0x18004f09d  call    ??$trim_view@_WU?$char_traits@_W@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@_W$0A@@tlx@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V12@AEBV12@@Z; tlx::trim_view<wchar_t,utl::char_traits<wchar_t>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18004f0a2  movups  xmm1, xmmword ptr [rax]
0x18004f0a5  movdqu  [rbp+210h+var_278], xmm1
0x18004f0aa  lea     rdx, [rbp+210h+var_278]
0x18004f0ae  lea     rcx, [rsp+310h+var_2A0]
0x18004f0b3  call    ??$emplace_back@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@$0A@@?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA_NAEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@@Z; utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x18004f0b8  test    al, al
0x18004f0ba  jnz     short loc_18004F0EE
0x18004f0bc  mov     edi, 8007000Eh
0x18004f0c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0c8  cmp     rcx, rsi
0x18004f0cb  jz      short loc_18004F0EE
0x18004f0cd  test    byte ptr [rcx+1Ch], 4
0x18004f0d1  jz      short loc_18004F0EE
0x18004f0d3  mov     edx, 29h ; ')'
0x18004f0d8  mov     r9d, 8007000Eh
0x18004f0de  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18004f0e5  mov     rcx, [rcx+10h]
0x18004f0e9  call    WPP_SF_d
0x18004f0ee  lea     r13, [r15+2]
0x18004f0f2  jmp     loc_18004F050
0x18004f0f7  mov     edi, 801B8001h
0x18004f0fc  jmp     loc_18004F2A5
0x18004f101  mov     r15d, ecx
0x18004f104  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004f108  inc     rax
0x18004f10b  cmp     [r13+rax*2+0], cx
0x18004f111  jnz     short loc_18004F108
0x18004f113  mov     [rsp+310h+var_2B0], r13
0x18004f118  add     rax, rax
0x18004f11b  sar     rax, 1
0x18004f11e  mov     [rsp+310h+var_2A8], rax
0x18004f123  lea     r8, [rbp+210h+var_288]
0x18004f127  lea     rdx, [rsp+310h+var_2B0]
0x18004f12c  lea     rcx, [rbp+210h+var_268]
0x18004f130  call    ??$trim_view@_WU?$char_traits@_W@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@_W$0A@@tlx@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V12@AEBV12@@Z; tlx::trim_view<wchar_t,utl::char_traits<wchar_t>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18004f135  movups  xmm1, xmmword ptr [rax]
0x18004f138  movdqu  [rbp+210h+var_278], xmm1
0x18004f13d  lea     rdx, [rbp+210h+var_278]
0x18004f141  lea     rcx, [rsp+310h+var_2A0]
0x18004f146  call    ??$emplace_back@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@$0A@@?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA_NAEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@@Z; utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x18004f14b  test    al, al
0x18004f14d  jnz     short loc_18004F181
0x18004f14f  mov     edi, 8007000Eh
0x18004f154  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f15b  cmp     rcx, rsi
0x18004f15e  jz      short loc_18004F181
0x18004f160  test    byte ptr [rcx+1Ch], 4
0x18004f164  jz      short loc_18004F181
0x18004f166  mov     edx, 2Ah ; '*'
0x18004f16b  mov     r9d, 8007000Eh
0x18004f171  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18004f178  mov     rcx, [rcx+10h]
0x18004f17c  call    WPP_SF_d
0x18004f181  mov     r13d, [rsp+310h+var_2C0]
0x18004f186  lea     rax, [rsp+310h+var_2A0]
0x18004f18b  cmp     [rsp+310h+var_2A0], rax
0x18004f190  jz      short loc_18004F1E4
0x18004f192  mov     r9, rbx
0x18004f195  mov     r8d, r13d
0x18004f198  lea     rdx, [rsp+310h+var_2A0]
0x18004f19d  mov     rcx, r12
0x18004f1a0  call    ?GetRegKeyData@CDataCollection@@AEAAJAEAV?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@HPEAX@Z; CDataCollection::GetRegKeyData(utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &,int,void *)
0x18004f1a5  mov     edi, eax
0x18004f1a7  cmp     eax, 801B8001h
0x18004f1ac  jz      loc_18004F2A5
0x18004f1b2  xor     eax, eax
0x18004f1b4  test    r15d, r15d
0x18004f1b7  jnz     short loc_18004F1C2
0x18004f1b9  mov     r15d, eax
0x18004f1bc  test    edi, edi
0x18004f1be  setns   r15b
0x18004f1c2  mov     [rsp+310h+lpOverlapped], rax; lpOverlapped
0x18004f1c7  lea     r9, [rsp+310h+var_2BC]; lpNumberOfBytesWritten
0x18004f1cc  mov     r8d, 8; nNumberOfBytesToWrite
0x18004f1d2  lea     rdx, asc_1800C0970; "\r\n\r\n"
0x18004f1d9  mov     rcx, rbx; hFile
0x18004f1dc  call    cs:__imp_WriteFile
0x18004f1e2  jmp     short loc_18004F186
0x18004f1e4  xor     r13d, r13d
0x18004f1e7  test    r15d, r15d
0x18004f1ea  jz      loc_18004F2A8
0x18004f1f0  xor     r15d, r15d
0x18004f1f3  cmp     [r12+38h], r15d
0x18004f1f8  jnz     loc_18004F2A8
0x18004f1fe  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], r15; wchar_t *
0x18004f203  lea     rax, aRegistryTxt; "registry.txt"
0x18004f20a  mov     [rsp+310h+lpOverlapped], rax; wchar_t *
0x18004f20f  mov     r9, [r14]; wchar_t *
0x18004f212  lea     edx, [r13+5]; enum _WER_FILE_TYPE
0x18004f216  mov     r8d, 10001h; unsigned int
0x18004f21c  mov     rcx, [r12]; this
0x18004f220  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x18004f225  mov     edi, eax
0x18004f227  test    eax, eax
0x18004f229  jns     short loc_18004F25A
0x18004f22b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f232  cmp     rcx, rsi
0x18004f235  jz      short loc_18004F2A5
0x18004f237  test    byte ptr [rcx+1Ch], 1
0x18004f23b  jz      short loc_18004F2A5
0x18004f23d  lea     edx, [r13+2Bh]
0x18004f241  mov     dword ptr [rsp+310h+lpOverlapped], eax
0x18004f245  mov     r9, [r14]
0x18004f248  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18004f24f  mov     rcx, [rcx+10h]
0x18004f253  call    WPP_SF_SD
0x18004f258  jmp     short loc_18004F2A8
0x18004f25a  mov     dword ptr [r12+38h], 1
0x18004f263  jmp     short loc_18004F2A8
0x18004f265  lea     rsi, WPP_GLOBAL_Control
0x18004f26c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f273  cmp     rcx, rsi
0x18004f276  jz      short loc_18004F296
0x18004f278  test    byte ptr [rcx+1Ch], 1
0x18004f27c  jz      short loc_18004F296
0x18004f27e  mov     edx, 27h ; '''
0x18004f283  mov     r9, [r14]
0x18004f286  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18004f28d  mov     rcx, [rcx+10h]
0x18004f291  call    WPP_SF_S
0x18004f296  call    cs:__imp_GetLastError
0x18004f29c  mov     ecx, eax; unsigned int
0x18004f29e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18004f2a3  mov     edi, eax
0x18004f2a5  xor     r13d, r13d
0x18004f2a8  inc     rbx
0x18004f2ab  cmp     rbx, 1
0x18004f2af  jbe     short loc_18004F2E0
0x18004f2b1  xor     edx, edx
0x18004f2b3  lea     rcx, [rsp+310h+hFile]
0x18004f2b8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18004f2bd  cmp     [r12+38h], r13d
0x18004f2c2  jnz     short loc_18004F2E0
0x18004f2c4  cmp     [rbp+210h+FileName], r13w
0x18004f2c9  jz      short loc_18004F2E0
0x18004f2cb  lea     rcx, [rbp+210h+FileName]; lpFileName
0x18004f2cf  call    cs:__imp_DeleteFileW
0x18004f2d5  mov     rcx, [r14]
0x18004f2d8  mov     [r14+8], rcx
0x18004f2dc  mov     [rcx], r13w
0x18004f2e0  mov     rdx, [rsp+310h+var_2A0]
0x18004f2e5  lea     rax, [rsp+310h+var_2A0]
0x18004f2ea  cmp     rdx, rax
0x18004f2ed  jz      short loc_18004F304
0x18004f2ef  mov     rcx, [rdx+8]
0x18004f2f3  mov     rax, [rdx]
0x18004f2f6  mov     [rcx], rax
0x18004f2f9  mov     [rax+8], rcx
0x18004f2fd  call    ??$_DeleteNode@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAAXPEAU?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_DeleteNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> *)
0x18004f302  jmp     short loc_18004F2E0
0x18004f304  mov     [rbp+210h+var_290], r13
0x18004f308  lea     rcx, [rsp+310h+hFile]
0x18004f30d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18004f312  mov     eax, edi
0x18004f314  mov     rcx, [rbp+210h+var_40]
0x18004f31b  xor     rcx, rsp; StackCookie
0x18004f31e  call    __security_check_cookie
0x18004f323  mov     rbx, [rsp+310h+arg_10]
0x18004f32b  add     rsp, 2E0h
0x18004f332  pop     r15
  ... truncated ...
```
