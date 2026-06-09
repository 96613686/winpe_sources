# SaveRepository(ushort *,ulong)

- ea: `0x1800149e8`
- end: `0x180014b77`
- name: `?SaveRepository@@YAJPEAGK@Z`
- size: `399`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000dcdc`

## callees

- `0x180003b08`
- `0x180007bc4`
- `0x18000b4f4`
- `0x180012c34`
- `0x1800142c0`
- `0x1800149e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014aba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014aba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014af5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014af5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014aaa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014aaa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014a19`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014b37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014a19`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014b37`
- `wbemcomn!GetMemLogObject` at `0x180014a09`
- `wbemcomn!GetMemLogObject` at `0x180014b2c`
- `wbemcomn!GetMemLogObject` at `0x180014a09`
- `wbemcomn!GetMemLogObject` at `0x180014b2c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800149fb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800149fb`

## string_xrefs

- `0x180014a89`: `%sTempBackup.%lu`

## pseudocode

```c
__int64 __fastcall SaveRepository(unsigned __int16 *a1)
{
  WCHAR *v2; // rax
  const unsigned __int16 *v3; // rsi
  CMemoryLog *v4; // rax
  int RepositoryDirectory; // ebx
  int i; // r14d
  int v8; // edi
  CMemoryLog *MemLogObject; // rax
  __int64 v10; // [rsp+20h] [rbp-68h]
  _QWORD v11[2]; // [rsp+30h] [rbp-58h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-48h] BYREF

  v2 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
  v3 = v2;
  if ( v2 )
  {
    v11[0] = v2;
    v11[1] = 0;
    RepositoryDirectory = GetRepositoryDirectory(v2);
    if ( RepositoryDirectory < 0 )
    {
LABEL_17:
      v8 = RepositoryDirectory;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        LODWORD(v10) = i;
        v8 = StringCchPrintfW(a1, 0x105u, L"%sTempBackup.%lu", v3, v10);
        if ( v8 < 0 )
          break;
        if ( GetFileAttributesW(a1) == -1 )
        {
          if ( GetLastError() != 2 )
            RepositoryDirectory = -2147217407;
          *(_QWORD *)&SecurityAttributes.nLength = 24;
          SecurityAttributes.lpSecurityDescriptor = &g_DirSD;
          *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
          if ( RepositoryDirectory >= 0 )
          {
            if ( CreateDirectoryW(a1, &SecurityAttributes) )
              RepositoryDirectory = MoveRepositoryFiles(v3, a1, 1);
            else
              RepositoryDirectory = -2147217407;
          }
          goto LABEL_17;
        }
      }
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v8);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids,
          (unsigned int)v8);
      }
    }
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v11);
    return (unsigned int)v8;
  }
  else
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2147217402);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x1800149e8  push    rbx
0x1800149ea  push    rbp
0x1800149eb  push    rsi
0x1800149ec  push    rdi
0x1800149ed  push    r14
0x1800149ef  sub     rsp, 60h
0x1800149f3  mov     rbp, rcx
0x1800149f6  mov     ecx, 20Ah
0x1800149fb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014a01  mov     rsi, rax
0x180014a04  test    rax, rax
0x180014a07  jnz     short loc_180014A5E
0x180014a09  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014a0f  mov     ebx, 80041006h
0x180014a14  mov     edx, ebx
0x180014a16  mov     rcx, rax
0x180014a19  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014a1f  lea     rax, WPP_GLOBAL_Control
0x180014a26  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a2d  cmp     rcx, rax
0x180014a30  jz      short loc_180014A57
0x180014a32  test    byte ptr [rcx+1Ch], 1
0x180014a36  jz      short loc_180014A57
0x180014a38  cmp     byte ptr [rcx+19h], 2
0x180014a3c  jb      short loc_180014A57
0x180014a3e  lea     edx, [rsi+35h]
0x180014a41  mov     r9d, 80041006h
0x180014a47  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x180014a4e  mov     rcx, [rcx+10h]
0x180014a52  call    WPP_SF_d
0x180014a57  mov     eax, ebx
0x180014a59  jmp     loc_180014B0F
0x180014a5e  mov     [rsp+88h+var_58], rsi
0x180014a63  mov     [rsp+88h+var_50], 0
0x180014a6c  mov     rcx, rsi; lpDst
0x180014a6f  call    ?GetRepositoryDirectory@@YAJQEAG@Z; GetRepositoryDirectory(ushort * const)
0x180014a74  mov     ebx, eax
0x180014a76  test    eax, eax
0x180014a78  js      loc_180014B01
0x180014a7e  xor     r14d, r14d
0x180014a81  mov     [rsp+88h+var_68], r14d
0x180014a86  mov     r9, rsi
0x180014a89  lea     r8, aStempbackupLu; "%sTempBackup.%lu"
0x180014a90  mov     edx, 105h; unsigned __int64
0x180014a95  mov     rcx, rbp; unsigned __int16 *
0x180014a98  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014a9d  mov     edi, eax
0x180014a9f  test    eax, eax
0x180014aa1  js      loc_180014B2C
0x180014aa7  mov     rcx, rbp; lpFileName
0x180014aaa  call    cs:__imp_GetFileAttributesW
0x180014ab0  cmp     eax, 0FFFFFFFFh
0x180014ab3  jz      short loc_180014ABA
0x180014ab5  inc     r14d
0x180014ab8  jmp     short loc_180014A81
0x180014aba  call    cs:__imp_GetLastError
0x180014ac0  mov     edi, 80041001h
0x180014ac5  cmp     eax, 2
0x180014ac8  cmovnz  ebx, edi
0x180014acb  mov     qword ptr [rsp+88h+SecurityAttributes.nLength], 18h
0x180014ad4  lea     rax, ?g_DirSD@@3PAKA; ulong near * g_DirSD
0x180014adb  mov     [rsp+88h+SecurityAttributes.lpSecurityDescriptor], rax
0x180014ae0  mov     qword ptr [rsp+88h+SecurityAttributes.bInheritHandle], 0
0x180014ae9  test    ebx, ebx
0x180014aeb  js      short loc_180014B01
0x180014aed  lea     rdx, [rsp+88h+SecurityAttributes]; lpSecurityAttributes
0x180014af2  mov     rcx, rbp; lpPathName
0x180014af5  call    cs:__imp_CreateDirectoryW
0x180014afb  test    eax, eax
0x180014afd  jnz     short loc_180014B1A
0x180014aff  mov     ebx, edi
0x180014b01  mov     edi, ebx
0x180014b03  lea     rcx, [rsp+88h+var_58]
0x180014b08  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180014b0d  mov     eax, edi
0x180014b0f  add     rsp, 60h
0x180014b13  pop     r14
0x180014b15  pop     rdi
0x180014b16  pop     rsi
0x180014b17  pop     rbp
0x180014b18  pop     rbx
0x180014b19  retn
0x180014b1a  mov     r8b, 1; bool
0x180014b1d  mov     rdx, rbp; unsigned __int16 *
0x180014b20  mov     rcx, rsi; unsigned __int16 *
0x180014b23  call    ?MoveRepositoryFiles@@YAJPEBG0_N@Z; MoveRepositoryFiles(ushort const *,ushort const *,bool)
0x180014b28  mov     ebx, eax
0x180014b2a  jmp     short loc_180014B01
0x180014b2c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014b32  mov     edx, edi
0x180014b34  mov     rcx, rax
0x180014b37  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014b3d  lea     rax, WPP_GLOBAL_Control
0x180014b44  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b4b  cmp     rcx, rax
0x180014b4e  jz      short loc_180014B03
0x180014b50  test    byte ptr [rcx+1Ch], 1
0x180014b54  jz      short loc_180014B03
0x180014b56  cmp     byte ptr [rcx+19h], 2
0x180014b5a  jb      short loc_180014B03
0x180014b5c  mov     edx, 36h ; '6'
0x180014b61  mov     r9d, edi
0x180014b64  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x180014b6b  mov     rcx, [rcx+10h]
0x180014b6f  call    WPP_SF_d
0x180014b74  jmp     short loc_180014B03
```
