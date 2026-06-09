# CLogFile::ReadExtendedHeader(ulong,void *,ulong)

- ea: `0x18000cf58`
- end: `0x18000cfc8`
- name: `?ReadExtendedHeader@CLogFile@@QEAAXKPEAXK@Z`
- size: `112`
- prototype: `void __fastcall(CLogFile *this, unsigned int, void *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a1bc`
- `0x18000c430`

## callees

- `0x18000cf58`
- `0x18000cfd0`
- `0x180010fbe`
- `0x180010fca`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cfa6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cfa6`

## pseudocode

```c
void __fastcall CLogFile::ReadExtendedHeader(CLogFile *this, unsigned int a2, void *a3, unsigned int a4)
{
  __int64 v4; // rsi
  __int64 v6; // r14
  char *v7; // rbx

  v4 = a4;
  v6 = a2;
  v7 = (char *)this + 80;
  CLogFileHeader::RaiseIfNotOpen((CLogFile *)((char *)this + 80));
  if ( v4 + v6 + 40 > (unsigned __int64)*((unsigned int *)v7 + 8) )
  {
    RaiseException(0x8DEAD001, 0, 0, 0);
    __debugbreak();
  }
  memcpy_0(a3, (const void *)(*((_QWORD *)v7 + 3) + (unsigned int)v6), (unsigned int)v4);
}

```

## disassembly

```asm
0x18000cf58  mov     [rsp+arg_0], rbx
0x18000cf5d  mov     [rsp+arg_18], r9d
0x18000cf62  mov     [rsp+arg_10], r8
0x18000cf67  push    rsi
0x18000cf68  push    rdi
0x18000cf69  push    r14
0x18000cf6b  sub     rsp, 20h
0x18000cf6f  mov     esi, r9d
0x18000cf72  mov     rdi, r8
0x18000cf75  mov     r14d, edx
0x18000cf78  lea     rbx, [rcx+50h]
0x18000cf7c  mov     rcx, rbx; this
0x18000cf7f  call    ?RaiseIfNotOpen@CLogFileHeader@@AEBAXXZ; CLogFileHeader::RaiseIfNotOpen(void)
0x18000cf84  mov     r8d, esi; Size
0x18000cf87  mov     edx, r14d
0x18000cf8a  lea     rcx, [r14+28h]
0x18000cf8e  add     rcx, rsi
0x18000cf91  mov     eax, [rbx+20h]
0x18000cf94  cmp     rcx, rax
0x18000cf97  jbe     short loc_18000CFAD
0x18000cf99  xor     r9d, r9d; lpArguments
0x18000cf9c  xor     r8d, r8d; nNumberOfArguments
0x18000cf9f  xor     edx, edx; dwExceptionFlags
0x18000cfa1  mov     ecx, 8DEAD001h; dwExceptionCode
0x18000cfa6  call    cs:__imp_RaiseException
0x18000cfac  int     3; Trap to Debugger
0x18000cfad  add     rdx, [rbx+18h]; Src
0x18000cfb1  mov     rcx, rdi; void *
0x18000cfb4  call    memcpy_0
0x18000cfb9  nop
0x18000cfba  mov     rbx, [rsp+38h+arg_0]
0x18000cfbf  add     rsp, 20h
0x18000cfc3  pop     r14
0x18000cfc5  pop     rdi
0x18000cfc6  pop     rsi
0x18000cfc7  retn
0x18001186c  push    rbp
0x18001186e  sub     rsp, 20h
0x180011872  mov     rbp, rdx
0x180011875  test    cl, cl
0x180011877  jz      short loc_180011889
0x180011879  mov     r8d, [rbp+58h]; Size
0x18001187d  xor     edx, edx; Val
0x18001187f  mov     rcx, [rbp+50h]; void *
0x180011883  call    memset_0
0x180011888  nop
0x180011889  add     rsp, 20h
0x18001188d  pop     rbp
0x18001188e  retn
```
