# CSilentProcessExitReport::PruneDumpFolder(ulong)

- ea: `0x180010df0`
- end: `0x1800111b8`
- name: `?PruneDumpFolder@CSilentProcessExitReport@@AEAAJK@Z`
- size: `968`
- prototype: `__int64 __fastcall(CSilentProcessExitReport *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f834`

## callees

- `0x1800030bc`
- `0x1800035dc`
- `0x180005c80`
- `0x180009580`
- `0x1800095a8`
- `0x1800095d0`
- `0x1800096a8`
- `0x1800096d0`
- `0x18000979c`
- `0x18000f44c`
- `0x18000f4e8`
- `0x18000f5c8`
- `0x18000f630`
- `0x18000f690`
- `0x180010df0`
- `0x18001275c`
- `0x18001378c`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x180010fa7`
- `KERNEL32!FindNextFileW` at `0x180010fa7`
- `KERNEL32!FindFirstFileExW` at `0x180010eb0`
- `KERNEL32!FindFirstFileExW` at `0x180010eb0`
- `KERNEL32!CompareFileTime` at `0x18001100b`
- `KERNEL32!CompareFileTime` at `0x18001100b`

## pseudocode

```c
__int64 __fastcall CSilentProcessExitReport::PruneDumpFolder(CSilentProcessExitReport *this, unsigned int a2)
{
  unsigned __int64 v2; // r14
  HANDLE FirstFile; // rax
  int v5; // edx
  int v6; // edx
  __int64 v7; // r8
  __int64 v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  _QWORD *v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rax
  const FILETIME *v14; // rbx
  const FILETIME *i; // rdi
  LONG v16; // eax
  const FILETIME *v17; // rcx
  unsigned int v18; // ebx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int v21; // edx
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // r9
  FILETIME *v24; // rcx
  FILETIME v25; // rax
  _QWORD *v26; // rcx
  __int64 v27; // rax
  int lpSearchFilter; // [rsp+20h] [rbp-E0h]
  HANDLE hFindFile; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v31[2]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v32; // [rsp+48h] [rbp-B8h]
  _QWORD *v33; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v35[40]; // [rsp+78h] [rbp-88h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  v2 = a2;
  hFindFile = (HANDLE)-1LL;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  utl::list<FileDate,utl::allocator<FileDate>>::list<FileDate,utl::allocator<FileDate>>(v31);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v35);
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          lpFileName,
                          *((_QWORD *)this + 105))
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          lpFileName,
                          L"\\*-(PID-*)-*",
                          12) )
  {
    FirstFile = FindFirstFileExW(lpFileName[0], FindExInfoStandard, &FindFileData, FindExSearchLimitToDirectories, 0, 0);
    tlx::unique_any<tlx::find_handle_traits>::reset(&hFindFile, FirstFile);
    if ( hFindFile == (HANDLE)-1LL )
    {
LABEL_20:
      v12 = 0;
      v13 = v32;
      if ( v32 >= v2 )
        v12 = v32 - v2 + 1;
      while ( 1 )
      {
        if ( !v13 || !v12 )
        {
          v18 = 0;
          goto LABEL_49;
        }
        v14 = (const FILETIME *)v31[0];
        for ( i = *(const FILETIME **)v31[0]; i != (const FILETIME *)v31; i = (const FILETIME *)*i )
        {
          v16 = CompareFileTime(v14 + 6, i + 6);
          v17 = i;
          if ( v16 != 1 )
            v17 = v14;
          v14 = v17;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 lpFileName,
                                 *((_QWORD *)this + 105))
          || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                                 lpFileName,
                                 92)
          || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 lpFileName,
                                 *(_QWORD *)&v14[2]) )
        {
          break;
        }
        if ( (int)UtilRecursiveRemoveDirectory(lpFileName[0], v21, v22, v23, lpSearchFilter) >= 0 )
        {
          --v12;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_0b9f8713f655331c3edd713292668335_Traceguids);
        }
        v24 = (FILETIME *)v14[1];
        v25 = *v14;
        *v24 = *v14;
        *(_QWORD *)(*(_QWORD *)&v25 + 8LL) = v24;
        utl::_ContainerBase<FileDate,utl::allocator<FileDate>>::_DeleteNode<utl::_DlistNode<FileDate>>(v24, v14);
        v13 = --v32;
      }
      v18 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v20 = 15;
        goto LABEL_48;
      }
    }
    else
    {
      while ( 1 )
      {
        v5 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v5 = FindFileData.cFileName[1];
        if ( v5 )
        {
          v6 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
          {
            v6 = FindFileData.cFileName[1] - 46;
            if ( FindFileData.cFileName[1] == 46 )
              v6 = FindFileData.cFileName[2];
          }
          if ( v6 )
          {
            v7 = -1;
            do
              ++v7;
            while ( FindFileData.cFileName[v7] );
            if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                     v35,
                                     FindFileData.cFileName) )
              break;
            v8 = v31[0];
            v9 = operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
            v10 = v9;
            v33 = v9;
            if ( v9 )
            {
              FileDate::FileDate(v9 + 2, v35, &FindFileData.ftCreationTime);
              v33 = 0;
              v11 = *(_QWORD **)(v8 + 8);
              v10[1] = v11;
              *v10 = v8;
              *v11 = v10;
              *(_QWORD *)(v8 + 8) = v10;
              ++v32;
            }
            else
            {
              v10 = 0;
            }
            utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<FileDate>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<FileDate>>>(&v33);
            if ( !v10 )
              break;
          }
        }
        if ( !FindNextFileW(hFindFile, &FindFileData) )
        {
          tlx::unique_any<tlx::find_handle_traits>::reset(&hFindFile, -1);
          goto LABEL_20;
        }
      }
      v18 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v20 = 14;
LABEL_48:
        WPP_SF_(v19[2], v20, &WPP_0b9f8713f655331c3edd713292668335_Traceguids);
      }
    }
  }
  else
  {
    v18 = -2147024882;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = 13;
      goto LABEL_48;
    }
  }
LABEL_49:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v35);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
  while ( (_QWORD *)v31[0] != v31 )
  {
    v26 = *(_QWORD **)(v31[0] + 8LL);
    v27 = *(_QWORD *)v31[0];
    *v26 = *(_QWORD *)v31[0];
    *(_QWORD *)(v27 + 8) = v26;
    ((void (*)(void))utl::_ContainerBase<FileDate,utl::allocator<FileDate>>::_DeleteNode<utl::_DlistNode<FileDate>>)();
  }
  v32 = 0;
  tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(&hFindFile);
  return v18;
}

```

## disassembly

```asm
0x180010df0  push    rbp
0x180010df2  push    rbx
0x180010df3  push    rsi
0x180010df4  push    rdi
0x180010df5  push    r12
0x180010df7  push    r13
0x180010df9  push    r14
0x180010dfb  push    r15
0x180010dfd  lea     rbp, [rsp-208h]
0x180010e05  sub     rsp, 308h
0x180010e0c  mov     rax, cs:__security_cookie
0x180010e13  xor     rax, rsp
0x180010e16  mov     [rbp+240h+var_50], rax
0x180010e1d  mov     r14d, edx
0x180010e20  mov     r15, rcx
0x180010e23  or      r13, 0FFFFFFFFFFFFFFFFh
0x180010e27  mov     [rsp+340h+hFindFile], r13
0x180010e2c  xor     edx, edx; Val
0x180010e2e  mov     r8d, 250h; Size
0x180010e34  lea     rcx, [rbp+240h+FindFileData]; void *
0x180010e38  call    memset_0
0x180010e3d  lea     rcx, [rsp+340h+var_308]
0x180010e42  call    ??0?$list@VFileDate@@V?$allocator@VFileDate@@@utl@@@utl@@QEAA@XZ; utl::list<FileDate,utl::allocator<FileDate>>::list<FileDate,utl::allocator<FileDate>>(void)
0x180010e47  nop
0x180010e48  lea     rcx, [rsp+340h+lpFileName]; void *
0x180010e4d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180010e52  nop
0x180010e53  lea     rcx, [rsp+340h+var_2C8]; void *
0x180010e58  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180010e5d  nop
0x180010e5e  mov     rdx, [r15+348h]
0x180010e65  lea     rcx, [rsp+340h+lpFileName]
0x180010e6a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180010e6f  xor     r12d, r12d
0x180010e72  test    al, al
0x180010e74  jz      loc_180011116
0x180010e7a  lea     r8d, [r13+0Dh]
0x180010e7e  lea     rdx, aPid; "\\*-(PID-*)-*"
0x180010e85  lea     rcx, [rsp+340h+lpFileName]
0x180010e8a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180010e8f  test    al, al
0x180010e91  jz      loc_180011116
0x180010e97  mov     [rsp+340h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x180010e9c  mov     [rsp+340h+lpSearchFilter], r12; int
0x180010ea1  lea     r9d, [r13+2]; fSearchOp
0x180010ea5  lea     r8, [rbp+240h+FindFileData]; lpFindFileData
0x180010ea9  xor     edx, edx; fInfoLevelId
0x180010eab  mov     rcx, [rsp+340h+lpFileName]; lpFileName
0x180010eb0  call    cs:__imp_FindFirstFileExW
0x180010eb6  mov     rdx, rax
0x180010eb9  lea     rcx, [rsp+340h+hFindFile]
0x180010ebe  call    ?reset@?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::find_handle_traits>::reset(void *)
0x180010ec3  cmp     [rsp+340h+hFindFile], r13
0x180010ec8  jz      loc_180010FC2
0x180010ece  lea     esi, [r13+2Fh]
0x180010ed2  movzx   edx, [rbp+240h+var_274]
0x180010ed6  sub     edx, esi
0x180010ed8  jnz     short loc_180010EE4
0x180010eda  movzx   edx, [rbp+240h+var_272]
0x180010ede  movzx   ecx, r12w
0x180010ee2  sub     edx, ecx
0x180010ee4  test    edx, edx
0x180010ee6  jz      loc_180010F9E
0x180010eec  movzx   edx, [rbp+240h+var_274]
0x180010ef0  sub     edx, esi
0x180010ef2  jnz     short loc_180010F06
0x180010ef4  movzx   edx, [rbp+240h+var_272]
0x180010ef8  sub     edx, esi
0x180010efa  jnz     short loc_180010F06
0x180010efc  movzx   edx, [rbp+240h+var_270]
0x180010f00  movzx   ecx, r12w
0x180010f04  sub     edx, ecx
0x180010f06  test    edx, edx
0x180010f08  jz      loc_180010F9E
0x180010f0e  lea     rax, [rbp+240h+var_274]
0x180010f12  mov     r8, r13
0x180010f15  inc     r8
0x180010f18  cmp     [rax+r8*2], r12w
0x180010f1d  jnz     short loc_180010F15
0x180010f1f  lea     rdx, [rbp+240h+var_274]
0x180010f23  lea     rcx, [rsp+340h+var_2C8]
0x180010f28  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180010f2d  test    al, al
0x180010f2f  jz      loc_180011023
0x180010f35  mov     rdi, [rsp+340h+var_308]
0x180010f3a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010f41  mov     ecx, 38h ; '8'; unsigned __int64
0x180010f46  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010f4b  mov     rbx, rax
0x180010f4e  mov     [rsp+340h+var_2F0], rax
0x180010f53  test    rax, rax
0x180010f56  jz      short loc_180010F88
0x180010f58  lea     rcx, [rax+10h]
0x180010f5c  lea     r8, [rbp+240h+var_29C]
0x180010f60  lea     rdx, [rsp+340h+var_2C8]
0x180010f65  call    ??0FileDate@@QEAA@$$QEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEBU_FILETIME@@@Z; FileDate::FileDate(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&,_FILETIME const &)
0x180010f6a  mov     [rsp+340h+var_2F0], r12
0x180010f6f  mov     rax, [rdi+8]
0x180010f73  mov     [rbx+8], rax
0x180010f77  mov     [rbx], rdi
0x180010f7a  mov     [rax], rbx
0x180010f7d  mov     [rdi+8], rbx
0x180010f81  inc     [rsp+340h+var_2F8]
0x180010f86  jmp     short loc_180010F8B
0x180010f88  mov     rbx, r12
0x180010f8b  lea     rcx, [rsp+340h+var_2F0]
0x180010f90  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@VFileDate@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<FileDate>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<FileDate>>>(void)
0x180010f95  test    rbx, rbx
0x180010f98  jz      loc_180011023
0x180010f9e  lea     rdx, [rbp+240h+FindFileData]; lpFindFileData
0x180010fa2  mov     rcx, [rsp+340h+hFindFile]; hFindFile
0x180010fa7  call    cs:__imp_FindNextFileW
0x180010fad  test    eax, eax
0x180010faf  jnz     loc_180010ED2
0x180010fb5  mov     rdx, r13
0x180010fb8  lea     rcx, [rsp+340h+hFindFile]
0x180010fbd  call    ?reset@?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::find_handle_traits>::reset(void *)
0x180010fc2  mov     rsi, r12
0x180010fc5  mov     rax, [rsp+340h+var_2F8]
0x180010fca  cmp     rax, r14
0x180010fcd  jb      short loc_180010FD8
0x180010fcf  mov     rsi, rax
0x180010fd2  sub     rsi, r14
0x180010fd5  inc     rsi
0x180010fd8  lea     r14, WPP_GLOBAL_Control
0x180010fdf  test    rax, rax
0x180010fe2  jz      loc_180011111
0x180010fe8  test    rsi, rsi
0x180010feb  jz      loc_180011111
0x180010ff1  mov     rbx, [rsp+340h+var_308]
0x180010ff6  mov     rdi, [rbx]
0x180010ff9  lea     rax, [rsp+340h+var_308]
0x180010ffe  cmp     rdi, rax
0x180011001  jz      short loc_180011053
0x180011003  lea     rdx, [rdi+30h]; lpFileTime2
0x180011007  lea     rcx, [rbx+30h]; lpFileTime1
0x18001100b  call    cs:__imp_CompareFileTime
0x180011011  mov     rcx, rdi
0x180011014  cmp     eax, 1
0x180011017  cmovnz  rcx, rbx
0x18001101b  mov     rbx, rcx
0x18001101e  mov     rdi, [rdi]
0x180011021  jmp     short loc_180010FF9
0x180011023  mov     ebx, 8007000Eh
0x180011028  lea     r14, WPP_GLOBAL_Control
0x18001102f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011036  cmp     rcx, r14
0x180011039  jz      loc_18001114A
0x18001103f  test    byte ptr [rcx+1Ch], 1
0x180011043  jz      loc_18001114A
0x180011049  mov     edx, 0Eh
0x18001104e  jmp     loc_180011139
0x180011053  mov     rdx, [r15+348h]
0x18001105a  lea     rcx, [rsp+340h+lpFileName]
0x18001105f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180011064  test    al, al
0x180011066  jz      loc_1800110F3
0x18001106c  mov     edx, 5Ch ; '\'
0x180011071  lea     rcx, [rsp+340h+lpFileName]
0x180011076  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x18001107b  test    al, al
0x18001107d  jz      short loc_1800110F3
0x18001107f  mov     rdx, [rbx+10h]
0x180011083  lea     rcx, [rsp+340h+lpFileName]
0x180011088  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001108d  test    al, al
0x18001108f  jz      short loc_1800110F3
0x180011091  mov     rcx, [rsp+340h+lpFileName]; unsigned __int16 *
0x180011096  call    ?UtilRecursiveRemoveDirectory@@YAJPEBGH00H@Z; UtilRecursiveRemoveDirectory(ushort const *,int,ushort const *,ushort const *,int)
0x18001109b  test    eax, eax
0x18001109d  jns     short loc_1800110C8
0x18001109f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110a6  cmp     rcx, r14
0x1800110a9  jz      short loc_1800110CB
0x1800110ab  test    byte ptr [rcx+1Ch], 2
0x1800110af  jz      short loc_1800110CB
0x1800110b1  mov     edx, 10h
0x1800110b6  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x1800110bd  mov     rcx, [rcx+10h]
0x1800110c1  call    WPP_SF_
0x1800110c6  jmp     short loc_1800110CB
0x1800110c8  dec     rsi
0x1800110cb  mov     rcx, [rbx+8]
0x1800110cf  mov     rax, [rbx]
0x1800110d2  mov     [rcx], rax
0x1800110d5  mov     [rax+8], rcx
0x1800110d9  mov     rdx, rbx
0x1800110dc  call    ??$_DeleteNode@U?$_DlistNode@VFileDate@@@utl@@@?$_ContainerBase@VFileDate@@V?$allocator@VFileDate@@@utl@@@utl@@IEAAXPEAU?$_DlistNode@VFileDate@@@1@@Z; utl::_ContainerBase<FileDate,utl::allocator<FileDate>>::_DeleteNode<utl::_DlistNode<FileDate>>(utl::_DlistNode<FileDate> *)
0x1800110e1  mov     rax, [rsp+340h+var_2F8]
0x1800110e6  dec     rax
0x1800110e9  mov     [rsp+340h+var_2F8], rax
0x1800110ee  jmp     loc_180010FDF
0x1800110f3  mov     ebx, 8007000Eh
0x1800110f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110ff  cmp     rcx, r14
0x180011102  jz      short loc_18001114A
0x180011104  test    byte ptr [rcx+1Ch], 1
0x180011108  jz      short loc_18001114A
0x18001110a  mov     edx, 0Fh
0x18001110f  jmp     short loc_180011139
0x180011111  mov     ebx, r12d
0x180011114  jmp     short loc_18001114A
0x180011116  mov     ebx, 8007000Eh
0x18001111b  lea     r14, WPP_GLOBAL_Control
0x180011122  mov     rcx, cs:WPP_GLOBAL_Control
0x180011129  cmp     rcx, r14
0x18001112c  jz      short loc_18001114A
0x18001112e  test    byte ptr [rcx+1Ch], 1
0x180011132  jz      short loc_18001114A
0x180011134  mov     edx, 0Dh
0x180011139  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x180011140  mov     rcx, [rcx+10h]
0x180011144  call    WPP_SF_
0x180011149  nop
0x18001114a  lea     rcx, [rsp+340h+var_2C8]
0x18001114f  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180011154  nop
0x180011155  lea     rcx, [rsp+340h+lpFileName]
0x18001115a  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001115f  nop
0x180011160  lea     rax, [rsp+340h+var_308]
0x180011165  mov     rdx, [rsp+340h+var_308]
0x18001116a  cmp     rdx, rax
0x18001116d  jz      short loc_180011184
0x18001116f  mov     rcx, [rdx+8]
0x180011173  mov     rax, [rdx]
0x180011176  mov     [rcx], rax
0x180011179  mov     [rax+8], rcx
0x18001117d  call    ??$_DeleteNode@U?$_DlistNode@VFileDate@@@utl@@@?$_ContainerBase@VFileDate@@V?$allocator@VFileDate@@@utl@@@utl@@IEAAXPEAU?$_DlistNode@VFileDate@@@1@@Z; utl::_ContainerBase<FileDate,utl::allocator<FileDate>>::_DeleteNode<utl::_DlistNode<FileDate>>(utl::_DlistNode<FileDate> *)
0x180011182  jmp     short loc_180011160
0x180011184  mov     [rsp+340h+var_2F8], r12
0x180011189  lea     rcx, [rsp+340h+hFindFile]
0x18001118e  call    ??1?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(void)
0x180011193  mov     eax, ebx
0x180011195  mov     rcx, [rbp+240h+var_50]
0x18001119c  xor     rcx, rsp; StackCookie
0x18001119f  call    __security_check_cookie
0x1800111a4  add     rsp, 308h
0x1800111ab  pop     r15
0x1800111ad  pop     r14
0x1800111af  pop     r13
0x1800111b1  pop     r12
0x1800111b3  pop     rdi
0x1800111b4  pop     rsi
0x1800111b5  pop     rbx
0x1800111b6  pop     rbp
0x1800111b7  retn
```
