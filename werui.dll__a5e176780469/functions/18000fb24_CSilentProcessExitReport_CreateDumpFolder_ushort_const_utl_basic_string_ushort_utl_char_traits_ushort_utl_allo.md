# CSilentProcessExitReport::CreateDumpFolder(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x18000fb24`
- end: `0x18000fc8c`
- name: `?CreateDumpFolder@CSilentProcessExitReport@@AEAAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000f834`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003fe4`
- `0x180005c20`
- `0x180005c80`
- `0x180009580`
- `0x1800096d0`
- `0x18000fb24`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18000fb64`
- `KERNEL32!GetTickCount` at `0x18000fb64`
- `SHELL32!SHCreateDirectoryExW` at `0x18000fba1`
- `SHELL32!SHCreateDirectoryExW` at `0x18000fba1`

## pseudocode

```c
__int64 __fastcall CSilentProcessExitReport::CreateDumpFolder(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  unsigned int i; // edi
  unsigned int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v13; // [rsp+20h] [rbp-58h]
  __int64 v14; // [rsp+28h] [rbp-50h]
  LPCWSTR pszPath; // [rsp+30h] [rbp-48h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&pszPath);
  v6 = -2147467259;
  if ( a2 && a3 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 0x32 )
        goto LABEL_23;
      LODWORD(v14) = GetTickCount();
      LODWORD(v13) = *(_DWORD *)(a1 + 4);
      v6 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
             &pszPath,
             L"%ls\\%ws-(PID-%u)-%u",
             *(_QWORD *)(a1 + 840),
             a2,
             v13,
             v14);
      if ( v6 < 0 )
        break;
      v8 = SHCreateDirectoryExW(0, pszPath, 0);
      if ( !v8 )
      {
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                a3,
                                pszPath) )
        {
          v6 = 0;
          goto LABEL_23;
        }
        v6 = -2147024882;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 26;
          v11 = 2147942414LL;
LABEL_19:
          WPP_SF_d(v9[2], v10, &WPP_0b9f8713f655331c3edd713292668335_Traceguids, v11);
          goto LABEL_23;
        }
        goto LABEL_23;
      }
      if ( v8 != 80 && v8 != 183 )
      {
        v6 = ERROR_HR_FROM_WIN32(v8);
        goto LABEL_23;
      }
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 25;
      v11 = (unsigned int)v6;
      goto LABEL_19;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_0b9f8713f655331c3edd713292668335_Traceguids);
  }
LABEL_23:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&pszPath);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000fb24  push    rbx
0x18000fb26  push    rbp
0x18000fb27  push    rsi
0x18000fb28  push    rdi
0x18000fb29  push    r14
0x18000fb2b  sub     rsp, 50h
0x18000fb2f  mov     r14, rcx
0x18000fb32  mov     rsi, r8
0x18000fb35  lea     rcx, [rsp+78h+pszPath]; void *
0x18000fb3a  mov     rbp, rdx
0x18000fb3d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000fb42  mov     ebx, 80004005h
0x18000fb47  test    rbp, rbp
0x18000fb4a  jz      loc_18000FC47
0x18000fb50  test    rsi, rsi
0x18000fb53  jz      loc_18000FC47
0x18000fb59  xor     edi, edi
0x18000fb5b  cmp     edi, 32h ; '2'
0x18000fb5e  jnb     loc_18000FC75
0x18000fb64  call    cs:__imp_GetTickCount
0x18000fb6a  mov     r8, [r14+348h]
0x18000fb71  lea     rdx, aLsWsPidUU; "%ls\\%ws-(PID-%u)-%u"
0x18000fb78  mov     dword ptr [rsp+78h+var_50], eax
0x18000fb7c  lea     rcx, [rsp+78h+pszPath]
0x18000fb81  mov     eax, [r14+4]
0x18000fb85  mov     r9, rbp
0x18000fb88  mov     dword ptr [rsp+78h+var_58], eax
0x18000fb8c  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18000fb91  mov     ebx, eax
0x18000fb93  test    eax, eax
0x18000fb95  js      short loc_18000FC14
0x18000fb97  mov     rdx, [rsp+78h+pszPath]; pszPath
0x18000fb9c  xor     r8d, r8d; psa
0x18000fb9f  xor     ecx, ecx; hwnd
0x18000fba1  call    cs:__imp_SHCreateDirectoryExW
0x18000fba7  test    eax, eax
0x18000fba9  jz      short loc_18000FBC9
0x18000fbab  cmp     eax, 50h ; 'P'
0x18000fbae  jz      short loc_18000FBB7
0x18000fbb0  cmp     eax, 0B7h
0x18000fbb5  jnz     short loc_18000FBBB
0x18000fbb7  inc     edi
0x18000fbb9  jmp     short loc_18000FB5B
0x18000fbbb  mov     ecx, eax; unsigned int
0x18000fbbd  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000fbc2  mov     ebx, eax
0x18000fbc4  jmp     loc_18000FC75
0x18000fbc9  mov     r8, [rsp+78h+var_40]
0x18000fbce  mov     rcx, rsi
0x18000fbd1  mov     rdx, [rsp+78h+pszPath]
0x18000fbd6  sub     r8, rdx
0x18000fbd9  sar     r8, 1
0x18000fbdc  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000fbe1  test    al, al
0x18000fbe3  jnz     short loc_18000FC10
0x18000fbe5  mov     ebx, 8007000Eh
0x18000fbea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbf1  lea     rax, WPP_GLOBAL_Control
0x18000fbf8  cmp     rcx, rax
0x18000fbfb  jz      short loc_18000FC75
0x18000fbfd  test    byte ptr [rcx+1Ch], 1
0x18000fc01  jz      short loc_18000FC75
0x18000fc03  mov     edx, 1Ah
0x18000fc08  mov     r9d, 8007000Eh
0x18000fc0e  jmp     short loc_18000FC35
0x18000fc10  xor     ebx, ebx
0x18000fc12  jmp     short loc_18000FC75
0x18000fc14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc1b  lea     rax, WPP_GLOBAL_Control
0x18000fc22  cmp     rcx, rax
0x18000fc25  jz      short loc_18000FC75
0x18000fc27  test    byte ptr [rcx+1Ch], 1
0x18000fc2b  jz      short loc_18000FC75
0x18000fc2d  mov     edx, 19h
0x18000fc32  mov     r9d, ebx
0x18000fc35  mov     rcx, [rcx+10h]
0x18000fc39  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x18000fc40  call    WPP_SF_d
0x18000fc45  jmp     short loc_18000FC75
0x18000fc47  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc4e  lea     rax, WPP_GLOBAL_Control
0x18000fc55  cmp     rcx, rax
0x18000fc58  jz      short loc_18000FC75
0x18000fc5a  test    byte ptr [rcx+1Ch], 1
0x18000fc5e  jz      short loc_18000FC75
0x18000fc60  mov     rcx, [rcx+10h]
0x18000fc64  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x18000fc6b  mov     edx, 18h
0x18000fc70  call    WPP_SF_
0x18000fc75  lea     rcx, [rsp+78h+pszPath]
0x18000fc7a  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000fc7f  mov     eax, ebx
0x18000fc81  add     rsp, 50h
0x18000fc85  pop     r14
0x18000fc87  pop     rdi
0x18000fc88  pop     rsi
0x18000fc89  pop     rbp
0x18000fc8a  pop     rbx
0x18000fc8b  retn
```
