# HrMakeFullNonHardCodedPath(ushort * const,ushort *,uint)

- ea: `0x18000e8bc`
- end: `0x18000ebb8`
- name: `?HrMakeFullNonHardCodedPath@@YAJQEAGPEAGI@Z`
- size: `764`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000bac8`
- `0x18000daac`
- `0x18000f7c4`

## callees

- `0x180003b90`
- `0x180007820`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000e8bc`
- `0x180010768`
- `0x1800107e4`
- `0x18001236c`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000e99f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000e99f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnExpandEnvStringsW` at `0x18000eb0e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnExpandEnvStringsW` at `0x18000eb0e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000ea32`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000ea32`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000e93e`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000e93e`

## pseudocode

```c
__int64 __fastcall HrMakeFullNonHardCodedPath(LPCWSTR lpSrc, unsigned __int16 *a2)
{
  unsigned int LastErrorHRESULT; // edi
  _QWORD *v5; // rcx
  int v6; // edx
  WCHAR *v7; // r9
  DWORD FullPathNameW; // eax
  unsigned __int16 *v10; // rdi
  __int64 v11; // r8
  __int64 v12; // r8
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // r9
  char v15; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dest[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  memset_0(Dest, 0, 0x20Au);
  memset_0(Buffer, 0, 0x20Au);
  memset_0(a2, 0, 0x20Au);
  if ( !ExpandEnvironmentStringsForUserW(0, lpSrc, Dest, 0x105u) )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return LastErrorHRESULT;
    v6 = 107;
    LODWORD(v7) = (_DWORD)lpSrc;
LABEL_5:
    WPP_SF_SD(v5[2], v6, (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, (_DWORD)v7, LastErrorHRESULT);
    return LastErrorHRESULT;
  }
  FullPathNameW = GetFullPathNameW(Dest, 0x105u, Buffer, &FilePart);
  if ( !FullPathNameW )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return LastErrorHRESULT;
    v6 = 108;
    v7 = Dest;
    goto LABEL_5;
  }
  if ( FullPathNameW < 0x105 )
  {
    while ( 1 )
    {
      if ( PathFileExistsW(Buffer) )
      {
        if ( !PathUnExpandEnvStringsW(Buffer, a2, 0x105u) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v15 = GetLastErrorHRESULT();
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              113,
              (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
              (unsigned int)Buffer,
              v15);
          }
          *a2 = 0;
          StringCchCopyNW(a2, v13, Buffer, v14);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, 0);
        return 0;
      }
      v10 = wcsistr(Buffer, L"\\oobe\\");
      if ( !v10 )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, v11, Buffer);
      *v10 = 0;
      StringCchCopyW(v10, 261 - ((unsigned __int64)(v10 - Buffer) >> 1), v10 + 5);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, v12, Buffer);
    }
    LastErrorHRESULT = GetLastErrorHRESULT();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = 112;
      v7 = Buffer;
      goto LABEL_5;
    }
    return LastErrorHRESULT;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      109,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)Dest,
      14);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000e8bc  mov     [rsp-8+arg_10], rbx
0x18000e8c1  push    rbp
0x18000e8c2  push    rsi
0x18000e8c3  push    rdi
0x18000e8c4  push    r14
0x18000e8c6  push    r15
0x18000e8c8  lea     rbp, [rsp-370h]
0x18000e8d0  sub     rsp, 470h
0x18000e8d7  mov     rax, cs:__security_cookie
0x18000e8de  xor     rax, rsp
0x18000e8e1  mov     [rbp+390h+var_30], rax
0x18000e8e8  mov     rsi, rdx
0x18000e8eb  mov     [rsp+490h+FilePart], 0
0x18000e8f4  mov     r14, rcx
0x18000e8f7  mov     ebx, 20Ah
0x18000e8fc  mov     r8d, ebx; Size
0x18000e8ff  lea     rcx, [rbp+390h+Dest]; void *
0x18000e906  xor     edx, edx; Val
0x18000e908  call    memset_0
0x18000e90d  mov     r8d, ebx; Size
0x18000e910  lea     rcx, [rsp+490h+Buffer]; void *
0x18000e915  xor     edx, edx; Val
0x18000e917  call    memset_0
0x18000e91c  mov     r8d, ebx; Size
0x18000e91f  xor     edx, edx; Val
0x18000e921  mov     rcx, rsi; void *
0x18000e924  call    memset_0
0x18000e929  mov     r15d, 105h
0x18000e92f  lea     r8, [rbp+390h+Dest]; lpDest
0x18000e936  mov     r9d, r15d; dwSize
0x18000e939  mov     rdx, r14; lpSrc
0x18000e93c  xor     ecx, ecx; hToken
0x18000e93e  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18000e944  test    eax, eax
0x18000e946  jnz     short loc_18000E98B
0x18000e948  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000e94d  mov     edi, eax
0x18000e94f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e956  lea     rbx, WPP_GLOBAL_Control
0x18000e95d  cmp     rcx, rbx
0x18000e960  jz      short loc_18000E984
0x18000e962  test    byte ptr [rcx+1Ch], 4
0x18000e966  jz      short loc_18000E984
0x18000e968  mov     edx, 6Bh ; 'k'
0x18000e96d  mov     r9, r14
0x18000e970  mov     rcx, [rcx+10h]
0x18000e974  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000e97b  mov     [rsp+490h+var_470], edi
0x18000e97f  call    WPP_SF_SD
0x18000e984  mov     eax, edi
0x18000e986  jmp     loc_18000EB92
0x18000e98b  lea     r9, [rsp+490h+FilePart]; lpFilePart
0x18000e990  mov     edx, r15d; nBufferLength
0x18000e993  lea     r8, [rsp+490h+Buffer]; lpBuffer
0x18000e998  lea     rcx, [rbp+390h+Dest]; lpFileName
0x18000e99f  call    cs:__imp_GetFullPathNameW
0x18000e9a5  test    eax, eax
0x18000e9a7  jnz     short loc_18000E9D7
0x18000e9a9  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000e9ae  mov     edi, eax
0x18000e9b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9b7  lea     rbx, WPP_GLOBAL_Control
0x18000e9be  cmp     rcx, rbx
0x18000e9c1  jz      short loc_18000E984
0x18000e9c3  test    byte ptr [rcx+1Ch], 4
0x18000e9c7  jz      short loc_18000E984
0x18000e9c9  mov     edx, 6Ch ; 'l'
0x18000e9ce  lea     r9, [rbp+390h+Dest]
0x18000e9d5  jmp     short loc_18000E970
0x18000e9d7  cmp     eax, r15d
0x18000e9da  jb      short loc_18000EA23
0x18000e9dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9e3  lea     rbx, WPP_GLOBAL_Control
0x18000e9ea  cmp     rcx, rbx
0x18000e9ed  jz      short loc_18000EA19
0x18000e9ef  test    byte ptr [rcx+1Ch], 4
0x18000e9f3  jz      short loc_18000EA19
0x18000e9f5  mov     rcx, [rcx+10h]
0x18000e9f9  lea     r9, [rbp+390h+Dest]
0x18000ea00  mov     edx, 6Dh ; 'm'
0x18000ea05  mov     [rsp+490h+var_470], 8007000Eh
0x18000ea0d  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000ea14  call    WPP_SF_SD
0x18000ea19  mov     eax, 8007000Eh
0x18000ea1e  jmp     loc_18000EB92
0x18000ea23  lea     rbx, WPP_GLOBAL_Control
0x18000ea2a  mov     r14b, 10h
0x18000ea2d  lea     rcx, [rsp+490h+Buffer]; pszPath
0x18000ea32  call    cs:__imp_PathFileExistsW
0x18000ea38  lea     rcx, [rsp+490h+Buffer]; unsigned __int16 *
0x18000ea3d  test    eax, eax
0x18000ea3f  jnz     loc_18000EB08
0x18000ea45  lea     rdx, aOobe; "\\oobe\\"
0x18000ea4c  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000ea51  mov     rdi, rax
0x18000ea54  test    rax, rax
0x18000ea57  jz      short loc_18000EAD8
0x18000ea59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea60  cmp     rcx, rbx
0x18000ea63  jz      short loc_18000EA7E
0x18000ea65  test    [rcx+1Ch], r14b
0x18000ea69  jz      short loc_18000EA7E
0x18000ea6b  mov     rcx, [rcx+10h]
0x18000ea6f  lea     r9, [rsp+490h+Buffer]
0x18000ea74  mov     edx, 6Eh ; 'n'
0x18000ea79  call    WPP_SF_S
0x18000ea7e  xor     eax, eax
0x18000ea80  lea     rcx, [rsp+490h+Buffer]
0x18000ea85  mov     [rdi], ax
0x18000ea88  lea     r8, [rdi+0Ah]; unsigned __int16 *
0x18000ea8c  mov     rax, rdi
0x18000ea8f  mov     rdx, r15
0x18000ea92  sub     rax, rcx
0x18000ea95  mov     rcx, rdi; unsigned __int16 *
0x18000ea98  sar     rax, 1
0x18000ea9b  shr     rax, 1
0x18000ea9e  sub     rdx, rax; unsigned __int64
0x18000eaa1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000eaa6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eaad  cmp     rcx, rbx
0x18000eab0  jz      loc_18000EA2D
0x18000eab6  test    [rcx+1Ch], r14b
0x18000eaba  jz      loc_18000EA2D
0x18000eac0  mov     rcx, [rcx+10h]
0x18000eac4  lea     r9, [rsp+490h+Buffer]
0x18000eac9  mov     edx, 6Fh ; 'o'
0x18000eace  call    WPP_SF_S
0x18000ead3  jmp     loc_18000EA2D
0x18000ead8  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000eadd  mov     edi, eax
0x18000eadf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eae6  cmp     rcx, rbx
0x18000eae9  jz      loc_18000E984
0x18000eaef  test    byte ptr [rcx+1Ch], 4
0x18000eaf3  jz      loc_18000E984
0x18000eaf9  mov     edx, 70h ; 'p'
0x18000eafe  lea     r9, [rsp+490h+Buffer]
0x18000eb03  jmp     loc_18000E970
0x18000eb08  mov     r8d, r15d; cchBuf
0x18000eb0b  mov     rdx, rsi; pszBuf
0x18000eb0e  call    cs:__imp_PathUnExpandEnvStringsW
0x18000eb14  test    eax, eax
0x18000eb16  jnz     short loc_18000EB66
0x18000eb18  mov     rax, cs:WPP_GLOBAL_Control
0x18000eb1f  cmp     rax, rbx
0x18000eb22  jz      short loc_18000EB54
0x18000eb24  test    byte ptr [rax+1Ch], 4
0x18000eb28  jz      short loc_18000EB54
0x18000eb2a  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000eb2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb36  lea     r9, [rsp+490h+Buffer]
0x18000eb3b  mov     edx, 71h ; 'q'
0x18000eb40  mov     [rsp+490h+var_470], eax
0x18000eb44  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000eb4b  mov     rcx, [rcx+10h]
0x18000eb4f  call    WPP_SF_SD
0x18000eb54  xor     eax, eax
0x18000eb56  lea     r8, [rsp+490h+Buffer]; unsigned __int16 *
0x18000eb5b  mov     rcx, rsi; unsigned __int16 *
0x18000eb5e  mov     [rsi], ax
0x18000eb61  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000eb66  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb6d  cmp     rcx, rbx
0x18000eb70  jz      short loc_18000EB90
0x18000eb72  test    [rcx+1Ch], r14b
0x18000eb76  jz      short loc_18000EB90
0x18000eb78  mov     rcx, [rcx+10h]
0x18000eb7c  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000eb83  mov     edx, 72h ; 'r'
0x18000eb88  xor     r9d, r9d
0x18000eb8b  call    WPP_SF_D
0x18000eb90  xor     eax, eax
0x18000eb92  mov     rcx, [rbp+390h+var_30]
0x18000eb99  xor     rcx, rsp; StackCookie
0x18000eb9c  call    __security_check_cookie
0x18000eba1  mov     rbx, [rsp+490h+arg_10]
0x18000eba9  add     rsp, 470h
0x18000ebb0  pop     r15
0x18000ebb2  pop     r14
0x18000ebb4  pop     rdi
0x18000ebb5  pop     rsi
0x18000ebb6  pop     rbp
0x18000ebb7  retn
```
