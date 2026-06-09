# CMllr_imp::RestoreRegBuf(void)

- ea: `0x1800a44b4`
- end: `0x1800a464d`
- name: `?RestoreRegBuf@CMllr_imp@@AEAAXXZ`
- size: `409`
- prototype: `void __fastcall(CMllr_imp *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000fcd0`
- `0x1800a5aa8`

## callees

- `0x1800a44b4`
- `0x1800a4654`
- `0x1800a5394`
- `0x1800a5990`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a451e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a451e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a4576`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a4576`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800a453a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800a4547`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800a453a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800a4547`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a463e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a463e`

## pseudocode

```c
void __fastcall CMllr_imp::RestoreRegBuf(HANDLE *this)
{
  __int64 FileW; // rdi
  const WCHAR *v3; // rcx
  __int64 v4; // rax
  DWORD FileSize; // esi
  HANDLE v6; // rdx
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 354) )
  {
    FileW = -1;
    CMllr_imp::InitIndexTables((CMllr_imp *)this);
    v3 = (const WCHAR *)this[50];
    if ( !v3 )
      goto LABEL_12;
    v4 = -1;
    do
      ++v4;
    while ( v3[v4] );
    if ( v4
      && (FileW = (__int64)CreateFileW(v3, 0x80000000, 1u, 0, 3u, 0x80u, 0), FileW != -1)
      && (FileSize = GetFileSize(this[53], 0), FileSize == GetFileSize((HANDLE)FileW, 0))
      && (v6 = this[55], NumberOfBytesRead = 0, ReadFile((HANDLE)FileW, v6, FileSize, &NumberOfBytesRead, 0))
      && NumberOfBytesRead == FileSize
      && (*((_DWORD *)this + 104) = 0, !(unsigned int)CMllr_imp::fCorruptedRegBuf((CMllr_imp *)this)) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this[2] + 2) + 128LL))(
        *((_QWORD *)this[2] + 2),
        2135,
        2);
    }
    else
    {
LABEL_12:
      CMllr_imp::ClearAdaptationData((CMllr_imp *)this);
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this[2] + 2) + 128LL))(
        *((_QWORD *)this[2] + 2),
        2135,
        2);
      if ( FileW == -1 )
        return;
    }
    CloseHandle((HANDLE)FileW);
  }
}

```

## disassembly

```asm
0x1800a44b4  push    rbx
0x1800a44b6  push    rbp
0x1800a44b7  push    rsi
0x1800a44b8  push    rdi
0x1800a44b9  sub     rsp, 78h
0x1800a44bd  xor     ebp, ebp
0x1800a44bf  mov     rbx, rcx
0x1800a44c2  cmp     [rcx+162h], bpl
0x1800a44c9  jnz     loc_1800A4644
0x1800a44cf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a44d3  call    ?InitIndexTables@CMllr_imp@@AEAAJXZ; CMllr_imp::InitIndexTables(void)
0x1800a44d8  mov     rcx, [rbx+190h]; lpFileName
0x1800a44df  test    rcx, rcx
0x1800a44e2  jz      loc_1800A45E7
0x1800a44e8  or      rax, rdi
0x1800a44eb  inc     rax
0x1800a44ee  cmp     [rcx+rax*2], bp
0x1800a44f2  jnz     short loc_1800A44EB
0x1800a44f4  test    rax, rax
0x1800a44f7  jz      loc_1800A45E7
0x1800a44fd  xor     r9d, r9d; lpSecurityAttributes
0x1800a4500  mov     [rsp+98h+hTemplateFile], rbp; hTemplateFile
0x1800a4505  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a450d  mov     edx, 80000000h; dwDesiredAccess
0x1800a4512  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a451a  lea     r8d, [r9+1]; dwShareMode
0x1800a451e  call    cs:__imp_CreateFileW
0x1800a4524  mov     rdi, rax
0x1800a4527  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a452b  jz      loc_1800A45E7
0x1800a4531  mov     rcx, [rbx+1A8h]; hFile
0x1800a4538  xor     edx, edx; lpFileSizeHigh
0x1800a453a  call    cs:__imp_GetFileSize
0x1800a4540  xor     edx, edx; lpFileSizeHigh
0x1800a4542  mov     rcx, rdi; hFile
0x1800a4545  mov     esi, eax
0x1800a4547  call    cs:__imp_GetFileSize
0x1800a454d  cmp     esi, eax
0x1800a454f  jnz     loc_1800A45E7
0x1800a4555  mov     rdx, [rbx+1B8h]; lpBuffer
0x1800a455c  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a4564  mov     r8d, esi; nNumberOfBytesToRead
0x1800a4567  mov     [rsp+98h+NumberOfBytesRead], ebp
0x1800a456e  mov     rcx, rdi; hFile
0x1800a4571  mov     qword ptr [rsp+98h+dwCreationDisposition], rbp; lpOverlapped
0x1800a4576  call    cs:__imp_ReadFile
0x1800a457c  test    eax, eax
0x1800a457e  jz      short loc_1800A45E7
0x1800a4580  cmp     [rsp+98h+NumberOfBytesRead], esi
0x1800a4587  jnz     short loc_1800A45E7
0x1800a4589  mov     rcx, rbx; this
0x1800a458c  mov     [rbx+1A0h], ebp
0x1800a4592  call    ?fCorruptedRegBuf@CMllr_imp@@AEAAHXZ; CMllr_imp::fCorruptedRegBuf(void)
0x1800a4597  test    eax, eax
0x1800a4599  jnz     short loc_1800A45E7
0x1800a459b  mov     rax, [rbx+10h]
0x1800a459f  mov     r9d, 80h
0x1800a45a5  mov     [rsp+98h+var_40], ebp
0x1800a45a9  mov     edx, 857h
0x1800a45ae  mov     [rsp+98h+var_48], ebp
0x1800a45b2  mov     [rsp+98h+var_50], ebp
0x1800a45b6  mov     rcx, [rax+10h]
0x1800a45ba  lea     r8d, [r9-7Eh]
0x1800a45be  mov     [rsp+98h+var_58], ebp
0x1800a45c2  mov     [rsp+98h+var_60], ebp
0x1800a45c6  mov     dword ptr [rsp+98h+hTemplateFile], ebp
0x1800a45ca  mov     rax, [rcx]
0x1800a45cd  mov     [rsp+98h+dwFlagsAndAttributes], ebp
0x1800a45d1  mov     [rsp+98h+dwCreationDisposition], 1
0x1800a45d9  mov     rax, [rax+80h]
0x1800a45e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a45e5  jmp     short loc_1800A463B
0x1800a45e7  mov     rcx, rbx; this
0x1800a45ea  call    ?ClearAdaptationData@CMllr_imp@@QEAAXXZ; CMllr_imp::ClearAdaptationData(void)
0x1800a45ef  mov     rax, [rbx+10h]
0x1800a45f3  mov     r9d, 80h
0x1800a45f9  mov     [rsp+98h+var_40], ebp
0x1800a45fd  mov     edx, 857h
0x1800a4602  mov     [rsp+98h+var_48], ebp
0x1800a4606  mov     [rsp+98h+var_50], ebp
0x1800a460a  mov     rcx, [rax+10h]
0x1800a460e  lea     r8d, [r9-7Eh]
0x1800a4612  mov     [rsp+98h+var_58], ebp
0x1800a4616  mov     [rsp+98h+var_60], ebp
0x1800a461a  mov     dword ptr [rsp+98h+hTemplateFile], ebp
0x1800a461e  mov     rax, [rcx]
0x1800a4621  mov     [rsp+98h+dwFlagsAndAttributes], ebp
0x1800a4625  mov     [rsp+98h+dwCreationDisposition], ebp
0x1800a4629  mov     rax, [rax+80h]
0x1800a4630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4635  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800a4639  jz      short loc_1800A4644
0x1800a463b  mov     rcx, rdi; hObject
0x1800a463e  call    cs:__imp_CloseHandle
0x1800a4644  add     rsp, 78h
0x1800a4648  pop     rdi
0x1800a4649  pop     rsi
0x1800a464a  pop     rbp
0x1800a464b  pop     rbx
0x1800a464c  retn
```
