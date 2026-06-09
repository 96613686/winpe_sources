# HrMakeFullNonHardCodedPath(ushort * const,ushort *,uint)

- ea: `0x18000d598`
- end: `0x18000d8af`
- name: `?HrMakeFullNonHardCodedPath@@YAJQEAGPEAGI@Z`
- size: `791`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000d8b8`

## callees

- `0x180004370`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000d598`
- `0x18000e03c`
- `0x18000e0f0`
- `0x18000e8dc`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000d67b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000d67b`
- `SHLWAPI!PathFileExistsW` at `0x18000d70e`
- `SHLWAPI!PathFileExistsW` at `0x18000d70e`
- `SHLWAPI!PathUnExpandEnvStringsW` at `0x18000d7fc`
- `SHLWAPI!PathUnExpandEnvStringsW` at `0x18000d7fc`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000d61a`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000d61a`

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
  char v11; // al
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
            v11 = GetLastErrorHRESULT();
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              113,
              (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
              (unsigned int)Buffer,
              v11);
          }
          *a2 = 0;
          StringCchCopyNW(a2, 0x105u, Buffer, 0x104u);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, 0);
        return 0;
      }
      v10 = wcsistr(Buffer, L"\\oobe\\");
      if ( !v10 )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, Buffer);
      *v10 = 0;
      StringCchCopyW(v10, 261 - ((unsigned __int64)(v10 - Buffer) >> 1), v10 + 5);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, Buffer);
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
0x18000d598  mov     [rsp-8+arg_10], rbx
0x18000d59d  push    rbp
0x18000d59e  push    rsi
0x18000d59f  push    rdi
0x18000d5a0  push    r14
0x18000d5a2  push    r15
0x18000d5a4  lea     rbp, [rsp-370h]
0x18000d5ac  sub     rsp, 470h
0x18000d5b3  mov     rax, cs:__security_cookie
0x18000d5ba  xor     rax, rsp
0x18000d5bd  mov     [rbp+390h+var_30], rax
0x18000d5c4  mov     rsi, rdx
0x18000d5c7  mov     [rsp+490h+FilePart], 0
0x18000d5d0  mov     r14, rcx
0x18000d5d3  mov     ebx, 20Ah
0x18000d5d8  mov     r8d, ebx; Size
0x18000d5db  lea     rcx, [rbp+390h+Dest]; void *
0x18000d5e2  xor     edx, edx; Val
0x18000d5e4  call    memset_0
0x18000d5e9  mov     r8d, ebx; Size
0x18000d5ec  lea     rcx, [rsp+490h+Buffer]; void *
0x18000d5f1  xor     edx, edx; Val
0x18000d5f3  call    memset_0
0x18000d5f8  mov     r8d, ebx; Size
0x18000d5fb  xor     edx, edx; Val
0x18000d5fd  mov     rcx, rsi; void *
0x18000d600  call    memset_0
0x18000d605  mov     r15d, 105h
0x18000d60b  lea     r8, [rbp+390h+Dest]; lpDest
0x18000d612  mov     r9d, r15d; dwSize
0x18000d615  mov     rdx, r14; lpSrc
0x18000d618  xor     ecx, ecx; hToken
0x18000d61a  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18000d620  test    eax, eax
0x18000d622  jnz     short loc_18000D667
0x18000d624  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000d629  mov     edi, eax
0x18000d62b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d632  lea     rbx, WPP_GLOBAL_Control
0x18000d639  cmp     rcx, rbx
0x18000d63c  jz      short loc_18000D660
0x18000d63e  test    byte ptr [rcx+1Ch], 4
0x18000d642  jz      short loc_18000D660
0x18000d644  mov     edx, 6Bh ; 'k'
0x18000d649  mov     r9, r14
0x18000d64c  mov     rcx, [rcx+10h]
0x18000d650  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d657  mov     [rsp+490h+var_470], edi
0x18000d65b  call    WPP_SF_SD
0x18000d660  mov     eax, edi
0x18000d662  jmp     loc_18000D889
0x18000d667  lea     r9, [rsp+490h+FilePart]; lpFilePart
0x18000d66c  mov     edx, r15d; nBufferLength
0x18000d66f  lea     r8, [rsp+490h+Buffer]; lpBuffer
0x18000d674  lea     rcx, [rbp+390h+Dest]; lpFileName
0x18000d67b  call    cs:__imp_GetFullPathNameW
0x18000d681  test    eax, eax
0x18000d683  jnz     short loc_18000D6B3
0x18000d685  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000d68a  mov     edi, eax
0x18000d68c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d693  lea     rbx, WPP_GLOBAL_Control
0x18000d69a  cmp     rcx, rbx
0x18000d69d  jz      short loc_18000D660
0x18000d69f  test    byte ptr [rcx+1Ch], 4
0x18000d6a3  jz      short loc_18000D660
0x18000d6a5  mov     edx, 6Ch ; 'l'
0x18000d6aa  lea     r9, [rbp+390h+Dest]
0x18000d6b1  jmp     short loc_18000D64C
0x18000d6b3  cmp     eax, r15d
0x18000d6b6  jb      short loc_18000D6FF
0x18000d6b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6bf  lea     rbx, WPP_GLOBAL_Control
0x18000d6c6  cmp     rcx, rbx
0x18000d6c9  jz      short loc_18000D6F5
0x18000d6cb  test    byte ptr [rcx+1Ch], 4
0x18000d6cf  jz      short loc_18000D6F5
0x18000d6d1  mov     rcx, [rcx+10h]
0x18000d6d5  lea     r9, [rbp+390h+Dest]
0x18000d6dc  mov     edx, 6Dh ; 'm'
0x18000d6e1  mov     [rsp+490h+var_470], 8007000Eh
0x18000d6e9  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d6f0  call    WPP_SF_SD
0x18000d6f5  mov     eax, 8007000Eh
0x18000d6fa  jmp     loc_18000D889
0x18000d6ff  lea     rbx, WPP_GLOBAL_Control
0x18000d706  mov     r14b, 10h
0x18000d709  lea     rcx, [rsp+490h+Buffer]; pszPath
0x18000d70e  call    cs:__imp_PathFileExistsW
0x18000d714  lea     rcx, [rsp+490h+Buffer]; unsigned __int16 *
0x18000d719  test    eax, eax
0x18000d71b  jnz     loc_18000D7F6
0x18000d721  lea     rdx, aOobe; "\\oobe\\"
0x18000d728  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000d72d  mov     rdi, rax
0x18000d730  test    rax, rax
0x18000d733  jz      loc_18000D7C6
0x18000d739  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d740  cmp     rcx, rbx
0x18000d743  jz      short loc_18000D765
0x18000d745  test    [rcx+1Ch], r14b
0x18000d749  jz      short loc_18000D765
0x18000d74b  mov     rcx, [rcx+10h]
0x18000d74f  lea     r9, [rsp+490h+Buffer]
0x18000d754  mov     edx, 6Eh ; 'n'
0x18000d759  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d760  call    WPP_SF_S
0x18000d765  xor     eax, eax
0x18000d767  lea     rcx, [rsp+490h+Buffer]
0x18000d76c  mov     [rdi], ax
0x18000d76f  lea     r8, [rdi+0Ah]; unsigned __int16 *
0x18000d773  mov     rax, rdi
0x18000d776  mov     rdx, r15
0x18000d779  sub     rax, rcx
0x18000d77c  mov     rcx, rdi; unsigned __int16 *
0x18000d77f  sar     rax, 1
0x18000d782  shr     rax, 1
0x18000d785  sub     rdx, rax; unsigned __int64
0x18000d788  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d78d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d794  cmp     rcx, rbx
0x18000d797  jz      loc_18000D709
0x18000d79d  test    [rcx+1Ch], r14b
0x18000d7a1  jz      loc_18000D709
0x18000d7a7  mov     rcx, [rcx+10h]
0x18000d7ab  lea     r9, [rsp+490h+Buffer]
0x18000d7b0  mov     edx, 6Fh ; 'o'
0x18000d7b5  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d7bc  call    WPP_SF_S
0x18000d7c1  jmp     loc_18000D709
0x18000d7c6  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000d7cb  mov     edi, eax
0x18000d7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7d4  cmp     rcx, rbx
0x18000d7d7  jz      loc_18000D660
0x18000d7dd  test    byte ptr [rcx+1Ch], 4
0x18000d7e1  jz      loc_18000D660
0x18000d7e7  mov     edx, 70h ; 'p'
0x18000d7ec  lea     r9, [rsp+490h+Buffer]
0x18000d7f1  jmp     loc_18000D64C
0x18000d7f6  mov     r8d, r15d; cchBuf
0x18000d7f9  mov     rdx, rsi; pszBuf
0x18000d7fc  call    cs:__imp_PathUnExpandEnvStringsW
0x18000d802  test    eax, eax
0x18000d804  jnz     short loc_18000D85D
0x18000d806  mov     rax, cs:WPP_GLOBAL_Control
0x18000d80d  cmp     rax, rbx
0x18000d810  jz      short loc_18000D842
0x18000d812  test    byte ptr [rax+1Ch], 4
0x18000d816  jz      short loc_18000D842
0x18000d818  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000d81d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d824  lea     r9, [rsp+490h+Buffer]
0x18000d829  mov     edx, 71h ; 'q'
0x18000d82e  mov     [rsp+490h+var_470], eax
0x18000d832  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d839  mov     rcx, [rcx+10h]
0x18000d83d  call    WPP_SF_SD
0x18000d842  xor     eax, eax
0x18000d844  lea     r8, [rsp+490h+Buffer]; unsigned __int16 *
0x18000d849  mov     r9d, 104h; unsigned __int64
0x18000d84f  mov     [rsi], ax
0x18000d852  mov     rdx, r15; unsigned __int64
0x18000d855  mov     rcx, rsi; unsigned __int16 *
0x18000d858  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000d85d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d864  cmp     rcx, rbx
0x18000d867  jz      short loc_18000D887
0x18000d869  test    [rcx+1Ch], r14b
0x18000d86d  jz      short loc_18000D887
0x18000d86f  mov     rcx, [rcx+10h]
0x18000d873  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d87a  mov     edx, 72h ; 'r'
0x18000d87f  xor     r9d, r9d
0x18000d882  call    WPP_SF_d
0x18000d887  xor     eax, eax
0x18000d889  mov     rcx, [rbp+390h+var_30]
0x18000d890  xor     rcx, rsp; StackCookie
0x18000d893  call    __security_check_cookie
0x18000d898  mov     rbx, [rsp+490h+arg_10]
0x18000d8a0  add     rsp, 470h
0x18000d8a7  pop     r15
0x18000d8a9  pop     r14
0x18000d8ab  pop     rdi
0x18000d8ac  pop     rsi
0x18000d8ad  pop     rbp
0x18000d8ae  retn
```
