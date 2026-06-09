# TLPCMgr::TDispatcher::~TDispatcher(void)

- ea: `0x140010810`
- end: `0x1400108d3`
- name: `??1TDispatcher@TLPCMgr@@UEAA@XZ`
- size: `195`
- prototype: `void __fastcall(TLPCMgr::TDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140010b20`

## callees

- `0x140010614`
- `0x140010810`
- `0x1400132a8`
- `0x140016010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400108a8`
- `KERNEL32!CloseHandle` at `0x1400108a8`
- `KERNEL32!DeleteCriticalSection` at `0x140010886`
- `KERNEL32!DeleteCriticalSection` at `0x140010886`

## pseudocode

```c
void __fastcall TLPCMgr::TDispatcher::~TDispatcher(TLPCMgr::TDispatcher *this)
{
  volatile signed __int32 *v1; // rdx
  signed __int32 v3; // r8d
  void *v4; // rcx

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 28);
  if ( v1 )
  {
    do
      v3 = *((_DWORD *)v1 + 2);
    while ( v3 != 0x7FFFFFFF && v3 != _InterlockedCompareExchange(v1 + 2, v3 - 1, v3) );
    if ( v3 == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    *((_QWORD *)this + 28) = 0;
  }
  NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::~TList<NThreadingLibrary::TWorkItem>((char *)this + 184);
  if ( *((int *)this + 44) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    *((_DWORD *)this + 44) = -2147467259;
  }
  v4 = (void *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 13) = &NCoreLibrary::TAutoHandle::`vftable';
  if ( v4 != (void *)-1LL )
    CloseHandle(v4);
  *((_QWORD *)this + 15) = -1;
  *((_QWORD *)this + 13) = &NCoreLibrary::TReferenceCount::`vftable';
  NThreadingLibrary::TWorkItem::~TWorkItem(this);
}

```

## disassembly

```asm
0x140010810  mov     [rsp+arg_0], rbx
0x140010815  push    rdi
0x140010816  sub     rsp, 20h
0x14001081a  mov     rdx, [rcx+0E0h]
0x140010821  mov     rbx, rcx
0x140010824  test    rdx, rdx
0x140010827  jz      short loc_14001086A
0x140010829  mov     r9d, 7FFFFFFFh
0x14001082f  jmp     short loc_14001083F
0x140010831  lea     ecx, [r8-1]
0x140010835  mov     eax, r8d
0x140010838  lock cmpxchg [rdx+8], ecx
0x14001083d  jz      short loc_140010848
0x14001083f  mov     r8d, [rdx+8]
0x140010843  cmp     r8d, r9d
0x140010846  jnz     short loc_140010831
0x140010848  lea     eax, [r8-1]
0x14001084c  test    eax, eax
0x14001084e  jnz     short loc_14001085F
0x140010850  mov     rax, [rdx]
0x140010853  mov     rcx, rdx
0x140010856  mov     rax, [rax+8]
0x14001085a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001085f  mov     qword ptr [rbx+0E0h], 0
0x14001086a  lea     rcx, [rbx+0B8h]
0x140010871  call    ??1?$TList@VTWorkItem@NThreadingLibrary@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::~TList<NThreadingLibrary::TWorkItem>(void)
0x140010876  lea     rdi, [rbx+80h]
0x14001087d  cmp     dword ptr [rdi+30h], 0
0x140010881  jl      short loc_140010893
0x140010883  mov     rcx, rdi; lpCriticalSection
0x140010886  call    cs:__imp_DeleteCriticalSection
0x14001088c  mov     dword ptr [rdi+30h], 80004005h
0x140010893  mov     rcx, [rbx+78h]; hObject
0x140010897  lea     rax, ??_7TAutoHandle@NCoreLibrary@@6B@; const NCoreLibrary::TAutoHandle::`vftable'
0x14001089e  mov     [rbx+68h], rax
0x1400108a2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400108a6  jz      short loc_1400108AE
0x1400108a8  call    cs:__imp_CloseHandle
0x1400108ae  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x1400108b5  mov     qword ptr [rbx+78h], 0FFFFFFFFFFFFFFFFh
0x1400108bd  mov     rcx, rbx; this
0x1400108c0  mov     [rbx+68h], rax
0x1400108c4  mov     rbx, [rsp+28h+arg_0]
0x1400108c9  add     rsp, 20h
0x1400108cd  pop     rdi
0x1400108ce  jmp     ??1TWorkItem@NThreadingLibrary@@UEAA@XZ; NThreadingLibrary::TWorkItem::~TWorkItem(void)
```
