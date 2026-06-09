# ValidateRedirectedHandle

- ea: `0x180040a18`
- end: `0x180040cac`
- name: `ValidateRedirectedHandle`
- size: `660`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *String2)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18003d5cc`
- `0x18003e7c0`

## callees

- `0x180040a18`
- `0x1800607b0`
- `0x180060cd6`
- `0x180060ce2`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x180040b88`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180040c02`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180040b88`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180040c02`
- `KERNEL32!HeapFree` at `0x180040c41`
- `KERNEL32!HeapFree` at `0x180040c74`
- `KERNEL32!HeapFree` at `0x180040c41`
- `KERNEL32!HeapFree` at `0x180040c74`
- `KERNEL32!HeapAlloc` at `0x180040bd8`
- `KERNEL32!HeapAlloc` at `0x180040bd8`
- `KERNEL32!GetLastError` at `0x180040b9b`
- `KERNEL32!GetLastError` at `0x180040b9b`
- `KERNEL32!GetProcessHeap` at `0x180040bc1`
- `KERNEL32!GetProcessHeap` at `0x180040c2d`
- `KERNEL32!GetProcessHeap` at `0x180040c60`
- `KERNEL32!GetProcessHeap` at `0x180040bc1`
- `KERNEL32!GetProcessHeap` at `0x180040c2d`
- `KERNEL32!GetProcessHeap` at `0x180040c60`

## pseudocode

```c
__int64 __fastcall ValidateRedirectedHandle(char *hFile, wchar_t *String2, _DWORD *a3, WCHAR **a4)
{
  wchar_t *v6; // rdi
  DWORD v8; // esi
  wchar_t v9; // cx
  DWORD FinalPathNameByHandleW; // eax
  __int64 v11; // r14
  signed int LastError; // ecx
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  WCHAR *v15; // rax
  WCHAR *v16; // rbx
  DWORD v17; // eax
  HANDLE v18; // rax
  HANDLE v19; // rax
  wchar_t String2a[8]; // [rsp+20h] [rbp-49h] BYREF
  wchar_t v21[16]; // [rsp+30h] [rbp-39h] BYREF
  wchar_t v22[8]; // [rsp+50h] [rbp-19h] BYREF
  wchar_t v23[12]; // [rsp+60h] [rbp-9h] BYREF

  v6 = String2;
  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL || !String2 || !a3 )
    return 2147942487LL;
  v8 = 0;
  wcscpy(String2a, L"\\\\?\\");
  if ( wcsnicmp_0(String2, String2a, 4u)
    || (v9 = v6[4], (unsigned __int16)(v9 - 97) > 0x19u) && (unsigned __int16)(v9 - 65) > 0x19u
    || v6[5] != 58 )
  {
    if ( (unsigned __int16)(*v6 - 97) > 0x19u && (unsigned __int16)(*v6 - 65) > 0x19u || v6[1] != 58 )
    {
      wcscpy(v21, L"\\\\?\\GLOBALROOT");
      wcscpy(v23, L"\\\\?\\Volume{");
      wcscpy(v22, L"\\Device");
      if ( !wcsnicmp_0(v6, v21, 0xEu) )
        v6 += 14;
      if ( wcsnicmp_0(v6, v23, 0xBu) )
      {
        if ( !wcsnicmp_0(v6, v22, 7u) )
          v8 = 2;
      }
      else
      {
        v8 = 1;
      }
    }
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, v8);
  v11 = FinalPathNameByHandleW;
  if ( FinalPathNameByHandleW )
  {
    ProcessHeap = GetProcessHeap();
    v15 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * v11);
    v16 = v15;
    if ( !v15 )
      return 2147942408LL;
    v17 = GetFinalPathNameByHandleW(hFile, v15, v11, v8);
    if ( !v17 || v17 >= (unsigned int)v11 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v16);
      return 2147942522LL;
    }
    if ( wcsicmp_0(v16, v6) )
    {
      *a3 = 0;
      if ( a4 )
      {
        *a4 = v16;
        return 0;
      }
    }
    else
    {
      *a3 = 1;
    }
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v16);
    return 0;
  }
  LastError = GetLastError();
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x180040a18  push    rbp
0x180040a1a  push    rbx
0x180040a1b  push    rsi
0x180040a1c  push    rdi
0x180040a1d  push    r12
0x180040a1f  push    r13
0x180040a21  push    r14
0x180040a23  push    r15
0x180040a25  lea     rbp, [rsp-1Fh]
0x180040a2a  sub     rsp, 88h
0x180040a31  mov     rax, cs:__security_cookie
0x180040a38  xor     rax, rsp
0x180040a3b  mov     [rbp+57h+var_48], rax
0x180040a3f  lea     rax, [rcx-1]
0x180040a43  mov     r12, r9
0x180040a46  mov     r15, r8
0x180040a49  mov     rdi, rdx
0x180040a4c  mov     r13, rcx
0x180040a4f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040a53  ja      loc_180040C87
0x180040a59  test    rdx, rdx
0x180040a5c  jz      loc_180040C87
0x180040a62  test    r8, r8
0x180040a65  jz      loc_180040C87
0x180040a6b  movsd   xmm0, qword ptr cs:asc_180068CC8; "\\\\?\\"
0x180040a73  lea     rdx, [rbp+57h+String2]; String2
0x180040a77  movzx   eax, word ptr cs:asc_180068CC8+8; ""
0x180040a7e  xor     esi, esi
0x180040a80  mov     rcx, rdi; String1
0x180040a83  movsd   qword ptr [rbp+57h+String2], xmm0
0x180040a88  mov     [rbp+57h+var_98], ax
0x180040a8c  lea     r8d, [rsi+4]; MaxCount
0x180040a90  call    _wcsnicmp_0
0x180040a95  mov     dx, 19h
0x180040a99  test    eax, eax
0x180040a9b  jnz     short loc_180040ABD
0x180040a9d  movzx   ecx, word ptr [rdi+8]
0x180040aa1  lea     eax, [rcx-61h]
0x180040aa4  cmp     ax, dx
0x180040aa7  jbe     short loc_180040AB2
0x180040aa9  sub     cx, 41h ; 'A'
0x180040aad  cmp     cx, dx
0x180040ab0  ja      short loc_180040ABD
0x180040ab2  cmp     word ptr [rdi+0Ah], 3Ah ; ':'
0x180040ab7  jz      loc_180040B7D
0x180040abd  movzx   ecx, word ptr [rdi]
0x180040ac0  lea     eax, [rcx-61h]
0x180040ac3  cmp     ax, dx
0x180040ac6  jbe     short loc_180040AD1
0x180040ac8  sub     cx, 41h ; 'A'
0x180040acc  cmp     cx, dx
0x180040acf  ja      short loc_180040ADC
0x180040ad1  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180040ad6  jz      loc_180040B7D
0x180040adc  movups  xmm0, xmmword ptr cs:aGlobalroot_0; "\\\\?\\GLOBALROOT"
0x180040ae3  lea     rdx, [rbp+57h+var_90]; String2
0x180040ae7  mov     eax, dword ptr cs:aGlobalroot_0+18h; "OT"
0x180040aed  movsd   xmm1, qword ptr cs:aGlobalroot_0+10h; "ALROOT"
0x180040af5  mov     r8d, 0Eh; MaxCount
0x180040afb  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180040aff  mov     [rbp+57h+var_78], eax
0x180040b02  mov     rcx, rdi; String1
0x180040b05  movups  xmm0, xmmword ptr cs:aVolume; "\\\\?\\Volume{"
0x180040b0c  movzx   eax, word ptr cs:aGlobalroot_0+1Ch; ""
0x180040b13  movsd   [rbp+57h+var_80], xmm1
0x180040b18  movsd   xmm1, qword ptr cs:aVolume+10h; "me{"
0x180040b20  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180040b24  mov     [rbp+57h+var_74], ax
0x180040b28  movups  xmm0, xmmword ptr cs:aDevice; "\\Device"
0x180040b2f  movsd   [rbp+57h+var_50], xmm1
0x180040b34  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180040b39  call    _wcsnicmp_0
0x180040b3e  test    eax, eax
0x180040b40  jnz     short loc_180040B46
0x180040b42  add     rdi, 1Ch
0x180040b46  mov     r8d, 0Bh; MaxCount
0x180040b4c  lea     rdx, [rbp+57h+var_60]; String2
0x180040b50  mov     rcx, rdi; String1
0x180040b53  call    _wcsnicmp_0
0x180040b58  test    eax, eax
0x180040b5a  jnz     short loc_180040B61
0x180040b5c  lea     esi, [rax+1]
0x180040b5f  jmp     short loc_180040B7D
0x180040b61  mov     r8d, 7; MaxCount
0x180040b67  lea     rdx, [rbp+57h+var_70]; String2
0x180040b6b  mov     rcx, rdi; String1
0x180040b6e  call    _wcsnicmp_0
0x180040b73  test    eax, eax
0x180040b75  mov     ecx, 2
0x180040b7a  cmovz   esi, ecx
0x180040b7d  mov     r9d, esi; dwFlags
0x180040b80  xor     r8d, r8d; cchFilePath
0x180040b83  xor     edx, edx; lpszFilePath
0x180040b85  mov     rcx, r13; hFile
0x180040b88  call    cs:__imp_GetFinalPathNameByHandleW
0x180040b8f  nop     dword ptr [rax+rax+00h]
0x180040b94  mov     r14d, eax
0x180040b97  test    eax, eax
0x180040b99  jnz     short loc_180040BBB
0x180040b9b  call    cs:__imp_GetLastError
0x180040ba2  nop     dword ptr [rax+rax+00h]
0x180040ba7  mov     ecx, eax
0x180040ba9  movzx   eax, ax
0x180040bac  or      eax, 80070000h
0x180040bb1  test    ecx, ecx
0x180040bb3  cmovle  eax, ecx
0x180040bb6  jmp     loc_180040C8C
0x180040bbb  mov     rbx, r14
0x180040bbe  add     rbx, rbx
0x180040bc1  call    cs:__imp_GetProcessHeap
0x180040bc8  nop     dword ptr [rax+rax+00h]
0x180040bcd  mov     r8, rbx; dwBytes
0x180040bd0  mov     edx, 8; dwFlags
0x180040bd5  mov     rcx, rax; hHeap
0x180040bd8  call    cs:__imp_HeapAlloc
0x180040bdf  nop     dword ptr [rax+rax+00h]
0x180040be4  mov     rbx, rax
0x180040be7  test    rax, rax
0x180040bea  jnz     short loc_180040BF6
0x180040bec  mov     eax, 80070008h
0x180040bf1  jmp     loc_180040C8C
0x180040bf6  mov     r9d, esi; dwFlags
0x180040bf9  mov     r8d, r14d; cchFilePath
0x180040bfc  mov     rdx, rbx; lpszFilePath
0x180040bff  mov     rcx, r13; hFile
0x180040c02  call    cs:__imp_GetFinalPathNameByHandleW
0x180040c09  nop     dword ptr [rax+rax+00h]
0x180040c0e  test    eax, eax
0x180040c10  jz      short loc_180040C60
0x180040c12  cmp     eax, r14d
0x180040c15  jnb     short loc_180040C60
0x180040c17  mov     rdx, rdi; String2
0x180040c1a  mov     rcx, rbx; String1
0x180040c1d  call    _wcsicmp_0
0x180040c22  test    eax, eax
0x180040c24  jnz     short loc_180040C51
0x180040c26  mov     dword ptr [r15], 1
0x180040c2d  call    cs:__imp_GetProcessHeap
0x180040c34  nop     dword ptr [rax+rax+00h]
0x180040c39  mov     r8, rbx; lpMem
0x180040c3c  xor     edx, edx; dwFlags
0x180040c3e  mov     rcx, rax; hHeap
0x180040c41  call    cs:__imp_HeapFree
0x180040c48  nop     dword ptr [rax+rax+00h]
0x180040c4d  xor     eax, eax
0x180040c4f  jmp     short loc_180040C8C
0x180040c51  and     dword ptr [r15], 0
0x180040c55  test    r12, r12
0x180040c58  jz      short loc_180040C2D
0x180040c5a  mov     [r12], rbx
0x180040c5e  jmp     short loc_180040C4D
0x180040c60  call    cs:__imp_GetProcessHeap
0x180040c67  nop     dword ptr [rax+rax+00h]
0x180040c6c  mov     r8, rbx; lpMem
0x180040c6f  xor     edx, edx; dwFlags
0x180040c71  mov     rcx, rax; hHeap
0x180040c74  call    cs:__imp_HeapFree
0x180040c7b  nop     dword ptr [rax+rax+00h]
0x180040c80  mov     eax, 8007007Ah
0x180040c85  jmp     short loc_180040C8C
0x180040c87  mov     eax, 80070057h
0x180040c8c  mov     rcx, [rbp+57h+var_48]
0x180040c90  xor     rcx, rsp; StackCookie
0x180040c93  call    __security_check_cookie
0x180040c98  add     rsp, 88h
0x180040c9f  pop     r15
0x180040ca1  pop     r14
0x180040ca3  pop     r13
0x180040ca5  pop     r12
0x180040ca7  pop     rdi
0x180040ca8  pop     rsi
0x180040ca9  pop     rbx
0x180040caa  pop     rbp
0x180040cab  retn
```
