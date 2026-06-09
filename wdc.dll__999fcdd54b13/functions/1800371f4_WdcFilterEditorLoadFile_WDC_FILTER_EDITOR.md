# WdcFilterEditorLoadFile(_WDC_FILTER_EDITOR *)

- ea: `0x1800371f4`
- end: `0x180037338`
- name: `?WdcFilterEditorLoadFile@@YAJPEAU_WDC_FILTER_EDITOR@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(struct _WDC_FILTER_EDITOR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002af80`

## callees

- `0x18000b854`
- `0x1800371f4`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800372b9`
- `KERNEL32!ReadFile` at `0x1800372b9`
- `KERNEL32!CreateFileW` at `0x180037245`
- `KERNEL32!CreateFileW` at `0x180037245`
- `KERNEL32!CloseHandle` at `0x180037320`
- `KERNEL32!CloseHandle` at `0x180037320`
- `KERNEL32!GetLastError` at `0x180037253`
- `KERNEL32!GetLastError` at `0x1800372c7`
- `KERNEL32!GetLastError` at `0x180037253`
- `KERNEL32!GetLastError` at `0x1800372c7`

## pseudocode

```c
__int64 __fastcall WdcFilterEditorLoadFile(struct _WDC_FILTER_EDITOR *a1)
{
  const WCHAR *v2; // rcx
  char *v3; // rax
  char *v4; // rdi
  signed int LastError; // eax
  signed int v6; // ebx
  signed int v7; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-48h]
  LPOVERLAPPED lpOverlappeda; // [rsp+20h] [rbp-48h]
  struct _SECURITY_ATTRIBUTES v11; // [rsp+40h] [rbp-28h] BYREF

  v2 = (const WCHAR *)*((_QWORD *)a1 + 6);
  *(_QWORD *)&v11.nLength = 24;
  *(_QWORD *)&v11.bInheritHandle = 1;
  v11.lpSecurityDescriptor = 0;
  v3 = (char *)CreateFileW(v2, 0xC0000000, 3u, &v11, 3u, 0, 0);
  v4 = v3;
  if ( v3 && v3 != (char *)-1LL )
    goto LABEL_10;
  LastError = GetLastError();
  v6 = LastError;
  if ( !LastError )
  {
    v6 = -2147467259;
LABEL_8:
    LODWORD(lpOverlapped) = v6;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp",
      "WdcFilterEditorLoadFile",
      0,
      L"FAILURE: 0x%08x",
      lpOverlapped);
    return (unsigned int)v6;
  }
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_8;
LABEL_10:
  if ( ReadFile(v4, *((LPVOID *)a1 + 7), *((_DWORD *)a1 + 10), (LPDWORD)a1 + 8, 0) )
  {
    v6 = 0;
LABEL_16:
    *((_DWORD *)a1 + 3) = 2;
    goto LABEL_19;
  }
  v7 = GetLastError();
  v6 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 >= 0 )
      goto LABEL_16;
  }
  else
  {
    v6 = -2147467259;
  }
  LODWORD(lpOverlappeda) = v6;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp",
    "WdcFilterEditorLoadFile",
    0,
    L"FAILURE: 0x%08x",
    lpOverlappeda);
LABEL_19:
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800371f4  mov     rax, rsp
0x1800371f7  mov     [rax+8], rbx
0x1800371fb  mov     [rax+10h], rsi
0x1800371ff  push    rdi
0x180037200  sub     rsp, 60h
0x180037204  mov     qword ptr [rax-38h], 0
0x18003720c  lea     r9, [rax-28h]; lpSecurityAttributes
0x180037210  mov     rsi, rcx
0x180037213  mov     dword ptr [rax-40h], 0
0x18003721a  mov     rcx, [rcx+30h]; lpFileName
0x18003721e  mov     r8d, 3; dwShareMode
0x180037224  mov     edx, 0C0000000h; dwDesiredAccess
0x180037229  mov     [rax-48h], r8d
0x18003722d  mov     qword ptr [rax-28h], 18h
0x180037235  mov     qword ptr [rax-18h], 1
0x18003723d  mov     qword ptr [rax-20h], 0
0x180037245  call    cs:__imp_CreateFileW
0x18003724b  mov     rdi, rax
0x18003724e  test    rax, rax
0x180037251  jnz     short loc_18003729B
0x180037253  call    cs:__imp_GetLastError
0x180037259  mov     ebx, eax
0x18003725b  test    eax, eax
0x18003725d  jz      short loc_180037270
0x18003725f  jle     short loc_18003726A
0x180037261  movzx   ebx, ax
0x180037264  or      ebx, 80070000h
0x18003726a  test    ebx, ebx
0x18003726c  jns     short loc_1800372A1
0x18003726e  jmp     short loc_180037275
0x180037270  mov     ebx, 80004005h
0x180037275  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18003727c  mov     dword ptr [rsp+68h+lpOverlapped], ebx
0x180037280  xor     r8d, r8d; int
0x180037283  lea     rdx, aWdcfilteredito; "WdcFilterEditorLoadFile"
0x18003728a  lea     rcx, aBaseDiagnosisP_28; "base\\diagnosis\\pdui\\perfmon\\mmc\\di"...
0x180037291  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180037296  jmp     loc_180037326
0x18003729b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003729f  jz      short loc_180037253
0x1800372a1  mov     r8d, [rsi+28h]; nNumberOfBytesToRead
0x1800372a5  lea     r9, [rsi+20h]; lpNumberOfBytesRead
0x1800372a9  mov     rdx, [rsi+38h]; lpBuffer
0x1800372ad  mov     rcx, rdi; hFile
0x1800372b0  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800372b9  call    cs:__imp_ReadFile
0x1800372bf  test    eax, eax
0x1800372c1  jz      short loc_1800372C7
0x1800372c3  xor     ebx, ebx
0x1800372c5  jmp     short loc_1800372E2
0x1800372c7  call    cs:__imp_GetLastError
0x1800372cd  mov     ebx, eax
0x1800372cf  test    eax, eax
0x1800372d1  jz      short loc_1800372EB
0x1800372d3  jle     short loc_1800372DE
0x1800372d5  movzx   ebx, ax
0x1800372d8  or      ebx, 80070000h
0x1800372de  test    ebx, ebx
0x1800372e0  js      short loc_1800372F0
0x1800372e2  mov     dword ptr [rsi+0Ch], 2
0x1800372e9  jmp     short loc_180037313
0x1800372eb  mov     ebx, 80004005h
0x1800372f0  mov     eax, ebx
0x1800372f2  mov     dword ptr [rsp+68h+lpOverlapped], ebx
0x1800372f6  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800372fd  xor     r8d, r8d; int
0x180037300  lea     rdx, aWdcfilteredito; "WdcFilterEditorLoadFile"
0x180037307  lea     rcx, aBaseDiagnosisP_28; "base\\diagnosis\\pdui\\perfmon\\mmc\\di"...
0x18003730e  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180037313  lea     rcx, [rdi-1]
0x180037317  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003731b  ja      short loc_180037326
0x18003731d  mov     rcx, rdi; hObject
0x180037320  call    cs:__imp_CloseHandle
0x180037326  mov     rsi, [rsp+68h+arg_8]
0x18003732b  mov     eax, ebx
0x18003732d  mov     rbx, [rsp+68h+arg_0]
0x180037332  add     rsp, 60h
0x180037336  pop     rdi
0x180037337  retn
```
