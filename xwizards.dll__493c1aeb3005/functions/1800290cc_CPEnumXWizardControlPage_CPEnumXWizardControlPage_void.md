# CPEnumXWizardControlPage::~CPEnumXWizardControlPage(void)

- ea: `0x1800290cc`
- end: `0x180029168`
- name: `??1CPEnumXWizardControlPage@@QEAA@XZ`
- size: `156`
- prototype: `void __fastcall(CPEnumXWizardControlPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002908c`

## callees

- `0x18000327c`
- `0x1800290cc`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002913c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002913c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029119`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029119`

## pseudocode

```c
void __fastcall CPEnumXWizardControlPage::~CPEnumXWizardControlPage(CPEnumXWizardControlPage *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  LPVOID *v4; // rcx
  LPVOID *v5; // rax

  v2 = *((_QWORD *)this + 8);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 9);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (LPVOID *)*((_QWORD *)this + 10);
  v5 = (LPVOID *)*((_QWORD *)this + 11);
  if ( v4 != v5 )
  {
    while ( 1 )
    {
      v4 = (LPVOID *)*((_QWORD *)this + 10);
      if ( v4 == v5 )
        break;
      CoTaskMemFree(*(v5 - 1));
      v5 = (LPVOID *)*((_QWORD *)this + 11);
      if ( *((LPVOID **)this + 10) != v5 )
        *((_QWORD *)this + 11) = --v5;
    }
    *((_QWORD *)this + 11) = v4;
  }
  if ( v4 )
  {
    operator delete(v4);
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 12) = 0;
  }
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CPEnumXWizardControlPage *)((char *)this + 16));
}

```

## disassembly

```asm
0x1800290cc  push    rbx
0x1800290ce  sub     rsp, 20h
0x1800290d2  mov     rbx, rcx
0x1800290d5  mov     rcx, [rcx+40h]
0x1800290d9  test    rcx, rcx
0x1800290dc  jz      short loc_1800290EA
0x1800290de  mov     rax, [rcx]
0x1800290e1  mov     rax, [rax+10h]
0x1800290e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290ea  mov     rcx, [rbx+48h]
0x1800290ee  test    rcx, rcx
0x1800290f1  jz      short loc_1800290FF
0x1800290f3  mov     rax, [rcx]
0x1800290f6  mov     rax, [rax+10h]
0x1800290fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290ff  mov     rcx, [rbx+50h]
0x180029103  mov     rax, [rbx+58h]
0x180029107  cmp     rcx, rax
0x18002910a  jz      short loc_180029137
0x18002910c  mov     rcx, [rbx+50h]
0x180029110  cmp     rcx, rax
0x180029113  jz      short loc_180029133
0x180029115  mov     rcx, [rax-8]; pv
0x180029119  call    cs:__imp_CoTaskMemFree
0x18002911f  mov     rax, [rbx+58h]
0x180029123  cmp     [rbx+50h], rax
0x180029127  jz      short loc_18002910C
0x180029129  add     rax, 0FFFFFFFFFFFFFFF8h
0x18002912d  mov     [rbx+58h], rax
0x180029131  jmp     short loc_18002910C
0x180029133  mov     [rbx+58h], rcx
0x180029137  test    rcx, rcx
0x18002913a  jz      short loc_18002915A
0x18002913c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180029142  mov     qword ptr [rbx+50h], 0
0x18002914a  mov     qword ptr [rbx+58h], 0
0x180029152  mov     qword ptr [rbx+60h], 0
0x18002915a  lea     rcx, [rbx+10h]; this
0x18002915e  add     rsp, 20h
0x180029162  pop     rbx
0x180029163  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
