# GetApplicationPhysicalPath(INativeConfigurationElement *,STRU *)

- ea: `0x180011d44`
- end: `0x180011f6a`
- name: `?GetApplicationPhysicalPath@@YAJPEAVINativeConfigurationElement@@PEAVSTRU@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(struct INativeConfigurationElement *, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800108c0`

## callees

- `0x180011d44`
- `0x1800160a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180011e78`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180011ecc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180011e78`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180011ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e82`
- `iisutil!PuDbgPrintError` at `0x180011de0`
- `iisutil!PuDbgPrintError` at `0x180011de0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011ebc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011eef`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011ebc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011eef`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180011f41`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180011f41`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180011d79`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180011d79`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180011eae`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180011ed8`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180011eae`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180011ed8`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180011ea0`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180011ea0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011efb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011efb`

## string_xrefs

- `0x180011dd5`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180011db5`: ` Failed to get virtual directory collection \n`
- `0x180011dc9`: `GetApplicationPhysicalPath`
- `0x180011e14`: ` Failed to get an virtual directory element \n`
- `0x180011e37`: `physicalPath`
- `0x180011e5d`: ` Failed to get the physical path of virtual directory\n`

## pseudocode

```c
__int64 __fastcall GetApplicationPhysicalPath(struct INativeConfigurationElement *a1, struct STRU *a2)
{
  __int64 v4; // rax
  signed int v5; // ebx
  DWORD v6; // eax
  signed int LastError; // eax
  DWORD v8; // ebx
  WCHAR *Ptr; // rax
  DWORD v10; // ebx
  const unsigned __int16 *v11; // rax
  __int64 v13; // [rsp+30h] [rbp-50h] BYREF
  __int64 v14; // [rsp+38h] [rbp-48h] BYREF
  LPCWSTR lpSrc; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v16[48]; // [rsp+48h] [rbp-38h] BYREF

  lpSrc = 0;
  BUFFER::BUFFER((BUFFER *)v16);
  v4 = *(_QWORD *)a1;
  v13 = 0;
  v14 = 0;
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(v4 + 40))(a1, &v14);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 32LL))(v14, 0, &v13);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
             v13,
             L"physicalPath",
             &lpSrc,
             0,
             0);
      if ( v5 >= 0 )
      {
        v6 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
        if ( v6 && BUFFER::Resize((BUFFER *)v16, 2 * v6) )
        {
          v8 = BUFFER::QuerySize((BUFFER *)v16) >> 1;
          Ptr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v16);
          v10 = ExpandEnvironmentStringsW(lpSrc, Ptr, v8);
          if ( v10 <= BUFFER::QuerySize((BUFFER *)v16) >> 1 )
          {
            v11 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v16);
            v5 = STRU::Copy(a2, v11);
          }
          else
          {
            v5 = -2147418113;
          }
        }
        else
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
          1589,
          "GetApplicationPhysicalPath",
          v5,
          " Failed to get the physical path of virtual directory\n");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
        1575,
        "GetApplicationPhysicalPath",
        v5,
        " Failed to get an virtual directory element \n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
      1563,
      "GetApplicationPhysicalPath",
      v5,
      " Failed to get virtual directory collection \n");
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011d44  mov     [rsp-8+arg_10], rbx
0x180011d49  mov     [rsp-8+arg_18], rdi
0x180011d4e  push    rbp
0x180011d4f  mov     rbp, rsp
0x180011d52  sub     rsp, 80h
0x180011d59  mov     rax, cs:__security_cookie
0x180011d60  xor     rax, rsp
0x180011d63  mov     [rbp+var_8], rax
0x180011d67  mov     rbx, rcx
0x180011d6a  mov     [rbp+lpSrc], 0
0x180011d72  lea     rcx, [rbp+var_38]
0x180011d76  mov     rdi, rdx
0x180011d79  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180011d7f  mov     rax, [rbx]
0x180011d82  lea     rdx, [rbp+var_48]
0x180011d86  mov     rcx, rbx
0x180011d89  mov     [rbp+var_50], 0
0x180011d91  mov     [rbp+var_48], 0
0x180011d99  mov     rax, [rax+28h]
0x180011d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011da2  mov     ebx, eax
0x180011da4  test    eax, eax
0x180011da6  jns     short loc_180011DEB
0x180011da8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180011daf  jz      loc_180011F03
0x180011db5  lea     rax, aFailedToGetVir; " Failed to get virtual directory collec"...
0x180011dbc  mov     r8d, 61Bh
0x180011dc2  mov     rcx, cs:g_pDebug
0x180011dc9  lea     r9, aGetapplication; "GetApplicationPhysicalPath"
0x180011dd0  mov     [rsp+80h+var_58], rax
0x180011dd5  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180011ddc  mov     dword ptr [rsp+80h+var_60], ebx
0x180011de0  call    cs:__imp_PuDbgPrintError
0x180011de6  jmp     loc_180011F03
0x180011deb  mov     rcx, [rbp+var_48]
0x180011def  lea     r8, [rbp+var_50]
0x180011df3  xor     edx, edx
0x180011df5  mov     rax, [rcx]
0x180011df8  mov     rax, [rax+20h]
0x180011dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e01  mov     ebx, eax
0x180011e03  test    eax, eax
0x180011e05  jns     short loc_180011E23
0x180011e07  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180011e0e  jz      loc_180011F03
0x180011e14  lea     rax, aFailedToGetAnV; " Failed to get an virtual directory ele"...
0x180011e1b  mov     r8d, 627h
0x180011e21  jmp     short loc_180011DC2
0x180011e23  mov     rcx, [rbp+var_50]
0x180011e27  lea     r8, [rbp+lpSrc]
0x180011e2b  xor     r9d, r9d
0x180011e2e  mov     [rsp+80h+var_60], 0
0x180011e37  lea     rdx, aPhysicalpath; "physicalPath"
0x180011e3e  mov     rax, [rcx]
0x180011e41  mov     rax, [rax+40h]
0x180011e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e4a  mov     ebx, eax
0x180011e4c  test    eax, eax
0x180011e4e  jns     short loc_180011E6F
0x180011e50  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180011e57  jz      loc_180011F03
0x180011e5d  lea     rax, aFailedToGetThe_0; " Failed to get the physical path of vir"...
0x180011e64  mov     r8d, 635h
0x180011e6a  jmp     loc_180011DC2
0x180011e6f  mov     rcx, [rbp+lpSrc]; lpSrc
0x180011e73  xor     r8d, r8d; nSize
0x180011e76  xor     edx, edx; lpDst
0x180011e78  call    cs:__imp_ExpandEnvironmentStringsW
0x180011e7e  test    eax, eax
0x180011e80  jnz     short loc_180011E99
0x180011e82  call    cs:__imp_GetLastError
0x180011e88  mov     ebx, eax
0x180011e8a  test    eax, eax
0x180011e8c  jle     short loc_180011F03
0x180011e8e  movzx   ebx, ax
0x180011e91  or      ebx, 80070000h
0x180011e97  jmp     short loc_180011F03
0x180011e99  lea     edx, [rax+rax]
0x180011e9c  lea     rcx, [rbp+var_38]
0x180011ea0  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180011ea6  test    al, al
0x180011ea8  jz      short loc_180011E82
0x180011eaa  lea     rcx, [rbp+var_38]
0x180011eae  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180011eb4  mov     ebx, eax
0x180011eb6  lea     rcx, [rbp+var_38]
0x180011eba  shr     ebx, 1
0x180011ebc  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180011ec2  mov     rcx, [rbp+lpSrc]; lpSrc
0x180011ec6  mov     r8d, ebx; nSize
0x180011ec9  mov     rdx, rax; lpDst
0x180011ecc  call    cs:__imp_ExpandEnvironmentStringsW
0x180011ed2  lea     rcx, [rbp+var_38]
0x180011ed6  mov     ebx, eax
0x180011ed8  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180011ede  shr     eax, 1
0x180011ee0  cmp     ebx, eax
0x180011ee2  jbe     short loc_180011EEB
0x180011ee4  mov     ebx, 8000FFFFh
0x180011ee9  jmp     short loc_180011F03
0x180011eeb  lea     rcx, [rbp+var_38]
0x180011eef  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180011ef5  mov     rdx, rax
0x180011ef8  mov     rcx, rdi
0x180011efb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180011f01  mov     ebx, eax
0x180011f03  mov     rcx, [rbp+var_50]
0x180011f07  test    rcx, rcx
0x180011f0a  jz      short loc_180011F20
0x180011f0c  mov     rax, [rcx]
0x180011f0f  mov     rax, [rax+10h]
0x180011f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f18  mov     [rbp+var_50], 0
0x180011f20  mov     rcx, [rbp+var_48]
0x180011f24  test    rcx, rcx
0x180011f27  jz      short loc_180011F3D
0x180011f29  mov     rax, [rcx]
0x180011f2c  mov     rax, [rax+10h]
0x180011f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f35  mov     [rbp+var_48], 0
0x180011f3d  lea     rcx, [rbp+var_38]
0x180011f41  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180011f47  mov     eax, ebx
0x180011f49  mov     rcx, [rbp+var_8]
0x180011f4d  xor     rcx, rsp; StackCookie
0x180011f50  call    __security_check_cookie
0x180011f55  lea     r11, [rsp+80h+var_s0]
0x180011f5d  mov     rbx, [r11+20h]
0x180011f61  mov     rdi, [r11+28h]
0x180011f65  mov     rsp, r11
0x180011f68  pop     rbp
0x180011f69  retn
```
