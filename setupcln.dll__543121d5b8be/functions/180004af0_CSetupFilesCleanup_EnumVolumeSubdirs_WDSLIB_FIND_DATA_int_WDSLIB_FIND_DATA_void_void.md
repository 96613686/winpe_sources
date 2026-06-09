# CSetupFilesCleanup::EnumVolumeSubdirs(_WDSLIB_FIND_DATA *,int (*)(_WDSLIB_FIND_DATA *,void *),void *)

- ea: `0x180004af0`
- end: `0x180004b7c`
- name: `?EnumVolumeSubdirs@CSetupFilesCleanup@@CAHPEAU_WDSLIB_FIND_DATA@@P6AH0PEAX@Z1@Z`
- size: `140`
- prototype: `_BOOL8 __fastcall(struct _WDSLIB_FIND_DATA *, int (*)(struct _WDSLIB_FIND_DATA *, void *), int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004af0`
- `0x1800059f8`
- `0x180006868`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b69`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004b33`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004b33`

## string_xrefs

- `0x180004b15`: `Windows.old`

## pseudocode

```c
_BOOL8 __fastcall CSetupFilesCleanup::EnumVolumeSubdirs(
        struct _WDSLIB_FIND_DATA *a1,
        int (*a2)(struct _WDSLIB_FIND_DATA *, void *),
        int *a3)
{
  if ( a3 && *((_QWORD *)a3 + 2) && a1 )
  {
    if ( CompareStringW(0x409u, 1u, *((PCNZWCH *)a1 + 6), -1, L"Windows.old", -1) == 2
      || (unsigned int)IsWindowsOldPattern(*((_QWORD *)a1 + 6)) )
    {
      SetupClnEnum(a3, *((const char **)a1 + 5));
    }
    return **((_DWORD **)a3 + 2) == 0;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180004af0  mov     [rsp+arg_0], rbx
0x180004af5  push    rdi
0x180004af6  sub     rsp, 30h
0x180004afa  mov     rbx, r8
0x180004afd  mov     rdi, rcx
0x180004b00  test    r8, r8
0x180004b03  jz      short loc_180004B64
0x180004b05  cmp     qword ptr [r8+10h], 0
0x180004b0a  jz      short loc_180004B64
0x180004b0c  test    rcx, rcx
0x180004b0f  jz      short loc_180004B64
0x180004b11  mov     r8, [rcx+30h]; lpString1
0x180004b15  lea     rax, aWindowsOld_0; "Windows.old"
0x180004b1c  or      r9d, 0FFFFFFFFh; cchCount1
0x180004b20  mov     ecx, 409h; Locale
0x180004b25  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180004b2a  mov     [rsp+38h+lpString2], rax; lpString2
0x180004b2f  lea     edx, [r9+2]; dwCmpFlags
0x180004b33  call    cs:__imp_CompareStringW
0x180004b39  cmp     eax, 2
0x180004b3c  jz      short loc_180004B4B
0x180004b3e  mov     rcx, [rdi+30h]
0x180004b42  call    IsWindowsOldPattern
0x180004b47  test    eax, eax
0x180004b49  jz      short loc_180004B57
0x180004b4b  mov     rdx, [rdi+28h]
0x180004b4f  mov     rcx, rbx
0x180004b52  call    SetupClnEnum
0x180004b57  mov     rcx, [rbx+10h]
0x180004b5b  xor     eax, eax
0x180004b5d  cmp     [rcx], eax
0x180004b5f  setz    al
0x180004b62  jmp     short loc_180004B71
0x180004b64  mov     ecx, 57h ; 'W'; dwErrCode
0x180004b69  call    cs:__imp_SetLastError
0x180004b6f  xor     eax, eax
0x180004b71  mov     rbx, [rsp+38h+arg_0]
0x180004b76  add     rsp, 30h
0x180004b7a  pop     rdi
0x180004b7b  retn
```
