# DhcpCompletionContext::Initialize(ulong)

- ea: `0x18000963c`
- end: `0x1800097c2`
- name: `?Initialize@DhcpCompletionContext@@QEAAJK@Z`
- size: `390`
- prototype: `int(DhcpCompletionContext *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009c2c`

## callees

- `0x180009408`
- `0x180009540`
- `0x18000963c`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800096b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800096b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009703`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009703`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x18000969c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x18000969c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000973e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000973e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009711`

## pseudocode

```c
__int64 __fastcall DhcpCompletionContext::Initialize(DhcpCompletionContext *this, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v5; // r14d
  signed int v6; // edi
  HANDLE Event; // rbx
  signed int LastError; // eax
  struct DhcpResultInfoList *v10; // [rsp+20h] [rbp-28h] BYREF
  int v11; // [rsp+2Ch] [rbp-1Ch]

  v11 = 0;
  v10 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v5 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 10, WPP_23704f1b4e2e3e34f275fa2c63adb185_Traceguids, a2, v10);
  v6 = CreateDhcpResultInfoList(a2, &v10);
  if ( v6 < 0 )
  {
    v11 = 179;
    goto LABEL_9;
  }
  Event = CreateEventExA(0, 0, 1u, 0x100002u);
  if ( Event )
  {
    if ( v4 )
    {
      EnterCriticalSection(v4);
      v5 = 1;
    }
    if ( !*((_DWORD *)this + 3) )
    {
      v6 = 0;
      *((_QWORD *)this + 8) = v10;
      v10 = 0;
      *((_QWORD *)this + 7) = Event;
      *((_DWORD *)this + 3) = 1;
LABEL_9:
      Event = 0;
      goto LABEL_10;
    }
    v6 = -2147024809;
    v11 = 186;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v11 = 182;
    if ( v6 >= 0 )
      v6 = -2147418113;
  }
LABEL_10:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 11, WPP_23704f1b4e2e3e34f275fa2c63adb185_Traceguids, (unsigned int)v6, v10);
  if ( v5 && v4 )
    LeaveCriticalSection(v4);
  if ( Event )
    CloseHandle(Event);
  if ( v10 )
    FreeDhcpResultInfoList(&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000963c  mov     [rsp+arg_10], rbx
0x180009641  mov     [rsp+arg_18], rbp
0x180009646  push    rsi
0x180009647  push    rdi
0x180009648  push    r14
0x18000964a  sub     rsp, 30h
0x18000964e  mov     ebx, edx
0x180009650  mov     [rsp+48h+var_1C], 0
0x180009658  mov     rbp, rcx
0x18000965b  mov     [rsp+48h+var_28], 0
0x180009664  lea     rsi, [rcx+10h]
0x180009668  xor     r14d, r14d
0x18000966b  test    byte ptr cs:xmmword_180107A60, 20h
0x180009672  jnz     loc_180009786
0x180009678  lea     rdx, [rsp+48h+var_28]; struct DhcpResultInfoList **
0x18000967d  mov     ecx, ebx; unsigned int
0x18000967f  call    ?CreateDhcpResultInfoList@@YAJKPEAPEAUDhcpResultInfoList@@@Z; CreateDhcpResultInfoList(ulong,DhcpResultInfoList * *)
0x180009684  mov     edi, eax
0x180009686  test    eax, eax
0x180009688  js      loc_180009779
0x18000968e  xor     edx, edx; lpName
0x180009690  xor     ecx, ecx; lpEventAttributes
0x180009692  mov     r9d, 100002h; dwDesiredAccess
0x180009698  lea     r8d, [rdx+1]; dwFlags
0x18000969c  call    cs:__imp_CreateEventExA
0x1800096a2  mov     rbx, rax
0x1800096a5  test    rax, rax
0x1800096a8  jz      loc_18000973E
0x1800096ae  test    rsi, rsi
0x1800096b1  jz      short loc_1800096C2
0x1800096b3  mov     rcx, rsi; lpCriticalSection
0x1800096b6  call    cs:__imp_EnterCriticalSection
0x1800096bc  mov     r14d, 1
0x1800096c2  cmp     dword ptr [rbp+0Ch], 0
0x1800096c6  jnz     loc_180009767
0x1800096cc  mov     rax, [rsp+48h+var_28]
0x1800096d1  xor     edi, edi
0x1800096d3  mov     [rbp+40h], rax
0x1800096d7  mov     [rsp+48h+var_28], rdi
0x1800096dc  mov     [rbp+38h], rbx
0x1800096e0  mov     dword ptr [rbp+0Ch], 1
0x1800096e7  xor     ebx, ebx
0x1800096e9  test    byte ptr cs:xmmword_180107A60, 20h
0x1800096f0  jnz     loc_1800097A4
0x1800096f6  test    r14d, r14d
0x1800096f9  jz      short loc_180009709
0x1800096fb  test    rsi, rsi
0x1800096fe  jz      short loc_180009709
0x180009700  mov     rcx, rsi; lpCriticalSection
0x180009703  call    cs:__imp_LeaveCriticalSection
0x180009709  test    rbx, rbx
0x18000970c  jz      short loc_180009717
0x18000970e  mov     rcx, rbx; hObject
0x180009711  call    cs:__imp_CloseHandle
0x180009717  cmp     [rsp+48h+var_28], 0
0x18000971d  jz      short loc_180009729
0x18000971f  lea     rcx, [rsp+48h+var_28]; struct DhcpResultInfoList **
0x180009724  call    ?FreeDhcpResultInfoList@@YAXPEAPEAUDhcpResultInfoList@@@Z; FreeDhcpResultInfoList(DhcpResultInfoList * *)
0x180009729  mov     rbx, [rsp+48h+arg_10]
0x18000972e  mov     eax, edi
0x180009730  mov     rbp, [rsp+48h+arg_18]
0x180009735  add     rsp, 30h
0x180009739  pop     r14
0x18000973b  pop     rdi
0x18000973c  pop     rsi
0x18000973d  retn
0x18000973e  call    cs:__imp_GetLastError
0x180009744  mov     edi, eax
0x180009746  test    eax, eax
0x180009748  jle     short loc_180009753
0x18000974a  movzx   edi, ax
0x18000974d  or      edi, 80070000h
0x180009753  test    edi, edi
0x180009755  mov     [rsp+48h+var_1C], 0B6h
0x18000975d  mov     eax, 8000FFFFh
0x180009762  cmovns  edi, eax
0x180009765  jmp     short loc_1800096E9
0x180009767  mov     edi, 80070057h
0x18000976c  mov     [rsp+48h+var_1C], 0BAh
0x180009774  jmp     loc_1800096E9
0x180009779  mov     [rsp+48h+var_1C], 0B3h
0x180009781  jmp     loc_1800096E7
0x180009786  mov     edx, 0Ah
0x18000978b  lea     r8, WPP_23704f1b4e2e3e34f275fa2c63adb185_Traceguids
0x180009792  mov     ecx, 405h
0x180009797  mov     r9d, ebx
0x18000979a  call    WPP_SF_d
0x18000979f  jmp     loc_180009678
0x1800097a4  mov     edx, 0Bh
0x1800097a9  lea     r8, WPP_23704f1b4e2e3e34f275fa2c63adb185_Traceguids
0x1800097b0  mov     ecx, 405h
0x1800097b5  mov     r9d, edi
0x1800097b8  call    WPP_SF_d
0x1800097bd  jmp     loc_1800096F6
```
