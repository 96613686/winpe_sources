# CDVRSource::~CDVRSource(void)

- ea: `0x1800053a4`
- end: `0x18000540a`
- name: `??1CDVRSource@@UEAA@XZ`
- size: `102`
- prototype: `void __fastcall(CDVRSource *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005410`

## callees

- `0x1800053a4`
- `0x18002b010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180005403`
- `KERNEL32!CloseHandle` at `0x1800053f1`
- `KERNEL32!CloseHandle` at `0x1800053f1`

## pseudocode

```c
void __fastcall CDVRSource::~CDVRSource(CDVRSource *this)
{
  __int64 v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CDVRSource::`vftable'{for `IStream'};
  *((_QWORD *)this + 1) = &CDVRSource::`vftable'{for `IDVRFileSource2'};
  *((_QWORD *)this + 2) = &CDVRSource::`vftable'{for `IWMIStreamProps'};
  v2 = *((_QWORD *)this + 18);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (void *)*((_QWORD *)this + 17);
  if ( v3 )
    CloseHandle(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
}

```

## disassembly

```asm
0x1800053a4  push    rbx
0x1800053a6  sub     rsp, 20h
0x1800053aa  lea     rax, ??_7CDVRSource@@6BIStream@@@; const CDVRSource::`vftable'{for `IStream'}
0x1800053b1  mov     rbx, rcx
0x1800053b4  mov     [rcx], rax
0x1800053b7  lea     rax, ??_7CDVRSource@@6BIDVRFileSource2@@@; const CDVRSource::`vftable'{for `IDVRFileSource2'}
0x1800053be  mov     [rcx+8], rax
0x1800053c2  lea     rax, ??_7CDVRSource@@6BIWMIStreamProps@@@; const CDVRSource::`vftable'{for `IWMIStreamProps'}
0x1800053c9  mov     [rcx+10h], rax
0x1800053cd  mov     rcx, [rcx+90h]
0x1800053d4  test    rcx, rcx
0x1800053d7  jz      short loc_1800053E5
0x1800053d9  mov     rax, [rcx]
0x1800053dc  mov     rax, [rax+10h]
0x1800053e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e5  mov     rcx, [rbx+88h]; hObject
0x1800053ec  test    rcx, rcx
0x1800053ef  jz      short loc_1800053F7
0x1800053f1  call    cs:__imp_CloseHandle
0x1800053f7  lea     rcx, [rbx+0C0h]
0x1800053fe  add     rsp, 20h
0x180005402  pop     rbx
0x180005403  jmp     cs:__imp_DeleteCriticalSection
```
