# RdVhd::Uvhd::CDirectoryHelper::CreateSymbolicLinkW(ushort const *,ushort const *,ulong)

- ea: `0x18004d880`
- end: `0x18004da00`
- name: `?CreateSymbolicLinkW@CDirectoryHelper@Uvhd@RdVhd@@UEBAJPEBG0K@Z`
- size: `384`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CDirectoryHelper *this, const unsigned __int16 *, const unsigned __int16 *, DWORD)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180019b00`
- `0x180048b28`
- `0x18004d880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d977`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18004d8a5`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18004d96d`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18004d8a5`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18004d96d`

## string_xrefs

- `0x18004d934`: `CreateSymbolicLink failed for path '%s' '%s'. Trying with long path`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::CreateSymbolicLinkW(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4)
{
  unsigned int v7; // edi
  signed int LastError; // eax
  const WCHAR *v9; // rbx
  const WCHAR *v10; // rax
  signed int v11; // eax
  void **v13; // [rsp+30h] [rbp-50h] BYREF
  int v14; // [rsp+38h] [rbp-48h]
  __int64 v15; // [rsp+3Ch] [rbp-44h]
  int v16; // [rsp+44h] [rbp-3Ch]
  __int64 v17; // [rsp+48h] [rbp-38h]
  int v18; // [rsp+50h] [rbp-30h]
  void **v19; // [rsp+58h] [rbp-28h] BYREF
  int v20; // [rsp+60h] [rbp-20h]
  __int64 v21; // [rsp+64h] [rbp-1Ch]
  int v22; // [rsp+6Ch] [rbp-14h]
  __int64 v23; // [rsp+70h] [rbp-10h]
  int v24; // [rsp+78h] [rbp-8h]

  v7 = 0;
  if ( !CreateSymbolicLinkW(a2, a3, a4) && GetLastError() == 3 )
  {
    v21 = 128;
    v24 = 0x8000000;
    v19 = &CPathString::`vftable';
    v18 = 0x8000000;
    v13 = &CPathString::`vftable';
    v23 = 0;
    v22 = 0;
    v20 = 0;
    v15 = 128;
    v17 = 0;
    v16 = 0;
    v14 = 0;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v7 = v7 & 0x8000FFFF | 0x502C0000;
    }
    _TraceNrmRdvVmEx(L"UVHD", v7, L"CreateSymbolicLink failed for path '%s' '%s'. Trying with long path", a2, a3);
    v9 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a3, (struct CPathString *)&v13);
    v10 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a2, (struct CPathString *)&v19);
    if ( !CreateSymbolicLinkW(v10, v9, a4) )
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 && (v11 & 0xFFFF0000) == 0 )
      {
        if ( v11 > 0 )
          v7 = (unsigned __int16)v11 | 0x80070000;
        v7 = v7 & 0x8000FFFF | 0x50160000;
      }
      if ( (v7 & 0x80000000) != 0
        && WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, v7);
      }
    }
    CPathString::~CPathString((CPathString *)&v13);
    CPathString::~CPathString((CPathString *)&v19);
  }
  return v7;
}

```

## disassembly

```asm
0x18004d880  push    rbp
0x18004d882  push    rbx
0x18004d883  push    rsi
0x18004d884  push    rdi
0x18004d885  push    r14
0x18004d887  mov     rbp, rsp
0x18004d88a  sub     rsp, 80h
0x18004d891  mov     r14d, r9d
0x18004d894  mov     rbx, r8
0x18004d897  mov     rsi, rdx
0x18004d89a  xor     edi, edi
0x18004d89c  mov     r8d, r9d; dwFlags
0x18004d89f  mov     rdx, rbx; lpTargetFileName
0x18004d8a2  mov     rcx, rsi; lpSymlinkFileName
0x18004d8a5  call    cs:__imp_CreateSymbolicLinkW
0x18004d8ab  test    al, al
0x18004d8ad  jnz     loc_18004D9F0
0x18004d8b3  call    cs:__imp_GetLastError
0x18004d8b9  cmp     eax, 3
0x18004d8bc  jnz     loc_18004D9F0
0x18004d8c2  mov     ecx, 8000000h
0x18004d8c7  mov     [rbp+var_1C], 80h
0x18004d8cf  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x18004d8d6  mov     [rbp+var_8], ecx
0x18004d8d9  mov     [rbp+var_28], rax
0x18004d8dd  mov     [rbp+var_30], ecx
0x18004d8e0  mov     [rbp+var_50], rax
0x18004d8e4  mov     [rbp+var_10], rdi
0x18004d8e8  mov     [rbp+var_14], edi
0x18004d8eb  mov     [rbp+var_20], edi
0x18004d8ee  mov     [rbp+var_44], 80h
0x18004d8f6  mov     [rbp+var_38], rdi
0x18004d8fa  mov     [rbp+var_3C], edi
0x18004d8fd  mov     [rbp+var_48], edi
0x18004d900  call    cs:__imp_GetLastError
0x18004d906  mov     edi, eax
0x18004d908  test    eax, eax
0x18004d90a  jz      short loc_18004D92C
0x18004d90c  test    eax, 0FFFF0000h
0x18004d911  jnz     short loc_18004D92C
0x18004d913  test    eax, eax
0x18004d915  jle     short loc_18004D920
0x18004d917  movzx   edi, ax
0x18004d91a  or      edi, 80070000h
0x18004d920  and     edi, 0D02CFFFFh
0x18004d926  or      edi, 502C0000h
0x18004d92c  mov     r9, rsi
0x18004d92f  mov     [rsp+80h+var_60], rbx
0x18004d934  lea     r8, aCreatesymbolic; "CreateSymbolicLink failed for path '%s'"...
0x18004d93b  mov     edx, edi; int
0x18004d93d  lea     rcx, aUvhd; "UVHD"
0x18004d944  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18004d949  lea     rdx, [rbp+var_50]; struct CPathString *
0x18004d94d  mov     rcx, rbx; unsigned __int16 *
0x18004d950  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x18004d955  lea     rdx, [rbp+var_28]; struct CPathString *
0x18004d959  mov     rcx, rsi; unsigned __int16 *
0x18004d95c  mov     rbx, rax
0x18004d95f  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x18004d964  mov     r8d, r14d; dwFlags
0x18004d967  mov     rdx, rbx; lpTargetFileName
0x18004d96a  mov     rcx, rax; lpSymlinkFileName
0x18004d96d  call    cs:__imp_CreateSymbolicLinkW
0x18004d973  test    al, al
0x18004d975  jnz     short loc_18004D9DE
0x18004d977  call    cs:__imp_GetLastError
0x18004d97d  mov     edi, eax
0x18004d97f  test    eax, eax
0x18004d981  jz      short loc_18004D9A3
0x18004d983  test    eax, 0FFFF0000h
0x18004d988  jnz     short loc_18004D9A3
0x18004d98a  test    eax, eax
0x18004d98c  jle     short loc_18004D997
0x18004d98e  movzx   edi, ax
0x18004d991  or      edi, 80070000h
0x18004d997  and     edi, 0D016FFFFh
0x18004d99d  or      edi, 50160000h
0x18004d9a3  test    edi, edi
0x18004d9a5  jns     short loc_18004D9DE
0x18004d9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d9ae  lea     rax, WPP_GLOBAL_Control
0x18004d9b5  cmp     rcx, rax
0x18004d9b8  jz      short loc_18004D9DE
0x18004d9ba  test    byte ptr [rcx+1Ch], 4
0x18004d9be  jz      short loc_18004D9DE
0x18004d9c0  cmp     byte ptr [rcx+19h], 2
0x18004d9c4  jb      short loc_18004D9DE
0x18004d9c6  mov     rcx, [rcx+10h]
0x18004d9ca  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004d9d1  mov     edx, 73h ; 's'
0x18004d9d6  mov     r9d, edi
0x18004d9d9  call    WPP_SF_d
0x18004d9de  lea     rcx, [rbp+var_50]; this
0x18004d9e2  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18004d9e7  lea     rcx, [rbp+var_28]; this
0x18004d9eb  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18004d9f0  mov     eax, edi
0x18004d9f2  add     rsp, 80h
0x18004d9f9  pop     r14
0x18004d9fb  pop     rdi
0x18004d9fc  pop     rsi
0x18004d9fd  pop     rbx
0x18004d9fe  pop     rbp
0x18004d9ff  retn
```
