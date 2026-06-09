# CExtraClocksDlg::_FillTimeZoneComboBoxes(tagTZNODE const *)

- ea: `0x18000fc90`
- end: `0x18000fee4`
- name: `?_FillTimeZoneComboBoxes@CExtraClocksDlg@@AEAAXPEBUtagTZNODE@@@Z`
- size: `596`
- prototype: `void __fastcall(CExtraClocksDlg *__hidden this, const struct tagTZNODE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000feec`

## callees

- `0x1800089c8`
- `0x18000fc90`
- `0x18001cbc4`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fd47`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fe40`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fd47`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fe40`
- `USER32!SendMessageW` at `0x18000fce6`
- `USER32!SendMessageW` at `0x18000fd15`
- `USER32!SendMessageW` at `0x18000fd62`
- `USER32!SendMessageW` at `0x18000fd7f`
- `USER32!SendMessageW` at `0x18000fdf4`
- `USER32!SendMessageW` at `0x18000fe16`
- `USER32!SendMessageW` at `0x18000fe73`
- `USER32!SendMessageW` at `0x18000fe87`
- `USER32!SendMessageW` at `0x18000fce6`
- `USER32!SendMessageW` at `0x18000fd15`
- `USER32!SendMessageW` at `0x18000fd62`
- `USER32!SendMessageW` at `0x18000fd7f`
- `USER32!SendMessageW` at `0x18000fdf4`
- `USER32!SendMessageW` at `0x18000fe16`
- `USER32!SendMessageW` at `0x18000fe73`
- `USER32!SendMessageW` at `0x18000fe87`

## pseudocode

```c
void __fastcall CExtraClocksDlg::_FillTimeZoneComboBoxes(HWND *this, const struct tagTZNODE *a2)
{
  const struct tagTZNODE *i; // rbx
  __int64 v4; // rbp
  __int64 v5; // rdi
  int v6; // eax
  int v7; // r15d
  __int64 j; // rdi
  int v9; // ebx
  unsigned int v10; // r8d
  __int64 v11; // r14
  int v12; // r15d
  unsigned int v13; // ebp
  const WCHAR *v14; // rax
  const unsigned __int16 *v15; // rax
  int v16[2]; // [rsp+30h] [rbp-158h]
  WCHAR String2[128]; // [rsp+40h] [rbp-148h] BYREF

  *(_QWORD *)v16 = -1;
  for ( i = a2; i; i = *(const struct tagTZNODE **)i )
  {
    v4 = 0;
    v5 = 0;
    do
    {
      v6 = SendMessageW(this[v5 + 3], 0x143u, 0, (LPARAM)i + 8);
      v7 = v6;
      if ( (unsigned int)(v6 + 2) > 1 )
      {
        if ( (unsigned int)SendMessageW(this[v5 + 3], 0x151u, v6, (LPARAM)i + 264) == -1 )
        {
          SendMessageW(this[v5 + 3], 0x144u, v7, 0);
        }
        else if ( v16[v4] == -1 && CompareStringW(0x7Fu, 0, (PCNZWCH)i + 132, -1, (PCNZWCH)&this[v5 + 9], -1) == 2 )
        {
          SendMessageW(this[v5 + 3], 0x14Eu, v7, 0);
          v16[v4] = v7;
        }
      }
      ++v4;
      v5 += 38;
    }
    while ( v4 != 2 );
  }
  for ( j = 0; j != 2; ++j )
  {
    v9 = v16[j];
    if ( v9 == -1 )
    {
      memset_0(String2, 0, sizeof(String2));
      CDateTimeOm::get_UITimeZone(g_pom, String2, v10);
      v11 = 38 * j;
      v12 = SendMessageW(this[38 * j + 3], 0x146u, 0, 0);
      if ( v12 > 0 )
      {
        v13 = 0;
        while ( v9 == -1 )
        {
          v14 = (const WCHAR *)SendMessageW(this[v11 + 3], 0x150u, v13, 0);
          if ( v14 != (const WCHAR *)-1LL && v14 && CompareStringW(0x7Fu, 0, v14, -1, String2, -1) == 2 )
          {
            v9 = v13;
            v16[j] = v13;
          }
          if ( (int)++v13 >= v12 )
          {
            if ( v9 == -1 )
            {
              v9 = 0;
              v16[j] = 0;
            }
            break;
          }
        }
        SendMessageW(this[v11 + 3], 0x14Eu, v9, 0);
      }
      v15 = (const unsigned __int16 *)SendMessageW(this[v11 + 3], 0x150u, v9, 0);
      if ( v15 != (const unsigned __int16 *)-1LL )
      {
        if ( v15 )
          StringCchCopyW((unsigned __int16 *)&this[v11 + 9], 0x80u, v15);
      }
    }
  }
}

```

## disassembly

```asm
0x18000fc90  mov     [rsp+arg_10], rbx
0x18000fc95  push    rbp
0x18000fc96  push    rsi
0x18000fc97  push    rdi
0x18000fc98  push    r12
0x18000fc9a  push    r13
0x18000fc9c  push    r14
0x18000fc9e  push    r15
0x18000fca0  sub     rsp, 150h
0x18000fca7  mov     rax, cs:__security_cookie
0x18000fcae  xor     rax, rsp
0x18000fcb1  mov     [rsp+188h+var_48], rax
0x18000fcb9  mov     qword ptr [rsp+188h+var_158], 0FFFFFFFFFFFFFFFFh
0x18000fcc2  mov     rbx, rdx
0x18000fcc5  mov     rsi, rcx
0x18000fcc8  test    rdx, rdx
0x18000fccb  jz      loc_18000FDA5
0x18000fcd1  xor     ebp, ebp
0x18000fcd3  xor     edi, edi
0x18000fcd5  mov     rcx, [rdi+rsi+18h]; hWnd
0x18000fcda  lea     r9, [rbx+8]; lParam
0x18000fcde  xor     r8d, r8d; wParam
0x18000fce1  mov     edx, 143h; Msg
0x18000fce6  call    cs:__imp_SendMessageW
0x18000fcec  mov     r15, rax
0x18000fcef  lea     ecx, [rax+2]
0x18000fcf2  cmp     ecx, 1
0x18000fcf5  jbe     loc_18000FD85
0x18000fcfb  mov     rcx, [rdi+rsi+18h]; hWnd
0x18000fd00  lea     r12, [rbx+108h]
0x18000fd07  movsxd  r14, r15d
0x18000fd0a  mov     r9, r12; lParam
0x18000fd0d  mov     r8, r14; wParam
0x18000fd10  mov     edx, 151h; Msg
0x18000fd15  call    cs:__imp_SendMessageW
0x18000fd1b  cmp     eax, 0FFFFFFFFh
0x18000fd1e  jz      short loc_18000FD6F
0x18000fd20  cmp     [rsp+rbp*4+188h+var_158], 0FFFFFFFFh
0x18000fd25  jnz     short loc_18000FD85
0x18000fd27  xor     edx, edx; dwCmpFlags
0x18000fd29  mov     [rsp+188h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fd31  lea     rax, [rsi+48h]
0x18000fd35  or      r9d, 0FFFFFFFFh; cchCount1
0x18000fd39  add     rax, rdi
0x18000fd3c  mov     r8, r12; lpString1
0x18000fd3f  mov     [rsp+188h+lpString2], rax; lpString2
0x18000fd44  lea     ecx, [rdx+7Fh]; Locale
0x18000fd47  call    cs:__imp_CompareStringW
0x18000fd4d  cmp     eax, 2
0x18000fd50  jnz     short loc_18000FD85
0x18000fd52  mov     rcx, [rdi+rsi+18h]; hWnd
0x18000fd57  xor     r9d, r9d; lParam
0x18000fd5a  mov     r8, r14; wParam
0x18000fd5d  mov     edx, 14Eh; Msg
0x18000fd62  call    cs:__imp_SendMessageW
0x18000fd68  mov     [rsp+rbp*4+188h+var_158], r15d
0x18000fd6d  jmp     short loc_18000FD85
0x18000fd6f  mov     rcx, [rdi+rsi+18h]; hWnd
0x18000fd74  xor     r9d, r9d; lParam
0x18000fd77  mov     r8, r14; wParam
0x18000fd7a  mov     edx, 144h; Msg
0x18000fd7f  call    cs:__imp_SendMessageW
0x18000fd85  inc     rbp
0x18000fd88  add     rdi, 130h
0x18000fd8f  cmp     rbp, 2
0x18000fd93  jnz     loc_18000FCD5
0x18000fd99  mov     rbx, [rbx]
0x18000fd9c  test    rbx, rbx
0x18000fd9f  jnz     loc_18000FCD1
0x18000fda5  xor     edi, edi
0x18000fda7  mov     r12d, 150h
0x18000fdad  mov     ebx, [rsp+rdi*4+188h+var_158]
0x18000fdb1  cmp     ebx, 0FFFFFFFFh
0x18000fdb4  jnz     loc_18000FEAC
0x18000fdba  xor     edx, edx; Val
0x18000fdbc  lea     rcx, [rsp+188h+String2]; void *
0x18000fdc1  mov     r8d, 100h; Size
0x18000fdc7  call    memset_0
0x18000fdcc  mov     rcx, cs:?g_pom@@3PEAVCDateTimeOm@@EA; this
0x18000fdd3  lea     rdx, [rsp+188h+String2]; unsigned __int16 *
0x18000fdd8  call    ?get_UITimeZone@CDateTimeOm@@QEAAHPEAGK@Z; CDateTimeOm::get_UITimeZone(ushort *,ulong)
0x18000fddd  imul    r14, rdi, 130h
0x18000fde4  xor     r9d, r9d; lParam
0x18000fde7  xor     r8d, r8d; wParam
0x18000fdea  mov     edx, 146h; Msg
0x18000fdef  mov     rcx, [r14+rsi+18h]; hWnd
0x18000fdf4  call    cs:__imp_SendMessageW
0x18000fdfa  mov     r15, rax
0x18000fdfd  test    eax, eax
0x18000fdff  jle     short loc_18000FE79
0x18000fe01  xor     ebp, ebp
0x18000fe03  cmp     ebx, 0FFFFFFFFh
0x18000fe06  jnz     short loc_18000FE63
0x18000fe08  mov     rcx, [r14+rsi+18h]; hWnd
0x18000fe0d  xor     r9d, r9d; lParam
0x18000fe10  mov     r8d, ebp; wParam
0x18000fe13  mov     edx, r12d; Msg
0x18000fe16  call    cs:__imp_SendMessageW
0x18000fe1c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fe20  jz      short loc_18000FE51
0x18000fe22  test    rax, rax
0x18000fe25  jz      short loc_18000FE51
0x18000fe27  lea     rcx, [rsp+188h+String2]
0x18000fe2c  mov     [rsp+188h+cchCount2], ebx; cchCount2
0x18000fe30  xor     edx, edx; dwCmpFlags
0x18000fe32  mov     [rsp+188h+lpString2], rcx; lpString2
0x18000fe37  or      r9d, ebx; cchCount1
0x18000fe3a  mov     r8, rax; lpString1
0x18000fe3d  lea     ecx, [rdx+7Fh]; Locale
0x18000fe40  call    cs:__imp_CompareStringW
0x18000fe46  cmp     eax, 2
0x18000fe49  jnz     short loc_18000FE51
0x18000fe4b  mov     ebx, ebp
0x18000fe4d  mov     [rsp+rdi*4+188h+var_158], ebp
0x18000fe51  inc     ebp
0x18000fe53  cmp     ebp, r15d
0x18000fe56  jl      short loc_18000FE03
0x18000fe58  cmp     ebx, 0FFFFFFFFh
0x18000fe5b  jnz     short loc_18000FE63
0x18000fe5d  xor     ebx, ebx
0x18000fe5f  mov     [rsp+rdi*4+188h+var_158], ebx
0x18000fe63  mov     rcx, [r14+rsi+18h]; hWnd
0x18000fe68  xor     r9d, r9d; lParam
0x18000fe6b  movsxd  r8, ebx; wParam
0x18000fe6e  mov     edx, 14Eh; Msg
0x18000fe73  call    cs:__imp_SendMessageW
0x18000fe79  mov     rcx, [r14+rsi+18h]; hWnd
0x18000fe7e  xor     r9d, r9d; lParam
0x18000fe81  movsxd  r8, ebx; wParam
0x18000fe84  mov     edx, r12d; Msg
0x18000fe87  call    cs:__imp_SendMessageW
0x18000fe8d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fe91  jz      short loc_18000FEAC
0x18000fe93  test    rax, rax
0x18000fe96  jz      short loc_18000FEAC
0x18000fe98  lea     rcx, [rsi+48h]
0x18000fe9c  mov     r8, rax; unsigned __int16 *
0x18000fe9f  add     rcx, r14; unsigned __int16 *
0x18000fea2  mov     edx, 80h; unsigned __int64
0x18000fea7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000feac  inc     rdi
0x18000feaf  cmp     rdi, 2
0x18000feb3  jnz     loc_18000FDAD
0x18000feb9  mov     rcx, [rsp+188h+var_48]
0x18000fec1  xor     rcx, rsp; StackCookie
0x18000fec4  call    __security_check_cookie
0x18000fec9  mov     rbx, [rsp+188h+arg_10]
0x18000fed1  add     rsp, 150h
0x18000fed8  pop     r15
0x18000feda  pop     r14
0x18000fedc  pop     r13
0x18000fede  pop     r12
0x18000fee0  pop     rdi
0x18000fee1  pop     rsi
0x18000fee2  pop     rbp
0x18000fee3  retn
```
