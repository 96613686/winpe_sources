# SecpReadIdpCacheEntry

- ea: `0x18001fb54`
- end: `0x18001fd5c`
- name: `SecpReadIdpCacheEntry`
- size: `520`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001f940`

## callees

- `0x18001f89c`
- `0x18001fb54`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x18001fcfc`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x18001fcfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fbe2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fbe2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fd18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fd18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fd26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fd26`

## pseudocode

```c
__int64 __fastcall SecpReadIdpCacheEntry(HKEY hKey, LPCWSTR lpSubKey, __int128 *a3, _QWORD *a4, _DWORD *a5)
{
  char *v9; // rdi
  unsigned int RegValueHelper; // ebx
  __int64 v11; // rax
  SIZE_T v12; // rsi
  char *v13; // rax
  bool v14; // zf
  int v15; // eax
  __int128 v16; // xmm0
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Source[128]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  memset_0(Source, 0, sizeof(Source));
  if ( !a5 || !a4 || !lpSubKey )
    return 87;
  v9 = 0;
  RegValueHelper = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya);
  if ( RegValueHelper - 2 > 1 )
  {
    if ( !RegValueHelper )
    {
      RegValueHelper = QueryRegValueHelper((_DWORD)hKeya, (unsigned int)L"Name", 1, 1, (__int64)Source, 254);
      if ( !RegValueHelper )
      {
        v11 = -1;
        do
          ++v11;
        while ( Source[v11] );
        v12 = (2 * (_DWORD)v11 + 81) & 0xFFFFFFF8;
        v13 = (char *)LocalAlloc(0x40u, v12);
        v9 = v13;
        if ( v13 )
        {
          if ( ((unsigned __int8)v13 & 3) != 0 )
          {
            RegValueHelper = 1359;
          }
          else
          {
            v18 = 0;
            RegValueHelper = QueryRegValueHelper((_DWORD)hKeya, (unsigned int)L"Connected", 4, 0, (__int64)&v18, 4);
            if ( !RegValueHelper )
            {
              v14 = v18 == 0;
              v15 = 2;
              *((_DWORD *)v9 + 1) = v12;
              if ( !v14 )
                v15 = 3;
              *(_DWORD *)v9 = 1128614227;
              *((_DWORD *)v9 + 8) = 40;
              *((_DWORD *)v9 + 16) = v15;
              v16 = *a3;
              *((_QWORD *)v9 + 5) = v9 + 72;
              *((_OWORD *)v9 + 3) = v16;
              wcscpy_s((wchar_t *)v9 + 36, (v12 - 72) >> 1, Source);
              *a4 = v9;
              RegValueHelper = 0;
              *a5 = v12;
              v9 = 0;
            }
          }
        }
        else
        {
          RegValueHelper = 8;
        }
      }
    }
  }
  else
  {
    RegValueHelper = 1168;
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v9 )
    LocalFree(v9);
  return RegValueHelper;
}

```

## disassembly

```asm
0x18001fb54  mov     [rsp-8+arg_10], rbx
0x18001fb59  push    rbp
0x18001fb5a  push    rsi
0x18001fb5b  push    rdi
0x18001fb5c  push    r12
0x18001fb5e  push    r13
0x18001fb60  push    r14
0x18001fb62  push    r15
0x18001fb64  lea     rbp, [rsp-50h]
0x18001fb69  sub     rsp, 150h
0x18001fb70  mov     rax, cs:__security_cookie
0x18001fb77  xor     rax, rsp
0x18001fb7a  mov     [rbp+80h+var_40], rax
0x18001fb7e  mov     r15, [rbp+80h+arg_20]
0x18001fb85  mov     r12, r8
0x18001fb88  mov     rbx, rdx
0x18001fb8b  mov     rsi, rcx
0x18001fb8e  xor     r13d, r13d
0x18001fb91  lea     rcx, [rsp+180h+Source]; void *
0x18001fb96  xor     edx, edx; Val
0x18001fb98  mov     [rsp+180h+hKey], r13
0x18001fb9d  mov     r8d, 100h; Size
0x18001fba3  mov     r14, r9
0x18001fba6  call    memset_0
0x18001fbab  test    r15, r15
0x18001fbae  jz      loc_18001FD30
0x18001fbb4  test    r14, r14
0x18001fbb7  jz      loc_18001FD30
0x18001fbbd  test    rbx, rbx
0x18001fbc0  jz      loc_18001FD30
0x18001fbc6  lea     rax, [rsp+180h+hKey]
0x18001fbcb  mov     r9d, 20019h; samDesired
0x18001fbd1  xor     r8d, r8d; ulOptions
0x18001fbd4  mov     [rsp+180h+phkResult], rax; phkResult
0x18001fbd9  mov     rdx, rbx; lpSubKey
0x18001fbdc  mov     rcx, rsi; hKey
0x18001fbdf  mov     edi, r13d
0x18001fbe2  call    cs:__imp_RegOpenKeyExW
0x18001fbe8  mov     ebx, eax
0x18001fbea  lea     r8d, [r13+1]
0x18001fbee  add     eax, 0FFFFFFFEh
0x18001fbf1  cmp     eax, r8d
0x18001fbf4  ja      short loc_18001FC00
0x18001fbf6  mov     ebx, 490h
0x18001fbfb  jmp     loc_18001FD0E
0x18001fc00  test    ebx, ebx
0x18001fc02  jnz     loc_18001FD0E
0x18001fc08  mov     rcx, [rsp+180h+hKey]
0x18001fc0d  lea     rax, [rsp+180h+Source]
0x18001fc12  mov     [rsp+180h+var_158], 0FEh
0x18001fc1a  lea     rdx, aName; "Name"
0x18001fc21  mov     r9d, r8d
0x18001fc24  mov     [rsp+180h+phkResult], rax
0x18001fc29  call    QueryRegValueHelper
0x18001fc2e  mov     ebx, eax
0x18001fc30  test    eax, eax
0x18001fc32  jnz     loc_18001FD0E
0x18001fc38  lea     rcx, [rsp+180h+Source]
0x18001fc3d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fc41  inc     rax
0x18001fc44  cmp     [rcx+rax*2], r13w
0x18001fc49  jnz     short loc_18001FC41
0x18001fc4b  lea     eax, ds:51h[rax*2]
0x18001fc52  mov     ecx, 40h ; '@'; uFlags
0x18001fc57  and     eax, 0FFFFFFF8h
0x18001fc5a  mov     edx, eax; uBytes
0x18001fc5c  mov     esi, eax
0x18001fc5e  call    cs:__imp_LocalAlloc
0x18001fc64  mov     rdi, rax
0x18001fc67  test    rax, rax
0x18001fc6a  jnz     short loc_18001FC74
0x18001fc6c  lea     ebx, [rax+8]
0x18001fc6f  jmp     loc_18001FD0E
0x18001fc74  test    dil, 3
0x18001fc78  jz      short loc_18001FC84
0x18001fc7a  mov     ebx, 54Fh
0x18001fc7f  jmp     loc_18001FD0E
0x18001fc84  mov     rcx, [rsp+180h+hKey]
0x18001fc89  lea     rax, [rsp+180h+var_150]
0x18001fc8e  mov     r8d, 4
0x18001fc94  mov     [rsp+180h+var_150], r13d
0x18001fc99  mov     [rsp+180h+var_158], r8d
0x18001fc9e  lea     rdx, aConnected; "Connected"
0x18001fca5  xor     r9d, r9d
0x18001fca8  mov     [rsp+180h+phkResult], rax
0x18001fcad  call    QueryRegValueHelper
0x18001fcb2  mov     ebx, eax
0x18001fcb4  test    eax, eax
0x18001fcb6  jnz     short loc_18001FD0E
0x18001fcb8  cmp     [rsp+180h+var_150], r13d
0x18001fcbd  lea     eax, [rbx+2]
0x18001fcc0  mov     [rdi+4], esi
0x18001fcc3  lea     ecx, [rbx+3]
0x18001fcc6  cmovnz  eax, ecx
0x18001fcc9  mov     dword ptr [rdi], 43454953h
0x18001fccf  lea     rcx, [rdi+48h]; Destination
0x18001fcd3  mov     dword ptr [rdi+20h], 28h ; '('
0x18001fcda  mov     [rdi+40h], eax
0x18001fcdd  lea     r8, [rsp+180h+Source]; Source
0x18001fce2  movups  xmm0, xmmword ptr [r12]
0x18001fce7  mov     rdx, rsi
0x18001fcea  mov     [rdi+28h], rcx
0x18001fcee  sub     rdx, rcx
0x18001fcf1  add     rdx, rdi
0x18001fcf4  shr     rdx, 1; SizeInWords
0x18001fcf7  movdqu  xmmword ptr [rdi+30h], xmm0
0x18001fcfc  call    cs:__imp_wcscpy_s
0x18001fd02  mov     [r14], rdi
0x18001fd05  mov     ebx, r13d
0x18001fd08  mov     [r15], esi
0x18001fd0b  mov     rdi, r13
0x18001fd0e  mov     rcx, [rsp+180h+hKey]; hKey
0x18001fd13  test    rcx, rcx
0x18001fd16  jz      short loc_18001FD1E
0x18001fd18  call    cs:__imp_RegCloseKey
0x18001fd1e  test    rdi, rdi
0x18001fd21  jz      short loc_18001FD2C
0x18001fd23  mov     rcx, rdi; hMem
0x18001fd26  call    cs:__imp_LocalFree
0x18001fd2c  mov     eax, ebx
0x18001fd2e  jmp     short loc_18001FD35
0x18001fd30  mov     eax, 57h ; 'W'
0x18001fd35  mov     rcx, [rbp+80h+var_40]
0x18001fd39  xor     rcx, rsp; StackCookie
0x18001fd3c  call    __security_check_cookie
0x18001fd41  mov     rbx, [rsp+180h+arg_10]
0x18001fd49  add     rsp, 150h
0x18001fd50  pop     r15
0x18001fd52  pop     r14
0x18001fd54  pop     r13
0x18001fd56  pop     r12
0x18001fd58  pop     rdi
0x18001fd59  pop     rsi
0x18001fd5a  pop     rbp
0x18001fd5b  retn
```
