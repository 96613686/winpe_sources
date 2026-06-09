# GetProcessFullImageName(ulong,ushort * *)

- ea: `0x180005594`
- end: `0x1800056e6`
- name: `?GetProcessFullImageName@@YAJKPEAPEAG@Z`
- size: `338`
- prototype: `__int64 __fastcall(DWORD dwProcessId, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180005388`

## callees

- `0x180005594`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800056cc`
- `KERNEL32!CloseHandle` at `0x1800056cc`
- `KERNEL32!GetLastError` at `0x180005605`
- `KERNEL32!GetLastError` at `0x18000566e`
- `KERNEL32!GetLastError` at `0x180005605`
- `KERNEL32!GetLastError` at `0x18000566e`
- `KERNEL32!OpenProcess` at `0x1800055f7`
- `KERNEL32!OpenProcess` at `0x1800055f7`
- `KERNEL32!QueryFullProcessImageNameW` at `0x180005660`
- `KERNEL32!QueryFullProcessImageNameW` at `0x180005660`
- `OLEAUT32!__imp_SysAllocString` at `0x18000568c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000568c`

## pseudocode

```c
__int64 __fastcall GetProcessFullImageName(DWORD dwProcessId, unsigned __int16 **a2, int a3)
{
  OLECHAR *v5; // rsi
  signed int v6; // ebx
  char *v7; // rax
  char *v8; // rdi
  signed int LastError; // eax
  const char *v10; // rdx
  int v11; // r8d
  signed int v12; // eax
  DWORD dwSize; // [rsp+70h] [rbp+18h] BYREF

  dwSize = 260;
  v5 = (OLECHAR *)WdcAlloc(0x208u, (const char *)a2, a3);
  if ( v5 )
  {
    *v5 = 0;
    v7 = (char *)OpenProcess(0x400u, 0, dwProcessId);
    v8 = v7;
    if ( v7 && v7 != (char *)-1LL )
      goto LABEL_12;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
      {
LABEL_12:
        if ( QueryFullProcessImageNameW(v8, 0, v5, &dwSize) )
        {
          v6 = 0;
LABEL_18:
          *a2 = SysAllocString(v5);
          goto LABEL_21;
        }
        v12 = GetLastError();
        v6 = v12;
        if ( v12 )
        {
          if ( v12 > 0 )
            v6 = (unsigned __int16)v12 | 0x80070000;
          if ( v6 >= 0 )
            goto LABEL_18;
        }
        else
        {
          v6 = -2147467259;
        }
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\port.cpp",
          "GetProcessFullImageName",
          0,
          L"FAILURE: 0x%08x",
          v6);
LABEL_21:
        if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v8);
        goto LABEL_23;
      }
    }
    else
    {
      v6 = -2147467259;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\port.cpp",
      "GetProcessFullImageName",
      0,
      L"FAILURE: 0x%08x",
      v6);
LABEL_23:
    WdcFree(v5, v10, v11);
    return (unsigned int)v6;
  }
  v6 = -2147024882;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\port.cpp",
    "GetProcessFullImageName",
    0,
    L"FAILURE: 0x%08x",
    -2147024882);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005594  push    rbx
0x180005596  push    rsi
0x180005597  push    rdi
0x180005598  push    r14
0x18000559a  sub     rsp, 38h
0x18000559e  mov     ebx, ecx
0x1800055a0  mov     [rsp+58h+dwSize], 104h
0x1800055a8  mov     ecx, 208h; dwBytes
0x1800055ad  mov     r14, rdx
0x1800055b0  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800055b5  mov     rsi, rax
0x1800055b8  test    rax, rax
0x1800055bb  jnz     short loc_1800055E8
0x1800055bd  mov     ebx, 8007000Eh
0x1800055c2  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800055c9  xor     r8d, r8d; int
0x1800055cc  mov     [rsp+58h+var_38], ebx
0x1800055d0  lea     rdx, aGetprocessfull; "GetProcessFullImageName"
0x1800055d7  lea     rcx, aBaseDiagnosisP; "base\\diagnosis\\pdui\\perfmon\\mon\\po"...
0x1800055de  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800055e3  jmp     loc_1800056DA
0x1800055e8  xor     eax, eax
0x1800055ea  mov     r8d, ebx; dwProcessId
0x1800055ed  xor     edx, edx; bInheritHandle
0x1800055ef  mov     [rsi], ax
0x1800055f2  mov     ecx, 400h; dwDesiredAccess
0x1800055f7  call    cs:__imp_OpenProcess
0x1800055fd  mov     rdi, rax
0x180005600  test    rax, rax
0x180005603  jnz     short loc_18000564D
0x180005605  call    cs:__imp_GetLastError
0x18000560b  mov     ebx, eax
0x18000560d  test    eax, eax
0x18000560f  jz      short loc_180005622
0x180005611  jle     short loc_18000561C
0x180005613  movzx   ebx, ax
0x180005616  or      ebx, 80070000h
0x18000561c  test    ebx, ebx
0x18000561e  jns     short loc_180005653
0x180005620  jmp     short loc_180005627
0x180005622  mov     ebx, 80004005h
0x180005627  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18000562e  mov     [rsp+58h+var_38], ebx
0x180005632  xor     r8d, r8d; int
0x180005635  lea     rdx, aGetprocessfull; "GetProcessFullImageName"
0x18000563c  lea     rcx, aBaseDiagnosisP; "base\\diagnosis\\pdui\\perfmon\\mon\\po"...
0x180005643  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180005648  jmp     loc_1800056D2
0x18000564d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180005651  jz      short loc_180005605
0x180005653  lea     r9, [rsp+58h+dwSize]; lpdwSize
0x180005658  mov     r8, rsi; lpExeName
0x18000565b  xor     edx, edx; dwFlags
0x18000565d  mov     rcx, rdi; hProcess
0x180005660  call    cs:__imp_QueryFullProcessImageNameW
0x180005666  test    eax, eax
0x180005668  jz      short loc_18000566E
0x18000566a  xor     ebx, ebx
0x18000566c  jmp     short loc_180005689
0x18000566e  call    cs:__imp_GetLastError
0x180005674  mov     ebx, eax
0x180005676  test    eax, eax
0x180005678  jz      short loc_180005697
0x18000567a  jle     short loc_180005685
0x18000567c  movzx   ebx, ax
0x18000567f  or      ebx, 80070000h
0x180005685  test    ebx, ebx
0x180005687  js      short loc_18000569C
0x180005689  mov     rcx, rsi; psz
0x18000568c  call    cs:__imp_SysAllocString
0x180005692  mov     [r14], rax
0x180005695  jmp     short loc_1800056BF
0x180005697  mov     ebx, 80004005h
0x18000569c  mov     eax, ebx
0x18000569e  mov     [rsp+58h+var_38], ebx
0x1800056a2  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800056a9  xor     r8d, r8d; int
0x1800056ac  lea     rdx, aGetprocessfull; "GetProcessFullImageName"
0x1800056b3  lea     rcx, aBaseDiagnosisP; "base\\diagnosis\\pdui\\perfmon\\mon\\po"...
0x1800056ba  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800056bf  lea     rcx, [rdi-1]
0x1800056c3  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800056c7  ja      short loc_1800056D2
0x1800056c9  mov     rcx, rdi; hObject
0x1800056cc  call    cs:__imp_CloseHandle
0x1800056d2  mov     rcx, rsi; void *
0x1800056d5  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x1800056da  mov     eax, ebx
0x1800056dc  add     rsp, 38h
0x1800056e0  pop     r14
0x1800056e2  pop     rdi
0x1800056e3  pop     rsi
0x1800056e4  pop     rbx
0x1800056e5  retn
```
