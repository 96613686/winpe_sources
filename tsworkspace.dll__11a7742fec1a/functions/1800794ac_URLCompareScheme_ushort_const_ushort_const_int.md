# URLCompareScheme(ushort const *,ushort const *,int *)

- ea: `0x1800794ac`
- end: `0x180079625`
- name: `?URLCompareScheme@@YAJPEBG0PEAH@Z`
- size: `377`
- prototype: `__int64 __fastcall(LPCWSTR lpszUrl, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002d6ec`
- `0x180059490`

## callees

- `0x1800044bf`
- `0x18000b1d8`
- `0x18000ec94`
- `0x1800794ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007957c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007957c`
- `KERNEL32!CompareStringOrdinal` at `0x180079600`
- `KERNEL32!CompareStringOrdinal` at `0x180079600`
- `WININET!InternetCrackUrlW` at `0x180079572`
- `WININET!InternetCrackUrlW` at `0x180079572`

## pseudocode

```c
__int64 __fastcall URLCompareScheme(LPCWSTR lpszUrl, const unsigned __int16 *a2, int *a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  signed int LastError; // ebx
  unsigned int v8; // eax
  struct $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+30h] [rbp-78h] BYREF

  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  if ( !lpszUrl )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 26;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_8f87464425bd38a0257d033d5861bd18_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147024809);
    return (unsigned int)-2147024809;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 28;
    goto LABEL_6;
  }
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwSchemeLength = 1;
  if ( InternetCrackUrlW(lpszUrl, 0, 0, &UrlComponents) )
  {
    *a3 = CompareStringOrdinal(UrlComponents.lpszScheme, UrlComponents.dwSchemeLength, L"radc-aad", -1, 1) == 2;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids, v8, LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800794ac  mov     [rsp+arg_0], rbx
0x1800794b1  push    rdi
0x1800794b2  sub     rsp, 0A0h
0x1800794b9  xor     edx, edx; Val
0x1800794bb  mov     rbx, r8
0x1800794be  mov     rdi, rcx
0x1800794c1  lea     rcx, [rsp+0A8h+UrlComponents]; void *
0x1800794c6  lea     r8d, [rdx+68h]; Size
0x1800794ca  call    memset_0
0x1800794cf  test    rdi, rdi
0x1800794d2  jnz     short loc_180079527
0x1800794d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800794db  lea     rax, WPP_GLOBAL_Control
0x1800794e2  cmp     rcx, rax
0x1800794e5  jz      short loc_18007951D
0x1800794e7  test    byte ptr [rcx+1Ch], 8
0x1800794eb  jz      short loc_18007951D
0x1800794ed  cmp     byte ptr [rcx+19h], 2
0x1800794f1  jb      short loc_18007951D
0x1800794f3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800794f8  lea     edx, [rdi+1Ah]
0x1800794fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180079502  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x180079509  mov     r9d, eax
0x18007950c  mov     [rsp+0A8h+bIgnoreCase], 80070057h
0x180079514  mov     rcx, [rcx+10h]
0x180079518  call    WPP_SF_Dd
0x18007951d  mov     ebx, 80070057h
0x180079522  jmp     loc_180079612
0x180079527  test    rbx, rbx
0x18007952a  jnz     short loc_180079555
0x18007952c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079533  lea     rax, WPP_GLOBAL_Control
0x18007953a  cmp     rcx, rax
0x18007953d  jz      short loc_18007951D
0x18007953f  test    byte ptr [rcx+1Ch], 8
0x180079543  jz      short loc_18007951D
0x180079545  cmp     byte ptr [rcx+19h], 2
0x180079549  jb      short loc_18007951D
0x18007954b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079550  lea     edx, [rbx+1Ch]
0x180079553  jmp     short loc_1800794FB
0x180079555  lea     r9, [rsp+0A8h+UrlComponents]; lpUrlComponents
0x18007955a  mov     [rsp+0A8h+UrlComponents.dwStructSize], 68h ; 'h'
0x180079562  xor     r8d, r8d; dwFlags
0x180079565  mov     [rsp+0A8h+UrlComponents.dwSchemeLength], 1
0x18007956d  xor     edx, edx; dwUrlLength
0x18007956f  mov     rcx, rdi; lpszUrl
0x180079572  call    cs:__imp_InternetCrackUrlW
0x180079578  test    eax, eax
0x18007957a  jnz     short loc_1800795E4
0x18007957c  call    cs:__imp_GetLastError
0x180079582  mov     ebx, eax
0x180079584  mov     rcx, cs:WPP_GLOBAL_Control
0x18007958b  lea     rax, WPP_GLOBAL_Control
0x180079592  cmp     rcx, rax
0x180079595  jz      short loc_1800795CB
0x180079597  test    byte ptr [rcx+1Ch], 8
0x18007959b  jz      short loc_1800795CB
0x18007959d  cmp     byte ptr [rcx+19h], 2
0x1800795a1  jb      short loc_1800795CB
0x1800795a3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800795a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800795af  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x1800795b6  mov     edx, 1Dh
0x1800795bb  mov     [rsp+0A8h+bIgnoreCase], ebx
0x1800795bf  mov     r9d, eax
0x1800795c2  mov     rcx, [rcx+10h]
0x1800795c6  call    WPP_SF_Dd
0x1800795cb  test    ebx, ebx
0x1800795cd  jle     short loc_1800795D8
0x1800795cf  movzx   ebx, bx
0x1800795d2  or      ebx, 80070000h
0x1800795d8  test    ebx, ebx
0x1800795da  mov     eax, 80004005h
0x1800795df  cmovns  ebx, eax
0x1800795e2  jmp     short loc_180079612
0x1800795e4  mov     edx, [rsp+0A8h+UrlComponents.dwSchemeLength]; cchCount1
0x1800795e8  lea     r8, aRadcAad; "radc-aad"
0x1800795ef  mov     rcx, [rsp+0A8h+UrlComponents.lpszScheme]; lpString1
0x1800795f4  or      r9d, 0FFFFFFFFh; cchCount2
0x1800795f8  mov     [rsp+0A8h+bIgnoreCase], 1; bIgnoreCase
0x180079600  call    cs:__imp_CompareStringOrdinal
0x180079606  xor     ecx, ecx
0x180079608  cmp     eax, 2
0x18007960b  setz    cl
0x18007960e  mov     [rbx], ecx
0x180079610  xor     ebx, ebx
0x180079612  mov     eax, ebx
0x180079614  mov     rbx, [rsp+0A8h+arg_0]
0x18007961c  add     rsp, 0A0h
0x180079623  pop     rdi
0x180079624  retn
```
