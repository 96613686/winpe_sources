# NetpSetPrimarySamAccountName

- ea: `0x180027ac8`
- end: `0x180027c7d`
- name: `NetpSetPrimarySamAccountName`
- size: `437`
- prototype: `__int64 __fastcall(LPCWSTR servername, LPCWSTR username, LPCWSTR, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180026840`

## callees

- `0x18002016c`
- `0x180027ac8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027baf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027baf`
- `netutils!NetApiBufferFree` at `0x180027c27`
- `netutils!NetApiBufferFree` at `0x180027c27`
- `samcli!NetUserGetInfo` at `0x180027b79`
- `samcli!NetUserGetInfo` at `0x180027b79`
- `samcli!NetUserSetInfo` at `0x180027b43`
- `samcli!NetUserSetInfo` at `0x180027bd8`
- `samcli!NetUserSetInfo` at `0x180027b43`
- `samcli!NetUserSetInfo` at `0x180027bd8`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027c17`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027c68`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027c17`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027c68`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpManageIPCConnect` at `0x180027b17`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpManageIPCConnect` at `0x180027c46`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpManageIPCConnect` at `0x180027b17`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpManageIPCConnect` at `0x180027c46`

## string_xrefs

- `0x180027bf0`: `NetpSetPrimarySamAccountName: failed to update display name on %ws (ignored) 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetpSetPrimarySamAccountName(
        LPCWSTR servername,
        LPCWSTR username,
        LPCWSTR a3,
        __int64 a4,
        __int64 a5)
{
  char v9; // r14
  DWORD v10; // edi
  const wchar_t *v11; // rcx
  DWORD Info; // ebp
  __int64 v13; // rcx
  DWORD v14; // esi
  unsigned int v15; // esi
  LPBYTE bufptr; // [rsp+30h] [rbp-58h] BYREF
  BYTE buf[8]; // [rsp+38h] [rbp-50h] BYREF
  BYTE v19[72]; // [rsp+40h] [rbp-48h] BYREF

  *(_QWORD *)buf = 0;
  bufptr = 0;
  if ( !IsNetpManageIPCConnectPresent() )
  {
    v10 = 50;
    goto LABEL_15;
  }
  v9 = 1;
  v10 = NetpManageIPCConnect(servername, a4, a5, 1);
  if ( v10 )
  {
LABEL_15:
    v9 = 0;
    if ( !IsNetpManageIPCConnectPresent() )
      goto LABEL_18;
    v11 = L"NetpSetPrimarySamAccountName: NetpManageIPCConnect failed to connect to %ws: 0x%lx\n";
    goto LABEL_17;
  }
  *(_QWORD *)buf = a3;
  v10 = NetUserSetInfo(servername, username, 0, buf, 0);
  if ( v10 )
  {
    if ( !IsNetpManageIPCConnectPresent() )
      goto LABEL_18;
    v11 = L"NetpSetPrimarySamAccountName: NetUserSetInfo failed on %ws: 0x%lx\n";
LABEL_17:
    NetpLogPrintHelper(v11, servername, v10);
    goto LABEL_18;
  }
  Info = NetUserGetInfo(servername, a3, 0xAu, &bufptr);
  if ( Info )
  {
    if ( IsNetpManageIPCConnectPresent() )
      NetpLogPrintHelper(
        L"NetpSetPrimarySamAccountName: failed to get display name on %ws (ignored) 0x%lx\n",
        servername,
        Info);
  }
  else
  {
    v13 = *((_QWORD *)bufptr + 3);
    if ( v13 )
    {
      if ( (unsigned int)_o__wcsicmp(v13, a3) )
      {
        *(_QWORD *)v19 = a3;
        v14 = NetUserSetInfo(servername, a3, 0x3F3u, v19, 0);
        if ( v14 )
        {
          if ( IsNetpManageIPCConnectPresent() )
            NetpLogPrintHelper(
              L"NetpSetPrimarySamAccountName: failed to update display name on %ws (ignored) 0x%lx\n",
              servername,
              v14);
        }
      }
    }
  }
LABEL_18:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  if ( v9 )
  {
    v15 = NetpManageIPCConnect(servername, a4, a5, 2);
    if ( v15 )
    {
      if ( IsNetpManageIPCConnectPresent() )
        NetpLogPrintHelper(
          L"NetpSetPrimarySamAccountName: NetpManageIPCConnect failed to disconnect from %ws: 0x%lx\n",
          servername,
          v15);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180027ac8  push    rbx
0x180027aca  push    rbp
0x180027acb  push    rsi
0x180027acc  push    rdi
0x180027acd  push    r14
0x180027acf  push    r15
0x180027ad1  sub     rsp, 58h
0x180027ad5  mov     r15, r9
0x180027ad8  mov     qword ptr [rsp+88h+buf], 0
0x180027ae1  mov     rsi, r8
0x180027ae4  mov     [rsp+88h+bufptr], 0
0x180027aed  mov     rbp, rdx
0x180027af0  mov     rbx, rcx
0x180027af3  call    IsNetpManageIPCConnectPresent
0x180027af8  test    al, al
0x180027afa  jz      loc_180027BF9
0x180027b00  mov     r8, [rsp+88h+arg_20]
0x180027b08  mov     r14d, 1
0x180027b0e  mov     r9d, r14d
0x180027b11  mov     rdx, r15
0x180027b14  mov     rcx, rbx
0x180027b17  call    cs:__imp_NetpManageIPCConnect
0x180027b1d  mov     edi, eax
0x180027b1f  test    eax, eax
0x180027b21  jnz     loc_180027BFE
0x180027b27  lea     r9, [rsp+88h+buf]; buf
0x180027b2c  mov     qword ptr [rsp+88h+buf], rsi
0x180027b31  xor     r8d, r8d; level
0x180027b34  mov     [rsp+88h+parm_err], 0; parm_err
0x180027b3d  mov     rdx, rbp; username
0x180027b40  mov     rcx, rbx; servername
0x180027b43  call    cs:__imp_NetUserSetInfo
0x180027b49  mov     edi, eax
0x180027b4b  test    eax, eax
0x180027b4d  jz      short loc_180027B68
0x180027b4f  call    IsNetpManageIPCConnectPresent
0x180027b54  test    al, al
0x180027b56  jz      loc_180027C1D
0x180027b5c  lea     rcx, aNetpsetprimary_3; "NetpSetPrimarySamAccountName: NetUserSe"...
0x180027b63  jmp     loc_180027C11
0x180027b68  lea     r9, [rsp+88h+bufptr]; bufptr
0x180027b6d  mov     r8d, 0Ah; level
0x180027b73  mov     rdx, rsi; username
0x180027b76  mov     rcx, rbx; servername
0x180027b79  call    cs:__imp_NetUserGetInfo
0x180027b7f  mov     ebp, eax
0x180027b81  test    eax, eax
0x180027b83  jz      short loc_180027B9E
0x180027b85  call    IsNetpManageIPCConnectPresent
0x180027b8a  test    al, al
0x180027b8c  jz      loc_180027C1D
0x180027b92  mov     r8d, ebp
0x180027b95  lea     rcx, aNetpsetprimary; "NetpSetPrimarySamAccountName: failed to"...
0x180027b9c  jmp     short loc_180027C14
0x180027b9e  mov     rax, [rsp+88h+bufptr]
0x180027ba3  mov     rcx, [rax+18h]
0x180027ba7  test    rcx, rcx
0x180027baa  jz      short loc_180027C1D
0x180027bac  mov     rdx, rsi
0x180027baf  call    cs:__imp__o__wcsicmp
0x180027bb5  test    eax, eax
0x180027bb7  jz      short loc_180027C1D
0x180027bb9  lea     r9, [rsp+88h+var_48]; buf
0x180027bbe  mov     qword ptr [rsp+88h+var_48], rsi
0x180027bc3  mov     r8d, 3F3h; level
0x180027bc9  mov     [rsp+88h+parm_err], 0; parm_err
0x180027bd2  mov     rdx, rsi; username
0x180027bd5  mov     rcx, rbx; servername
0x180027bd8  call    cs:__imp_NetUserSetInfo
0x180027bde  mov     esi, eax
0x180027be0  test    eax, eax
0x180027be2  jz      short loc_180027C1D
0x180027be4  call    IsNetpManageIPCConnectPresent
0x180027be9  test    al, al
0x180027beb  jz      short loc_180027C1D
0x180027bed  mov     r8d, esi
0x180027bf0  lea     rcx, aNetpsetprimary_0; "NetpSetPrimarySamAccountName: failed to"...
0x180027bf7  jmp     short loc_180027C14
0x180027bf9  mov     edi, 32h ; '2'
0x180027bfe  xor     r14b, r14b
0x180027c01  call    IsNetpManageIPCConnectPresent
0x180027c06  test    al, al
0x180027c08  jz      short loc_180027C1D
0x180027c0a  lea     rcx, aNetpsetprimary_1; "NetpSetPrimarySamAccountName: NetpManag"...
0x180027c11  mov     r8d, edi
0x180027c14  mov     rdx, rbx
0x180027c17  call    cs:__imp_NetpLogPrintHelper
0x180027c1d  mov     rcx, [rsp+88h+bufptr]; Buffer
0x180027c22  test    rcx, rcx
0x180027c25  jz      short loc_180027C2D
0x180027c27  call    cs:__imp_NetApiBufferFree
0x180027c2d  test    r14b, r14b
0x180027c30  jz      short loc_180027C6E
0x180027c32  mov     r8, [rsp+88h+arg_20]
0x180027c3a  mov     r9d, 2
0x180027c40  mov     rdx, r15
0x180027c43  mov     rcx, rbx
0x180027c46  call    cs:__imp_NetpManageIPCConnect
0x180027c4c  mov     esi, eax
0x180027c4e  test    eax, eax
0x180027c50  jz      short loc_180027C6E
0x180027c52  call    IsNetpManageIPCConnectPresent
0x180027c57  test    al, al
0x180027c59  jz      short loc_180027C6E
0x180027c5b  mov     r8d, esi
0x180027c5e  lea     rcx, aNetpsetprimary_2; "NetpSetPrimarySamAccountName: NetpManag"...
0x180027c65  mov     rdx, rbx
0x180027c68  call    cs:__imp_NetpLogPrintHelper
0x180027c6e  mov     eax, edi
0x180027c70  add     rsp, 58h
0x180027c74  pop     r15
0x180027c76  pop     r14
0x180027c78  pop     rdi
0x180027c79  pop     rsi
0x180027c7a  pop     rbp
0x180027c7b  pop     rbx
0x180027c7c  retn
```
