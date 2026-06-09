# CDlpHelpersT<CEmptyType>::FlushVolumeToDisk(ushort const *)

- ea: `0x180017320`
- end: `0x180017481`
- name: `?FlushVolumeToDisk@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBG@Z`
- size: `353`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800244d4`

## callees

- `0x180001be8`
- `0x180001f30`
- `0x18000aba4`
- `0x1800140dc`
- `0x180017320`
- `0x18001fd60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800173fd`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800173fd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001735e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001735e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800173d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800173d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017407`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001746c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001746c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDlpHelpersT<CEmptyType>::FlushVolumeToDisk(LPCWSTR lpFileName)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  DWORD FileAttributesW; // edi
  int v5; // edi
  int v6; // eax
  __int64 v7; // rcx
  HANDLE FileW; // rax
  signed int LastError; // eax
  char *v10; // rdi
  int v12; // [rsp+60h] [rbp+8h] BYREF
  int v13; // [rsp+64h] [rbp+Ch]
  __int64 v14; // [rsp+68h] [rbp+10h]
  void *v15; // [rsp+70h] [rbp+18h] BYREF

  v2 = -1;
  v14 = -1;
  v15 = 0;
  v12 = 17;
  v13 = 18;
  if ( !lpFileName )
  {
    v3 = -2147024809;
LABEL_17:
    v7 = v3;
    goto LABEL_18;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
    v5 = 0;
  else
    v5 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v5 )
  {
    v3 = -2147024893;
    goto LABEL_17;
  }
  v6 = CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(&v15, (__int64)&v12, 2u);
  v3 = v6;
  if ( v6 >= 0 )
  {
    FileW = CreateFileW(lpFileName, 0xC0000000, 7u, 0, 3u, 0x2000000u, 0);
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v2 = (__int64)FileW;
      v14 = (__int64)FileW;
      if ( FlushFileBuffers(FileW) )
        goto LABEL_19;
    }
    else
    {
      v14 = -1;
    }
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    goto LABEL_17;
  }
  v7 = (unsigned int)v6;
LABEL_18:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_19:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v15 )
  {
    v10 = (char *)v15 - 8;
    `eh vector destructor iterator'(
      v15,
      8u,
      *((_QWORD *)v15 - 1),
      (void (*)(void *))CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState);
    operator delete(v10);
  }
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v2);
  return v3;
}

```

## disassembly

```asm
0x180017320  mov     rax, rsp
0x180017323  mov     [rax+20h], rbx
0x180017327  push    rbp
0x180017328  push    rsi
0x180017329  push    rdi
0x18001732a  sub     rsp, 40h
0x18001732e  mov     rbp, rcx
0x180017331  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017335  mov     [rax+10h], rbx
0x180017339  mov     qword ptr [rax+18h], 0
0x180017341  mov     dword ptr [rax+8], 11h
0x180017348  mov     dword ptr [rax+0Ch], 12h
0x18001734f  test    rcx, rcx
0x180017352  jnz     short loc_18001735E
0x180017354  mov     esi, 80070057h
0x180017359  jmp     loc_180017425
0x18001735e  call    cs:__imp_GetFileAttributesW
0x180017364  mov     edi, eax
0x180017366  cmp     eax, 0FFFFFFFFh
0x180017369  jz      short loc_180017373
0x18001736b  shr     edi, 4
0x18001736e  and     edi, 1
0x180017371  jmp     short loc_180017375
0x180017373  xor     edi, edi
0x180017375  xor     ecx, ecx
0x180017377  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001737c  xor     ecx, ecx
0x18001737e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017383  test    edi, edi
0x180017385  jnz     short loc_180017391
0x180017387  mov     esi, 80070003h
0x18001738c  jmp     loc_180017425
0x180017391  mov     r8d, 2
0x180017397  lea     rdx, [rsp+58h+arg_0]
0x18001739c  lea     rcx, [rsp+58h+arg_10]
0x1800173a1  call    ?Enable@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAAJPEBKK@Z; CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(ulong const *,ulong)
0x1800173a6  mov     esi, eax
0x1800173a8  test    eax, eax
0x1800173aa  jns     short loc_1800173B0
0x1800173ac  mov     ecx, eax
0x1800173ae  jmp     short loc_180017427
0x1800173b0  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800173b9  mov     [rsp+58h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800173c1  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800173c9  xor     r9d, r9d; lpSecurityAttributes
0x1800173cc  mov     edx, 0C0000000h; dwDesiredAccess
0x1800173d1  lea     r8d, [r9+7]; dwShareMode
0x1800173d5  mov     rcx, rbp; lpFileName
0x1800173d8  call    cs:__imp_CreateFileW
0x1800173de  lea     rcx, [rax+1]
0x1800173e2  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800173e9  jnz     short loc_1800173F2
0x1800173eb  mov     [rsp+58h+arg_8], rbx
0x1800173f0  jmp     short loc_180017407
0x1800173f2  mov     rbx, rax
0x1800173f5  mov     [rsp+58h+arg_8], rax
0x1800173fa  mov     rcx, rax; hFile
0x1800173fd  call    cs:__imp_FlushFileBuffers
0x180017403  test    eax, eax
0x180017405  jnz     short loc_18001742C
0x180017407  call    cs:__imp_GetLastError
0x18001740d  mov     esi, eax
0x18001740f  test    eax, eax
0x180017411  jnz     short loc_18001741A
0x180017413  mov     esi, 80004005h
0x180017418  jmp     short loc_180017425
0x18001741a  jle     short loc_180017425
0x18001741c  movzx   esi, ax
0x18001741f  or      esi, 80070000h
0x180017425  mov     ecx, esi
0x180017427  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001742c  mov     ecx, esi
0x18001742e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017433  nop
0x180017434  mov     rcx, [rsp+58h+arg_10]; void *
0x180017439  test    rcx, rcx
0x18001743c  jz      short loc_18001745F
0x18001743e  lea     rdi, [rcx-8]
0x180017442  lea     r9, ??1CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; void (*)(void *)
0x180017449  mov     r8, [rdi]; unsigned __int64
0x18001744c  mov     edx, 8; unsigned __int64
0x180017451  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180017456  mov     rcx, rdi; Block
0x180017459  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001745e  nop
0x18001745f  lea     rax, [rbx-1]
0x180017463  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017467  ja      short loc_180017472
0x180017469  mov     rcx, rbx; hObject
0x18001746c  call    cs:__imp_CloseHandle
0x180017472  mov     eax, esi
0x180017474  mov     rbx, [rsp+58h+arg_18]
0x180017479  add     rsp, 40h
0x18001747d  pop     rdi
0x18001747e  pop     rsi
0x18001747f  pop     rbp
0x180017480  retn
```
