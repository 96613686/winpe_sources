# Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext(void)

- ea: `0x18001ffdc`
- end: `0x1800200ac`
- name: `??1CallerContext@Web@Authentication@Security@Internal@Windows@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(Windows::Internal::Security::Authentication::Web::CallerContext *__hidden this)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008130`
- `0x180008730`
- `0x180009f40`
- `0x18001ee10`
- `0x180020840`
- `0x180020d90`
- `0x18005ed54`
- `0x180065dc0`
- `0x18008110c`
- `0x1800c2180`
- `0x18011410e`
- `0x1801141b0`
- `0x1801143e0`
- `0x1801162fa`
- `0x180116620`

## callees

- `0x18001ffdc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020037`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020064`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020073`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020082`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020037`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020064`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020073`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020082`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002008e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800200a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002008e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800200a4`

## pseudocode

```c
void __fastcall Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext(
        Windows::Internal::Security::Authentication::Web::CallerContext *this)
{
  char *v2; // rcx
  void *v3; // rcx
  char *v4; // rcx
  char *v5; // rcx
  HSTRING v6; // rcx
  HSTRING v7; // rcx
  HSTRING v8; // rcx
  HSTRING v9; // rcx
  HSTRING v10; // rcx
  HSTRING v11; // rcx

  v2 = (char *)*((_QWORD *)this + 39);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 38);
  if ( v3 )
    CloseHandle(v3);
  v4 = (char *)*((_QWORD *)this + 37);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = (char *)*((_QWORD *)this + 36);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  v6 = (HSTRING)*((_QWORD *)this + 9);
  if ( v6 )
    WindowsDeleteString(v6);
  v7 = (HSTRING)*((_QWORD *)this + 8);
  if ( v7 )
    WindowsDeleteString(v7);
  v8 = (HSTRING)*((_QWORD *)this + 7);
  if ( v8 )
    WindowsDeleteString(v8);
  v9 = (HSTRING)*((_QWORD *)this + 6);
  if ( v9 )
    WindowsDeleteString(v9);
  v10 = (HSTRING)*((_QWORD *)this + 5);
  if ( v10 )
    WindowsDeleteString(v10);
  v11 = (HSTRING)*((_QWORD *)this + 4);
  if ( v11 )
    WindowsDeleteString(v11);
}

```

## disassembly

```asm
0x18001ffdc  push    rbx
0x18001ffde  sub     rsp, 20h
0x18001ffe2  mov     rbx, rcx
0x18001ffe5  mov     rcx, [rcx+138h]; hObject
0x18001ffec  lea     rax, [rcx-1]
0x18001fff0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001fff4  jbe     loc_18002008E
0x18001fffa  mov     rcx, [rbx+130h]; hObject
0x180020001  test    rcx, rcx
0x180020004  jz      short loc_18002000C
0x180020006  call    cs:__imp_CloseHandle
0x18002000c  mov     rcx, [rbx+128h]; hObject
0x180020013  lea     rax, [rcx-1]
0x180020017  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002001b  jbe     short loc_180020099
0x18002001d  mov     rcx, [rbx+120h]; hObject
0x180020024  lea     rax, [rcx-1]
0x180020028  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002002c  jbe     short loc_1800200A4
0x18002002e  mov     rcx, [rbx+48h]; string
0x180020032  test    rcx, rcx
0x180020035  jz      short loc_18002003D
0x180020037  call    cs:__imp_WindowsDeleteString
0x18002003d  mov     rcx, [rbx+40h]; string
0x180020041  test    rcx, rcx
0x180020044  jz      short loc_18002004C
0x180020046  call    cs:__imp_WindowsDeleteString
0x18002004c  mov     rcx, [rbx+38h]; string
0x180020050  test    rcx, rcx
0x180020053  jz      short loc_18002005B
0x180020055  call    cs:__imp_WindowsDeleteString
0x18002005b  mov     rcx, [rbx+30h]; string
0x18002005f  test    rcx, rcx
0x180020062  jz      short loc_18002006A
0x180020064  call    cs:__imp_WindowsDeleteString
0x18002006a  mov     rcx, [rbx+28h]; string
0x18002006e  test    rcx, rcx
0x180020071  jz      short loc_180020079
0x180020073  call    cs:__imp_WindowsDeleteString
0x180020079  mov     rcx, [rbx+20h]; string
0x18002007d  test    rcx, rcx
0x180020080  jz      short loc_180020088
0x180020082  call    cs:__imp_WindowsDeleteString
0x180020088  add     rsp, 20h
0x18002008c  pop     rbx
0x18002008d  retn
0x18002008e  call    cs:__imp_CloseHandle
0x180020094  jmp     loc_18001FFFA
0x180020099  call    cs:__imp_CloseHandle
0x18002009f  jmp     loc_18002001D
0x1800200a4  call    cs:__imp_CloseHandle
0x1800200aa  jmp     short loc_18002002E
```
