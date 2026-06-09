# BfspSetSystemVolumePath

- ea: `0x180031e78`
- end: `0x180032064`
- name: `BfspSetSystemVolumePath`
- size: `492`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18000be9c`

## callees

- `0x180001df8`
- `0x180031e78`
- `0x18007ec82`
- `0x18007ed40`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180031f02`
- `msvcrt!wcscpy_s` at `0x180031f79`
- `msvcrt!wcscpy_s` at `0x180031f02`
- `msvcrt!wcscpy_s` at `0x180031f79`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180031f38`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180031f38`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180031f18`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180031f18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ff4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032005`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032005`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180031f5e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180031f5e`

## pseudocode

```c
__int64 __fastcall BfspSetSystemVolumePath(LPCWSTR lpszFileName)
{
  unsigned int v2; // ebx
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rax
  SIZE_T v5; // rsi
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  HANDLE ProcessHeap; // rax
  void *v11; // rax
  __int16 v13; // [rsp+2Eh] [rbp-D2h]
  wchar_t Destination; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v15; // [rsp+32h] [rbp-CEh]
  WCHAR szVolumeName[56]; // [rsp+240h] [rbp+140h] BYREF

  if ( !lpszFileName )
  {
    v2 = 0;
    BfspSystemPartitionName = 0;
    return v2;
  }
  if ( *lpszFileName == 92 )
  {
    v3 = -1;
    do
      ++v3;
    while ( lpszFileName[v3] );
    v4 = 2 * v3;
    if ( is_mul_ok(v3, 2u) )
    {
      v5 = v4 + 2;
      if ( v4 + 2 >= v4 )
      {
        v2 = 0;
        wcscpy_s(&Destination, 0x104u, lpszFileName);
        goto LABEL_25;
      }
    }
    return (unsigned int)-1073741675;
  }
  v6 = -1;
  if ( !QueryDosDeviceW(lpszFileName, &Destination, 0x104u) )
  {
    if ( !GetVolumePathNameW(lpszFileName, &Destination, 0x104u)
      || !GetVolumeNameForVolumeMountPointW(&Destination, szVolumeName, 0x32u) )
    {
      return (unsigned int)-1073741811;
    }
    wcscpy_s(&Destination, 0x104u, szVolumeName);
    v7 = -1;
    do
      ++v7;
    while ( *(&Destination + v7) );
    if ( v7 > 1 )
    {
      if ( v15 == 92 )
        v15 = 63;
      if ( *(&v13 + v7) == 92 )
      {
        v8 = 2 * v7 - 2;
        if ( v8 >= 0x208 )
          _report_rangecheckfailure();
        *(wchar_t *)((char *)&Destination + v8) = 0;
      }
    }
  }
  do
    ++v6;
  while ( *(&Destination + v6) );
  v9 = 2 * v6;
  if ( !is_mul_ok(v6, 2u) )
    return (unsigned int)-1073741675;
  v5 = v9 + 2;
  if ( v9 + 2 < v9 )
    return (unsigned int)-1073741675;
  v2 = 0;
LABEL_25:
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, v5);
  BfspSystemPartitionName = v11;
  if ( v11 )
    memcpy_0(v11, &Destination, v5);
  else
    return (unsigned int)-1073741801;
  return v2;
}

```

## disassembly

```asm
0x180031e78  mov     [rsp-8+arg_8], rbx
0x180031e7d  mov     [rsp-8+arg_10], rsi
0x180031e82  push    rbp
0x180031e83  push    rdi
0x180031e84  push    r15
0x180031e86  lea     rbp, [rsp-1C0h]
0x180031e8e  sub     rsp, 2C0h
0x180031e95  mov     rax, cs:__security_cookie
0x180031e9c  xor     rax, rsp
0x180031e9f  mov     [rbp+1D0h+var_20], rax
0x180031ea6  xor     r15d, r15d
0x180031ea9  mov     rdi, rcx
0x180031eac  test    rcx, rcx
0x180031eaf  jnz     short loc_180031EC0
0x180031eb1  mov     ebx, r15d
0x180031eb4  mov     cs:BfspSystemPartitionName, r15
0x180031ebb  jmp     loc_180032035
0x180031ec0  cmp     word ptr [rcx], 5Ch ; '\'
0x180031ec4  jnz     short loc_180031F0D
0x180031ec6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180031eca  inc     rbx
0x180031ecd  cmp     [rcx+rbx*2], r15w
0x180031ed2  jnz     short loc_180031ECA
0x180031ed4  mov     eax, 2
0x180031ed9  mul     rbx
0x180031edc  test    rdx, rdx
0x180031edf  jnz     loc_180032030
0x180031ee5  lea     rsi, [rax+2]
0x180031ee9  cmp     rsi, rax
0x180031eec  jb      loc_180032030
0x180031ef2  mov     r8, rdi; Source
0x180031ef5  lea     rcx, [rsp+2D0h+Destination]; Destination
0x180031efa  mov     edx, 104h; SizeInWords
0x180031eff  mov     ebx, r15d
0x180031f02  call    cs:__imp_wcscpy_s
0x180031f08  jmp     loc_180031FF4
0x180031f0d  mov     r8d, 104h; ucchMax
0x180031f13  lea     rdx, [rsp+2D0h+Destination]; lpTargetPath
0x180031f18  call    cs:__imp_QueryDosDeviceW
0x180031f1e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180031f22  test    eax, eax
0x180031f24  jnz     loc_180031FCC
0x180031f2a  mov     r8d, 104h; cchBufferLength
0x180031f30  lea     rdx, [rsp+2D0h+Destination]; lpszVolumePathName
0x180031f35  mov     rcx, rdi; lpszFileName
0x180031f38  call    cs:__imp_GetVolumePathNameW
0x180031f3e  test    eax, eax
0x180031f40  jnz     short loc_180031F4C
0x180031f42  mov     ebx, 0C000000Dh
0x180031f47  jmp     loc_180032035
0x180031f4c  mov     r8d, 32h ; '2'; cchBufferLength
0x180031f52  lea     rdx, [rbp+1D0h+szVolumeName]; lpszVolumeName
0x180031f59  lea     rcx, [rsp+2D0h+Destination]; lpszVolumeMountPoint
0x180031f5e  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180031f64  test    eax, eax
0x180031f66  jz      short loc_180031F42
0x180031f68  lea     r8, [rbp+1D0h+szVolumeName]; Source
0x180031f6f  mov     edx, 104h; SizeInWords
0x180031f74  lea     rcx, [rsp+2D0h+Destination]; Destination
0x180031f79  call    cs:__imp_wcscpy_s
0x180031f7f  lea     rcx, [rsp+2D0h+Destination]
0x180031f84  mov     rax, rbx
0x180031f87  inc     rax
0x180031f8a  cmp     [rcx+rax*2], r15w
0x180031f8f  jnz     short loc_180031F87
0x180031f91  cmp     rax, 1
0x180031f95  jbe     short loc_180031FCC
0x180031f97  cmp     [rsp+2D0h+var_29E], 5Ch ; '\'
0x180031f9d  jnz     short loc_180031FA9
0x180031f9f  mov     ecx, 3Fh ; '?'
0x180031fa4  mov     [rsp+2D0h+var_29E], cx
0x180031fa9  cmp     [rsp+rax*2+2D0h+var_2A2], 5Ch ; '\'
0x180031faf  jnz     short loc_180031FCC
0x180031fb1  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180031fb9  cmp     rcx, 208h
0x180031fc0  jnb     loc_18003205E
0x180031fc6  mov     [rsp+rcx+2D0h+Destination], r15w
0x180031fcc  lea     rax, [rsp+2D0h+Destination]
0x180031fd1  inc     rbx
0x180031fd4  cmp     [rax+rbx*2], r15w
0x180031fd9  jnz     short loc_180031FD1
0x180031fdb  mov     eax, 2
0x180031fe0  mul     rbx
0x180031fe3  test    rdx, rdx
0x180031fe6  jnz     short loc_180032030
0x180031fe8  lea     rsi, [rax+2]
0x180031fec  cmp     rsi, rax
0x180031fef  jb      short loc_180032030
0x180031ff1  mov     ebx, r15d
0x180031ff4  call    cs:__imp_GetProcessHeap
0x180031ffa  mov     r8, rsi; dwBytes
0x180031ffd  mov     edx, 8; dwFlags
0x180032002  mov     rcx, rax; hHeap
0x180032005  call    cs:__imp_HeapAlloc
0x18003200b  mov     cs:BfspSystemPartitionName, rax
0x180032012  test    rax, rax
0x180032015  jnz     short loc_18003201E
0x180032017  mov     ebx, 0C0000017h
0x18003201c  jmp     short loc_180032035
0x18003201e  mov     r8, rsi; Size
0x180032021  lea     rdx, [rsp+2D0h+Destination]; Src
0x180032026  mov     rcx, rax; void *
0x180032029  call    memcpy_0
0x18003202e  jmp     short loc_180032035
0x180032030  mov     ebx, 0C0000095h
0x180032035  mov     eax, ebx
0x180032037  mov     rcx, [rbp+1D0h+var_20]
0x18003203e  xor     rcx, rsp; StackCookie
0x180032041  call    __security_check_cookie
0x180032046  lea     r11, [rsp+2D0h+var_10]
0x18003204e  mov     rbx, [r11+28h]
0x180032052  mov     rsi, [r11+30h]
0x180032056  mov     rsp, r11
0x180032059  pop     r15
0x18003205b  pop     rdi
0x18003205c  pop     rbp
0x18003205d  retn
0x18003205e  call    __report_rangecheckfailure
```
