# TryGetDeviceInterfaceFromVolume(ushort const *,ushort * *)

- ea: `0x1800c8450`
- end: `0x1800c8919`
- name: `?TryGetDeviceInterfaceFromVolume@@YAJPEBGPEAPEAG@Z`
- size: `1225`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800c8110`

## callees

- `0x180038f50`
- `0x1800c8450`
- `0x1803b1f60`
- `0x1803b29ea`
- `0x1803b2ac0`
- `0x1803b69c5`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c88a7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c88fd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c88a7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c88fd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c8702`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c8702`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800c8687`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800c8687`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800c86a9`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800c86a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c854b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c8640`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c8741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c854b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c8640`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c8741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c850a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c86db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8786`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c88e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c850a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c86db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8786`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c88e2`
- `CFGMGR32!CM_Get_Device_Interface_List_SizeW` at `0x1800c8497`
- `CFGMGR32!CM_Get_Device_Interface_List_SizeW` at `0x1800c8497`
- `CFGMGR32!CM_Get_Device_Interface_ListW` at `0x1800c857c`
- `CFGMGR32!CM_Get_Device_Interface_ListW` at `0x1800c857c`

## pseudocode

```c
__int64 __fastcall TryGetDeviceInterfaceFromVolume(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  WCHAR *v3; // rax
  WCHAR *v4; // rdi
  WCHAR *v5; // rbx
  __int64 v6; // r12
  __int64 v7; // rax
  bool v8; // zf
  __int64 v9; // r13
  WCHAR *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rax
  __int64 v14; // r14
  SIZE_T v15; // rbp
  WCHAR *v16; // rax
  WCHAR *v17; // r15
  size_t v18; // rsi
  HRESULT v19; // eax
  __int64 v20; // rax
  WCHAR *v21; // rax
  size_t v22; // rsi
  size_t v23; // r14
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rbp
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  ULONG ulFlags; // [rsp+20h] [rbp-E8h]
  ULONG ulFlagsa; // [rsp+20h] [rbp-E8h]
  ULONG pulLen[4]; // [rsp+40h] [rbp-C8h] BYREF
  WCHAR szVolumeName[56]; // [rsp+50h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  *a2 = 0;
  pulLen[0] = 0;
  if ( CM_Get_Device_Interface_List_SizeW(pulLen, &GUID_DEVINTERFACE_VOLUME, 0, 1u) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x844,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\mtptl2.cpp",
      (const char *)0x80004005LL,
      ulFlags);
    return 2147500037LL;
  }
  v3 = (WCHAR *)CoTaskMemAlloc(2LL * pulLen[0]);
  v4 = v3;
  if ( !v3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x847,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\mtptl2.cpp",
      (const char *)0x8007000ELL,
      ulFlags);
    return 2147942414LL;
  }
  if ( CM_Get_Device_Interface_ListW(&GUID_DEVINTERFACE_VOLUME, 0, v3, pulLen[0], 1u) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84E,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\mtptl2.cpp",
      (const char *)0x80004005LL,
      ulFlagsa);
    CoTaskMemFree(v4);
    return 2147500037LL;
  }
  v5 = v4;
  v6 = 0x7FFFFFFF;
  while ( 1 )
  {
    if ( !*v5 )
      goto LABEL_35;
    szVolumeName[0] = 0;
    v7 = -1;
    do
      v8 = v5[++v7] == 0;
    while ( !v8 );
    v9 = v7 + 1;
    v10 = v5;
    if ( (unsigned __int64)(v7 + 1) >= 0x7FFFFFFF )
    {
      v11 = 0x7FFFFFFF;
    }
    else
    {
      v11 = v7 + 1;
      if ( !v9 )
        goto LABEL_15;
    }
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v11;
    }
    while ( v11 );
LABEL_15:
    v12 = v10 - v5;
    v13 = v12;
    if ( v9 != -1 )
      v13 = v9;
    v14 = v13;
    v15 = 2 * v13 + 2;
    v16 = (WCHAR *)CoTaskMemAlloc(v15);
    v17 = v16;
    if ( !v16 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82D,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\mtptl2.cpp",
        (const char *)0x8007000ELL,
        ulFlagsa);
      goto LABEL_38;
    }
    v18 = 2 * v12;
    if ( v18 )
    {
      if ( v15 < v18 )
      {
        memset_0(v16, 0, v15);
        *(_DWORD *)_o__errno(v27) = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v16, v5, v18);
      }
    }
    v17[v18 / 2] = 0;
    v17[v14] = 0;
    v19 = PathCchAddBackslash(v17, v9 + 1);
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82E,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\mtptl2.cpp",
        (const char *)(unsigned int)v19,
        ulFlagsa);
      CoTaskMemFree(v17);
      goto LABEL_38;
    }
    if ( GetVolumeNameForVolumeMountPointW(v17, szVolumeName, 0x32u) )
    {
      v20 = -1;
      do
        ++v20;
      while ( szVolumeName[v20] );
      if ( v20 && *((_WORD *)&pulLen[3] + v20 + 1) == 92 )
        *((_WORD *)&pulLen[3] + v20 + 1) = 0;
    }
    CoTaskMemFree(v17);
    if ( CompareStringOrdinal(a1, -1, szVolumeName, -1, 1) == 2 )
      break;
LABEL_38:
    v26 = -1;
    do
      v8 = v5[++v26] == 0;
    while ( !v8 );
    v5 += v26 + 1;
  }
  v21 = v5;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v6;
  }
  while ( v6 );
  v22 = 2 * (v21 - v5);
  v23 = v22 + 2;
  v24 = (unsigned __int16 *)CoTaskMemAlloc(v22 + 2);
  v25 = v24;
  if ( v24 )
  {
    if ( v22 )
    {
      if ( v23 < v22 )
      {
        memset_0(v24, 0, v23);
        *(_DWORD *)_o__errno(v28) = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v24, v5, v22);
      }
    }
    v25[v22 / 2] = 0;
    *a2 = v25;
LABEL_35:
    CoTaskMemFree(v4);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x857,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\mtptl2.cpp",
    (const char *)0x8007000ELL,
    ulFlagsa);
  CoTaskMemFree(v4);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800c8450  sub     rsp, 108h
0x1800c8457  mov     rax, cs:__security_cookie
0x1800c845e  xor     rax, rsp
0x1800c8461  mov     [rsp+108h+var_48], rax
0x1800c8469  mov     [rsp+108h+var_D0], rdx
0x1800c846e  mov     r9d, 1; ulFlags
0x1800c8474  mov     [rsp+108h+lpString1], rcx
0x1800c8479  xor     r8d, r8d; pDeviceID
0x1800c847c  mov     qword ptr [rdx], 0
0x1800c8483  lea     rcx, [rsp+108h+pulLen]; pulLen
0x1800c8488  lea     rdx, GUID_DEVINTERFACE_VOLUME; InterfaceClassGuid
0x1800c848f  mov     [rsp+108h+pulLen], 0
0x1800c8497  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x1800c849e  nop     dword ptr [rax+rax+00h]
0x1800c84a3  test    eax, eax
0x1800c84a5  jz      loc_1800C853C
0x1800c84ab  mov     rcx, [rsp+108h]; this
0x1800c84b3  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800c84ba  mov     r9d, 80004005h; char *
0x1800c84c0  mov     edx, 844h; void *
0x1800c84c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c84ca  mov     eax, 80004005h
0x1800c84cf  mov     rcx, [rsp+108h+var_48]
0x1800c84d7  xor     rcx, rsp; StackCookie
0x1800c84da  call    __security_check_cookie
0x1800c84df  add     rsp, 108h
0x1800c84e6  retn
0x1800c84e8  mov     rcx, [rsp+108h]; this
0x1800c84f0  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800c84f7  mov     r9d, 80004005h; char *
0x1800c84fd  mov     edx, 84Eh; void *
0x1800c8502  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8507  mov     rcx, rdi; pv
0x1800c850a  call    cs:__imp_CoTaskMemFree
0x1800c8511  nop     dword ptr [rax+rax+00h]
0x1800c8516  mov     eax, 80004005h
0x1800c851b  mov     rdi, [rsp+108h+var_18]
0x1800c8523  mov     rcx, [rsp+108h+var_48]
0x1800c852b  xor     rcx, rsp; StackCookie
0x1800c852e  call    __security_check_cookie
0x1800c8533  add     rsp, 108h
0x1800c853a  retn
0x1800c853c  mov     ecx, [rsp+108h+pulLen]
0x1800c8540  add     rcx, rcx; cb
0x1800c8543  mov     [rsp+108h+var_18], rdi
0x1800c854b  call    cs:__imp_CoTaskMemAlloc
0x1800c8552  nop     dword ptr [rax+rax+00h]
0x1800c8557  mov     rdi, rax
0x1800c855a  test    rax, rax
0x1800c855d  jz      loc_1800C8874
0x1800c8563  mov     r9d, [rsp+108h+pulLen]; BufferLen
0x1800c8568  lea     rcx, GUID_DEVINTERFACE_VOLUME; InterfaceClassGuid
0x1800c856f  mov     r8, rax; Buffer
0x1800c8572  mov     [rsp+108h+ulFlags], 1; int
0x1800c857a  xor     edx, edx; pDeviceID
0x1800c857c  call    cs:__imp_CM_Get_Device_Interface_ListW
0x1800c8583  nop     dword ptr [rax+rax+00h]
0x1800c8588  test    eax, eax
0x1800c858a  jnz     loc_1800C84E8
0x1800c8590  mov     [rsp+108h+arg_10], rbx
0x1800c8598  mov     rbx, rdi
0x1800c859b  mov     [rsp+108h+var_10], rsi
0x1800c85a3  mov     [rsp+108h+var_20], r12
0x1800c85ab  mov     r12d, 7FFFFFFFh
0x1800c85b1  mov     [rsp+108h+var_8], rbp
0x1800c85b9  mov     [rsp+108h+var_28], r13
0x1800c85c1  mov     [rsp+108h+var_30], r14
0x1800c85c9  mov     [rsp+108h+var_38], r15
0x1800c85d1  cmp     word ptr [rbx], 0
0x1800c85d5  jz      loc_1800C8783
0x1800c85db  xor     eax, eax
0x1800c85dd  mov     [rsp+108h+szVolumeName], ax
0x1800c85e2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800c85e9  nop     dword ptr [rax+00000000h]
0x1800c85f0  cmp     word ptr [rbx+rax*2+2], 0
0x1800c85f6  lea     rax, [rax+1]
0x1800c85fa  jnz     short loc_1800C85F0
0x1800c85fc  lea     r13, [rax+1]
0x1800c8600  mov     rsi, rbx
0x1800c8603  cmp     r13, r12
0x1800c8606  jnb     loc_1800C8799
0x1800c860c  mov     rax, r13
0x1800c860f  test    r13, r13
0x1800c8612  jz      short loc_1800C8624
0x1800c8614  cmp     word ptr [rsi], 0
0x1800c8618  jz      short loc_1800C8624
0x1800c861a  add     rsi, 2
0x1800c861e  sub     rax, 1
0x1800c8622  jnz     short loc_1800C8614
0x1800c8624  sub     rsi, rbx
0x1800c8627  sar     rsi, 1
0x1800c862a  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800c862e  mov     rax, rsi
0x1800c8631  cmovnz  rax, r13
0x1800c8635  lea     r14, [rax+rax]
0x1800c8639  lea     rbp, [r14+2]
0x1800c863d  mov     rcx, rbp; cb
0x1800c8640  call    cs:__imp_CoTaskMemAlloc
0x1800c8647  nop     dword ptr [rax+rax+00h]
0x1800c864c  mov     r15, rax
0x1800c864f  test    rax, rax
0x1800c8652  jz      loc_1800C87A1
0x1800c8658  add     rsi, rsi
0x1800c865b  jz      short loc_1800C8674
0x1800c865d  mov     rcx, rax; void *
0x1800c8660  cmp     rbp, rsi
0x1800c8663  jb      loc_1800C889D
0x1800c8669  mov     r8, rsi; Size
0x1800c866c  mov     rdx, rbx; Src
0x1800c866f  call    memcpy_0
0x1800c8674  xor     eax, eax
0x1800c8676  lea     rdx, [r13+1]; cchPath
0x1800c867a  mov     [rsi+r15], ax
0x1800c867f  mov     rcx, r15; pszPath
0x1800c8682  mov     [r14+r15], ax
0x1800c8687  call    cs:__imp_PathCchAddBackslash
0x1800c868e  nop     dword ptr [rax+rax+00h]
0x1800c8693  test    eax, eax
0x1800c8695  js      loc_1800C88C3
0x1800c869b  mov     r8d, 32h ; '2'; cchBufferLength
0x1800c86a1  lea     rdx, [rsp+108h+szVolumeName]; lpszVolumeName
0x1800c86a6  mov     rcx, r15; lpszVolumeMountPoint
0x1800c86a9  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800c86b0  nop     dword ptr [rax+rax+00h]
0x1800c86b5  test    eax, eax
0x1800c86b7  jz      short loc_1800C86D8
0x1800c86b9  lea     rcx, [rsp+108h+szVolumeName]
0x1800c86be  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800c86c5  inc     rax
0x1800c86c8  cmp     word ptr [rcx+rax*2], 0
0x1800c86cd  jnz     short loc_1800C86C5
0x1800c86cf  test    rax, rax
0x1800c86d2  jnz     loc_1800C87E9
0x1800c86d8  mov     rcx, r15; pv
0x1800c86db  call    cs:__imp_CoTaskMemFree
0x1800c86e2  nop     dword ptr [rax+rax+00h]
0x1800c86e7  mov     rcx, [rsp+108h+lpString1]; lpString1
0x1800c86ec  lea     r8, [rsp+108h+szVolumeName]; lpString2
0x1800c86f1  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800c86f7  mov     [rsp+108h+ulFlags], 1; int
0x1800c86ff  mov     edx, r9d; cchCount1
0x1800c8702  call    cs:__imp_CompareStringOrdinal
0x1800c8709  nop     dword ptr [rax+rax+00h]
0x1800c870e  cmp     eax, 2
0x1800c8711  jnz     loc_1800C87C0
0x1800c8717  mov     rax, rbx
0x1800c871a  nop     word ptr [rax+rax+00h]
0x1800c8720  cmp     word ptr [rax], 0
0x1800c8724  jz      short loc_1800C8730
0x1800c8726  add     rax, 2
0x1800c872a  sub     r12, 1
0x1800c872e  jnz     short loc_1800C8720
0x1800c8730  sub     rax, rbx
0x1800c8733  sar     rax, 1
0x1800c8736  lea     rsi, [rax+rax]
0x1800c873a  lea     r14, [rsi+2]
0x1800c873e  mov     rcx, r14; cb
0x1800c8741  call    cs:__imp_CoTaskMemAlloc
0x1800c8748  nop     dword ptr [rax+rax+00h]
0x1800c874d  mov     rbp, rax
0x1800c8750  test    rax, rax
0x1800c8753  jz      loc_1800C8804
0x1800c8759  test    rsi, rsi
0x1800c875c  jz      short loc_1800C8775
0x1800c875e  mov     rcx, rax; void *
0x1800c8761  cmp     r14, rsi
0x1800c8764  jb      loc_1800C88F3
0x1800c876a  mov     r8, rsi; Size
0x1800c876d  mov     rdx, rbx; Src
0x1800c8770  call    memcpy_0
0x1800c8775  xor     eax, eax
0x1800c8777  mov     [rsi+rbp], ax
0x1800c877b  mov     rax, [rsp+108h+var_D0]
0x1800c8780  mov     [rax], rbp
0x1800c8783  mov     rcx, rdi; pv
0x1800c8786  call    cs:__imp_CoTaskMemFree
0x1800c878d  nop     dword ptr [rax+rax+00h]
0x1800c8792  xor     eax, eax
0x1800c8794  jmp     loc_1800C8837
0x1800c8799  mov     rax, r12
0x1800c879c  jmp     loc_1800C8614
0x1800c87a1  mov     rcx, [rsp+108h]; this
0x1800c87a9  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800c87b0  mov     r9d, 8007000Eh; char *
0x1800c87b6  mov     edx, 82Dh; void *
0x1800c87bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c87c0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800c87c7  nop     word ptr [rax+rax+00000000h]
0x1800c87d0  cmp     word ptr [rbx+rax*2+2], 0
0x1800c87d6  lea     rax, [rax+1]
0x1800c87da  jnz     short loc_1800C87D0
0x1800c87dc  lea     rbx, [rbx+rax*2]
0x1800c87e0  add     rbx, 2
0x1800c87e4  jmp     loc_1800C85D1
0x1800c87e9  cmp     [rsp+rax*2+108h+var_BA], 5Ch ; '\'
0x1800c87ef  lea     rcx, [rsp+rax*2+108h+var_BA]
0x1800c87f4  jnz     loc_1800C86D8
0x1800c87fa  xor     eax, eax
0x1800c87fc  mov     [rcx], ax
0x1800c87ff  jmp     loc_1800C86D8
0x1800c8804  mov     rcx, [rsp+108h]; this
0x1800c880c  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800c8813  mov     r9d, 8007000Eh; char *
0x1800c8819  mov     edx, 857h; void *
0x1800c881e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8823  mov     rcx, rdi; pv
0x1800c8826  call    cs:__imp_CoTaskMemFree
0x1800c882d  nop     dword ptr [rax+rax+00h]
0x1800c8832  mov     eax, 8007000Eh
0x1800c8837  mov     r14, [rsp+108h+var_30]
0x1800c883f  mov     r13, [rsp+108h+var_28]
0x1800c8847  mov     rbp, [rsp+108h+var_8]
0x1800c884f  mov     r15, [rsp+108h+var_38]
0x1800c8857  mov     rsi, [rsp+108h+var_10]
0x1800c885f  mov     rbx, [rsp+108h+arg_10]
0x1800c8867  mov     r12, [rsp+108h+var_20]
0x1800c886f  jmp     loc_1800C851B
0x1800c8874  mov     rcx, [rsp+108h]; this
0x1800c887c  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800c8883  mov     r9d, 8007000Eh; char *
0x1800c8889  mov     edx, 847h; void *
0x1800c888e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8893  mov     eax, 8007000Eh
0x1800c8898  jmp     loc_1800C851B
0x1800c889d  mov     r8, rbp; Size
0x1800c88a0  xor     edx, edx; Val
0x1800c88a2  call    memset_0
0x1800c88a7  call    cs:__imp__o__errno
0x1800c88ae  nop     dword ptr [rax+rax+00h]
0x1800c88b3  mov     dword ptr [rax], 22h ; '"'
0x1800c88b9  call    _invalid_parameter_noinfo
0x1800c88be  jmp     loc_1800C8674
0x1800c88c3  mov     rcx, [rsp+108h]; this
0x1800c88cb  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800c88d2  mov     r9d, eax; char *
0x1800c88d5  mov     edx, 82Eh; void *
0x1800c88da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c88df  mov     rcx, r15; pv
0x1800c88e2  call    cs:__imp_CoTaskMemFree
0x1800c88e9  nop     dword ptr [rax+rax+00h]
0x1800c88ee  jmp     loc_1800C87C0
0x1800c88f3  mov     r8, r14; Size
0x1800c88f6  xor     edx, edx; Val
0x1800c88f8  call    memset_0
0x1800c88fd  call    cs:__imp__o__errno
0x1800c8904  nop     dword ptr [rax+rax+00h]
0x1800c8909  mov     dword ptr [rax], 22h ; '"'
0x1800c890f  call    _invalid_parameter_noinfo
0x1800c8914  jmp     loc_1800C8775
```
