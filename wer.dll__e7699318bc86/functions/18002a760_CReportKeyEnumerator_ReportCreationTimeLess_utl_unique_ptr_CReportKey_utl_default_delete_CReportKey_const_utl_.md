# CReportKeyEnumerator::ReportCreationTimeLess(utl::unique_ptr<CReportKey,utl::default_delete<CReportKey>> const &,utl::unique_ptr<CReportKey,utl::default_delete<CReportKey>> const &)

- ea: `0x18002a760`
- end: `0x18002a944`
- name: `?ReportCreationTimeLess@CReportKeyEnumerator@@CA_NAEBV?$unique_ptr@VCReportKey@@U?$default_delete@VCReportKey@@@utl@@@utl@@0@Z`
- size: `484`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001fe24`
- `0x18002a760`
- `0x180050db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8d5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002a924`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002a924`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002a817`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002a8cb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002a817`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002a8cb`

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
0x18002a760  mov     [rsp-8+arg_0], rbx
0x18002a765  push    rbp
0x18002a766  mov     rbp, rsp
0x18002a769  sub     rsp, 60h
0x18002a76d  mov     rax, cs:__security_cookie
0x18002a774  xor     rax, rsp
0x18002a777  mov     [rbp+var_10], rax
0x18002a77b  mov     rax, [rcx]
0x18002a77e  xorps   xmm0, xmm0
0x18002a781  xorps   xmm1, xmm1
0x18002a784  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18002a78c  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18002a790  mov     qword ptr [rbp+FileTime2.dwLowDateTime], 0
0x18002a798  mov     rbx, rdx
0x18002a79b  movups  xmmword ptr [rbp+var_20.wYear], xmm1
0x18002a79f  cmp     dword ptr [rax], 0
0x18002a7a2  jnz     short loc_18002A806
0x18002a7a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7ab  lea     rbx, WPP_GLOBAL_Control
0x18002a7b2  cmp     rcx, rbx
0x18002a7b5  jz      loc_18002A918
0x18002a7bb  test    byte ptr [rcx+1Ch], 1
0x18002a7bf  jz      short loc_18002A7E3
0x18002a7c1  mov     rcx, [rcx+10h]
0x18002a7c5  lea     r8, WPP_2b65f2070ddc3355d8bae1c2704efb8f_Traceguids
0x18002a7cc  mov     edx, 10h
0x18002a7d1  mov     r9d, 8000FFFFh
0x18002a7d7  call    WPP_SF_d
0x18002a7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7e3  cmp     rcx, rbx
0x18002a7e6  jz      loc_18002A918
0x18002a7ec  test    byte ptr [rcx+1Ch], 1
0x18002a7f0  jz      loc_18002A918
0x18002a7f6  mov     edx, 28h ; '('
0x18002a7fb  mov     r9d, 8000FFFFh
0x18002a801  jmp     loc_18002A908
0x18002a806  movups  xmm0, xmmword ptr [rax+48h]
0x18002a80a  movdqu  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18002a80f  lea     rdx, [rbp+FileTime]; lpFileTime
0x18002a813  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18002a817  call    cs:__imp_SystemTimeToFileTime
0x18002a81d  test    eax, eax
0x18002a81f  jnz     short loc_18002A85E
0x18002a821  call    cs:__imp_GetLastError
0x18002a827  test    eax, eax
0x18002a829  jle     short loc_18002A833
0x18002a82b  movzx   eax, ax
0x18002a82e  or      eax, 80070000h
0x18002a833  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a83a  lea     rbx, WPP_GLOBAL_Control
0x18002a841  cmp     rcx, rbx
0x18002a844  jz      loc_18002A918
0x18002a84a  test    byte ptr [rcx+1Ch], 1
0x18002a84e  jz      loc_18002A918
0x18002a854  mov     edx, 29h ; ')'
0x18002a859  jmp     loc_18002A905
0x18002a85e  mov     rax, [rbx]
0x18002a861  cmp     dword ptr [rax], 0
0x18002a864  jnz     short loc_18002A8BA
0x18002a866  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a86d  lea     rbx, WPP_GLOBAL_Control
0x18002a874  cmp     rcx, rbx
0x18002a877  jz      loc_18002A918
0x18002a87d  test    byte ptr [rcx+1Ch], 1
0x18002a881  jz      short loc_18002A8A5
0x18002a883  mov     rcx, [rcx+10h]
0x18002a887  lea     r8, WPP_2b65f2070ddc3355d8bae1c2704efb8f_Traceguids
0x18002a88e  mov     edx, 10h
0x18002a893  mov     r9d, 8000FFFFh
0x18002a899  call    WPP_SF_d
0x18002a89e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8a5  cmp     rcx, rbx
0x18002a8a8  jz      short loc_18002A918
0x18002a8aa  test    byte ptr [rcx+1Ch], 1
0x18002a8ae  jz      short loc_18002A918
0x18002a8b0  mov     edx, 2Ah ; '*'
0x18002a8b5  jmp     loc_18002A7FB
0x18002a8ba  movups  xmm0, xmmword ptr [rax+48h]
0x18002a8be  movdqu  xmmword ptr [rbp+var_20.wYear], xmm0
0x18002a8c3  lea     rdx, [rbp+FileTime2]; lpFileTime
0x18002a8c7  lea     rcx, [rbp+var_20]; lpSystemTime
0x18002a8cb  call    cs:__imp_SystemTimeToFileTime
0x18002a8d1  test    eax, eax
0x18002a8d3  jnz     short loc_18002A91C
0x18002a8d5  call    cs:__imp_GetLastError
0x18002a8db  test    eax, eax
0x18002a8dd  jle     short loc_18002A8E7
0x18002a8df  movzx   eax, ax
0x18002a8e2  or      eax, 80070000h
0x18002a8e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8ee  lea     rbx, WPP_GLOBAL_Control
0x18002a8f5  cmp     rcx, rbx
0x18002a8f8  jz      short loc_18002A918
0x18002a8fa  test    byte ptr [rcx+1Ch], 1
0x18002a8fe  jz      short loc_18002A918
0x18002a900  mov     edx, 2Bh ; '+'
0x18002a905  mov     r9d, eax
0x18002a908  mov     rcx, [rcx+10h]
0x18002a90c  lea     r8, WPP_20a8864f92ef381b2c942ca08a6ab8ee_Traceguids
0x18002a913  call    WPP_SF_d
0x18002a918  xor     al, al
0x18002a91a  jmp     short loc_18002A92D
0x18002a91c  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18002a920  lea     rcx, [rbp+FileTime]; lpFileTime1
0x18002a924  call    cs:__imp_CompareFileTime
0x18002a92a  shr     eax, 1Fh
0x18002a92d  mov     rcx, [rbp+var_10]
0x18002a931  xor     rcx, rsp; StackCookie
0x18002a934  call    __security_check_cookie
0x18002a939  mov     rbx, [rsp+60h+arg_0]
0x18002a93e  add     rsp, 60h
0x18002a942  pop     rbp
0x18002a943  retn
```
