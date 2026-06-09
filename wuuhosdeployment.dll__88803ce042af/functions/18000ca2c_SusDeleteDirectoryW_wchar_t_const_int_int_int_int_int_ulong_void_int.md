# SusDeleteDirectoryW(wchar_t const *,int,int,int,int,int,ulong,void *,int)

- ea: `0x18000ca2c`
- end: `0x18000cbbe`
- name: `?SusDeleteDirectoryW@@YAJPEB_WHHHHHKPEAXH@Z`
- size: `402`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18002b4fc`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000c3a0`
- `0x18000c414`
- `0x18000c714`
- `0x18000ca2c`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cafa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cafa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cae6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cae6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18000ca82`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18000ca82`

## string_xrefs

- `0x18000cb3c`: `SusDeleteDirectoryW deleted directory=%ls`

## pseudocode

```c
__int64 __fastcall SusDeleteDirectoryW(const wchar_t *a1)
{
  struct _WIN32_FIND_DATAW *v2; // rbx
  __int64 v3; // rdx
  unsigned __int64 v4; // r9
  int v5; // edi
  HANDLE ProcessHeap; // rax
  struct _WIN32_FIND_DATAW *lpFindFileData; // rax
  int v8; // r8d
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-60h]
  void *lpMem; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int64 v13; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v2 = 0;
  lpMem = 0;
  v13 = 0;
  if ( !a1 || !*a1 )
  {
    v3 = 680;
    goto LABEL_16;
  }
  if ( PathIsRootW(a1) )
  {
    v3 = 681;
LABEL_16:
    v5 = -2147024809;
    goto LABEL_17;
  }
  if ( (unsigned int)HasLocalShortPathPrefix(a1)
    && (v5 = WUAppendPathReAlloc((wchar_t **)&lpMem, &v13, L"\\\\?\\", v4), v5 < 0) )
  {
    v3 = 685;
  }
  else
  {
    v5 = WUAppendPathReAlloc((wchar_t **)&lpMem, &v13, a1, v4);
    if ( v5 >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      lpFindFileData = (struct _WIN32_FIND_DATAW *)HeapAlloc(ProcessHeap, 8u, 0x250u);
      v2 = lpFindFileData;
      if ( lpFindFileData )
      {
        v5 = SusDeleteDirectoryWorker((int)&lpMem, (int)&v13, v8, v9, v11, lpFindFileData);
        if ( v5 >= 0 )
        {
          WUTrace(0, 0, 32, 4);
          v5 = 0;
          goto LABEL_18;
        }
        v3 = 701;
      }
      else
      {
        v5 = -2147024882;
        v3 = 690;
      }
    }
    else
    {
      v3 = 688;
    }
  }
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)(unsigned int)v5,
    v11);
LABEL_18:
  CSusBaseAllocTag<942762101>::operator delete(lpMem);
  if ( v2 )
    CSusBaseAllocTag<942762101>::operator delete(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ca2c  mov     [rsp-18h+arg_8], rbx
0x18000ca31  mov     [rsp-18h+arg_10], rsi
0x18000ca36  push    rbp
0x18000ca37  push    rdi
0x18000ca38  push    r14
0x18000ca3a  mov     rbp, rsp
0x18000ca3d  sub     rsp, 80h
0x18000ca44  mov     rax, cs:__security_cookie
0x18000ca4b  xor     rax, rsp
0x18000ca4e  mov     [rbp+var_8], rax
0x18000ca52  mov     rsi, rcx
0x18000ca55  xor     r14d, r14d
0x18000ca58  mov     ebx, r14d
0x18000ca5b  mov     [rbp+lpMem], r14
0x18000ca5f  mov     [rbp+var_10], r14
0x18000ca63  lea     rax, [rbp+lpMem]
0x18000ca67  mov     [rbp+var_28], rax
0x18000ca6b  mov     [rbp+var_20], 1
0x18000ca6f  test    rcx, rcx
0x18000ca72  jz      loc_18000CB63
0x18000ca78  cmp     [rcx], r14w
0x18000ca7c  jz      loc_18000CB63
0x18000ca82  call    cs:__imp_PathIsRootW
0x18000ca88  test    eax, eax
0x18000ca8a  jz      short loc_18000CA96
0x18000ca8c  mov     edx, 2A9h
0x18000ca91  jmp     loc_18000CB68
0x18000ca96  mov     rcx, rsi; wchar_t *
0x18000ca99  call    ?HasLocalShortPathPrefix@@YAHPEB_W@Z; HasLocalShortPathPrefix(wchar_t const *)
0x18000ca9e  test    eax, eax
0x18000caa0  jz      short loc_18000CAC6
0x18000caa2  lea     r8, asc_18004FB78; "\\\\?\\"
0x18000caa9  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x18000caad  lea     rcx, [rbp+lpMem]; wchar_t **
0x18000cab1  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x18000cab6  mov     edi, eax
0x18000cab8  test    eax, eax
0x18000caba  jns     short loc_18000CAC6
0x18000cabc  mov     edx, 2ADh
0x18000cac1  jmp     loc_18000CB6D
0x18000cac6  mov     r8, rsi; wchar_t *
0x18000cac9  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x18000cacd  lea     rcx, [rbp+lpMem]; wchar_t **
0x18000cad1  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x18000cad6  mov     edi, eax
0x18000cad8  test    eax, eax
0x18000cada  jns     short loc_18000CAE6
0x18000cadc  mov     edx, 2B0h
0x18000cae1  jmp     loc_18000CB6D
0x18000cae6  call    cs:__imp_GetProcessHeap
0x18000caec  mov     edx, 8; dwFlags
0x18000caf1  mov     r8d, 250h; dwBytes
0x18000caf7  mov     rcx, rax; hHeap
0x18000cafa  call    cs:__imp_HeapAlloc
0x18000cb00  mov     rbx, rax
0x18000cb03  mov     [rbp+var_30], rax
0x18000cb07  test    rax, rax
0x18000cb0a  jnz     short loc_18000CB18
0x18000cb0c  mov     edi, 8007000Eh
0x18000cb11  mov     edx, 2B2h
0x18000cb16  jmp     short loc_18000CB6D
0x18000cb18  mov     [rsp+80h+lpFindFileData], rax; lpFindFileData
0x18000cb1d  lea     rdx, [rbp+var_10]; int
0x18000cb21  lea     rcx, [rbp+lpMem]; int
0x18000cb25  call    SusDeleteDirectoryWorker
0x18000cb2a  mov     edi, eax
0x18000cb2c  test    eax, eax
0x18000cb2e  jns     short loc_18000CB37
0x18000cb30  mov     edx, 2BDh
0x18000cb35  jmp     short loc_18000CB6D
0x18000cb37  mov     [rsp+80h+var_50], rsi
0x18000cb3c  lea     rax, aSusdeletedirec; "SusDeleteDirectoryW deleted directory=%"...
0x18000cb43  mov     [rsp+80h+lpFindFileData], rax
0x18000cb48  mov     [rsp+80h+var_60], r14
0x18000cb4d  xor     edx, edx
0x18000cb4f  xor     ecx, ecx
0x18000cb51  lea     r9d, [rdx+4]
0x18000cb55  lea     r8d, [rdx+20h]
0x18000cb59  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18000cb5e  mov     edi, r14d
0x18000cb61  jmp     short loc_18000CB81
0x18000cb63  mov     edx, 2A8h; void *
0x18000cb68  mov     edi, 80070057h
0x18000cb6d  mov     rcx, [rbp+18h]; this
0x18000cb71  mov     r9d, edi; char *
0x18000cb74  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000cb7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb80  nop
0x18000cb81  mov     rcx, [rbp+lpMem]; lpMem
0x18000cb85  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18000cb8a  nop
0x18000cb8b  test    rbx, rbx
0x18000cb8e  jz      short loc_18000CB98
0x18000cb90  mov     rcx, rbx; lpMem
0x18000cb93  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18000cb98  mov     eax, edi
0x18000cb9a  mov     rcx, [rbp+var_8]
0x18000cb9e  xor     rcx, rsp; StackCookie
0x18000cba1  call    __security_check_cookie
0x18000cba6  lea     r11, [rsp+80h+var_s0]
0x18000cbae  mov     rbx, [r11+28h]
0x18000cbb2  mov     rsi, [r11+30h]
0x18000cbb6  mov     rsp, r11
0x18000cbb9  pop     r14
0x18000cbbb  pop     rdi
0x18000cbbc  pop     rbp
0x18000cbbd  retn
```
