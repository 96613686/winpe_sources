# CLangDataPack::Load(ushort const *)

- ea: `0x1800d2e40`
- end: `0x1800d2f7f`
- name: `?Load@CLangDataPack@@UEAAJPEBG@Z`
- size: `319`
- prototype: `__int64 __fastcall(CLangDataPack *__hidden this, LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800042d8`
- `0x180016f48`
- `0x1800c4700`
- `0x1800d2b68`
- `0x1800d2e40`
- `0x1800d3018`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800d2ead`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800d2ead`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d2e8c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d2e8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d2f67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d2f67`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLangDataPack::Load(CLangDataPack *this, LPCWSTR lpFileName)
{
  HANDLE FileW; // rsi
  int Error; // ebx
  void *v6; // rcx
  ATL::CAtlFileMappingBase *v7; // rax
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // r9
  __int64 v10; // rax
  unsigned int v11; // r8d
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-28h]
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-20h]

  if ( !lpFileName )
    return 2147942487LL;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x10000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error < 0 )
      goto LABEL_17;
  }
  if ( GetFileType(FileW) == 1 )
  {
    v6 = (void *)*((_QWORD *)this + 5);
    if ( v6 )
    {
      ATL::CAtlFileMapping<unsigned char>::`scalar deleting destructor'(v6);
      *((_QWORD *)this + 5) = 0;
    }
    v7 = (ATL::CAtlFileMappingBase *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v7 )
    {
      *((_QWORD *)v7 + 1) = 0;
      *((_QWORD *)v7 + 3) = 0;
      *((_QWORD *)v7 + 4) = 0;
      *(_QWORD *)v7 = 0;
      *((_QWORD *)v7 + 2) = 0;
      *((_QWORD *)this + 5) = v7;
      Error = ATL::CAtlFileMappingBase::MapFile(v7, FileW, v8, v9, dwCreationDisposition, dwFlagsAndAttributes);
      if ( Error >= 0 )
      {
        v10 = *((_QWORD *)this + 5);
        if ( *(_QWORD *)v10 && (v11 = *(_DWORD *)(v10 + 8)) != 0 )
          Error = CLangDataPack::LoadFromMemory((CLangDataPack **)this, *(const unsigned __int8 **)v10, v11);
        else
          Error = -2147023504;
      }
    }
    else
    {
      *((_QWORD *)this + 5) = 0;
      Error = -2147024882;
    }
  }
  else
  {
    Error = -2147024809;
  }
  if ( FileW )
LABEL_17:
    CloseHandle(FileW);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d2e40  mov     [rsp+arg_0], rbx
0x1800d2e45  mov     [rsp+arg_8], rsi
0x1800d2e4a  push    rdi
0x1800d2e4b  sub     rsp, 40h
0x1800d2e4f  mov     rax, rdx
0x1800d2e52  mov     rdi, rcx
0x1800d2e55  test    rdx, rdx
0x1800d2e58  jnz     short loc_1800D2E64
0x1800d2e5a  mov     eax, 80070057h
0x1800d2e5f  jmp     loc_1800D2F6F
0x1800d2e64  xor     r9d, r9d; lpSecurityAttributes
0x1800d2e67  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800d2e70  mov     [rsp+48h+dwFlagsAndAttributes], 10000080h; unsigned int
0x1800d2e78  mov     edx, 80000000h; dwDesiredAccess
0x1800d2e7d  mov     rcx, rax; lpFileName
0x1800d2e80  mov     [rsp+48h+dwCreationDisposition], 3; unsigned int
0x1800d2e88  lea     r8d, [r9+1]; dwShareMode
0x1800d2e8c  call    cs:__imp_CreateFileW
0x1800d2e92  mov     rsi, rax
0x1800d2e95  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d2e99  jnz     short loc_1800D2EAA
0x1800d2e9b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800d2ea0  mov     ebx, eax
0x1800d2ea2  test    eax, eax
0x1800d2ea4  js      loc_1800D2F64
0x1800d2eaa  mov     rcx, rsi; hFile
0x1800d2ead  call    cs:__imp_GetFileType
0x1800d2eb3  cmp     eax, 1
0x1800d2eb6  jz      short loc_1800D2EC2
0x1800d2eb8  mov     ebx, 80070057h
0x1800d2ebd  jmp     loc_1800D2F5F
0x1800d2ec2  mov     rcx, [rdi+28h]; void *
0x1800d2ec6  test    rcx, rcx
0x1800d2ec9  jz      short loc_1800D2ED8
0x1800d2ecb  call    ??_G?$CAtlFileMapping@E@ATL@@QEAAPEAXI@Z; ATL::CAtlFileMapping<uchar>::`scalar deleting destructor'(uint)
0x1800d2ed0  mov     qword ptr [rdi+28h], 0
0x1800d2ed8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d2edf  mov     ecx, 28h ; '('; unsigned __int64
0x1800d2ee4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d2ee9  test    rax, rax
0x1800d2eec  jz      short loc_1800D2F52
0x1800d2eee  mov     qword ptr [rax+8], 0
0x1800d2ef6  mov     rdx, rsi; void *
0x1800d2ef9  mov     qword ptr [rax+18h], 0
0x1800d2f01  mov     rcx, rax; this
0x1800d2f04  mov     qword ptr [rax+20h], 0
0x1800d2f0c  mov     qword ptr [rax], 0
0x1800d2f13  mov     qword ptr [rax+10h], 0
0x1800d2f1b  mov     [rdi+28h], rax
0x1800d2f1f  call    ?MapFile@CAtlFileMappingBase@ATL@@QEAAJPEAX_K1KK@Z; ATL::CAtlFileMappingBase::MapFile(void *,unsigned __int64,unsigned __int64,ulong,ulong)
0x1800d2f24  mov     ebx, eax
0x1800d2f26  test    eax, eax
0x1800d2f28  js      short loc_1800D2F5F
0x1800d2f2a  mov     rax, [rdi+28h]
0x1800d2f2e  mov     rdx, [rax]; unsigned __int8 *
0x1800d2f31  test    rdx, rdx
0x1800d2f34  jz      short loc_1800D2F4B
0x1800d2f36  mov     r8d, [rax+8]; unsigned int
0x1800d2f3a  test    r8d, r8d
0x1800d2f3d  jz      short loc_1800D2F4B
0x1800d2f3f  mov     rcx, rdi; this
0x1800d2f42  call    ?LoadFromMemory@CLangDataPack@@AEAAJPEBEK@Z; CLangDataPack::LoadFromMemory(uchar const *,ulong)
0x1800d2f47  mov     ebx, eax
0x1800d2f49  jmp     short loc_1800D2F5F
0x1800d2f4b  mov     ebx, 80070570h
0x1800d2f50  jmp     short loc_1800D2F5F
0x1800d2f52  mov     qword ptr [rdi+28h], 0
0x1800d2f5a  mov     ebx, 8007000Eh
0x1800d2f5f  test    rsi, rsi
0x1800d2f62  jz      short loc_1800D2F6D
0x1800d2f64  mov     rcx, rsi; hObject
0x1800d2f67  call    cs:__imp_CloseHandle
0x1800d2f6d  mov     eax, ebx
0x1800d2f6f  mov     rbx, [rsp+48h+arg_0]
0x1800d2f74  mov     rsi, [rsp+48h+arg_8]
0x1800d2f79  add     rsp, 40h
0x1800d2f7d  pop     rdi
0x1800d2f7e  retn
```
