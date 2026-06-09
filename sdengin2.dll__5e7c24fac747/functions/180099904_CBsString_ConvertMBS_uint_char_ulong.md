# CBsString::ConvertMBS(uint,char * *,ulong *)

- ea: `0x180099904`
- end: `0x180099a49`
- name: `?ConvertMBS@CBsString@@QEAAJIPEAPEADPEAK@Z`
- size: `325`
- prototype: `int(CBsString *__hidden this, unsigned int, char **, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003c10`
- `0x180005c94`
- `0x180006a94`
- `0x180006e84`

## callees

- `0x180099904`
- `0x1800c97da`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009999c`
- `KERNEL32!GetLastError` at `0x18009999c`
- `KERNEL32!WideCharToMultiByte` at `0x180099982`
- `KERNEL32!WideCharToMultiByte` at `0x180099a0c`
- `KERNEL32!WideCharToMultiByte` at `0x180099982`
- `KERNEL32!WideCharToMultiByte` at `0x180099a0c`
- `ole32!CoTaskMemFree` at `0x180099a30`
- `ole32!CoTaskMemFree` at `0x180099a30`
- `ole32!CoTaskMemAlloc` at `0x1800999be`
- `ole32!CoTaskMemAlloc` at `0x1800999be`

## pseudocode

```c
__int64 __fastcall CBsString::ConvertMBS(LPCWCH *this, UINT a2, char **a3, unsigned int *a4)
{
  CHAR *lpMultiByteStr; // rdi
  DWORD v8; // ebx
  const CHAR *lpDefaultChar; // r15
  int v10; // eax
  unsigned int v11; // ebp
  unsigned int v12; // ebx
  signed int LastError; // eax
  unsigned int cbMultiByte; // r12d
  CHAR *v15; // rax
  int v16; // eax

  lpMultiByteStr = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a4 || (*a4 = 0, !a3) )
  {
    v12 = -2147024809;
    goto LABEL_18;
  }
  v8 = 0;
  lpDefaultChar = 0;
  if ( a2 - 65000 > 1 )
  {
    v8 = 1024;
    lpDefaultChar = "_";
  }
  v10 = WideCharToMultiByte(a2, v8, *this, -1, 0, 0, lpDefaultChar, 0);
  v11 = v10;
  if ( v10 < 0 )
  {
LABEL_8:
    v12 = -2147418113;
    goto LABEL_18;
  }
  if ( v10 )
  {
    cbMultiByte = v10 + 1;
    v15 = (CHAR *)CoTaskMemAlloc((unsigned int)(v10 + 1));
    lpMultiByteStr = v15;
    if ( !v15 )
    {
      v12 = -2147024882;
      goto LABEL_18;
    }
    memset_0(v15, 0, cbMultiByte);
    v16 = WideCharToMultiByte(a2, v8, *this, -1, lpMultiByteStr, cbMultiByte, lpDefaultChar, 0);
    if ( v16 < 0 )
      goto LABEL_8;
    if ( v16 )
    {
      *a3 = lpMultiByteStr;
      v12 = 0;
      lpMultiByteStr = 0;
      *a4 = v11;
      goto LABEL_18;
    }
  }
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
  CoTaskMemFree(lpMultiByteStr);
  return v12;
}

```

## disassembly

```asm
0x180099904  mov     [rsp+arg_0], rcx
0x180099909  push    rbx
0x18009990a  push    rbp
0x18009990b  push    rsi
0x18009990c  push    rdi
0x18009990d  push    r12
0x18009990f  push    r13
0x180099911  push    r14
0x180099913  push    r15
0x180099915  sub     rsp, 48h
0x180099919  xor     r12d, r12d
0x18009991c  mov     r14, r9
0x18009991f  mov     rsi, r8
0x180099922  mov     r13d, edx
0x180099925  mov     edi, r12d
0x180099928  test    r8, r8
0x18009992b  jz      short loc_180099930
0x18009992d  mov     [r8], r12
0x180099930  test    r14, r14
0x180099933  jz      loc_180099A28
0x180099939  mov     [r9], r12d
0x18009993c  test    rsi, rsi
0x18009993f  jz      loc_180099A28
0x180099945  lea     eax, [rdx-0FDE8h]
0x18009994b  mov     ebx, r12d
0x18009994e  mov     r15, r12
0x180099951  cmp     eax, 1
0x180099954  jbe     short loc_180099962
0x180099956  mov     ebx, 400h
0x18009995b  lea     r15, DefaultChar; "_"
0x180099962  mov     r8, [rcx]; lpWideCharStr
0x180099965  or      r9d, 0FFFFFFFFh; cchWideChar
0x180099969  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18009996e  mov     edx, ebx; dwFlags
0x180099970  mov     [rsp+88h+lpDefaultChar], r15; lpDefaultChar
0x180099975  mov     ecx, r13d; CodePage
0x180099978  mov     [rsp+88h+cbMultiByte], r12d; cbMultiByte
0x18009997d  mov     [rsp+88h+lpMultiByteStr], r12; lpMultiByteStr
0x180099982  call    cs:__imp_WideCharToMultiByte
0x180099988  mov     ebp, eax
0x18009998a  test    eax, eax
0x18009998c  jns     short loc_180099998
0x18009998e  mov     ebx, 8000FFFFh
0x180099993  jmp     loc_180099A2D
0x180099998  test    ebp, ebp
0x18009999a  jnz     short loc_1800999B7
0x18009999c  call    cs:__imp_GetLastError
0x1800999a2  mov     ebx, eax
0x1800999a4  test    eax, eax
0x1800999a6  jle     loc_180099A2D
0x1800999ac  movzx   ebx, ax
0x1800999af  or      ebx, 80070000h
0x1800999b5  jmp     short loc_180099A2D
0x1800999b7  lea     r12d, [rax+1]
0x1800999bb  mov     ecx, r12d; cb
0x1800999be  call    cs:__imp_CoTaskMemAlloc
0x1800999c4  mov     rdi, rax
0x1800999c7  test    rax, rax
0x1800999ca  jnz     short loc_1800999D3
0x1800999cc  mov     ebx, 8007000Eh
0x1800999d1  jmp     short loc_180099A2D
0x1800999d3  mov     r8d, r12d; Size
0x1800999d6  xor     edx, edx; Val
0x1800999d8  mov     rcx, rdi; void *
0x1800999db  call    memset_0
0x1800999e0  mov     r8, [rsp+88h+arg_0]
0x1800999e8  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800999ec  mov     [rsp+88h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800999f5  mov     edx, ebx; dwFlags
0x1800999f7  mov     [rsp+88h+lpDefaultChar], r15; lpDefaultChar
0x1800999fc  mov     ecx, r13d; CodePage
0x1800999ff  mov     [rsp+88h+cbMultiByte], r12d; cbMultiByte
0x180099a04  mov     r8, [r8]; lpWideCharStr
0x180099a07  mov     [rsp+88h+lpMultiByteStr], rdi; lpMultiByteStr
0x180099a0c  call    cs:__imp_WideCharToMultiByte
0x180099a12  test    eax, eax
0x180099a14  js      loc_18009998E
0x180099a1a  jz      short loc_18009999C
0x180099a1c  mov     [rsi], rdi
0x180099a1f  xor     ebx, ebx
0x180099a21  xor     edi, edi
0x180099a23  mov     [r14], ebp
0x180099a26  jmp     short loc_180099A2D
0x180099a28  mov     ebx, 80070057h
0x180099a2d  mov     rcx, rdi; pv
0x180099a30  call    cs:__imp_CoTaskMemFree
0x180099a36  mov     eax, ebx
0x180099a38  add     rsp, 48h
0x180099a3c  pop     r15
0x180099a3e  pop     r14
0x180099a40  pop     r13
0x180099a42  pop     r12
0x180099a44  pop     rdi
0x180099a45  pop     rsi
0x180099a46  pop     rbp
0x180099a47  pop     rbx
0x180099a48  retn
```
