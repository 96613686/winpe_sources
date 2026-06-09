# UtilLaunchNonElevatedProcess(NON_ELEVATED_PROC_DATA *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18000b334`
- end: `0x18000b5d6`
- name: `?UtilLaunchNonElevatedProcess@@YAJPEAUNON_ELEVATED_PROC_DATA@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `674`
- prototype: `__int64 __fastcall(const void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b82c`

## callees

- `0x180005ddc`
- `0x18000983c`
- `0x180009a30`
- `0x180009b10`
- `0x180009c80`
- `0x180009d14`
- `0x18000af9c`
- `0x18000b334`
- `0x18000bb20`
- `0x180016c06`
- `0x180016c1e`
- `0x180016c50`
- `0x180016d10`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18000b4a5`
- `KERNEL32!MapViewOfFile` at `0x18000b4a5`
- `KERNEL32!CreateFileMappingW` at `0x18000b452`
- `KERNEL32!CreateFileMappingW` at `0x18000b452`
- `KERNEL32!GetLastError` at `0x18000b474`
- `KERNEL32!GetLastError` at `0x18000b474`
- `ntdll!RtlNtStatusToDosError` at `0x18000b53d`
- `ntdll!RtlNtStatusToDosError` at `0x18000b53d`

## pseudocode

```c
__int64 __fastcall UtilLaunchNonElevatedProcess(const void *a1)
{
  int v2; // ebx
  PCWSTR v3; // rax
  HANDLE FileMappingW; // rax
  unsigned int v5; // edi
  signed int LastError; // eax
  void *v7; // rbx
  unsigned int v8; // r9d
  const WCHAR *v9; // rcx
  NTSTATUS v10; // eax
  signed int v11; // eax
  HANDLE hFileMappingObject; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[8]; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR SourceString; // [rsp+58h] [rbp-A8h]
  const WCHAR *v18; // [rsp+B0h] [rbp-50h]
  _BYTE Src[1568]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v20; // [rsp+6E0h] [rbp+5E0h] BYREF
  _BYTE v21[38]; // [rsp+6E2h] [rbp+5E2h] BYREF
  int v22; // [rsp+708h] [rbp+608h]
  int v23; // [rsp+70Ch] [rbp+60Ch]
  __int64 v24; // [rsp+718h] [rbp+618h]
  _DWORD v25[12]; // [rsp+C60h] [rbp+B60h] BYREF
  __int64 v26; // [rsp+C90h] [rbp+B90h]

  LOWORD(v25[0]) = 0;
  memset_0((char *)v25 + 2, 0, 0x576u);
  v20 = 0;
  memset_0(v21, 0, 0x576u);
  hFileMappingObject = 0;
  v14 = 0;
  CRegSetting::CRegSetting((CRegSetting *)v16);
  v2 = CRegSetting::Initialize(v16, 1, L"Software\\Microsoft\\Windows\\Windows Error Reporting", L"ErrorPort", 0);
  if ( v2 >= 0 )
  {
    v2 = CRegSetting::Load((CRegSetting *)v16, HKEY_LOCAL_MACHINE, 0x100u);
    if ( v2 >= 0 )
    {
      v3 = v18;
      if ( v16[0] )
        v3 = SourceString;
      if ( v3 )
      {
        if ( a1 )
        {
          FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x620u, 0);
          tlx::unique_any<tlx::file_handle_traits>::reset(&hFileMappingObject, FileMappingW);
          v5 = (unsigned int)hFileMappingObject;
          if ( (unsigned __int64)hFileMappingObject + 1 > 1
            && (v14 = MapViewOfFile(hFileMappingObject, 0x120116u, 0, 0, 0x620u), (v7 = v14) != 0) )
          {
            memcpy_0(Src, a1, sizeof(Src));
            memcpy_0(v7, Src, 0x620u);
            memset_0(Src, 0, 0x578u);
            memcpy_0(v25, Src, 0x578u);
            v9 = v18;
            if ( v16[0] )
              v9 = SourceString;
            v25[0] = 91751760;
            v25[10] = -1879048192;
            v26 = v5;
            v10 = WersvcSendMessage(v9, (struct _WERSVC_MSG *)v25, (struct _WERSVC_MSG *)&v20, v8);
            v11 = RtlNtStatusToDosError(v10);
            v2 = v11;
            if ( v11 > 0 )
              v2 = (unsigned __int16)v11 | 0x80070000;
            if ( v2 >= 0 )
            {
              if ( v22 == -1879048191 )
              {
                v15 = v24;
                tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v15);
                v2 = 0;
              }
              else if ( v22 == -1879048190 )
              {
                v2 = v23 | 0x10000000;
              }
              else
              {
                v2 = -2147467259;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v2 = LastError;
            if ( LastError > 0 )
              v2 = (unsigned __int16)LastError | 0x80070000;
          }
        }
        else
        {
          v2 = -2147024809;
        }
      }
    }
  }
  CRegSetting::~CRegSetting((CRegSetting *)v16);
  tlx::unique_any<tlx::handle_traits<NON_ELEVATED_PROC_DATA *,int (*)(void const *),&int UnmapViewOfFile(void const *),0>>::~unique_any<tlx::handle_traits<NON_ELEVATED_PROC_DATA *,int (*)(void const *),&int UnmapViewOfFile(void const *),0>>(&v14);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFileMappingObject);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b334  push    rbp
0x18000b336  push    rbx
0x18000b337  push    rsi
0x18000b338  push    rdi
0x18000b339  push    r15
0x18000b33b  lea     rbp, [rsp-10F0h]
0x18000b343  mov     eax, 11F0h
0x18000b348  call    _alloca_probe
0x18000b34d  sub     rsp, rax
0x18000b350  mov     rax, cs:__security_cookie
0x18000b357  xor     rax, rsp
0x18000b35a  mov     [rbp+1110h+var_30], rax
0x18000b361  mov     rsi, rcx
0x18000b364  xor     eax, eax
0x18000b366  mov     ebx, 576h
0x18000b36b  mov     word ptr [rbp+1110h+var_5B0], ax
0x18000b372  mov     r8d, ebx; Size
0x18000b375  lea     rcx, [rbp+1110h+var_5B0+2]; void *
0x18000b37c  xor     edx, edx; Val
0x18000b37e  call    memset_0
0x18000b383  xor     eax, eax
0x18000b385  lea     rcx, [rbp+1110h+var_B2E]; void *
0x18000b38c  mov     r8d, ebx; Size
0x18000b38f  mov     [rbp+1110h+var_B30], ax
0x18000b396  xor     edx, edx; Val
0x18000b398  call    memset_0
0x18000b39d  lea     rcx, [rsp+1210h+var_11C0]; this
0x18000b3a2  mov     [rsp+1210h+hFileMappingObject], 0
0x18000b3ab  mov     [rsp+1210h+var_11D8], 0
0x18000b3b4  call    ??0CRegSetting@@QEAA@XZ; CRegSetting::CRegSetting(void)
0x18000b3b9  lea     r9, aErrorport; "ErrorPort"
0x18000b3c0  mov     qword ptr [rsp+1210h+dwMaximumSizeLow], 0
0x18000b3c9  lea     r8, SubKey; "Software\\Microsoft\\Windows\\Windows E"...
0x18000b3d0  mov     edx, 1
0x18000b3d5  lea     rcx, [rsp+1210h+var_11C0]
0x18000b3da  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEBG1_K@Z; CRegSetting::Initialize(_DataType,ushort const *,ushort const *,unsigned __int64)
0x18000b3df  mov     ebx, eax
0x18000b3e1  test    eax, eax
0x18000b3e3  js      loc_18000B599
0x18000b3e9  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000b3f0  lea     rcx, [rsp+1210h+var_11C0]; this
0x18000b3f5  mov     r8d, 100h; unsigned int
0x18000b3fb  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x18000b400  mov     ebx, eax
0x18000b402  test    eax, eax
0x18000b404  js      loc_18000B599
0x18000b40a  cmp     [rsp+1210h+var_11C0], 0
0x18000b40f  mov     rax, [rbp+1110h+var_1160]
0x18000b413  cmovnz  rax, [rsp+1210h+SourceString]
0x18000b419  test    rax, rax
0x18000b41c  jz      loc_18000B599
0x18000b422  test    rsi, rsi
0x18000b425  jnz     short loc_18000B431
0x18000b427  mov     ebx, 80070057h
0x18000b42c  jmp     loc_18000B599
0x18000b431  xor     r9d, r9d; dwMaximumSizeHigh
0x18000b434  mov     [rsp+1210h+lpName], 0; lpName
0x18000b43d  mov     r15d, 620h
0x18000b443  xor     edx, edx; lpFileMappingAttributes
0x18000b445  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000b449  mov     [rsp+1210h+dwMaximumSizeLow], r15d; dwMaximumSizeLow
0x18000b44e  lea     r8d, [r9+4]; flProtect
0x18000b452  call    cs:__imp_CreateFileMappingW
0x18000b458  mov     rdx, rax
0x18000b45b  lea     rcx, [rsp+1210h+hFileMappingObject]
0x18000b460  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18000b465  mov     rdi, [rsp+1210h+hFileMappingObject]
0x18000b46a  lea     rax, [rdi+1]
0x18000b46e  cmp     rax, 1
0x18000b472  ja      short loc_18000B492
0x18000b474  call    cs:__imp_GetLastError
0x18000b47a  mov     ebx, eax
0x18000b47c  test    eax, eax
0x18000b47e  jle     loc_18000B599
0x18000b484  movzx   ebx, ax
0x18000b487  or      ebx, 80070000h
0x18000b48d  jmp     loc_18000B599
0x18000b492  xor     r9d, r9d; dwFileOffsetLow
0x18000b495  mov     qword ptr [rsp+1210h+dwMaximumSizeLow], r15; dwNumberOfBytesToMap
0x18000b49a  xor     r8d, r8d; dwFileOffsetHigh
0x18000b49d  mov     edx, 120116h; dwDesiredAccess
0x18000b4a2  mov     rcx, rdi; hFileMappingObject
0x18000b4a5  call    cs:__imp_MapViewOfFile
0x18000b4ab  mov     [rsp+1210h+var_11D8], rax
0x18000b4b0  mov     rbx, rax
0x18000b4b3  test    rax, rax
0x18000b4b6  jz      short loc_18000B474
0x18000b4b8  lea     rcx, [rbp+1110h+Src]; void *
0x18000b4bc  mov     rdx, rsi; Src
0x18000b4bf  mov     r8, r15; Size
0x18000b4c2  call    memcpy_0
0x18000b4c7  mov     rcx, rbx; void *
0x18000b4ca  lea     rdx, [rbp+1110h+Src]; Src
0x18000b4ce  mov     r8, r15; Size
0x18000b4d1  call    memcpy_0
0x18000b4d6  mov     ebx, 578h
0x18000b4db  lea     rcx, [rbp+1110h+Src]; void *
0x18000b4df  mov     r8d, ebx; Size
0x18000b4e2  xor     edx, edx; Val
0x18000b4e4  call    memset_0
0x18000b4e9  lea     rcx, [rbp+1110h+var_5B0]; void *
0x18000b4f0  mov     r8d, ebx; Size
0x18000b4f3  lea     rdx, [rbp+1110h+Src]; Src
0x18000b4f7  call    memcpy_0
0x18000b4fc  cmp     [rsp+1210h+var_11C0], 0
0x18000b501  lea     r8, [rbp+1110h+var_B30]; struct _WERSVC_MSG *
0x18000b508  mov     rcx, [rbp+1110h+var_1160]
0x18000b50c  lea     rdx, [rbp+1110h+var_5B0]; struct _WERSVC_MSG *
0x18000b513  cmovnz  rcx, [rsp+1210h+SourceString]; SourceString
0x18000b519  mov     eax, edi
0x18000b51b  mov     [rbp+1110h+var_5B0], 5780550h
0x18000b525  mov     [rbp+1110h+var_588], 90000000h
0x18000b52f  mov     [rbp+1110h+var_580], rax
0x18000b536  call    ?WersvcSendMessage@@YAJPEBGPEAU_WERSVC_MSG@@1K@Z; WersvcSendMessage(ushort const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x18000b53b  mov     ecx, eax; Status
0x18000b53d  call    cs:__imp_RtlNtStatusToDosError
0x18000b543  mov     ebx, eax
0x18000b545  test    eax, eax
0x18000b547  jle     short loc_18000B552
0x18000b549  movzx   ebx, ax
0x18000b54c  or      ebx, 80070000h
0x18000b552  test    ebx, ebx
0x18000b554  js      short loc_18000B599
0x18000b556  cmp     [rbp+1110h+var_B08], 90000001h
0x18000b560  jz      short loc_18000B581
0x18000b562  cmp     [rbp+1110h+var_B08], 90000002h
0x18000b56c  jz      short loc_18000B575
0x18000b56e  mov     ebx, 80004005h
0x18000b573  jmp     short loc_18000B599
0x18000b575  mov     ebx, [rbp+1110h+var_B04]
0x18000b57b  bts     ebx, 1Ch
0x18000b57f  jmp     short loc_18000B599
0x18000b581  mov     rax, [rbp+1110h+var_AF8]
0x18000b588  lea     rcx, [rsp+1210h+var_11D0]
0x18000b58d  mov     [rsp+1210h+var_11D0], rax
0x18000b592  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18000b597  xor     ebx, ebx
0x18000b599  lea     rcx, [rsp+1210h+var_11C0]; this
0x18000b59e  call    ??1CRegSetting@@QEAA@XZ; CRegSetting::~CRegSetting(void)
0x18000b5a3  lea     rcx, [rsp+1210h+var_11D8]
0x18000b5a8  call    ??1?$unique_any@U?$handle_traits@PEAUNON_ELEVATED_PROC_DATA@@P6AHPEBX@Z$1?UnmapViewOfFile@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<NON_ELEVATED_PROC_DATA *,int (*)(void const *),&UnmapViewOfFile(void const *),0>>::~unique_any<tlx::handle_traits<NON_ELEVATED_PROC_DATA *,int (*)(void const *),&UnmapViewOfFile(void const *),0>>(void)
0x18000b5ad  lea     rcx, [rsp+1210h+hFileMappingObject]
0x18000b5b2  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18000b5b7  mov     eax, ebx
0x18000b5b9  mov     rcx, [rbp+1110h+var_30]
0x18000b5c0  xor     rcx, rsp; StackCookie
0x18000b5c3  call    __security_check_cookie
0x18000b5c8  add     rsp, 11F0h
0x18000b5cf  pop     r15
0x18000b5d1  pop     rdi
0x18000b5d2  pop     rsi
0x18000b5d3  pop     rbx
0x18000b5d4  pop     rbp
0x18000b5d5  retn
```
