# GetDurationUTC

- ea: `0x180026290`
- end: `0x18002635a`
- name: `GetDurationUTC`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180024cac`

## callees

- `0x180026290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026338`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800262b2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800262cd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800262b2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800262cd`
- `KERNEL32!CompareFileTime` at `0x1800262eb`
- `KERNEL32!CompareFileTime` at `0x1800262eb`

## pseudocode

```c
signed int __fastcall GetDurationUTC(const SYSTEMTIME *a1, const SYSTEMTIME *a2, _QWORD *a3)
{
  FILETIME v5; // rbx
  struct _FILETIME v6; // rdi
  LONG v7; // ecx
  unsigned __int128 v8; // rax
  unsigned __int64 v9; // rdx
  signed int result; // eax
  struct _FILETIME FileTime; // [rsp+20h] [rbp-18h] BYREF
  FILETIME FileTime2; // [rsp+58h] [rbp+20h] BYREF

  FileTime2 = 0;
  if ( SystemTimeToFileTime(a1, &FileTime2)
    && (FileTime = 0, SystemTimeToFileTime(a2, &FileTime))
    && ((v5 = FileTime2, v6 = FileTime, v7 = CompareFileTime(&FileTime, &FileTime2), v7 >= 0)
      ? (v8 = (unsigned __int64)(*(_QWORD *)&v6 - *(_QWORD *)&v5) * (unsigned __int128)0x346DC5D63886594BuLL)
      : (v8 = (unsigned __int64)(*(_QWORD *)&v5 - *(_QWORD *)&v6) * (unsigned __int128)0x346DC5D63886594BuLL),
        v9 = *((_QWORD *)&v8 + 1) >> 11,
        v9 <= 0x7FFFFFFFFFFFFFFFLL) )
  {
    *a3 = v9 * (int)(((v7 >> 31) & 0xFFFFFFFE) + 1);
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180026290  mov     rax, rsp
0x180026293  mov     [rax+8], rbx
0x180026297  mov     [rax+10h], rsi
0x18002629b  push    rdi
0x18002629c  sub     rsp, 30h
0x1800262a0  mov     rbx, rdx
0x1800262a3  mov     qword ptr [rax+20h], 0
0x1800262ab  lea     rdx, [rax+20h]; lpFileTime
0x1800262af  mov     rsi, r8
0x1800262b2  call    cs:__imp_SystemTimeToFileTime
0x1800262b8  test    eax, eax
0x1800262ba  jz      short loc_180026338
0x1800262bc  lea     rdx, [rsp+38h+FileTime]; lpFileTime
0x1800262c1  mov     qword ptr [rsp+38h+FileTime.dwLowDateTime], 0
0x1800262ca  mov     rcx, rbx; lpSystemTime
0x1800262cd  call    cs:__imp_SystemTimeToFileTime
0x1800262d3  test    eax, eax
0x1800262d5  jz      short loc_180026338
0x1800262d7  mov     rbx, qword ptr [rsp+38h+FileTime2.dwLowDateTime]
0x1800262dc  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x1800262e1  mov     rdi, qword ptr [rsp+38h+FileTime.dwLowDateTime]
0x1800262e6  lea     rcx, [rsp+38h+FileTime]; lpFileTime1
0x1800262eb  call    cs:__imp_CompareFileTime
0x1800262f1  mov     ecx, eax
0x1800262f3  test    eax, eax
0x1800262f5  mov     rax, 346DC5D63886594Bh
0x1800262ff  jns     short loc_180026309
0x180026301  sub     rbx, rdi
0x180026304  mul     rbx
0x180026307  jmp     short loc_18002630F
0x180026309  sub     rdi, rbx
0x18002630c  mul     rdi
0x18002630f  shr     rdx, 0Bh
0x180026313  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002631d  cmp     rdx, rax
0x180026320  ja      short loc_180026338
0x180026322  sar     ecx, 1Fh
0x180026325  and     ecx, 0FFFFFFFEh
0x180026328  lea     eax, [rcx+1]
0x18002632b  cdqe
0x18002632d  imul    rax, rdx
0x180026331  mov     [rsi], rax
0x180026334  xor     eax, eax
0x180026336  jmp     short loc_18002634A
0x180026338  call    cs:__imp_GetLastError
0x18002633e  test    eax, eax
0x180026340  jle     short loc_18002634A
0x180026342  movzx   eax, ax
0x180026345  or      eax, 80070000h
0x18002634a  mov     rbx, [rsp+38h+arg_0]
0x18002634f  mov     rsi, [rsp+38h+arg_8]
0x180026354  add     rsp, 30h
0x180026358  pop     rdi
0x180026359  retn
```
