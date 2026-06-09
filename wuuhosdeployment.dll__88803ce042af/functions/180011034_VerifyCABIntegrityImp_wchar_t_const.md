# VerifyCABIntegrityImp(wchar_t const *)

- ea: `0x180011034`
- end: `0x1800111e1`
- name: `?VerifyCABIntegrityImp@@YAJPEB_W@Z`
- size: `429`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, __int64, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180012480`

## callees

- `0x180003950`
- `0x180003974`
- `0x18000b658`
- `0x18000deec`
- `0x180011034`
- `0x180014778`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111b3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180011105`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180011105`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001112e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001112e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180011196`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180011196`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001109f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001109f`

## pseudocode

```c
__int64 __fastcall VerifyCABIntegrityImp(const wchar_t *a1, __int64 a2, __int64 a3, struct _SECURITY_ATTRIBUTES *a4)
{
  HANDLE FileMappingW; // rbx
  unsigned __int8 *v5; // rdi
  void *FileRetryIfSharingViolation; // rax
  const char *v7; // r9
  void *v8; // rbp
  __int64 v9; // rdx
  int LastError; // eax
  DWORD LowPart; // esi
  unsigned __int8 *v12; // rax
  unsigned int v13; // esi
  int Header; // eax
  unsigned int dwMaximumSizeLow; // [rsp+20h] [rbp-68h]
  int dwMaximumSizeLowa; // [rsp+20h] [rbp-68h]
  void *v18; // [rsp+30h] [rbp-58h]
  unsigned int v19; // [rsp+38h] [rbp-50h]
  void *v20; // [rsp+40h] [rbp-48h]
  LARGE_INTEGER FileSize; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  FileMappingW = 0;
  v5 = 0;
  FileSize.QuadPart = 0;
  FileRetryIfSharingViolation = SusCreateFileRetryIfSharingViolation(a1, 0x80000000, 5u, a4, 3u, 0, v18, v19, v20, 0, 0);
  v8 = FileRetryIfSharingViolation;
  if ( FileRetryIfSharingViolation == (void *)-1LL )
  {
    v9 = 181;
LABEL_15:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\wutrust\\lib\\trust.cpp",
                  v7);
    goto LABEL_16;
  }
  if ( !GetFileSizeEx(FileRetryIfSharingViolation, &FileSize) )
  {
    v9 = 184;
    goto LABEL_15;
  }
  if ( !FileSize.QuadPart )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xBE,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\wutrust\\lib\\trust.cpp",
                  (const char *)0xDE,
                  dwMaximumSizeLow);
LABEL_16:
    v13 = LastError;
    goto LABEL_19;
  }
  LowPart = 104;
  if ( FileSize.LowPart < 0x68 )
    LowPart = FileSize.LowPart;
  if ( FileSize.HighPart )
    LowPart = 104;
  FileMappingW = CreateFileMappingW(v8, 0, 2u, 0, LowPart, 0);
  if ( !FileMappingW )
  {
    v9 = 204;
    goto LABEL_15;
  }
  v12 = (unsigned __int8 *)MapViewOfFile(FileMappingW, 4u, 0, 0, LowPart);
  v5 = v12;
  if ( !v12 )
  {
    v9 = 212;
    goto LABEL_15;
  }
  Header = StrictReadHeader(v12, LowPart, FileSize.QuadPart);
  v13 = Header;
  if ( Header < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\wutrust\\lib\\trust.cpp",
      (const char *)(unsigned int)Header,
      dwMaximumSizeLowa);
LABEL_19:
    if ( !v5 )
      goto LABEL_23;
    goto LABEL_22;
  }
  v13 = 0;
LABEL_22:
  UnmapViewOfFile(v5);
LABEL_23:
  if ( FileMappingW )
    CloseHandle(FileMappingW);
  if ( v8 != (void *)-1LL )
    CloseHandle(v8);
  return v13;
}

```

## disassembly

```asm
0x180011034  mov     r11, rsp
0x180011037  mov     [r11+10h], rbx
0x18001103b  mov     [r11+18h], rbp
0x18001103f  mov     [r11+20h], rsi
0x180011043  push    rdi
0x180011044  sub     rsp, 80h
0x18001104b  mov     rax, cs:__security_cookie
0x180011052  xor     rax, rsp
0x180011055  mov     [rsp+88h+var_18], rax
0x18001105a  xor     ebx, ebx
0x18001105c  mov     edx, 80000000h; dwDesiredAccess
0x180011061  mov     [rsp+88h+var_38], ebx; unsigned int
0x180011065  xor     edi, edi
0x180011067  mov     [rsp+88h+var_40], ebx; int
0x18001106b  mov     dword ptr [rsp+88h+lpName], ebx; DWORD
0x18001106f  lea     r8d, [rbx+5]; dwShareMode
0x180011073  mov     [r11-20h], rbx
0x180011077  mov     [rsp+88h+dwMaximumSizeLow], 3; unsigned int
0x18001107f  call    ?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z; SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)
0x180011084  mov     rbp, rax
0x180011087  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001108b  jnz     short loc_180011097
0x18001108d  mov     edx, 0B5h
0x180011092  jmp     loc_180011141
0x180011097  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x18001109c  mov     rcx, rbp; hFile
0x18001109f  call    cs:__imp_GetFileSizeEx
0x1800110a5  test    eax, eax
0x1800110a7  jnz     short loc_1800110B3
0x1800110a9  mov     edx, 0B8h
0x1800110ae  jmp     loc_180011141
0x1800110b3  mov     rax, qword ptr [rsp+88h+FileSize]
0x1800110b8  test    rax, rax
0x1800110bb  jnz     short loc_1800110DD
0x1800110bd  mov     rcx, [rsp+88h]; this
0x1800110c5  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x1800110cc  mov     r9d, 0DEh; char *
0x1800110d2  lea     edx, [r9-20h]; void *
0x1800110d6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800110db  jmp     short loc_180011155
0x1800110dd  mov     ecx, 68h ; 'h'
0x1800110e2  mov     [rsp+88h+lpName], rbx; lpName
0x1800110e7  cmp     eax, ecx
0x1800110e9  mov     esi, ecx
0x1800110eb  cmovb   esi, eax
0x1800110ee  cmp     dword ptr [rsp+88h+FileSize+4], ebx
0x1800110f2  lea     r8d, [rcx-66h]; flProtect
0x1800110f6  cmovnz  esi, ecx
0x1800110f9  xor     r9d, r9d; dwMaximumSizeHigh
0x1800110fc  xor     edx, edx; lpFileMappingAttributes
0x1800110fe  mov     [rsp+88h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x180011102  mov     rcx, rbp; hFile
0x180011105  call    cs:__imp_CreateFileMappingW
0x18001110b  mov     rbx, rax
0x18001110e  test    rax, rax
0x180011111  jnz     short loc_18001111A
0x180011113  mov     edx, 0CCh
0x180011118  jmp     short loc_180011141
0x18001111a  xor     r9d, r9d; dwFileOffsetLow
0x18001111d  mov     eax, esi
0x18001111f  xor     r8d, r8d; dwFileOffsetHigh
0x180011122  mov     qword ptr [rsp+88h+dwMaximumSizeLow], rax; int
0x180011127  mov     rcx, rbx; hFileMappingObject
0x18001112a  lea     edx, [r9+4]; dwDesiredAccess
0x18001112e  call    cs:__imp_MapViewOfFile
0x180011134  mov     rdi, rax
0x180011137  test    rax, rax
0x18001113a  jnz     short loc_180011159
0x18001113c  mov     edx, 0D4h; void *
0x180011141  mov     rcx, [rsp+88h]; this
0x180011149  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x180011150  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011155  mov     esi, eax
0x180011157  jmp     short loc_18001118A
0x180011159  mov     r8, qword ptr [rsp+88h+FileSize]; __int64
0x18001115e  mov     edx, esi; unsigned int
0x180011160  mov     rcx, rax; unsigned __int8 *
0x180011163  call    ?StrictReadHeader@@YAJQEAEK_J@Z; StrictReadHeader(uchar * const,ulong,__int64)
0x180011168  mov     esi, eax
0x18001116a  test    eax, eax
0x18001116c  jns     short loc_180011191
0x18001116e  mov     rcx, [rsp+88h]; this
0x180011176  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x18001117d  mov     r9d, eax; char *
0x180011180  mov     edx, 0D6h; void *
0x180011185  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001118a  test    rdi, rdi
0x18001118d  jz      short loc_18001119C
0x18001118f  jmp     short loc_180011193
0x180011191  xor     esi, esi
0x180011193  mov     rcx, rdi; lpBaseAddress
0x180011196  call    cs:__imp_UnmapViewOfFile
0x18001119c  test    rbx, rbx
0x18001119f  jz      short loc_1800111AA
0x1800111a1  mov     rcx, rbx; hObject
0x1800111a4  call    cs:__imp_CloseHandle
0x1800111aa  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800111ae  jz      short loc_1800111B9
0x1800111b0  mov     rcx, rbp; hObject
0x1800111b3  call    cs:__imp_CloseHandle
0x1800111b9  mov     eax, esi
0x1800111bb  mov     rcx, [rsp+88h+var_18]
0x1800111c0  xor     rcx, rsp; StackCookie
0x1800111c3  call    __security_check_cookie
0x1800111c8  lea     r11, [rsp+88h+var_8]
0x1800111d0  mov     rbx, [r11+18h]
0x1800111d4  mov     rbp, [r11+20h]
0x1800111d8  mov     rsi, [r11+28h]
0x1800111dc  mov     rsp, r11
0x1800111df  pop     rdi
0x1800111e0  retn
```
