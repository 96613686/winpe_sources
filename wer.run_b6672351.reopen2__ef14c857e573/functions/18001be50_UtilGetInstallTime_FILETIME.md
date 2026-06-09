# UtilGetInstallTime(_FILETIME *)

- ea: `0x18001be50`
- end: `0x18001c03d`
- name: `?UtilGetInstallTime@@YAJPEAU_FILETIME@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(LPFILETIME lpFileTime)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013838`
- `0x1800955c0`

## callees

- `0x18001be50`
- `0x18001c368`
- `0x180020680`
- `0x180040950`
- `0x180047c0c`
- `0x180053300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfe4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bef9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bef9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bebb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bebb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001bfd0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001bfd0`

## string_xrefs

- `0x18001beb0`: `Software\Microsoft\WindowsUpdate\Orchestrator\Installation\Target`
- `0x18001bed8`: `UpdateTimestamp`
- `0x18001bf7a`: `OobeCompleteTime`

## pseudocode

```c
__int64 __fastcall UtilGetInstallTime(LPFILETIME lpFileTime)
{
  LSTATUS ValueW; // eax
  unsigned __int64 v3; // r9
  char v4; // si
  struct _FILETIME v5; // rbx
  unsigned int BINARY; // ebx
  struct _FILETIME QWORD; // rax
  HKEY v9; // rcx
  signed int LastError; // eax
  bool pvData; // [rsp+28h] [rbp-21h]
  bool pvDataa; // [rsp+28h] [rbp-21h]
  bool v13; // [rsp+40h] [rbp-9h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-5h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-1h] BYREF
  bool v16[8]; // [rsp+50h] [rbp+7h] BYREF
  HKEY hkey; // [rsp+58h] [rbp+Fh] BYREF
  SYSTEMTIME SystemTime; // [rsp+60h] [rbp+17h] BYREF

  v15 = 16;
  *(_QWORD *)v16 = 0;
  pcbData = 8;
  v13 = 0;
  hkey = 0;
  SystemTime = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\Installation\\Target",
             0,
             0x101u,
             &hkey);
  if ( ValueW || (ValueW = RegGetValueW(hkey, 0, L"UpdateTimestamp", 0x40u, 0, v16, &pcbData)) != 0 )
  {
    v4 = 0;
    if ( (int)ERROR_HR_FROM_WIN32(ValueW) < 0 )
    {
      *(_QWORD *)v16 = 0;
      v4 = 1;
      v13 = 1;
    }
  }
  else
  {
    v4 = 0;
  }
  v5 = *(struct _FILETIME *)v16;
  if ( hkey )
    RegCloseKey(hkey);
  if ( !v4 )
  {
    *lpFileTime = v5;
    return 0;
  }
  QWORD = (struct _FILETIME)UtilRegGetQWORD(
                              HKEY_LOCAL_MACHINE,
                              L"Software\\Microsoft\\Shell\\OOBE",
                              L"OobeCompleteTime",
                              v3,
                              &v13,
                              pvData);
  if ( !v13 )
  {
    *lpFileTime = QWORD;
    return 0;
  }
  BINARY = UtilRegGetBINARY(
             v9,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
             L"EndTimeStamp",
             (unsigned __int8 *)&SystemTime,
             &v15,
             pvDataa);
  if ( (BINARY & 0x80000000) != 0 )
    return BINARY;
  if ( SystemTimeToFileTime(&SystemTime, lpFileTime) )
    return 0;
  LastError = GetLastError();
  BINARY = LastError;
  if ( LastError > 0 )
    BINARY = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, BINARY);
  return BINARY;
}

```

## disassembly

```asm
0x18001be50  push    rbp
0x18001be52  push    rbx
0x18001be53  push    rsi
0x18001be54  push    rdi
0x18001be55  lea     rbp, [rsp-3Fh]
0x18001be5a  sub     rsp, 88h
0x18001be61  mov     rax, cs:__security_cookie
0x18001be68  xor     rax, rsp
0x18001be6b  mov     [rbp+57h+var_30], rax
0x18001be6f  mov     rdi, rcx
0x18001be72  mov     [rbp+57h+var_58], 10h
0x18001be79  xorps   xmm0, xmm0
0x18001be7c  mov     qword ptr [rbp+57h+var_50], 0
0x18001be84  lea     rax, [rbp+57h+hkey]
0x18001be88  mov     [rbp+57h+var_5C], 8
0x18001be8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001be96  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18001be9b  mov     r9d, 101h; samDesired
0x18001bea1  mov     [rbp+57h+var_60], 0
0x18001bea5  xor     r8d, r8d; ulOptions
0x18001bea8  mov     [rbp+57h+hkey], 0
0x18001beb0  lea     rdx, aSoftwareMicros_23; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x18001beb7  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001bebb  call    cs:__imp_RegOpenKeyExW
0x18001bec2  nop     dword ptr [rax+rax+00h]
0x18001bec7  test    eax, eax
0x18001bec9  jnz     short loc_18001BF09
0x18001becb  mov     rcx, [rbp+57h+hkey]; hkey
0x18001becf  lea     rax, [rbp+57h+var_5C]
0x18001bed3  mov     [rsp+0A0h+pcbData], rax; pcbData
0x18001bed8  lea     r8, aUpdatetimestam; "UpdateTimestamp"
0x18001bedf  lea     rax, [rbp+57h+var_50]
0x18001bee3  mov     r9d, 40h ; '@'; dwFlags
0x18001bee9  mov     [rsp+0A0h+pvData], rax; bool
0x18001beee  xor     edx, edx; lpSubKey
0x18001bef0  mov     [rsp+0A0h+phkResult], 0; pdwType
0x18001bef9  call    cs:__imp_RegGetValueW
0x18001bf00  nop     dword ptr [rax+rax+00h]
0x18001bf05  test    eax, eax
0x18001bf07  jz      short loc_18001BF28
0x18001bf09  mov     ecx, eax; unsigned int
0x18001bf0b  xor     sil, sil
0x18001bf0e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001bf13  test    eax, eax
0x18001bf15  jns     short loc_18001BF2B
0x18001bf17  mov     qword ptr [rbp+57h+var_50], 0
0x18001bf1f  mov     sil, 1
0x18001bf22  mov     [rbp+57h+var_60], 1
0x18001bf26  jmp     short loc_18001BF2B
0x18001bf28  xor     sil, sil
0x18001bf2b  mov     rcx, [rbp+57h+hkey]; hKey
0x18001bf2f  mov     rbx, qword ptr [rbp+57h+var_50]
0x18001bf33  test    rcx, rcx
0x18001bf36  jz      short loc_18001BF44
0x18001bf38  call    cs:__imp_RegCloseKey
0x18001bf3f  nop     dword ptr [rax+rax+00h]
0x18001bf44  test    sil, sil
0x18001bf47  jnz     short loc_18001BF6F
0x18001bf49  mov     [rdi], ebx
0x18001bf4b  shr     rbx, 20h
0x18001bf4f  mov     [rdi+4], ebx
0x18001bf52  xor     ebx, ebx
0x18001bf54  mov     eax, ebx
0x18001bf56  mov     rcx, [rbp+57h+var_30]
0x18001bf5a  xor     rcx, rsp; StackCookie
0x18001bf5d  call    __security_check_cookie
0x18001bf62  add     rsp, 88h
0x18001bf69  pop     rdi
0x18001bf6a  pop     rsi
0x18001bf6b  pop     rbx
0x18001bf6c  pop     rbp
0x18001bf6d  retn
0x18001bf6f  lea     rax, [rbp+57h+var_60]
0x18001bf73  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001bf7a  lea     r8, aOobecompleteti; "OobeCompleteTime"
0x18001bf81  mov     [rsp+0A0h+phkResult], rax; bool *
0x18001bf86  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Shell\\OOBE"
0x18001bf8d  call    ?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z; UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)
0x18001bf92  cmp     [rbp+57h+var_60], 0
0x18001bf96  jnz     short loc_18001BFA3
0x18001bf98  mov     [rdi], eax
0x18001bf9a  shr     rax, 20h
0x18001bf9e  mov     [rdi+4], eax
0x18001bfa1  jmp     short loc_18001BF52
0x18001bfa3  lea     rax, [rbp+57h+var_58]
0x18001bfa7  lea     r9, [rbp+57h+SystemTime]; unsigned __int8 *
0x18001bfab  mov     [rsp+0A0h+phkResult], rax; unsigned int *
0x18001bfb0  lea     r8, aEndtimestamp; "EndTimeStamp"
0x18001bfb7  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001bfbe  call    ?UtilRegGetBINARY@@YAJPEAUHKEY__@@PEB_W1PEAEPEAK_N@Z; UtilRegGetBINARY(HKEY__ *,wchar_t const *,wchar_t const *,uchar *,ulong *,bool)
0x18001bfc3  mov     ebx, eax
0x18001bfc5  test    eax, eax
0x18001bfc7  js      short loc_18001BF54
0x18001bfc9  mov     rdx, rdi; lpFileTime
0x18001bfcc  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001bfd0  call    cs:__imp_SystemTimeToFileTime
0x18001bfd7  nop     dword ptr [rax+rax+00h]
0x18001bfdc  test    eax, eax
0x18001bfde  jnz     loc_18001BF52
0x18001bfe4  call    cs:__imp_GetLastError
0x18001bfeb  nop     dword ptr [rax+rax+00h]
0x18001bff0  mov     ebx, eax
0x18001bff2  test    eax, eax
0x18001bff4  jle     short loc_18001BFFF
0x18001bff6  movzx   ebx, ax
0x18001bff9  or      ebx, 80070000h
0x18001bfff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c006  lea     rax, WPP_GLOBAL_Control
0x18001c00d  cmp     rcx, rax
0x18001c010  jz      loc_18001BF54
0x18001c016  test    byte ptr [rcx+1Ch], 1
0x18001c01a  jz      loc_18001BF54
0x18001c020  mov     rcx, [rcx+10h]
0x18001c024  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18001c02b  mov     edx, 0A5h
0x18001c030  mov     r9d, ebx
0x18001c033  call    WPP_SF_d
0x18001c038  jmp     loc_18001BF54
```
