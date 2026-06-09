# MakeIniBinding(IPubResource *,INI_OPTIONS *,INI_BINDING *,int)

- ea: `0x180002fd0`
- end: `0x1800031db`
- name: `?MakeIniBinding@@YAJPEAVIPubResource@@PEAUINI_OPTIONS@@PEAUINI_BINDING@@H@Z`
- size: `523`
- prototype: `int __fastcall(struct IPubResource *, struct INI_OPTIONS *, struct INI_BINDING *, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001c30`
- `0x180001cdc`
- `0x180002080`
- `0x180002220`
- `0x180002520`

## callees

- `0x180002fd0`
- `0x180004010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000301e`
- `msvcrt!wcsrchr` at `0x1800030f6`
- `msvcrt!wcsrchr` at `0x18000301e`
- `msvcrt!wcsrchr` at `0x1800030f6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003004`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800030d3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003102`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003004`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800030d3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003102`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003049`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800030a2`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003049`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800030a2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000308a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800030b2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000308a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800030b2`
- `iisutil!?Escape@STRU@@QEAAJXZ` at `0x180003113`
- `iisutil!?Escape@STRU@@QEAAJXZ` at `0x180003113`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000319c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000319c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003172`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003172`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800031b9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800031b9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000306a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000306a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031a5`

## pseudocode

```c
int __fastcall MakeIniBinding(struct IPubResource *a1, struct INI_OPTIONS *a2, struct INI_BINDING *a3, int a4)
{
  const unsigned __int16 *v8; // rax
  int result; // eax
  wchar_t *v10; // rax
  wchar_t *v11; // rdi
  const unsigned __int16 *v12; // rdx
  const WCHAR *v13; // rax
  DWORD FileAttributesW; // eax
  const wchar_t *v15; // rax
  wchar_t *v16; // rax
  const WCHAR *v17; // rcx
  HANDLE FileW; // rax
  void *v19; // rdi
  __int16 Buffer; // [rsp+70h] [rbp+8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  v8 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IPubResource *))(*(_QWORD *)a1 + 16LL))(a1);
  result = STRU::Copy(a3, v8);
  if ( result < 0 )
    return result;
  v10 = wcsrchr(*((const wchar_t **)a3 + 4), 0x5Cu);
  v11 = v10;
  if ( !v10 )
    return -2147024809;
  if ( *(_DWORD *)a2 )
  {
    if ( !v10[1] )
    {
      *v10 = 0;
      STRU::SyncWithBuffer(a3);
    }
    v12 = L":";
LABEL_12:
    result = STRU::Append(a3, v12);
    if ( result < 0 )
      return result;
    goto LABEL_15;
  }
  v13 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IPubResource *))(*(_QWORD *)a1 + 16LL))(a1);
  FileAttributesW = GetFileAttributesW(v13);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    v11[1] = 0;
    STRU::SyncWithBuffer(a3);
  }
  else if ( v11[1] )
  {
    v12 = L"\\";
    goto LABEL_12;
  }
LABEL_15:
  result = STRU::Append(a3, L"properties.dav");
  if ( result < 0 )
    return result;
  if ( *(_DWORD *)a2 )
  {
    result = STRU::Copy((struct INI_BINDING *)((char *)a3 + 56), L"WebDAV");
  }
  else
  {
    v15 = (const wchar_t *)(**(__int64 (__fastcall ***)(struct IPubResource *))a1)(a1);
    v16 = wcsrchr(v15, 0x2Fu);
    result = STRU::Copy((struct INI_BINDING *)((char *)a3 + 56), v16);
    if ( result < 0 )
      return result;
    result = STRU::Escape((struct INI_BINDING *)((char *)a3 + 56));
    if ( result < 0 )
      return result;
    if ( *((_DWORD *)a3 + 26) >= 0x7FBCu )
      result = -2147024888;
  }
  if ( result >= 0 && a4 )
  {
    v17 = (const WCHAR *)*((_QWORD *)a3 + 4);
    Buffer = -257;
    NumberOfBytesWritten = 0;
    FileW = CreateFileW(v17, 0x120116u, 0, 0, 1u, 0x80u, 0);
    v19 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      WriteFile(FileW, &Buffer, 2u, &NumberOfBytesWritten, 0);
      CloseHandle(v19);
    }
    if ( !*(_DWORD *)a2 )
      SetFileAttributesW(*((LPCWSTR *)a3 + 4), 6u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002fd0  mov     [rsp+arg_8], rbx
0x180002fd5  mov     [rsp+arg_18], rbp
0x180002fda  push    rsi
0x180002fdb  push    rdi
0x180002fdc  push    r12
0x180002fde  push    r14
0x180002fe0  push    r15
0x180002fe2  sub     rsp, 40h
0x180002fe6  mov     rax, [rcx]
0x180002fe9  mov     ebp, r9d
0x180002fec  mov     rbx, r8
0x180002fef  mov     rsi, rdx
0x180002ff2  mov     r14, rcx
0x180002ff5  mov     rax, [rax+10h]
0x180002ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ffe  mov     rdx, rax
0x180003001  mov     rcx, rbx
0x180003004  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000300a  xor     r12d, r12d
0x18000300d  test    eax, eax
0x18000300f  js      loc_1800031C2
0x180003015  mov     rcx, [rbx+20h]; Str
0x180003019  lea     edx, [r12+5Ch]; Ch
0x18000301e  call    cs:__imp_wcsrchr
0x180003024  mov     rdi, rax
0x180003027  test    rax, rax
0x18000302a  jnz     short loc_180003036
0x18000302c  mov     eax, 80070057h
0x180003031  jmp     loc_1800031C2
0x180003036  cmp     [rsi], r12d
0x180003039  jz      short loc_180003058
0x18000303b  cmp     [rax+2], r12w
0x180003040  jnz     short loc_18000304F
0x180003042  mov     rcx, rbx
0x180003045  mov     [rax], r12w
0x180003049  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000304f  lea     rdx, asc_180005554; ":"
0x180003056  jmp     short loc_180003087
0x180003058  mov     rax, [r14]
0x18000305b  mov     rcx, r14
0x18000305e  mov     rax, [rax+10h]
0x180003062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003067  mov     rcx, rax; lpFileName
0x18000306a  call    cs:__imp_GetFileAttributesW
0x180003070  cmp     eax, 0FFFFFFFFh
0x180003073  jz      short loc_18000309A
0x180003075  test    al, 10h
0x180003077  jz      short loc_18000309A
0x180003079  cmp     [rdi+2], r12w
0x18000307e  jz      short loc_1800030A8
0x180003080  lea     rdx, asc_180005510; "\\"
0x180003087  mov     rcx, rbx
0x18000308a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180003090  test    eax, eax
0x180003092  js      loc_1800031C2
0x180003098  jmp     short loc_1800030A8
0x18000309a  mov     rcx, rbx
0x18000309d  mov     [rdi+2], r12w
0x1800030a2  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800030a8  lea     rdx, aPropertiesDav; "properties.dav"
0x1800030af  mov     rcx, rbx
0x1800030b2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800030b8  test    eax, eax
0x1800030ba  js      loc_1800031C2
0x1800030c0  lea     rdi, [rbx+38h]
0x1800030c4  cmp     [rsi], r12d
0x1800030c7  jz      short loc_1800030DB
0x1800030c9  lea     rdx, aWebdav; "WebDAV"
0x1800030d0  mov     rcx, rdi
0x1800030d3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800030d9  jmp     short loc_18000312F
0x1800030db  mov     rax, [r14]
0x1800030de  mov     rcx, r14
0x1800030e1  mov     r15d, 2Fh ; '/'
0x1800030e7  mov     rax, [rax]
0x1800030ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ef  mov     rcx, rax; Str
0x1800030f2  movzx   edx, r15w; Ch
0x1800030f6  call    cs:__imp_wcsrchr
0x1800030fc  mov     rdx, rax
0x1800030ff  mov     rcx, rdi
0x180003102  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003108  test    eax, eax
0x18000310a  js      loc_1800031C2
0x180003110  mov     rcx, rdi
0x180003113  call    cs:__imp_?Escape@STRU@@QEAAJXZ; STRU::Escape(void)
0x180003119  test    eax, eax
0x18000311b  js      loc_1800031C2
0x180003121  cmp     dword ptr [rdi+30h], 7FBCh
0x180003128  jb      short loc_18000312F
0x18000312a  mov     eax, 80070008h
0x18000312f  test    eax, eax
0x180003131  js      loc_1800031C2
0x180003137  test    ebp, ebp
0x180003139  jz      loc_1800031C2
0x18000313f  mov     rcx, [rbx+20h]; lpFileName
0x180003143  xor     r9d, r9d; lpSecurityAttributes
0x180003146  mov     [rsp+68h+hTemplateFile], r12; hTemplateFile
0x18000314b  xor     r8d, r8d; dwShareMode
0x18000314e  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180003156  mov     edx, 120116h; dwDesiredAccess
0x18000315b  mov     [rsp+68h+dwCreationDisposition], 1; dwCreationDisposition
0x180003163  mov     [rsp+68h+Buffer], 0FEFFh
0x18000316a  mov     [rsp+68h+NumberOfBytesWritten], r12d
0x180003172  call    cs:__imp_CreateFileW
0x180003178  mov     rdi, rax
0x18000317b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000317f  jz      short loc_1800031AB
0x180003181  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180003189  mov     qword ptr [rsp+68h+dwCreationDisposition], r12; lpOverlapped
0x18000318e  mov     r8d, 2; nNumberOfBytesToWrite
0x180003194  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x180003199  mov     rcx, rax; hFile
0x18000319c  call    cs:__imp_WriteFile
0x1800031a2  mov     rcx, rdi; hObject
0x1800031a5  call    cs:__imp_CloseHandle
0x1800031ab  cmp     [rsi], r12d
0x1800031ae  jnz     short loc_1800031BF
0x1800031b0  mov     rcx, [rbx+20h]; lpFileName
0x1800031b4  mov     edx, 6; dwFileAttributes
0x1800031b9  call    cs:__imp_SetFileAttributesW
0x1800031bf  mov     eax, r12d
0x1800031c2  lea     r11, [rsp+68h+var_28]
0x1800031c7  mov     rbx, [r11+38h]
0x1800031cb  mov     rbp, [r11+48h]
0x1800031cf  mov     rsp, r11
0x1800031d2  pop     r15
0x1800031d4  pop     r14
0x1800031d6  pop     r12
0x1800031d8  pop     rdi
0x1800031d9  pop     rsi
0x1800031da  retn
```
