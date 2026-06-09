# TryGetDeviceInterfaceFromVolume(ushort const *,ushort * *)

- ea: `0x1800e3e70`
- end: `0x1800e42e1`
- name: `?TryGetDeviceInterfaceFromVolume@@YAJPEBGPEAPEAG@Z`
- size: `1137`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800e3b20`

## callees

- `0x1800432f0`
- `0x1800e3e70`
- `0x1803a4cb0`
- `0x1803a570a`
- `0x1803a57e0`
- `0x1803a96e5`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e4281`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e42cb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e4281`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e42cb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e40fa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e40fa`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800e4091`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800e4091`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800e40ad`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800e40ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e3f5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e4050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e4131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e3f5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e4050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e4131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e40d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e4170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e4206`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e42b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e40d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e4170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e4206`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e42b6`
- `CFGMGR32!CM_Get_Device_Interface_List_SizeW` at `0x1800e3eb7`
- `CFGMGR32!CM_Get_Device_Interface_List_SizeW` at `0x1800e3eb7`
- `CFGMGR32!CM_Get_Device_Interface_ListW` at `0x1800e3f88`
- `CFGMGR32!CM_Get_Device_Interface_ListW` at `0x1800e3f88`

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
0x1800e3e70  sub     rsp, 108h
0x1800e3e77  mov     rax, cs:__security_cookie
0x1800e3e7e  xor     rax, rsp
0x1800e3e81  mov     [rsp+108h+var_48], rax
0x1800e3e89  mov     [rsp+108h+var_D0], rdx
0x1800e3e8e  mov     r9d, 1; ulFlags
0x1800e3e94  mov     [rsp+108h+lpString1], rcx
0x1800e3e99  xor     r8d, r8d; pDeviceID
0x1800e3e9c  mov     qword ptr [rdx], 0
0x1800e3ea3  lea     rcx, [rsp+108h+pulLen]; pulLen
0x1800e3ea8  lea     rdx, GUID_DEVINTERFACE_VOLUME; InterfaceClassGuid
0x1800e3eaf  mov     [rsp+108h+pulLen], 0
0x1800e3eb7  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x1800e3ebd  test    eax, eax
0x1800e3ebf  jz      loc_1800E3F4E
0x1800e3ec5  mov     rcx, [rsp+108h]; this
0x1800e3ecd  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800e3ed4  mov     r9d, 80004005h; char *
0x1800e3eda  mov     edx, 844h; void *
0x1800e3edf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3ee4  mov     eax, 80004005h
0x1800e3ee9  mov     rcx, [rsp+108h+var_48]
0x1800e3ef1  xor     rcx, rsp; StackCookie
0x1800e3ef4  call    __security_check_cookie
0x1800e3ef9  add     rsp, 108h
0x1800e3f00  retn
0x1800e3f01  mov     rcx, [rsp+108h]; this
0x1800e3f09  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800e3f10  mov     r9d, 80004005h; char *
0x1800e3f16  mov     edx, 84Eh; void *
0x1800e3f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3f20  mov     rcx, rdi; pv
0x1800e3f23  call    cs:__imp_CoTaskMemFree
0x1800e3f29  mov     eax, 80004005h
0x1800e3f2e  mov     rdi, [rsp+108h+var_18]
0x1800e3f36  mov     rcx, [rsp+108h+var_48]
0x1800e3f3e  xor     rcx, rsp; StackCookie
0x1800e3f41  call    __security_check_cookie
0x1800e3f46  add     rsp, 108h
0x1800e3f4d  retn
0x1800e3f4e  mov     ecx, [rsp+108h+pulLen]
0x1800e3f52  add     rcx, rcx; cb
0x1800e3f55  mov     [rsp+108h+var_18], rdi
0x1800e3f5d  call    cs:__imp_CoTaskMemAlloc
0x1800e3f63  mov     rdi, rax
0x1800e3f66  test    rax, rax
0x1800e3f69  jz      loc_1800E424E
0x1800e3f6f  mov     r9d, [rsp+108h+pulLen]; BufferLen
0x1800e3f74  lea     rcx, GUID_DEVINTERFACE_VOLUME; InterfaceClassGuid
0x1800e3f7b  mov     r8, rax; Buffer
0x1800e3f7e  mov     [rsp+108h+ulFlags], 1; int
0x1800e3f86  xor     edx, edx; pDeviceID
0x1800e3f88  call    cs:__imp_CM_Get_Device_Interface_ListW
0x1800e3f8e  test    eax, eax
0x1800e3f90  jnz     loc_1800E3F01
0x1800e3f96  mov     [rsp+108h+arg_10], rbx
0x1800e3f9e  mov     rbx, rdi
0x1800e3fa1  mov     [rsp+108h+var_10], rsi
0x1800e3fa9  mov     [rsp+108h+var_20], r12
0x1800e3fb1  mov     r12d, 7FFFFFFFh
0x1800e3fb7  mov     [rsp+108h+var_8], rbp
0x1800e3fbf  mov     [rsp+108h+var_28], r13
0x1800e3fc7  mov     [rsp+108h+var_30], r14
0x1800e3fcf  mov     [rsp+108h+var_38], r15
0x1800e3fd7  nop     word ptr [rax+rax+00000000h]
0x1800e3fe0  cmp     word ptr [rbx], 0
0x1800e3fe4  jz      loc_1800E416D
0x1800e3fea  xor     eax, eax
0x1800e3fec  mov     [rsp+108h+szVolumeName], ax
0x1800e3ff1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800e3ff8  nop     dword ptr [rax+rax+00000000h]
0x1800e4000  cmp     word ptr [rbx+rax*2+2], 0
0x1800e4006  lea     rax, [rax+1]
0x1800e400a  jnz     short loc_1800E4000
0x1800e400c  lea     r13, [rax+1]
0x1800e4010  mov     rsi, rbx
0x1800e4013  cmp     r13, r12
0x1800e4016  jnb     loc_1800E417D
0x1800e401c  mov     rax, r13
0x1800e401f  test    r13, r13
0x1800e4022  jz      short loc_1800E4034
0x1800e4024  cmp     word ptr [rsi], 0
0x1800e4028  jz      short loc_1800E4034
0x1800e402a  add     rsi, 2
0x1800e402e  sub     rax, 1
0x1800e4032  jnz     short loc_1800E4024
0x1800e4034  sub     rsi, rbx
0x1800e4037  sar     rsi, 1
0x1800e403a  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800e403e  mov     rax, rsi
0x1800e4041  cmovnz  rax, r13
0x1800e4045  lea     r14, [rax+rax]
0x1800e4049  lea     rbp, [r14+2]
0x1800e404d  mov     rcx, rbp; cb
0x1800e4050  call    cs:__imp_CoTaskMemAlloc
0x1800e4056  mov     r15, rax
0x1800e4059  test    rax, rax
0x1800e405c  jz      loc_1800E4185
0x1800e4062  add     rsi, rsi
0x1800e4065  jz      short loc_1800E407E
0x1800e4067  mov     rcx, rax; void *
0x1800e406a  cmp     rbp, rsi
0x1800e406d  jb      loc_1800E4277
0x1800e4073  mov     r8, rsi; Size
0x1800e4076  mov     rdx, rbx; Src
0x1800e4079  call    memcpy_0
0x1800e407e  xor     eax, eax
0x1800e4080  lea     rdx, [r13+1]; cchPath
0x1800e4084  mov     [rsi+r15], ax
0x1800e4089  mov     rcx, r15; pszPath
0x1800e408c  mov     [r14+r15], ax
0x1800e4091  call    cs:__imp_PathCchAddBackslash
0x1800e4097  test    eax, eax
0x1800e4099  js      loc_1800E4297
0x1800e409f  mov     r8d, 32h ; '2'; cchBufferLength
0x1800e40a5  lea     rdx, [rsp+108h+szVolumeName]; lpszVolumeName
0x1800e40aa  mov     rcx, r15; lpszVolumeMountPoint
0x1800e40ad  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800e40b3  test    eax, eax
0x1800e40b5  jz      short loc_1800E40D6
0x1800e40b7  lea     rcx, [rsp+108h+szVolumeName]
0x1800e40bc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800e40c3  inc     rax
0x1800e40c6  cmp     word ptr [rcx+rax*2], 0
0x1800e40cb  jnz     short loc_1800E40C3
0x1800e40cd  test    rax, rax
0x1800e40d0  jnz     loc_1800E41C9
0x1800e40d6  mov     rcx, r15; pv
0x1800e40d9  call    cs:__imp_CoTaskMemFree
0x1800e40df  mov     rcx, [rsp+108h+lpString1]; lpString1
0x1800e40e4  lea     r8, [rsp+108h+szVolumeName]; lpString2
0x1800e40e9  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800e40ef  mov     [rsp+108h+ulFlags], 1; int
0x1800e40f7  mov     edx, r9d; cchCount1
0x1800e40fa  call    cs:__imp_CompareStringOrdinal
0x1800e4100  cmp     eax, 2
0x1800e4103  jnz     loc_1800E41A4
0x1800e4109  mov     rax, rbx
0x1800e410c  nop     dword ptr [rax+00h]
0x1800e4110  cmp     word ptr [rax], 0
0x1800e4114  jz      short loc_1800E4120
0x1800e4116  add     rax, 2
0x1800e411a  sub     r12, 1
0x1800e411e  jnz     short loc_1800E4110
0x1800e4120  sub     rax, rbx
0x1800e4123  sar     rax, 1
0x1800e4126  lea     rsi, [rax+rax]
0x1800e412a  lea     r14, [rsi+2]
0x1800e412e  mov     rcx, r14; cb
0x1800e4131  call    cs:__imp_CoTaskMemAlloc
0x1800e4137  mov     rbp, rax
0x1800e413a  test    rax, rax
0x1800e413d  jz      loc_1800E41E4
0x1800e4143  test    rsi, rsi
0x1800e4146  jz      short loc_1800E415F
0x1800e4148  mov     rcx, rax; void *
0x1800e414b  cmp     r14, rsi
0x1800e414e  jb      loc_1800E42C1
0x1800e4154  mov     r8, rsi; Size
0x1800e4157  mov     rdx, rbx; Src
0x1800e415a  call    memcpy_0
0x1800e415f  xor     eax, eax
0x1800e4161  mov     [rsi+rbp], ax
0x1800e4165  mov     rax, [rsp+108h+var_D0]
0x1800e416a  mov     [rax], rbp
0x1800e416d  mov     rcx, rdi; pv
0x1800e4170  call    cs:__imp_CoTaskMemFree
0x1800e4176  xor     eax, eax
0x1800e4178  jmp     loc_1800E4211
0x1800e417d  mov     rax, r12
0x1800e4180  jmp     loc_1800E4024
0x1800e4185  mov     rcx, [rsp+108h]; this
0x1800e418d  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800e4194  mov     r9d, 8007000Eh; char *
0x1800e419a  mov     edx, 82Dh; void *
0x1800e419f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e41a4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800e41ab  nop     dword ptr [rax+rax+00h]
0x1800e41b0  cmp     word ptr [rbx+rax*2+2], 0
0x1800e41b6  lea     rax, [rax+1]
0x1800e41ba  jnz     short loc_1800E41B0
0x1800e41bc  lea     rbx, [rbx+rax*2]
0x1800e41c0  add     rbx, 2
0x1800e41c4  jmp     loc_1800E3FE0
0x1800e41c9  cmp     [rsp+rax*2+108h+var_BA], 5Ch ; '\'
0x1800e41cf  lea     rcx, [rsp+rax*2+108h+var_BA]
0x1800e41d4  jnz     loc_1800E40D6
0x1800e41da  xor     eax, eax
0x1800e41dc  mov     [rcx], ax
0x1800e41df  jmp     loc_1800E40D6
0x1800e41e4  mov     rcx, [rsp+108h]; this
0x1800e41ec  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800e41f3  mov     r9d, 8007000Eh; char *
0x1800e41f9  mov     edx, 857h; void *
0x1800e41fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4203  mov     rcx, rdi; pv
0x1800e4206  call    cs:__imp_CoTaskMemFree
0x1800e420c  mov     eax, 8007000Eh
0x1800e4211  mov     r14, [rsp+108h+var_30]
0x1800e4219  mov     r13, [rsp+108h+var_28]
0x1800e4221  mov     rbp, [rsp+108h+var_8]
0x1800e4229  mov     r15, [rsp+108h+var_38]
0x1800e4231  mov     rsi, [rsp+108h+var_10]
0x1800e4239  mov     rbx, [rsp+108h+arg_10]
0x1800e4241  mov     r12, [rsp+108h+var_20]
0x1800e4249  jmp     loc_1800E3F2E
0x1800e424e  mov     rcx, [rsp+108h]; this
0x1800e4256  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800e425d  mov     r9d, 8007000Eh; char *
0x1800e4263  mov     edx, 847h; void *
0x1800e4268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e426d  mov     eax, 8007000Eh
0x1800e4272  jmp     loc_1800E3F2E
0x1800e4277  mov     r8, rbp; Size
0x1800e427a  xor     edx, edx; Val
0x1800e427c  call    memset_0
0x1800e4281  call    cs:__imp__o__errno
0x1800e4287  mov     dword ptr [rax], 22h ; '"'
0x1800e428d  call    _invalid_parameter_noinfo
0x1800e4292  jmp     loc_1800E407E
0x1800e4297  mov     rcx, [rsp+108h]; this
0x1800e429f  lea     r8, aOnecoreuapShel_33; "onecoreuap\\shell\\windows.storage\\sha"...
0x1800e42a6  mov     r9d, eax; char *
0x1800e42a9  mov     edx, 82Eh; void *
0x1800e42ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e42b3  mov     rcx, r15; pv
0x1800e42b6  call    cs:__imp_CoTaskMemFree
0x1800e42bc  jmp     loc_1800E41A4
0x1800e42c1  mov     r8, r14; Size
0x1800e42c4  xor     edx, edx; Val
0x1800e42c6  call    memset_0
0x1800e42cb  call    cs:__imp__o__errno
0x1800e42d1  mov     dword ptr [rax], 22h ; '"'
0x1800e42d7  call    _invalid_parameter_noinfo
0x1800e42dc  jmp     loc_1800E415F
```
