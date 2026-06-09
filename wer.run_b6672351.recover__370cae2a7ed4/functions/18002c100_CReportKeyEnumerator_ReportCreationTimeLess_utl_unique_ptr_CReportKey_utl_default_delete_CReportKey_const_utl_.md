# CReportKeyEnumerator::ReportCreationTimeLess(utl::unique_ptr<CReportKey,utl::default_delete<CReportKey>> const &,utl::unique_ptr<CReportKey,utl::default_delete<CReportKey>> const &)

- ea: `0x18002c100`
- end: `0x18002c303`
- name: `?ReportCreationTimeLess@CReportKeyEnumerator@@CA_NAEBV?$unique_ptr@VCReportKey@@U?$default_delete@VCReportKey@@@utl@@@utl@@0@Z`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180020680`
- `0x18002c100`
- `0x180053300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c287`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002c2dc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002c2dc`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002c1b7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002c277`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002c1b7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002c277`

## pseudocode

```c
char __fastcall CReportKeyEnumerator::ReportCreationTimeLess(__int64 *a1, __int64 a2)
{
  __int64 v2; // rax
  wchar_t *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  signed int LastError; // eax
  int v8; // eax
  FILETIME FileTime2; // [rsp+20h] [rbp-40h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-38h] BYREF
  SYSTEMTIME SystemTime; // [rsp+30h] [rbp-30h] BYREF
  SYSTEMTIME v13; // [rsp+40h] [rbp-20h] BYREF

  v2 = *a1;
  FileTime = 0;
  SystemTime = 0;
  FileTime2 = 0;
  v13 = 0;
  if ( !*(_DWORD *)v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
      goto LABEL_30;
    if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2b65f2070ddc3355d8bae1c2704efb8f_Traceguids, 2147549183LL);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 == (wchar_t *)&WPP_GLOBAL_Control || (v4[14] & 1) == 0 )
      goto LABEL_30;
    v5 = 40;
    goto LABEL_8;
  }
  SystemTime = *(SYSTEMTIME *)(v2 + 72);
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_30;
    v5 = 41;
    goto LABEL_28;
  }
  if ( !**(_DWORD **)a2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
      goto LABEL_30;
    if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2b65f2070ddc3355d8bae1c2704efb8f_Traceguids, 2147549183LL);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 == (wchar_t *)&WPP_GLOBAL_Control || (v4[14] & 1) == 0 )
      goto LABEL_30;
    v5 = 42;
LABEL_8:
    v6 = 2147549183LL;
LABEL_29:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_20a8864f92ef381b2c942ca08a6ab8ee_Traceguids, v6);
    goto LABEL_30;
  }
  v13 = *(SYSTEMTIME *)(*(_QWORD *)a2 + 72LL);
  if ( SystemTimeToFileTime(&v13, &FileTime2) )
    return (unsigned int)CompareFileTime(&FileTime, &FileTime2) >> 31;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v5 = 43;
LABEL_28:
    v6 = (unsigned int)LastError;
    goto LABEL_29;
  }
LABEL_30:
  LOBYTE(v8) = 0;
  return v8;
}

```

## disassembly

```asm
0x18002c100  mov     [rsp-8+arg_0], rbx
0x18002c105  push    rbp
0x18002c106  mov     rbp, rsp
0x18002c109  sub     rsp, 60h
0x18002c10d  mov     rax, cs:__security_cookie
0x18002c114  xor     rax, rsp
0x18002c117  mov     [rbp+var_10], rax
0x18002c11b  mov     rax, [rcx]
0x18002c11e  xorps   xmm0, xmm0
0x18002c121  xorps   xmm1, xmm1
0x18002c124  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18002c12c  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18002c130  mov     qword ptr [rbp+FileTime2.dwLowDateTime], 0
0x18002c138  mov     rbx, rdx
0x18002c13b  movups  xmmword ptr [rbp+var_20.wYear], xmm1
0x18002c13f  cmp     dword ptr [rax], 0
0x18002c142  jnz     short loc_18002C1A6
0x18002c144  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c14b  lea     rbx, WPP_GLOBAL_Control
0x18002c152  cmp     rcx, rbx
0x18002c155  jz      loc_18002C2D0
0x18002c15b  test    byte ptr [rcx+1Ch], 1
0x18002c15f  jz      short loc_18002C183
0x18002c161  mov     rcx, [rcx+10h]
0x18002c165  lea     r8, WPP_2b65f2070ddc3355d8bae1c2704efb8f_Traceguids
0x18002c16c  mov     edx, 10h
0x18002c171  mov     r9d, 8000FFFFh
0x18002c177  call    WPP_SF_d
0x18002c17c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c183  cmp     rcx, rbx
0x18002c186  jz      loc_18002C2D0
0x18002c18c  test    byte ptr [rcx+1Ch], 1
0x18002c190  jz      loc_18002C2D0
0x18002c196  mov     edx, 28h ; '('
0x18002c19b  mov     r9d, 8000FFFFh
0x18002c1a1  jmp     loc_18002C2C0
0x18002c1a6  movups  xmm0, xmmword ptr [rax+48h]
0x18002c1aa  movdqu  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18002c1af  lea     rdx, [rbp+FileTime]; lpFileTime
0x18002c1b3  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18002c1b7  call    cs:__imp_SystemTimeToFileTime
0x18002c1be  nop     dword ptr [rax+rax+00h]
0x18002c1c3  test    eax, eax
0x18002c1c5  jnz     short loc_18002C20A
0x18002c1c7  call    cs:__imp_GetLastError
0x18002c1ce  nop     dword ptr [rax+rax+00h]
0x18002c1d3  test    eax, eax
0x18002c1d5  jle     short loc_18002C1DF
0x18002c1d7  movzx   eax, ax
0x18002c1da  or      eax, 80070000h
0x18002c1df  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1e6  lea     rbx, WPP_GLOBAL_Control
0x18002c1ed  cmp     rcx, rbx
0x18002c1f0  jz      loc_18002C2D0
0x18002c1f6  test    byte ptr [rcx+1Ch], 1
0x18002c1fa  jz      loc_18002C2D0
0x18002c200  mov     edx, 29h ; ')'
0x18002c205  jmp     loc_18002C2BD
0x18002c20a  mov     rax, [rbx]
0x18002c20d  cmp     dword ptr [rax], 0
0x18002c210  jnz     short loc_18002C266
0x18002c212  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c219  lea     rbx, WPP_GLOBAL_Control
0x18002c220  cmp     rcx, rbx
0x18002c223  jz      loc_18002C2D0
0x18002c229  test    byte ptr [rcx+1Ch], 1
0x18002c22d  jz      short loc_18002C251
0x18002c22f  mov     rcx, [rcx+10h]
0x18002c233  lea     r8, WPP_2b65f2070ddc3355d8bae1c2704efb8f_Traceguids
0x18002c23a  mov     edx, 10h
0x18002c23f  mov     r9d, 8000FFFFh
0x18002c245  call    WPP_SF_d
0x18002c24a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c251  cmp     rcx, rbx
0x18002c254  jz      short loc_18002C2D0
0x18002c256  test    byte ptr [rcx+1Ch], 1
0x18002c25a  jz      short loc_18002C2D0
0x18002c25c  mov     edx, 2Ah ; '*'
0x18002c261  jmp     loc_18002C19B
0x18002c266  movups  xmm0, xmmword ptr [rax+48h]
0x18002c26a  movdqu  xmmword ptr [rbp+var_20.wYear], xmm0
0x18002c26f  lea     rdx, [rbp+FileTime2]; lpFileTime
0x18002c273  lea     rcx, [rbp+var_20]; lpSystemTime
0x18002c277  call    cs:__imp_SystemTimeToFileTime
0x18002c27e  nop     dword ptr [rax+rax+00h]
0x18002c283  test    eax, eax
0x18002c285  jnz     short loc_18002C2D4
0x18002c287  call    cs:__imp_GetLastError
0x18002c28e  nop     dword ptr [rax+rax+00h]
0x18002c293  test    eax, eax
0x18002c295  jle     short loc_18002C29F
0x18002c297  movzx   eax, ax
0x18002c29a  or      eax, 80070000h
0x18002c29f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2a6  lea     rbx, WPP_GLOBAL_Control
0x18002c2ad  cmp     rcx, rbx
0x18002c2b0  jz      short loc_18002C2D0
0x18002c2b2  test    byte ptr [rcx+1Ch], 1
0x18002c2b6  jz      short loc_18002C2D0
0x18002c2b8  mov     edx, 2Bh ; '+'
0x18002c2bd  mov     r9d, eax
0x18002c2c0  mov     rcx, [rcx+10h]
0x18002c2c4  lea     r8, WPP_20a8864f92ef381b2c942ca08a6ab8ee_Traceguids
0x18002c2cb  call    WPP_SF_d
0x18002c2d0  xor     al, al
0x18002c2d2  jmp     short loc_18002C2EB
0x18002c2d4  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18002c2d8  lea     rcx, [rbp+FileTime]; lpFileTime1
0x18002c2dc  call    cs:__imp_CompareFileTime
0x18002c2e3  nop     dword ptr [rax+rax+00h]
0x18002c2e8  shr     eax, 1Fh
0x18002c2eb  mov     rcx, [rbp+var_10]
0x18002c2ef  xor     rcx, rsp; StackCookie
0x18002c2f2  call    __security_check_cookie
0x18002c2f7  mov     rbx, [rsp+60h+arg_0]
0x18002c2fc  add     rsp, 60h
0x18002c300  pop     rbp
0x18002c301  retn
```
