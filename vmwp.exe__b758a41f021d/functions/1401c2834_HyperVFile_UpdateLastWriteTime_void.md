# HyperVFile::UpdateLastWriteTime(void)

- ea: `0x1401c2834`
- end: `0x1401c2911`
- name: `?UpdateLastWriteTime@HyperVFile@@IEAAXXZ`
- size: `221`
- prototype: `void __fastcall(HyperVFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140055130`

## callees

- `0x14011ea40`
- `0x1401c2834`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1401c28a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1401c28a3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401c287a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401c28b9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401c287a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401c28b9`

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
0x1401c2834  mov     [rsp+arg_8], rbx
0x1401c2839  push    rdi
0x1401c283a  sub     rsp, 40h
0x1401c283e  mov     rax, cs:__security_cookie
0x1401c2845  xor     rax, rsp
0x1401c2848  mov     [rsp+48h+var_18], rax
0x1401c284d  mov     rdi, rcx
0x1401c2850  lea     rdx, [rsp+48h+FileTime1]
0x1401c2855  mov     rcx, [rcx+258h]
0x1401c285c  mov     rax, [rcx]
0x1401c285f  mov     rax, [rax+0A8h]
0x1401c2866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c286b  lea     rbx, [rdi+308h]
0x1401c2872  mov     rdx, rbx; lpFileTime2
0x1401c2875  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x1401c287a  call    cs:__imp_CompareFileTime
0x1401c2881  nop     dword ptr [rax+rax+00h]
0x1401c2886  test    eax, eax
0x1401c2888  jg      short loc_1401C28F0
0x1401c288a  mov     rax, [rbx]
0x1401c288d  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1401c2892  inc     rax
0x1401c2895  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1401c289e  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], rax
0x1401c28a3  call    cs:__imp_GetSystemTimeAsFileTime
0x1401c28aa  nop     dword ptr [rax+rax+00h]
0x1401c28af  lea     rdx, [rsp+48h+SystemTimeAsFileTime]; lpFileTime2
0x1401c28b4  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x1401c28b9  call    cs:__imp_CompareFileTime
0x1401c28c0  nop     dword ptr [rax+rax+00h]
0x1401c28c5  test    eax, eax
0x1401c28c7  jns     short loc_1401C28D5
0x1401c28c9  mov     rdx, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x1401c28ce  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], rdx
0x1401c28d3  jmp     short loc_1401C28DA
0x1401c28d5  mov     rdx, qword ptr [rsp+48h+FileTime1.dwLowDateTime]
0x1401c28da  mov     rcx, [rdi+258h]
0x1401c28e1  mov     rax, [rcx]
0x1401c28e4  mov     rax, [rax+0B0h]
0x1401c28eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c28f0  mov     rax, qword ptr [rsp+48h+FileTime1.dwLowDateTime]
0x1401c28f5  mov     [rbx], rax
0x1401c28f8  mov     rcx, [rsp+48h+var_18]
0x1401c28fd  xor     rcx, rsp; StackCookie
0x1401c2900  call    __security_check_cookie
0x1401c2905  mov     rbx, [rsp+48h+arg_8]
0x1401c290a  add     rsp, 40h
0x1401c290e  pop     rdi
0x1401c290f  retn
```
