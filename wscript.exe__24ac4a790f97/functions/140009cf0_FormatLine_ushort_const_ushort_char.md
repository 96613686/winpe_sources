# FormatLine(ushort const *,ushort * *,char * *)

- ea: `0x140009cf0`
- end: `0x140009eef`
- name: `?FormatLine@@YAJPEBGPEAPEAGPEAPEAD@Z`
- size: `511`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, unsigned __int16 **, char **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400057f0`
- `0x140009ef8`
- `0x140009f30`
- `0x14000a098`

## callees

- `0x140009cf0`
- `0x1400175a0`
- `0x1400175d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140009ea0`
- `OLEAUT32!__imp_SysAllocString` at `0x140009ea0`
- `KERNEL32!FormatMessageW` at `0x140009d4e`
- `KERNEL32!FormatMessageW` at `0x140009d4e`
- `KERNEL32!GetLastError` at `0x140009d5c`
- `KERNEL32!GetLastError` at `0x140009d5c`
- `KERNEL32!MultiByteToWideChar` at `0x140009e4d`
- `KERNEL32!MultiByteToWideChar` at `0x140009e8e`
- `KERNEL32!MultiByteToWideChar` at `0x140009e4d`
- `KERNEL32!MultiByteToWideChar` at `0x140009e8e`
- `KERNEL32!WideCharToMultiByte` at `0x140009d99`
- `KERNEL32!WideCharToMultiByte` at `0x140009dfa`
- `KERNEL32!WideCharToMultiByte` at `0x140009d99`
- `KERNEL32!WideCharToMultiByte` at `0x140009dfa`
- `KERNEL32!LocalAlloc` at `0x140009e66`
- `KERNEL32!LocalAlloc` at `0x140009e66`
- `KERNEL32!LocalFree` at `0x140009ebf`
- `KERNEL32!LocalFree` at `0x140009ece`
- `KERNEL32!LocalFree` at `0x140009ebf`
- `KERNEL32!LocalFree` at `0x140009ece`
- `KERNEL32!FormatMessageA` at `0x140009e29`
- `KERNEL32!FormatMessageA` at `0x140009e29`

## pseudocode

```c
__int64 __fastcall FormatLine(LPCWCH lpWideCharStr, unsigned __int16 **a2, char **Arguments)
{
  DWORD v6; // eax
  signed int LastError; // eax
  unsigned int v8; // edi
  int v9; // eax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  int v14; // eax
  int v15; // ebx
  WCHAR *v16; // rax
  int v17; // ebx
  unsigned __int16 *v18; // rax
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp+8h] BYREF

  *(_QWORD *)Buffer = 0;
  *(_QWORD *)MultiByteStr = 0;
  if ( Global::g_fWindowsNT )
  {
    v6 = FormatMessageW(0x500u, lpWideCharStr, 0, 0, Buffer, 0, Arguments);
  }
  else
  {
    v9 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( !v9 )
      goto LABEL_4;
    v10 = v9 + 15LL;
    if ( v10 < v9 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    if ( !MultiByteStr )
    {
      v8 = -2147024882;
      goto LABEL_19;
    }
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, v9, 0, 0) )
      goto LABEL_4;
    if ( !FormatMessageA(0x500u, MultiByteStr, 0, 0, MultiByteStr, 0, Arguments) )
      goto LABEL_4;
    v14 = MultiByteToWideChar(0, 0, *(LPCCH *)MultiByteStr, -1, 0, 0);
    v15 = v14;
    if ( !v14 )
      goto LABEL_4;
    v16 = (WCHAR *)LocalAlloc(0, 2LL * v14);
    *(_QWORD *)Buffer = v16;
    if ( !v16 )
      goto LABEL_4;
    v6 = MultiByteToWideChar(0, 0, *(LPCCH *)MultiByteStr, -1, v16, v15);
  }
  if ( !v6 )
  {
LABEL_4:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_19;
  }
  v17 = 0;
  v18 = SysAllocString(*(const OLECHAR **)Buffer);
  *a2 = v18;
  if ( !v18 )
    v17 = -2147024882;
  v8 = v17;
LABEL_19:
  if ( *(_QWORD *)MultiByteStr )
    LocalFree(*(HLOCAL *)MultiByteStr);
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  return v8;
}

```

## disassembly

```asm
0x140009cf0  push    rbp
0x140009cf2  push    rbx
0x140009cf3  push    rsi
0x140009cf4  push    rdi
0x140009cf5  push    r14
0x140009cf7  push    r15
0x140009cf9  sub     rsp, 68h
0x140009cfd  lea     rbp, [rsp+40h]
0x140009d02  mov     rax, cs:__security_cookie
0x140009d09  xor     rax, rbp
0x140009d0c  mov     [rbp+50h+var_40], rax
0x140009d10  xor     r15d, r15d
0x140009d13  mov     rsi, r8
0x140009d16  cmp     cs:?g_fWindowsNT@Global@@2_NA, r15b; bool Global::g_fWindowsNT
0x140009d1d  mov     r14, rdx
0x140009d20  mov     rdi, rcx
0x140009d23  mov     qword ptr [rbp+50h+Buffer], r15
0x140009d27  mov     qword ptr [rbp+50h+MultiByteStr], r15
0x140009d2b  jz      short loc_140009D7A
0x140009d2d  mov     [rsp+90h+Arguments], r8; Arguments
0x140009d32  lea     rax, [rbp+50h+Buffer]
0x140009d36  mov     rdx, rcx; lpSource
0x140009d39  mov     [rsp+90h+nSize], r15d; nSize
0x140009d3e  xor     r8d, r8d; dwMessageId
0x140009d41  mov     [rsp+90h+lpBuffer], rax; lpBuffer
0x140009d46  mov     ecx, 500h; dwFlags
0x140009d4b  xor     r9d, r9d; dwLanguageId
0x140009d4e  call    cs:__imp_FormatMessageW
0x140009d54  test    eax, eax
0x140009d56  jnz     loc_140009E99
0x140009d5c  call    cs:__imp_GetLastError
0x140009d62  mov     edi, eax
0x140009d64  test    eax, eax
0x140009d66  jle     loc_140009EB6
0x140009d6c  movzx   edi, ax
0x140009d6f  or      edi, 80070000h
0x140009d75  jmp     loc_140009EB6
0x140009d7a  mov     [rsp+90h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x140009d7f  or      r9d, 0FFFFFFFFh; cchWideChar
0x140009d83  mov     [rsp+90h+Arguments], r15; lpDefaultChar
0x140009d88  mov     r8, rdi; lpWideCharStr
0x140009d8b  mov     [rsp+90h+nSize], r15d; cbMultiByte
0x140009d90  xor     edx, edx; dwFlags
0x140009d92  xor     ecx, ecx; CodePage
0x140009d94  mov     [rsp+90h+lpBuffer], r15; lpMultiByteStr
0x140009d99  call    cs:__imp_WideCharToMultiByte
0x140009d9f  movsxd  rdx, eax
0x140009da2  test    eax, eax
0x140009da4  jz      short loc_140009D5C
0x140009da6  lea     rcx, [rdx+0Fh]
0x140009daa  cmp     rcx, rdx
0x140009dad  ja      short loc_140009DB9
0x140009daf  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140009db9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140009dbd  mov     rax, rcx
0x140009dc0  call    _alloca_probe
0x140009dc5  sub     rsp, rcx
0x140009dc8  lea     rbx, [rsp+90h+MultiByteStr]
0x140009dcd  test    rbx, rbx
0x140009dd0  jnz     short loc_140009DDC
0x140009dd2  mov     edi, 8007000Eh
0x140009dd7  jmp     loc_140009EB6
0x140009ddc  mov     [rsp+90h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x140009de1  or      r9d, 0FFFFFFFFh; cchWideChar
0x140009de5  mov     [rsp+90h+Arguments], r15; lpDefaultChar
0x140009dea  mov     r8, rdi; lpWideCharStr
0x140009ded  mov     [rsp+90h+nSize], edx; cbMultiByte
0x140009df1  xor     ecx, ecx; CodePage
0x140009df3  xor     edx, edx; dwFlags
0x140009df5  mov     [rsp+90h+lpBuffer], rbx; lpMultiByteStr
0x140009dfa  call    cs:__imp_WideCharToMultiByte
0x140009e00  test    eax, eax
0x140009e02  jz      loc_140009D5C
0x140009e08  mov     [rsp+90h+Arguments], rsi; Arguments
0x140009e0d  lea     rax, [rbp+50h+MultiByteStr]
0x140009e11  mov     [rsp+90h+nSize], r15d; nSize
0x140009e16  xor     r9d, r9d; dwLanguageId
0x140009e19  xor     r8d, r8d; dwMessageId
0x140009e1c  mov     [rsp+90h+lpBuffer], rax; lpBuffer
0x140009e21  mov     rdx, rbx; lpSource
0x140009e24  mov     ecx, 500h; dwFlags
0x140009e29  call    cs:__imp_FormatMessageA
0x140009e2f  test    eax, eax
0x140009e31  jz      loc_140009D5C
0x140009e37  mov     r8, qword ptr [rbp+50h+MultiByteStr]; lpMultiByteStr
0x140009e3b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140009e3f  mov     [rsp+90h+nSize], r15d; cchWideChar
0x140009e44  xor     edx, edx; dwFlags
0x140009e46  xor     ecx, ecx; CodePage
0x140009e48  mov     [rsp+90h+lpBuffer], r15; lpWideCharStr
0x140009e4d  call    cs:__imp_MultiByteToWideChar
0x140009e53  movsxd  rbx, eax
0x140009e56  test    eax, eax
0x140009e58  jz      loc_140009D5C
0x140009e5e  mov     rdx, rbx
0x140009e61  xor     ecx, ecx; uFlags
0x140009e63  add     rdx, rdx; uBytes
0x140009e66  call    cs:__imp_LocalAlloc
0x140009e6c  mov     qword ptr [rbp+50h+Buffer], rax
0x140009e70  test    rax, rax
0x140009e73  jz      loc_140009D5C
0x140009e79  mov     r8, qword ptr [rbp+50h+MultiByteStr]; lpMultiByteStr
0x140009e7d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140009e81  mov     [rsp+90h+nSize], ebx; cchWideChar
0x140009e85  xor     edx, edx; dwFlags
0x140009e87  xor     ecx, ecx; CodePage
0x140009e89  mov     [rsp+90h+lpBuffer], rax; lpWideCharStr
0x140009e8e  call    cs:__imp_MultiByteToWideChar
0x140009e94  jmp     loc_140009D54
0x140009e99  mov     rcx, qword ptr [rbp+50h+Buffer]; psz
0x140009e9d  mov     ebx, r15d
0x140009ea0  call    cs:__imp_SysAllocString
0x140009ea6  mov     edi, 8007000Eh
0x140009eab  mov     [r14], rax
0x140009eae  test    rax, rax
0x140009eb1  cmovz   ebx, edi
0x140009eb4  mov     edi, ebx
0x140009eb6  mov     rcx, qword ptr [rbp+50h+MultiByteStr]; hMem
0x140009eba  test    rcx, rcx
0x140009ebd  jz      short loc_140009EC5
0x140009ebf  call    cs:__imp_LocalFree
0x140009ec5  mov     rcx, qword ptr [rbp+50h+Buffer]; hMem
0x140009ec9  test    rcx, rcx
0x140009ecc  jz      short loc_140009ED4
0x140009ece  call    cs:__imp_LocalFree
0x140009ed4  mov     eax, edi
0x140009ed6  mov     rcx, [rbp+50h+var_40]
0x140009eda  xor     rcx, rbp; StackCookie
0x140009edd  call    __security_check_cookie
0x140009ee2  lea     rsp, [rbp+28h]
0x140009ee6  pop     r15
0x140009ee8  pop     r14
0x140009eea  pop     rdi
0x140009eeb  pop     rsi
0x140009eec  pop     rbx
0x140009eed  pop     rbp
0x140009eee  retn
```
