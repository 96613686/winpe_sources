# CDiagnosticProvider::~CDiagnosticProvider(void)

- ea: `0x180006628`
- end: `0x1800066d4`
- name: `??1CDiagnosticProvider@@UEAA@XZ`
- size: `172`
- prototype: `void __fastcall(CDiagnosticProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006720`

## callees

- `0x1800065bc`
- `0x180006628`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006650`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000665d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006650`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000665d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006674`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006674`

## pseudocode

```c
void __fastcall CDiagnosticProvider::~CDiagnosticProvider(CDiagnosticProvider *this)
{
  bool v1; // zf
  char *v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx

  v1 = *((_DWORD *)this + 23) == 0;
  *(_QWORD *)this = &CDiagnosticProvider::`vftable'{for `IDiagnosticProvider'};
  *((_QWORD *)this + 1) = &CDiagnosticProvider::`vftable'{for `SDiagPrvSyncObject'};
  if ( !v1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  }
  v3 = (char *)*((_QWORD *)this + 22);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 22) = 0;
  }
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 9);
  if ( v4 )
  {
    (**v4)(v4, 1);
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 10);
  if ( v5 )
  {
    (**v5)(v5, 1);
    *((_QWORD *)this + 10) = 0;
  }
  Unknown<IDiagnosticProvider>::~Unknown<IDiagnosticProvider>(this);
}

```

## disassembly

```asm
0x180006628  push    rbx
0x18000662a  sub     rsp, 20h
0x18000662e  cmp     dword ptr [rcx+5Ch], 0
0x180006632  lea     rax, ??_7CDiagnosticProvider@@6BIDiagnosticProvider@@@; const CDiagnosticProvider::`vftable'{for `IDiagnosticProvider'}
0x180006639  mov     [rcx], rax
0x18000663c  mov     rbx, rcx
0x18000663f  lea     rax, ??_7CDiagnosticProvider@@6BSDiagPrvSyncObject@@@; const CDiagnosticProvider::`vftable'{for `SDiagPrvSyncObject'}
0x180006646  mov     [rcx+8], rax
0x18000664a  jz      short loc_180006663
0x18000664c  add     rcx, 60h ; '`'; lpCriticalSection
0x180006650  call    cs:__imp_DeleteCriticalSection
0x180006656  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000665d  call    cs:__imp_DeleteCriticalSection
0x180006663  mov     rcx, [rbx+0B0h]; hObject
0x18000666a  lea     rax, [rcx-1]
0x18000666e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006672  ja      short loc_180006685
0x180006674  call    cs:__imp_CloseHandle
0x18000667a  mov     qword ptr [rbx+0B0h], 0
0x180006685  mov     rcx, [rbx+48h]
0x180006689  test    rcx, rcx
0x18000668c  jz      short loc_1800066A6
0x18000668e  mov     rax, [rcx]
0x180006691  mov     edx, 1
0x180006696  mov     rax, [rax]
0x180006699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000669e  mov     qword ptr [rbx+48h], 0
0x1800066a6  mov     rcx, [rbx+50h]
0x1800066aa  test    rcx, rcx
0x1800066ad  jz      short loc_1800066C7
0x1800066af  mov     rax, [rcx]
0x1800066b2  mov     edx, 1
0x1800066b7  mov     rax, [rax]
0x1800066ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066bf  mov     qword ptr [rbx+50h], 0
0x1800066c7  mov     rcx, rbx
0x1800066ca  add     rsp, 20h
0x1800066ce  pop     rbx
0x1800066cf  jmp     ??1?$Unknown@UIDiagnosticProvider@@@@UEAA@XZ; Unknown<IDiagnosticProvider>::~Unknown<IDiagnosticProvider>(void)
```
