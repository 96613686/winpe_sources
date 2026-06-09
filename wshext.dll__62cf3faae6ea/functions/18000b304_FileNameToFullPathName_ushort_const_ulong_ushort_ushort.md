# FileNameToFullPathName(ushort const *,ulong,ushort *,ushort * *)

- ea: `0x18000b304`
- end: `0x18000b494`
- name: `?FileNameToFullPathName@@YAJPEBGKPEAGPEAPEAG@Z`
- size: `400`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000acd0`
- `0x18000aeb0`

## callees

- `0x18000b304`
- `0x18000d1c0`
- `0x18000d250`

## import_xrefs

- `KERNEL32!GetFullPathNameA` at `0x18000b41e`
- `KERNEL32!GetFullPathNameA` at `0x18000b41e`
- `KERNEL32!GetFullPathNameW` at `0x18000b344`
- `KERNEL32!GetFullPathNameW` at `0x18000b344`
- `KERNEL32!GetLastError` at `0x18000b352`
- `KERNEL32!GetLastError` at `0x18000b352`
- `KERNEL32!MultiByteToWideChar` at `0x18000b444`
- `KERNEL32!MultiByteToWideChar` at `0x18000b469`
- `KERNEL32!MultiByteToWideChar` at `0x18000b444`
- `KERNEL32!MultiByteToWideChar` at `0x18000b469`
- `KERNEL32!WideCharToMultiByte` at `0x18000b38e`
- `KERNEL32!WideCharToMultiByte` at `0x18000b3ef`
- `KERNEL32!WideCharToMultiByte` at `0x18000b38e`
- `KERNEL32!WideCharToMultiByte` at `0x18000b3ef`

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
0x18000b304  push    rbp
0x18000b306  push    rbx
0x18000b307  push    rsi
0x18000b308  push    rdi
0x18000b309  push    r14
0x18000b30b  push    r15
0x18000b30d  sub     rsp, 58h
0x18000b311  lea     rbp, [rsp+40h]
0x18000b316  mov     rax, cs:__security_cookie
0x18000b31d  xor     rax, rbp
0x18000b320  mov     [rbp+40h+var_38], rax
0x18000b324  xor     ebx, ebx
0x18000b326  mov     qword ptr [rbp+40h+MultiByteStr], 0
0x18000b32e  cmp     cs:?g_fWindowsNT@Global@@2_NA, bl; bool Global::g_fWindowsNT
0x18000b334  mov     r15, r9
0x18000b337  mov     r14, r8
0x18000b33a  mov     rdi, rcx
0x18000b33d  jz      short loc_18000B370
0x18000b33f  mov     edx, 104h; nBufferLength
0x18000b344  call    cs:__imp_GetFullPathNameW
0x18000b34a  test    eax, eax
0x18000b34c  jnz     loc_18000B479
0x18000b352  call    cs:__imp_GetLastError
0x18000b358  mov     ebx, eax
0x18000b35a  test    eax, eax
0x18000b35c  jle     loc_18000B479
0x18000b362  movzx   ebx, ax
0x18000b365  or      ebx, 80070000h
0x18000b36b  jmp     loc_18000B479
0x18000b370  mov     [rsp+80h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x18000b375  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000b379  mov     [rsp+80h+lpDefaultChar], rbx; lpDefaultChar
0x18000b37e  mov     r8, rdi; lpWideCharStr
0x18000b381  mov     [rsp+80h+cbMultiByte], ebx; cbMultiByte
0x18000b385  xor     edx, edx; dwFlags
0x18000b387  xor     ecx, ecx; CodePage
0x18000b389  mov     [rsp+80h+lpMultiByteStr], rbx; lpMultiByteStr
0x18000b38e  call    cs:__imp_WideCharToMultiByte
0x18000b394  movsxd  rdx, eax
0x18000b397  test    eax, eax
0x18000b399  jz      short loc_18000B352
0x18000b39b  lea     rcx, [rdx+0Fh]
0x18000b39f  cmp     rcx, rdx
0x18000b3a2  ja      short loc_18000B3AE
0x18000b3a4  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000b3ae  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000b3b2  mov     rax, rcx
0x18000b3b5  call    _alloca_probe
0x18000b3ba  sub     rsp, rcx
0x18000b3bd  lea     rsi, [rsp+80h+MultiByteStr]
0x18000b3c2  test    rsi, rsi
0x18000b3c5  jnz     short loc_18000B3D1
0x18000b3c7  mov     ebx, 8007000Eh
0x18000b3cc  jmp     loc_18000B479
0x18000b3d1  mov     [rsp+80h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x18000b3d6  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000b3da  mov     [rsp+80h+lpDefaultChar], rbx; lpDefaultChar
0x18000b3df  mov     r8, rdi; lpWideCharStr
0x18000b3e2  mov     [rsp+80h+cbMultiByte], edx; cbMultiByte
0x18000b3e6  xor     ecx, ecx; CodePage
0x18000b3e8  xor     edx, edx; dwFlags
0x18000b3ea  mov     [rsp+80h+lpMultiByteStr], rsi; lpMultiByteStr
0x18000b3ef  call    cs:__imp_WideCharToMultiByte
0x18000b3f5  test    eax, eax
0x18000b3f7  jz      loc_18000B352
0x18000b3fd  mov     eax, [rsp+80h+var_80]
0x18000b400  mov     eax, 110h
0x18000b405  sub     rsp, rax
0x18000b408  lea     rdi, [rsp+190h+Buffer]
0x18000b40d  mov     eax, [rdi]
0x18000b40f  lea     r9, [rbp+40h+MultiByteStr]; lpFilePart
0x18000b413  mov     r8, rdi; lpBuffer
0x18000b416  mov     edx, 104h; nBufferLength
0x18000b41b  mov     rcx, rsi; lpFileName
0x18000b41e  call    cs:__imp_GetFullPathNameA
0x18000b424  test    eax, eax
0x18000b426  jz      loc_18000B352
0x18000b42c  mov     [rsp+190h+cchWideChar], 104h; cchWideChar
0x18000b434  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000b438  mov     r8, rdi; lpMultiByteStr
0x18000b43b  mov     [rsp+190h+lpWideCharStr], r14; lpWideCharStr
0x18000b440  xor     edx, edx; dwFlags
0x18000b442  xor     ecx, ecx; CodePage
0x18000b444  call    cs:__imp_MultiByteToWideChar
0x18000b44a  test    eax, eax
0x18000b44c  jz      loc_18000B352
0x18000b452  mov     r9d, dword ptr [rbp+40h+MultiByteStr]
0x18000b456  mov     r8, rdi; lpMultiByteStr
0x18000b459  sub     r9d, edi; cbMultiByte
0x18000b45c  mov     [rsp+190h+cchWideChar], ebx; cchWideChar
0x18000b460  xor     edx, edx; dwFlags
0x18000b462  mov     [rsp+190h+lpWideCharStr], rbx; lpWideCharStr
0x18000b467  xor     ecx, ecx; CodePage
0x18000b469  call    cs:__imp_MultiByteToWideChar
0x18000b46f  movsxd  rcx, eax
0x18000b472  lea     rdx, [r14+rcx*2]
0x18000b476  mov     [r15], rdx
0x18000b479  mov     eax, ebx
0x18000b47b  mov     rcx, [rbp+40h+var_38]
0x18000b47f  xor     rcx, rbp; StackCookie
0x18000b482  call    __security_check_cookie
0x18000b487  lea     rsp, [rbp+18h]
0x18000b48b  pop     r15
0x18000b48d  pop     r14
0x18000b48f  pop     rdi
0x18000b490  pop     rsi
0x18000b491  pop     rbx
0x18000b492  pop     rbp
0x18000b493  retn
```
