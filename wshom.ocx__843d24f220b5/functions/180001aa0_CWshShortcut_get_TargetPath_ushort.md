# CWshShortcut::get_TargetPath(ushort * *)

- ea: `0x180001aa0`
- end: `0x180001bcf`
- name: `?get_TargetPath@CWshShortcut@@UEAAJPEAPEAG@Z`
- size: `303`
- prototype: `__int64 __fastcall(CWshShortcut *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001aa0`
- `0x180010212`
- `0x180010250`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180001b52`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180001b52`
- `KERNEL32!MultiByteToWideChar` at `0x180001b41`
- `KERNEL32!MultiByteToWideChar` at `0x180001b7b`
- `KERNEL32!MultiByteToWideChar` at `0x180001b41`
- `KERNEL32!MultiByteToWideChar` at `0x180001b7b`

## pseudocode

```c
__int64 __fastcall CWshShortcut::get_TargetPath(CWshShortcut *this, unsigned __int16 **a2)
{
  __int64 v3; // rbx
  __int64 result; // rax
  int v5; // eax
  int cchWideChar; // ebx
  unsigned __int16 *lpWideCharStr; // rax
  CHAR v8[320]; // [rsp+30h] [rbp-558h] BYREF
  CHAR MultiByteStr[1024]; // [rsp+170h] [rbp-418h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v3 = *((_QWORD *)this + 9);
  if ( !v3 )
    return 2147500037LL;
  memset_0(v8, 0, sizeof(v8));
  result = (*(__int64 (__fastcall **)(__int64, CHAR *, __int64, CHAR *, int))(*(_QWORD *)v3 + 24LL))(
             v3,
             MultiByteStr,
             1024,
             v8,
             2);
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
0x180001aa0  push    rdi
0x180001aa2  sub     rsp, 580h
0x180001aa9  mov     rax, cs:__security_cookie
0x180001ab0  xor     rax, rsp
0x180001ab3  mov     [rsp+588h+var_18], rax
0x180001abb  mov     rdi, rdx
0x180001abe  test    rdx, rdx
0x180001ac1  jz      loc_180001BB7
0x180001ac7  mov     [rsp+588h+arg_10], rbx
0x180001acf  mov     rbx, [rcx+48h]
0x180001ad3  test    rbx, rbx
0x180001ad6  jz      loc_180001BBE
0x180001adc  xor     edx, edx; Val
0x180001ade  lea     rcx, [rsp+588h+var_558]; void *
0x180001ae3  mov     r8d, 140h; Size
0x180001ae9  call    memset_0
0x180001aee  mov     rax, [rbx]
0x180001af1  lea     r9, [rsp+588h+var_558]
0x180001af6  mov     r8d, 400h
0x180001afc  mov     dword ptr [rsp+588h+lpWideCharStr], 2
0x180001b04  lea     rdx, [rsp+588h+MultiByteStr]
0x180001b0c  mov     rcx, rbx
0x180001b0f  mov     rax, [rax+18h]
0x180001b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b18  test    eax, eax
0x180001b1a  js      short loc_180001B96
0x180001b1c  mov     [rsp+588h+arg_18], rsi
0x180001b24  lea     r8, [rsp+588h+MultiByteStr]; lpMultiByteStr
0x180001b2c  xor     esi, esi
0x180001b2e  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180001b34  mov     [rsp+588h+cchWideChar], esi; cchWideChar
0x180001b38  xor     edx, edx; dwFlags
0x180001b3a  xor     ecx, ecx; CodePage
0x180001b3c  mov     [rsp+588h+lpWideCharStr], rsi; lpWideCharStr
0x180001b41  call    cs:__imp_MultiByteToWideChar
0x180001b47  mov     ebx, eax
0x180001b49  test    eax, eax
0x180001b4b  jz      short loc_180001BC5
0x180001b4d  lea     edx, [rax-1]; ui
0x180001b50  xor     ecx, ecx; strIn
0x180001b52  call    cs:__imp_SysAllocStringLen
0x180001b58  mov     [rdi], rax
0x180001b5b  test    rax, rax
0x180001b5e  jz      short loc_180001B81
0x180001b60  mov     [rsp+588h+cchWideChar], ebx; cchWideChar
0x180001b64  lea     r8, [rsp+588h+MultiByteStr]; lpMultiByteStr
0x180001b6c  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180001b72  mov     [rsp+588h+lpWideCharStr], rax; lpWideCharStr
0x180001b77  xor     edx, edx; dwFlags
0x180001b79  xor     ecx, ecx; CodePage
0x180001b7b  call    cs:__imp_MultiByteToWideChar
0x180001b81  mov     eax, esi
0x180001b83  mov     ecx, 8007000Eh
0x180001b88  cmp     [rdi], rax
0x180001b8b  cmovz   eax, ecx
0x180001b8e  mov     rsi, [rsp+588h+arg_18]
0x180001b96  mov     rbx, [rsp+588h+arg_10]
0x180001b9e  mov     rcx, [rsp+588h+var_18]
0x180001ba6  xor     rcx, rsp; StackCookie
0x180001ba9  call    __security_check_cookie
0x180001bae  add     rsp, 580h
0x180001bb5  pop     rdi
0x180001bb6  retn
0x180001bb7  mov     eax, 80004003h
0x180001bbc  jmp     short loc_180001B9E
0x180001bbe  mov     eax, 80004005h
0x180001bc3  jmp     short loc_180001B96
0x180001bc5  mov     [rdi], rsi
0x180001bc8  mov     eax, 8007000Eh
0x180001bcd  jmp     short loc_180001B8E
```
