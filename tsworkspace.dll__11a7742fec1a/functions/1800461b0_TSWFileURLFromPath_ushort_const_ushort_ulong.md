# TSWFileURLFromPath(ushort const *,ushort *,ulong *)

- ea: `0x1800461b0`
- end: `0x18004634f`
- name: `?TSWFileURLFromPath@@YAJPEBGPEAGPEAK@Z`
- size: `415`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180033718`
- `0x180067078`
- `0x1800676d8`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x1800461b0`
- `0x18009a520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004624c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004624c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800461e5`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800461e5`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x1800462cd`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x1800462cd`

## string_xrefs

- `0x1800462fd`: `UrlCreateFromPathW failed`

## pseudocode

```c
__int64 __fastcall TSWFileURLFromPath(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned int *a3)
{
  DWORD v5; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  signed int v9; // eax
  HRESULT v10; // ebx
  unsigned int v11; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HRESULT v14; // [rsp+28h] [rbp-230h]
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  *a2 = 0;
  v5 = ExpandEnvironmentStringsW(a1, Dst, 0x104u);
  if ( v5 )
  {
    if ( v5 <= 0x104 )
    {
      v10 = UrlCreateFromPathW(Dst, a2, a3, 0);
      if ( v10 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = v10;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"UrlCreateFromPathW failed",
          v14);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids,
          v11,
          -2147024774);
      }
      return (unsigned int)-2147024774;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids, v8, v7);
    }
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800461b0  mov     [rsp+arg_18], rbx
0x1800461b5  push    rdi
0x1800461b6  sub     rsp, 250h
0x1800461bd  mov     rax, cs:__security_cookie
0x1800461c4  xor     rax, rsp
0x1800461c7  mov     [rsp+258h+var_18], rax
0x1800461cf  xor     eax, eax
0x1800461d1  mov     rdi, r8
0x1800461d4  mov     [rdx], ax
0x1800461d7  mov     rbx, rdx
0x1800461da  lea     rdx, [rsp+258h+Dst]; lpDst
0x1800461df  mov     r8d, 104h; nSize
0x1800461e5  call    cs:__imp_ExpandEnvironmentStringsW
0x1800461eb  test    eax, eax
0x1800461ed  jnz     short loc_180046266
0x1800461ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800461f6  lea     rax, WPP_GLOBAL_Control
0x1800461fd  mov     edi, 80070000h
0x180046202  cmp     rcx, rax
0x180046205  jz      short loc_18004624C
0x180046207  test    byte ptr [rcx+1Ch], 8
0x18004620b  jz      short loc_18004624C
0x18004620d  cmp     byte ptr [rcx+19h], 2
0x180046211  jb      short loc_18004624C
0x180046213  call    cs:__imp_GetLastError
0x180046219  mov     ebx, eax
0x18004621b  test    eax, eax
0x18004621d  jle     short loc_180046224
0x18004621f  movzx   ebx, ax
0x180046222  or      ebx, edi
0x180046224  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046229  mov     rcx, cs:WPP_GLOBAL_Control
0x180046230  lea     r8, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids
0x180046237  mov     edx, 0Eh
0x18004623c  mov     dword ptr [rsp+258h+var_238], ebx
0x180046240  mov     r9d, eax
0x180046243  mov     rcx, [rcx+10h]
0x180046247  call    WPP_SF_Dd
0x18004624c  call    cs:__imp_GetLastError
0x180046252  mov     ebx, eax
0x180046254  test    eax, eax
0x180046256  jle     loc_18004632C
0x18004625c  movzx   ebx, ax
0x18004625f  or      ebx, edi
0x180046261  jmp     loc_18004632C
0x180046266  cmp     eax, 104h
0x18004626b  jbe     short loc_1800462BF
0x18004626d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046274  lea     rax, WPP_GLOBAL_Control
0x18004627b  cmp     rcx, rax
0x18004627e  jz      short loc_1800462B8
0x180046280  test    byte ptr [rcx+1Ch], 8
0x180046284  jz      short loc_1800462B8
0x180046286  cmp     byte ptr [rcx+19h], 2
0x18004628a  jb      short loc_1800462B8
0x18004628c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046291  mov     rcx, cs:WPP_GLOBAL_Control
0x180046298  lea     r8, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids
0x18004629f  mov     edx, 0Fh
0x1800462a4  mov     dword ptr [rsp+258h+var_238], 8007007Ah
0x1800462ac  mov     r9d, eax
0x1800462af  mov     rcx, [rcx+10h]
0x1800462b3  call    WPP_SF_Dd
0x1800462b8  mov     ebx, 8007007Ah
0x1800462bd  jmp     short loc_18004632C
0x1800462bf  xor     r9d, r9d; dwFlags
0x1800462c2  lea     rcx, [rsp+258h+Dst]; pszPath
0x1800462c7  mov     r8, rdi; pcchUrl
0x1800462ca  mov     rdx, rbx; pszUrl
0x1800462cd  call    cs:__imp_UrlCreateFromPathW
0x1800462d3  mov     ebx, eax
0x1800462d5  test    eax, eax
0x1800462d7  jns     short loc_18004632C
0x1800462d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462e0  lea     rax, WPP_GLOBAL_Control
0x1800462e7  cmp     rcx, rax
0x1800462ea  jz      short loc_18004632C
0x1800462ec  test    byte ptr [rcx+1Ch], 8
0x1800462f0  jz      short loc_18004632C
0x1800462f2  cmp     byte ptr [rcx+19h], 2
0x1800462f6  jb      short loc_18004632C
0x1800462f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800462fd  lea     rcx, aUrlcreatefromp; "UrlCreateFromPathW failed"
0x180046304  mov     [rsp+258h+var_230], ebx
0x180046308  mov     [rsp+258h+var_238], rcx
0x18004630d  lea     r8, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids
0x180046314  mov     rcx, cs:WPP_GLOBAL_Control
0x18004631b  mov     edx, 10h
0x180046320  mov     r9d, eax
0x180046323  mov     rcx, [rcx+10h]
0x180046327  call    WPP_SF_DsD
0x18004632c  mov     eax, ebx
0x18004632e  mov     rcx, [rsp+258h+var_18]
0x180046336  xor     rcx, rsp; StackCookie
0x180046339  call    __security_check_cookie
0x18004633e  mov     rbx, [rsp+258h+arg_18]
0x180046346  add     rsp, 250h
0x18004634d  pop     rdi
0x18004634e  retn
```
