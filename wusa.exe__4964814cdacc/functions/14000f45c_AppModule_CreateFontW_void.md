# AppModule::CreateFontW(void)

- ea: `0x14000f45c`
- end: `0x14000f66d`
- name: `?CreateFontW@AppModule@@AEAAJXZ`
- size: `529`
- prototype: `__int64 __fastcall(AppModule *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f8f0`

## callees

- `0x140001a63`
- `0x14000f45c`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000f4a8`
- `KERNEL32!GetLastError` at `0x14000f4e1`
- `KERNEL32!GetLastError` at `0x14000f51d`
- `KERNEL32!GetLastError` at `0x14000f5d9`
- `KERNEL32!GetLastError` at `0x14000f5fc`
- `KERNEL32!GetLastError` at `0x14000f618`
- `KERNEL32!GetLastError` at `0x14000f4a8`
- `KERNEL32!GetLastError` at `0x14000f4e1`
- `KERNEL32!GetLastError` at `0x14000f51d`
- `KERNEL32!GetLastError` at `0x14000f5d9`
- `KERNEL32!GetLastError` at `0x14000f5fc`
- `KERNEL32!GetLastError` at `0x14000f618`
- `GDI32!DeleteDC` at `0x14000f5cf`
- `GDI32!DeleteDC` at `0x14000f5cf`
- `GDI32!GetTextExtentPoint32W` at `0x14000f5a3`
- `GDI32!GetTextExtentPoint32W` at `0x14000f5a3`
- `GDI32!SelectObject` at `0x14000f574`
- `GDI32!SelectObject` at `0x14000f5bd`
- `GDI32!SelectObject` at `0x14000f574`
- `GDI32!SelectObject` at `0x14000f5bd`
- `GDI32!CreateCompatibleDC` at `0x14000f558`
- `GDI32!CreateCompatibleDC` at `0x14000f558`
- `GDI32!DeleteObject` at `0x14000f513`
- `GDI32!DeleteObject` at `0x14000f513`
- `GDI32!CreateFontIndirectW` at `0x14000f4d3`
- `GDI32!CreateFontIndirectW` at `0x14000f4d3`
- `USER32!SystemParametersInfoW` at `0x14000f49e`
- `USER32!SystemParametersInfoW` at `0x14000f49e`

## string_xrefs

- `0x14000f4bd`: `Failure returned by SystemParametersInfo()`
- `0x14000f63b`: `AppModule::CreateFontW`
- `0x14000f4f6`: `Failure returned by CreateFontIndirectW()`
- `0x14000f532`: `Failure returned by DeleteObject()`
- `0x14000f5ee`: `Failure returned by DeleteDC ()`

## pseudocode

```c
__int64 __fastcall AppModule::CreateFontW(AppModule *this)
{
  signed int v2; // eax
  unsigned int v3; // ebx
  const char *v4; // r8
  __int64 v5; // rdx
  HFONT v6; // rdi
  signed int v7; // eax
  void *v8; // rcx
  signed int v9; // eax
  HDC CompatibleDC; // rax
  HDC v11; // rdi
  char *v12; // rbp
  signed int v13; // eax
  signed int v14; // eax
  signed int LastError; // eax
  tagSIZE psizl; // [rsp+20h] [rbp-A8h] BYREF
  LOGFONTW pvParam; // [rsp+30h] [rbp-98h] BYREF

  memset_0(&pvParam, 0, sizeof(pvParam));
  if ( SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0) )
  {
    v6 = CreateFontIndirectW(&pvParam);
    if ( v6 )
    {
      v8 = (void *)*((_QWORD *)this + 16);
      if ( !v8 || DeleteObject(v8) )
      {
        *((_QWORD *)this + 16) = v6;
        v3 = 0;
        *((_DWORD *)this + 34) = 12;
        CompatibleDC = CreateCompatibleDC(0);
        v11 = CompatibleDC;
        if ( !CompatibleDC )
          return v3;
        v12 = (char *)SelectObject(CompatibleDC, *((HGDIOBJ *)this + 16));
        if ( (unsigned __int64)(v12 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          v5 = 775;
        }
        else
        {
          psizl = 0;
          if ( GetTextExtentPoint32W(v11, L"X", 1, &psizl) )
            *((_DWORD *)this + 34) = psizl.cy;
          if ( (char *)SelectObject(v11, v12) - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            if ( DeleteDC(v11) )
              return v3;
            v13 = GetLastError();
            v3 = v13;
            if ( v13 > 0 )
              v3 = (unsigned __int16)v13 | 0x80070000;
            v4 = "Failure returned by DeleteDC ()";
            v5 = 791;
            goto LABEL_30;
          }
          v14 = GetLastError();
          v3 = v14;
          if ( v14 > 0 )
            v3 = (unsigned __int16)v14 | 0x80070000;
          v5 = 787;
        }
        v4 = "Failure returned by SelectObject()";
      }
      else
      {
        v9 = GetLastError();
        v3 = v9;
        if ( v9 > 0 )
          v3 = (unsigned __int16)v9 | 0x80070000;
        v4 = "Failure returned by DeleteObject()";
        v5 = 764;
      }
    }
    else
    {
      v7 = GetLastError();
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      v4 = "Failure returned by CreateFontIndirectW()";
      v5 = 758;
    }
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = "Failure returned by SystemParametersInfo()";
    v5 = 752;
  }
LABEL_30:
  if ( (v3 & 0x80000000) == 0 )
    v3 = -2147467259;
  WusaLogDebugEventA(L"AppModule::CreateFontW", v5, v4);
  return v3;
}

```

## disassembly

```asm
0x14000f45c  push    rbx
0x14000f45e  push    rbp
0x14000f45f  push    rsi
0x14000f460  push    rdi
0x14000f461  sub     rsp, 0A8h
0x14000f468  mov     rax, cs:__security_cookie
0x14000f46f  xor     rax, rsp
0x14000f472  mov     [rsp+0C8h+var_38], rax
0x14000f47a  mov     rsi, rcx
0x14000f47d  mov     ebx, 5Ch ; '\'
0x14000f482  mov     r8d, ebx; Size
0x14000f485  lea     rcx, [rsp+0C8h+pvParam]; void *
0x14000f48a  xor     edx, edx; Val
0x14000f48c  call    memset_0
0x14000f491  xor     r9d, r9d; fWinIni
0x14000f494  lea     r8, [rsp+0C8h+pvParam]; pvParam
0x14000f499  mov     edx, ebx; uiParam
0x14000f49b  lea     ecx, [rbx-3Dh]; uiAction
0x14000f49e  call    cs:__imp_SystemParametersInfoW
0x14000f4a4  test    eax, eax
0x14000f4a6  jnz     short loc_14000F4CE
0x14000f4a8  call    cs:__imp_GetLastError
0x14000f4ae  mov     ebx, eax
0x14000f4b0  test    eax, eax
0x14000f4b2  jle     short loc_14000F4BD
0x14000f4b4  movzx   ebx, ax
0x14000f4b7  or      ebx, 80070000h
0x14000f4bd  lea     r8, aFailureReturne_12; "Failure returned by SystemParametersInf"...
0x14000f4c4  mov     edx, 2F0h
0x14000f4c9  jmp     loc_14000F639
0x14000f4ce  lea     rcx, [rsp+0C8h+pvParam]; lplf
0x14000f4d3  call    cs:__imp_CreateFontIndirectW
0x14000f4d9  mov     rdi, rax
0x14000f4dc  test    rax, rax
0x14000f4df  jnz     short loc_14000F507
0x14000f4e1  call    cs:__imp_GetLastError
0x14000f4e7  mov     ebx, eax
0x14000f4e9  test    eax, eax
0x14000f4eb  jle     short loc_14000F4F6
0x14000f4ed  movzx   ebx, ax
0x14000f4f0  or      ebx, 80070000h
0x14000f4f6  lea     r8, aFailureReturne_9; "Failure returned by CreateFontIndirectW"...
0x14000f4fd  mov     edx, 2F6h
0x14000f502  jmp     loc_14000F639
0x14000f507  mov     rcx, [rsi+80h]; ho
0x14000f50e  test    rcx, rcx
0x14000f511  jz      short loc_14000F543
0x14000f513  call    cs:__imp_DeleteObject
0x14000f519  test    eax, eax
0x14000f51b  jnz     short loc_14000F543
0x14000f51d  call    cs:__imp_GetLastError
0x14000f523  mov     ebx, eax
0x14000f525  test    eax, eax
0x14000f527  jle     short loc_14000F532
0x14000f529  movzx   ebx, ax
0x14000f52c  or      ebx, 80070000h
0x14000f532  lea     r8, aFailureReturne_1; "Failure returned by DeleteObject()"
0x14000f539  mov     edx, 2FCh
0x14000f53e  jmp     loc_14000F639
0x14000f543  xor     ecx, ecx; hdc
0x14000f545  mov     [rsi+80h], rdi
0x14000f54c  xor     ebx, ebx
0x14000f54e  mov     dword ptr [rsi+88h], 0Ch
0x14000f558  call    cs:__imp_CreateCompatibleDC
0x14000f55e  mov     rdi, rax
0x14000f561  test    rax, rax
0x14000f564  jz      loc_14000F64F
0x14000f56a  mov     rdx, [rsi+80h]; h
0x14000f571  mov     rcx, rax; hdc
0x14000f574  call    cs:__imp_SelectObject
0x14000f57a  mov     rbp, rax
0x14000f57d  lea     rcx, [rax-1]
0x14000f581  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14000f585  ja      loc_14000F618
0x14000f58b  lea     r9, [rsp+0C8h+psizl]; psizl
0x14000f590  mov     qword ptr [rsp+0C8h+psizl.cx], rbx
0x14000f595  lea     r8d, [rbx+1]; c
0x14000f599  mov     rcx, rdi; hdc
0x14000f59c  lea     rdx, String; "X"
0x14000f5a3  call    cs:__imp_GetTextExtentPoint32W
0x14000f5a9  test    eax, eax
0x14000f5ab  jz      short loc_14000F5B7
0x14000f5ad  mov     eax, [rsp+0C8h+psizl.cy]
0x14000f5b1  mov     [rsi+88h], eax
0x14000f5b7  mov     rdx, rbp; h
0x14000f5ba  mov     rcx, rdi; hdc
0x14000f5bd  call    cs:__imp_SelectObject
0x14000f5c3  dec     rax
0x14000f5c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000f5ca  ja      short loc_14000F5FC
0x14000f5cc  mov     rcx, rdi; hdc
0x14000f5cf  call    cs:__imp_DeleteDC
0x14000f5d5  test    eax, eax
0x14000f5d7  jnz     short loc_14000F64F
0x14000f5d9  call    cs:__imp_GetLastError
0x14000f5df  mov     ebx, eax
0x14000f5e1  test    eax, eax
0x14000f5e3  jle     short loc_14000F5EE
0x14000f5e5  movzx   ebx, ax
0x14000f5e8  or      ebx, 80070000h
0x14000f5ee  lea     r8, aFailureReturne; "Failure returned by DeleteDC ()"
0x14000f5f5  mov     edx, 317h
0x14000f5fa  jmp     short loc_14000F639
0x14000f5fc  call    cs:__imp_GetLastError
0x14000f602  mov     ebx, eax
0x14000f604  test    eax, eax
0x14000f606  jle     short loc_14000F611
0x14000f608  movzx   ebx, ax
0x14000f60b  or      ebx, 80070000h
0x14000f611  mov     edx, 313h
0x14000f616  jmp     short loc_14000F632
0x14000f618  call    cs:__imp_GetLastError
0x14000f61e  mov     ebx, eax
0x14000f620  test    eax, eax
0x14000f622  jle     short loc_14000F62D
0x14000f624  movzx   ebx, ax
0x14000f627  or      ebx, 80070000h
0x14000f62d  mov     edx, 307h
0x14000f632  lea     r8, aFailureReturne_6; "Failure returned by SelectObject()"
0x14000f639  test    ebx, ebx
0x14000f63b  lea     rcx, aAppmoduleCreat; "AppModule::CreateFontW"
0x14000f642  mov     eax, 80004005h
0x14000f647  cmovns  ebx, eax
0x14000f64a  call    WusaLogDebugEventA
0x14000f64f  mov     eax, ebx
0x14000f651  mov     rcx, [rsp+0C8h+var_38]
0x14000f659  xor     rcx, rsp; StackCookie
0x14000f65c  call    __security_check_cookie
0x14000f661  add     rsp, 0A8h
0x14000f668  pop     rdi
0x14000f669  pop     rsi
0x14000f66a  pop     rbp
0x14000f66b  pop     rbx
0x14000f66c  retn
```
