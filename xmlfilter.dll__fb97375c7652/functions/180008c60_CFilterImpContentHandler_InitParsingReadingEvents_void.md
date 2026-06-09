# CFilterImpContentHandler::InitParsingReadingEvents(void)

- ea: `0x180008c60`
- end: `0x180008d87`
- name: `?InitParsingReadingEvents@CFilterImpContentHandler@@QEAAJXZ`
- size: `295`
- prototype: `__int64 __fastcall(CFilterImpContentHandler *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800060c0`

## callees

- `0x180008c60`
- `0x18000b744`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d56`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180008cb4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180008d44`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180008cb4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180008d44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d1e`

## string_xrefs

- `0x180008ce5`: `onecoreuap\base\appmodel\search\filters\xml\FilterImpContentHandler.h`

## pseudocode

```c
__int64 __fastcall CFilterImpContentHandler::InitParsingReadingEvents(CFilterImpContentHandler *this)
{
  char *v1; // rsi
  DWORD LastError; // ebx
  HANDLE Event; // rax
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  char *v9; // rsi
  DWORD v10; // ebx
  HANDLE v11; // rax
  signed int v12; // eax
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (char *)*((_QWORD *)this + 51);
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v1);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 51) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)this + 51) = Event;
  if ( Event )
  {
    v9 = (char *)*((_QWORD *)this + 52);
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v10 = GetLastError();
      CloseHandle(v9);
      SetLastError(v10);
    }
    *((_QWORD *)this + 52) = 0;
    v11 = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)this + 52) = v11;
    if ( v11 )
      return 0;
    v12 = GetLastError();
    v6 = v12;
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    v7 = 71;
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = 69;
  }
  if ( (v6 & 0x80000000) == 0 )
    v6 = -2147467259;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\FilterImpContentHandler.h",
    (const char *)v6,
    v13);
  return v6;
}

```

## disassembly

```asm
0x180008c60  mov     [rsp+arg_0], rbx
0x180008c65  mov     [rsp+arg_8], rsi
0x180008c6a  push    rdi; int
0x180008c6b  sub     rsp, 20h
0x180008c6f  mov     rsi, [rcx+198h]
0x180008c76  mov     rdi, rcx
0x180008c79  lea     rax, [rsi-1]
0x180008c7d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008c81  ja      short loc_180008C9C
0x180008c83  call    cs:__imp_GetLastError
0x180008c89  mov     rcx, rsi; hObject
0x180008c8c  mov     ebx, eax
0x180008c8e  call    cs:__imp_CloseHandle
0x180008c94  mov     ecx, ebx; dwErrCode
0x180008c96  call    cs:__imp_SetLastError
0x180008c9c  mov     r9d, 1F0003h; dwDesiredAccess
0x180008ca2  mov     qword ptr [rdi+198h], 0
0x180008cad  xor     r8d, r8d; dwFlags
0x180008cb0  xor     edx, edx; lpName
0x180008cb2  xor     ecx, ecx; lpEventAttributes
0x180008cb4  call    cs:__imp_CreateEventExW
0x180008cba  mov     [rdi+198h], rax
0x180008cc1  test    rax, rax
0x180008cc4  jnz     short loc_180008D02
0x180008cc6  call    cs:__imp_GetLastError
0x180008ccc  mov     ebx, eax
0x180008cce  test    eax, eax
0x180008cd0  jle     short loc_180008CDB
0x180008cd2  movzx   ebx, ax
0x180008cd5  or      ebx, 80070000h
0x180008cdb  mov     edx, 45h ; 'E'; void *
0x180008ce0  mov     rcx, [rsp+28h]; this
0x180008ce5  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180008cec  test    ebx, ebx
0x180008cee  mov     eax, 80004005h
0x180008cf3  cmovns  ebx, eax
0x180008cf6  mov     r9d, ebx; char *
0x180008cf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cfe  mov     eax, ebx
0x180008d00  jmp     short loc_180008D77
0x180008d02  mov     rsi, [rdi+1A0h]
0x180008d09  lea     rax, [rsi-1]
0x180008d0d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008d11  ja      short loc_180008D2C
0x180008d13  call    cs:__imp_GetLastError
0x180008d19  mov     rcx, rsi; hObject
0x180008d1c  mov     ebx, eax
0x180008d1e  call    cs:__imp_CloseHandle
0x180008d24  mov     ecx, ebx; dwErrCode
0x180008d26  call    cs:__imp_SetLastError
0x180008d2c  mov     r9d, 1F0003h; dwDesiredAccess
0x180008d32  mov     qword ptr [rdi+1A0h], 0
0x180008d3d  xor     r8d, r8d; dwFlags
0x180008d40  xor     edx, edx; lpName
0x180008d42  xor     ecx, ecx; lpEventAttributes
0x180008d44  call    cs:__imp_CreateEventExW
0x180008d4a  mov     [rdi+1A0h], rax
0x180008d51  test    rax, rax
0x180008d54  jnz     short loc_180008D75
0x180008d56  call    cs:__imp_GetLastError
0x180008d5c  mov     ebx, eax
0x180008d5e  test    eax, eax
0x180008d60  jle     short loc_180008D6B
0x180008d62  movzx   ebx, ax
0x180008d65  or      ebx, 80070000h
0x180008d6b  mov     edx, 47h ; 'G'
0x180008d70  jmp     loc_180008CE0
0x180008d75  xor     eax, eax
0x180008d77  mov     rbx, [rsp+28h+arg_0]
0x180008d7c  mov     rsi, [rsp+28h+arg_8]
0x180008d81  add     rsp, 20h
0x180008d85  pop     rdi
0x180008d86  retn
```
