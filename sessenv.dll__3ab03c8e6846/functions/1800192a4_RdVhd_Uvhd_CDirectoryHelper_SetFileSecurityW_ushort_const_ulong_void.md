# RdVhd::Uvhd::CDirectoryHelper::SetFileSecurityW(ushort const *,ulong,void *)

- ea: `0x1800192a4`
- end: `0x18001938c`
- name: `?SetFileSecurityW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBGKPEAX@Z`
- size: `232`
- prototype: `int(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004f3d0`
- `0x18004f96c`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x1800192a4`
- `0x180019b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019311`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800192c4`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180019368`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800192c4`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180019368`

## string_xrefs

- `0x18001933b`: `SetFileSecurityW failed for path '%s'. Trying with long path`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::SetFileSecurityW(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        __int64 a3,
        void *a4)
{
  unsigned int v6; // ebx
  signed int LastError; // eax
  const WCHAR *v8; // rax
  void **v10; // [rsp+20h] [rbp-38h] BYREF
  __int128 v11; // [rsp+28h] [rbp-30h]
  __int64 v12; // [rsp+38h] [rbp-20h]
  __int64 v13; // [rsp+40h] [rbp-18h]

  v6 = SetFileSecurityW(a2, 4u, a4);
  if ( !v6 && GetLastError() == 123 )
  {
    *(_QWORD *)((char *)&v11 + 4) = 128;
    v10 = &CPathString::`vftable';
    v12 = 0;
    HIDWORD(v11) = v6;
    LODWORD(v13) = 0x8000000;
    LODWORD(v11) = v6;
    LastError = GetLastError();
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastError = LastError & 0x8000FFFF | 0x502E0000;
    }
    _TraceNrmRdvVmEx(
      L"UVHD",
      LastError,
      L"SetFileSecurityW failed for path '%s'. Trying with long path",
      a2,
      v10,
      v11,
      v12,
      v13);
    v8 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a2, (struct CPathString *)&v10);
    v6 = SetFileSecurityW(v8, 4u, a4);
    CPathString::~CPathString((CPathString *)&v10);
  }
  return v6;
}

```

## disassembly

```asm
0x1800192a4  mov     [rsp+arg_0], rbx
0x1800192a9  mov     [rsp+arg_8], rsi
0x1800192ae  push    rdi
0x1800192af  sub     rsp, 50h
0x1800192b3  mov     rsi, r9
0x1800192b6  mov     rdi, rdx
0x1800192b9  mov     r8, r9; pSecurityDescriptor
0x1800192bc  mov     edx, 4; SecurityInformation
0x1800192c1  mov     rcx, rdi; lpFileName
0x1800192c4  call    cs:__imp_SetFileSecurityW
0x1800192ca  mov     ebx, eax
0x1800192cc  test    eax, eax
0x1800192ce  jnz     loc_18001937A
0x1800192d4  call    cs:__imp_GetLastError
0x1800192da  cmp     eax, 7Bh ; '{'
0x1800192dd  jnz     loc_18001937A
0x1800192e3  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x1800192ea  mov     qword ptr [rsp+58h+var_30+4], 80h
0x1800192f3  mov     [rsp+58h+var_38], rax
0x1800192f8  mov     [rsp+58h+var_20], 0
0x180019301  mov     dword ptr [rsp+58h+var_30+0Ch], ebx
0x180019305  mov     dword ptr [rsp+58h+var_18], 8000000h
0x18001930d  mov     dword ptr [rsp+58h+var_30], ebx
0x180019311  call    cs:__imp_GetLastError
0x180019317  test    eax, eax
0x180019319  jz      short loc_180019338
0x18001931b  test    eax, 0FFFF0000h
0x180019320  jnz     short loc_180019338
0x180019322  test    eax, eax
0x180019324  jle     short loc_18001932E
0x180019326  movzx   eax, ax
0x180019329  or      eax, 80070000h
0x18001932e  and     eax, 0D02EFFFFh
0x180019333  or      eax, 502E0000h
0x180019338  mov     r9, rdi
0x18001933b  lea     r8, aSetfilesecurit; "SetFileSecurityW failed for path '%s'. "...
0x180019342  mov     edx, eax; int
0x180019344  lea     rcx, aUvhd; "UVHD"
0x18001934b  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180019350  lea     rdx, [rsp+58h+var_38]; struct CPathString *
0x180019355  mov     rcx, rdi; unsigned __int16 *
0x180019358  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x18001935d  mov     rcx, rax; lpFileName
0x180019360  mov     r8, rsi; pSecurityDescriptor
0x180019363  mov     edx, 4; SecurityInformation
0x180019368  call    cs:__imp_SetFileSecurityW
0x18001936e  lea     rcx, [rsp+58h+var_38]; this
0x180019373  mov     ebx, eax
0x180019375  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18001937a  mov     rsi, [rsp+58h+arg_8]
0x18001937f  mov     eax, ebx
0x180019381  mov     rbx, [rsp+58h+arg_0]
0x180019386  add     rsp, 50h
0x18001938a  pop     rdi
0x18001938b  retn
```
