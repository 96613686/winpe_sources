# CTSSDFarmRpc::LocalGroupAddUser(ushort const *,int,int *)

- ea: `0x18003984c`
- end: `0x18003999b`
- name: `?LocalGroupAddUser@CTSSDFarmRpc@@AEAAJPEBGHPEAH@Z`
- size: `335`
- prototype: `int(CTSSDFarmRpc *__hidden this, const unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180038628`

## callees

- `0x180003f30`
- `0x1800392b4`
- `0x18003984c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039892`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039980`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039980`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180039888`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180039888`
- `samcli!NetLocalGroupAddMembers` at `0x18003992c`
- `samcli!NetLocalGroupAddMembers` at `0x18003992c`

## string_xrefs

- `0x1800398ab`: `ConvertStringSidToSid pszUserSid failed: 0x%x in %s`
- `0x1800398f9`: `GetLocalGroupNameFromSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSDFarmRpc::LocalGroupAddUser(CTSSDFarmRpc *this, const unsigned __int16 *a2, int a3, int *a4)
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
      v12 = NetLocalGroupAddMembers(0, groupname, 0, buf, 1u);
      if ( v12 )
      {
        if ( v12 != 1378 )
        {
          if ( v12 > 0 )
            v10 = (unsigned __int16)v12 | 0x80070000;
          else
            v10 = v12;
          _DbgPrintMessage(8, "NetLocalGroupAddMembers failed: 0x%x in %s", v10, "CTSSDFarmRpc::LocalGroupAddUser");
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
        "CTSSDFarmRpc::LocalGroupAddUser");
      v4 = (WCHAR *)groupname;
    }
  }
  else
  {
    _DbgPrintMessage(8, "ConvertStringSidToSid pszUserSid failed: 0x%x in %s", v10, "CTSSDFarmRpc::LocalGroupAddUser");
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
0x18003984c  mov     rax, rsp
0x18003984f  mov     [rax+10h], rbx
0x180039853  mov     [rax+18h], rbp
0x180039857  mov     [rax+8], rcx
0x18003985b  push    rsi
0x18003985c  push    rdi
0x18003985d  push    r14
0x18003985f  sub     rsp, 40h
0x180039863  mov     rcx, rdx; StringSid
0x180039866  mov     qword ptr [rax+20h], 0
0x18003986e  xor     edi, edi
0x180039870  mov     qword ptr [rax-28h], 0
0x180039878  lea     rdx, [rax+20h]; Sid
0x18003987c  mov     [rax+8], rdi
0x180039880  mov     r14, r9
0x180039883  mov     esi, r8d
0x180039886  xor     ebp, ebp
0x180039888  call    cs:__imp_ConvertStringSidToSidW
0x18003988e  test    eax, eax
0x180039890  jnz     short loc_1800398CB
0x180039892  call    cs:__imp_GetLastError
0x180039898  mov     ebx, eax
0x18003989a  test    eax, eax
0x18003989c  jle     short loc_1800398A7
0x18003989e  movzx   ebx, ax
0x1800398a1  or      ebx, 80070000h
0x1800398a7  test    ebx, ebx
0x1800398a9  jns     short loc_1800398CB
0x1800398ab  lea     rdx, aConvertstrings_3; "ConvertStringSidToSid pszUserSid failed"...
0x1800398b2  mov     r8d, ebx
0x1800398b5  lea     r9, aCtssdfarmrpcLo; "CTSSDFarmRpc::LocalGroupAddUser"
0x1800398bc  mov     ecx, 8; int
0x1800398c1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800398c6  jmp     loc_180039960
0x1800398cb  mov     rax, [rsp+58h+hMem]
0x1800398d0  lea     r8, [rsp+58h+groupname]; unsigned __int16 **
0x1800398d5  neg     esi
0x1800398d7  mov     qword ptr [rsp+58h+buf], rax
0x1800398dc  sbb     edx, edx
0x1800398de  and     edx, 0FFFFFFF6h
0x1800398e1  add     edx, 24h ; '$'; enum WELL_KNOWN_SID_TYPE
0x1800398e4  call    ?GetLocalGroupNameFromSid@CTSSDFarmRpc@@AEAAJW4WELL_KNOWN_SID_TYPE@@PEAPEAG@Z; CTSSDFarmRpc::GetLocalGroupNameFromSid(WELL_KNOWN_SID_TYPE,ushort * *)
0x1800398e9  mov     ebx, eax
0x1800398eb  test    eax, eax
0x1800398ed  jns     short loc_180039911
0x1800398ef  lea     r9, aCtssdfarmrpcLo; "CTSSDFarmRpc::LocalGroupAddUser"
0x1800398f6  mov     r8d, eax
0x1800398f9  lea     rdx, aGetlocalgroupn; "GetLocalGroupNameFromSid failed: 0x%x i"...
0x180039900  mov     ecx, 8; int
0x180039905  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003990a  mov     rdi, [rsp+58h+groupname]
0x18003990f  jmp     short loc_180039960
0x180039911  mov     rdi, [rsp+58h+groupname]
0x180039916  lea     r9, [rsp+58h+buf]; buf
0x18003991b  mov     esi, 1
0x180039920  mov     rdx, rdi; groupname
0x180039923  xor     r8d, r8d; level
0x180039926  mov     [rsp+58h+totalentries], esi; totalentries
0x18003992a  xor     ecx, ecx; servername
0x18003992c  call    cs:__imp_NetLocalGroupAddMembers
0x180039932  test    eax, eax
0x180039934  jz      short loc_18003995E
0x180039936  cmp     eax, 562h
0x18003993b  jz      short loc_180039960
0x18003993d  test    eax, eax
0x18003993f  jg      short loc_180039945
0x180039941  mov     ebx, eax
0x180039943  jmp     short loc_18003994E
0x180039945  movzx   ebx, ax
0x180039948  or      ebx, 80070000h
0x18003994e  test    ebx, ebx
0x180039950  jns     short loc_18003995E
0x180039952  lea     rdx, aNetlocalgroupa_0; "NetLocalGroupAddMembers failed: 0x%x in"...
0x180039959  jmp     loc_1800398B2
0x18003995e  mov     ebp, esi
0x180039960  test    r14, r14
0x180039963  jz      short loc_180039968
0x180039965  mov     [r14], ebp
0x180039968  test    rdi, rdi
0x18003996b  jz      short loc_180039976
0x18003996d  mov     rcx, rdi; hMem
0x180039970  call    cs:__imp_LocalFree
0x180039976  mov     rcx, [rsp+58h+hMem]; hMem
0x18003997b  test    rcx, rcx
0x18003997e  jz      short loc_180039986
0x180039980  call    cs:__imp_LocalFree
0x180039986  mov     rbp, [rsp+58h+arg_10]
0x18003998b  mov     eax, ebx
0x18003998d  mov     rbx, [rsp+58h+arg_8]
0x180039992  add     rsp, 40h
0x180039996  pop     r14
0x180039998  pop     rdi
0x180039999  pop     rsi
0x18003999a  retn
```
