# FileLogEnd

- ea: `0x18000b494`
- end: `0x18000b5ec`
- name: `FileLogEnd`
- size: `344`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180009a80`
- `0x18000c28c`
- `0x180039100`

## callees

- `0x18000b494`
- `0x180039fa8`
- `0x18003d2d8`
- `0x18004ecd0`
- `0x18004ed38`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b4ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b512`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b5cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b4ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b512`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b5cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b589`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b589`
- `ntdll!RtlDeleteResource` at `0x18000b55f`
- `ntdll!RtlDeleteResource` at `0x18000b5b3`
- `ntdll!RtlDeleteResource` at `0x18000b55f`
- `ntdll!RtlDeleteResource` at `0x18000b5b3`

## pseudocode

```c
HLOCAL FileLogEnd()
{
  HLOCAL result; // rax
  char *v1; // rcx
  void *v2; // rbx

  if ( _pwszFileNameSuffix )
  {
    result = LocalFree(_pwszFileNameSuffix);
    _pwszFileNameSuffix = 0;
  }
  v1 = (char *)_pflstate;
  if ( _pflstate )
  {
    if ( *((_BYTE *)_pflstate + 315) == 1 && *((_QWORD *)_pflstate + 5) )
    {
      FlushCloseFile();
      v1 = (char *)_pflstate;
    }
    if ( *((_QWORD *)v1 + 3) )
    {
      FreeLogEntryRangeChain(*((HLOCAL *)v1 + 3));
      v1 = (char *)_pflstate;
      *((_QWORD *)_pflstate + 3) = 0;
    }
    if ( *((_QWORD *)v1 + 2) )
    {
      LocalFree(*((HLOCAL *)v1 + 2));
      v1 = (char *)_pflstate;
      *((_QWORD *)_pflstate + 2) = 0;
    }
    v2 = (void *)*((_QWORD *)v1 + 9);
    if ( v2 )
    {
      std::vector<AutoPtr<FileLogThreadInfo>,MyThrowingAllocator<AutoPtr<FileLogThreadInfo>>>::~vector<AutoPtr<FileLogThreadInfo>,MyThrowingAllocator<AutoPtr<FileLogThreadInfo>>>(*((_QWORD *)v1 + 9));
      operator delete(v2);
      v1 = (char *)_pflstate;
      *((_QWORD *)_pflstate + 9) = 0;
    }
    if ( v1[312] )
    {
      RtlDeleteResource((PRTL_RESOURCE)(v1 + 80));
      v1 = (char *)_pflstate;
      *((_BYTE *)_pflstate + 312) = 0;
    }
    if ( v1[313] )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 176));
      v1 = (char *)_pflstate;
      *((_BYTE *)_pflstate + 313) = 0;
    }
    if ( v1[314] )
    {
      RtlDeleteResource((PRTL_RESOURCE)(v1 + 216));
      v1 = (char *)_pflstate;
      *((_BYTE *)_pflstate + 314) = 0;
    }
    result = LocalFree(v1);
    _pflstate = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b494  mov     [rsp+arg_0], rbx
0x18000b499  push    rdi
0x18000b49a  sub     rsp, 20h
0x18000b49e  mov     rcx, cs:?_pwszFileNameSuffix@@3PEAGEA; hMem
0x18000b4a5  xor     edi, edi
0x18000b4a7  test    rcx, rcx
0x18000b4aa  jz      short loc_18000B4BF
0x18000b4ac  call    cs:__imp_LocalFree
0x18000b4b3  nop     dword ptr [rax+rax+00h]
0x18000b4b8  mov     cs:?_pwszFileNameSuffix@@3PEAGEA, rdi; ushort * _pwszFileNameSuffix
0x18000b4bf  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000b4c6  test    rcx, rcx
0x18000b4c9  jz      loc_18000B5E0
0x18000b4cf  cmp     byte ptr [rcx+13Bh], 1
0x18000b4d6  jnz     short loc_18000B4EA
0x18000b4d8  cmp     [rcx+28h], rdi
0x18000b4dc  jz      short loc_18000B4EA
0x18000b4de  call    ?FlushCloseFile@@YAJXZ; FlushCloseFile(void)
0x18000b4e3  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000b4ea  mov     rax, [rcx+18h]
0x18000b4ee  test    rax, rax
0x18000b4f1  jz      short loc_18000B506
0x18000b4f3  mov     rcx, rax; hMem
0x18000b4f6  call    ?FreeLogEntryRangeChain@@YAXPEAULogEntryRange@@@Z; FreeLogEntryRangeChain(LogEntryRange *)
0x18000b4fb  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000b502  mov     [rcx+18h], rdi
0x18000b506  mov     rax, [rcx+10h]
0x18000b50a  test    rax, rax
0x18000b50d  jz      short loc_18000B529
0x18000b50f  mov     rcx, rax; hMem
0x18000b512  call    cs:__imp_LocalFree
0x18000b519  nop     dword ptr [rax+rax+00h]
0x18000b51e  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000b525  mov     [rcx+10h], rdi
0x18000b529  mov     rbx, [rcx+48h]
0x18000b52d  test    rbx, rbx
0x18000b530  jz      short loc_18000B552
0x18000b532  mov     rcx, rbx
0x18000b535  call    ??1?$vector@V?$AutoPtr@UFileLogThreadInfo@@@@V?$MyThrowingAllocator@V?$AutoPtr@UFileLogThreadInfo@@@@@@@std@@QEAA@XZ; std::vector<AutoPtr<FileLogThreadInfo>,MyThrowingAllocator<AutoPtr<FileLogThreadInfo>>>::~vector<AutoPtr<FileLogThreadInfo>,MyThrowingAllocator<AutoPtr<FileLogThreadInfo>>>(void)
0x18000b53a  mov     edx, 18h; unsigned __int64
0x18000b53f  mov     rcx, rbx; void *
0x18000b542  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b547  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000b54e  mov     [rcx+48h], rdi
0x18000b552  cmp     [rcx+138h], dil
0x18000b559  jz      short loc_18000B579
0x18000b55b  add     rcx, 50h ; 'P'; Resource
0x18000b55f  call    cs:__imp_RtlDeleteResource
0x18000b566  nop     dword ptr [rax+rax+00h]
0x18000b56b  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000b572  mov     [rcx+138h], dil
0x18000b579  cmp     [rcx+139h], dil
0x18000b580  jz      short loc_18000B5A3
0x18000b582  add     rcx, 0B0h; lpCriticalSection
0x18000b589  call    cs:__imp_DeleteCriticalSection
0x18000b590  nop     dword ptr [rax+rax+00h]
0x18000b595  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000b59c  mov     [rcx+139h], dil
0x18000b5a3  cmp     [rcx+13Ah], dil
0x18000b5aa  jz      short loc_18000B5CD
0x18000b5ac  add     rcx, 0D8h; Resource
0x18000b5b3  call    cs:__imp_RtlDeleteResource
0x18000b5ba  nop     dword ptr [rax+rax+00h]
0x18000b5bf  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; hMem
0x18000b5c6  mov     [rcx+13Ah], dil
0x18000b5cd  call    cs:__imp_LocalFree
0x18000b5d4  nop     dword ptr [rax+rax+00h]
0x18000b5d9  mov     cs:?_pflstate@@3PEAUFileLogState@@EA, rdi; FileLogState * _pflstate
0x18000b5e0  mov     rbx, [rsp+28h+arg_0]
0x18000b5e5  add     rsp, 20h
0x18000b5e9  pop     rdi
0x18000b5ea  retn
```
