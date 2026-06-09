# CThumbnailCacheIndex::_InitializeNewIndexFile(void *,uint)

- ea: `0x1800258dc`
- end: `0x1800259fa`
- name: `?_InitializeNewIndexFile@CThumbnailCacheIndex@@AEAAJPEAXI@Z`
- size: `286`
- prototype: `int(CThumbnailCacheIndex *__hidden this, void *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18002556c`
- `0x180028d00`

## callees

- `0x18000bfd8`
- `0x1800258dc`
- `0x180025a8c`
- `0x180025b4c`
- `0x180025c94`
- `0x1800346ec`
- `0x180035830`
- `0x1800364ac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180025977`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180025977`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180025914`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180025914`

## string_xrefs

- `0x18002599d`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbidx.cpp`
- `0x1800259e1`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbidx.cpp`

## pseudocode

```c
__int64 __fastcall CThumbnailCacheIndex::_InitializeNewIndexFile(CThumbnailCacheIndex *this, void *a2, int a3)
{
  const char *v5; // r9
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rdx
  int lpOverlapped; // [rsp+20h] [rbp-C8h]
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-B8h] BYREF
  unsigned int Buffer; // [rsp+40h] [rbp-A8h] BYREF
  _DWORD v13[35]; // [rsp+44h] [rbp-A4h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  NumberOfBytesWritten = 0;
  if ( SetFilePointer(a2, 0, 0, 0) == -1 )
  {
    v9 = 256;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
             v5);
  }
  memset_0(v13, 0, sizeof(v13));
  Buffer = GetSnapSizeCookie();
  v13[0] = 1296911689;
  v13[1] = 32;
  v13[5] = a3;
  v13[3] = GetGlobalAssocCounter();
  if ( !WriteFile(a2, &Buffer, 0x90u, &NumberOfBytesWritten, 0) )
  {
    v9 = 266;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
             v5);
  }
  v6 = WriteZerosToFile(a2, 72 * a3);
  v7 = v6;
  if ( v6 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10D,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
    (const char *)(unsigned int)v6,
    lpOverlapped);
  return v7;
}

```

## disassembly

```asm
0x1800258dc  mov     [rsp+arg_0], rbx
0x1800258e1  push    rdi
0x1800258e2  sub     rsp, 0E0h
0x1800258e9  mov     rax, cs:__security_cookie
0x1800258f0  xor     rax, rsp
0x1800258f3  mov     [rsp+0E8h+var_18], rax
0x1800258fb  mov     rdi, rdx
0x1800258fe  mov     [rsp+0E8h+NumberOfBytesWritten], 0
0x180025906  mov     ebx, r8d
0x180025909  mov     rcx, rdi; hFile
0x18002590c  xor     r9d, r9d; dwMoveMethod
0x18002590f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180025912  xor     edx, edx; lDistanceToMove
0x180025914  call    cs:__imp_SetFilePointer
0x18002591a  cmp     eax, 0FFFFFFFFh
0x18002591d  jz      loc_1800259EF
0x180025923  xor     edx, edx; Val
0x180025925  lea     rcx, [rsp+0E8h+var_A4]; void *
0x18002592a  mov     r8d, 8Ch; Size
0x180025930  call    memset_0
0x180025935  call    ?GetSnapSizeCookie@@YAKXZ; GetSnapSizeCookie(void)
0x18002593a  mov     [rsp+0E8h+Buffer], eax
0x18002593e  mov     [rsp+0E8h+var_A4], 4D4D4D49h
0x180025946  mov     [rsp+0E8h+var_A0], 20h ; ' '
0x18002594e  mov     [rsp+0E8h+var_90], ebx
0x180025952  call    GetGlobalAssocCounter
0x180025957  lea     r9, [rsp+0E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002595c  mov     [rsp+0E8h+var_98], eax
0x180025960  mov     r8d, 90h; nNumberOfBytesToWrite
0x180025966  mov     qword ptr [rsp+0E8h+lpOverlapped], 0; int
0x18002596f  lea     rdx, [rsp+0E8h+Buffer]; lpBuffer
0x180025974  mov     rcx, rdi; hFile
0x180025977  call    cs:__imp_WriteFile
0x18002597d  test    eax, eax
0x18002597f  jz      short loc_1800259D4
0x180025981  lea     edx, [rbx+rbx*8]
0x180025984  mov     rcx, rdi; void *
0x180025987  shl     edx, 3; unsigned int
0x18002598a  call    ?WriteZerosToFile@@YAJPEAXI@Z; WriteZerosToFile(void *,uint)
0x18002598f  mov     ebx, eax
0x180025991  test    eax, eax
0x180025993  jns     short loc_1800259F6
0x180025995  mov     rcx, [rsp+0E8h]; this
0x18002599d  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800259a4  mov     r9d, eax; char *
0x1800259a7  mov     edx, 10Dh; void *
0x1800259ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800259b1  mov     eax, ebx
0x1800259b3  mov     rcx, [rsp+0E8h+var_18]
0x1800259bb  xor     rcx, rsp; StackCookie
0x1800259be  call    __security_check_cookie
0x1800259c3  mov     rbx, [rsp+0E8h+arg_0]
0x1800259cb  add     rsp, 0E0h
0x1800259d2  pop     rdi
0x1800259d3  retn
0x1800259d4  mov     edx, 10Ah; void *
0x1800259d9  mov     rcx, [rsp+0E8h]; this
0x1800259e1  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800259e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800259ed  jmp     short loc_1800259B3
0x1800259ef  mov     edx, 100h
0x1800259f4  jmp     short loc_1800259D9
0x1800259f6  xor     eax, eax
0x1800259f8  jmp     short loc_1800259B3
```
