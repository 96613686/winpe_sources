# Windows::Internal::Security::Authentication::Web::CallerContext::`scalar deleting destructor'(uint)

- ea: `0x18002607c`
- end: `0x180026178`
- name: `??_GCallerContext@Web@Authentication@Security@Internal@Windows@@QEAAPEAXI@Z`
- size: `252`
- prototype: `void *__fastcall(Windows::Internal::Security::Authentication::Web::CallerContext *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024c88`
- `0x18005ecc0`
- `0x18006072c`
- `0x1800abd50`
- `0x1800e1ff0`

## callees

- `0x18002607c`
- `0x18008e6b4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026130`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800260ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026157`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002616d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800260ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026157`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002616d`

## pseudocode

```c
Windows::Internal::Security::Authentication::Web::CallerContext *__fastcall Windows::Internal::Security::Authentication::Web::CallerContext::`scalar deleting destructor'(
        Windows::Internal::Security::Authentication::Web::CallerContext *this,
        char a2)
{
  char *v4; // rcx
  void *v5; // rcx
  char *v6; // rcx
  char *v7; // rcx
  HSTRING v8; // rcx
  HSTRING v9; // rcx
  HSTRING v10; // rcx
  HSTRING v11; // rcx
  HSTRING v12; // rcx
  HSTRING v13; // rcx

  v4 = (char *)*((_QWORD *)this + 39);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 38);
  if ( v5 )
    CloseHandle(v5);
  v6 = (char *)*((_QWORD *)this + 37);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  v7 = (char *)*((_QWORD *)this + 36);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  v8 = (HSTRING)*((_QWORD *)this + 9);
  if ( v8 )
    WindowsDeleteString(v8);
  v9 = (HSTRING)*((_QWORD *)this + 8);
  if ( v9 )
    WindowsDeleteString(v9);
  v10 = (HSTRING)*((_QWORD *)this + 7);
  if ( v10 )
    WindowsDeleteString(v10);
  v11 = (HSTRING)*((_QWORD *)this + 6);
  if ( v11 )
    WindowsDeleteString(v11);
  v12 = (HSTRING)*((_QWORD *)this + 5);
  if ( v12 )
    WindowsDeleteString(v12);
  v13 = (HSTRING)*((_QWORD *)this + 4);
  if ( v13 )
    WindowsDeleteString(v13);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18002607c  mov     [rsp+arg_0], rbx
0x180026081  push    rdi
0x180026082  sub     rsp, 20h
0x180026086  mov     rbx, rcx
0x180026089  mov     edi, edx
0x18002608b  mov     rcx, [rcx+138h]; hObject
0x180026092  lea     rax, [rcx-1]
0x180026096  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002609a  jbe     loc_180026157
0x1800260a0  mov     rcx, [rbx+130h]; hObject
0x1800260a7  test    rcx, rcx
0x1800260aa  jz      short loc_1800260B2
0x1800260ac  call    cs:__imp_CloseHandle
0x1800260b2  mov     rcx, [rbx+128h]; hObject
0x1800260b9  lea     rax, [rcx-1]
0x1800260bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800260c1  jbe     loc_180026162
0x1800260c7  mov     rcx, [rbx+120h]; hObject
0x1800260ce  lea     rax, [rcx-1]
0x1800260d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800260d6  jbe     loc_18002616D
0x1800260dc  mov     rcx, [rbx+48h]; string
0x1800260e0  test    rcx, rcx
0x1800260e3  jz      short loc_1800260EB
0x1800260e5  call    cs:__imp_WindowsDeleteString
0x1800260eb  mov     rcx, [rbx+40h]; string
0x1800260ef  test    rcx, rcx
0x1800260f2  jz      short loc_1800260FA
0x1800260f4  call    cs:__imp_WindowsDeleteString
0x1800260fa  mov     rcx, [rbx+38h]; string
0x1800260fe  test    rcx, rcx
0x180026101  jz      short loc_180026109
0x180026103  call    cs:__imp_WindowsDeleteString
0x180026109  mov     rcx, [rbx+30h]; string
0x18002610d  test    rcx, rcx
0x180026110  jz      short loc_180026118
0x180026112  call    cs:__imp_WindowsDeleteString
0x180026118  mov     rcx, [rbx+28h]; string
0x18002611c  test    rcx, rcx
0x18002611f  jz      short loc_180026127
0x180026121  call    cs:__imp_WindowsDeleteString
0x180026127  mov     rcx, [rbx+20h]; string
0x18002612b  test    rcx, rcx
0x18002612e  jz      short loc_180026136
0x180026130  call    cs:__imp_WindowsDeleteString
0x180026136  test    dil, 1
0x18002613a  jz      short loc_180026149
0x18002613c  mov     edx, 140h
0x180026141  mov     rcx, rbx; Block
0x180026144  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026149  mov     rax, rbx
0x18002614c  mov     rbx, [rsp+28h+arg_0]
0x180026151  add     rsp, 20h
0x180026155  pop     rdi
0x180026156  retn
0x180026157  call    cs:__imp_CloseHandle
0x18002615d  jmp     loc_1800260A0
0x180026162  call    cs:__imp_CloseHandle
0x180026168  jmp     loc_1800260C7
0x18002616d  call    cs:__imp_CloseHandle
0x180026173  jmp     loc_1800260DC
```
