# CWebCrawler::CDownloadNotify::~CDownloadNotify(void)

- ea: `0x18001def8`
- end: `0x18001df3e`
- name: `??1CDownloadNotify@CWebCrawler@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(CWebCrawler::CDownloadNotify *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021dd0`

## callees

- `0x18001def8`
- `0x18002a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001df32`
- `KERNEL32!DeleteCriticalSection` at `0x18001df32`

## pseudocode

```c
void __fastcall CWebCrawler::CDownloadNotify::~CDownloadNotify(CWebCrawler::CDownloadNotify *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CWebCrawler::CDownloadNotify::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *((int *)this + 16) >= 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x18001def8  push    rbx
0x18001defa  sub     rsp, 20h
0x18001defe  lea     rax, ??_7CDownloadNotify@CWebCrawler@@6B@; const CWebCrawler::CDownloadNotify::`vftable'
0x18001df05  mov     rbx, rcx
0x18001df08  mov     [rcx], rax
0x18001df0b  mov     rcx, [rcx+10h]
0x18001df0f  test    rcx, rcx
0x18001df12  jz      short loc_18001DF28
0x18001df14  mov     rax, [rcx]
0x18001df17  mov     rax, [rax+10h]
0x18001df1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df20  mov     qword ptr [rbx+10h], 0
0x18001df28  cmp     dword ptr [rbx+40h], 0
0x18001df2c  jl      short loc_18001DF38
0x18001df2e  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001df32  call    cs:__imp_DeleteCriticalSection
0x18001df38  add     rsp, 20h
0x18001df3c  pop     rbx
0x18001df3d  retn
```
