# _PathUnExpandEnvStrings(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort *,uint)

- ea: `0x180002e6c`
- end: `0x1800030db`
- name: `?_PathUnExpandEnvStrings@@YAHP6AKPEAXPEBGPEAGK@Z012I@Z`
- size: `623`
- prototype: `__int64 __fastcall(unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int), void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180020d00`

## callees

- `0x180002e6c`
- `0x180003474`
- `0x180003560`
- `0x180012550`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002f06`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002f06`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002f18`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002f2b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002f18`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002f2b`

## string_xrefs

- `0x180003082`: `\\%COMPUTERNAME%`

## pseudocode

```c
__int64 __fastcall _PathUnExpandEnvStrings(
        __int64 (*a1)(void *, const WCHAR *, ...),
        void *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        signed int a5)
{
  const WCHAR *v9; // r13
  int v10; // eax
  unsigned int v11; // r12d
  int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // r8
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rcx
  int v18; // [rsp+30h] [rbp-278h]
  WCHAR String1[264]; // [rsp+40h] [rbp-268h] BYREF

  if ( !a4 )
    return 0;
  if ( !a3 )
  {
    if ( a5 )
      *a4 = 0;
    return 0;
  }
  v9 = L"%APPDATA%";
  v10 = a1(a2, L"%APPDATA%", String1, 260);
  v11 = 1;
  v18 = v10;
  if ( v10
    && CompareStringW(0x800u, 0x10000001u, String1, v10 - 1, a3, v10 - 1) == 2
    && (v12 = lstrlenW(a3) - (v18 - 1), v12 + lstrlenW(L"%APPDATA%") < a5) )
  {
    if ( a5 )
    {
      if ( (unsigned int)a5 <= 0x7FFFFFFFuLL )
      {
        v13 = 2147483646;
        v14 = (unsigned int)a5;
        v15 = a4;
        do
        {
          if ( !v13 )
            break;
          if ( !*v9 )
            break;
          *v15++ = *v9++;
          --v13;
          --v14;
        }
        while ( v14 );
        v16 = v15 - 1;
        if ( v14 )
          v16 = v15;
        *v16 = 0;
      }
      else
      {
        *a4 = 0;
      }
    }
    StringCchCatW(a4, (unsigned int)a5, &a3[v18 - 1]);
  }
  else if ( !_UnExpandEnvironmentString(
               (unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int))a1,
               a2,
               a3,
               L"%USERPROFILE%",
               a4,
               a5)
         && !_UnExpandEnvironmentString(
               (unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int))a1,
               a2,
               a3,
               L"%ALLUSERSPROFILE%",
               a4,
               a5)
         && !_UnExpandEnvironmentString(
               (unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int))a1,
               a2,
               a3,
               L"%ProgramFiles(x86)%",
               a4,
               a5)
         && !_UnExpandEnvironmentString(
               (unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int))a1,
               a2,
               a3,
               L"%ProgramFiles%",
               a4,
               a5)
         && !_UnExpandEnvironmentString(
               (unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int))a1,
               a2,
               a3,
               L"%SystemRoot%",
               a4,
               a5)
         && !_UnExpandEnvironmentString(
               (unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int))a1,
               a2,
               a3,
               L"%SystemDrive%",
               a4,
               a5)
         && !_UnExpandEnvironmentString(
               (unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int))a1,
               a2,
               a3,
               L"\\\\%COMPUTERNAME%",
               a4,
               a5) )
  {
    return 0;
  }
  return v11;
}

```

## disassembly

```asm
0x180002e6c  push    rbx
0x180002e6e  push    rbp
0x180002e6f  push    rsi
0x180002e70  push    rdi
0x180002e71  push    r12
0x180002e73  push    r13
0x180002e75  push    r14
0x180002e77  push    r15
0x180002e79  sub     rsp, 268h
0x180002e80  mov     rax, cs:__security_cookie
0x180002e87  xor     rax, rsp
0x180002e8a  mov     [rsp+2A8h+var_58], rax
0x180002e92  xor     ebx, ebx
0x180002e94  mov     rdi, r9
0x180002e97  mov     rsi, r8
0x180002e9a  mov     r15, rdx
0x180002e9d  mov     r14, rcx
0x180002ea0  test    r9, r9
0x180002ea3  jz      loc_1800030B5
0x180002ea9  test    r8, r8
0x180002eac  jz      loc_1800030A8
0x180002eb2  lea     r13, String; "%APPDATA%"
0x180002eb9  mov     r9d, 104h
0x180002ebf  mov     rdx, r13
0x180002ec2  lea     r8, [rsp+2A8h+String1]
0x180002ec7  mov     rcx, r15
0x180002eca  mov     rax, r14
0x180002ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ed2  mov     ebp, [rsp+2A8h+arg_20]
0x180002ed9  lea     r12d, [rbx+1]
0x180002edd  mov     [rsp+2A8h+var_278], eax
0x180002ee1  test    eax, eax
0x180002ee3  jz      loc_180002FA6
0x180002ee9  dec     eax
0x180002eeb  lea     r8, [rsp+2A8h+String1]; lpString1
0x180002ef0  mov     [rsp+2A8h+cchCount2], eax; cchCount2
0x180002ef4  mov     r9d, eax; cchCount1
0x180002ef7  mov     edx, 10000001h; dwCmpFlags
0x180002efc  mov     [rsp+2A8h+lpString2], rsi; lpString2
0x180002f01  mov     ecx, 800h; Locale
0x180002f06  call    cs:__imp_CompareStringW
0x180002f0c  cmp     eax, 2
0x180002f0f  jnz     loc_180002FA6
0x180002f15  mov     rcx, rsi; lpString
0x180002f18  call    cs:__imp_lstrlenW
0x180002f1e  mov     ebx, eax
0x180002f20  mov     rcx, r13; lpString
0x180002f23  mov     eax, [rsp+2A8h+var_278]
0x180002f27  dec     eax
0x180002f29  sub     ebx, eax
0x180002f2b  call    cs:__imp_lstrlenW
0x180002f31  add     eax, ebx
0x180002f33  cmp     eax, ebp
0x180002f35  jge     short loc_180002FA4
0x180002f37  xor     r10d, r10d
0x180002f3a  mov     edx, ebp; unsigned __int64
0x180002f3c  test    ebp, ebp
0x180002f3e  jz      short loc_180002F8D
0x180002f40  cmp     rdx, 7FFFFFFFh
0x180002f47  jbe     short loc_180002F4F
0x180002f49  mov     [rdi], r10w
0x180002f4d  jmp     short loc_180002F8D
0x180002f4f  mov     ecx, 7FFFFFFEh
0x180002f54  mov     r8, rdx
0x180002f57  mov     rax, rdi
0x180002f5a  test    rcx, rcx
0x180002f5d  jz      short loc_180002F7E
0x180002f5f  movzx   r9d, word ptr [r13+0]
0x180002f64  test    r9w, r9w
0x180002f68  jz      short loc_180002F7E
0x180002f6a  mov     [rax], r9w
0x180002f6e  add     r13, 2
0x180002f72  add     rax, 2
0x180002f76  sub     rcx, r12
0x180002f79  sub     r8, r12
0x180002f7c  jnz     short loc_180002F5A
0x180002f7e  test    r8, r8
0x180002f81  lea     rcx, [rax-2]
0x180002f85  cmovnz  rcx, rax
0x180002f89  mov     [rcx], r10w
0x180002f8d  mov     eax, [rsp+2A8h+var_278]
0x180002f91  mov     rcx, rdi; unsigned __int16 *
0x180002f94  dec     eax
0x180002f96  lea     r8, [rsi+rax*2]; unsigned __int16 *
0x180002f9a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180002f9f  jmp     loc_1800030A3
0x180002fa4  xor     ebx, ebx
0x180002fa6  mov     [rsp+2A8h+cchCount2], ebp; unsigned int
0x180002faa  lea     r9, aUserprofile_1; "%USERPROFILE%"
0x180002fb1  mov     r8, rsi; unsigned __int16 *
0x180002fb4  mov     [rsp+2A8h+lpString2], rdi; unsigned __int16 *
0x180002fb9  mov     rdx, r15; void *
0x180002fbc  mov     rcx, r14; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x180002fbf  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x180002fc4  test    eax, eax
0x180002fc6  jnz     loc_1800030A3
0x180002fcc  mov     [rsp+2A8h+cchCount2], ebp; unsigned int
0x180002fd0  lea     r9, aAllusersprofil; "%ALLUSERSPROFILE%"
0x180002fd7  mov     r8, rsi; unsigned __int16 *
0x180002fda  mov     [rsp+2A8h+lpString2], rdi; unsigned __int16 *
0x180002fdf  mov     rdx, r15; void *
0x180002fe2  mov     rcx, r14; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x180002fe5  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x180002fea  test    eax, eax
0x180002fec  jnz     loc_1800030A3
0x180002ff2  mov     [rsp+2A8h+cchCount2], ebp; unsigned int
0x180002ff6  lea     r9, aProgramfilesX8_0; "%ProgramFiles(x86)%"
0x180002ffd  mov     r8, rsi; unsigned __int16 *
0x180003000  mov     [rsp+2A8h+lpString2], rdi; unsigned __int16 *
0x180003005  mov     rdx, r15; void *
0x180003008  mov     rcx, r14; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x18000300b  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x180003010  test    eax, eax
0x180003012  jnz     loc_1800030A3
0x180003018  mov     [rsp+2A8h+cchCount2], ebp; unsigned int
0x18000301c  lea     r9, aProgramfiles; "%ProgramFiles%"
0x180003023  mov     r8, rsi; unsigned __int16 *
0x180003026  mov     [rsp+2A8h+lpString2], rdi; unsigned __int16 *
0x18000302b  mov     rdx, r15; void *
0x18000302e  mov     rcx, r14; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x180003031  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x180003036  test    eax, eax
0x180003038  jnz     short loc_1800030A3
0x18000303a  mov     [rsp+2A8h+cchCount2], ebp; unsigned int
0x18000303e  lea     r9, aSystemroot_1; "%SystemRoot%"
0x180003045  mov     r8, rsi; unsigned __int16 *
0x180003048  mov     [rsp+2A8h+lpString2], rdi; unsigned __int16 *
0x18000304d  mov     rdx, r15; void *
0x180003050  mov     rcx, r14; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x180003053  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x180003058  test    eax, eax
0x18000305a  jnz     short loc_1800030A3
0x18000305c  mov     [rsp+2A8h+cchCount2], ebp; unsigned int
0x180003060  lea     r9, aSystemdrive_0; "%SystemDrive%"
0x180003067  mov     r8, rsi; unsigned __int16 *
0x18000306a  mov     [rsp+2A8h+lpString2], rdi; unsigned __int16 *
0x18000306f  mov     rdx, r15; void *
0x180003072  mov     rcx, r14; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x180003075  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x18000307a  test    eax, eax
0x18000307c  jnz     short loc_1800030A3
0x18000307e  mov     [rsp+2A8h+cchCount2], ebp; unsigned int
0x180003082  lea     r9, aComputername; "\\\\%COMPUTERNAME%"
0x180003089  mov     r8, rsi; unsigned __int16 *
0x18000308c  mov     [rsp+2A8h+lpString2], rdi; unsigned __int16 *
0x180003091  mov     rdx, r15; void *
0x180003094  mov     rcx, r14; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x180003097  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x18000309c  test    eax, eax
0x18000309e  jnz     short loc_1800030A3
0x1800030a0  mov     r12d, ebx
0x1800030a3  mov     eax, r12d
0x1800030a6  jmp     short loc_1800030B7
0x1800030a8  cmp     [rsp+2A8h+arg_20], ebx
0x1800030af  jbe     short loc_1800030B5
0x1800030b1  mov     [r9], bx
0x1800030b5  xor     eax, eax
0x1800030b7  mov     rcx, [rsp+2A8h+var_58]
0x1800030bf  xor     rcx, rsp; StackCookie
0x1800030c2  call    __security_check_cookie
0x1800030c7  add     rsp, 268h
0x1800030ce  pop     r15
0x1800030d0  pop     r14
0x1800030d2  pop     r13
0x1800030d4  pop     r12
0x1800030d6  pop     rdi
0x1800030d7  pop     rsi
0x1800030d8  pop     rbp
0x1800030d9  pop     rbx
0x1800030da  retn
```
