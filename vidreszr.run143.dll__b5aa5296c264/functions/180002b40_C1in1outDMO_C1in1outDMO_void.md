# C1in1outDMO::~C1in1outDMO(void)

- ea: `0x180002b40`
- end: `0x180002bbb`
- name: `??1C1in1outDMO@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(C1in1outDMO *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ac0`

## callees

- `0x180002b40`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002b65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002b65`
- `msdmo!MoFreeMediaType` at `0x180002b75`
- `msdmo!MoFreeMediaType` at `0x180002b88`
- `msdmo!MoFreeMediaType` at `0x180002b75`
- `msdmo!MoFreeMediaType` at `0x180002b88`

## pseudocode

```c
void __fastcall C1in1outDMO::~C1in1outDMO(C1in1outDMO *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &C1in1outDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'};
  *((_QWORD *)this + 6) = &C1in1outDMO::`vftable'{for `IMediaObject'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  if ( *((_DWORD *)this + 14) )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 64));
  if ( *((_DWORD *)this + 15) )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 152));
  v2 = *((_QWORD *)this + 4);
  *(_QWORD *)this = &CMFTtoDMOImpl<CMFTtoDMO>::`vftable';
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x180002b40  push    rbx
0x180002b42  sub     rsp, 20h
0x180002b46  lea     rax, ??_7C1in1outDMO@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const C1in1outDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x180002b4d  mov     rbx, rcx
0x180002b50  mov     [rcx], rax
0x180002b53  lea     rax, ??_7C1in1outDMO@@6BIMediaObject@@@; const C1in1outDMO::`vftable'{for `IMediaObject'}
0x180002b5a  mov     [rcx+30h], rax
0x180002b5e  add     rcx, 108h; lpCriticalSection
0x180002b65  call    cs:__imp_DeleteCriticalSection
0x180002b6b  cmp     dword ptr [rbx+38h], 0
0x180002b6f  jz      short loc_180002B7B
0x180002b71  lea     rcx, [rbx+40h]; pmt
0x180002b75  call    cs:__imp_MoFreeMediaType
0x180002b7b  cmp     dword ptr [rbx+3Ch], 0
0x180002b7f  jz      short loc_180002B8E
0x180002b81  lea     rcx, [rbx+98h]; pmt
0x180002b88  call    cs:__imp_MoFreeMediaType
0x180002b8e  mov     rcx, [rbx+20h]
0x180002b92  lea     rax, ??_7?$CMFTtoDMOImpl@VCMFTtoDMO@@@@6B@; const CMFTtoDMOImpl<CMFTtoDMO>::`vftable'
0x180002b99  mov     [rbx], rax
0x180002b9c  test    rcx, rcx
0x180002b9f  jz      short loc_180002BB5
0x180002ba1  mov     rax, [rcx]
0x180002ba4  mov     rax, [rax+10h]
0x180002ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bad  mov     qword ptr [rbx+20h], 0
0x180002bb5  add     rsp, 20h
0x180002bb9  pop     rbx
0x180002bba  retn
```
