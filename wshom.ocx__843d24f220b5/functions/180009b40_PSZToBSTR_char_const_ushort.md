# PSZToBSTR(char const *,ushort * *)

- ea: `0x180009b40`
- end: `0x180009bfd`
- name: `?PSZToBSTR@@YAJPEBDPEAPEAG@Z`
- size: `189`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000419c`
- `0x180004cc0`
- `0x180009a9c`
- `0x18000b2f8`
- `0x18000ba20`
- `0x18000c00c`
- `0x18000c128`
- `0x18000d6a0`
- `0x18000dbe0`

## callees

- `0x180009b40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009be8`
- `OLEAUT32!__imp_SysAllocString` at `0x180009be8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180009b9a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180009b9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180009bd0`
- `OLEAUT32!__imp_SysFreeString` at `0x180009bd0`
- `KERNEL32!MultiByteToWideChar` at `0x180009b80`
- `KERNEL32!MultiByteToWideChar` at `0x180009bbc`
- `KERNEL32!MultiByteToWideChar` at `0x180009b80`
- `KERNEL32!MultiByteToWideChar` at `0x180009bbc`

## pseudocode

```c
__int64 __fastcall PSZToBSTR(LPCCH lpMultiByteStr, unsigned __int16 **a2)
{
  int v4; // eax
  int cchWideChar; // ebp
  unsigned __int16 *v6; // rdi
  unsigned int v7; // ebx
  WCHAR *lpWideCharStr; // rax

  *a2 = 0;
  if ( !lpMultiByteStr || !*lpMultiByteStr )
  {
    v6 = SysAllocString(&psz);
    if ( v6 )
      goto LABEL_8;
    goto LABEL_11;
  }
  v4 = MultiByteToWideChar(0, 0, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v4;
  if ( v4 )
  {
    lpWideCharStr = SysAllocStringLen(0, v4 - 1);
    v6 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( !MultiByteToWideChar(0, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
        goto LABEL_5;
LABEL_8:
      *a2 = v6;
      v6 = 0;
      v7 = 0;
      goto LABEL_9;
    }
LABEL_11:
    v7 = -2147024882;
    goto LABEL_9;
  }
  v6 = 0;
LABEL_5:
  v7 = -2147467259;
LABEL_9:
  SysFreeString(v6);
  return v7;
}

```

## disassembly

```asm
0x180009b40  push    rbx
0x180009b42  push    rbp
0x180009b43  push    rsi
0x180009b44  push    rdi
0x180009b45  sub     rsp, 38h
0x180009b49  mov     qword ptr [rdx], 0
0x180009b50  mov     rsi, rdx
0x180009b53  mov     rbx, rcx
0x180009b56  test    rcx, rcx
0x180009b59  jz      loc_180009BE1
0x180009b5f  cmp     byte ptr [rcx], 0
0x180009b62  jz      short loc_180009BE1
0x180009b64  mov     r8, rcx; lpMultiByteStr
0x180009b67  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x180009b6f  xor     ecx, ecx; CodePage
0x180009b71  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x180009b7a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180009b7e  xor     edx, edx; dwFlags
0x180009b80  call    cs:__imp_MultiByteToWideChar
0x180009b86  mov     ebp, eax
0x180009b88  test    eax, eax
0x180009b8a  jnz     short loc_180009B95
0x180009b8c  xor     edi, edi
0x180009b8e  mov     ebx, 80004005h
0x180009b93  jmp     short loc_180009BCD
0x180009b95  lea     edx, [rax-1]; ui
0x180009b98  xor     ecx, ecx; strIn
0x180009b9a  call    cs:__imp_SysAllocStringLen
0x180009ba0  mov     rdi, rax
0x180009ba3  test    rax, rax
0x180009ba6  jz      short loc_180009BF6
0x180009ba8  mov     [rsp+58h+cchWideChar], ebp; cchWideChar
0x180009bac  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180009bb0  mov     r8, rbx; lpMultiByteStr
0x180009bb3  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x180009bb8  xor     edx, edx; dwFlags
0x180009bba  xor     ecx, ecx; CodePage
0x180009bbc  call    cs:__imp_MultiByteToWideChar
0x180009bc2  test    eax, eax
0x180009bc4  jz      short loc_180009B8E
0x180009bc6  mov     [rsi], rdi
0x180009bc9  xor     edi, edi
0x180009bcb  xor     ebx, ebx
0x180009bcd  mov     rcx, rdi; bstrString
0x180009bd0  call    cs:__imp_SysFreeString
0x180009bd6  mov     eax, ebx
0x180009bd8  add     rsp, 38h
0x180009bdc  pop     rdi
0x180009bdd  pop     rsi
0x180009bde  pop     rbp
0x180009bdf  pop     rbx
0x180009be0  retn
0x180009be1  lea     rcx, psz; psz
0x180009be8  call    cs:__imp_SysAllocString
0x180009bee  mov     rdi, rax
0x180009bf1  test    rax, rax
0x180009bf4  jnz     short loc_180009BC6
0x180009bf6  mov     ebx, 8007000Eh
0x180009bfb  jmp     short loc_180009BCD
```
