# CabWriter::FciGetOpenInfo(char *,ushort *,ushort *,ushort *,int *,void *)

- ea: `0x180069ec0`
- end: `0x18006a06c`
- name: `?FciGetOpenInfo@CabWriter@@CA_JPEADPEAG11PEAHPEAX@Z`
- size: `428`
- prototype: `INT_PTR __cdecl(LPSTR pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err, void *pv)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180030f64`
- `0x1800358c0`
- `0x180068d54`
- `0x180069740`
- `0x180069ec0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180069f41`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180069f41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a025`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a025`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180069f9e`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180069f9e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180069f6a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180069f6a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x180069fb2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x180069fb2`

## pseudocode

```c
_QWORD *__fastcall CabWriter::FciGetOpenInfo(
        const CHAR *pszName,
        USHORT *pdate,
        USHORT *ptime,
        USHORT *pattribs,
        int *err,
        UINT *pv)
{
  __int64 v6; // rsi
  int Error; // ebx
  bool v11; // zf
  USHORT v12; // dx
  USHORT v13; // cx
  USHORT v14; // dx
  USHORT v15; // ax
  LPCWCH lpString1; // [rsp+30h] [rbp-50h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+38h] [rbp-48h] BYREF
  USHORT *v19; // [rsp+40h] [rbp-40h]
  int *v20; // [rsp+48h] [rbp-38h]
  __int128 FileInformation; // [rsp+50h] [rbp-30h] BYREF
  FILETIME FileTime[2]; // [rsp+60h] [rbp-20h] BYREF
  int v23; // [rsp+70h] [rbp-10h]

  v6 = -1;
  v19 = pattribs;
  v20 = err;
  if ( !pv )
    return (_QWORD *)v6;
  lpString1 = 0;
  Error = AnsiToUnicodeWithAlloc(*pv, pszName, (unsigned __int16 **)&lpString1);
  if ( Error < 0 )
    return (_QWORD *)v6;
  if ( CompareStringOrdinal(lpString1, -1, "?", -1, 0) != 2 )
  {
    v23 = 0;
    FileInformation = 0;
    *(_OWORD *)&FileTime[0].dwLowDateTime = 0;
    if ( GetFileAttributesExW(lpString1, GetFileExInfoStandard, &FileInformation) )
    {
      v11 = (pv[474] & 1) == 0;
      LocalFileTime = 0;
      if ( !v11 )
      {
        *pdate = 0;
        *ptime = 0;
LABEL_11:
        v12 = FileInformation & 0x20 | 4;
        if ( (FileInformation & 4) == 0 )
          v12 = FileInformation & 0x20;
        v13 = v12 | 2;
        if ( (FileInformation & 2) == 0 )
          v13 = v12;
        v14 = v13 | 1;
        if ( (FileInformation & 1) == 0 )
          v14 = v13;
        v15 = v14 | 0x80;
        if ( *pv != 65001 )
          v15 = v14;
        *v19 = v15;
        goto LABEL_20;
      }
      if ( FileTimeToLocalFileTime((const FILETIME *)&FileTime[0].dwHighDateTime, &LocalFileTime)
        && FileTimeToDosDateTime(&LocalFileTime, pdate, ptime) )
      {
        Error = 0;
        goto LABEL_11;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_11;
    }
  }
LABEL_20:
  CoTaskMemFree((LPVOID)lpString1);
  if ( Error >= 0 )
    return CabWriter::FciFileOpen(pszName, 0x8000, 0, (DWORD *)v20, pv);
  return (_QWORD *)v6;
}

```

## disassembly

```asm
0x180069ec0  push    rbp
0x180069ec2  push    rbx
0x180069ec3  push    rsi
0x180069ec4  push    rdi
0x180069ec5  push    r12
0x180069ec7  push    r13
0x180069ec9  push    r15
0x180069ecb  mov     rbp, rsp
0x180069ece  sub     rsp, 80h
0x180069ed5  mov     rax, cs:__security_cookie
0x180069edc  xor     rax, rsp
0x180069edf  mov     [rbp+var_8], rax
0x180069ee3  mov     rdi, [rbp+pv]
0x180069ee7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180069eeb  mov     rax, [rbp+err]
0x180069eef  mov     r12, r8
0x180069ef2  mov     [rbp+var_40], r9
0x180069ef6  mov     r15, rdx
0x180069ef9  mov     [rbp+var_38], rax
0x180069efd  mov     r13, rcx
0x180069f00  test    rdi, rdi
0x180069f03  jz      loc_18006A04B
0x180069f09  mov     rdx, rcx; lpMultiByteStr
0x180069f0c  mov     [rbp+lpString1], 0
0x180069f14  mov     ecx, [rdi]; CodePage
0x180069f16  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x180069f1a  call    ?AnsiToUnicodeWithAlloc@@YAJIPEBDPEAPEAG@Z; AnsiToUnicodeWithAlloc(uint,char const *,ushort * *)
0x180069f1f  mov     ebx, eax
0x180069f21  test    eax, eax
0x180069f23  js      loc_18006A04B
0x180069f29  mov     rcx, [rbp+lpString1]; lpString1
0x180069f2d  lea     r8, asc_18007B88C; "?"
0x180069f34  mov     r9d, esi; cchCount2
0x180069f37  mov     [rsp+80h+bIgnoreCase], 0; bIgnoreCase
0x180069f3f  mov     edx, esi; cchCount1
0x180069f41  call    cs:__imp_CompareStringOrdinal
0x180069f47  cmp     eax, 2
0x180069f4a  jz      loc_18006A021
0x180069f50  mov     rcx, [rbp+lpString1]; lpFileName
0x180069f54  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180069f58  xorps   xmm0, xmm0
0x180069f5b  xor     eax, eax
0x180069f5d  xor     edx, edx; fInfoLevelId
0x180069f5f  mov     [rbp+var_10], eax
0x180069f62  movups  [rbp+FileInformation], xmm0
0x180069f66  movups  xmmword ptr [rbp+FileTime.dwLowDateTime], xmm0
0x180069f6a  call    cs:__imp_GetFileAttributesExW
0x180069f70  test    eax, eax
0x180069f72  jz      loc_18006A021
0x180069f78  test    byte ptr [rdi+768h], 1
0x180069f7f  mov     qword ptr [rbp+LocalFileTime.dwLowDateTime], 0
0x180069f87  jz      short loc_180069F96
0x180069f89  xor     eax, eax
0x180069f8b  mov     [r15], ax
0x180069f8f  mov     [r12], ax
0x180069f94  jmp     short loc_180069FCB
0x180069f96  lea     rdx, [rbp+LocalFileTime]; lpLocalFileTime
0x180069f9a  lea     rcx, [rbp+FileTime.dwHighDateTime]; lpFileTime
0x180069f9e  call    cs:__imp_FileTimeToLocalFileTime
0x180069fa4  test    eax, eax
0x180069fa6  jz      short loc_180069FC0
0x180069fa8  mov     r8, r12; lpFatTime
0x180069fab  lea     rcx, [rbp+LocalFileTime]; lpFileTime
0x180069faf  mov     rdx, r15; lpFatDate
0x180069fb2  call    cs:__imp_FileTimeToDosDateTime
0x180069fb8  test    eax, eax
0x180069fba  jz      short loc_180069FC0
0x180069fbc  xor     ebx, ebx
0x180069fbe  jmp     short loc_180069FCB
0x180069fc0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180069fc5  mov     ebx, eax
0x180069fc7  test    eax, eax
0x180069fc9  js      short loc_18006A021
0x180069fcb  mov     r8d, dword ptr [rbp+FileInformation]
0x180069fcf  mov     r9d, 2
0x180069fd5  movzx   ecx, word ptr [rbp+FileInformation]
0x180069fd9  and     cx, 20h
0x180069fdd  movzx   edx, cx
0x180069fe0  or      dx, 4
0x180069fe4  test    r8b, 4
0x180069fe8  cmovz   dx, cx
0x180069fec  movzx   ecx, dx
0x180069fef  or      cx, r9w
0x180069ff3  test    r9b, r8b
0x180069ff6  cmovz   cx, dx
0x180069ffa  movzx   edx, cx
0x180069ffd  or      dx, 1
0x18006a001  test    r8b, 1
0x18006a005  cmovz   dx, cx
0x18006a009  mov     rcx, [rbp+var_40]
0x18006a00d  movzx   eax, dx
0x18006a010  or      ax, 80h
0x18006a014  cmp     dword ptr [rdi], 0FDE9h
0x18006a01a  cmovnz  ax, dx
0x18006a01e  mov     [rcx], ax
0x18006a021  mov     rcx, [rbp+lpString1]; pv
0x18006a025  call    cs:__imp_CoTaskMemFree
0x18006a02b  test    ebx, ebx
0x18006a02d  js      short loc_18006A04B
0x18006a02f  mov     r9, [rbp+var_38]; err
0x18006a033  xor     r8d, r8d; pmode
0x18006a036  mov     edx, 8000h; oflag
0x18006a03b  mov     qword ptr [rsp+80h+bIgnoreCase], rdi; pv
0x18006a040  mov     rcx, r13; pszFile
0x18006a043  call    ?FciFileOpen@CabWriter@@CA_JPEADHHPEAHPEAX@Z; CabWriter::FciFileOpen(char *,int,int,int *,void *)
0x18006a048  mov     rsi, rax
0x18006a04b  mov     rax, rsi
0x18006a04e  mov     rcx, [rbp+var_8]
0x18006a052  xor     rcx, rsp; StackCookie
0x18006a055  call    __security_check_cookie
0x18006a05a  add     rsp, 80h
0x18006a061  pop     r15
0x18006a063  pop     r13
0x18006a065  pop     r12
0x18006a067  pop     rdi
0x18006a068  pop     rsi
0x18006a069  pop     rbx
0x18006a06a  pop     rbp
0x18006a06b  retn
```
