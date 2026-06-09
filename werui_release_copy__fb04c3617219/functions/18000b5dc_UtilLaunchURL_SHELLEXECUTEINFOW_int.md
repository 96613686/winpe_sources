# UtilLaunchURL(_SHELLEXECUTEINFOW *,int)

- ea: `0x18000b5dc`
- end: `0x18000b825`
- name: `?UtilLaunchURL@@YAJPEAU_SHELLEXECUTEINFOW@@H@Z`
- size: `585`
- prototype: `__int64 __fastcall(struct _SHELLEXECUTEINFOW *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004430`

## callees

- `0x1800030bc`
- `0x1800035dc`
- `0x180003604`
- `0x180003fe4`
- `0x180005c80`
- `0x180005ddc`
- `0x1800096a8`
- `0x18000983c`
- `0x18000afbc`
- `0x18000b5dc`
- `0x180016c1e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b6ca`
- `KERNEL32!GetLastError` at `0x18000b791`
- `KERNEL32!GetLastError` at `0x18000b6ca`
- `KERNEL32!GetLastError` at `0x18000b791`
- `KERNEL32!FreeLibrary` at `0x18000b6ab`
- `KERNEL32!FreeLibrary` at `0x18000b6ab`
- `KERNEL32!CreateThread` at `0x18000b772`
- `KERNEL32!CreateThread` at `0x18000b772`
- `KERNEL32!GetModuleHandleExW` at `0x18000b6c0`
- `KERNEL32!GetModuleHandleExW` at `0x18000b6c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilLaunchURL(struct _SHELLEXECUTEINFOW *a1)
{
  unsigned int v2; // ebx
  char *v3; // rax
  char *v4; // rbx
  HMODULE v5; // rcx
  DWORD v6; // eax
  signed int LastError; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int128 v10; // xmm1
  __int128 v11; // xmm2
  __int128 v12; // xmm3
  __int128 v13; // xmm4
  __int128 v14; // xmm5
  __int128 v15; // xmm6
  HANDLE v16; // rax
  char *v18; // [rsp+70h] [rbp+30h] BYREF
  DWORD ThreadId; // [rsp+78h] [rbp+38h] BYREF
  __int64 v20; // [rsp+80h] [rbp+40h] BYREF
  __int64 v21; // [rsp+88h] [rbp+48h] BYREF

  v20 = 0;
  v18 = 0;
  ThreadId = 0;
  if ( a1 )
  {
    v3 = (char *)operator new(0x98u, (const struct std::nothrow_t *)std::nothrow);
    v4 = v3;
    if ( v3 )
    {
      *(_OWORD *)(v3 + 120) = 0;
      *(_OWORD *)(v3 + 136) = 0;
      memset_0(v3, 0, 0x70u);
      *((_QWORD *)v4 + 14) = 0;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v4 + 120);
    }
    else
    {
      v4 = 0;
    }
    v21 = 0;
    v18 = v4;
    utl::unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>::~unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>(&v21);
    if ( !v4
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v4 + 120,
                             a1->lpFile) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_84e0403860003c8b7f85a224b3bf7818_Traceguids);
      goto LABEL_25;
    }
    v5 = (HMODULE)*((_QWORD *)v4 + 14);
    *((_QWORD *)v4 + 14) = 0;
    if ( v5 )
      FreeLibrary(v5);
    if ( GetModuleHandleExW(4u, (LPCWSTR)LaunchURLStub, (HMODULE *)v4 + 14) )
    {
      v10 = *(_OWORD *)&a1->lpVerb;
      v11 = *(_OWORD *)&a1->lpParameters;
      v12 = *(_OWORD *)&a1->nShow;
      v13 = *(_OWORD *)&a1->lpIDList;
      v14 = *(_OWORD *)&a1->hkeyClass;
      v15 = *(_OWORD *)&a1->hIcon;
      *(_OWORD *)v4 = *(_OWORD *)&a1->cbSize;
      *((_OWORD *)v4 + 1) = v10;
      *((_OWORD *)v4 + 2) = v11;
      *((_OWORD *)v4 + 3) = v12;
      *((_OWORD *)v4 + 4) = v13;
      *((_OWORD *)v4 + 5) = v14;
      *((_OWORD *)v4 + 6) = v15;
      *((_QWORD *)v4 + 3) = *((_QWORD *)v4 + 15);
      v16 = CreateThread(0, 0, LaunchURLStub, v4, 0, &ThreadId);
      tlx::unique_any<tlx::file_handle_traits>::reset(&v20, v16);
      if ( v20 != -1 && v20 != 0 )
      {
        v18 = 0;
        goto LABEL_25;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_25;
      v9 = 21;
    }
    else
    {
      v6 = GetLastError();
      LastError = ERROR_HR_FROM_WIN32(v6);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_25;
      v9 = 20;
    }
    WPP_SF_d(v8[2], v9, WPP_84e0403860003c8b7f85a224b3bf7818_Traceguids, (unsigned int)LastError);
LABEL_25:
    v2 = 0;
    goto LABEL_26;
  }
  v2 = -2147024809;
LABEL_26:
  utl::unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>::~unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>(&v18);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v20);
  return v2;
}

```

## disassembly

```asm
0x18000b5dc  mov     [rsp-28h+ThreadId], edx
0x18000b5e0  push    rbp
0x18000b5e1  push    rbx
0x18000b5e2  push    rsi
0x18000b5e3  push    rdi
0x18000b5e4  push    r14
0x18000b5e6  mov     rbp, rsp
0x18000b5e9  sub     rsp, 40h
0x18000b5ed  movaps  [rsp+40h+var_10], xmm6
0x18000b5f2  mov     rsi, rcx
0x18000b5f5  mov     [rbp+arg_10], 0
0x18000b5fd  mov     [rbp+arg_0], 0
0x18000b605  mov     [rbp+ThreadId], 0
0x18000b60c  test    rcx, rcx
0x18000b60f  jnz     short loc_18000B61B
0x18000b611  mov     ebx, 80070057h
0x18000b616  jmp     loc_18000B800
0x18000b61b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b622  mov     ecx, 98h; unsigned __int64
0x18000b627  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b62c  mov     rbx, rax
0x18000b62f  test    rax, rax
0x18000b632  jz      short loc_18000B663
0x18000b634  xorps   xmm0, xmm0
0x18000b637  movups  xmmword ptr [rax+78h], xmm0
0x18000b63b  movups  xmmword ptr [rax+88h], xmm0
0x18000b642  xor     edx, edx; Val
0x18000b644  lea     r8d, [rdx+70h]; Size
0x18000b648  mov     rcx, rax; void *
0x18000b64b  call    memset_0
0x18000b650  mov     qword ptr [rbx+70h], 0
0x18000b658  lea     rcx, [rbx+78h]; void *
0x18000b65c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000b661  jmp     short loc_18000B665
0x18000b663  xor     ebx, ebx
0x18000b665  mov     [rbp+arg_18], 0
0x18000b66d  mov     [rbp+arg_0], rbx
0x18000b671  lea     rcx, [rbp+arg_18]
0x18000b675  call    ??1?$unique_ptr@ULAUNCH_URL_PARAMETERS@@U?$default_delete@ULAUNCH_URL_PARAMETERS@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>::~unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>(void)
0x18000b67a  test    rbx, rbx
0x18000b67d  jz      loc_18000B7D0
0x18000b683  mov     rdx, [rsi+18h]
0x18000b687  lea     rcx, [rbx+78h]
0x18000b68b  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000b690  test    al, al
0x18000b692  jz      loc_18000B7D0
0x18000b698  lea     rdi, [rbx+70h]
0x18000b69c  mov     rcx, [rdi]; hLibModule
0x18000b69f  mov     qword ptr [rdi], 0
0x18000b6a6  test    rcx, rcx
0x18000b6a9  jz      short loc_18000B6B1
0x18000b6ab  call    cs:__imp_FreeLibrary
0x18000b6b1  mov     r8, rdi; phModule
0x18000b6b4  lea     rdx, ?LaunchURLStub@@YAKPEAX@Z; lpModuleName
0x18000b6bb  mov     ecx, 4; dwFlags
0x18000b6c0  call    cs:__imp_GetModuleHandleExW
0x18000b6c6  test    eax, eax
0x18000b6c8  jnz     short loc_18000B715
0x18000b6ca  call    cs:__imp_GetLastError
0x18000b6d0  mov     ecx, eax; unsigned int
0x18000b6d2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000b6d7  lea     rdx, WPP_GLOBAL_Control
0x18000b6de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6e5  cmp     rcx, rdx
0x18000b6e8  jz      loc_18000B7FE
0x18000b6ee  test    byte ptr [rcx+1Ch], 1
0x18000b6f2  jz      loc_18000B7FE
0x18000b6f8  mov     edx, 14h
0x18000b6fd  mov     r9d, eax
0x18000b700  lea     r8, WPP_84e0403860003c8b7f85a224b3bf7818_Traceguids
0x18000b707  mov     rcx, [rcx+10h]
0x18000b70b  call    WPP_SF_d
0x18000b710  jmp     loc_18000B7FE
0x18000b715  movaps  xmm0, xmmword ptr [rsi]
0x18000b718  movaps  xmm1, xmmword ptr [rsi+10h]
0x18000b71c  movaps  xmm2, xmmword ptr [rsi+20h]
0x18000b720  movaps  xmm3, xmmword ptr [rsi+30h]
0x18000b724  movaps  xmm4, xmmword ptr [rsi+40h]
0x18000b728  movaps  xmm5, xmmword ptr [rsi+50h]
0x18000b72c  movaps  xmm6, xmmword ptr [rsi+60h]
0x18000b730  movups  xmmword ptr [rbx], xmm0
0x18000b733  movups  xmmword ptr [rbx+10h], xmm1
0x18000b737  movups  xmmword ptr [rbx+20h], xmm2
0x18000b73b  movups  xmmword ptr [rbx+30h], xmm3
0x18000b73f  movups  xmmword ptr [rbx+40h], xmm4
0x18000b743  movups  xmmword ptr [rbx+50h], xmm5
0x18000b747  movups  xmmword ptr [rbx+60h], xmm6
0x18000b74b  mov     rax, [rbx+78h]
0x18000b74f  mov     [rbx+18h], rax
0x18000b753  lea     rax, [rbp+ThreadId]
0x18000b757  mov     [rsp+40h+lpThreadId], rax; lpThreadId
0x18000b75c  mov     [rsp+40h+dwCreationFlags], 0; dwCreationFlags
0x18000b764  mov     r9, rbx; lpParameter
0x18000b767  lea     r8, ?LaunchURLStub@@YAKPEAX@Z; lpStartAddress
0x18000b76e  xor     edx, edx; dwStackSize
0x18000b770  xor     ecx, ecx; lpThreadAttributes
0x18000b772  call    cs:__imp_CreateThread
0x18000b778  mov     rdx, rax
0x18000b77b  lea     rcx, [rbp+arg_10]
0x18000b77f  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18000b784  mov     rax, [rbp+arg_10]
0x18000b788  inc     rax
0x18000b78b  cmp     rax, 1
0x18000b78f  ja      short loc_18000B7C6
0x18000b791  call    cs:__imp_GetLastError
0x18000b797  test    eax, eax
0x18000b799  jle     short loc_18000B7A3
0x18000b79b  movzx   eax, ax
0x18000b79e  or      eax, 80070000h
0x18000b7a3  lea     rdx, WPP_GLOBAL_Control
0x18000b7aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7b1  cmp     rcx, rdx
0x18000b7b4  jz      short loc_18000B7FE
0x18000b7b6  test    byte ptr [rcx+1Ch], 1
0x18000b7ba  jz      short loc_18000B7FE
0x18000b7bc  mov     edx, 15h
0x18000b7c1  jmp     loc_18000B6FD
0x18000b7c6  mov     [rbp+arg_0], 0
0x18000b7ce  jmp     short loc_18000B7FE
0x18000b7d0  lea     rdx, WPP_GLOBAL_Control
0x18000b7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7de  cmp     rcx, rdx
0x18000b7e1  jz      short loc_18000B7FE
0x18000b7e3  test    byte ptr [rcx+1Ch], 1
0x18000b7e7  jz      short loc_18000B7FE
0x18000b7e9  mov     edx, 13h
0x18000b7ee  lea     r8, WPP_84e0403860003c8b7f85a224b3bf7818_Traceguids
0x18000b7f5  mov     rcx, [rcx+10h]
0x18000b7f9  call    WPP_SF_
0x18000b7fe  xor     ebx, ebx
0x18000b800  lea     rcx, [rbp+arg_0]
0x18000b804  call    ??1?$unique_ptr@ULAUNCH_URL_PARAMETERS@@U?$default_delete@ULAUNCH_URL_PARAMETERS@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>::~unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>(void)
0x18000b809  nop
0x18000b80a  lea     rcx, [rbp+arg_10]
0x18000b80e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18000b813  mov     eax, ebx
0x18000b815  movaps  xmm6, [rsp+40h+var_10]
0x18000b81a  add     rsp, 40h
0x18000b81e  pop     r14
0x18000b820  pop     rdi
0x18000b821  pop     rsi
0x18000b822  pop     rbx
0x18000b823  pop     rbp
0x18000b824  retn
```
