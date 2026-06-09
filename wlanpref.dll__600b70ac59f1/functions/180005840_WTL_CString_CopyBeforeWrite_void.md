# WTL::CString::CopyBeforeWrite(void)

- ea: `0x180005840`
- end: `0x18000589e`
- name: `?CopyBeforeWrite@CString@WTL@@IEAAXXZ`
- size: `94`
- prototype: `void __fastcall(WTL::CString *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b888`
- `0x180011190`
- `0x180012d4c`
- `0x18002c5e8`
- `0x18002c674`

## callees

- `0x1800048d4`
- `0x180004c00`
- `0x180005840`
- `0x18000b810`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005886`
- `msvcrt!memcpy_s` at `0x180005886`

## pseudocode

```c
void __fastcall WTL::CString::CopyBeforeWrite(WTL::CString *this)
{
  const void *v1; // rdi
  errno_t v3; // eax

  v1 = *(const void **)this;
  if ( *(int *)(*(_QWORD *)this - 12LL) > 1 )
  {
    WTL::CString::Release(this);
    if ( (unsigned int)WTL::CString::AllocBuffer(this, *((_DWORD *)v1 - 2)) )
    {
      v3 = memcpy_s(
             *(void *const *)this,
             2LL * (*(_DWORD *)(*(_QWORD *)this - 4LL) + 1),
             v1,
             2LL * (*((_DWORD *)v1 - 2) + 1));
      ATL::AtlCrtErrorCheck(v3);
    }
  }
}

```

## disassembly

```asm
0x180005840  mov     [rsp+arg_0], rbx
0x180005845  push    rdi
0x180005846  sub     rsp, 20h
0x18000584a  mov     rdi, [rcx]
0x18000584d  mov     rbx, rcx
0x180005850  cmp     dword ptr [rdi-0Ch], 1
0x180005854  jle     short loc_180005893
0x180005856  call    ?Release@CString@WTL@@IEAAXXZ; WTL::CString::Release(void)
0x18000585b  mov     edx, [rdi-8]; int
0x18000585e  mov     rcx, rbx; this
0x180005861  call    ?AllocBuffer@CString@WTL@@IEAAHH@Z; WTL::CString::AllocBuffer(int)
0x180005866  test    eax, eax
0x180005868  jz      short loc_180005893
0x18000586a  mov     rcx, [rbx]; Destination
0x18000586d  mov     r8, rdi; Source
0x180005870  mov     eax, [rdi-8]
0x180005873  inc     eax
0x180005875  movsxd  r9, eax
0x180005878  mov     eax, [rcx-4]
0x18000587b  add     r9, r9; SourceSize
0x18000587e  inc     eax
0x180005880  movsxd  rdx, eax
0x180005883  add     rdx, rdx; DestinationSize
0x180005886  call    cs:__imp_memcpy_s
0x18000588c  mov     ecx, eax; int
0x18000588e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005893  mov     rbx, [rsp+28h+arg_0]
0x180005898  add     rsp, 20h
0x18000589c  pop     rdi
0x18000589d  retn
```
