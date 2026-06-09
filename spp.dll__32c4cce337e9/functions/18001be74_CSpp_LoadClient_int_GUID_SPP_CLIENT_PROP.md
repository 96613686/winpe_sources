# CSpp::_LoadClient(int,_GUID,_SPP_CLIENT_PROP *)

- ea: `0x18001be74`
- end: `0x18001c2e1`
- name: `?_LoadClient@CSpp@@AEAAJHU_GUID@@PEAU_SPP_CLIENT_PROP@@@Z`
- size: `1133`
- prototype: `__int64 __fastcall(CSpp *__hidden this, int, struct _GUID *__struct_ptr, struct _SPP_CLIENT_PROP *)`
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a430`
- `0x18000e7b0`
- `0x180017dfc`
- `0x18001c2e8`

## callees

- `0x18001be74`
- `0x18001e508`
- `0x18001f31c`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002e410`
- `0x18002e880`
- `0x1800346c0`
- `0x180035390`
- `0x180035b00`
- `0x180035b76`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001c1cb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001c1cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c25b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c25b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001bfca`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001bfca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c03e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c17e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c286`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c03e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c17e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c286`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c067`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c1a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c067`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c1a7`

## string_xrefs

- `0x18001c00d`: `SPP-Temp`
- `0x18001c14d`: `SPP-Temp`

## pseudocode

```c
__int64 __fastcall CSpp::_LoadClient(CSpp *this, int a2, struct _GUID *a3, struct _SPP_CLIENT_PROP *a4)
{
  unsigned __int16 *v8; // rdi
  __int64 v9; // rcx
  struct _SPP_CLIENT_PROP *v10; // rax
  bool v11; // zf
  __int16 v12; // ax
  __int64 v13; // xmm0_8
  bool v14; // sf
  int v15; // eax
  int v16; // eax
  bool v17; // sf
  int v18; // r9d
  unsigned __int64 v19; // rdx
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  unsigned int v22; // ebx
  __int64 v23; // r8
  char *v24; // rdx
  const unsigned __int16 *v26; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v27; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v28; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v29; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v30; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v31; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v32; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v33; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v34; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v35; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v36; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v37; // [rsp+50h] [rbp-B0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+70h] [rbp-90h] BYREF
  __int16 v41; // [rsp+74h] [rbp-8Ch]
  __int16 v42; // [rsp+76h] [rbp-8Ah]
  LPCWSTR lpSubKey[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v44; // [rsp+B8h] [rbp-48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v46; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v47[3]; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR sz; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v49[78]; // [rsp+112h] [rbp+12h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v40, "CSpp::_LoadClient", 3181, 1);
  hKey = 0;
  lpSubKey[0] = &FileName;
  lpSubKey[1] = 0;
  v8 = 0;
  v44 = 0;
  sz = 0;
  memset_0(v49, 0, 0x4Cu);
  v39 = 0;
  memset(v47, 0, sizeof(v47));
  SystemTimeAsFileTime = 0;
  *(_QWORD *)&v46.Data1 = 0;
  if ( a4 )
  {
    v9 = 48;
    v10 = a4;
    do
    {
      *(_BYTE *)v10 = 0;
      v10 = (struct _SPP_CLIENT_PROP *)((char *)v10 + 1);
      --v9;
    }
    while ( v9 );
  }
  v11 = memcmp_0(a3, &GUID_NULL, 0x10u) == 0;
  v12 = 3197;
  if ( v11 || (v41 = 3197, v12 = 3198, !a4) )
  {
    v40 = -2147024809;
LABEL_9:
    v42 = v12;
    goto LABEL_41;
  }
  v13 = *(_QWORD *)&a3->Data2;
  v41 = 3198;
  LODWORD(v47[0]) = a3->Data1;
  HIDWORD(v47[0]) = *(_DWORD *)&a3->Data4[4];
  v40 = 0;
  *(_QWORD *)((char *)v47 + 4) = v13;
  v11 = StringFromGUID2(a3, &sz, 39) == 0;
  v12 = 3202;
  if ( v11 )
  {
    v40 = -2147418113;
    goto LABEL_9;
  }
  v40 = 0;
  v41 = 3202;
  if ( a2 )
  {
    v40 = CBsString::SetPath(
            (CBsString *)lpSubKey,
            L"SPP-Temp",
            L"Microsoft\\Windows NT\\CurrentVersion\\SPP",
            L"Clients",
            0,
            v26,
            v28,
            v30,
            v32,
            v34,
            v36);
    v14 = v40 < 0;
    v12 = 3206;
  }
  else
  {
    v40 = CBsString::SetPath(
            (CBsString *)lpSubKey,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP",
            L"Clients",
            0,
            0,
            v26,
            v28,
            v30,
            v32,
            v34,
            v36);
    v14 = v40 < 0;
    v12 = 3210;
  }
  if ( v14 )
    goto LABEL_9;
  v41 = v12;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  v40 = v15;
  v14 = v15 < 0;
  v12 = 3212;
  if ( v14 )
    goto LABEL_9;
  v41 = 3212;
  v16 = SxRegReadMultiString(hKey, &sz, &v44);
  v8 = v44;
  if ( v16 < 0 )
  {
    v40 = -2130706169;
    v12 = 3221;
    goto LABEL_9;
  }
  v40 = CSpp::_SplitClientVolumes(this, v44, (struct _SPP_CLIENT_PROP *)v47, &v39);
  v12 = 3223;
  if ( v40 < 0 )
    goto LABEL_9;
  v41 = 3223;
  *(_QWORD *)&v47[1] = 2;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( a2 )
  {
    v40 = CBsString::SetPath(
            (CBsString *)lpSubKey,
            L"SPP-Temp",
            L"Microsoft\\Windows NT\\CurrentVersion\\SPP",
            L"Leases",
            0,
            v27,
            v29,
            v31,
            v33,
            v35,
            v37);
    v17 = v40 < 0;
    v12 = 3235;
  }
  else
  {
    v40 = CBsString::SetPath(
            (CBsString *)lpSubKey,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP",
            L"Leases",
            0,
            0,
            v27,
            v29,
            v31,
            v33,
            v35,
            v37);
    v17 = v40 < 0;
    v12 = 3239;
  }
  if ( v17 )
    goto LABEL_9;
  v41 = v12;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey)
    && (int)SxRegReadULONGLONG(hKey, &sz, (unsigned __int64 *)&v46.Data1, v18) >= 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(_QWORD *)&v47[1] = 1;
    if ( *(_QWORD *)&v46.Data1 > *(unsigned __int64 *)&SystemTimeAsFileTime )
    {
      v19 = (*(_QWORD *)&v46.Data1 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL;
      if ( v19 > 0xFFFFFFFF )
        LODWORD(v19) = -1;
      DWORD1(v47[1]) = v19;
    }
  }
  if ( v39 )
  {
    v46 = *a3;
    CSpp::_UpdateClientVolumes(
      this,
      &v46,
      DWORD2(v47[1]),
      *(const unsigned __int16 *const **)&v47[2],
      *((const unsigned __int16 *const **)&v47[2] + 1));
  }
  v20 = v47[1];
  *(_OWORD *)a4 = v47[0];
  v21 = v47[2];
  *((_OWORD *)a4 + 1) = v20;
  *((_OWORD *)a4 + 2) = v21;
  memset(v47, 0, sizeof(v47));
LABEL_41:
  CoTaskMemFree(v8);
  Free_SPP_CLIENT_PROP((struct _SPP_CLIENT_PROP *)v47);
  v22 = v40;
  CBsString::_Release((CBsString *)lpSubKey);
  v24 = (char *)hKey - 1;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v40, (__int64)v24, v23);
  return v22;
}

```

## disassembly

```asm
0x18001be74  push    rbp
0x18001be76  push    rbx
0x18001be77  push    rsi
0x18001be78  push    rdi
0x18001be79  push    r12
0x18001be7b  push    r14
0x18001be7d  push    r15
0x18001be7f  lea     rbp, [rsp-70h]
0x18001be84  sub     rsp, 170h
0x18001be8b  mov     rax, cs:__security_cookie
0x18001be92  xor     rax, rsp
0x18001be95  mov     [rbp+0A0h+var_40], rax
0x18001be99  mov     rbx, r9
0x18001be9c  mov     rsi, r8
0x18001be9f  mov     r14d, edx
0x18001bea2  mov     r15, rcx
0x18001bea5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001beac  lea     rax, WPP_GLOBAL_Control
0x18001beb3  cmp     rcx, rax
0x18001beb6  jz      short loc_18001BED6
0x18001beb8  test    dword ptr [rcx+1Ch], 20000000h
0x18001bebf  jz      short loc_18001BED6
0x18001bec1  mov     rcx, [rcx+10h]
0x18001bec5  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001becc  mov     edx, 24h ; '$'
0x18001bed1  call    WPP_SF_
0x18001bed6  mov     r9d, 1; unsigned __int16
0x18001bedc  lea     rdx, aCsppLoadclient_0; "CSpp::_LoadClient"
0x18001bee3  mov     r8d, 0C6Dh; unsigned __int16
0x18001bee9  lea     rcx, [rsp+1A0h+var_130]; this
0x18001beee  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001bef3  xor     r12d, r12d
0x18001bef6  lea     rax, FileName
0x18001befd  xor     edx, edx; Val
0x18001beff  mov     [rsp+1A0h+hKey], r12
0x18001bf04  lea     rcx, [rbp+0A0h+var_8E]; void *
0x18001bf08  mov     [rbp+0A0h+lpSubKey], rax
0x18001bf0c  mov     [rbp+0A0h+var_F0], r12
0x18001bf10  mov     edi, r12d
0x18001bf13  lea     r8d, [r12+4Ch]; Size
0x18001bf18  mov     [rbp+0A0h+var_E8], r12
0x18001bf1c  mov     [rbp+0A0h+sz], r12w
0x18001bf21  call    memset_0
0x18001bf26  mov     [rsp+1A0h+var_138], r12d
0x18001bf2b  xorps   xmm0, xmm0
0x18001bf2e  mov     dword ptr [rbp+0A0h+var_C0], r12d
0x18001bf32  mov     qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18001bf36  mov     qword ptr [rbp+0A0h+var_D0.Data1], r12
0x18001bf3a  movups  xmmword ptr [rbp+0A0h+var_AC], xmm0
0x18001bf3e  movups  xmmword ptr [rbp+0A0h+var_AC+0Ch], xmm0
0x18001bf42  movups  [rbp+0A0h+var_C0+4], xmm0
0x18001bf46  test    rbx, rbx
0x18001bf49  jz      short loc_18001BF5F
0x18001bf4b  lea     ecx, [r12+30h]
0x18001bf50  mov     rax, rbx
0x18001bf53  mov     [rax], r12b
0x18001bf56  inc     rax
0x18001bf59  sub     rcx, 1
0x18001bf5d  jnz     short loc_18001BF53
0x18001bf5f  mov     r8d, 10h; Size
0x18001bf65  lea     rdx, GUID_NULL; Buf2
0x18001bf6c  mov     rcx, rsi; Buf1
0x18001bf6f  call    memcmp_0
0x18001bf74  test    eax, eax
0x18001bf76  mov     eax, 0C7Dh
0x18001bf7b  jnz     short loc_18001BF8F
0x18001bf7d  mov     [rsp+1A0h+var_130], 80070057h
0x18001bf85  mov     [rsp+1A0h+var_12A], ax
0x18001bf8a  jmp     loc_18001C258
0x18001bf8f  mov     [rsp+1A0h+var_12C], ax
0x18001bf94  mov     eax, 0C7Eh
0x18001bf99  test    rbx, rbx
0x18001bf9c  jz      short loc_18001BF7D
0x18001bf9e  movsd   xmm0, qword ptr [rsi+4]
0x18001bfa3  lea     rdx, [rbp+0A0h+sz]; lpsz
0x18001bfa7  mov     [rsp+1A0h+var_12C], ax
0x18001bfac  mov     r8d, 27h ; '''; cchMax
0x18001bfb2  mov     eax, [rsi]
0x18001bfb4  mov     rcx, rsi; rguid
0x18001bfb7  mov     dword ptr [rbp+0A0h+var_C0], eax
0x18001bfba  mov     eax, [rsi+0Ch]
0x18001bfbd  mov     dword ptr [rbp+0A0h+var_C0+0Ch], eax
0x18001bfc0  mov     [rsp+1A0h+var_130], r12d
0x18001bfc5  movsd   qword ptr [rbp+0A0h+var_C0+4], xmm0
0x18001bfca  call    cs:__imp_StringFromGUID2
0x18001bfd0  test    eax, eax
0x18001bfd2  mov     eax, 0C82h
0x18001bfd7  jnz     short loc_18001BFE3
0x18001bfd9  mov     [rsp+1A0h+var_130], 8000FFFFh
0x18001bfe1  jmp     short loc_18001BF85
0x18001bfe3  mov     [rsp+1A0h+var_130], r12d
0x18001bfe8  lea     rcx, [rbp+0A0h+lpSubKey]; this
0x18001bfec  mov     [rsp+1A0h+var_12C], ax
0x18001bff1  mov     [rsp+1A0h+phkResult], r12; unsigned __int16 *
0x18001bff6  test    r14d, r14d
0x18001bff9  jz      loc_18001C0BB
0x18001bfff  lea     r9, aClients; "Clients"
0x18001c006  lea     r8, aMicrosoftWindo_0; "Microsoft\\Windows NT\\CurrentVersion\\"...
0x18001c00d  lea     rdx, SubKey; "SPP-Temp"
0x18001c014  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001c019  mov     [rsp+1A0h+var_130], eax
0x18001c01d  test    eax, eax
0x18001c01f  mov     eax, 0C86h
0x18001c024  js      loc_18001BF85
0x18001c02a  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18001c02f  mov     [rsp+1A0h+var_12C], ax
0x18001c034  lea     rax, [rcx-1]
0x18001c038  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c03c  ja      short loc_18001C049
0x18001c03e  call    cs:__imp_RegCloseKey
0x18001c044  mov     [rsp+1A0h+hKey], r12
0x18001c049  mov     rdx, [rbp+0A0h+lpSubKey]; lpSubKey
0x18001c04d  lea     rax, [rsp+1A0h+hKey]
0x18001c052  mov     r9d, 20019h; samDesired
0x18001c058  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18001c05d  xor     r8d, r8d; ulOptions
0x18001c060  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c067  call    cs:__imp_RegOpenKeyExW
0x18001c06d  test    eax, eax
0x18001c06f  jle     short loc_18001C079
0x18001c071  movzx   eax, ax
0x18001c074  or      eax, 80070000h
0x18001c079  mov     [rsp+1A0h+var_130], eax
0x18001c07d  test    eax, eax
0x18001c07f  mov     eax, 0C8Ch
0x18001c084  js      loc_18001BF85
0x18001c08a  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18001c08f  lea     r8, [rbp+0A0h+var_E8]; unsigned __int16 **
0x18001c093  lea     rdx, [rbp+0A0h+sz]; lpValueName
0x18001c097  mov     [rsp+1A0h+var_12C], ax
0x18001c09c  call    ?SxRegReadMultiString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; SxRegReadMultiString(HKEY__ *,ushort const *,ushort * *)
0x18001c0a1  mov     rdi, [rbp+0A0h+var_E8]
0x18001c0a5  test    eax, eax
0x18001c0a7  jns     short loc_18001C0E1
0x18001c0a9  mov     [rsp+1A0h+var_130], 81000107h
0x18001c0b1  mov     eax, 0C95h
0x18001c0b6  jmp     loc_18001BF85
0x18001c0bb  xor     r9d, r9d; unsigned __int16 *
0x18001c0be  lea     r8, aClients; "Clients"
0x18001c0c5  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001c0cc  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001c0d1  mov     [rsp+1A0h+var_130], eax
0x18001c0d5  test    eax, eax
0x18001c0d7  mov     eax, 0C8Ah
0x18001c0dc  jmp     loc_18001C024
0x18001c0e1  lea     r9, [rsp+1A0h+var_138]; int *
0x18001c0e6  mov     rdx, rdi; unsigned __int16 *
0x18001c0e9  lea     r8, [rbp+0A0h+var_C0]; struct _SPP_CLIENT_PROP *
0x18001c0ed  mov     rcx, r15; this
0x18001c0f0  call    ?_SplitClientVolumes@CSpp@@AEAAJPEBGPEAU_SPP_CLIENT_PROP@@PEAH@Z; CSpp::_SplitClientVolumes(ushort const *,_SPP_CLIENT_PROP *,int *)
0x18001c0f5  mov     [rsp+1A0h+var_130], eax
0x18001c0f9  test    eax, eax
0x18001c0fb  mov     eax, 0C97h
0x18001c100  js      loc_18001BF85
0x18001c106  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18001c10b  mov     [rsp+1A0h+var_12C], ax
0x18001c110  mov     qword ptr [rbp-10h], 2
0x18001c118  lea     rax, [rcx-1]
0x18001c11c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c120  ja      short loc_18001C12D
0x18001c122  call    cs:__imp_RegCloseKey
0x18001c128  mov     [rsp+1A0h+hKey], r12
0x18001c12d  mov     [rsp+1A0h+phkResult], r12; unsigned __int16 *
0x18001c132  lea     rcx, [rbp+0A0h+lpSubKey]; this
0x18001c136  test    r14d, r14d
0x18001c139  jz      loc_18001C2BB
0x18001c13f  lea     r9, aLeases; "Leases"
0x18001c146  lea     r8, aMicrosoftWindo_0; "Microsoft\\Windows NT\\CurrentVersion\\"...
0x18001c14d  lea     rdx, SubKey; "SPP-Temp"
0x18001c154  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001c159  mov     [rsp+1A0h+var_130], eax
0x18001c15d  test    eax, eax
0x18001c15f  mov     eax, 0CA3h
0x18001c164  js      loc_18001BF85
0x18001c16a  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18001c16f  mov     [rsp+1A0h+var_12C], ax
0x18001c174  lea     rax, [rcx-1]
0x18001c178  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c17c  ja      short loc_18001C189
0x18001c17e  call    cs:__imp_RegCloseKey
0x18001c184  mov     [rsp+1A0h+hKey], r12
0x18001c189  mov     rdx, [rbp+0A0h+lpSubKey]; lpSubKey
0x18001c18d  lea     rax, [rsp+1A0h+hKey]
0x18001c192  mov     r9d, 20019h; samDesired
0x18001c198  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18001c19d  xor     r8d, r8d; ulOptions
0x18001c1a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c1a7  call    cs:__imp_RegOpenKeyExW
0x18001c1ad  test    eax, eax
0x18001c1af  jnz     short loc_18001C206
0x18001c1b1  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18001c1b6  lea     r8, [rbp+0A0h+var_D0]; unsigned __int64 *
0x18001c1ba  lea     rdx, [rbp+0A0h+sz]; lpValueName
0x18001c1be  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x18001c1c3  test    eax, eax
0x18001c1c5  js      short loc_18001C206
0x18001c1c7  lea     rcx, [rbp+0A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c1cb  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c1d1  mov     rcx, qword ptr [rbp+0A0h+var_D0.Data1]
0x18001c1d5  mov     qword ptr [rbp-10h], 1
0x18001c1dd  cmp     rcx, qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime]
0x18001c1e1  jbe     short loc_18001C206
0x18001c1e3  sub     rcx, qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime]
0x18001c1e7  mov     rax, 346DC5D63886594Bh
0x18001c1f1  mul     rcx
0x18001c1f4  mov     eax, 0FFFFFFFFh
0x18001c1f9  shr     rdx, 0Bh
0x18001c1fd  cmp     rdx, rax
0x18001c200  cmova   edx, eax
0x18001c203  mov     dword ptr [rbp+0A0h+var_AC], edx
0x18001c206  cmp     [rsp+1A0h+var_138], r12d
0x18001c20b  jz      short loc_18001C232
0x18001c20d  movaps  xmm0, xmmword ptr [rsi]
0x18001c210  lea     rdx, [rbp+0A0h+var_D0]; struct _GUID
0x18001c214  mov     rax, [rbp+0A0h+var_98]
0x18001c218  mov     rcx, r15; this
0x18001c21b  mov     r9, [rbp+0A0h+var_AC+0Ch]; unsigned __int16 **
0x18001c21f  mov     r8d, dword ptr [rbp+0A0h+var_AC+4]; unsigned int
0x18001c223  movdqa  xmmword ptr [rbp+0A0h+var_D0.Data1], xmm0
0x18001c228  mov     [rsp+1A0h+phkResult], rax; unsigned __int16 **
0x18001c22d  call    ?_UpdateClientVolumes@CSpp@@AEAAJU_GUID@@KPEBQEBG1@Z; CSpp::_UpdateClientVolumes(_GUID,ulong,ushort const * const *,ushort const * const *)
0x18001c232  movups  xmm0, [rbp+0A0h+var_C0]
0x18001c236  movups  xmm1, xmmword ptr [rbp-10h]
0x18001c23a  movups  xmmword ptr [rbx], xmm0
0x18001c23d  movups  xmm0, xmmword ptr [rbp+0A0h+var_AC+0Ch]
0x18001c241  movups  xmmword ptr [rbx+10h], xmm1
0x18001c245  xorps   xmm1, xmm1
0x18001c248  movups  xmmword ptr [rbx+20h], xmm0
0x18001c24c  movups  [rbp+0A0h+var_C0], xmm1
0x18001c250  movups  xmmword ptr [rbp-10h], xmm1
0x18001c254  movups  xmmword ptr [rbp+0A0h+var_AC+0Ch], xmm1
0x18001c258  mov     rcx, rdi; pv
0x18001c25b  call    cs:__imp_CoTaskMemFree
0x18001c261  lea     rcx, [rbp+0A0h+var_C0]; struct _SPP_CLIENT_PROP *
0x18001c265  call    ?Free_SPP_CLIENT_PROP@@YAXPEAU_SPP_CLIENT_PROP@@@Z; Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *)
0x18001c26a  mov     ebx, [rsp+1A0h+var_130]
0x18001c26e  lea     rcx, [rbp+0A0h+lpSubKey]; this
0x18001c272  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001c277  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18001c27c  lea     rdx, [rcx-1]
0x18001c280  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001c284  ja      short loc_18001C291
0x18001c286  call    cs:__imp_RegCloseKey
0x18001c28c  mov     [rsp+1A0h+hKey], r12
0x18001c291  lea     rcx, [rsp+1A0h+var_130]; this
0x18001c296  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001c29b  mov     eax, ebx
0x18001c29d  mov     rcx, [rbp+0A0h+var_40]
0x18001c2a1  xor     rcx, rsp; StackCookie
0x18001c2a4  call    __security_check_cookie
0x18001c2a9  add     rsp, 170h
0x18001c2b0  pop     r15
0x18001c2b2  pop     r14
0x18001c2b4  pop     r12
0x18001c2b6  pop     rdi
0x18001c2b7  pop     rsi
0x18001c2b8  pop     rbx
0x18001c2b9  pop     rbp
0x18001c2ba  retn
0x18001c2bb  xor     r9d, r9d; unsigned __int16 *
0x18001c2be  lea     r8, aLeases; "Leases"
0x18001c2c5  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001c2cc  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001c2d1  mov     [rsp+1A0h+var_130], eax
0x18001c2d5  test    eax, eax
0x18001c2d7  mov     eax, 0CA7h
0x18001c2dc  jmp     loc_18001C164
```
