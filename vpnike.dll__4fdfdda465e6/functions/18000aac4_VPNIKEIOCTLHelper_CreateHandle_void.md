# VPNIKEIOCTLHelper::CreateHandle(void)

- ea: `0x18000aac4`
- end: `0x18000ac35`
- name: `?CreateHandle@VPNIKEIOCTLHelper@@IEAAKXZ`
- size: `369`
- prototype: `__int64 __fastcall(VPNIKEIOCTLHelper *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a5e8`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18000aac4`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab6e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18000ab5e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18000ab5e`

## string_xrefs

- `0x18000abc4`: `Created AgileVPNDriverHandle`

## pseudocode

```c
__int64 __fastcall VPNIKEIOCTLHelper::CreateHandle(VPNIKEIOCTLHelper *this)
{
  DWORD v2; // ebx
  HANDLE FileA; // rax
  DWORD LastError; // eax
  int v6; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v7[2044]; // [rsp+54h] [rbp-814h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_45d935e7e0d7382daf50f1a345cf85df_Traceguids);
  }
  v6 = 0;
  v2 = 0;
  memset_0(v7, 0, sizeof(v7));
  FileA = CreateFileA("\\\\.\\AGILEVPN", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  *((_QWORD *)this + 1) = FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(&v6, L"Creating AgileVPNDriverHandle failed: %d", LastError);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v6);
    }
  }
  if ( (byte_1800AA941 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceInfo,
      L"Created AgileVPNDriverHandle");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_45d935e7e0d7382daf50f1a345cf85df_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18000aac4  mov     [rsp+arg_8], rbx
0x18000aac9  mov     [rsp+arg_10], rsi
0x18000aace  push    rdi
0x18000aacf  sub     rsp, 860h
0x18000aad6  mov     rax, cs:__security_cookie
0x18000aadd  xor     rax, rsp
0x18000aae0  mov     [rsp+868h+var_18], rax
0x18000aae8  mov     rdi, rcx
0x18000aaeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaf2  lea     rsi, WPP_GLOBAL_Control
0x18000aaf9  cmp     rcx, rsi
0x18000aafc  jz      short loc_18000AB1F
0x18000aafe  test    byte ptr [rcx+1Ch], 1
0x18000ab02  jz      short loc_18000AB1F
0x18000ab04  cmp     byte ptr [rcx+19h], 6
0x18000ab08  jb      short loc_18000AB1F
0x18000ab0a  mov     rcx, [rcx+10h]
0x18000ab0e  lea     r8, WPP_45d935e7e0d7382daf50f1a345cf85df_Traceguids
0x18000ab15  mov     edx, 0Dh
0x18000ab1a  call    WPP_SF_
0x18000ab1f  xor     eax, eax
0x18000ab21  lea     rcx, [rsp+868h+var_814]; void *
0x18000ab26  xor     edx, edx; Val
0x18000ab28  mov     [rsp+868h+var_818], eax
0x18000ab2c  mov     r8d, 7FCh; Size
0x18000ab32  xor     ebx, ebx
0x18000ab34  call    memset_0
0x18000ab39  lea     r8d, [rbx+3]; dwShareMode
0x18000ab3d  mov     [rsp+868h+hTemplateFile], rbx; hTemplateFile
0x18000ab42  mov     [rsp+868h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18000ab4a  lea     rcx, FileName; "\\\\.\\AGILEVPN"
0x18000ab51  xor     r9d, r9d; lpSecurityAttributes
0x18000ab54  mov     [rsp+868h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000ab59  mov     edx, 0C0000000h; dwDesiredAccess
0x18000ab5e  call    cs:__imp_CreateFileA
0x18000ab64  mov     [rdi+8], rax
0x18000ab68  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ab6c  jnz     short loc_18000ABBB
0x18000ab6e  call    cs:__imp_GetLastError
0x18000ab74  test    cs:byte_1800AA941, 4
0x18000ab7b  mov     ebx, eax
0x18000ab7d  jz      short loc_18000ABBB
0x18000ab7f  xor     ecx, ecx
0x18000ab81  lea     rdx, aCreatingAgilev; "Creating AgileVPNDriverHandle failed: %"...
0x18000ab88  mov     word ptr [rsp+868h+var_818], cx
0x18000ab8d  mov     r8d, eax
0x18000ab90  lea     rcx, [rsp+868h+var_818]
0x18000ab95  call    FormatRRASErrorString
0x18000ab9a  test    cs:byte_1800AA941, 4
0x18000aba1  jz      short loc_18000ABBB
0x18000aba3  lea     r8, [rsp+868h+var_818]
0x18000aba8  lea     rdx, RasVpnIkeTraceError
0x18000abaf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000abb6  call    McTemplateU0z_EventWriteTransfer
0x18000abbb  test    cs:byte_1800AA941, 8
0x18000abc2  jz      short loc_18000ABDE
0x18000abc4  lea     r8, aCreatedAgilevp; "Created AgileVPNDriverHandle"
0x18000abcb  lea     rdx, RasVpnIkeTraceInfo
0x18000abd2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000abd9  call    McTemplateU0z_EventWriteTransfer
0x18000abde  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abe5  cmp     rcx, rsi
0x18000abe8  jz      short loc_18000AC0E
0x18000abea  test    byte ptr [rcx+1Ch], 1
0x18000abee  jz      short loc_18000AC0E
0x18000abf0  cmp     byte ptr [rcx+19h], 6
0x18000abf4  jb      short loc_18000AC0E
0x18000abf6  mov     rcx, [rcx+10h]
0x18000abfa  lea     r8, WPP_45d935e7e0d7382daf50f1a345cf85df_Traceguids
0x18000ac01  mov     edx, 0Eh
0x18000ac06  mov     r9d, ebx
0x18000ac09  call    WPP_SF_d
0x18000ac0e  mov     eax, ebx
0x18000ac10  mov     rcx, [rsp+868h+var_18]
0x18000ac18  xor     rcx, rsp; StackCookie
0x18000ac1b  call    __security_check_cookie
0x18000ac20  lea     r11, [rsp+868h+var_8]
0x18000ac28  mov     rbx, [r11+18h]
0x18000ac2c  mov     rsi, [r11+20h]
0x18000ac30  mov     rsp, r11
0x18000ac33  pop     rdi
0x18000ac34  retn
```
