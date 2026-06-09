# NAdvancedLibrary::TCopyCritsec::TCopyCritsec(void)

- ea: `0x140013f74`
- end: `0x140013ff0`
- name: `??0TCopyCritsec@NAdvancedLibrary@@QEAA@XZ`
- size: `124`
- prototype: `__int64 __fastcall(NAdvancedLibrary::TCopyCritsec *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140010400`

## callees

- `0x140002198`
- `0x1400112c8`
- `0x140013f74`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140013fc5`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140013fc5`

## pseudocode

```c
NAdvancedLibrary::TCopyCritsec *__fastcall NAdvancedLibrary::TCopyCritsec::TCopyCritsec(
        NAdvancedLibrary::TCopyCritsec *this)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rbx
  NCoreLibrary *v4; // rcx
  int LastErrorAsFailHR; // eax

  v2 = operator new(0x38u, (const struct std::nothrow_t *)&NCoreLibrary::nothrow);
  v3 = v2;
  if ( v2 )
  {
    v2[10] = 0;
    v2[11] = 0;
    v2[12] = -2147467259;
    v2[11] = 0;
    v2[10] = 0;
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)v2, 0x80000000) )
      LastErrorAsFailHR = 0;
    else
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v4);
    v3[12] = LastErrorAsFailHR;
  }
  else
  {
    v3 = 0;
  }
  *(_QWORD *)this = v3;
  return this;
}

```

## disassembly

```asm
0x140013f74  mov     [rsp+arg_0], rbx
0x140013f79  push    rdi
0x140013f7a  sub     rsp, 20h
0x140013f7e  mov     rdi, rcx
0x140013f81  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x140013f88  mov     ecx, 38h ; '8'; unsigned __int64
0x140013f8d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140013f92  mov     rbx, rax
0x140013f95  test    rax, rax
0x140013f98  jz      short loc_140013FDD
0x140013f9a  mov     dword ptr [rax+28h], 0
0x140013fa1  mov     edx, 80000000h; dwSpinCount
0x140013fa6  mov     dword ptr [rax+2Ch], 0
0x140013fad  mov     rcx, rax; lpCriticalSection
0x140013fb0  mov     dword ptr [rax+30h], 80004005h
0x140013fb7  mov     dword ptr [rax+2Ch], 0
0x140013fbe  mov     dword ptr [rax+28h], 0
0x140013fc5  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140013fcb  test    eax, eax
0x140013fcd  jz      short loc_140013FD3
0x140013fcf  xor     eax, eax
0x140013fd1  jmp     short loc_140013FD8
0x140013fd3  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x140013fd8  mov     [rbx+30h], eax
0x140013fdb  jmp     short loc_140013FDF
0x140013fdd  xor     ebx, ebx
0x140013fdf  mov     [rdi], rbx
0x140013fe2  mov     rax, rdi
0x140013fe5  mov     rbx, [rsp+28h+arg_0]
0x140013fea  add     rsp, 20h
0x140013fee  pop     rdi
0x140013fef  retn
```
