# CRun::AdvanceKillTime(_FILETIME)

- ea: `0x18002d450`
- end: `0x18002d485`
- name: `?AdvanceKillTime@CRun@@QEAAXU_FILETIME@@@Z`
- size: `53`
- prototype: `void __fastcall(CRun *__hidden this, struct _FILETIME)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d268`

## callees

- `0x18002d450`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d466`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d466`

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
0x18002d450  mov     qword ptr [rsp+FileTime1.dwLowDateTime], rdx
0x18002d455  push    rbx
0x18002d456  sub     rsp, 20h
0x18002d45a  lea     rbx, [rcx+28h]
0x18002d45e  mov     rdx, rbx; lpFileTime2
0x18002d461  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x18002d466  call    cs:__imp_CompareFileTime
0x18002d46d  nop     dword ptr [rax+rax+00h]
0x18002d472  test    eax, eax
0x18002d474  jns     short loc_18002D47E
0x18002d476  mov     rax, qword ptr [rsp+28h+FileTime1.dwLowDateTime]
0x18002d47b  mov     [rbx], rax
0x18002d47e  add     rsp, 20h
0x18002d482  pop     rbx
0x18002d483  retn
```
