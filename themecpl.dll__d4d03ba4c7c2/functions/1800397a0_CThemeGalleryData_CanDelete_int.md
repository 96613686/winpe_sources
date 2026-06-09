# CThemeGalleryData::CanDelete(int)

- ea: `0x1800397a0`
- end: `0x180039889`
- name: `?CanDelete@CThemeGalleryData@@UEAA_NH@Z`
- size: `233`
- prototype: `char __fastcall(HDPA *this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800397a0`
- `0x18005501c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039860`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039850`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039850`
- `OLEAUT32!__imp_SysFreeString` at `0x180039872`
- `OLEAUT32!__imp_SysFreeString` at `0x180039872`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003983b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003983b`

## pseudocode

```c
char __fastcall CThemeGalleryData::CanDelete(HDPA *this, unsigned int a2)
{
  INT_PTR v2; // rsi
  char v4; // bl
  PVOID Ptr; // rax
  HANDLE FileW; // rax
  int v8; // [rsp+60h] [rbp+8h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp+20h] BYREF

  v2 = (int)a2;
  v4 = 0;
  v8 = 0;
  (*((void (__fastcall **)(HDPA *, _QWORD, int *))*this + 15))(this, a2, &v8);
  if ( (v8 & 0xFFFFFFFD) == 0 )
  {
    Ptr = DPA_GetPtr(this[1], v2);
    lpFileName = 0;
    if ( Ptr
      && (*(int (__fastcall **)(PVOID, __int64, LPCWSTR *))(*(_QWORD *)Ptr + 288LL))(Ptr, 0xFFFFFFFFLL, &lpFileName) >= 0 )
    {
      FileW = CreateFileW(lpFileName, 0x10000u, 7u, 0, 3u, 0x2000000u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        GetLastError();
      }
      else
      {
        CloseHandle(FileW);
        v4 = 1;
      }
    }
    SysFreeString((BSTR)lpFileName);
  }
  return v4;
}

```

## disassembly

```asm
0x1800397a0  push    rbx
0x1800397a2  push    rsi
0x1800397a3  push    rdi
0x1800397a4  sub     rsp, 40h
0x1800397a8  movsxd  rsi, edx
0x1800397ab  mov     rdi, rcx
0x1800397ae  xor     bl, bl
0x1800397b0  mov     [rsp+58h+arg_0], 0
0x1800397b8  mov     rax, [rcx]
0x1800397bb  lea     r8, [rsp+58h+arg_0]
0x1800397c0  mov     edx, esi
0x1800397c2  mov     rax, [rax+78h]
0x1800397c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397cb  test    [rsp+58h+arg_0], 0FFFFFFFDh
0x1800397d3  jnz     loc_18003987E
0x1800397d9  mov     rdx, rsi; i
0x1800397dc  mov     rcx, [rdi+8]; hdpa
0x1800397e0  call    DPA_GetPtr
0x1800397e5  mov     rcx, rax
0x1800397e8  mov     [rsp+58h+lpFileName], 0
0x1800397f1  test    rax, rax
0x1800397f4  jz      short loc_18003986D
0x1800397f6  mov     rax, [rax]
0x1800397f9  or      edx, 0FFFFFFFFh
0x1800397fc  lea     r8, [rsp+58h+lpFileName]
0x180039801  mov     rax, [rax+120h]
0x180039808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003980d  test    eax, eax
0x18003980f  js      short loc_18003986D
0x180039811  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18003981a  mov     [rsp+58h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180039822  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18003982a  xor     r9d, r9d; lpSecurityAttributes
0x18003982d  mov     edx, 10000h; dwDesiredAccess
0x180039832  lea     r8d, [r9+7]; dwShareMode
0x180039836  mov     rcx, [rsp+58h+lpFileName]; lpFileName
0x18003983b  call    cs:__imp_CreateFileW
0x180039842  nop     dword ptr [rax+rax+00h]
0x180039847  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003984b  jz      short loc_180039860
0x18003984d  mov     rcx, rax; hObject
0x180039850  call    cs:__imp_CloseHandle
0x180039857  nop     dword ptr [rax+rax+00h]
0x18003985c  mov     bl, 1
0x18003985e  jmp     short loc_18003986D
0x180039860  call    cs:__imp_GetLastError
0x180039867  nop     dword ptr [rax+rax+00h]
0x18003986c  nop
0x18003986d  mov     rcx, [rsp+58h+lpFileName]; bstrString
0x180039872  call    cs:__imp_SysFreeString
0x180039879  nop     dword ptr [rax+rax+00h]
0x18003987e  mov     al, bl
0x180039880  add     rsp, 40h
0x180039884  pop     rdi
0x180039885  pop     rsi
0x180039886  pop     rbx
0x180039887  retn
```
