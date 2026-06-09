# ExpandEnvStringsW

- ea: `0x1800040a0`
- end: `0x180004194`
- name: `ExpandEnvStringsW`
- size: `244`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038c0`
- `0x180004010`
- `0x180004060`

## callees

- `0x1800040a0`
- `0x180010250`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800040fb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800040fb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000416e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000416e`
- `OLEAUT32!__imp_SysFreeString` at `0x180004113`
- `OLEAUT32!__imp_SysFreeString` at `0x180004113`
- `KERNEL32!GetLastError` at `0x18000414b`
- `KERNEL32!GetLastError` at `0x18000414b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800040e3`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180004185`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800040e3`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180004185`

## pseudocode

```c
__int64 __fastcall ExpandEnvStringsW(LPCWSTR lpSrc, OLECHAR **a2)
{
  DWORD v4; // eax
  DWORD v5; // ebp
  OLECHAR *v6; // rdi
  unsigned int v7; // ebx
  signed int LastError; // eax
  WCHAR *v10; // rax
  WCHAR Dst[1024]; // [rsp+20h] [rbp-828h] BYREF

  if ( lpSrc && *lpSrc )
  {
    v4 = ExpandEnvironmentStringsW(lpSrc, Dst, 0x400u);
    v5 = v4;
    if ( v4 )
    {
      if ( v4 <= 0x400 )
      {
        v6 = SysAllocString(Dst);
        if ( v6 )
        {
LABEL_6:
          *a2 = v6;
          v6 = 0;
          v7 = 0;
LABEL_7:
          SysFreeString(v6);
          return v7;
        }
LABEL_12:
        v7 = -2147024882;
        goto LABEL_7;
      }
      v10 = SysAllocStringLen(0, v4 - 1);
      v6 = v10;
      if ( !v10 )
        goto LABEL_12;
      if ( ExpandEnvironmentStringsW(lpSrc, v10, v5) )
        goto LABEL_6;
    }
    else
    {
      v6 = 0;
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x1800040a0  mov     r11, rsp
0x1800040a3  push    rbx
0x1800040a4  push    rsi
0x1800040a5  sub     rsp, 838h
0x1800040ac  mov     rax, cs:__security_cookie
0x1800040b3  xor     rax, rsp
0x1800040b6  mov     [rsp+848h+var_28], rax
0x1800040be  mov     rsi, rdx
0x1800040c1  mov     rbx, rcx
0x1800040c4  test    rcx, rcx
0x1800040c7  jz      short loc_180004145
0x1800040c9  xor     eax, eax
0x1800040cb  cmp     ax, [rcx]
0x1800040ce  jz      short loc_180004145
0x1800040d0  mov     [r11+18h], rbp
0x1800040d4  lea     rdx, [rsp+848h+Dst]; lpDst
0x1800040d9  mov     r8d, 400h; nSize
0x1800040df  mov     [r11-18h], rdi
0x1800040e3  call    cs:__imp_ExpandEnvironmentStringsW
0x1800040e9  mov     ebp, eax
0x1800040eb  test    eax, eax
0x1800040ed  jz      short loc_180004149
0x1800040ef  cmp     eax, 400h
0x1800040f4  ja      short loc_180004169
0x1800040f6  lea     rcx, [rsp+848h+Dst]; psz
0x1800040fb  call    cs:__imp_SysAllocString
0x180004101  mov     rdi, rax
0x180004104  test    rax, rax
0x180004107  jz      short loc_180004162
0x180004109  mov     [rsi], rdi
0x18000410c  xor     edi, edi
0x18000410e  xor     ebx, ebx
0x180004110  mov     rcx, rdi; bstrString
0x180004113  call    cs:__imp_SysFreeString
0x180004119  mov     rdi, [rsp+848h+var_18]
0x180004121  mov     eax, ebx
0x180004123  mov     rbp, [rsp+848h+arg_10]
0x18000412b  mov     rcx, [rsp+848h+var_28]
0x180004133  xor     rcx, rsp; StackCookie
0x180004136  call    __security_check_cookie
0x18000413b  add     rsp, 838h
0x180004142  pop     rsi
0x180004143  pop     rbx
0x180004144  retn
0x180004145  xor     eax, eax
0x180004147  jmp     short loc_18000412B
0x180004149  xor     edi, edi
0x18000414b  call    cs:__imp_GetLastError
0x180004151  mov     ebx, eax
0x180004153  test    eax, eax
0x180004155  jle     short loc_180004110
0x180004157  movzx   ebx, ax
0x18000415a  or      ebx, 80070000h
0x180004160  jmp     short loc_180004110
0x180004162  mov     ebx, 8007000Eh
0x180004167  jmp     short loc_180004110
0x180004169  lea     edx, [rax-1]; ui
0x18000416c  xor     ecx, ecx; strIn
0x18000416e  call    cs:__imp_SysAllocStringLen
0x180004174  mov     rdi, rax
0x180004177  test    rax, rax
0x18000417a  jz      short loc_180004162
0x18000417c  mov     r8d, ebp; nSize
0x18000417f  mov     rdx, rax; lpDst
0x180004182  mov     rcx, rbx; lpSrc
0x180004185  call    cs:__imp_ExpandEnvironmentStringsW
0x18000418b  test    eax, eax
0x18000418d  jz      short loc_18000414B
0x18000418f  jmp     loc_180004109
```
