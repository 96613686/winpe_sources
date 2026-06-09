# LogSharingViolationErrorInfo

- ea: `0x18001756c`
- end: `0x18001798c`
- name: `LogSharingViolationErrorInfo`
- size: `1056`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18000db70`

## callees

- `0x180011788`
- `0x180017344`
- `0x18001756c`
- `0x1800607b0`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x18001772a`
- `KERNEL32!OpenProcess` at `0x18001772a`
- `KERNEL32!HeapFree` at `0x180017664`
- `KERNEL32!HeapFree` at `0x180017850`
- `KERNEL32!HeapFree` at `0x180017927`
- `KERNEL32!HeapFree` at `0x180061b20`
- `KERNEL32!HeapFree` at `0x180017664`
- `KERNEL32!HeapFree` at `0x180017850`
- `KERNEL32!HeapFree` at `0x180017927`
- `KERNEL32!HeapFree` at `0x180061b20`
- `KERNEL32!HeapAlloc` at `0x180017692`
- `KERNEL32!HeapAlloc` at `0x180017796`
- `KERNEL32!HeapAlloc` at `0x180017692`
- `KERNEL32!HeapAlloc` at `0x180017796`
- `KERNEL32!GetLastError` at `0x1800175fe`
- `KERNEL32!GetLastError` at `0x18001760e`
- `KERNEL32!GetLastError` at `0x18001761c`
- `KERNEL32!GetLastError` at `0x1800175fe`
- `KERNEL32!GetLastError` at `0x18001760e`
- `KERNEL32!GetLastError` at `0x18001761c`
- `KERNEL32!CloseHandle` at `0x180017940`
- `KERNEL32!CloseHandle` at `0x180061b46`
- `KERNEL32!CloseHandle` at `0x180017940`
- `KERNEL32!CloseHandle` at `0x180061b46`
- `KERNEL32!CreateFileW` at `0x1800175df`
- `KERNEL32!CreateFileW` at `0x1800175df`
- `KERNEL32!GetProcessHeap` at `0x180017650`
- `KERNEL32!GetProcessHeap` at `0x18001767b`
- `KERNEL32!GetProcessHeap` at `0x18001777f`
- `KERNEL32!GetProcessHeap` at `0x18001783c`
- `KERNEL32!GetProcessHeap` at `0x180017913`
- `KERNEL32!GetProcessHeap` at `0x180061b0c`
- `KERNEL32!GetProcessHeap` at `0x180017650`
- `KERNEL32!GetProcessHeap` at `0x18001767b`
- `KERNEL32!GetProcessHeap` at `0x18001777f`
- `KERNEL32!GetProcessHeap` at `0x18001783c`
- `KERNEL32!GetProcessHeap` at `0x180017913`
- `KERNEL32!GetProcessHeap` at `0x180061b0c`
- `ntdll!NtQueryInformationProcess` at `0x18001775e`
- `ntdll!NtQueryInformationProcess` at `0x1800177ce`
- `ntdll!NtQueryInformationProcess` at `0x18001775e`
- `ntdll!NtQueryInformationProcess` at `0x1800177ce`
- `ntdll!NtQueryInformationFile` at `0x1800176ce`
- `ntdll!NtQueryInformationFile` at `0x1800176ce`

## string_xrefs

- `0x1800177f0`: `Process %s is accessing file wim %s`
- `0x180017872`: `Process PID %d is accessing file wim %s`
- `0x1800178c3`: `Process PID %d is accessing file wim %s`

## pseudocode

```c
__int64 __fastcall LogSharingViolationErrorInfo(const WCHAR *a1, int a2)
{
  unsigned int *v3; // rdi
  ULONG v4; // esi
  char *FileW; // r14
  HANDLE ProcessHeap; // rax
  HANDLE v7; // rax
  unsigned int *v8; // rax
  NTSTATUS v9; // eax
  unsigned int v10; // esi
  DWORD v11; // r15d
  char *v12; // r13
  NTSTATUS InformationProcess; // ebx
  ULONG v14; // ebx
  HANDLE v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r15
  HANDLE v18; // rax
  HANDLE v19; // rax
  ULONG ReturnLength; // [rsp+44h] [rbp-694h] BYREF
  DWORD v22; // [rsp+48h] [rbp-690h]
  unsigned int *v23; // [rsp+50h] [rbp-688h]
  int v24; // [rsp+58h] [rbp-680h]
  __int64 v25; // [rsp+60h] [rbp-678h]
  ULONG v26; // [rsp+68h] [rbp-670h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-668h] BYREF
  wchar_t Buffer[784]; // [rsp+80h] [rbp-658h] BYREF

  v25 = -1;
  v3 = 0;
  v23 = 0;
  v4 = 16;
  ReturnLength = 0;
  if ( a2 == 32 )
  {
    FileW = (char *)CreateFileW(a1, 0x100080u, 7u, 0, 3u, 0x2000000u, 0);
    v25 = (__int64)FileW;
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      while ( 1 )
      {
        IoStatusBlock.Pointer = 0;
        IoStatusBlock.Information = 0;
        if ( v3 )
        {
          ProcessHeap = GetProcessHeap();
          if ( HeapFree(ProcessHeap, 0, v3) )
            v3 = 0;
          v23 = v3;
        }
        v7 = GetProcessHeap();
        v8 = (unsigned int *)HeapAlloc(v7, 8u, v4);
        v3 = v8;
        v23 = v8;
        if ( !v8 )
          break;
        v9 = NtQueryInformationFile(FileW, &IoStatusBlock, v8, v4, FileProcessIdsUsingFileInformation);
        if ( v9 >= 0 )
        {
          if ( 4 * *v3 + 12 <= v4 )
          {
            v10 = 0;
            v24 = 0;
            while ( v10 < *v3 )
            {
              v11 = v3[2 * v10 + 2];
              v22 = v11;
              v12 = (char *)OpenProcess(0x400u, 0, v11);
              if ( (unsigned __int64)(v12 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
              {
                StringCchPrintfW(Buffer, 0x30Cu, L"Process PID %d is accessing file wim %s", v11, a1);
                WIMLogMsg(2, 0, 0, (int)Buffer, 0, (__int64)L"LogSharingViolationErrorInfo", 2052);
              }
              else
              {
                InformationProcess = NtQueryInformationProcess(v12, ProcessImageFileName, 0, 0, &ReturnLength);
                if ( InformationProcess == -1073741820 )
                {
                  v14 = ReturnLength;
                  v15 = GetProcessHeap();
                  v16 = HeapAlloc(v15, 8u, v14);
                  v17 = v16;
                  if ( v16 )
                  {
                    InformationProcess = NtQueryInformationProcess(v12, ProcessImageFileName, v16, ReturnLength, 0);
                    if ( InformationProcess >= 0 )
                    {
                      StringCchPrintfW(Buffer, 0x30Cu, L"Process %s is accessing file wim %s", v17[1], a1);
                      WIMLogMsg(2, 0, 0, (int)Buffer, 0, (__int64)L"LogSharingViolationErrorInfo", 2030);
                    }
                  }
                  else
                  {
                    InformationProcess = -1073741789;
                  }
                  if ( v17 )
                  {
                    v18 = GetProcessHeap();
                    HeapFree(v18, 0, v17);
                  }
                  v11 = v22;
                }
                if ( InformationProcess )
                {
                  StringCchPrintfW(Buffer, 0x30Cu, L"Process PID %d is accessing file wim %s", v11, a1);
                  WIMLogMsg(2, 0, 0, (int)Buffer, 0, (__int64)L"LogSharingViolationErrorInfo", 2045);
                }
              }
              v24 = ++v10;
            }
          }
          break;
        }
        if ( v9 != -2147483643 && v9 != -1073741789 && v9 != -1073741820 )
          break;
        v4 *= 2;
        v26 = v4;
      }
    }
    else if ( (int)GetLastError() > 0 )
    {
      GetLastError();
    }
    else
    {
      GetLastError();
    }
    if ( v3 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v3);
    }
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
  }
  return 0;
}

```

## disassembly

```asm
0x18001756c  mov     [rsp+arg_8], rbx
0x180017571  mov     [rsp+arg_10], rsi
0x180017576  push    rdi
0x180017577  push    r12
0x180017579  push    r13
0x18001757b  push    r14
0x18001757d  push    r15
0x18001757f  sub     rsp, 6B0h
0x180017586  mov     rax, cs:__security_cookie
0x18001758d  xor     rax, rsp
0x180017590  mov     [rsp+6D8h+var_38], rax
0x180017598  mov     r12, rcx
0x18001759b  or      [rsp+6D8h+var_678], 0FFFFFFFFFFFFFFFFh
0x1800175a1  xor     r13d, r13d
0x1800175a4  mov     edi, r13d
0x1800175a7  mov     [rsp+6D8h+var_688], r13
0x1800175ac  lea     esi, [r13+10h]
0x1800175b0  mov     [rsp+6D8h+ReturnLength], r13d
0x1800175b5  cmp     edx, 20h ; ' '
0x1800175b8  jnz     loc_18001794C
0x1800175be  mov     [rsp+6D8h+hTemplateFile], r13; hTemplateFile
0x1800175c3  mov     [rsp+6D8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800175cb  mov     [rsp+6D8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800175d3  xor     r9d, r9d; lpSecurityAttributes
0x1800175d6  mov     edx, 100080h; dwDesiredAccess
0x1800175db  lea     r8d, [r13+7]; dwShareMode
0x1800175df  call    cs:__imp_CreateFileW
0x1800175e6  nop     dword ptr [rax+rax+00h]
0x1800175eb  mov     r14, rax
0x1800175ee  mov     [rsp+6D8h+var_678], rax
0x1800175f3  inc     rax
0x1800175f6  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800175fc  jnz     short loc_180017639
0x1800175fe  call    cs:__imp_GetLastError
0x180017605  nop     dword ptr [rax+rax+00h]
0x18001760a  test    eax, eax
0x18001760c  jg      short loc_18001761C
0x18001760e  call    cs:__imp_GetLastError
0x180017615  nop     dword ptr [rax+rax+00h]
0x18001761a  jmp     short loc_180017630
0x18001761c  call    cs:__imp_GetLastError
0x180017623  nop     dword ptr [rax+rax+00h]
0x180017628  movzx   eax, ax
0x18001762b  or      eax, 0C0070000h
0x180017630  mov     [rsp+6D8h+var_698], eax
0x180017634  jmp     loc_18001790E
0x180017639  mov     r15d, 80000005h
0x18001763f  xor     eax, eax
0x180017641  mov     qword ptr [rsp+6D8h+IoStatusBlock], rax
0x180017646  mov     [rsp+6D8h+IoStatusBlock.Information], rax
0x18001764b  test    rdi, rdi
0x18001764e  jz      short loc_18001767B
0x180017650  call    cs:__imp_GetProcessHeap
0x180017657  nop     dword ptr [rax+rax+00h]
0x18001765c  mov     rcx, rax; hHeap
0x18001765f  mov     r8, rdi; lpMem
0x180017662  xor     edx, edx; dwFlags
0x180017664  call    cs:__imp_HeapFree
0x18001766b  nop     dword ptr [rax+rax+00h]
0x180017670  test    eax, eax
0x180017672  cmovnz  rdi, r13
0x180017676  mov     [rsp+6D8h+var_688], rdi
0x18001767b  call    cs:__imp_GetProcessHeap
0x180017682  nop     dword ptr [rax+rax+00h]
0x180017687  mov     rcx, rax; hHeap
0x18001768a  mov     r8d, esi; dwBytes
0x18001768d  mov     edx, 8; dwFlags
0x180017692  call    cs:__imp_HeapAlloc
0x180017699  nop     dword ptr [rax+rax+00h]
0x18001769e  mov     rdi, rax
0x1800176a1  mov     [rsp+6D8h+var_688], rax
0x1800176a6  test    rax, rax
0x1800176a9  jnz     short loc_1800176B8
0x1800176ab  mov     [rsp+6D8h+var_698], 0C0000017h
0x1800176b3  jmp     loc_18001790E
0x1800176b8  mov     [rsp+6D8h+dwCreationDisposition], 2Fh ; '/'; FileInformationClass
0x1800176c0  mov     r9d, esi; Length
0x1800176c3  mov     r8, rdi; FileInformation
0x1800176c6  lea     rdx, [rsp+6D8h+IoStatusBlock]; IoStatusBlock
0x1800176cb  mov     rcx, r14; FileHandle
0x1800176ce  call    cs:__imp_NtQueryInformationFile
0x1800176d5  nop     dword ptr [rax+rax+00h]
0x1800176da  mov     [rsp+6D8h+var_698], eax
0x1800176de  test    eax, eax
0x1800176e0  js      loc_1800178FB
0x1800176e6  mov     eax, [rdi]
0x1800176e8  lea     eax, ds:0Ch[rax*4]
0x1800176ef  cmp     eax, esi
0x1800176f1  jbe     short loc_1800176FD
0x1800176f3  mov     [rsp+6D8h+var_698], r15d
0x1800176f8  jmp     loc_18001790E
0x1800176fd  mov     esi, r13d
0x180017700  mov     [rsp+6D8h+var_680], r13d
0x180017705  lea     rbx, aLogsharingviol; "LogSharingViolationErrorInfo"
0x18001770c  cmp     esi, [rdi]
0x18001770e  jnb     loc_18001790E
0x180017714  mov     eax, esi
0x180017716  mov     r15d, [rdi+rax*8+8]
0x18001771b  mov     [rsp+6D8h+var_690], r15d
0x180017720  mov     r8d, r15d; dwProcessId
0x180017723  xor     edx, edx; bInheritHandle
0x180017725  mov     ecx, 400h; dwDesiredAccess
0x18001772a  call    cs:__imp_OpenProcess
0x180017731  nop     dword ptr [rax+rax+00h]
0x180017736  mov     r13, rax
0x180017739  lea     rcx, [rax-1]
0x18001773d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180017741  ja      loc_1800178BB
0x180017747  lea     rax, [rsp+6D8h+ReturnLength]
0x18001774c  mov     qword ptr [rsp+6D8h+dwCreationDisposition], rax; ReturnLength
0x180017751  xor     r9d, r9d; ProcessInformationLength
0x180017754  xor     r8d, r8d; ProcessInformation
0x180017757  lea     edx, [r9+1Bh]; ProcessInformationClass
0x18001775b  mov     rcx, r13; ProcessHandle
0x18001775e  call    cs:__imp_NtQueryInformationProcess
0x180017765  nop     dword ptr [rax+rax+00h]
0x18001776a  mov     ebx, eax
0x18001776c  mov     [rsp+6D8h+var_698], eax
0x180017770  cmp     eax, 0C0000004h
0x180017775  jnz     loc_180017863
0x18001777b  mov     ebx, [rsp+6D8h+ReturnLength]
0x18001777f  call    cs:__imp_GetProcessHeap
0x180017786  nop     dword ptr [rax+rax+00h]
0x18001778b  mov     rcx, rax; hHeap
0x18001778e  mov     r8d, ebx; dwBytes
0x180017791  mov     edx, 8; dwFlags
0x180017796  call    cs:__imp_HeapAlloc
0x18001779d  nop     dword ptr [rax+rax+00h]
0x1800177a2  mov     r15, rax
0x1800177a5  test    rax, rax
0x1800177a8  jnz     short loc_1800177B8
0x1800177aa  mov     ebx, 0C0000023h
0x1800177af  mov     [rsp+6D8h+var_698], ebx
0x1800177b3  xor     r13d, r13d
0x1800177b6  jmp     short loc_180017837
0x1800177b8  and     qword ptr [rsp+6D8h+dwCreationDisposition], 0
0x1800177be  mov     r9d, [rsp+6D8h+ReturnLength]; ProcessInformationLength
0x1800177c3  mov     r8, r15; ProcessInformation
0x1800177c6  mov     edx, 1Bh; ProcessInformationClass
0x1800177cb  mov     rcx, r13; ProcessHandle
0x1800177ce  call    cs:__imp_NtQueryInformationProcess
0x1800177d5  nop     dword ptr [rax+rax+00h]
0x1800177da  mov     ebx, eax
0x1800177dc  mov     [rsp+6D8h+var_698], eax
0x1800177e0  xor     r13d, r13d
0x1800177e3  test    eax, eax
0x1800177e5  js      short loc_180017837
0x1800177e7  mov     qword ptr [rsp+6D8h+dwCreationDisposition], r12
0x1800177ec  mov     r9, [r15+8]
0x1800177f0  lea     r8, aProcessSIsAcce; "Process %s is accessing file wim %s"
0x1800177f7  mov     edx, 30Ch; unsigned __int64
0x1800177fc  lea     rcx, [rsp+6D8h+Buffer]; Buffer
0x180017804  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017809  mov     dword ptr [rsp+6D8h+hTemplateFile], 7EEh; int
0x180017811  lea     rax, aLogsharingviol; "LogSharingViolationErrorInfo"
0x180017818  mov     qword ptr [rsp+6D8h+dwFlagsAndAttributes], rax; __int64
0x18001781d  mov     [rsp+6D8h+dwCreationDisposition], r13d; Status
0x180017822  lea     r9, [rsp+6D8h+Buffer]; int
0x18001782a  xor     r8d, r8d; int
0x18001782d  xor     edx, edx; int
0x18001782f  lea     ecx, [rdx+2]; int
0x180017832  call    _WIMLogMsg
0x180017837  test    r15, r15
0x18001783a  jz      short loc_18001785C
0x18001783c  call    cs:__imp_GetProcessHeap
0x180017843  nop     dword ptr [rax+rax+00h]
0x180017848  mov     rcx, rax; hHeap
0x18001784b  mov     r8, r15; lpMem
0x18001784e  xor     edx, edx; dwFlags
0x180017850  call    cs:__imp_HeapFree
0x180017857  nop     dword ptr [rax+rax+00h]
0x18001785c  mov     r15d, [rsp+6D8h+var_690]
0x180017861  jmp     short loc_180017866
0x180017863  xor     r13d, r13d
0x180017866  test    ebx, ebx
0x180017868  jz      short loc_1800178E9
0x18001786a  mov     qword ptr [rsp+6D8h+dwCreationDisposition], r12
0x18001786f  mov     r9d, r15d
0x180017872  lea     r8, aProcessPidDIsA; "Process PID %d is accessing file wim %s"
0x180017879  mov     edx, 30Ch; unsigned __int64
0x18001787e  lea     rcx, [rsp+6D8h+Buffer]; Buffer
0x180017886  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001788b  mov     dword ptr [rsp+6D8h+hTemplateFile], 7FDh; int
0x180017893  lea     rbx, aLogsharingviol; "LogSharingViolationErrorInfo"
0x18001789a  mov     qword ptr [rsp+6D8h+dwFlagsAndAttributes], rbx; __int64
0x18001789f  mov     [rsp+6D8h+dwCreationDisposition], r13d; Status
0x1800178a4  lea     r9, [rsp+6D8h+Buffer]; int
0x1800178ac  xor     r8d, r8d; int
0x1800178af  xor     edx, edx; int
0x1800178b1  lea     ecx, [rdx+2]; int
0x1800178b4  call    _WIMLogMsg
0x1800178b9  jmp     short loc_1800178F0
0x1800178bb  mov     qword ptr [rsp+6D8h+dwCreationDisposition], r12
0x1800178c0  mov     r9d, r15d
0x1800178c3  lea     r8, aProcessPidDIsA; "Process PID %d is accessing file wim %s"
0x1800178ca  mov     edx, 30Ch; unsigned __int64
0x1800178cf  lea     rcx, [rsp+6D8h+Buffer]; Buffer
0x1800178d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800178dc  mov     dword ptr [rsp+6D8h+hTemplateFile], 804h
0x1800178e4  xor     r13d, r13d
0x1800178e7  jmp     short loc_18001789A
0x1800178e9  lea     rbx, aLogsharingviol; "LogSharingViolationErrorInfo"
0x1800178f0  inc     esi
0x1800178f2  mov     [rsp+6D8h+var_680], esi
0x1800178f6  jmp     loc_18001770C
0x1800178fb  cmp     eax, r15d
0x1800178fe  jz      short loc_18001797B
0x180017900  cmp     eax, 0C0000023h
0x180017905  jz      short loc_18001797B
0x180017907  cmp     eax, 0C0000004h
0x18001790c  jz      short loc_18001797B
0x18001790e  test    rdi, rdi
0x180017911  jz      short loc_180017933
0x180017913  call    cs:__imp_GetProcessHeap
0x18001791a  nop     dword ptr [rax+rax+00h]
0x18001791f  mov     rcx, rax; hHeap
0x180017922  mov     r8, rdi; lpMem
0x180017925  xor     edx, edx; dwFlags
0x180017927  call    cs:__imp_HeapFree
0x18001792e  nop     dword ptr [rax+rax+00h]
0x180017933  lea     rax, [r14-1]
0x180017937  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001793b  ja      short loc_18001794C
0x18001793d  mov     rcx, r14; hObject
0x180017940  call    cs:__imp_CloseHandle
0x180017947  nop     dword ptr [rax+rax+00h]
0x18001794c  xor     eax, eax
0x18001794e  mov     rcx, [rsp+6D8h+var_38]
0x180017956  xor     rcx, rsp; StackCookie
0x180017959  call    __security_check_cookie
0x18001795e  lea     r11, [rsp+6D8h+var_28]
0x180017966  mov     rbx, [r11+38h]
0x18001796a  mov     rsi, [r11+40h]
0x18001796e  mov     rsp, r11
0x180017971  pop     r15
0x180017973  pop     r14
0x180017975  pop     r13
0x180017977  pop     r12
0x180017979  pop     rdi
0x18001797a  retn
0x18001797b  add     esi, esi
0x18001797d  mov     [rsp+6D8h+var_670], esi
0x180017981  mov     [rsp+6D8h+var_698], r13d
0x180017986  jmp     loc_18001763F
0x180061af9  push    rbx
0x180061afb  push    rbp
0x180061afc  sub     rsp, 48h
0x180061b00  mov     rbp, rdx
0x180061b03  mov     rbx, [rbp+50h]
0x180061b07  test    rbx, rbx
0x180061b0a  jz      short loc_180061B38
0x180061b0c  call    cs:__imp_GetProcessHeap
0x180061b13  nop     dword ptr [rax+rax+00h]
0x180061b18  mov     rcx, rax; hHeap
0x180061b1b  mov     r8, rbx; lpMem
0x180061b1e  xor     edx, edx; dwFlags
0x180061b20  call    cs:__imp_HeapFree
0x180061b27  nop     dword ptr [rax+rax+00h]
0x180061b2c  xor     ecx, ecx
0x180061b2e  test    eax, eax
0x180061b30  cmovnz  rbx, rcx
0x180061b34  mov     [rbp+50h], rbx
0x180061b38  mov     rcx, [rbp+60h]; hObject
0x180061b3c  lea     rax, [rcx-1]
0x180061b40  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180061b44  ja      short loc_180061B53
0x180061b46  call    cs:__imp_CloseHandle
0x180061b4d  nop     dword ptr [rax+rax+00h]
0x180061b52  nop
0x180061b53  add     rsp, 48h
0x180061b57  pop     rbp
0x180061b58  pop     rbx
0x180061b59  retn
```
