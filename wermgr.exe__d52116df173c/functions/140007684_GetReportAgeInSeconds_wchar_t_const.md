# GetReportAgeInSeconds(wchar_t const *)

- ea: `0x140007684`
- end: `0x140007880`
- name: `?GetReportAgeInSeconds@@YAKPEB_W@Z`
- size: `508`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140005f98`

## callees

- `0x140003200`
- `0x140007684`
- `0x14000e340`
- `0x14000e3e0`
- `0x14001c0e0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400077f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400077f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400077df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400077df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007860`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007860`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400076ec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400076ec`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x14000775b`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x14000775b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400077b8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400077b8`

## pseudocode

```c
__int64 __fastcall GetReportAgeInSeconds(const wchar_t *a1)
{
  int v1; // esi
  __int64 v2; // rbx
  HANDLE FileW; // rax
  void *v4; // rdi
  char v5; // al
  DWORD LastError; // eax
  __int64 v7; // rdx
  int TimeDeltaInMilliseconds; // eax
  struct _FILETIME CreationTime; // [rsp+40h] [rbp-9h] BYREF
  __int64 v11; // [rsp+48h] [rbp-1h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+50h] [rbp+7h] BYREF
  struct _SYSTEMTIME v13; // [rsp+60h] [rbp+17h] BYREF

  CreationTime = 0;
  v11 = 0;
  v1 = (int)a1;
  LODWORD(v2) = -1;
  v13 = 0;
  SystemTime = 0;
  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
  v4 = FileW;
  if ( (unsigned __int64)FileW + 1 > 1 )
  {
    if ( GetFileTime(FileW, &CreationTime, 0, 0) )
    {
      if ( FileTimeToSystemTime(&CreationTime, &SystemTime) )
      {
        GetSystemTime(&v13);
        TimeDeltaInMilliseconds = CTime::GetTimeDeltaInMilliseconds(&v13, &SystemTime, &v11);
        if ( TimeDeltaInMilliseconds >= 0 )
        {
          v2 = v11 / 1000;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids,
            (unsigned int)TimeDeltaInMilliseconds);
        }
        goto LABEL_19;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_19:
        CloseHandle(v4);
        return (unsigned int)v2;
      }
      LastError = GetLastError();
      v7 = 32;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      LastError = GetLastError();
      v7 = 31;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids, LastError);
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = GetLastError();
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids,
      v1,
      v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140007684  push    rbp
0x140007686  push    rbx
0x140007687  push    rsi
0x140007688  push    rdi
0x140007689  lea     rbp, [rsp-3Fh]
0x14000768e  sub     rsp, 88h
0x140007695  mov     rax, cs:__security_cookie
0x14000769c  xor     rax, rsp
0x14000769f  mov     [rbp+57h+var_30], rax
0x1400076a3  xor     r9d, r9d; lpSecurityAttributes
0x1400076a6  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x1400076af  xorps   xmm0, xmm0
0x1400076b2  mov     [rsp+0A0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1400076ba  xorps   xmm1, xmm1
0x1400076bd  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], 0
0x1400076c5  mov     edx, 80000000h; dwDesiredAccess
0x1400076ca  mov     [rbp+57h+var_58], 0
0x1400076d2  lea     r8d, [r9+7]; dwShareMode
0x1400076d6  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x1400076de  mov     rsi, rcx
0x1400076e1  or      ebx, 0FFFFFFFFh
0x1400076e4  movups  xmmword ptr [rbp+57h+var_40.wYear], xmm0
0x1400076e8  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm1
0x1400076ec  call    cs:__imp_CreateFileW
0x1400076f2  mov     rdi, rax
0x1400076f5  lea     rcx, [rax+1]
0x1400076f9  cmp     rcx, 1
0x1400076fd  ja      short loc_14000774E
0x1400076ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140007706  lea     rax, WPP_GLOBAL_Control
0x14000770d  cmp     rcx, rax
0x140007710  jz      loc_140007866
0x140007716  test    byte ptr [rcx+1Ch], 1
0x14000771a  jz      loc_140007866
0x140007720  call    cs:__imp_GetLastError
0x140007726  mov     rcx, cs:WPP_GLOBAL_Control
0x14000772d  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x140007734  mov     edx, 1Eh
0x140007739  mov     [rsp+0A0h+dwCreationDisposition], eax
0x14000773d  mov     r9, rsi
0x140007740  mov     rcx, [rcx+10h]
0x140007744  call    WPP_SF_SD
0x140007749  jmp     loc_140007866
0x14000774e  xor     r9d, r9d; lpLastWriteTime
0x140007751  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x140007755  xor     r8d, r8d; lpLastAccessTime
0x140007758  mov     rcx, rdi; hFile
0x14000775b  call    cs:__imp_GetFileTime
0x140007761  test    eax, eax
0x140007763  jnz     short loc_1400077B0
0x140007765  mov     rcx, cs:WPP_GLOBAL_Control
0x14000776c  lea     rax, WPP_GLOBAL_Control
0x140007773  cmp     rcx, rax
0x140007776  jz      loc_14000785D
0x14000777c  test    byte ptr [rcx+1Ch], 1
0x140007780  jz      loc_14000785D
0x140007786  call    cs:__imp_GetLastError
0x14000778c  mov     edx, 1Fh
0x140007791  mov     rcx, cs:WPP_GLOBAL_Control
0x140007798  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x14000779f  mov     r9d, eax
0x1400077a2  mov     rcx, [rcx+10h]
0x1400077a6  call    WPP_SF_d
0x1400077ab  jmp     loc_14000785D
0x1400077b0  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1400077b4  lea     rcx, [rbp+57h+CreationTime]; lpFileTime
0x1400077b8  call    cs:__imp_FileTimeToSystemTime
0x1400077be  test    eax, eax
0x1400077c0  jnz     short loc_1400077EC
0x1400077c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400077c9  lea     rax, WPP_GLOBAL_Control
0x1400077d0  cmp     rcx, rax
0x1400077d3  jz      loc_14000785D
0x1400077d9  test    byte ptr [rcx+1Ch], 1
0x1400077dd  jz      short loc_14000785D
0x1400077df  call    cs:__imp_GetLastError
0x1400077e5  mov     edx, 20h ; ' '
0x1400077ea  jmp     short loc_140007791
0x1400077ec  lea     rcx, [rbp+57h+var_40]; lpSystemTime
0x1400077f0  call    cs:__imp_GetSystemTime
0x1400077f6  lea     r8, [rbp+57h+var_58]; __int64 *
0x1400077fa  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x1400077fe  lea     rcx, [rbp+57h+var_40]; struct _SYSTEMTIME *
0x140007802  call    ?GetTimeDeltaInMilliseconds@CTime@@SAJPEAU_SYSTEMTIME@@0PEA_J@Z; CTime::GetTimeDeltaInMilliseconds(_SYSTEMTIME *,_SYSTEMTIME *,__int64 *)
0x140007807  mov     r9d, eax
0x14000780a  test    eax, eax
0x14000780c  jns     short loc_14000783E
0x14000780e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007815  lea     rax, WPP_GLOBAL_Control
0x14000781c  cmp     rcx, rax
0x14000781f  jz      short loc_14000785D
0x140007821  test    byte ptr [rcx+1Ch], 1
0x140007825  jz      short loc_14000785D
0x140007827  mov     rcx, [rcx+10h]
0x14000782b  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x140007832  mov     edx, 21h ; '!'
0x140007837  call    WPP_SF_d
0x14000783c  jmp     short loc_14000785D
0x14000783e  mov     rax, 20C49BA5E353F7CFh
0x140007848  imul    [rbp+57h+var_58]
0x14000784c  mov     rbx, rdx
0x14000784f  sar     rbx, 7
0x140007853  mov     rcx, rbx
0x140007856  shr     rcx, 3Fh
0x14000785a  add     rbx, rcx
0x14000785d  mov     rcx, rdi; hObject
0x140007860  call    cs:__imp_CloseHandle
0x140007866  mov     eax, ebx
0x140007868  mov     rcx, [rbp+57h+var_30]
0x14000786c  xor     rcx, rsp; StackCookie
0x14000786f  call    __security_check_cookie
0x140007874  add     rsp, 88h
0x14000787b  pop     rdi
0x14000787c  pop     rsi
0x14000787d  pop     rbx
0x14000787e  pop     rbp
0x14000787f  retn
```
