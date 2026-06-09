# HyperVFile::UpdateLastWriteTime(void)

- ea: `0x1401d32e4`
- end: `0x1401d33c1`
- name: `?UpdateLastWriteTime@HyperVFile@@IEAAXXZ`
- size: `221`
- prototype: `void __fastcall(HyperVFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140055460`

## callees

- `0x140132960`
- `0x1401d32e4`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1401d3353`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1401d3353`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401d332a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401d3369`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401d332a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401d3369`

## pseudocode

```c
void __fastcall HyperVFile::UpdateLastWriteTime(HyperVFile *this)
{
  FILETIME *v2; // rbx
  FILETIME v3; // rax
  FILETIME FileTime1; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-20h] BYREF

  (*(void (__fastcall **)(_QWORD, FILETIME *))(**((_QWORD **)this + 75) + 168LL))(*((_QWORD *)this + 75), &FileTime1);
  v2 = (FILETIME *)((char *)this + 776);
  if ( CompareFileTime(&FileTime1, (const FILETIME *)this + 97) <= 0 )
  {
    v3 = (FILETIME)(*(_QWORD *)v2 + 1LL);
    SystemTimeAsFileTime = 0;
    FileTime1 = v3;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) < 0 )
      FileTime1 = SystemTimeAsFileTime;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 176LL))(*((_QWORD *)this + 75));
  }
  *v2 = FileTime1;
}

```

## disassembly

```asm
0x1401d32e4  mov     [rsp+arg_8], rbx
0x1401d32e9  push    rdi
0x1401d32ea  sub     rsp, 40h
0x1401d32ee  mov     rax, cs:__security_cookie
0x1401d32f5  xor     rax, rsp
0x1401d32f8  mov     [rsp+48h+var_18], rax
0x1401d32fd  mov     rdi, rcx
0x1401d3300  lea     rdx, [rsp+48h+FileTime1]
0x1401d3305  mov     rcx, [rcx+258h]
0x1401d330c  mov     rax, [rcx]
0x1401d330f  mov     rax, [rax+0A8h]
0x1401d3316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401d331b  lea     rbx, [rdi+308h]
0x1401d3322  mov     rdx, rbx; lpFileTime2
0x1401d3325  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x1401d332a  call    cs:__imp_CompareFileTime
0x1401d3331  nop     dword ptr [rax+rax+00h]
0x1401d3336  test    eax, eax
0x1401d3338  jg      short loc_1401D33A0
0x1401d333a  mov     rax, [rbx]
0x1401d333d  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1401d3342  inc     rax
0x1401d3345  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1401d334e  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], rax
0x1401d3353  call    cs:__imp_GetSystemTimeAsFileTime
0x1401d335a  nop     dword ptr [rax+rax+00h]
0x1401d335f  lea     rdx, [rsp+48h+SystemTimeAsFileTime]; lpFileTime2
0x1401d3364  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x1401d3369  call    cs:__imp_CompareFileTime
0x1401d3370  nop     dword ptr [rax+rax+00h]
0x1401d3375  test    eax, eax
0x1401d3377  jns     short loc_1401D3385
0x1401d3379  mov     rdx, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x1401d337e  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], rdx
0x1401d3383  jmp     short loc_1401D338A
0x1401d3385  mov     rdx, qword ptr [rsp+48h+FileTime1.dwLowDateTime]
0x1401d338a  mov     rcx, [rdi+258h]
0x1401d3391  mov     rax, [rcx]
0x1401d3394  mov     rax, [rax+0B0h]
0x1401d339b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401d33a0  mov     rax, qword ptr [rsp+48h+FileTime1.dwLowDateTime]
0x1401d33a5  mov     [rbx], rax
0x1401d33a8  mov     rcx, [rsp+48h+var_18]
0x1401d33ad  xor     rcx, rsp; StackCookie
0x1401d33b0  call    __security_check_cookie
0x1401d33b5  mov     rbx, [rsp+48h+arg_8]
0x1401d33ba  add     rsp, 40h
0x1401d33be  pop     rdi
0x1401d33bf  retn
```
