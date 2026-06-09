# SetWlanSecuritySettings(ulong,ulong,ulong,int,ushort const *)

- ea: `0x18009eb60`
- end: `0x18009ecf8`
- name: `?SetWlanSecuritySettings@@YAKKKKHPEBG@Z`
- size: `408`
- prototype: `unsigned int __fastcall(unsigned int, unsigned int, unsigned int, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18011c28c`
- `0x18012b140`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18009eb60`
- `0x1800c6774`
- `0x180106340`
- `0x180107330`
- `0x180108234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18009ec5b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18009ec70`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18009ec5b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18009ec70`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18009ec40`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18009ec40`
- `MobileNetworking!ReplaceObject` at `0x18009ec93`
- `MobileNetworking!ReplaceObject` at `0x18009ec93`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x18009ec27`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x18009ec27`

## string_xrefs

- `0x18009ec18`: `System\CurrentControlSet\Services\WlanSvc`
- `0x18009ec31`: `System\CurrentControlSet\Services\WlanSvc`

## pseudocode

```c
__int64 __fastcall SetWlanSecuritySettings(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        const unsigned __int16 *a5)
{
  __int64 v7; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  PVOID *v11; // rcx
  wchar_t **v12; // rdi
  unsigned int v13; // ebx
  _BYTE v15[528]; // [rsp+30h] [rbp-268h] BYREF

  v7 = a1;
  memset_0(v15, 0, 0x208u);
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (unsigned int)v7 >= 0x11 )
  {
    v13 = 87;
  }
  else
  {
    v12 = &(&off_18022D620)[4 * v7];
    if ( *((_DWORD *)v12 + 2) != (_DWORD)v7 )
      MicrosoftTelemetryAssertTriggeredNoArgs(&off_18022D620, v9, v10);
    if ( IsGetCustomWfdSettingsRegPathPresent()
      && (int)GetCustomRegRootPath(v15, 260, L"System\\CurrentControlSet\\Services\\WlanSvc") >= 0
      || (v13 = _o_wcscpy_s(v15, 260, L"System\\CurrentControlSet\\Services\\WlanSvc")) == 0 )
    {
      _o_wcscat_s(v15, 260, L"\\");
      v13 = _o_wcscat_s(v15, 260, L"Parameters\\WlanAPIPermissions");
    }
    if ( !v13 )
      v13 = ReplaceObject(v15, a2, a3, a4, v12, a5);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 105) >= 4u && (*((_BYTE *)v11 + 108) & 1) != 0 )
    WPP_SF_d(v11[12], 24, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18009eb60  push    rbx
0x18009eb62  push    rbp
0x18009eb63  push    rsi
0x18009eb64  push    rdi
0x18009eb65  push    r12
0x18009eb67  push    r13
0x18009eb69  push    r14
0x18009eb6b  push    r15
0x18009eb6d  sub     rsp, 258h
0x18009eb74  mov     rax, cs:__security_cookie
0x18009eb7b  xor     rax, rsp
0x18009eb7e  mov     [rsp+298h+var_58], rax
0x18009eb86  mov     r15, [rsp+298h+arg_20]
0x18009eb8e  mov     ebp, r8d
0x18009eb91  mov     esi, edx
0x18009eb93  mov     ebx, ecx
0x18009eb95  xor     edx, edx; Val
0x18009eb97  lea     rcx, [rsp+298h+var_268]; void *
0x18009eb9c  mov     r8d, 208h; Size
0x18009eba2  mov     r14d, r9d
0x18009eba5  call    memset_0
0x18009ebaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ebb1  lea     r13, WPP_GLOBAL_Control
0x18009ebb8  cmp     rcx, r13
0x18009ebbb  jz      short loc_18009EBE5
0x18009ebbd  cmp     byte ptr [rcx+69h], 4
0x18009ebc1  jb      short loc_18009EBE5
0x18009ebc3  test    byte ptr [rcx+6Ch], 1
0x18009ebc7  jz      short loc_18009EBE5
0x18009ebc9  mov     rcx, [rcx+60h]
0x18009ebcd  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18009ebd4  mov     edx, 17h
0x18009ebd9  call    WPP_SF_
0x18009ebde  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ebe5  cmp     ebx, 11h
0x18009ebe8  jnb     loc_18009ECA4
0x18009ebee  mov     rdi, rbx
0x18009ebf1  lea     rcx, off_18022D620; "Permit List"
0x18009ebf8  shl     rdi, 5
0x18009ebfc  add     rdi, rcx
0x18009ebff  cmp     [rdi+8], ebx
0x18009ec02  jz      short loc_18009EC09
0x18009ec04  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pSecSettings->dwObjectID == dwObjectId")
0x18009ec09  call    IsGetCustomWfdSettingsRegPathPresent
0x18009ec0e  mov     r12d, 104h
0x18009ec14  test    al, al
0x18009ec16  jz      short loc_18009EC31
0x18009ec18  lea     r8, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Wl"...
0x18009ec1f  mov     edx, r12d
0x18009ec22  lea     rcx, [rsp+298h+var_268]
0x18009ec27  call    cs:__imp_GetCustomRegRootPath
0x18009ec2d  test    eax, eax
0x18009ec2f  jns     short loc_18009EC4C
0x18009ec31  lea     r8, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Wl"...
0x18009ec38  mov     rdx, r12
0x18009ec3b  lea     rcx, [rsp+298h+var_268]
0x18009ec40  call    cs:__imp__o_wcscpy_s
0x18009ec46  mov     ebx, eax
0x18009ec48  test    eax, eax
0x18009ec4a  jnz     short loc_18009EC78
0x18009ec4c  lea     r8, SubBlock; "\\"
0x18009ec53  mov     rdx, r12
0x18009ec56  lea     rcx, [rsp+298h+var_268]
0x18009ec5b  call    cs:__imp__o_wcscat_s
0x18009ec61  lea     r8, aParametersWlan; "Parameters\\WlanAPIPermissions"
0x18009ec68  mov     rdx, r12
0x18009ec6b  lea     rcx, [rsp+298h+var_268]
0x18009ec70  call    cs:__imp__o_wcscat_s
0x18009ec76  mov     ebx, eax
0x18009ec78  test    ebx, ebx
0x18009ec7a  jnz     short loc_18009EC9B
0x18009ec7c  mov     [rsp+298h+var_270], r15
0x18009ec81  lea     rcx, [rsp+298h+var_268]
0x18009ec86  mov     r9d, r14d
0x18009ec89  mov     [rsp+298h+var_278], rdi
0x18009ec8e  mov     r8d, ebp
0x18009ec91  mov     edx, esi
0x18009ec93  call    cs:__imp_ReplaceObject
0x18009ec99  mov     ebx, eax
0x18009ec9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009eca2  jmp     short loc_18009ECA9
0x18009eca4  mov     ebx, 57h ; 'W'
0x18009eca9  cmp     rcx, r13
0x18009ecac  jz      short loc_18009ECD2
0x18009ecae  cmp     byte ptr [rcx+69h], 4
0x18009ecb2  jb      short loc_18009ECD2
0x18009ecb4  test    byte ptr [rcx+6Ch], 1
0x18009ecb8  jz      short loc_18009ECD2
0x18009ecba  mov     rcx, [rcx+60h]
0x18009ecbe  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18009ecc5  mov     edx, 18h
0x18009ecca  mov     r9d, ebx
0x18009eccd  call    WPP_SF_d
0x18009ecd2  mov     eax, ebx
0x18009ecd4  mov     rcx, [rsp+298h+var_58]
0x18009ecdc  xor     rcx, rsp; StackCookie
0x18009ecdf  call    __security_check_cookie
0x18009ece4  add     rsp, 258h
0x18009eceb  pop     r15
0x18009eced  pop     r14
0x18009ecef  pop     r13
0x18009ecf1  pop     r12
0x18009ecf3  pop     rdi
0x18009ecf4  pop     rsi
0x18009ecf5  pop     rbp
0x18009ecf6  pop     rbx
0x18009ecf7  retn
```
