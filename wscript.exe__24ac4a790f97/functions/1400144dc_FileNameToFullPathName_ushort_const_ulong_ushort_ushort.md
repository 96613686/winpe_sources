# FileNameToFullPathName(ushort const *,ulong,ushort *,ushort * *)

- ea: `0x1400144dc`
- end: `0x14001466c`
- name: `?FileNameToFullPathName@@YAJPEBGKPEAGPEAPEAG@Z`
- size: `400`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000757c`
- `0x14000f700`
- `0x140010c38`

## callees

- `0x1400144dc`
- `0x1400175a0`
- `0x1400175d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001452a`
- `KERNEL32!GetLastError` at `0x14001452a`
- `KERNEL32!MultiByteToWideChar` at `0x14001461c`
- `KERNEL32!MultiByteToWideChar` at `0x140014641`
- `KERNEL32!MultiByteToWideChar` at `0x14001461c`
- `KERNEL32!MultiByteToWideChar` at `0x140014641`
- `KERNEL32!WideCharToMultiByte` at `0x140014566`
- `KERNEL32!WideCharToMultiByte` at `0x1400145c7`
- `KERNEL32!WideCharToMultiByte` at `0x140014566`
- `KERNEL32!WideCharToMultiByte` at `0x1400145c7`
- `KERNEL32!GetFullPathNameA` at `0x1400145f6`
- `KERNEL32!GetFullPathNameA` at `0x1400145f6`
- `KERNEL32!GetFullPathNameW` at `0x14001451c`
- `KERNEL32!GetFullPathNameW` at `0x14001451c`

## pseudocode

```c
__int64 __fastcall FileNameToFullPathName(
        LPCWCH lpWideCharStr,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned int v4; // ebx
  signed int LastError; // eax
  int cbMultiByte; // eax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  void *v14; // rsp
  CHAR Buffer[208]; // [rsp+20h] [rbp-110h] BYREF
  CHAR MultiByteStr[8]; // [rsp+130h] [rbp+0h] BYREF

  v4 = 0;
  *(_QWORD *)MultiByteStr = 0;
  if ( Global::g_fWindowsNT )
  {
    if ( GetFullPathNameW(lpWideCharStr, 0x104u, a3, a4) )
      return v4;
  }
  else
  {
    cbMultiByte = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( cbMultiByte )
    {
      v10 = cbMultiByte + 15LL;
      if ( v10 < cbMultiByte )
        v10 = 0xFFFFFFFFFFFFFF0LL;
      v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
      v12 = alloca(v11);
      v13 = alloca(v11);
      if ( !MultiByteStr )
        return (unsigned int)-2147024882;
      if ( WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, cbMultiByte, 0, 0) )
      {
        v14 = alloca(272);
        if ( GetFullPathNameA(MultiByteStr, 0x104u, Buffer, (LPSTR *)MultiByteStr) )
        {
          if ( MultiByteToWideChar(0, 0, Buffer, -1, a3, 260) )
          {
            *a4 = &a3[MultiByteToWideChar(0, 0, Buffer, *(_DWORD *)MultiByteStr - (unsigned int)Buffer, 0, 0)];
            return v4;
          }
        }
      }
    }
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v4;
}

```

## disassembly

```asm
0x1400144dc  push    rbp
0x1400144de  push    rbx
0x1400144df  push    rsi
0x1400144e0  push    rdi
0x1400144e1  push    r14
0x1400144e3  push    r15
0x1400144e5  sub     rsp, 58h
0x1400144e9  lea     rbp, [rsp+40h]
0x1400144ee  mov     rax, cs:__security_cookie
0x1400144f5  xor     rax, rbp
0x1400144f8  mov     [rbp+40h+var_38], rax
0x1400144fc  xor     ebx, ebx
0x1400144fe  mov     qword ptr [rbp+40h+MultiByteStr], 0
0x140014506  cmp     cs:?g_fWindowsNT@Global@@2_NA, bl; bool Global::g_fWindowsNT
0x14001450c  mov     r15, r9
0x14001450f  mov     r14, r8
0x140014512  mov     rdi, rcx
0x140014515  jz      short loc_140014548
0x140014517  mov     edx, 104h; nBufferLength
0x14001451c  call    cs:__imp_GetFullPathNameW
0x140014522  test    eax, eax
0x140014524  jnz     loc_140014651
0x14001452a  call    cs:__imp_GetLastError
0x140014530  mov     ebx, eax
0x140014532  test    eax, eax
0x140014534  jle     loc_140014651
0x14001453a  movzx   ebx, ax
0x14001453d  or      ebx, 80070000h
0x140014543  jmp     loc_140014651
0x140014548  mov     [rsp+80h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x14001454d  or      r9d, 0FFFFFFFFh; cchWideChar
0x140014551  mov     [rsp+80h+lpDefaultChar], rbx; lpDefaultChar
0x140014556  mov     r8, rdi; lpWideCharStr
0x140014559  mov     [rsp+80h+cbMultiByte], ebx; cbMultiByte
0x14001455d  xor     edx, edx; dwFlags
0x14001455f  xor     ecx, ecx; CodePage
0x140014561  mov     [rsp+80h+lpMultiByteStr], rbx; lpMultiByteStr
0x140014566  call    cs:__imp_WideCharToMultiByte
0x14001456c  movsxd  rdx, eax
0x14001456f  test    eax, eax
0x140014571  jz      short loc_14001452A
0x140014573  lea     rcx, [rdx+0Fh]
0x140014577  cmp     rcx, rdx
0x14001457a  ja      short loc_140014586
0x14001457c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140014586  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14001458a  mov     rax, rcx
0x14001458d  call    _alloca_probe
0x140014592  sub     rsp, rcx
0x140014595  lea     rsi, [rsp+80h+MultiByteStr]
0x14001459a  test    rsi, rsi
0x14001459d  jnz     short loc_1400145A9
0x14001459f  mov     ebx, 8007000Eh
0x1400145a4  jmp     loc_140014651
0x1400145a9  mov     [rsp+80h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x1400145ae  or      r9d, 0FFFFFFFFh; cchWideChar
0x1400145b2  mov     [rsp+80h+lpDefaultChar], rbx; lpDefaultChar
0x1400145b7  mov     r8, rdi; lpWideCharStr
0x1400145ba  mov     [rsp+80h+cbMultiByte], edx; cbMultiByte
0x1400145be  xor     ecx, ecx; CodePage
0x1400145c0  xor     edx, edx; dwFlags
0x1400145c2  mov     [rsp+80h+lpMultiByteStr], rsi; lpMultiByteStr
0x1400145c7  call    cs:__imp_WideCharToMultiByte
0x1400145cd  test    eax, eax
0x1400145cf  jz      loc_14001452A
0x1400145d5  mov     eax, [rsp+80h+var_80]
0x1400145d8  mov     eax, 110h
0x1400145dd  sub     rsp, rax
0x1400145e0  lea     rdi, [rsp+190h+Buffer]
0x1400145e5  mov     eax, [rdi]
0x1400145e7  lea     r9, [rbp+40h+MultiByteStr]; lpFilePart
0x1400145eb  mov     r8, rdi; lpBuffer
0x1400145ee  mov     edx, 104h; nBufferLength
0x1400145f3  mov     rcx, rsi; lpFileName
0x1400145f6  call    cs:__imp_GetFullPathNameA
0x1400145fc  test    eax, eax
0x1400145fe  jz      loc_14001452A
0x140014604  mov     [rsp+190h+cchWideChar], 104h; cchWideChar
0x14001460c  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140014610  mov     r8, rdi; lpMultiByteStr
0x140014613  mov     [rsp+190h+lpWideCharStr], r14; lpWideCharStr
0x140014618  xor     edx, edx; dwFlags
0x14001461a  xor     ecx, ecx; CodePage
0x14001461c  call    cs:__imp_MultiByteToWideChar
0x140014622  test    eax, eax
0x140014624  jz      loc_14001452A
0x14001462a  mov     r9d, dword ptr [rbp+40h+MultiByteStr]
0x14001462e  mov     r8, rdi; lpMultiByteStr
0x140014631  sub     r9d, edi; cbMultiByte
0x140014634  mov     [rsp+190h+cchWideChar], ebx; cchWideChar
0x140014638  xor     edx, edx; dwFlags
0x14001463a  mov     [rsp+190h+lpWideCharStr], rbx; lpWideCharStr
0x14001463f  xor     ecx, ecx; CodePage
0x140014641  call    cs:__imp_MultiByteToWideChar
0x140014647  movsxd  rcx, eax
0x14001464a  lea     rdx, [r14+rcx*2]
0x14001464e  mov     [r15], rdx
0x140014651  mov     eax, ebx
0x140014653  mov     rcx, [rbp+40h+var_38]
0x140014657  xor     rcx, rbp; StackCookie
0x14001465a  call    __security_check_cookie
0x14001465f  lea     rsp, [rbp+18h]
0x140014663  pop     r15
0x140014665  pop     r14
0x140014667  pop     rdi
0x140014668  pop     rsi
0x140014669  pop     rbx
0x14001466a  pop     rbp
0x14001466b  retn
```
