# CBsString::ConvertMBS(uint,char * *,ulong *)

- ea: `0x18009df24`
- end: `0x18009e08f`
- name: `?ConvertMBS@CBsString@@QEAAJIPEAPEADPEAK@Z`
- size: `363`
- prototype: `int(CBsString *__hidden this, unsigned int, char **, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003d30`
- `0x180005d94`
- `0x180006bc8`
- `0x180006fd0`

## callees

- `0x18009df24`
- `0x1800cf56a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009dfc2`
- `KERNEL32!GetLastError` at `0x18009dfc2`
- `KERNEL32!WideCharToMultiByte` at `0x18009dfa2`
- `KERNEL32!WideCharToMultiByte` at `0x18009e041`
- `KERNEL32!WideCharToMultiByte` at `0x18009dfa2`
- `KERNEL32!WideCharToMultiByte` at `0x18009e041`
- `ole32!CoTaskMemFree` at `0x18009e06f`
- `ole32!CoTaskMemFree` at `0x18009e06f`
- `ole32!CoTaskMemAlloc` at `0x18009dfed`
- `ole32!CoTaskMemAlloc` at `0x18009dfed`

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
0x18009df24  mov     [rsp+arg_0], rcx
0x18009df29  push    rbx
0x18009df2a  push    rbp
0x18009df2b  push    rsi
0x18009df2c  push    rdi
0x18009df2d  push    r12
0x18009df2f  push    r13
0x18009df31  push    r14
0x18009df33  push    r15
0x18009df35  sub     rsp, 48h
0x18009df39  xor     r12d, r12d
0x18009df3c  mov     r14, r9
0x18009df3f  mov     rsi, r8
0x18009df42  mov     r13d, edx
0x18009df45  mov     edi, r12d
0x18009df48  test    r8, r8
0x18009df4b  jz      short loc_18009DF50
0x18009df4d  mov     [r8], r12
0x18009df50  test    r14, r14
0x18009df53  jz      loc_18009E067
0x18009df59  mov     [r9], r12d
0x18009df5c  test    rsi, rsi
0x18009df5f  jz      loc_18009E067
0x18009df65  lea     eax, [rdx-0FDE8h]
0x18009df6b  mov     ebx, r12d
0x18009df6e  mov     r15, r12
0x18009df71  cmp     eax, 1
0x18009df74  jbe     short loc_18009DF82
0x18009df76  mov     ebx, 400h
0x18009df7b  lea     r15, DefaultChar; "_"
0x18009df82  mov     r8, [rcx]; lpWideCharStr
0x18009df85  or      r9d, 0FFFFFFFFh; cchWideChar
0x18009df89  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18009df8e  mov     edx, ebx; dwFlags
0x18009df90  mov     [rsp+88h+lpDefaultChar], r15; lpDefaultChar
0x18009df95  mov     ecx, r13d; CodePage
0x18009df98  mov     [rsp+88h+cbMultiByte], r12d; cbMultiByte
0x18009df9d  mov     [rsp+88h+lpMultiByteStr], r12; lpMultiByteStr
0x18009dfa2  call    cs:__imp_WideCharToMultiByte
0x18009dfa9  nop     dword ptr [rax+rax+00h]
0x18009dfae  mov     ebp, eax
0x18009dfb0  test    eax, eax
0x18009dfb2  jns     short loc_18009DFBE
0x18009dfb4  mov     ebx, 8000FFFFh
0x18009dfb9  jmp     loc_18009E06C
0x18009dfbe  test    ebp, ebp
0x18009dfc0  jnz     short loc_18009DFE6
0x18009dfc2  call    cs:__imp_GetLastError
0x18009dfc9  nop     dword ptr [rax+rax+00h]
0x18009dfce  mov     ebx, eax
0x18009dfd0  test    eax, eax
0x18009dfd2  jle     loc_18009E06C
0x18009dfd8  movzx   ebx, ax
0x18009dfdb  or      ebx, 80070000h
0x18009dfe1  jmp     loc_18009E06C
0x18009dfe6  lea     r12d, [rax+1]
0x18009dfea  mov     ecx, r12d; cb
0x18009dfed  call    cs:__imp_CoTaskMemAlloc
0x18009dff4  nop     dword ptr [rax+rax+00h]
0x18009dff9  mov     rdi, rax
0x18009dffc  test    rax, rax
0x18009dfff  jnz     short loc_18009E008
0x18009e001  mov     ebx, 8007000Eh
0x18009e006  jmp     short loc_18009E06C
0x18009e008  mov     r8d, r12d; Size
0x18009e00b  xor     edx, edx; Val
0x18009e00d  mov     rcx, rdi; void *
0x18009e010  call    memset_0
0x18009e015  mov     r8, [rsp+88h+arg_0]
0x18009e01d  or      r9d, 0FFFFFFFFh; cchWideChar
0x18009e021  mov     [rsp+88h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18009e02a  mov     edx, ebx; dwFlags
0x18009e02c  mov     [rsp+88h+lpDefaultChar], r15; lpDefaultChar
0x18009e031  mov     ecx, r13d; CodePage
0x18009e034  mov     [rsp+88h+cbMultiByte], r12d; cbMultiByte
0x18009e039  mov     r8, [r8]; lpWideCharStr
0x18009e03c  mov     [rsp+88h+lpMultiByteStr], rdi; lpMultiByteStr
0x18009e041  call    cs:__imp_WideCharToMultiByte
0x18009e048  nop     dword ptr [rax+rax+00h]
0x18009e04d  test    eax, eax
0x18009e04f  js      loc_18009DFB4
0x18009e055  jz      loc_18009DFC2
0x18009e05b  mov     [rsi], rdi
0x18009e05e  xor     ebx, ebx
0x18009e060  xor     edi, edi
0x18009e062  mov     [r14], ebp
0x18009e065  jmp     short loc_18009E06C
0x18009e067  mov     ebx, 80070057h
0x18009e06c  mov     rcx, rdi; pv
0x18009e06f  call    cs:__imp_CoTaskMemFree
0x18009e076  nop     dword ptr [rax+rax+00h]
0x18009e07b  mov     eax, ebx
0x18009e07d  add     rsp, 48h
0x18009e081  pop     r15
0x18009e083  pop     r14
0x18009e085  pop     r13
0x18009e087  pop     r12
0x18009e089  pop     rdi
0x18009e08a  pop     rsi
0x18009e08b  pop     rbp
0x18009e08c  pop     rbx
0x18009e08d  retn
```
