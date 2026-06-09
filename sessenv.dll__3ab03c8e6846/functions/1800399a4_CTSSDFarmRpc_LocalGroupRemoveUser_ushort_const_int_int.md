# CTSSDFarmRpc::LocalGroupRemoveUser(ushort const *,int,int *)

- ea: `0x1800399a4`
- end: `0x180039af3`
- name: `?LocalGroupRemoveUser@CTSSDFarmRpc@@AEAAJPEBGHPEAH@Z`
- size: `335`
- prototype: `int(CTSSDFarmRpc *__hidden this, const unsigned __int16 *, int, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180002730`
- `0x180038628`
- `0x180038c44`

## callees

- `0x180003f30`
- `0x1800392b4`
- `0x1800399a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800399ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800399ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039ac8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039ad8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039ac8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039ad8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800399e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800399e0`
- `samcli!NetLocalGroupDelMembers` at `0x180039a84`
- `samcli!NetLocalGroupDelMembers` at `0x180039a84`

## string_xrefs

- `0x180039a03`: `ConvertStringSidToSid pszUserSid failed: 0x%x in %s`
- `0x180039a51`: `GetLocalGroupNameFromSid failed: 0x%x in %s`
- `0x180039a0d`: `CTSSDFarmRpc::LocalGroupRemoveUser`
- `0x180039a47`: `CTSSDFarmRpc::LocalGroupRemoveUser`

## pseudocode

```c
__int64 __fastcall CTSSDFarmRpc::LocalGroupRemoveUser(CTSSDFarmRpc *this, const unsigned __int16 *a2, int a3, int *a4)
{
  WCHAR *v4; // rdi
  int v7; // ebp
  CTSSDFarmRpc *v8; // rcx
  signed int LastError; // eax
  unsigned int v10; // ebx
  int LocalGroupNameFromSid; // eax
  signed int v12; // eax
  BYTE buf[40]; // [rsp+30h] [rbp-28h] BYREF
  LPCWSTR groupname; // [rsp+60h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  hMem = 0;
  v4 = 0;
  *(_QWORD *)buf = 0;
  groupname = 0;
  v7 = 0;
  if ( ConvertStringSidToSidW(a2, &hMem) )
    goto LABEL_6;
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  if ( (v10 & 0x80000000) == 0 )
  {
LABEL_6:
    *(_QWORD *)buf = hMem;
    LocalGroupNameFromSid = CTSSDFarmRpc::GetLocalGroupNameFromSid(
                              v8,
                              (enum WELL_KNOWN_SID_TYPE)(a3 != 0
                                                       ? WinBuiltinAdministratorsSid
                                                       : WinBuiltinRemoteDesktopUsersSid),
                              (unsigned __int16 **)&groupname);
    v10 = LocalGroupNameFromSid;
    if ( LocalGroupNameFromSid >= 0 )
    {
      v4 = (WCHAR *)groupname;
      v12 = NetLocalGroupDelMembers(0, groupname, 0, buf, 1u);
      if ( v12 )
      {
        if ( v12 != 1377 )
        {
          if ( v12 > 0 )
            v10 = (unsigned __int16)v12 | 0x80070000;
          else
            v10 = v12;
          _DbgPrintMessage(8, "NetLocalGroupDelMembers failed: 0x%x in %s", v10, "CTSSDFarmRpc::LocalGroupRemoveUser");
        }
      }
      else
      {
        v7 = 1;
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "GetLocalGroupNameFromSid failed: 0x%x in %s",
        LocalGroupNameFromSid,
        "CTSSDFarmRpc::LocalGroupRemoveUser");
      v4 = (WCHAR *)groupname;
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "ConvertStringSidToSid pszUserSid failed: 0x%x in %s",
      v10,
      "CTSSDFarmRpc::LocalGroupRemoveUser");
  }
  if ( a4 )
    *a4 = v7;
  if ( v4 )
    LocalFree(v4);
  if ( hMem )
    LocalFree(hMem);
  return v10;
}

```

## disassembly

```asm
0x1800399a4  mov     rax, rsp
0x1800399a7  mov     [rax+10h], rbx
0x1800399ab  mov     [rax+18h], rbp
0x1800399af  mov     [rax+8], rcx
0x1800399b3  push    rsi
0x1800399b4  push    rdi
0x1800399b5  push    r14
0x1800399b7  sub     rsp, 40h
0x1800399bb  mov     rcx, rdx; StringSid
0x1800399be  mov     qword ptr [rax+20h], 0
0x1800399c6  xor     edi, edi
0x1800399c8  mov     qword ptr [rax-28h], 0
0x1800399d0  lea     rdx, [rax+20h]; Sid
0x1800399d4  mov     [rax+8], rdi
0x1800399d8  mov     r14, r9
0x1800399db  mov     esi, r8d
0x1800399de  xor     ebp, ebp
0x1800399e0  call    cs:__imp_ConvertStringSidToSidW
0x1800399e6  test    eax, eax
0x1800399e8  jnz     short loc_180039A23
0x1800399ea  call    cs:__imp_GetLastError
0x1800399f0  mov     ebx, eax
0x1800399f2  test    eax, eax
0x1800399f4  jle     short loc_1800399FF
0x1800399f6  movzx   ebx, ax
0x1800399f9  or      ebx, 80070000h
0x1800399ff  test    ebx, ebx
0x180039a01  jns     short loc_180039A23
0x180039a03  lea     rdx, aConvertstrings_3; "ConvertStringSidToSid pszUserSid failed"...
0x180039a0a  mov     r8d, ebx
0x180039a0d  lea     r9, aCtssdfarmrpcLo_0; "CTSSDFarmRpc::LocalGroupRemoveUser"
0x180039a14  mov     ecx, 8; int
0x180039a19  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039a1e  jmp     loc_180039AB8
0x180039a23  mov     rax, [rsp+58h+hMem]
0x180039a28  lea     r8, [rsp+58h+groupname]; unsigned __int16 **
0x180039a2d  neg     esi
0x180039a2f  mov     qword ptr [rsp+58h+buf], rax
0x180039a34  sbb     edx, edx
0x180039a36  and     edx, 0FFFFFFF6h
0x180039a39  add     edx, 24h ; '$'; enum WELL_KNOWN_SID_TYPE
0x180039a3c  call    ?GetLocalGroupNameFromSid@CTSSDFarmRpc@@AEAAJW4WELL_KNOWN_SID_TYPE@@PEAPEAG@Z; CTSSDFarmRpc::GetLocalGroupNameFromSid(WELL_KNOWN_SID_TYPE,ushort * *)
0x180039a41  mov     ebx, eax
0x180039a43  test    eax, eax
0x180039a45  jns     short loc_180039A69
0x180039a47  lea     r9, aCtssdfarmrpcLo_0; "CTSSDFarmRpc::LocalGroupRemoveUser"
0x180039a4e  mov     r8d, eax
0x180039a51  lea     rdx, aGetlocalgroupn; "GetLocalGroupNameFromSid failed: 0x%x i"...
0x180039a58  mov     ecx, 8; int
0x180039a5d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039a62  mov     rdi, [rsp+58h+groupname]
0x180039a67  jmp     short loc_180039AB8
0x180039a69  mov     rdi, [rsp+58h+groupname]
0x180039a6e  lea     r9, [rsp+58h+buf]; buf
0x180039a73  mov     esi, 1
0x180039a78  mov     rdx, rdi; groupname
0x180039a7b  xor     r8d, r8d; level
0x180039a7e  mov     [rsp+58h+totalentries], esi; totalentries
0x180039a82  xor     ecx, ecx; servername
0x180039a84  call    cs:__imp_NetLocalGroupDelMembers
0x180039a8a  test    eax, eax
0x180039a8c  jz      short loc_180039AB6
0x180039a8e  cmp     eax, 561h
0x180039a93  jz      short loc_180039AB8
0x180039a95  test    eax, eax
0x180039a97  jg      short loc_180039A9D
0x180039a99  mov     ebx, eax
0x180039a9b  jmp     short loc_180039AA6
0x180039a9d  movzx   ebx, ax
0x180039aa0  or      ebx, 80070000h
0x180039aa6  test    ebx, ebx
0x180039aa8  jns     short loc_180039AB6
0x180039aaa  lea     rdx, aNetlocalgroupd_0; "NetLocalGroupDelMembers failed: 0x%x in"...
0x180039ab1  jmp     loc_180039A0A
0x180039ab6  mov     ebp, esi
0x180039ab8  test    r14, r14
0x180039abb  jz      short loc_180039AC0
0x180039abd  mov     [r14], ebp
0x180039ac0  test    rdi, rdi
0x180039ac3  jz      short loc_180039ACE
0x180039ac5  mov     rcx, rdi; hMem
0x180039ac8  call    cs:__imp_LocalFree
0x180039ace  mov     rcx, [rsp+58h+hMem]; hMem
0x180039ad3  test    rcx, rcx
0x180039ad6  jz      short loc_180039ADE
0x180039ad8  call    cs:__imp_LocalFree
0x180039ade  mov     rbp, [rsp+58h+arg_10]
0x180039ae3  mov     eax, ebx
0x180039ae5  mov     rbx, [rsp+58h+arg_8]
0x180039aea  add     rsp, 40h
0x180039aee  pop     r14
0x180039af0  pop     rdi
0x180039af1  pop     rsi
0x180039af2  retn
```
