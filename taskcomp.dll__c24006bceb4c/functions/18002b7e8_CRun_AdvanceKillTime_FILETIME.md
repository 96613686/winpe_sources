# CRun::AdvanceKillTime(_FILETIME)

- ea: `0x18002b7e8`
- end: `0x18002b816`
- name: `?AdvanceKillTime@CRun@@QEAAXU_FILETIME@@@Z`
- size: `46`
- prototype: `void __fastcall(const FILETIME *this, FILETIME)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002b618`

## callees

- `0x18002b7e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002b7fe`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002b7fe`

## pseudocode

```c
void __fastcall CRun::AdvanceKillTime(const FILETIME *this, FILETIME a2)
{
  FILETIME *v2; // rbx
  FILETIME FileTime1; // [rsp+38h] [rbp+10h] BYREF

  FileTime1 = a2;
  v2 = (FILETIME *)&this[5];
  if ( CompareFileTime(&FileTime1, this + 5) < 0 )
    *v2 = FileTime1;
}

```

## disassembly

```asm
0x18002b7e8  mov     qword ptr [rsp+FileTime1.dwLowDateTime], rdx
0x18002b7ed  push    rbx
0x18002b7ee  sub     rsp, 20h
0x18002b7f2  lea     rbx, [rcx+28h]
0x18002b7f6  mov     rdx, rbx; lpFileTime2
0x18002b7f9  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x18002b7fe  call    cs:__imp_CompareFileTime
0x18002b804  test    eax, eax
0x18002b806  jns     short loc_18002B810
0x18002b808  mov     rax, qword ptr [rsp+28h+FileTime1.dwLowDateTime]
0x18002b80d  mov     [rbx], rax
0x18002b810  add     rsp, 20h
0x18002b814  pop     rbx
0x18002b815  retn
```
