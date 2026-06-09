# NetpSetPrimarySamAccountName

- ea: `0x180029dbc`
- end: `0x180029faf`
- name: `NetpSetPrimarySamAccountName`
- size: `499`
- prototype: `__int64 __usercall@<rax>(LPCWSTR servername@<rcx>, LPCWSTR username@<rdx>, LPCWSTR@<r8>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800288a8`

## callees

- `0x18002191c`
- `0x180029dbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029ebc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029ebc`
- `netutils!NetApiBufferFree` at `0x180029f46`
- `netutils!NetApiBufferFree` at `0x180029f46`
- `samcli!NetUserGetInfo` at `0x180029e79`
- `samcli!NetUserGetInfo` at `0x180029e79`
- `samcli!NetUserSetInfo` at `0x180029e3d`
- `samcli!NetUserSetInfo` at `0x180029eeb`
- `samcli!NetUserSetInfo` at `0x180029e3d`
- `samcli!NetUserSetInfo` at `0x180029eeb`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029f30`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029f93`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029f30`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029f93`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpManageIPCConnect` at `0x180029e0b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpManageIPCConnect` at `0x180029f6b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpManageIPCConnect` at `0x180029e0b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpManageIPCConnect` at `0x180029f6b`

## string_xrefs

- `0x180029f09`: `NetpSetPrimarySamAccountName: failed to update display name on %ws (ignored) 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetpSetPrimarySamAccountName(
        LPCWSTR servername,
        LPCWSTR username,
        LPCWSTR a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v9; // rcx
  char v10; // r14
  DWORD v11; // edi
  __int64 v12; // rcx
  const wchar_t *v13; // rcx
  __int64 v14; // rcx
  DWORD Info; // ebp
  __int64 v16; // rcx
  __int64 v17; // rcx
  DWORD v18; // esi
  __int64 v19; // rcx
  unsigned int v20; // esi
  LPBYTE bufptr; // [rsp+30h] [rbp-58h] BYREF
  BYTE buf[8]; // [rsp+38h] [rbp-50h] BYREF
  BYTE v24[72]; // [rsp+40h] [rbp-48h] BYREF

  *(_QWORD *)buf = 0;
  bufptr = 0;
  if ( !(unsigned __int8)IsNetpManageIPCConnectPresent(servername) )
  {
    v11 = 50;
    goto LABEL_15;
  }
  v10 = 1;
  v11 = NetpManageIPCConnect(servername, a4, a5, 1);
  if ( v11 )
  {
LABEL_15:
    v10 = 0;
    if ( !(unsigned __int8)IsNetpManageIPCConnectPresent(v9) )
      goto LABEL_18;
    v13 = L"NetpSetPrimarySamAccountName: NetpManageIPCConnect failed to connect to %ws: 0x%lx\n";
    goto LABEL_17;
  }
  *(_QWORD *)buf = a3;
  v11 = NetUserSetInfo(servername, username, 0, buf, 0);
  if ( v11 )
  {
    if ( !(unsigned __int8)IsNetpManageIPCConnectPresent(v12) )
      goto LABEL_18;
    v13 = L"NetpSetPrimarySamAccountName: NetUserSetInfo failed on %ws: 0x%lx\n";
LABEL_17:
    NetpLogPrintHelper(v13, servername, v11);
    goto LABEL_18;
  }
  Info = NetUserGetInfo(servername, a3, 0xAu, &bufptr);
  if ( Info )
  {
    if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v14) )
      NetpLogPrintHelper(
        L"NetpSetPrimarySamAccountName: failed to get display name on %ws (ignored) 0x%lx\n",
        servername,
        Info);
  }
  else
  {
    v16 = *((_QWORD *)bufptr + 3);
    if ( v16 )
    {
      if ( (unsigned int)_o__wcsicmp(v16, a3) )
      {
        *(_QWORD *)v24 = a3;
        v18 = NetUserSetInfo(servername, a3, 0x3F3u, v24, 0);
        if ( v18 )
        {
          if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v17) )
            NetpLogPrintHelper(
              L"NetpSetPrimarySamAccountName: failed to update display name on %ws (ignored) 0x%lx\n",
              servername,
              v18);
        }
      }
    }
  }
LABEL_18:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  if ( v10 )
  {
    v20 = NetpManageIPCConnect(servername, a4, a5, 2);
    if ( v20 )
    {
      if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v19) )
        NetpLogPrintHelper(
          L"NetpSetPrimarySamAccountName: NetpManageIPCConnect failed to disconnect from %ws: 0x%lx\n",
          servername,
          v20);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180029dbc  push    rbx
0x180029dbe  push    rbp
0x180029dbf  push    rsi
0x180029dc0  push    rdi
0x180029dc1  push    r14
0x180029dc3  push    r15
0x180029dc5  sub     rsp, 58h
0x180029dc9  mov     r15, r9
0x180029dcc  mov     qword ptr [rsp+88h+buf], 0
0x180029dd5  mov     rsi, r8
0x180029dd8  mov     [rsp+88h+bufptr], 0
0x180029de1  mov     rbp, rdx
0x180029de4  mov     rbx, rcx
0x180029de7  call    IsNetpManageIPCConnectPresent
0x180029dec  test    al, al
0x180029dee  jz      loc_180029F12
0x180029df4  mov     r8, [rsp+88h+arg_20]
0x180029dfc  mov     r14d, 1
0x180029e02  mov     r9d, r14d
0x180029e05  mov     rdx, r15
0x180029e08  mov     rcx, rbx
0x180029e0b  call    cs:__imp_NetpManageIPCConnect
0x180029e12  nop     dword ptr [rax+rax+00h]
0x180029e17  mov     edi, eax
0x180029e19  test    eax, eax
0x180029e1b  jnz     loc_180029F17
0x180029e21  lea     r9, [rsp+88h+buf]; buf
0x180029e26  mov     qword ptr [rsp+88h+buf], rsi
0x180029e2b  xor     r8d, r8d; level
0x180029e2e  mov     [rsp+88h+parm_err], 0; parm_err
0x180029e37  mov     rdx, rbp; username
0x180029e3a  mov     rcx, rbx; servername
0x180029e3d  call    cs:__imp_NetUserSetInfo
0x180029e44  nop     dword ptr [rax+rax+00h]
0x180029e49  mov     edi, eax
0x180029e4b  test    eax, eax
0x180029e4d  jz      short loc_180029E68
0x180029e4f  call    IsNetpManageIPCConnectPresent
0x180029e54  test    al, al
0x180029e56  jz      loc_180029F3C
0x180029e5c  lea     rcx, aNetpsetprimary_3; "NetpSetPrimarySamAccountName: NetUserSe"...
0x180029e63  jmp     loc_180029F2A
0x180029e68  lea     r9, [rsp+88h+bufptr]; bufptr
0x180029e6d  mov     r8d, 0Ah; level
0x180029e73  mov     rdx, rsi; username
0x180029e76  mov     rcx, rbx; servername
0x180029e79  call    cs:__imp_NetUserGetInfo
0x180029e80  nop     dword ptr [rax+rax+00h]
0x180029e85  mov     ebp, eax
0x180029e87  test    eax, eax
0x180029e89  jz      short loc_180029EA7
0x180029e8b  call    IsNetpManageIPCConnectPresent
0x180029e90  test    al, al
0x180029e92  jz      loc_180029F3C
0x180029e98  mov     r8d, ebp
0x180029e9b  lea     rcx, aNetpsetprimary; "NetpSetPrimarySamAccountName: failed to"...
0x180029ea2  jmp     loc_180029F2D
0x180029ea7  mov     rax, [rsp+88h+bufptr]
0x180029eac  mov     rcx, [rax+18h]
0x180029eb0  test    rcx, rcx
0x180029eb3  jz      loc_180029F3C
0x180029eb9  mov     rdx, rsi
0x180029ebc  call    cs:__imp__o__wcsicmp
0x180029ec3  nop     dword ptr [rax+rax+00h]
0x180029ec8  test    eax, eax
0x180029eca  jz      short loc_180029F3C
0x180029ecc  lea     r9, [rsp+88h+var_48]; buf
0x180029ed1  mov     qword ptr [rsp+88h+var_48], rsi
0x180029ed6  mov     r8d, 3F3h; level
0x180029edc  mov     [rsp+88h+parm_err], 0; parm_err
0x180029ee5  mov     rdx, rsi; username
0x180029ee8  mov     rcx, rbx; servername
0x180029eeb  call    cs:__imp_NetUserSetInfo
0x180029ef2  nop     dword ptr [rax+rax+00h]
0x180029ef7  mov     esi, eax
0x180029ef9  test    eax, eax
0x180029efb  jz      short loc_180029F3C
0x180029efd  call    IsNetpManageIPCConnectPresent
0x180029f02  test    al, al
0x180029f04  jz      short loc_180029F3C
0x180029f06  mov     r8d, esi
0x180029f09  lea     rcx, aNetpsetprimary_0; "NetpSetPrimarySamAccountName: failed to"...
0x180029f10  jmp     short loc_180029F2D
0x180029f12  mov     edi, 32h ; '2'
0x180029f17  xor     r14b, r14b
0x180029f1a  call    IsNetpManageIPCConnectPresent
0x180029f1f  test    al, al
0x180029f21  jz      short loc_180029F3C
0x180029f23  lea     rcx, aNetpsetprimary_1; "NetpSetPrimarySamAccountName: NetpManag"...
0x180029f2a  mov     r8d, edi
0x180029f2d  mov     rdx, rbx
0x180029f30  call    cs:__imp_NetpLogPrintHelper
0x180029f37  nop     dword ptr [rax+rax+00h]
0x180029f3c  mov     rcx, [rsp+88h+bufptr]; Buffer
0x180029f41  test    rcx, rcx
0x180029f44  jz      short loc_180029F52
0x180029f46  call    cs:__imp_NetApiBufferFree
0x180029f4d  nop     dword ptr [rax+rax+00h]
0x180029f52  test    r14b, r14b
0x180029f55  jz      short loc_180029F9F
0x180029f57  mov     r8, [rsp+88h+arg_20]
0x180029f5f  mov     r9d, 2
0x180029f65  mov     rdx, r15
0x180029f68  mov     rcx, rbx
0x180029f6b  call    cs:__imp_NetpManageIPCConnect
0x180029f72  nop     dword ptr [rax+rax+00h]
0x180029f77  mov     esi, eax
0x180029f79  test    eax, eax
0x180029f7b  jz      short loc_180029F9F
0x180029f7d  call    IsNetpManageIPCConnectPresent
0x180029f82  test    al, al
0x180029f84  jz      short loc_180029F9F
0x180029f86  mov     r8d, esi
0x180029f89  lea     rcx, aNetpsetprimary_2; "NetpSetPrimarySamAccountName: NetpManag"...
0x180029f90  mov     rdx, rbx
0x180029f93  call    cs:__imp_NetpLogPrintHelper
0x180029f9a  nop     dword ptr [rax+rax+00h]
0x180029f9f  mov     eax, edi
0x180029fa1  add     rsp, 58h
0x180029fa5  pop     r15
0x180029fa7  pop     r14
0x180029fa9  pop     rdi
0x180029faa  pop     rsi
0x180029fab  pop     rbp
0x180029fac  pop     rbx
0x180029fad  retn
```
