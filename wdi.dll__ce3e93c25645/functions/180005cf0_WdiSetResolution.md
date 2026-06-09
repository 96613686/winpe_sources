# WdiSetResolution

- ea: `0x180005cf0`
- end: `0x180005f96`
- name: `WdiSetResolution`
- size: `678`
- prototype: `__int64 __fastcall(__int64, _QWORD *, void *, int, int, FILETIME FileTime1)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002ba0`
- `0x180005cf0`
- `0x180006e40`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x180005ee0`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180005ee0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005e2e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005e2e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180005e85`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180005e85`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180005f05`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180005f05`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005eaa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005e18`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005e18`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180005e68`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180005e68`

## pseudocode

```c
__int64 __fastcall WdiSetResolution(__int64 a1, _QWORD *a2, void *a3, int a4, int a5, FILETIME FileTime1)
{
  int v10; // r8d
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // esi
  unsigned int v14; // ebx
  int v15; // eax
  _QWORD *SessionFromId; // rcx
  DWORD LengthSid; // ebx
  int v19; // ebp
  unsigned __int64 v20; // r14
  signed int LastError; // eax
  int Args; // [rsp+20h] [rbp-58h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  if ( !a1 )
  {
    v10 = 1113;
LABEL_3:
    v11 = -2147024809;
    Args = 87;
LABEL_4:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (__int64)L"WdiSetResolution",
      v10,
      (const wchar_t *)L"Error = %d",
      Args);
    return v11;
  }
  v12 = *(_QWORD *)(a1 + 40);
  if ( !v12 )
  {
    v10 = 1114;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v10 = 1115;
    goto LABEL_3;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 16) - 1) <= 1 )
    return (unsigned int)-2147020579;
  v13 = a5;
  v14 = a5 & 0xF;
  if ( v14 > 8 )
    return (unsigned int)-2147024809;
  v15 = 279;
  if ( !_bittest(&v15, v14) )
    return (unsigned int)-2147024809;
  if ( *(_DWORD *)(v12 + 44) != 4 )
    return (unsigned int)-2147020579;
  SessionFromId = WdipGetSessionFromId(a2);
  if ( !SessionFromId )
    return (unsigned int)-2147024809;
  if ( v14 == 2 && *(_DWORD *)(*(_QWORD *)(a1 + 40) + 116LL) == 1 )
    return (unsigned int)-2147020579;
  if ( (v13 & 0x10) != 0 )
  {
    if ( !v14 )
      return (unsigned int)-2147020579;
  }
  else if ( (v13 & 8) == 0 && v14 != 4 )
  {
    if ( (v13 & 0x20) != 0 )
      return (unsigned int)-2147020579;
    goto LABEL_29;
  }
  if ( (SessionFromId[10] & 1) == 0 || (*(_BYTE *)(*(_QWORD *)(a1 + 40) + 120LL) & 1) == 0 )
    return (unsigned int)-2147020579;
  if ( (v13 & 0x20) != 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) > 0 )
    {
      SessionFromId = *(_QWORD **)(a1 + 40);
      *(FILETIME *)((char *)SessionFromId + 148) = FileTime1;
      goto LABEL_29;
    }
    return (unsigned int)-2147024809;
  }
LABEL_29:
  if ( v14 == 1 )
  {
    if ( !a3 )
    {
      v10 = 1224;
      goto LABEL_3;
    }
    if ( a4 == (unsigned int)WTSGetServiceSessionId(SessionFromId) && (v13 & 0x10) == 0 )
    {
      v10 = 1230;
      goto LABEL_3;
    }
    if ( !IsValidSid(a3) )
    {
      v11 = -2147467259;
      Args = 16389;
      v10 = 1235;
      goto LABEL_4;
    }
    LengthSid = GetLengthSid(a3);
    v19 = 208;
    if ( LengthSid + 208 < 0xD0 )
    {
      v11 = -2147024362;
      Args = 534;
      v10 = 1247;
      goto LABEL_4;
    }
    v20 = (LengthSid + 215) & 0xFFFFFFF8;
    if ( v20 >= AlpcMaxAllowedMessageLength() )
      return (unsigned int)-2147467259;
    if ( CopySid(LengthSid, (PSID)(*(_QWORD *)(a1 + 40) + 248LL), a3) )
    {
      v11 = 0;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (v11 & 0x80000000) != 0 )
      {
        v10 = 1263;
        Args = (unsigned __int16)v11;
        goto LABEL_4;
      }
    }
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 156LL) = a4;
  }
  else
  {
    v11 = 0;
    LODWORD(v20) = 248;
    v19 = 0;
  }
  *(_DWORD *)(*(_QWORD *)(a1 + 40) + 160LL) = v19;
  *(_DWORD *)(*(_QWORD *)(a1 + 40) + 124LL) = v20;
  *(_DWORD *)(*(_QWORD *)(a1 + 40) + 144LL) = v13;
  if ( *(_QWORD *)(a1 + 40) != -128 )
    *(_OWORD *)(*(_QWORD *)(a1 + 40) + 128LL) = *(_OWORD *)a2;
  return v11;
}

```

## disassembly

```asm
0x180005cf0  push    rbx
0x180005cf2  push    rbp
0x180005cf3  push    rsi
0x180005cf4  push    rdi
0x180005cf5  push    r12
0x180005cf7  push    r13
0x180005cf9  push    r14
0x180005cfb  push    r15
0x180005cfd  sub     rsp, 38h
0x180005d01  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180005d0d  mov     r13d, r9d
0x180005d10  mov     r15, r8
0x180005d13  mov     r12, rdx
0x180005d16  mov     rdi, rcx
0x180005d19  test    rcx, rcx
0x180005d1c  jnz     short loc_180005D50
0x180005d1e  mov     r8d, 459h; int
0x180005d24  mov     ebx, 80070057h
0x180005d29  mov     dword ptr [rsp+78h+Args], 57h ; 'W'; Args
0x180005d31  lea     r9, aErrorD_0; "Error = %d"
0x180005d38  lea     rdx, aWdisetresoluti_0; "WdiSetResolution"
0x180005d3f  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180005d46  call    WdipTraceError
0x180005d4b  jmp     loc_180005DD4
0x180005d50  mov     rcx, [rcx+28h]
0x180005d54  test    rcx, rcx
0x180005d57  jnz     short loc_180005D61
0x180005d59  mov     r8d, 45Ah
0x180005d5f  jmp     short loc_180005D24
0x180005d61  test    r12, r12
0x180005d64  jnz     short loc_180005D6E
0x180005d66  mov     r8d, 45Bh
0x180005d6c  jmp     short loc_180005D24
0x180005d6e  mov     eax, [rdi+10h]
0x180005d71  dec     eax
0x180005d73  cmp     eax, 1
0x180005d76  jbe     short loc_180005DCF
0x180005d78  mov     esi, [rsp+78h+arg_20]
0x180005d7f  mov     ebx, esi
0x180005d81  and     ebx, 0Fh
0x180005d84  cmp     ebx, 8
0x180005d87  ja      loc_180005F8C
0x180005d8d  mov     eax, 117h
0x180005d92  bt      eax, ebx
0x180005d95  jnb     loc_180005F8C
0x180005d9b  cmp     dword ptr [rcx+2Ch], 4
0x180005d9f  jnz     short loc_180005DCF
0x180005da1  mov     rcx, r12
0x180005da4  call    WdipGetSessionFromId
0x180005da9  mov     rcx, rax
0x180005dac  test    rax, rax
0x180005daf  jz      loc_180005F8C
0x180005db5  cmp     ebx, 2
0x180005db8  jnz     short loc_180005DC4
0x180005dba  mov     rax, [rdi+28h]
0x180005dbe  cmp     dword ptr [rax+74h], 1
0x180005dc2  jz      short loc_180005DCF
0x180005dc4  mov     ebp, esi
0x180005dc6  and     ebp, 10h
0x180005dc9  jz      short loc_180005DE7
0x180005dcb  test    ebx, ebx
0x180005dcd  jnz     short loc_180005DFA
0x180005dcf  mov     ebx, 800710DDh
0x180005dd4  mov     eax, ebx
0x180005dd6  add     rsp, 38h
0x180005dda  pop     r15
0x180005ddc  pop     r14
0x180005dde  pop     r13
0x180005de0  pop     r12
0x180005de2  pop     rdi
0x180005de3  pop     rsi
0x180005de4  pop     rbp
0x180005de5  pop     rbx
0x180005de6  retn
0x180005de7  test    sil, 8
0x180005deb  jnz     short loc_180005DFA
0x180005ded  cmp     ebx, 4
0x180005df0  jz      short loc_180005DFA
0x180005df2  test    sil, 20h
0x180005df6  jz      short loc_180005E4F
0x180005df8  jmp     short loc_180005DCF
0x180005dfa  test    byte ptr [rcx+50h], 1
0x180005dfe  jz      short loc_180005DCF
0x180005e00  mov     rax, [rdi+28h]
0x180005e04  test    byte ptr [rax+78h], 1
0x180005e08  jz      short loc_180005DCF
0x180005e0a  test    sil, 20h
0x180005e0e  jz      short loc_180005E4F
0x180005e10  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005e18  call    cs:__imp_GetSystemTimeAsFileTime
0x180005e1e  lea     rdx, [rsp+78h+SystemTimeAsFileTime]; lpFileTime2
0x180005e26  lea     rcx, [rsp+78h+FileTime1]; lpFileTime1
0x180005e2e  call    cs:__imp_CompareFileTime
0x180005e34  test    eax, eax
0x180005e36  jle     loc_180005F8C
0x180005e3c  mov     rcx, [rdi+28h]
0x180005e40  mov     rax, qword ptr [rsp+78h+FileTime1.dwLowDateTime]
0x180005e48  mov     [rcx+94h], rax
0x180005e4f  cmp     ebx, 1
0x180005e52  jnz     loc_180005F49
0x180005e58  test    r15, r15
0x180005e5b  jnz     short loc_180005E68
0x180005e5d  mov     r8d, 4C8h
0x180005e63  jmp     loc_180005D24
0x180005e68  call    cs:__imp_WTSGetServiceSessionId
0x180005e6e  cmp     r13d, eax
0x180005e71  jnz     short loc_180005E82
0x180005e73  test    ebp, ebp
0x180005e75  jnz     short loc_180005E82
0x180005e77  mov     r8d, 4CEh
0x180005e7d  jmp     loc_180005D24
0x180005e82  mov     rcx, r15; pSid
0x180005e85  call    cs:__imp_IsValidSid
0x180005e8b  test    eax, eax
0x180005e8d  jnz     short loc_180005EA7
0x180005e8f  mov     ebx, 80004005h
0x180005e94  mov     dword ptr [rsp+78h+Args], 4005h
0x180005e9c  mov     r8d, 4D3h
0x180005ea2  jmp     loc_180005D31
0x180005ea7  mov     rcx, r15; pSid
0x180005eaa  call    cs:__imp_GetLengthSid
0x180005eb0  mov     ebx, eax
0x180005eb2  mov     ebp, 0D0h
0x180005eb7  add     eax, 0D0h
0x180005ebc  cmp     eax, ebp
0x180005ebe  jnb     short loc_180005ED8
0x180005ec0  mov     ebx, 80070216h
0x180005ec5  mov     dword ptr [rsp+78h+Args], 216h
0x180005ecd  mov     r8d, 4DFh
0x180005ed3  jmp     loc_180005D31
0x180005ed8  lea     r14d, [rax+7]
0x180005edc  and     r14d, 0FFFFFFF8h
0x180005ee0  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180005ee6  cmp     r14, rax
0x180005ee9  jb      short loc_180005EF5
0x180005eeb  mov     ebx, 80004005h
0x180005ef0  jmp     loc_180005DD4
0x180005ef5  mov     rdx, [rdi+28h]
0x180005ef9  mov     r8, r15; pSourceSid
0x180005efc  add     rdx, 0F8h; pDestinationSid
0x180005f03  mov     ecx, ebx; nDestinationSidLength
0x180005f05  call    cs:__imp_CopySid
0x180005f0b  test    eax, eax
0x180005f0d  jz      short loc_180005F1E
0x180005f0f  xor     ebx, ebx
0x180005f11  mov     rax, [rdi+28h]
0x180005f15  mov     [rax+9Ch], r13d
0x180005f1c  jmp     short loc_180005F53
0x180005f1e  call    cs:__imp_GetLastError
0x180005f24  mov     ebx, eax
0x180005f26  test    eax, eax
0x180005f28  jle     short loc_180005F33
0x180005f2a  movzx   ebx, ax
0x180005f2d  or      ebx, 80070000h
0x180005f33  test    ebx, ebx
0x180005f35  jns     short loc_180005F11
0x180005f37  movzx   eax, bx
0x180005f3a  mov     r8d, 4EFh
0x180005f40  mov     dword ptr [rsp+78h+Args], eax
0x180005f44  jmp     loc_180005D31
0x180005f49  xor     ebx, ebx
0x180005f4b  mov     r14d, 0F8h
0x180005f51  xor     ebp, ebp
0x180005f53  mov     rax, [rdi+28h]
0x180005f57  mov     [rax+0A0h], ebp
0x180005f5d  mov     rax, [rdi+28h]
0x180005f61  mov     [rax+7Ch], r14d
0x180005f65  mov     rax, [rdi+28h]
0x180005f69  mov     [rax+90h], esi
0x180005f6f  mov     rax, [rdi+28h]
0x180005f73  add     rax, 80h
0x180005f79  jz      loc_180005DD4
0x180005f7f  movups  xmm0, xmmword ptr [r12]
0x180005f84  movups  xmmword ptr [rax], xmm0
0x180005f87  jmp     loc_180005DD4
0x180005f8c  mov     ebx, 80070057h
0x180005f91  jmp     loc_180005DD4
```
