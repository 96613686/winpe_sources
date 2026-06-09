# ArgExpandFiles(ushort * *,int)

- ea: `0x14003dd0c`
- end: `0x14003e00c`
- name: `?ArgExpandFiles@@YAJPEAPEAGH@Z`
- size: `768`
- prototype: `__int64 __fastcall(unsigned __int16 **, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14002ec00`
- `0x14003e954`
- `0x14003eb98`

## callees

- `0x1400020e4`
- `0x14003dd0c`
- `0x14003e3a0`
- `0x14003e4c0`
- `0x1400400be`
- `0x1400400d6`
- `0x140040130`

## import_xrefs

- `msvcrt!wcschr` at `0x14003dead`
- `msvcrt!wcschr` at `0x14003debe`
- `msvcrt!wcschr` at `0x14003dead`
- `msvcrt!wcschr` at `0x14003debe`
- `msvcrt!_wsplitpath_s` at `0x14003ddc9`
- `msvcrt!_wsplitpath_s` at `0x14003ddc9`
- `msvcrt!_wmakepath_s` at `0x14003de49`
- `msvcrt!_wmakepath_s` at `0x14003de49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003df4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003df4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003df3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003df6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003df3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003df6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003df7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003df7d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14003dddf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14003dddf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14003de95`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14003de95`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14003dfc6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14003dfc6`

## pseudocode

```c
__int64 __fastcall ArgExpandFiles(unsigned __int16 **a1, int a2)
{
  __int64 FirstFileW; // r14
  int v5; // esi
  const wchar_t *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rax
  wchar_t *v9; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v11; // rbx
  HANDLE v12; // rax
  unsigned __int16 *v13; // rax
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  char *v16; // [rsp+58h] [rbp-A8h]
  _WORD v17[8]; // [rsp+60h] [rbp-A0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Drive[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wchar_t Dir[256]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wchar_t Buffer[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  wchar_t Ext[256]; // [rsp+6E0h] [rbp+5E0h] BYREF
  wchar_t Filename[256]; // [rsp+8E0h] [rbp+7E0h] BYREF

  FirstFileW = -1;
  v5 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v6 = *a1;
  Src = v17;
  v7 = 1;
  v17[0] = 0;
  v16 = (char *)v17;
  while ( *v6 )
  {
    if ( _wsplitpath_s(v6, Drive, 3u, Dir, 0x100u, Filename, 0x100u, Ext, 0x100u) )
    {
      v7 = -2147024566;
      goto LABEL_35;
    }
    FirstFileW = (__int64)FindFirstFileW(v6, &FindFileData);
    if ( FirstFileW != -1 )
    {
      do
      {
        if ( FindFileData.cFileName[0] != 46
          || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
        {
          if ( _wmakepath_s(Buffer, 0x104u, Drive, Dir, FindFileData.cFileName, &::Ext) )
          {
            v7 = -2147024690;
            goto LABEL_36;
          }
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                   &Src,
                                   Buffer)
            || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(&Src) )
          {
            v7 = -2147024882;
            goto LABEL_36;
          }
          ++v5;
          if ( !a2 )
            goto LABEL_28;
        }
      }
      while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    }
    if ( !wcschr(v6, 0x2Au) && !wcschr(v6, 0x3Fu) )
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &Src,
                               v6)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(&Src) )
      {
        v7 = -2147024882;
        goto LABEL_37;
      }
      ++v5;
      if ( !a2 )
        break;
    }
    if ( !a2 )
      break;
    v8 = -1;
    do
      ++v8;
    while ( v6[v8] );
    v6 += v8 + 1;
  }
LABEL_28:
  v9 = *a1;
  if ( *a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
    *a1 = 0;
  }
  if ( v5 )
  {
    v11 = 2 * ((v16 - (_BYTE *)Src) >> 1) + 2;
    v12 = GetProcessHeap();
    v13 = (unsigned __int16 *)HeapAlloc(v12, 0, v11);
    *a1 = v13;
    if ( v13 )
    {
      *v13 = 0;
      memcpy_0(*a1, Src, 2 * ((v16 - (_BYTE *)Src) >> 1) + 2);
    }
    else
    {
      v7 = -2147024882;
    }
  }
  else
  {
    v7 = -2147024894;
  }
LABEL_35:
  if ( FirstFileW != -1 )
LABEL_36:
    FindClose((HANDLE)FirstFileW);
LABEL_37:
  if ( Src != v17 )
    operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
  return v7;
}

```

## disassembly

```asm
0x14003dd0c  push    rbp
0x14003dd0e  push    rbx
0x14003dd0f  push    rsi
0x14003dd10  push    rdi
0x14003dd11  push    r12
0x14003dd13  push    r13
0x14003dd15  push    r14
0x14003dd17  push    r15
0x14003dd19  lea     rbp, [rsp-9F8h]
0x14003dd21  sub     rsp, 0AF8h
0x14003dd28  mov     rax, cs:__security_cookie
0x14003dd2f  xor     rax, rsp
0x14003dd32  mov     [rbp+0A30h+var_50], rax
0x14003dd39  mov     r12d, edx
0x14003dd3c  mov     r15, rcx
0x14003dd3f  xor     r13d, r13d
0x14003dd42  lea     rcx, [rsp+0B30h+FindFileData]; void *
0x14003dd47  xor     edx, edx; Val
0x14003dd49  or      r14, 0FFFFFFFFFFFFFFFFh
0x14003dd4d  mov     r8d, 250h; Size
0x14003dd53  mov     esi, r13d
0x14003dd56  call    memset_0
0x14003dd5b  mov     rbx, [r15]
0x14003dd5e  lea     rax, [rsp+0B30h+var_AD0]
0x14003dd63  mov     [rsp+0B30h+Src], rax
0x14003dd68  lea     edi, [r13+1]
0x14003dd6c  lea     rax, [rsp+0B30h+var_AD0]
0x14003dd71  mov     [rsp+0B30h+var_AD0], r13w
0x14003dd77  mov     [rsp+0B30h+var_AD8], rax
0x14003dd7c  cmp     [rbx], r13w
0x14003dd80  jz      loc_14003DF37
0x14003dd86  mov     ecx, 100h
0x14003dd8b  lea     rax, [rbp+0A30h+var_450]
0x14003dd92  mov     [rsp+0B30h+ExtCount], rcx; ExtCount
0x14003dd97  lea     r9, [rbp+0A30h+Dir]; Dir
0x14003dd9e  mov     [rsp+0B30h+Ext], rax; Ext
0x14003dda3  lea     rdx, [rbp+0A30h+Drive]; Drive
0x14003ddaa  mov     [rsp+0B30h+FilenameCount], rcx; FilenameCount
0x14003ddaf  lea     rax, [rbp+0A30h+var_250]
0x14003ddb6  mov     [rsp+0B30h+Filename], rax; Filename
0x14003ddbb  mov     r8d, 3; DriveCount
0x14003ddc1  mov     [rsp+0B30h+DirCount], rcx; DirCount
0x14003ddc6  mov     rcx, rbx; FullPath
0x14003ddc9  call    cs:__imp__wsplitpath_s
0x14003ddcf  test    eax, eax
0x14003ddd1  jnz     loc_14003DF2D
0x14003ddd7  lea     rdx, [rsp+0B30h+FindFileData]; lpFindFileData
0x14003dddc  mov     rcx, rbx; lpFileName
0x14003dddf  call    cs:__imp_FindFirstFileW
0x14003dde5  mov     r14, rax
0x14003dde8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003ddec  jz      loc_14003DEA5
0x14003ddf2  cmp     [rbp+0A30h+FindFileData.cFileName], 2Eh ; '.'
0x14003ddf7  movzx   ecx, [rbp+0A30h+FindFileData.cFileName+2]
0x14003ddfb  jnz     short loc_14003DE1A
0x14003ddfd  test    cx, cx
0x14003de00  jz      loc_14003DE8D
0x14003de06  cmp     [rbp+0A30h+FindFileData.cFileName], 2Eh ; '.'
0x14003de0b  jnz     short loc_14003DE1A
0x14003de0d  cmp     cx, 2Eh ; '.'
0x14003de11  jnz     short loc_14003DE1A
0x14003de13  cmp     [rbp+0A30h+FindFileData.cFileName+4], r13w
0x14003de18  jz      short loc_14003DE8D
0x14003de1a  lea     rax, Ext
0x14003de21  mov     edx, 104h; BufferCount
0x14003de26  mov     [rsp+0B30h+Filename], rax; Ext
0x14003de2b  lea     r9, [rbp+0A30h+Dir]; Dir
0x14003de32  lea     rax, [rbp+0A30h+FindFileData.cFileName]
0x14003de36  lea     r8, [rbp+0A30h+Drive]; Drive
0x14003de3d  mov     [rsp+0B30h+DirCount], rax; Filename
0x14003de42  lea     rcx, [rbp+0A30h+Buffer]; Buffer
0x14003de49  call    cs:__imp__wmakepath_s
0x14003de4f  test    eax, eax
0x14003de51  jnz     loc_14003DF19
0x14003de57  lea     rdx, [rbp+0A30h+Buffer]
0x14003de5e  lea     rcx, [rsp+0B30h+Src]
0x14003de63  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14003de68  test    al, al
0x14003de6a  jz      loc_14003DF0F
0x14003de70  lea     rcx, [rsp+0B30h+Src]
0x14003de75  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x14003de7a  test    al, al
0x14003de7c  jz      loc_14003DF0F
0x14003de82  add     esi, edi
0x14003de84  test    r12d, r12d
0x14003de87  jz      loc_14003DF37
0x14003de8d  lea     rdx, [rsp+0B30h+FindFileData]; lpFindFileData
0x14003de92  mov     rcx, r14; hFindFile
0x14003de95  call    cs:__imp_FindNextFileW
0x14003de9b  test    eax, eax
0x14003de9d  jnz     loc_14003DDF2
0x14003dea3  jmp     short loc_14003DEEF
0x14003dea5  mov     edx, 2Ah ; '*'; Ch
0x14003deaa  mov     rcx, rbx; Str
0x14003dead  call    cs:__imp_wcschr
0x14003deb3  test    rax, rax
0x14003deb6  jnz     short loc_14003DEEF
0x14003deb8  lea     edx, [rax+3Fh]; Ch
0x14003debb  mov     rcx, rbx; Str
0x14003debe  call    cs:__imp_wcschr
0x14003dec4  test    rax, rax
0x14003dec7  jnz     short loc_14003DEEF
0x14003dec9  mov     rdx, rbx
0x14003decc  lea     rcx, [rsp+0B30h+Src]
0x14003ded1  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14003ded6  test    al, al
0x14003ded8  jz      short loc_14003DF23
0x14003deda  lea     rcx, [rsp+0B30h+Src]
0x14003dedf  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x14003dee4  test    al, al
0x14003dee6  jz      short loc_14003DF23
0x14003dee8  add     esi, edi
0x14003deea  test    r12d, r12d
0x14003deed  jz      short loc_14003DF37
0x14003deef  test    r12d, r12d
0x14003def2  jz      short loc_14003DF37
0x14003def4  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003def8  inc     rax
0x14003defb  cmp     [rbx+rax*2], r13w
0x14003df00  jnz     short loc_14003DEF8
0x14003df02  lea     rbx, [rbx+rax*2]
0x14003df06  add     rbx, 2
0x14003df0a  jmp     loc_14003DD7C
0x14003df0f  mov     edi, 8007000Eh
0x14003df14  jmp     loc_14003DFC3
0x14003df19  mov     edi, 800700CEh
0x14003df1e  jmp     loc_14003DFC3
0x14003df23  mov     edi, 8007000Eh
0x14003df28  jmp     loc_14003DFCC
0x14003df2d  mov     edi, 8007014Ah
0x14003df32  jmp     loc_14003DFBD
0x14003df37  mov     rbx, [r15]
0x14003df3a  test    rbx, rbx
0x14003df3d  jz      short loc_14003DF56
0x14003df3f  call    cs:__imp_GetProcessHeap
0x14003df45  mov     r8, rbx; lpMem
0x14003df48  xor     edx, edx; dwFlags
0x14003df4a  mov     rcx, rax; hHeap
0x14003df4d  call    cs:__imp_HeapFree
0x14003df53  mov     [r15], r13
0x14003df56  test    esi, esi
0x14003df58  jz      short loc_14003DFB8
0x14003df5a  mov     rbx, [rsp+0B30h+var_AD8]
0x14003df5f  sub     rbx, [rsp+0B30h+Src]
0x14003df64  sar     rbx, 1
0x14003df67  lea     rbx, ds:2[rbx*2]
0x14003df6f  call    cs:__imp_GetProcessHeap
0x14003df75  mov     r8, rbx; dwBytes
0x14003df78  xor     edx, edx; dwFlags
0x14003df7a  mov     rcx, rax; hHeap
0x14003df7d  call    cs:__imp_HeapAlloc
0x14003df83  mov     [r15], rax
0x14003df86  test    rax, rax
0x14003df89  jnz     short loc_14003DF92
0x14003df8b  mov     edi, 8007000Eh
0x14003df90  jmp     short loc_14003DFBD
0x14003df92  mov     [rax], r13w
0x14003df96  mov     r8, [rsp+0B30h+var_AD8]
0x14003df9b  mov     rdx, [rsp+0B30h+Src]; Src
0x14003dfa0  mov     rcx, [r15]; void *
0x14003dfa3  sub     r8, rdx
0x14003dfa6  sar     r8, 1
0x14003dfa9  lea     r8, ds:2[r8*2]; Size
0x14003dfb1  call    memcpy_0
0x14003dfb6  jmp     short loc_14003DFBD
0x14003dfb8  mov     edi, 80070002h
0x14003dfbd  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14003dfc1  jz      short loc_14003DFCC
0x14003dfc3  mov     rcx, r14; hFindFile
0x14003dfc6  call    cs:__imp_FindClose
0x14003dfcc  mov     rcx, [rsp+0B30h+Src]; void *
0x14003dfd1  lea     rax, [rsp+0B30h+var_AD0]
0x14003dfd6  cmp     rcx, rax
0x14003dfd9  jz      short loc_14003DFE7
0x14003dfdb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003dfe2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003dfe7  mov     eax, edi
0x14003dfe9  mov     rcx, [rbp+0A30h+var_50]
0x14003dff0  xor     rcx, rsp; StackCookie
0x14003dff3  call    __security_check_cookie
0x14003dff8  add     rsp, 0AF8h
0x14003dfff  pop     r15
0x14003e001  pop     r14
0x14003e003  pop     r13
0x14003e005  pop     r12
0x14003e007  pop     rdi
0x14003e008  pop     rsi
0x14003e009  pop     rbx
0x14003e00a  pop     rbp
0x14003e00b  retn
```
