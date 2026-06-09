# HostCharToAce

- ea: `0x1800da348`
- end: `0x1800da527`
- name: `HostCharToAce`
- size: `479`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, UINT CodePage)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c1cc0`

## callees

- `0x1800701d0`
- `0x1800da348`
- `0x1800da530`
- `0x18014b3b4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da3b0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da400`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da3b0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da400`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da3cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da3cb`

## pseudocode

```c
__int64 __fastcall HostCharToAce(LPCCH lpMultiByteStr, UINT CodePage, _QWORD *a3)
{
  LPSTR v4; // rcx
  WCHAR *v7; // rbx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int cchWideChar; // r15d
  SIZE_T v12; // rbp
  WCHAR *v13; // rax
  WCHAR *lpWideCharStr; // r14
  __int64 v15; // rdx
  __int64 v16; // rcx
  int LastError; // eax
  signed int v18; // edi
  int v19; // eax
  int v21; // eax
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF
  int v23; // [rsp+3Ch] [rbp-4Ch]
  LPSTR v24; // [rsp+40h] [rbp-48h] BYREF

  v4 = 0;
  v24 = 0;
  v22 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !lpMultiByteStr || !*lpMultiByteStr )
  {
    v7 = 0;
    HIDWORD(v22) = 127;
    v18 = -2147024809;
LABEL_19:
    if ( v4 )
      CoTaskMemFree(v4);
    goto LABEL_21;
  }
  if ( !a3 )
  {
    HIDWORD(v22) = 128;
    return (unsigned int)-2147024809;
  }
  v23 = 0;
  v7 = 0;
  v8 = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v8;
  if ( v8 )
  {
    v23 = 0;
    v12 = (unsigned int)(2 * v8);
    v13 = (WCHAR *)CoTaskMemAlloc(v12);
    lpWideCharStr = v13;
    if ( v13 )
    {
      memset_0(v13, 0, (unsigned int)v12);
      if ( MultiByteToWideChar(CodePage, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
      {
        v7 = lpWideCharStr;
        v19 = HostWCharToCharEx(lpWideCharStr, 0xFFFFFFFF, 1, &v24, (int *)&v22);
        v18 = v19;
        if ( v19 > 0 )
          v18 = (unsigned __int16)v19 | 0x80070000;
        if ( v18 < 0 )
        {
          v4 = v24;
          HIDWORD(v22) = 137;
        }
        else
        {
          v4 = 0;
          *a3 = v24;
        }
        goto LABEL_19;
      }
      LastError = WxGetLastError(v16, v15);
      v18 = LastError;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      v23 = 209;
      if ( v18 >= 0 )
        v18 = -2147418113;
      CoTaskMemFree(lpWideCharStr);
    }
    else
    {
      v18 = -2147024882;
      v23 = 197;
    }
  }
  else
  {
    v21 = WxGetLastError(v10, v9);
    v18 = v21;
    if ( v21 > 0 )
      v18 = (unsigned __int16)v21 | 0x80070000;
    v23 = 182;
    if ( v18 >= 0 )
      v18 = -2147418113;
  }
  HIDWORD(v22) = 132;
LABEL_21:
  if ( v7 )
    CoTaskMemFree(v7);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800da348  push    rbx
0x1800da34a  push    rbp
0x1800da34b  push    rsi
0x1800da34c  push    rdi
0x1800da34d  push    r12
0x1800da34f  push    r14
0x1800da351  push    r15
0x1800da353  sub     rsp, 50h
0x1800da357  mov     rdi, rcx
0x1800da35a  mov     dword ptr [rsp+88h+var_58+4], 0
0x1800da362  xor     ecx, ecx
0x1800da364  mov     rsi, r8
0x1800da367  mov     [rsp+88h+var_48], rcx
0x1800da36c  mov     r12d, edx
0x1800da36f  mov     dword ptr [rsp+88h+var_58], ecx
0x1800da373  test    r8, r8
0x1800da376  jz      short loc_1800DA37B
0x1800da378  mov     [r8], rcx
0x1800da37b  test    rdi, rdi
0x1800da37e  jz      loc_1800DA4AE
0x1800da384  cmp     [rdi], cl
0x1800da386  jz      loc_1800DA4AE
0x1800da38c  test    rsi, rsi
0x1800da38f  jz      loc_1800DA506
0x1800da395  mov     [rsp+88h+cchWideChar], ecx; cchWideChar
0x1800da399  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800da39d  mov     [rsp+88h+lpWideCharStr], rcx; lpWideCharStr
0x1800da3a2  mov     r8, rdi; lpMultiByteStr
0x1800da3a5  mov     [rsp+88h+var_4C], ecx
0x1800da3a9  xor     edx, edx; dwFlags
0x1800da3ab  mov     ecx, r12d; CodePage
0x1800da3ae  xor     ebx, ebx
0x1800da3b0  call    cs:__imp_MultiByteToWideChar
0x1800da3b6  mov     r15d, eax
0x1800da3b9  test    eax, eax
0x1800da3bb  jz      loc_1800DA4DE
0x1800da3c1  add     eax, eax
0x1800da3c3  mov     [rsp+88h+var_4C], ebx
0x1800da3c7  mov     ecx, eax; cb
0x1800da3c9  mov     ebp, eax
0x1800da3cb  call    cs:__imp_CoTaskMemAlloc
0x1800da3d1  mov     r14, rax
0x1800da3d4  test    rax, rax
0x1800da3d7  jz      loc_1800DA4BF
0x1800da3dd  mov     r8d, ebp; Size
0x1800da3e0  xor     edx, edx; Val
0x1800da3e2  mov     rcx, rax; void *
0x1800da3e5  call    memset_0
0x1800da3ea  mov     [rsp+88h+cchWideChar], r15d; cchWideChar
0x1800da3ef  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800da3f3  mov     r8, rdi; lpMultiByteStr
0x1800da3f6  mov     [rsp+88h+lpWideCharStr], r14; lpWideCharStr
0x1800da3fb  xor     edx, edx; dwFlags
0x1800da3fd  mov     ecx, r12d; CodePage
0x1800da400  call    cs:__imp_MultiByteToWideChar
0x1800da406  mov     ebp, 80070000h
0x1800da40b  test    eax, eax
0x1800da40d  jz      short loc_1800DA414
0x1800da40f  mov     rbx, r14
0x1800da412  jmp     short loc_1800DA447
0x1800da414  call    WxGetLastError
0x1800da419  mov     edi, eax
0x1800da41b  test    eax, eax
0x1800da41d  jle     short loc_1800DA424
0x1800da41f  movzx   edi, ax
0x1800da422  or      edi, ebp
0x1800da424  test    edi, edi
0x1800da426  mov     [rsp+88h+var_4C], 0D1h
0x1800da42e  mov     eax, 8000FFFFh
0x1800da433  mov     rcx, r14; pv
0x1800da436  cmovns  edi, eax
0x1800da439  call    cs:__imp_CoTaskMemFree
0x1800da43f  test    edi, edi
0x1800da441  js      loc_1800DA4D4
0x1800da447  lea     rax, [rsp+88h+var_58]
0x1800da44c  mov     r8d, 1
0x1800da452  lea     r9, [rsp+88h+var_48]
0x1800da457  mov     [rsp+88h+lpWideCharStr], rax; __int64
0x1800da45c  or      edx, 0FFFFFFFFh; cchUnicodeChar
0x1800da45f  mov     rcx, rbx; lpUnicodeCharStr
0x1800da462  call    HostWCharToCharEx
0x1800da467  mov     edi, eax
0x1800da469  test    eax, eax
0x1800da46b  jle     short loc_1800DA472
0x1800da46d  movzx   edi, ax
0x1800da470  or      edi, ebp
0x1800da472  test    edi, edi
0x1800da474  js      loc_1800DA515
0x1800da47a  mov     rax, [rsp+88h+var_48]
0x1800da47f  xor     ecx, ecx; pv
0x1800da481  mov     [rsi], rax
0x1800da484  test    rcx, rcx
0x1800da487  jz      short loc_1800DA48F
0x1800da489  call    cs:__imp_CoTaskMemFree
0x1800da48f  test    rbx, rbx
0x1800da492  jz      short loc_1800DA49D
0x1800da494  mov     rcx, rbx; pv
0x1800da497  call    cs:__imp_CoTaskMemFree
0x1800da49d  mov     eax, edi
0x1800da49f  add     rsp, 50h
0x1800da4a3  pop     r15
0x1800da4a5  pop     r14
0x1800da4a7  pop     r12
0x1800da4a9  pop     rdi
0x1800da4aa  pop     rsi
0x1800da4ab  pop     rbp
0x1800da4ac  pop     rbx
0x1800da4ad  retn
0x1800da4ae  xor     ebx, ebx
0x1800da4b0  mov     dword ptr [rsp+88h+var_58+4], 7Fh
0x1800da4b8  mov     edi, 80070057h
0x1800da4bd  jmp     short loc_1800DA484
0x1800da4bf  mov     [rsp+88h+var_4C], 4Ch ; 'L'
0x1800da4c7  mov     edi, 8007000Eh
0x1800da4cc  mov     [rsp+88h+var_4C], 0C5h
0x1800da4d4  mov     dword ptr [rsp+88h+var_58+4], 84h
0x1800da4dc  jmp     short loc_1800DA48F
0x1800da4de  call    WxGetLastError
0x1800da4e3  mov     edi, eax
0x1800da4e5  test    eax, eax
0x1800da4e7  jle     short loc_1800DA4F2
0x1800da4e9  movzx   edi, ax
0x1800da4ec  or      edi, 80070000h
0x1800da4f2  test    edi, edi
0x1800da4f4  mov     [rsp+88h+var_4C], 0B6h
0x1800da4fc  mov     eax, 8000FFFFh
0x1800da501  cmovns  edi, eax
0x1800da504  jmp     short loc_1800DA4D4
0x1800da506  mov     dword ptr [rsp+88h+var_58+4], 80h
0x1800da50e  mov     edi, 80070057h
0x1800da513  jmp     short loc_1800DA49D
0x1800da515  mov     rcx, [rsp+88h+var_48]
0x1800da51a  mov     dword ptr [rsp+88h+var_58+4], 89h
0x1800da522  jmp     loc_1800DA484
```
