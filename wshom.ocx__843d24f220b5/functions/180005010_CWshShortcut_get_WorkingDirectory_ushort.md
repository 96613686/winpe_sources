# CWshShortcut::get_WorkingDirectory(ushort * *)

- ea: `0x180005010`
- end: `0x18000511f`
- name: `?get_WorkingDirectory@CWshShortcut@@UEAAJPEAPEAG@Z`
- size: `271`
- prototype: `__int64 __fastcall(CWshShortcut *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005010`
- `0x180010250`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800050b3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800050b3`
- `KERNEL32!MultiByteToWideChar` at `0x1800050a2`
- `KERNEL32!MultiByteToWideChar` at `0x1800050d9`
- `KERNEL32!MultiByteToWideChar` at `0x1800050a2`
- `KERNEL32!MultiByteToWideChar` at `0x1800050d9`

## pseudocode

```c
__int64 __fastcall CWshShortcut::get_WorkingDirectory(CWshShortcut *this, unsigned __int16 **a2)
{
  __int64 v3; // rcx
  __int64 result; // rax
  int v5; // eax
  int cchWideChar; // edi
  unsigned __int16 *lpWideCharStr; // rax
  CHAR MultiByteStr[1024]; // [rsp+30h] [rbp-418h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v3 = *((_QWORD *)this + 9);
  if ( !v3 )
    return 2147500037LL;
  result = (*(__int64 (__fastcall **)(__int64, CHAR *, __int64))(*(_QWORD *)v3 + 64LL))(v3, MultiByteStr, 1024);
  if ( (int)result >= 0 )
  {
    v5 = MultiByteToWideChar(0, 0, MultiByteStr, -1, 0, 0);
    cchWideChar = v5;
    if ( v5 )
    {
      lpWideCharStr = SysAllocStringLen(0, v5 - 1);
      *a2 = lpWideCharStr;
      if ( lpWideCharStr )
        MultiByteToWideChar(0, 0, MultiByteStr, -1, lpWideCharStr, cchWideChar);
      result = 0;
      if ( !*a2 )
        return 2147942414LL;
    }
    else
    {
      *a2 = 0;
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005010  push    rbx
0x180005012  sub     rsp, 440h
0x180005019  mov     rax, cs:__security_cookie
0x180005020  xor     rax, rsp
0x180005023  mov     [rsp+448h+var_18], rax
0x18000502b  mov     rbx, rdx
0x18000502e  test    rdx, rdx
0x180005031  jz      loc_180005101
0x180005037  mov     rcx, [rcx+48h]
0x18000503b  test    rcx, rcx
0x18000503e  jz      loc_18000510B
0x180005044  mov     rax, [rcx]
0x180005047  lea     rdx, [rsp+448h+MultiByteStr]
0x18000504c  mov     r8d, 400h
0x180005052  mov     rax, [rax+40h]
0x180005056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000505b  test    eax, eax
0x18000505d  jns     short loc_180005078
0x18000505f  mov     rcx, [rsp+448h+var_18]
0x180005067  xor     rcx, rsp; StackCookie
0x18000506a  call    __security_check_cookie
0x18000506f  add     rsp, 440h
0x180005076  pop     rbx
0x180005077  retn
0x180005078  mov     [rsp+448h+arg_10], rsi
0x180005080  lea     r8, [rsp+448h+MultiByteStr]; lpMultiByteStr
0x180005085  xor     esi, esi
0x180005087  mov     [rsp+448h+arg_18], rdi
0x18000508f  mov     [rsp+448h+cchWideChar], esi; cchWideChar
0x180005093  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180005099  xor     edx, edx; dwFlags
0x18000509b  mov     [rsp+448h+lpWideCharStr], rsi; lpWideCharStr
0x1800050a0  xor     ecx, ecx; CodePage
0x1800050a2  call    cs:__imp_MultiByteToWideChar
0x1800050a8  mov     edi, eax
0x1800050aa  test    eax, eax
0x1800050ac  jz      short loc_180005115
0x1800050ae  lea     edx, [rax-1]; ui
0x1800050b1  xor     ecx, ecx; strIn
0x1800050b3  call    cs:__imp_SysAllocStringLen
0x1800050b9  mov     [rbx], rax
0x1800050bc  test    rax, rax
0x1800050bf  jz      short loc_1800050DF
0x1800050c1  mov     [rsp+448h+cchWideChar], edi; cchWideChar
0x1800050c5  lea     r8, [rsp+448h+MultiByteStr]; lpMultiByteStr
0x1800050ca  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800050d0  mov     [rsp+448h+lpWideCharStr], rax; lpWideCharStr
0x1800050d5  xor     edx, edx; dwFlags
0x1800050d7  xor     ecx, ecx; CodePage
0x1800050d9  call    cs:__imp_MultiByteToWideChar
0x1800050df  mov     eax, esi
0x1800050e1  mov     ecx, 8007000Eh
0x1800050e6  cmp     [rbx], rax
0x1800050e9  cmovz   eax, ecx
0x1800050ec  mov     rsi, [rsp+448h+arg_10]
0x1800050f4  mov     rdi, [rsp+448h+arg_18]
0x1800050fc  jmp     loc_18000505F
0x180005101  mov     eax, 80004003h
0x180005106  jmp     loc_18000505F
0x18000510b  mov     eax, 80004005h
0x180005110  jmp     loc_18000505F
0x180005115  mov     [rbx], rsi
0x180005118  mov     eax, 8007000Eh
0x18000511d  jmp     short loc_1800050EC
```
