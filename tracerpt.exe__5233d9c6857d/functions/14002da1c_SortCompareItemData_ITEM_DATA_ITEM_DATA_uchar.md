# SortCompareItemData(_ITEM_DATA *,_ITEM_DATA *,uchar)

- ea: `0x14002da1c`
- end: `0x14002dc61`
- name: `?SortCompareItemData@@YAJPEAU_ITEM_DATA@@0E@Z`
- size: `581`
- prototype: `__int64 __fastcall(struct _ITEM_DATA *, struct _ITEM_DATA *, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400294e0`
- `0x14002dcec`

## callees

- `0x14002d650`
- `0x14002d754`
- `0x14002da1c`
- `0x14002dc68`
- `0x140032488`
- `0x140040130`
- `0x1400401c0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14002dc37`
- `msvcrt!_wcsnicmp` at `0x14002dc37`
- `msvcrt!_strnicmp` at `0x14002dc23`
- `msvcrt!_strnicmp` at `0x14002dc23`
- `msvcrt!_wcsicmp` at `0x14002db37`
- `msvcrt!_wcsicmp` at `0x14002db37`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14002db7e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14002db8d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14002db7e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14002db8d`

## pseudocode

```c
int __fastcall SortCompareItemData(struct _ITEM_DATA *a1, struct _ITEM_DATA *a2, char a3)
{
  int v3; // eax
  double v5; // xmm0_8
  double v6; // xmm1_8
  int v8; // r9d
  unsigned __int16 v9; // ax
  unsigned __int16 v10; // ax
  char v11; // r8
  char v12; // [rsp+20h] [rbp-E0h]
  struct _FILETIME v13; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t String2[2048]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t String1[2048]; // [rsp+1040h] [rbp+F40h] BYREF

  v3 = 0;
  FileTime = 0;
  v13 = 0;
  if ( !*((_BYTE *)a1 + 25) )
  {
    if ( *(_WORD *)a1 == 1 )
      return _wcsnicmp(*((const wchar_t **)a1 + 1), *((const wchar_t **)a2 + 1), *((unsigned int *)a1 + 4));
    if ( *(_WORD *)a1 == 22 )
      return _wcsnicmp(*((const wchar_t **)a1 + 1), *((const wchar_t **)a2 + 1), *((unsigned int *)a1 + 4));
    v8 = 85;
    v9 = *(_WORD *)a1 - 300;
    if ( v9 <= 6u )
    {
      if ( _bittest(&v8, v9) )
        return _wcsnicmp(*((const wchar_t **)a1 + 1), *((const wchar_t **)a2 + 1), *((unsigned int *)a1 + 4));
    }
    if ( *(_WORD *)a1 == 2 )
      return _strnicmp(*((const char **)a1 + 1), *((const char **)a2 + 1), *((unsigned int *)a1 + 4));
    if ( *(_WORD *)a1 == 23 )
      return _strnicmp(*((const char **)a1 + 1), *((const char **)a2 + 1), *((unsigned int *)a1 + 4));
    v10 = *(_WORD *)a1 - 301;
    if ( v10 <= 6u )
    {
      if ( _bittest(&v8, v10) )
        return _strnicmp(*((const char **)a1 + 1), *((const char **)a2 + 1), *((unsigned int *)a1 + 4));
    }
    switch ( *(_WORD *)a1 )
    {
      case 0xF:
        CpdiGuidToString(String1, 0x800u, *((struct _GUID **)a1 + 1));
        CpdiGuidToString(String2, 0x800u, *((struct _GUID **)a2 + 1));
        return _wcsicmp(String1, String2);
      case 0x11:
        v12 = 1;
        break;
      case 0x12:
        SystemTimeToFileTime(*((const SYSTEMTIME **)a1 + 1), &FileTime);
        SystemTimeToFileTime(*((const SYSTEMTIME **)a2 + 1), &v13);
        return SortCompareMemory((char *)&FileTime, 8u, (char *)&v13, 8u, 1);
      case 0x13:
        PrintSidToString(*((unsigned __int8 **)a1 + 1), String1);
        PrintSidToString(*((unsigned __int8 **)a2 + 1), String2);
        return _wcsicmp(String1, String2);
      case 0x136:
        PrintWbemSidToString(*((unsigned __int8 **)a1 + 1), String1, a3, *((_DWORD *)a1 + 7));
        PrintWbemSidToString(*((unsigned __int8 **)a2 + 1), String2, v11, *((_DWORD *)a2 + 7));
        return _wcsicmp(String1, String2);
      default:
        v12 = a3;
        break;
    }
    return SortCompareMemory(*((char **)a1 + 1), *((_WORD *)a1 + 8), *((char **)a2 + 1), *((_WORD *)a2 + 8), v12);
  }
  v5 = *((double *)a2 + 1);
  v6 = *((double *)a1 + 1);
  if ( v6 > v5 )
    return 1;
  LOBYTE(v3) = v5 <= v6;
  return v3 - 1;
}

```

## disassembly

```asm
0x14002da1c  mov     [rsp-8+arg_10], rbx
0x14002da21  mov     [rsp-8+arg_18], rdi
0x14002da26  push    rbp
0x14002da27  lea     rbp, [rsp-1F50h]
0x14002da2f  mov     eax, 2050h
0x14002da34  call    _alloca_probe
0x14002da39  sub     rsp, rax
0x14002da3c  mov     rax, cs:__security_cookie
0x14002da43  xor     rax, rsp
0x14002da46  mov     [rbp+1F50h+var_10], rax
0x14002da4d  xor     eax, eax
0x14002da4f  mov     rdi, rdx
0x14002da52  mov     qword ptr [rsp+2050h+FileTime.dwLowDateTime], rax
0x14002da57  mov     qword ptr [rsp+2050h+var_2020.dwLowDateTime], rax
0x14002da5c  cmp     [rcx+19h], al
0x14002da5f  jz      short loc_14002DA8E
0x14002da61  movsd   xmm0, qword ptr [rdx+8]
0x14002da66  movsd   xmm1, qword ptr [rcx+8]
0x14002da6b  comisd  xmm1, xmm0
0x14002da6f  jbe     short loc_14002DA7B
0x14002da71  mov     eax, 1
0x14002da76  jmp     loc_14002DC3D
0x14002da7b  comisd  xmm0, xmm1
0x14002da7f  mov     ebx, 1
0x14002da84  setbe   al
0x14002da87  sub     eax, ebx
0x14002da89  jmp     loc_14002DC3D
0x14002da8e  mov     ebx, 1
0x14002da93  cmp     [rcx], bx
0x14002da96  jz      loc_14002DC2B
0x14002da9c  cmp     word ptr [rcx], 16h
0x14002daa0  jz      loc_14002DC2B
0x14002daa6  movzx   eax, word ptr [rcx]
0x14002daa9  lea     r9d, [rbx+54h]
0x14002daad  mov     edx, 12Ch
0x14002dab2  sub     ax, dx
0x14002dab5  cmp     ax, 6
0x14002dab9  ja      short loc_14002DAC8
0x14002dabb  movzx   eax, ax
0x14002dabe  bt      r9d, eax
0x14002dac2  jb      loc_14002DC2B
0x14002dac8  cmp     word ptr [rcx], 2
0x14002dacc  jz      loc_14002DC17
0x14002dad2  cmp     word ptr [rcx], 17h
0x14002dad6  jz      loc_14002DC17
0x14002dadc  movzx   eax, word ptr [rcx]
0x14002dadf  mov     edx, 12Dh
0x14002dae4  sub     ax, dx
0x14002dae7  cmp     ax, 6
0x14002daeb  ja      short loc_14002DAFA
0x14002daed  movzx   eax, ax
0x14002daf0  bt      r9d, eax
0x14002daf4  jb      loc_14002DC17
0x14002dafa  mov     eax, 0Fh
0x14002daff  cmp     ax, [rcx]
0x14002db02  jnz     short loc_14002DB42
0x14002db04  mov     r8, [rcx+8]; struct _GUID *
0x14002db08  mov     ebx, 800h
0x14002db0d  mov     edx, ebx; unsigned int
0x14002db0f  lea     rcx, [rbp+1F50h+String1]; unsigned __int16 *
0x14002db16  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x14002db1b  mov     r8, [rdi+8]; struct _GUID *
0x14002db1f  lea     rcx, [rsp+2050h+String2]; unsigned __int16 *
0x14002db24  mov     edx, ebx; unsigned int
0x14002db26  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x14002db2b  lea     rdx, [rsp+2050h+String2]; String2
0x14002db30  lea     rcx, [rbp+1F50h+String1]; String1
0x14002db37  call    cs:__imp__wcsicmp
0x14002db3d  jmp     loc_14002DC3D
0x14002db42  mov     eax, 11h
0x14002db47  cmp     ax, [rcx]
0x14002db4a  jnz     short loc_14002DB6B
0x14002db4c  mov     [rsp+2050h+var_2030], bl; char
0x14002db50  movzx   edx, word ptr [rcx+10h]; unsigned __int16
0x14002db54  mov     rcx, [rcx+8]; char *
0x14002db58  movzx   r9d, word ptr [rdi+10h]; unsigned __int16
0x14002db5d  mov     r8, [rdi+8]; char *
0x14002db61  call    ?SortCompareMemory@@YAJPEADG0GE@Z; SortCompareMemory(char *,ushort,char *,ushort,uchar)
0x14002db66  jmp     loc_14002DC3D
0x14002db6b  mov     eax, 12h
0x14002db70  cmp     ax, [rcx]
0x14002db73  jnz     short loc_14002DBAB
0x14002db75  mov     rcx, [rcx+8]; lpSystemTime
0x14002db79  lea     rdx, [rsp+2050h+FileTime]; lpFileTime
0x14002db7e  call    cs:__imp_SystemTimeToFileTime
0x14002db84  mov     rcx, [rdi+8]; lpSystemTime
0x14002db88  lea     rdx, [rsp+2050h+var_2020]; lpFileTime
0x14002db8d  call    cs:__imp_SystemTimeToFileTime
0x14002db93  mov     edx, 8
0x14002db98  mov     [rsp+2050h+var_2030], bl
0x14002db9c  mov     r9d, edx
0x14002db9f  lea     r8, [rsp+2050h+var_2020]
0x14002dba4  lea     rcx, [rsp+2050h+FileTime]
0x14002dba9  jmp     short loc_14002DB61
0x14002dbab  mov     eax, 13h
0x14002dbb0  cmp     ax, [rcx]
0x14002dbb3  jnz     short loc_14002DBD8
0x14002dbb5  mov     rcx, [rcx+8]; unsigned __int8 *
0x14002dbb9  lea     rdx, [rbp+1F50h+String1]; unsigned __int16 *
0x14002dbc0  call    ?PrintSidToString@@YAKPEAEPEAGK@Z; PrintSidToString(uchar *,ushort *,ulong)
0x14002dbc5  mov     rcx, [rdi+8]; unsigned __int8 *
0x14002dbc9  lea     rdx, [rsp+2050h+String2]; unsigned __int16 *
0x14002dbce  call    ?PrintSidToString@@YAKPEAEPEAGK@Z; PrintSidToString(uchar *,ushort *,ulong)
0x14002dbd3  jmp     loc_14002DB2B
0x14002dbd8  mov     eax, 136h
0x14002dbdd  cmp     ax, [rcx]
0x14002dbe0  jnz     short loc_14002DC0D
0x14002dbe2  mov     r9d, [rcx+1Ch]; unsigned int
0x14002dbe6  lea     rdx, [rbp+1F50h+String1]; unsigned __int16 *
0x14002dbed  mov     rcx, [rcx+8]; unsigned __int8 *
0x14002dbf1  call    ?PrintWbemSidToString@@YAKPEAEPEAGKK@Z; PrintWbemSidToString(uchar *,ushort *,ulong,ulong)
0x14002dbf6  mov     r9d, [rdi+1Ch]; unsigned int
0x14002dbfa  lea     rdx, [rsp+2050h+String2]; unsigned __int16 *
0x14002dbff  mov     rcx, [rdi+8]; unsigned __int8 *
0x14002dc03  call    ?PrintWbemSidToString@@YAKPEAEPEAGKK@Z; PrintWbemSidToString(uchar *,ushort *,ulong,ulong)
0x14002dc08  jmp     loc_14002DB2B
0x14002dc0d  mov     [rsp+2050h+var_2030], r8b
0x14002dc12  jmp     loc_14002DB50
0x14002dc17  mov     r8d, [rcx+10h]; MaxCount
0x14002dc1b  mov     rcx, [rcx+8]; String1
0x14002dc1f  mov     rdx, [rdi+8]; String2
0x14002dc23  call    cs:__imp__strnicmp
0x14002dc29  jmp     short loc_14002DC3D
0x14002dc2b  mov     r8d, [rcx+10h]; MaxCount
0x14002dc2f  mov     rcx, [rcx+8]; String1
0x14002dc33  mov     rdx, [rdi+8]; String2
0x14002dc37  call    cs:__imp__wcsnicmp
0x14002dc3d  mov     rcx, [rbp+1F50h+var_10]
0x14002dc44  xor     rcx, rsp; StackCookie
0x14002dc47  call    __security_check_cookie
0x14002dc4c  lea     r11, [rsp+2050h+var_s0]
0x14002dc54  mov     rbx, [r11+20h]
0x14002dc58  mov     rdi, [r11+28h]
0x14002dc5c  mov     rsp, r11
0x14002dc5f  pop     rbp
0x14002dc60  retn
```
