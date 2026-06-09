# CTftpSession::ReadDataIntoCache(ulong *)

- ea: `0x18000710c`
- end: `0x180007283`
- name: `?ReadDataIntoCache@CTftpSession@@AEAAKPEAK@Z`
- size: `375`
- prototype: `__int64 __fastcall(CTftpSession *this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18000728c`

## callees

- `0x18000710c`
- `0x1800091a4`
- `0x18000c49c`
- `0x18000d2bc`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007128`
- `KERNEL32!EnterCriticalSection` at `0x180007128`
- `KERNEL32!LeaveCriticalSection` at `0x180007264`
- `KERNEL32!LeaveCriticalSection` at `0x180007264`

## string_xrefs

- `0x1800071db`: `base\eco\wds\transport\server\tftp\tftpfilereader.cpp`
- `0x18000720d`: `base\eco\wds\transport\server\tftp\tftpfilereader.cpp`

## pseudocode

```c
__int64 __fastcall CTftpSession::ReadDataIntoCache(CTftpSession *this, unsigned int *a2)
{
  unsigned int updated; // edi
  int v5; // r10d
  int v6; // r9d
  union _ULARGE_INTEGER v7; // rax
  int v8; // ebx
  __int64 v9; // r8
  union _ULARGE_INTEGER v10; // rbx
  union _ULARGE_INTEGER v11; // r8
  __int64 v12; // rdi
  CTptReadFile **v13; // r14
  const char *v14; // rdx
  const char *v15; // rdx
  const char *v16; // rdx
  void *v18; // [rsp+20h] [rbp-38h]
  union _ULARGE_INTEGER v19; // [rsp+60h] [rbp+8h]

  updated = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = *((_DWORD *)this + 603);
  v6 = *((_DWORD *)this + 584);
  if ( v5 != v6 )
  {
    v7 = *(union _ULARGE_INTEGER *)((char *)this + 2432);
    v8 = *((_DWORD *)this + 583);
    v9 = (unsigned int)((v6 - v5) * v8);
    v10.QuadPart = *((_QWORD *)this + 303) + (unsigned int)(v5 * v8);
    v11.QuadPart = v10.QuadPart + v9 - 1;
    v19 = v11;
    if ( v11.QuadPart >= v7.QuadPart )
    {
      v11.QuadPart = v7.QuadPart - 1;
      v19.QuadPart = v7.QuadPart - 1;
    }
    if ( lpCriticalSection[14].LockCount )
    {
      v12 = *((_QWORD *)this + 305);
      v13 = (CTptReadFile **)((char *)this + 2448);
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 56), 0)
        || *(CTptReadFile **)(v12 + 88) == *v13
        || (unsigned int)CTptReadFile::ModifiedSinceOpen((LPCRITICAL_SECTION)*v13)
        || (updated = CTftpFileReader::MoveRequestToSharedReader(
                        (CTftpFileReader *)v12,
                        (struct CTptReadFile **)this + 306),
            !ElValidateWin32(updated, v14, "base\\eco\\wds\\transport\\server\\tftp\\tftpfilereader.cpp", 0x22Au)) )
      {
        updated = CTptReadFile::UpdateCache(*v13, v10, v19, this, v18, a2);
        ElValidateWin32(updated, v16, "base\\eco\\wds\\transport\\server\\tftp\\tftpfilereader.cpp", 0x232u);
      }
    }
    else
    {
      updated = CTptReadFile::UpdateCache(*((CTptReadFile **)this + 307), v10, v11, this, v18, a2);
    }
    if ( updated == 170 )
    {
      updated = 0;
    }
    else if ( updated != 183 )
    {
      ElValidateWin32(updated, v15, "base\\eco\\wds\\transport\\server\\tftp\\tftpsession.cpp", 0x44Bu);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return updated;
}

```

## disassembly

```asm
0x18000710c  mov     [rsp+arg_8], rbx
0x180007111  push    rbp
0x180007112  push    rsi
0x180007113  push    rdi
0x180007114  push    r14
0x180007116  push    r15
0x180007118  sub     rsp, 30h
0x18000711c  mov     rsi, rcx
0x18000711f  mov     r15, rdx
0x180007122  add     rcx, 18h; lpCriticalSection
0x180007126  xor     edi, edi
0x180007128  call    cs:__imp_EnterCriticalSection
0x18000712f  nop     dword ptr [rax+rax+00h]
0x180007134  mov     r10d, [rsi+96Ch]
0x18000713b  mov     r9d, [rsi+920h]
0x180007142  cmp     r10d, r9d
0x180007145  jz      loc_180007260
0x18000714b  mov     r8d, [rsi+91Ch]
0x180007152  sub     r9d, r10d
0x180007155  mov     rax, [rsi+980h]
0x18000715c  mov     ebx, r8d
0x18000715f  imul    r8d, r9d
0x180007163  imul    ebx, r10d
0x180007167  dec     r8
0x18000716a  add     rbx, [rsi+978h]
0x180007171  add     r8, rbx
0x180007174  mov     [rsp+58h+arg_10], rbx
0x180007179  mov     qword ptr [rsp+58h+arg_0], r8
0x18000717e  cmp     r8, rax
0x180007181  jb      short loc_18000718C
0x180007183  lea     r8, [rax-1]; union _ULARGE_INTEGER
0x180007187  mov     qword ptr [rsp+58h+arg_0], r8
0x18000718c  mov     rax, cs:lpCriticalSection
0x180007193  cmp     [rax+238h], edi
0x180007199  jz      loc_18000721F
0x18000719f  mov     rdi, [rsi+988h]
0x1800071a6  lea     r14, [rsi+990h]
0x1800071ad  xor     eax, eax
0x1800071af  lock xadd [rdi+38h], eax
0x1800071b4  test    eax, eax
0x1800071b6  jz      short loc_1800071EF
0x1800071b8  mov     rcx, [r14]; lpCriticalSection
0x1800071bb  cmp     [rdi+58h], rcx
0x1800071bf  jz      short loc_1800071EF
0x1800071c1  call    ?ModifiedSinceOpen@CTptReadFile@@QEAAHXZ; CTptReadFile::ModifiedSinceOpen(void)
0x1800071c6  test    eax, eax
0x1800071c8  jnz     short loc_1800071EF
0x1800071ca  mov     rdx, r14; struct CTptReadFile **
0x1800071cd  mov     rcx, rdi; this
0x1800071d0  call    ?MoveRequestToSharedReader@CTftpFileReader@@AEAAKPEAPEAVCTptReadFile@@@Z; CTftpFileReader::MoveRequestToSharedReader(CTptReadFile * *)
0x1800071d5  mov     r9d, 22Ah; unsigned int
0x1800071db  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800071e2  mov     ecx, eax; unsigned int
0x1800071e4  mov     edi, eax
0x1800071e6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800071eb  test    eax, eax
0x1800071ed  jnz     short loc_180007238
0x1800071ef  mov     r8, qword ptr [rsp+58h+arg_0]; union _ULARGE_INTEGER
0x1800071f4  mov     r9, rsi; struct ITptReadFileCallback *
0x1800071f7  mov     rcx, [r14]; this
0x1800071fa  mov     rdx, rbx; union _ULARGE_INTEGER
0x1800071fd  mov     [rsp+58h+var_30], r15; unsigned int *
0x180007202  call    ?UpdateCache@CTptReadFile@@QEAAKT_ULARGE_INTEGER@@0PEAVITptReadFileCallback@@PEAXPEAK@Z; CTptReadFile::UpdateCache(_ULARGE_INTEGER,_ULARGE_INTEGER,ITptReadFileCallback *,void *,ulong *)
0x180007207  mov     r9d, 232h; unsigned int
0x18000720d  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\tftp"...
0x180007214  mov     ecx, eax; unsigned int
0x180007216  mov     edi, eax
0x180007218  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000721d  jmp     short loc_180007238
0x18000721f  mov     rcx, [rsi+998h]; this
0x180007226  mov     r9, rsi; struct ITptReadFileCallback *
0x180007229  mov     rdx, rbx; union _ULARGE_INTEGER
0x18000722c  mov     [rsp+58h+var_30], r15; unsigned int *
0x180007231  call    ?UpdateCache@CTptReadFile@@QEAAKT_ULARGE_INTEGER@@0PEAVITptReadFileCallback@@PEAXPEAK@Z; CTptReadFile::UpdateCache(_ULARGE_INTEGER,_ULARGE_INTEGER,ITptReadFileCallback *,void *,ulong *)
0x180007236  mov     edi, eax
0x180007238  cmp     edi, 0AAh
0x18000723e  jnz     short loc_180007244
0x180007240  xor     edi, edi
0x180007242  jmp     short loc_180007260
0x180007244  cmp     edi, 0B7h
0x18000724a  jz      short loc_180007260
0x18000724c  mov     r9d, 44Bh; unsigned int
0x180007252  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\tftp"...
0x180007259  mov     ecx, edi; unsigned int
0x18000725b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180007260  lea     rcx, [rsi+18h]; lpCriticalSection
0x180007264  call    cs:__imp_LeaveCriticalSection
0x18000726b  nop     dword ptr [rax+rax+00h]
0x180007270  mov     rbx, [rsp+58h+arg_8]
0x180007275  mov     eax, edi
0x180007277  add     rsp, 30h
0x18000727b  pop     r15
0x18000727d  pop     r14
0x18000727f  pop     rdi
0x180007280  pop     rsi
0x180007281  pop     rbp
0x180007282  retn
```
