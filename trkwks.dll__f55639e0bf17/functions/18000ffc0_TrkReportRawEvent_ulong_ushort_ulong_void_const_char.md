# TrkReportRawEvent(ulong,ushort,ulong,void const *,char *)

- ea: `0x18000ffc0`
- end: `0x1800100ea`
- name: `?TrkReportRawEvent@@YAJKGKPEBXPEAD@Z`
- size: `298`
- prototype: `__int64 __fastcall(DWORD dwEventID, WORD, DWORD, void *, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cef8`
- `0x1800100f0`

## callees

- `0x18000ffc0`
- `0x180010fca`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100b5`
- `ADVAPI32!DeregisterEventSource` at `0x1800100a7`
- `ADVAPI32!DeregisterEventSource` at `0x1800100a7`
- `ADVAPI32!RegisterEventSourceW` at `0x180010032`
- `ADVAPI32!RegisterEventSourceW` at `0x180010032`
- `ADVAPI32!ReportEventW` at `0x180010084`
- `ADVAPI32!ReportEventW` at `0x180010084`

## string_xrefs

- `0x180010029`: `Distributed Link Tracking Client`

## pseudocode

```c
__int64 __fastcall TrkReportRawEvent(DWORD dwEventID, WORD a2, DWORD a3, void *a4, char *a5)
{
  WORD wNumStrings; // di
  __int64 v11; // rcx
  HANDLE v12; // rsi
  signed int v13; // eax
  unsigned int v14; // ebx
  signed int LastError; // eax
  signed int v16; // eax
  LPCWSTR Strings[100]; // [rsp+50h] [rbp-368h] BYREF

  memset_0(Strings, 0, sizeof(Strings));
  for ( wNumStrings = 0; wNumStrings < 0x64u; ++wNumStrings )
  {
    v11 = *(_QWORD *)a5;
    Strings[wNumStrings] = *(LPCWSTR *)a5;
    if ( !v11 )
      break;
    a5 += 8;
  }
  v12 = RegisterEventSourceW(0, L"Distributed Link Tracking Client");
  if ( v12 )
  {
    v14 = 0;
    if ( !ReportEventW(v12, a2, 0, dwEventID, 0, wNumStrings, a3, Strings, a4) )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( !DeregisterEventSource(v12) && !v14 )
    {
      v16 = GetLastError();
      v14 = v16;
      if ( v16 > 0 )
        return (unsigned __int16)v16 | 0x80070000;
    }
  }
  else
  {
    v13 = GetLastError();
    v14 = v13;
    if ( v13 > 0 )
      return (unsigned __int16)v13 | 0x80070000;
  }
  return v14;
}

```

## disassembly

```asm
0x18000ffc0  push    rbx
0x18000ffc2  push    rbp
0x18000ffc3  push    rsi
0x18000ffc4  push    rdi
0x18000ffc5  push    r12
0x18000ffc7  push    r14
0x18000ffc9  push    r15
0x18000ffcb  sub     rsp, 380h
0x18000ffd2  mov     rax, cs:__security_cookie
0x18000ffd9  xor     rax, rsp
0x18000ffdc  mov     [rsp+3B8h+var_48], rax
0x18000ffe4  mov     r15d, r8d
0x18000ffe7  movzx   r14d, dx
0x18000ffeb  mov     ebp, ecx
0x18000ffed  xor     edx, edx; Val
0x18000ffef  mov     r8d, 320h; Size
0x18000fff5  lea     rcx, [rsp+3B8h+Strings]; void *
0x18000fffa  mov     r12, r9
0x18000fffd  call    memset_0
0x180010002  mov     rdx, [rsp+3B8h+arg_20]
0x18001000a  xor     edi, edi
0x18001000c  mov     rcx, [rdx]
0x18001000f  movzx   eax, di
0x180010012  mov     [rsp+rax*8+3B8h+Strings], rcx
0x180010017  test    rcx, rcx
0x18001001a  jz      short loc_180010029
0x18001001c  add     rdx, 8
0x180010020  inc     di
0x180010023  cmp     di, 64h ; 'd'
0x180010027  jb      short loc_18001000C
0x180010029  lea     rdx, SourceName; "Distributed Link Tracking Client"
0x180010030  xor     ecx, ecx; lpUNCServerName
0x180010032  call    cs:__imp_RegisterEventSourceW
0x180010038  mov     rsi, rax
0x18001003b  test    rax, rax
0x18001003e  jnz     short loc_180010057
0x180010040  call    cs:__imp_GetLastError
0x180010046  mov     ebx, eax
0x180010048  test    eax, eax
0x18001004a  jle     short loc_1800100C6
0x18001004c  movzx   ebx, ax
0x18001004f  or      ebx, 80070000h
0x180010055  jmp     short loc_1800100C6
0x180010057  mov     [rsp+3B8h+lpRawData], r12; lpRawData
0x18001005c  lea     rax, [rsp+3B8h+Strings]
0x180010061  mov     [rsp+3B8h+lpStrings], rax; lpStrings
0x180010066  xor     ebx, ebx
0x180010068  mov     [rsp+3B8h+dwDataSize], r15d; dwDataSize
0x18001006d  xor     r8d, r8d; wCategory
0x180010070  mov     [rsp+3B8h+wNumStrings], di; wNumStrings
0x180010075  mov     r9d, ebp; dwEventID
0x180010078  movzx   edx, r14w; wType
0x18001007c  mov     [rsp+3B8h+lpUserSid], rbx; lpUserSid
0x180010081  mov     rcx, rsi; hEventLog
0x180010084  call    cs:__imp_ReportEventW
0x18001008a  mov     edi, 80070000h
0x18001008f  test    eax, eax
0x180010091  jnz     short loc_1800100A4
0x180010093  call    cs:__imp_GetLastError
0x180010099  mov     ebx, eax
0x18001009b  test    eax, eax
0x18001009d  jle     short loc_1800100A4
0x18001009f  movzx   ebx, ax
0x1800100a2  or      ebx, edi
0x1800100a4  mov     rcx, rsi; hEventLog
0x1800100a7  call    cs:__imp_DeregisterEventSource
0x1800100ad  test    eax, eax
0x1800100af  jnz     short loc_1800100C6
0x1800100b1  test    ebx, ebx
0x1800100b3  jnz     short loc_1800100C6
0x1800100b5  call    cs:__imp_GetLastError
0x1800100bb  mov     ebx, eax
0x1800100bd  test    eax, eax
0x1800100bf  jle     short loc_1800100C6
0x1800100c1  movzx   ebx, ax
0x1800100c4  or      ebx, edi
0x1800100c6  mov     eax, ebx
0x1800100c8  mov     rcx, [rsp+3B8h+var_48]
0x1800100d0  xor     rcx, rsp; StackCookie
0x1800100d3  call    __security_check_cookie
0x1800100d8  add     rsp, 380h
0x1800100df  pop     r15
0x1800100e1  pop     r14
0x1800100e3  pop     r12
0x1800100e5  pop     rdi
0x1800100e6  pop     rsi
0x1800100e7  pop     rbp
0x1800100e8  pop     rbx
0x1800100e9  retn
```
