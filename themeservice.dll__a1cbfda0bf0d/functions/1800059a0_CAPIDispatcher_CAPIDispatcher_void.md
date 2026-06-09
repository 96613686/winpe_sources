# CAPIDispatcher::~CAPIDispatcher(void)

- ea: `0x1800059a0`
- end: `0x180005a6e`
- name: `??1CAPIDispatcher@@UEAA@XZ`
- size: `206`
- prototype: `void __fastcall(CAPIDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e1e0`

## callees

- `0x1800059a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059f5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180005a5f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180005a5f`
- `ntdll!RtlDeleteCriticalSection` at `0x180005a0b`
- `ntdll!RtlDeleteCriticalSection` at `0x180005a44`
- `ntdll!RtlDeleteCriticalSection` at `0x180005a0b`
- `ntdll!RtlDeleteCriticalSection` at `0x180005a44`

## pseudocode

```c
void __fastcall CAPIDispatcher::~CAPIDispatcher(CAPIDispatcher *this)
{
  const void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rdi

  *(_QWORD *)this = &CAPIDispatcher::`vftable';
  v2 = (const void *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    UnmapViewOfFile(v2);
    *((_QWORD *)this + 3) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 13);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 13) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 12);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 12) = 0;
  }
  if ( *((int *)this + 30) >= 0 )
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 128));
  v6 = *((_QWORD *)this + 4);
  if ( v6 )
  {
    do
    {
      v7 = *(_QWORD *)(v6 + 8);
      (**(void (__fastcall ***)(__int64, __int64))v6)(v6, 1);
      *((_QWORD *)this + 4) = v7;
      v6 = v7;
    }
    while ( v7 );
  }
  if ( *((int *)this + 10) >= 0 )
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 48));
  *(_QWORD *)this = &CQueueElement::`vftable';
}

```

## disassembly

```asm
0x1800059a0  mov     [rsp+arg_0], rbx
0x1800059a5  push    rdi
0x1800059a6  sub     rsp, 20h
0x1800059aa  lea     rax, ??_7CAPIDispatcher@@6B@; const CAPIDispatcher::`vftable'
0x1800059b1  mov     rbx, rcx
0x1800059b4  mov     [rcx], rax
0x1800059b7  xor     edi, edi
0x1800059b9  mov     rcx, [rcx+18h]; lpBaseAddress
0x1800059bd  test    rcx, rcx
0x1800059c0  jnz     loc_180005A5F
0x1800059c6  mov     rcx, [rbx+10h]; hObject
0x1800059ca  test    rcx, rcx
0x1800059cd  jz      short loc_1800059D9
0x1800059cf  call    cs:__imp_CloseHandle
0x1800059d5  mov     [rbx+10h], rdi
0x1800059d9  mov     rcx, [rbx+68h]; hObject
0x1800059dd  test    rcx, rcx
0x1800059e0  jz      short loc_1800059EC
0x1800059e2  call    cs:__imp_CloseHandle
0x1800059e8  mov     [rbx+68h], rdi
0x1800059ec  mov     rcx, [rbx+60h]; hObject
0x1800059f0  test    rcx, rcx
0x1800059f3  jz      short loc_1800059FF
0x1800059f5  call    cs:__imp_CloseHandle
0x1800059fb  mov     [rbx+60h], rdi
0x1800059ff  cmp     [rbx+78h], edi
0x180005a02  jl      short loc_180005A11
0x180005a04  lea     rcx, [rbx+80h]; CriticalSection
0x180005a0b  call    cs:__imp_RtlDeleteCriticalSection
0x180005a11  mov     rcx, [rbx+20h]
0x180005a15  test    rcx, rcx
0x180005a18  jz      short loc_180005A3A
0x180005a1a  mov     rax, [rcx]
0x180005a1d  mov     edx, 1
0x180005a22  mov     rdi, [rcx+8]
0x180005a26  mov     rax, [rax]
0x180005a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a2e  mov     [rbx+20h], rdi
0x180005a32  mov     rcx, rdi
0x180005a35  test    rdi, rdi
0x180005a38  jnz     short loc_180005A1A
0x180005a3a  cmp     dword ptr [rbx+28h], 0
0x180005a3e  jl      short loc_180005A4A
0x180005a40  lea     rcx, [rbx+30h]; CriticalSection
0x180005a44  call    cs:__imp_RtlDeleteCriticalSection
0x180005a4a  lea     rax, ??_7CQueueElement@@6B@; const CQueueElement::`vftable'
0x180005a51  mov     [rbx], rax
0x180005a54  mov     rbx, [rsp+28h+arg_0]
0x180005a59  add     rsp, 20h
0x180005a5d  pop     rdi
0x180005a5e  retn
0x180005a5f  call    cs:__imp_UnmapViewOfFile
0x180005a65  mov     [rbx+18h], rdi
0x180005a69  jmp     loc_1800059C6
```
