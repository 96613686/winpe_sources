# WdcSnapinAbout::~WdcSnapinAbout(void)

- ea: `0x180042300`
- end: `0x180042392`
- name: `??1WdcSnapinAbout@@UEAA@XZ`
- size: `146`
- prototype: `void __fastcall(WdcSnapinAbout *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800423e8`

## callees

- `0x180042300`

## import_xrefs

- `GDI32!DeleteObject` at `0x180042327`
- `GDI32!DeleteObject` at `0x18004233e`
- `GDI32!DeleteObject` at `0x180042355`
- `GDI32!DeleteObject` at `0x18004236c`
- `GDI32!DeleteObject` at `0x180042327`
- `GDI32!DeleteObject` at `0x18004233e`
- `GDI32!DeleteObject` at `0x180042355`
- `GDI32!DeleteObject` at `0x18004236c`

## pseudocode

```c
void __fastcall WdcSnapinAbout::~WdcSnapinAbout(WdcSnapinAbout *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &WdcSnapinAbout::`vftable'{for `ISnapinAbout'};
  *((_QWORD *)this + 1) = &WdcSnapinAbout::`vftable'{for `Unknown'};
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    DeleteObject(v2);
    *((_QWORD *)this + 3) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    DeleteObject(v3);
    *((_QWORD *)this + 4) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 5);
  if ( v4 )
  {
    DeleteObject(v4);
    *((_QWORD *)this + 5) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 )
  {
    DeleteObject(v5);
    *((_QWORD *)this + 6) = 0;
  }
  *((_QWORD *)this + 1) = &Unknown::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)&g_uObjects);
}

```

## disassembly

```asm
0x180042300  push    rbx
0x180042302  sub     rsp, 20h
0x180042306  lea     rax, ??_7WdcSnapinAbout@@6BISnapinAbout@@@; const WdcSnapinAbout::`vftable'{for `ISnapinAbout'}
0x18004230d  mov     rbx, rcx
0x180042310  mov     [rcx], rax
0x180042313  lea     rax, ??_7WdcSnapinAbout@@6BUnknown@@@; const WdcSnapinAbout::`vftable'{for `Unknown'}
0x18004231a  mov     [rcx+8], rax
0x18004231e  mov     rcx, [rcx+18h]; ho
0x180042322  test    rcx, rcx
0x180042325  jz      short loc_180042335
0x180042327  call    cs:__imp_DeleteObject
0x18004232d  mov     qword ptr [rbx+18h], 0
0x180042335  mov     rcx, [rbx+20h]; ho
0x180042339  test    rcx, rcx
0x18004233c  jz      short loc_18004234C
0x18004233e  call    cs:__imp_DeleteObject
0x180042344  mov     qword ptr [rbx+20h], 0
0x18004234c  mov     rcx, [rbx+28h]; ho
0x180042350  test    rcx, rcx
0x180042353  jz      short loc_180042363
0x180042355  call    cs:__imp_DeleteObject
0x18004235b  mov     qword ptr [rbx+28h], 0
0x180042363  mov     rcx, [rbx+30h]; ho
0x180042367  test    rcx, rcx
0x18004236a  jz      short loc_18004237A
0x18004236c  call    cs:__imp_DeleteObject
0x180042372  mov     qword ptr [rbx+30h], 0
0x18004237a  lea     rax, ??_7Unknown@@6B@; const Unknown::`vftable'
0x180042381  mov     [rbx+8], rax
0x180042385  lock dec cs:?g_uObjects@@3KA; ulong g_uObjects
0x18004238c  add     rsp, 20h
0x180042390  pop     rbx
0x180042391  retn
```
