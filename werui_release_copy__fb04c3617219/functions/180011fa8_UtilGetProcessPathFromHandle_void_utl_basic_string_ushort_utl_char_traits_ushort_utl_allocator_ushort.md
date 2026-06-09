# UtilGetProcessPathFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180011fa8`
- end: `0x18001207c`
- name: `?UtilGetProcessPathFromHandle@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(HANDLE hProcess, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800111c0`

## callees

- `0x180003fe4`
- `0x1800096d0`
- `0x180011fa8`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `KERNEL32!QueryFullProcessImageNameW` at `0x18001200c`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18001200c`
- `KERNEL32!GetLastError` at `0x180012016`
- `KERNEL32!GetLastError` at `0x180012016`

## pseudocode

```c
__int64 __fastcall UtilGetProcessPathFromHandle(HANDLE hProcess, __int64 a2)
{
  DWORD LastError; // eax
  __int64 v6; // r8
  DWORD dwSize[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR ExeName; // [rsp+30h] [rbp-228h] BYREF
  _BYTE v9[526]; // [rsp+32h] [rbp-226h] BYREF

  ExeName = 0;
  memset_0(v9, 0, 0x206u);
  dwSize[0] = 260;
  if ( !a2 || !hProcess )
    return 2147942487LL;
  if ( QueryFullProcessImageNameW(hProcess, 0, &ExeName, dwSize) )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&v9[2 * v6 - 2] );
    return (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                              a2,
                              &ExeName) == 0
         ? 0x8007000E
         : 0;
  }
  else
  {
    LastError = GetLastError();
    return ERROR_HR_FROM_WIN32(LastError);
  }
}

```

## disassembly

```asm
0x180011fa8  mov     [rsp+arg_10], rbx
0x180011fad  mov     [rsp+arg_18], rsi
0x180011fb2  push    rdi
0x180011fb3  sub     rsp, 250h
0x180011fba  mov     rax, cs:__security_cookie
0x180011fc1  xor     rax, rsp
0x180011fc4  mov     [rsp+258h+var_18], rax
0x180011fcc  mov     rdi, rdx
0x180011fcf  mov     rbx, rcx
0x180011fd2  xor     esi, esi
0x180011fd4  lea     rcx, [rsp+258h+var_226]; void *
0x180011fd9  xor     edx, edx; Val
0x180011fdb  mov     [rsp+258h+ExeName], si
0x180011fe0  mov     r8d, 206h; Size
0x180011fe6  call    memset_0
0x180011feb  mov     [rsp+258h+dwSize], 104h
0x180011ff3  test    rdi, rdi
0x180011ff6  jz      short loc_180012052
0x180011ff8  test    rbx, rbx
0x180011ffb  jz      short loc_180012052
0x180011ffd  lea     r9, [rsp+258h+dwSize]; lpdwSize
0x180012002  xor     edx, edx; dwFlags
0x180012004  lea     r8, [rsp+258h+ExeName]; lpExeName
0x180012009  mov     rcx, rbx; hProcess
0x18001200c  call    cs:__imp_QueryFullProcessImageNameW
0x180012012  test    eax, eax
0x180012014  jnz     short loc_180012025
0x180012016  call    cs:__imp_GetLastError
0x18001201c  mov     ecx, eax; unsigned int
0x18001201e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180012023  jmp     short loc_180012057
0x180012025  lea     rax, [rsp+258h+ExeName]
0x18001202a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001202e  inc     r8
0x180012031  cmp     [rax+r8*2], si
0x180012036  jnz     short loc_18001202E
0x180012038  lea     rdx, [rsp+258h+ExeName]
0x18001203d  mov     rcx, rdi
0x180012040  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180012045  neg     al
0x180012047  sbb     eax, eax
0x180012049  not     eax
0x18001204b  and     eax, 8007000Eh
0x180012050  jmp     short loc_180012057
0x180012052  mov     eax, 80070057h
0x180012057  mov     rcx, [rsp+258h+var_18]
0x18001205f  xor     rcx, rsp; StackCookie
0x180012062  call    __security_check_cookie
0x180012067  lea     r11, [rsp+258h+var_8]
0x18001206f  mov     rbx, [r11+20h]
0x180012073  mov     rsi, [r11+28h]
0x180012077  mov     rsp, r11
0x18001207a  pop     rdi
0x18001207b  retn
```
