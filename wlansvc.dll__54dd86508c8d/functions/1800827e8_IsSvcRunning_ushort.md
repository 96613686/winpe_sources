# IsSvcRunning(ushort *)

- ea: `0x1800827e8`
- end: `0x180082a7b`
- name: `?IsSvcRunning@@YAHPEAG@Z`
- size: `659`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180033430`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003fda0`
- `0x1800827e8`
- `0x180106340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008298f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800829d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082a15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008298f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800829d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082a15`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800828c5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800828ce`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800828c5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800828ce`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008284f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008284f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008286d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008286d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800828ac`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800828ac`

## pseudocode

```c
__int64 __fastcall IsSvcRunning(unsigned __int16 *a1)
{
  unsigned int v1; // ebx
  PVOID *v2; // rcx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  SC_HANDLE v5; // rdi
  PVOID *v6; // rcx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD LastError; // eax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-68h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v13; // [rsp+48h] [rbp-50h]
  int v14; // [rsp+58h] [rbp-40h]

  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v14 = 0;
  v1 = 0;
  v13 = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
      {
        WPP_SF_S(v2[12], 31, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, L"Netman");
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
        WPP_SF_S(v2[12], 32, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, L"Netman");
    }
  }
  v3 = OpenSCManagerW(0, 0, 0x80000000);
  v4 = v3;
  if ( v3 )
  {
    v5 = OpenServiceW(v3, L"Netman", 0x20004u);
    if ( v5 )
    {
      v14 = 0;
      *(_OWORD *)Buffer = 0;
      v13 = 0;
      if ( QueryServiceStatusEx(v5, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      {
        LOBYTE(v1) = *(_DWORD *)&Buffer[4] == 4;
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 35, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, LastError);
        }
      }
      CloseServiceHandle(v5);
    }
    else
    {
      v9 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 34, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, v9);
      }
    }
    CloseServiceHandle(v4);
    goto LABEL_8;
  }
  v8 = GetLastError();
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 33, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, v8);
LABEL_8:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 105) >= 4u && (*((_BYTE *)v6 + 108) & 1) != 0 )
    WPP_SF_d(v6[12], 36, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x1800827e8  push    rbx
0x1800827ea  push    rsi
0x1800827eb  push    rdi
0x1800827ec  push    r14
0x1800827ee  push    r15
0x1800827f0  sub     rsp, 70h
0x1800827f4  mov     rax, cs:__security_cookie
0x1800827fb  xor     rax, rsp
0x1800827fe  mov     [rsp+98h+var_38], rax
0x180082803  xorps   xmm0, xmm0
0x180082806  mov     [rsp+98h+var_68], 0
0x18008280e  xor     eax, eax
0x180082810  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x180082815  mov     [rsp+98h+var_40], eax
0x180082819  xor     ebx, ebx
0x18008281b  movups  [rsp+98h+var_50], xmm0
0x180082820  mov     rcx, cs:WPP_GLOBAL_Control
0x180082827  lea     r14, WPP_GLOBAL_Control
0x18008282e  lea     rdi, ServiceName; "Netman"
0x180082835  lea     r15, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18008283c  cmp     rcx, r14
0x18008283f  jnz     loc_180082905
0x180082845  xor     edx, edx; lpDatabaseName
0x180082847  xor     ecx, ecx; lpMachineName
0x180082849  mov     r8d, 80000000h; dwDesiredAccess
0x18008284f  call    cs:__imp_OpenSCManagerW
0x180082855  mov     rsi, rax
0x180082858  test    rax, rax
0x18008285b  jz      loc_18008298F
0x180082861  mov     r8d, 20004h; dwDesiredAccess
0x180082867  mov     rdx, rdi; lpServiceName
0x18008286a  mov     rcx, rax; hSCManager
0x18008286d  call    cs:__imp_OpenServiceW
0x180082873  mov     rdi, rax
0x180082876  test    rax, rax
0x180082879  jz      loc_1800829D2
0x18008287f  xor     eax, eax
0x180082881  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x180082886  xorps   xmm0, xmm0
0x180082889  mov     [rsp+98h+var_40], eax
0x18008288d  lea     rax, [rsp+98h+var_68]
0x180082892  mov     r9d, 24h ; '$'; cbBufSize
0x180082898  xor     edx, edx; InfoLevel
0x18008289a  mov     [rsp+98h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18008289f  mov     rcx, rdi; hService
0x1800828a2  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x1800828a7  movups  [rsp+98h+var_50], xmm0
0x1800828ac  call    cs:__imp_QueryServiceStatusEx
0x1800828b2  test    eax, eax
0x1800828b4  jz      loc_180082A15
0x1800828ba  cmp     dword ptr [rsp+98h+Buffer+4], 4
0x1800828bf  setz    bl
0x1800828c2  mov     rcx, rdi; hSCObject
0x1800828c5  call    cs:__imp_CloseServiceHandle
0x1800828cb  mov     rcx, rsi; hSCObject
0x1800828ce  call    cs:__imp_CloseServiceHandle
0x1800828d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800828db  cmp     rcx, r14
0x1800828de  jz      short loc_1800828EA
0x1800828e0  cmp     byte ptr [rcx+69h], 4
0x1800828e4  jnb     loc_180082A58
0x1800828ea  mov     eax, ebx
0x1800828ec  mov     rcx, [rsp+98h+var_38]
0x1800828f1  xor     rcx, rsp; StackCookie
0x1800828f4  call    __security_check_cookie
0x1800828f9  add     rsp, 70h
0x1800828fd  pop     r15
0x1800828ff  pop     r14
0x180082901  pop     rdi
0x180082902  pop     rsi
0x180082903  pop     rbx
0x180082904  retn
0x180082905  cmp     byte ptr [rcx+69h], 4
0x180082909  jb      short loc_180082929
0x18008290b  test    byte ptr [rcx+6Ch], 1
0x18008290f  jz      short loc_180082929
0x180082911  mov     rcx, [rcx+60h]
0x180082915  mov     edx, 1Eh
0x18008291a  mov     r8, r15
0x18008291d  call    WPP_SF_
0x180082922  mov     rcx, cs:WPP_GLOBAL_Control
0x180082929  cmp     rcx, r14
0x18008292c  jz      loc_180082845
0x180082932  cmp     byte ptr [rcx+69h], 4
0x180082936  jb      short loc_180082959
0x180082938  test    byte ptr [rcx+6Ch], 1
0x18008293c  jz      short loc_180082959
0x18008293e  mov     rcx, [rcx+60h]
0x180082942  mov     edx, 1Fh
0x180082947  mov     r9, rdi
0x18008294a  mov     r8, r15
0x18008294d  call    WPP_SF_S
0x180082952  mov     rcx, cs:WPP_GLOBAL_Control
0x180082959  cmp     rcx, r14
0x18008295c  jz      loc_180082845
0x180082962  cmp     byte ptr [rcx+69h], 4
0x180082966  jb      loc_180082845
0x18008296c  test    byte ptr [rcx+6Ch], 1
0x180082970  jz      loc_180082845
0x180082976  mov     rcx, [rcx+60h]
0x18008297a  mov     edx, 20h ; ' '
0x18008297f  mov     r9, rdi
0x180082982  mov     r8, r15
0x180082985  call    WPP_SF_S
0x18008298a  jmp     loc_180082845
0x18008298f  call    cs:__imp_GetLastError
0x180082995  mov     rcx, cs:WPP_GLOBAL_Control
0x18008299c  cmp     rcx, r14
0x18008299f  jz      loc_1800828EA
0x1800829a5  cmp     byte ptr [rcx+69h], 1
0x1800829a9  jb      loc_1800828DB
0x1800829af  test    byte ptr [rcx+6Ch], 1
0x1800829b3  jz      loc_1800828DB
0x1800829b9  mov     rcx, [rcx+60h]
0x1800829bd  mov     edx, 21h ; '!'
0x1800829c2  mov     r9d, eax
0x1800829c5  mov     r8, r15
0x1800829c8  call    WPP_SF_d
0x1800829cd  jmp     loc_1800828D4
0x1800829d2  call    cs:__imp_GetLastError
0x1800829d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800829df  cmp     rcx, r14
0x1800829e2  jz      loc_1800828CB
0x1800829e8  cmp     byte ptr [rcx+69h], 1
0x1800829ec  jb      loc_1800828CB
0x1800829f2  test    byte ptr [rcx+6Ch], 1
0x1800829f6  jz      loc_1800828CB
0x1800829fc  mov     rcx, [rcx+60h]
0x180082a00  mov     edx, 22h ; '"'
0x180082a05  mov     r9d, eax
0x180082a08  mov     r8, r15
0x180082a0b  call    WPP_SF_d
0x180082a10  jmp     loc_1800828CB
0x180082a15  call    cs:__imp_GetLastError
0x180082a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180082a22  cmp     rcx, r14
0x180082a25  jz      loc_1800828C2
0x180082a2b  cmp     byte ptr [rcx+69h], 1
0x180082a2f  jb      loc_1800828C2
0x180082a35  test    byte ptr [rcx+6Ch], 1
0x180082a39  jz      loc_1800828C2
0x180082a3f  mov     rcx, [rcx+60h]
0x180082a43  mov     edx, 23h ; '#'
0x180082a48  mov     r9d, eax
0x180082a4b  mov     r8, r15
0x180082a4e  call    WPP_SF_d
0x180082a53  jmp     loc_1800828C2
0x180082a58  test    byte ptr [rcx+6Ch], 1
0x180082a5c  jz      loc_1800828EA
0x180082a62  mov     rcx, [rcx+60h]
0x180082a66  mov     edx, 24h ; '$'
0x180082a6b  mov     r9d, ebx
0x180082a6e  mov     r8, r15
0x180082a71  call    WPP_SF_d
0x180082a76  jmp     loc_1800828EA
```
