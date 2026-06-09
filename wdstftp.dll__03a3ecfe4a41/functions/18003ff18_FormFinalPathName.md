# FormFinalPathName

- ea: `0x18003ff18`
- end: `0x180040124`
- name: `FormFinalPathName`
- size: `524`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x18003eba8`

## callees

- `0x18003fdec`
- `0x18003ff18`
- `0x1800607b0`
- `0x180060cd6`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800400b2`
- `KERNEL32!GetLastError` at `0x1800400b2`
- `KERNEL32!CloseHandle` at `0x1800400c9`
- `KERNEL32!CloseHandle` at `0x1800400c9`
- `KERNEL32!CreateFileW` at `0x18004008b`
- `KERNEL32!CreateFileW` at `0x18004008b`
- `KERNEL32!SetLastError` at `0x1800400d7`
- `KERNEL32!SetLastError` at `0x1800400ed`
- `KERNEL32!SetLastError` at `0x1800400d7`
- `KERNEL32!SetLastError` at `0x1800400ed`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathName(wchar_t *String1)
{
  DWORD LastError; // ebx
  WCHAR *v3; // r14
  int v4; // esi
  wchar_t *v5; // r15
  wchar_t v6; // cx
  char *FileW; // rax
  char *v8; // rdi
  wchar_t String2[8]; // [rsp+48h] [rbp-19h] BYREF
  wchar_t v11[16]; // [rsp+58h] [rbp-9h] BYREF
  wchar_t v12[8]; // [rsp+78h] [rbp+17h] BYREF
  wchar_t v13[12]; // [rsp+88h] [rbp+27h] BYREF

  LastError = 0;
  v3 = 0;
  wcscpy(String2, L"\\\\?\\");
  v4 = 0;
  wcscpy(v11, L"\\\\?\\GLOBALROOT");
  wcscpy(v13, L"\\\\?\\Volume{");
  wcscpy(v12, L"\\Device");
  if ( String1 && *String1 )
  {
    v5 = String1;
    if ( wcsnicmp_0(String1, String2, 4u)
      || (v6 = v5[4], (unsigned __int16)(v6 - 97) > 0x19u) && (unsigned __int16)(v6 - 65) > 0x19u
      || String1[5] != 58 )
    {
      if ( (unsigned __int16)(*String1 - 97) > 0x19u && (unsigned __int16)(*String1 - 65) > 0x19u || String1[1] != 58 )
      {
        if ( !wcsnicmp_0(String1, v11, 0xEu) )
          v5 = String1 + 14;
        if ( wcsnicmp_0(v5, v13, 0xBu) )
        {
          if ( !wcsnicmp_0(v5, v12, 7u) )
            v4 = 2;
        }
        else
        {
          v4 = 1;
        }
      }
    }
    FileW = (char *)CreateFileW(String1, 0, 7u, 0, 3u, 0x2200000u, 0);
    v8 = FileW;
    if ( FileW == (char *)-1LL || (v3 = FormFinalPathNameByHandle(FileW, v4)) == 0 )
      LastError = GetLastError();
    if ( v8 != (char *)-1LL )
      CloseHandle(v8);
    SetLastError(LastError);
    return v3;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18003ff18  mov     rax, rsp
0x18003ff1b  mov     [rax+10h], rbx
0x18003ff1f  mov     [rax+18h], rsi
0x18003ff23  mov     [rax+20h], rdi
0x18003ff27  push    rbp
0x18003ff28  push    r14
0x18003ff2a  push    r15
0x18003ff2c  lea     rbp, [rax-5Fh]
0x18003ff30  sub     rsp, 0A0h
0x18003ff37  mov     rax, cs:__security_cookie
0x18003ff3e  xor     rax, rsp
0x18003ff41  mov     [rbp+57h+var_18], rax
0x18003ff45  movsd   xmm0, qword ptr cs:asc_180068CC8; "\\\\?\\"
0x18003ff4d  xor     ebx, ebx
0x18003ff4f  movzx   eax, word ptr cs:asc_180068CC8+8; ""
0x18003ff56  mov     rdi, rcx
0x18003ff59  movsd   xmm1, qword ptr cs:aGlobalroot_0+10h; "ALROOT"
0x18003ff61  mov     r14d, ebx
0x18003ff64  movsd   qword ptr [rbp+57h+String2], xmm0
0x18003ff69  mov     esi, ebx
0x18003ff6b  mov     [rbp+57h+var_68], ax
0x18003ff6f  mov     eax, dword ptr cs:aGlobalroot_0+18h; "OT"
0x18003ff75  movsd   [rbp+57h+var_50], xmm1
0x18003ff7a  movsd   xmm1, qword ptr cs:aVolume+10h; "me{"
0x18003ff82  mov     [rbp+57h+var_48], eax
0x18003ff85  movzx   eax, word ptr cs:aGlobalroot_0+1Ch; ""
0x18003ff8c  mov     [rbp+57h+var_44], ax
0x18003ff90  movsd   [rbp+57h+var_20], xmm1
0x18003ff95  movups  xmm0, xmmword ptr cs:aGlobalroot_0; "\\\\?\\GLOBALROOT"
0x18003ff9c  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18003ffa0  movups  xmm0, xmmword ptr cs:aVolume; "\\\\?\\Volume{"
0x18003ffa7  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x18003ffab  movups  xmm0, xmmword ptr cs:aDevice; "\\Device"
0x18003ffb2  movdqu  xmmword ptr [rbp+57h+var_40], xmm0
0x18003ffb7  test    rcx, rcx
0x18003ffba  jz      loc_1800400E8
0x18003ffc0  cmp     bx, [rcx]
0x18003ffc3  jz      loc_1800400E8
0x18003ffc9  lea     r8d, [rbx+4]; MaxCount
0x18003ffcd  mov     r15, rcx
0x18003ffd0  lea     rdx, [rbp+57h+String2]; String2
0x18003ffd4  call    _wcsnicmp_0
0x18003ffd9  mov     dx, 19h
0x18003ffdd  test    eax, eax
0x18003ffdf  jnz     short loc_18003FFFE
0x18003ffe1  movzx   ecx, word ptr [r15+8]
0x18003ffe6  lea     eax, [rcx-61h]
0x18003ffe9  cmp     ax, dx
0x18003ffec  jbe     short loc_18003FFF7
0x18003ffee  sub     cx, 41h ; 'A'
0x18003fff2  cmp     cx, dx
0x18003fff5  ja      short loc_18003FFFE
0x18003fff7  cmp     word ptr [rdi+0Ah], 3Ah ; ':'
0x18003fffc  jz      short loc_18004006A
0x18003fffe  movzx   ecx, word ptr [rdi]
0x180040001  lea     eax, [rcx-61h]
0x180040004  cmp     ax, dx
0x180040007  jbe     short loc_180040012
0x180040009  sub     cx, 41h ; 'A'
0x18004000d  cmp     cx, dx
0x180040010  ja      short loc_180040019
0x180040012  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180040017  jz      short loc_18004006A
0x180040019  mov     r8d, 0Eh; MaxCount
0x18004001f  lea     rdx, [rbp+57h+var_60]; String2
0x180040023  mov     rcx, rdi; String1
0x180040026  call    _wcsnicmp_0
0x18004002b  test    eax, eax
0x18004002d  jnz     short loc_180040033
0x18004002f  lea     r15, [rdi+1Ch]
0x180040033  mov     r8d, 0Bh; MaxCount
0x180040039  lea     rdx, [rbp+57h+var_30]; String2
0x18004003d  mov     rcx, r15; String1
0x180040040  call    _wcsnicmp_0
0x180040045  test    eax, eax
0x180040047  jnz     short loc_18004004E
0x180040049  lea     esi, [rax+1]
0x18004004c  jmp     short loc_18004006A
0x18004004e  mov     r8d, 7; MaxCount
0x180040054  lea     rdx, [rbp+57h+var_40]; String2
0x180040058  mov     rcx, r15; String1
0x18004005b  call    _wcsnicmp_0
0x180040060  test    eax, eax
0x180040062  mov     ecx, 2
0x180040067  cmovz   esi, ecx
0x18004006a  xor     r9d, r9d; lpSecurityAttributes
0x18004006d  mov     [rsp+0B0h+hTemplateFile], rbx; hTemplateFile
0x180040072  mov     [rsp+0B0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18004007a  xor     edx, edx; dwDesiredAccess
0x18004007c  mov     rcx, rdi; lpFileName
0x18004007f  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180040087  lea     r8d, [r9+7]; dwShareMode
0x18004008b  call    cs:__imp_CreateFileW
0x180040092  nop     dword ptr [rax+rax+00h]
0x180040097  mov     rdi, rax
0x18004009a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004009e  jz      short loc_1800400B2
0x1800400a0  mov     edx, esi
0x1800400a2  mov     rcx, rax; hFile
0x1800400a5  call    FormFinalPathNameByHandle
0x1800400aa  mov     r14, rax
0x1800400ad  test    rax, rax
0x1800400b0  jnz     short loc_1800400C0
0x1800400b2  call    cs:__imp_GetLastError
0x1800400b9  nop     dword ptr [rax+rax+00h]
0x1800400be  mov     ebx, eax
0x1800400c0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800400c4  jz      short loc_1800400D5
0x1800400c6  mov     rcx, rdi; hObject
0x1800400c9  call    cs:__imp_CloseHandle
0x1800400d0  nop     dword ptr [rax+rax+00h]
0x1800400d5  mov     ecx, ebx; dwErrCode
0x1800400d7  call    cs:__imp_SetLastError
0x1800400de  nop     dword ptr [rax+rax+00h]
0x1800400e3  mov     rax, r14
0x1800400e6  jmp     short loc_1800400FB
0x1800400e8  mov     ecx, 57h ; 'W'; dwErrCode
0x1800400ed  call    cs:__imp_SetLastError
0x1800400f4  nop     dword ptr [rax+rax+00h]
0x1800400f9  xor     eax, eax
0x1800400fb  mov     rcx, [rbp+57h+var_18]
0x1800400ff  xor     rcx, rsp; StackCookie
0x180040102  call    __security_check_cookie
0x180040107  lea     r11, [rsp+0B0h+var_10]
0x18004010f  mov     rbx, [r11+28h]
0x180040113  mov     rsi, [r11+30h]
0x180040117  mov     rdi, [r11+38h]
0x18004011b  mov     rsp, r11
0x18004011e  pop     r15
0x180040120  pop     r14
0x180040122  pop     rbp
0x180040123  retn
```
