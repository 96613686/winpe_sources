# XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)

- ea: `0x180019f5c`
- end: `0x18001a222`
- name: `?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z`
- size: `710`
- prototype: `int(XPerfCore::CFileMapping *__hidden this, const unsigned __int16 *, bool, struct XPerfCore::IErrorMessage *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180016698`
- `0x18003085c`

## callees

- `0x180019f5c`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a04e`
- `KERNEL32!GetLastError` at `0x18001a06f`
- `KERNEL32!GetLastError` at `0x18001a0d8`
- `KERNEL32!GetLastError` at `0x18001a18f`
- `KERNEL32!GetLastError` at `0x18001a04e`
- `KERNEL32!GetLastError` at `0x18001a06f`
- `KERNEL32!GetLastError` at `0x18001a0d8`
- `KERNEL32!GetLastError` at `0x18001a18f`
- `KERNEL32!CloseHandle` at `0x18001a11b`
- `KERNEL32!CloseHandle` at `0x18001a138`
- `KERNEL32!CloseHandle` at `0x18001a11b`
- `KERNEL32!CloseHandle` at `0x18001a138`
- `KERNEL32!GetCurrentProcess` at `0x180019fac`
- `KERNEL32!GetCurrentProcess` at `0x180019fac`
- `KERNEL32!IsWow64Process` at `0x180019fc0`
- `KERNEL32!IsWow64Process` at `0x180019fc0`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x180019fdc`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x180019fdc`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x18001a030`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x18001a030`
- `KERNEL32!CreateFileMappingW` at `0x18001a0b3`
- `KERNEL32!CreateFileMappingW` at `0x18001a0b3`
- `KERNEL32!MapViewOfFileEx` at `0x18001a167`
- `KERNEL32!MapViewOfFileEx` at `0x18001a167`
- `KERNEL32!UnmapViewOfFile` at `0x18001a102`
- `KERNEL32!UnmapViewOfFile` at `0x18001a102`
- `KERNEL32!CreateFileW` at `0x18001a015`
- `KERNEL32!CreateFileW` at `0x18001a015`

## string_xrefs

- `0x18001a05d`: `CreateFile failed: %d`
- `0x18001a0e4`: `CreateFileMapping failed: %d`

## pseudocode

```c
int __fastcall XPerfCore::CFileMapping::MapExistingFileReadOnly2(
        XPerfCore::CFileMapping *this,
        const unsigned __int16 *a2,
        char a3,
        struct XPerfCore::IErrorMessage *a4)
{
  HANDLE CurrentProcess; // rax
  void (*v9)(struct XPerfCore::IErrorMessage *, const wchar_t *, ...); // rbx
  DWORD v10; // eax
  int result; // eax
  HANDLE FileMappingW; // rax
  void (__fastcall *v13)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD); // rbx
  DWORD LastError; // eax
  const void *v15; // rcx
  void *v16; // rcx
  unsigned int *v17; // rcx
  void (__fastcall *v18)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD); // rbx
  DWORD v19; // eax
  __int64 v20; // rax
  unsigned int v21; // edx
  char *v22; // rcx
  PVOID OldValue[2]; // [rsp+40h] [rbp-28h] BYREF
  WINBOOL Wow64Process; // [rsp+70h] [rbp+8h] BYREF

  OldValue[1] = (PVOID)-2LL;
  if ( *(_OWORD *)this != 0xFFFFFFFFFFFFFFFFuLL || *((_QWORD *)this + 2) )
    return -2147483634;
  Wow64Process = 0;
  OldValue[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) && Wow64Process == 1 )
    Wow64Process = Wow64DisableWow64FsRedirection(OldValue);
  *(_QWORD *)this = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( Wow64Process )
    Wow64RevertWow64FsRedirection(OldValue[0]);
  if ( *(_QWORD *)this != -1 )
  {
    FileMappingW = CreateFileMappingW(*(HANDLE *)this, 0, a3 != 0 ? 285212674 : 2, 0, 0, 0);
    *((_QWORD *)this + 1) = FileMappingW;
    if ( !FileMappingW )
    {
      if ( a4 )
      {
        v13 = *(void (__fastcall **)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD))(*(_QWORD *)a4 + 8LL);
        LastError = GetLastError();
        v13(a4, L"CreateFileMapping failed: %d", LastError);
      }
LABEL_16:
      v15 = (const void *)*((_QWORD *)this + 2);
      if ( v15 )
      {
        UnmapViewOfFile(v15);
        *((_QWORD *)this + 2) = 0;
      }
      v16 = (void *)*((_QWORD *)this + 1);
      if ( v16 )
      {
        CloseHandle(v16);
        *((_QWORD *)this + 1) = 0;
      }
      if ( *(_QWORD *)this != -1 )
      {
        CloseHandle(*(HANDLE *)this);
        *(_QWORD *)this = -1;
      }
      goto LABEL_11;
    }
    v17 = (unsigned int *)MapViewOfFileEx(FileMappingW, 4u, 0, 0, 0, 0);
    *((_QWORD *)this + 2) = v17;
    if ( !v17 )
    {
      if ( a4 )
      {
        v18 = *(void (__fastcall **)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD))(*(_QWORD *)a4 + 8LL);
        v19 = GetLastError();
        v18(a4, L"MapViewOfFileEx failed: %d", v19);
      }
      goto LABEL_16;
    }
    if ( *(_WORD *)v17 == 23117 )
    {
      v20 = v17[15];
      if ( (v20 & 3) == 0 && (_DWORD)v20 != -1 )
      {
        v21 = ~(_DWORD)v20;
        if ( (unsigned int)~(_DWORD)v20 >= 0x1B )
        {
          v22 = (char *)v17 + v20;
          if ( *(_DWORD *)v22 == 17744 )
          {
            if ( *((_WORD *)v22 + 12) == 267 )
            {
              if ( v21 > 0xF8 )
              {
LABEL_36:
                *((_QWORD *)this + 3) = *((unsigned int *)v22 + 20);
                return 0;
              }
            }
            else if ( *((_WORD *)v22 + 12) == 523 && v21 > 0x108 )
            {
              goto LABEL_36;
            }
          }
        }
      }
    }
    v22 = 0;
    goto LABEL_36;
  }
  if ( a4 )
  {
    v9 = *(void (**)(struct XPerfCore::IErrorMessage *, const wchar_t *, ...))(*(_QWORD *)a4 + 8LL);
    v10 = GetLastError();
    v9(a4, L"CreateFile failed: %d", v10);
  }
LABEL_11:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180019f5c  mov     rax, rsp
0x180019f5f  push    rsi
0x180019f60  push    rdi
0x180019f61  push    r14
0x180019f63  sub     rsp, 50h
0x180019f67  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x180019f6f  mov     [rax+10h], rbx
0x180019f73  mov     [rax+18h], rbp
0x180019f77  mov     rsi, r9
0x180019f7a  mov     bpl, r8b
0x180019f7d  mov     rbx, rdx
0x180019f80  mov     rdi, rcx
0x180019f83  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180019f87  jnz     loc_18001A207
0x180019f8d  xor     r14d, r14d
0x180019f90  cmp     [rcx+8], r14
0x180019f94  jnz     loc_18001A207
0x180019f9a  cmp     [rcx+10h], r14
0x180019f9e  jnz     loc_18001A207
0x180019fa4  mov     [rax+8], r14d
0x180019fa8  mov     [rax-28h], r14
0x180019fac  call    cs:__imp_GetCurrentProcess
0x180019fb3  nop     dword ptr [rax+rax+00h]
0x180019fb8  mov     rcx, rax; hProcess
0x180019fbb  lea     rdx, [rsp+68h+Wow64Process]; Wow64Process
0x180019fc0  call    cs:__imp_IsWow64Process
0x180019fc7  nop     dword ptr [rax+rax+00h]
0x180019fcc  test    eax, eax
0x180019fce  jz      short loc_180019FF1
0x180019fd0  cmp     [rsp+68h+Wow64Process], 1
0x180019fd5  jnz     short loc_180019FF1
0x180019fd7  lea     rcx, [rsp+68h+OldValue]; OldValue
0x180019fdc  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180019fe3  nop     dword ptr [rax+rax+00h]
0x180019fe8  test    eax, eax
0x180019fea  jnz     short loc_180019FF1
0x180019fec  mov     [rsp+68h+Wow64Process], r14d
0x180019ff1  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180019ff6  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180019ffe  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18001a006  xor     r9d, r9d; lpSecurityAttributes
0x18001a009  mov     edx, 80000000h; dwDesiredAccess
0x18001a00e  lea     r8d, [r9+1]; dwShareMode
0x18001a012  mov     rcx, rbx; lpFileName
0x18001a015  call    cs:__imp_CreateFileW
0x18001a01c  nop     dword ptr [rax+rax+00h]
0x18001a021  mov     [rdi], rax
0x18001a024  cmp     [rsp+68h+Wow64Process], r14d
0x18001a029  jz      short loc_18001A03C
0x18001a02b  mov     rcx, [rsp+68h+OldValue]; OlValue
0x18001a030  call    cs:__imp_Wow64RevertWow64FsRedirection
0x18001a037  nop     dword ptr [rax+rax+00h]
0x18001a03c  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18001a040  jnz     short loc_18001A090
0x18001a042  test    rsi, rsi
0x18001a045  jz      short loc_18001A06F
0x18001a047  mov     rax, [rsi]
0x18001a04a  mov     rbx, [rax+8]
0x18001a04e  call    cs:__imp_GetLastError
0x18001a055  nop     dword ptr [rax+rax+00h]
0x18001a05a  mov     r8d, eax
0x18001a05d  lea     rdx, aCreatefileFail; "CreateFile failed: %d"
0x18001a064  mov     rcx, rsi
0x18001a067  mov     rax, rbx
0x18001a06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a06f  call    cs:__imp_GetLastError
0x18001a076  nop     dword ptr [rax+rax+00h]
0x18001a07b  test    eax, eax
0x18001a07d  jle     loc_18001A20C
0x18001a083  movzx   eax, ax
0x18001a086  or      eax, 80070000h
0x18001a08b  jmp     loc_18001A20C
0x18001a090  neg     bpl
0x18001a093  sbb     r8d, r8d
0x18001a096  and     r8d, 11000000h
0x18001a09d  add     r8d, 2; flProtect
0x18001a0a1  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r14; lpName
0x18001a0a6  mov     [rsp+68h+dwCreationDisposition], r14d; dwMaximumSizeLow
0x18001a0ab  xor     r9d, r9d; dwMaximumSizeHigh
0x18001a0ae  xor     edx, edx; lpFileMappingAttributes
0x18001a0b0  mov     rcx, [rdi]; hFile
0x18001a0b3  call    cs:__imp_CreateFileMappingW
0x18001a0ba  nop     dword ptr [rax+rax+00h]
0x18001a0bf  mov     [rdi+8], rax
0x18001a0c3  test    rax, rax
0x18001a0c6  jnz     loc_18001A150
0x18001a0cc  test    rsi, rsi
0x18001a0cf  jz      short loc_18001A0F9
0x18001a0d1  mov     rax, [rsi]
0x18001a0d4  mov     rbx, [rax+8]
0x18001a0d8  call    cs:__imp_GetLastError
0x18001a0df  nop     dword ptr [rax+rax+00h]
0x18001a0e4  lea     rdx, aCreatefilemapp; "CreateFileMapping failed: %d"
0x18001a0eb  mov     r8d, eax
0x18001a0ee  mov     rcx, rsi
0x18001a0f1  mov     rax, rbx
0x18001a0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0f9  mov     rcx, [rdi+10h]; lpBaseAddress
0x18001a0fd  test    rcx, rcx
0x18001a100  jz      short loc_18001A112
0x18001a102  call    cs:__imp_UnmapViewOfFile
0x18001a109  nop     dword ptr [rax+rax+00h]
0x18001a10e  mov     [rdi+10h], r14
0x18001a112  mov     rcx, [rdi+8]; hObject
0x18001a116  test    rcx, rcx
0x18001a119  jz      short loc_18001A12B
0x18001a11b  call    cs:__imp_CloseHandle
0x18001a122  nop     dword ptr [rax+rax+00h]
0x18001a127  mov     [rdi+8], r14
0x18001a12b  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18001a12f  jz      loc_18001A06F
0x18001a135  mov     rcx, [rdi]; hObject
0x18001a138  call    cs:__imp_CloseHandle
0x18001a13f  nop     dword ptr [rax+rax+00h]
0x18001a144  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18001a14b  jmp     loc_18001A06F
0x18001a150  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r14; lpBaseAddress
0x18001a155  mov     qword ptr [rsp+68h+dwCreationDisposition], r14; dwNumberOfBytesToMap
0x18001a15a  xor     r9d, r9d; dwFileOffsetLow
0x18001a15d  xor     r8d, r8d; dwFileOffsetHigh
0x18001a160  lea     edx, [r9+4]; dwDesiredAccess
0x18001a164  mov     rcx, rax; hFileMappingObject
0x18001a167  call    cs:__imp_MapViewOfFileEx
0x18001a16e  nop     dword ptr [rax+rax+00h]
0x18001a173  mov     rcx, rax
0x18001a176  mov     [rdi+10h], rax
0x18001a17a  test    rax, rax
0x18001a17d  jnz     short loc_18001A1A7
0x18001a17f  test    rsi, rsi
0x18001a182  jz      loc_18001A0F9
0x18001a188  mov     rax, [rsi]
0x18001a18b  mov     rbx, [rax+8]
0x18001a18f  call    cs:__imp_GetLastError
0x18001a196  nop     dword ptr [rax+rax+00h]
0x18001a19b  lea     rdx, aMapviewoffilee; "MapViewOfFileEx failed: %d"
0x18001a1a2  jmp     loc_18001A0EB
0x18001a1a7  mov     eax, 5A4Dh
0x18001a1ac  cmp     [rcx], ax
0x18001a1af  jnz     short loc_18001A1F9
0x18001a1b1  mov     eax, [rcx+3Ch]
0x18001a1b4  test    al, 3
0x18001a1b6  jnz     short loc_18001A1F9
0x18001a1b8  cmp     eax, 0FFFFFFFFh
0x18001a1bb  jnb     short loc_18001A1F9
0x18001a1bd  mov     edx, eax
0x18001a1bf  not     edx
0x18001a1c1  cmp     edx, 1Bh
0x18001a1c4  jb      short loc_18001A1F9
0x18001a1c6  add     rcx, rax
0x18001a1c9  cmp     dword ptr [rcx], 4550h
0x18001a1cf  jnz     short loc_18001A1F9
0x18001a1d1  mov     eax, 10Bh
0x18001a1d6  cmp     [rcx+18h], ax
0x18001a1da  jz      short loc_18001A1F1
0x18001a1dc  mov     eax, 20Bh
0x18001a1e1  cmp     [rcx+18h], ax
0x18001a1e5  jnz     short loc_18001A1F9
0x18001a1e7  cmp     edx, 108h
0x18001a1ed  jbe     short loc_18001A1F9
0x18001a1ef  jmp     short loc_18001A1FC
0x18001a1f1  cmp     edx, 0F8h
0x18001a1f7  ja      short loc_18001A1FC
0x18001a1f9  mov     rcx, r14
0x18001a1fc  mov     eax, [rcx+50h]
0x18001a1ff  mov     [rdi+18h], rax
0x18001a203  xor     eax, eax
0x18001a205  jmp     short loc_18001A20C
0x18001a207  mov     eax, 8000000Eh
0x18001a20c  lea     r11, [rsp+68h+var_18]
0x18001a211  mov     rbx, [r11+28h]
0x18001a215  mov     rbp, [r11+30h]
0x18001a219  mov     rsp, r11
0x18001a21c  pop     r14
0x18001a21e  pop     rdi
0x18001a21f  pop     rsi
0x18001a220  retn
```
