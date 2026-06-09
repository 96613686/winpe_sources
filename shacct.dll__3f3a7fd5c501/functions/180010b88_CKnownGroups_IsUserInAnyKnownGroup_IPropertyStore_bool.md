# CKnownGroups::IsUserInAnyKnownGroup(IPropertyStore *,bool *)

- ea: `0x180010b88`
- end: `0x180010cdc`
- name: `?IsUserInAnyKnownGroup@CKnownGroups@@QEBAJPEAUIPropertyStore@@PEA_N@Z`
- size: `340`
- prototype: `__int64 __fastcall(CKnownGroups *__hidden this, struct IPropertyStore *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b410`

## callees

- `0x180010b88`
- `0x1800117ec`
- `0x180016880`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180010c3b`
- `ntdll!RtlNtStatusToDosError` at `0x180010c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010cc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010cc7`
- `samcli!NetUserGetLocalGroups` at `0x180010c11`
- `samcli!NetUserGetLocalGroups` at `0x180010c11`
- `netutils!NetApiBufferFree` at `0x180010cbd`
- `netutils!NetApiBufferFree` at `0x180010cbd`

## pseudocode

```c
__int64 __fastcall CKnownGroups::IsUserInAnyKnownGroup(CKnownGroups *this, struct IPropertyStore *a2, bool *a3)
{
  signed int String; // ebx
  DWORD LocalGroups; // eax
  __int64 i; // rcx
  NTSTATUS v8; // ecx
  signed int v9; // eax
  CKnownGroups *v10; // rcx
  bool IsGroupInGroupList; // al
  CKnownGroups *v12; // rcx
  bool v13; // al
  CKnownGroups *v14; // rcx
  bool v15; // al
  CKnownGroups *v16; // rcx
  LPBYTE bufptr; // [rsp+40h] [rbp-10h] BYREF
  LPCWSTR username; // [rsp+48h] [rbp-8h] BYREF
  DWORD entriesread; // [rsp+80h] [rbp+30h] BYREF
  DWORD totalentries; // [rsp+88h] [rbp+38h] BYREF

  *a3 = 0;
  username = 0;
  String = IPropertyStore_GetString(a2, &PKEY_SAM_Name, &username);
  if ( String >= 0 )
  {
    entriesread = 0;
    totalentries = 0;
    bufptr = 0;
    LocalGroups = NetUserGetLocalGroups(0, username, 0, 1u, &bufptr, 0xFFFFFFFF, &entriesread, &totalentries);
    for ( i = 0; (unsigned int)i < 0x7A; i = (unsigned int)(i + 1) )
    {
      if ( LODWORD(ErrorMap[i]) == LocalGroups )
      {
        v8 = HIDWORD(ErrorMap[i]);
        goto LABEL_8;
      }
    }
    v8 = -1073741595;
LABEL_8:
    v9 = RtlNtStatusToDosError(v8);
    String = v9;
    if ( v9 > 0 )
      String = (unsigned __int16)v9 | 0x80070000;
    if ( String >= 0 )
    {
      IsGroupInGroupList = CKnownGroups::_IsGroupInGroupList(
                             v10,
                             (const unsigned __int16 *)this + 257,
                             (struct _LOCALGROUP_USERS_INFO_0 *)bufptr,
                             entriesread);
      *a3 = IsGroupInGroupList;
      if ( !IsGroupInGroupList )
      {
        v13 = CKnownGroups::_IsGroupInGroupList(
                v12,
                (const unsigned __int16 *)this,
                (struct _LOCALGROUP_USERS_INFO_0 *)bufptr,
                entriesread);
        *a3 = v13;
        if ( !v13 )
        {
          v15 = CKnownGroups::_IsGroupInGroupList(
                  v14,
                  (const unsigned __int16 *)this + 514,
                  (struct _LOCALGROUP_USERS_INFO_0 *)bufptr,
                  entriesread);
          *a3 = v15;
          if ( !v15 )
            *a3 = CKnownGroups::_IsGroupInGroupList(
                    v16,
                    (const unsigned __int16 *)this + 771,
                    (struct _LOCALGROUP_USERS_INFO_0 *)bufptr,
                    entriesread);
        }
      }
    }
    if ( bufptr )
      NetApiBufferFree(bufptr);
    CoTaskMemFree((LPVOID)username);
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180010b88  mov     [rsp-18h+arg_0], rbx
0x180010b8d  push    rbp
0x180010b8e  push    rsi
0x180010b8f  push    rdi
0x180010b90  mov     rbp, rsp
0x180010b93  sub     rsp, 50h
0x180010b97  mov     rax, rdx
0x180010b9a  mov     byte ptr [r8], 0
0x180010b9e  mov     rdi, r8
0x180010ba1  mov     [rbp+username], 0
0x180010ba9  mov     rsi, rcx
0x180010bac  lea     r8, [rbp+username]
0x180010bb0  mov     rcx, rax
0x180010bb3  lea     rdx, PKEY_SAM_Name
0x180010bba  call    IPropertyStore_GetString
0x180010bbf  mov     ebx, eax
0x180010bc1  test    eax, eax
0x180010bc3  js      loc_180010CCD
0x180010bc9  mov     rdx, [rbp+username]; username
0x180010bcd  lea     rax, [rbp+arg_18]
0x180010bd1  mov     [rsp+50h+totalentries], rax; totalentries
0x180010bd6  mov     r9d, 1; flags
0x180010bdc  lea     rax, [rbp+arg_10]
0x180010be0  mov     [rbp+arg_10], 0
0x180010be7  mov     [rsp+50h+entriesread], rax; entriesread
0x180010bec  xor     r8d, r8d; level
0x180010bef  lea     rax, [rbp+var_10]
0x180010bf3  mov     [rsp+50h+prefmaxlen], 0FFFFFFFFh; prefmaxlen
0x180010bfb  xor     ecx, ecx; servername
0x180010bfd  mov     [rsp+50h+bufptr], rax; bufptr
0x180010c02  mov     [rbp+arg_18], 0
0x180010c09  mov     [rbp+var_10], 0
0x180010c11  call    cs:__imp_NetUserGetLocalGroups
0x180010c17  xor     ecx, ecx
0x180010c19  lea     r8, ErrorMap
0x180010c20  cmp     ecx, 7Ah ; 'z'
0x180010c23  jnb     short loc_180010C36
0x180010c25  cmp     [r8+rcx*8], eax
0x180010c29  jz      short loc_180010C2F
0x180010c2b  inc     ecx
0x180010c2d  jmp     short loc_180010C20
0x180010c2f  mov     ecx, [r8+rcx*8+4]
0x180010c34  jmp     short loc_180010C3B
0x180010c36  mov     ecx, 0C00000E5h; Status
0x180010c3b  call    cs:__imp_RtlNtStatusToDosError
0x180010c41  mov     ebx, eax
0x180010c43  test    eax, eax
0x180010c45  jle     short loc_180010C50
0x180010c47  movzx   ebx, ax
0x180010c4a  or      ebx, 80070000h
0x180010c50  test    ebx, ebx
0x180010c52  js      short loc_180010CB4
0x180010c54  mov     r9d, [rbp+arg_10]; unsigned int
0x180010c58  lea     rdx, [rsi+202h]; unsigned __int16 *
0x180010c5f  mov     r8, [rbp+var_10]; struct _LOCALGROUP_USERS_INFO_0 *
0x180010c63  call    ?_IsGroupInGroupList@CKnownGroups@@AEBA_NPEBGPEAU_LOCALGROUP_USERS_INFO_0@@K@Z; CKnownGroups::_IsGroupInGroupList(ushort const *,_LOCALGROUP_USERS_INFO_0 *,ulong)
0x180010c68  mov     [rdi], al
0x180010c6a  test    al, al
0x180010c6c  jnz     short loc_180010CB4
0x180010c6e  mov     r9d, [rbp+arg_10]; unsigned int
0x180010c72  mov     rdx, rsi; unsigned __int16 *
0x180010c75  mov     r8, [rbp+var_10]; struct _LOCALGROUP_USERS_INFO_0 *
0x180010c79  call    ?_IsGroupInGroupList@CKnownGroups@@AEBA_NPEBGPEAU_LOCALGROUP_USERS_INFO_0@@K@Z; CKnownGroups::_IsGroupInGroupList(ushort const *,_LOCALGROUP_USERS_INFO_0 *,ulong)
0x180010c7e  mov     [rdi], al
0x180010c80  test    al, al
0x180010c82  jnz     short loc_180010CB4
0x180010c84  mov     r9d, [rbp+arg_10]; unsigned int
0x180010c88  lea     rdx, [rsi+404h]; unsigned __int16 *
0x180010c8f  mov     r8, [rbp+var_10]; struct _LOCALGROUP_USERS_INFO_0 *
0x180010c93  call    ?_IsGroupInGroupList@CKnownGroups@@AEBA_NPEBGPEAU_LOCALGROUP_USERS_INFO_0@@K@Z; CKnownGroups::_IsGroupInGroupList(ushort const *,_LOCALGROUP_USERS_INFO_0 *,ulong)
0x180010c98  mov     [rdi], al
0x180010c9a  test    al, al
0x180010c9c  jnz     short loc_180010CB4
0x180010c9e  mov     r9d, [rbp+arg_10]; unsigned int
0x180010ca2  lea     rdx, [rsi+606h]; unsigned __int16 *
0x180010ca9  mov     r8, [rbp+var_10]; struct _LOCALGROUP_USERS_INFO_0 *
0x180010cad  call    ?_IsGroupInGroupList@CKnownGroups@@AEBA_NPEBGPEAU_LOCALGROUP_USERS_INFO_0@@K@Z; CKnownGroups::_IsGroupInGroupList(ushort const *,_LOCALGROUP_USERS_INFO_0 *,ulong)
0x180010cb2  mov     [rdi], al
0x180010cb4  mov     rcx, [rbp+var_10]; Buffer
0x180010cb8  test    rcx, rcx
0x180010cbb  jz      short loc_180010CC3
0x180010cbd  call    cs:__imp_NetApiBufferFree
0x180010cc3  mov     rcx, [rbp+username]; pv
0x180010cc7  call    cs:__imp_CoTaskMemFree
0x180010ccd  mov     eax, ebx
0x180010ccf  mov     rbx, [rsp+50h+arg_0]
0x180010cd4  add     rsp, 50h
0x180010cd8  pop     rdi
0x180010cd9  pop     rsi
0x180010cda  pop     rbp
0x180010cdb  retn
```
