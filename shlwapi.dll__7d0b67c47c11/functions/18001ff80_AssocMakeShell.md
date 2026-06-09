# AssocMakeShell

- ea: `0x18001ff80`
- end: `0x18002015c`
- name: `AssocMakeShell`
- size: `476`
- prototype: `__int64 __fastcall(unsigned int, HKEY, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fd40`

## callees

- `0x180004e64`
- `0x180010304`
- `0x180012550`
- `0x18001f554`
- `0x18001ff80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020096`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020124`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020096`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020124`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002002c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800200ca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002002c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800200ca`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18002008b`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18002008b`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18002005a`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800200f5`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18002005a`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800200f5`

## pseudocode

```c
__int64 __fastcall AssocMakeShell(unsigned int a1, HKEY a2, const unsigned __int16 *a3, __int64 *a4)
{
  unsigned int Command; // r15d
  __int64 i; // rdi
  __int64 v10; // rbp
  __int64 v11; // rax
  int v12; // eax
  const WCHAR *v13; // rcx
  int v14; // eax
  const unsigned __int16 *v15; // r8
  HKEY hkey[2]; // [rsp+30h] [rbp-278h] BYREF
  unsigned __int16 v18[264]; // [rsp+40h] [rbp-268h] BYREF

  Command = -2147024809;
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)a4 + 2); i = (unsigned int)(i + 1) )
        {
          v10 = *a4;
          v11 = *(_QWORD *)(*a4 + 48 * i);
          if ( v11 )
          {
            hkey[0] = 0;
            StringCchPrintfW(v18, 0x104u, L"%s\\%s", L"shell", v11);
            if ( (_DWORD)i == *((_DWORD *)a4 + 3) )
            {
              v12 = lstrlenW(*(LPCWSTR *)(v10 + 48 * i));
              SHSetValueW(a2, L"shell", 0, 1u, *(LPCVOID *)(v10 + 48 * i), 2 * v12 + 2);
            }
            if ( _AssocOpenRegKey(a2, v18, 0x3001Fu, hkey, 0) >= 0 )
            {
              SHDeleteKeyW(hkey[0], 0);
              RegCloseKey(hkey[0]);
            }
            if ( _AssocOpenRegKey(a2, v18, 0x20006u, hkey, 1) >= 0 )
            {
              v13 = *(const WCHAR **)(v10 + 48 * i + 8);
              if ( v13 )
              {
                v14 = lstrlenW(v13);
                SHSetValueW(hkey[0], 0, 0, 1u, *(LPCVOID *)(v10 + 48 * i + 8), 2 * v14 + 2);
              }
              v15 = a3;
              if ( *(_QWORD *)(v10 + 48 * i + 24) )
                v15 = *(const unsigned __int16 **)(v10 + 48 * i + 24);
              Command = _AssocMakeCommand(a1, hkey[0], v15, *(const unsigned __int16 **)(v10 + 48 * i + 32));
              RegCloseKey(hkey[0]);
            }
          }
        }
      }
    }
  }
  return Command;
}

```

## disassembly

```asm
0x18001ff80  push    rbx
0x18001ff82  push    rbp
0x18001ff83  push    rsi
0x18001ff84  push    rdi
0x18001ff85  push    r12
0x18001ff87  push    r13
0x18001ff89  push    r14
0x18001ff8b  push    r15
0x18001ff8d  sub     rsp, 268h
0x18001ff94  mov     rax, cs:__security_cookie
0x18001ff9b  xor     rax, rsp
0x18001ff9e  mov     [rsp+2A8h+var_58], rax
0x18001ffa6  mov     rsi, r9
0x18001ffa9  mov     r12, r8
0x18001ffac  mov     r14, rdx
0x18001ffaf  mov     r13d, ecx
0x18001ffb2  mov     r15d, 80070057h
0x18001ffb8  test    rdx, rdx
0x18001ffbb  jz      loc_180020135
0x18001ffc1  test    r8, r8
0x18001ffc4  jz      loc_180020135
0x18001ffca  test    r9, r9
0x18001ffcd  jz      loc_180020135
0x18001ffd3  xor     edi, edi
0x18001ffd5  cmp     [r9+8], edi
0x18001ffd9  jbe     loc_180020135
0x18001ffdf  mov     rbp, [rsi]
0x18001ffe2  lea     rbx, [rdi+rdi*2]
0x18001ffe6  add     rbx, rbx
0x18001ffe9  mov     rax, [rbp+rbx*8+0]
0x18001ffee  test    rax, rax
0x18001fff1  jz      loc_18002012A
0x18001fff7  lea     r9, aShell; "shell"
0x18001fffe  mov     [rsp+2A8h+hkey], 0
0x180020007  lea     r8, aSS_0; "%s\\%s"
0x18002000e  mov     [rsp+2A8h+pvData], rax
0x180020013  mov     edx, 104h; unsigned __int64
0x180020018  lea     rcx, [rsp+2A8h+var_268]; unsigned __int16 *
0x18002001d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020022  cmp     edi, [rsi+0Ch]
0x180020025  jnz     short loc_180020060
0x180020027  mov     rcx, [rbp+rbx*8+0]; lpString
0x18002002c  call    cs:__imp_lstrlenW
0x180020032  mov     r9d, 1; dwType
0x180020038  lea     rdx, aShell; "shell"
0x18002003f  xor     r8d, r8d; pszValue
0x180020042  mov     rcx, r14; hkey
0x180020045  lea     eax, ds:2[rax*2]
0x18002004c  mov     [rsp+2A8h+cbData], eax; cbData
0x180020050  mov     rax, [rbp+rbx*8+0]
0x180020055  mov     [rsp+2A8h+pvData], rax; pvData
0x18002005a  call    cs:__imp_SHSetValueW
0x180020060  lea     r9, [rsp+2A8h+hkey]; HKEY *
0x180020065  mov     dword ptr [rsp+2A8h+pvData], 0; int
0x18002006d  mov     r8d, 3001Fh; unsigned int
0x180020073  lea     rdx, [rsp+2A8h+var_268]; unsigned __int16 *
0x180020078  mov     rcx, r14; HKEY
0x18002007b  call    ?_AssocOpenRegKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@H@Z; _AssocOpenRegKey(HKEY__ *,ushort const *,ulong,HKEY__ * *,int)
0x180020080  test    eax, eax
0x180020082  js      short loc_18002009C
0x180020084  mov     rcx, [rsp+2A8h+hkey]; hkey
0x180020089  xor     edx, edx; pszSubKey
0x18002008b  call    cs:__imp_SHDeleteKeyW
0x180020091  mov     rcx, [rsp+2A8h+hkey]; hKey
0x180020096  call    cs:__imp_RegCloseKey
0x18002009c  lea     r9, [rsp+2A8h+hkey]; HKEY *
0x1800200a1  mov     dword ptr [rsp+2A8h+pvData], 1; int
0x1800200a9  mov     r8d, 20006h; unsigned int
0x1800200af  lea     rdx, [rsp+2A8h+var_268]; unsigned __int16 *
0x1800200b4  mov     rcx, r14; HKEY
0x1800200b7  call    ?_AssocOpenRegKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@H@Z; _AssocOpenRegKey(HKEY__ *,ushort const *,ulong,HKEY__ * *,int)
0x1800200bc  test    eax, eax
0x1800200be  js      short loc_18002012A
0x1800200c0  mov     rcx, [rbp+rbx*8+8]; lpString
0x1800200c5  test    rcx, rcx
0x1800200c8  jz      short loc_1800200FB
0x1800200ca  call    cs:__imp_lstrlenW
0x1800200d0  mov     rcx, [rsp+2A8h+hkey]; hkey
0x1800200d5  mov     r9d, 1; dwType
0x1800200db  xor     r8d, r8d; pszValue
0x1800200de  xor     edx, edx; pszSubKey
0x1800200e0  lea     eax, ds:2[rax*2]
0x1800200e7  mov     [rsp+2A8h+cbData], eax; cbData
0x1800200eb  mov     rax, [rbp+rbx*8+8]
0x1800200f0  mov     [rsp+2A8h+pvData], rax; pvData
0x1800200f5  call    cs:__imp_SHSetValueW
0x1800200fb  mov     rax, [rbp+rbx*8+18h]
0x180020100  mov     r8, r12
0x180020103  mov     r9, [rbp+rbx*8+20h]; unsigned __int16 *
0x180020108  test    rax, rax
0x18002010b  mov     rdx, [rsp+2A8h+hkey]; HKEY
0x180020110  mov     ecx, r13d; unsigned int
0x180020113  cmovnz  r8, rax; unsigned __int16 *
0x180020117  call    ?_AssocMakeCommand@@YAJKPEAUHKEY__@@PEBG1@Z; _AssocMakeCommand(ulong,HKEY__ *,ushort const *,ushort const *)
0x18002011c  mov     rcx, [rsp+2A8h+hkey]; hKey
0x180020121  mov     r15d, eax
0x180020124  call    cs:__imp_RegCloseKey
0x18002012a  inc     edi
0x18002012c  cmp     edi, [rsi+8]
0x18002012f  jb      loc_18001FFDF
0x180020135  mov     eax, r15d
0x180020138  mov     rcx, [rsp+2A8h+var_58]
0x180020140  xor     rcx, rsp; StackCookie
0x180020143  call    __security_check_cookie
0x180020148  add     rsp, 268h
0x18002014f  pop     r15
0x180020151  pop     r14
0x180020153  pop     r13
0x180020155  pop     r12
0x180020157  pop     rdi
0x180020158  pop     rsi
0x180020159  pop     rbp
0x18002015a  pop     rbx
0x18002015b  retn
```
