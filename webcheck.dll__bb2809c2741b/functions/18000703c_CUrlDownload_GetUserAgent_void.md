# CUrlDownload::GetUserAgent(void)

- ea: `0x18000703c`
- end: `0x180007173`
- name: `?GetUserAgent@CUrlDownload@@QEAAPEBGXZ`
- size: `311`
- prototype: `const unsigned __int16 *__fastcall(CUrlDownload *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180006670`
- `0x1800074d0`

## callees

- `0x180003950`
- `0x18000703c`
- `0x180029280`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800070b9`
- `KERNEL32!LocalAlloc` at `0x1800070b9`
- `KERNEL32!LocalFree` at `0x18000713f`
- `KERNEL32!LocalFree` at `0x18000713f`
- `SHLWAPI!StrRChrW` at `0x18000710b`
- `SHLWAPI!StrRChrW` at `0x18000710b`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x1800070ee`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x1800070ee`
- `urlmon!UrlMkGetSessionOption` at `0x18000708e`
- `urlmon!UrlMkGetSessionOption` at `0x18000708e`

## string_xrefs

- `0x180007123`: `; MSIECrawler)`

## pseudocode

```c
const unsigned __int16 *__fastcall CUrlDownload::GetUserAgent(CUrlDownload *this)
{
  const unsigned __int16 *result; // rax
  __int64 v3; // rdi
  int v4; // esi
  _WORD *v5; // rax
  __int64 v6; // rbp
  PWSTR v7; // rdi
  _BYTE *v8; // rcx
  DWORD pdwBufferLengthOut[4]; // [rsp+30h] [rbp-448h] BYREF
  CHAR pBuffer[1024]; // [rsp+40h] [rbp-438h] BYREF

  result = (const unsigned __int16 *)*((_QWORD *)this + 94);
  if ( !result )
  {
    pdwBufferLengthOut[0] = 0;
    pBuffer[0] = 0;
    UrlMkGetSessionOption(0x10000001u, pBuffer, 0x400u, pdwBufferLengthOut, 0);
    v3 = -1;
    do
      ++v3;
    while ( pBuffer[v3] );
    if ( (int)v3 > 0 )
    {
      v4 = v3 + 15;
      v5 = LocalAlloc(0, 2LL * ((int)v3 + 15));
      *((_QWORD *)this + 94) = v5;
      if ( v5 )
      {
        v6 = (int)v3;
        *v5 = 0;
        v7 = &v5[(int)v3 - 1];
        SHAnsiToUnicode(pBuffer, *((PWSTR *)this + 94), v4);
        if ( *v7 != 41 )
          v7 = StrRChrW(*((PCWSTR *)this + 94), (PCWSTR)(*((_QWORD *)this + 94) + 2 * v6), 0x29u);
        v8 = (_BYTE *)*((_QWORD *)this + 94);
        if ( v7 )
        {
          StringCchCopyW(v7, (int)(v4 - (((char *)v7 - v8) >> 1)), L"; MSIECrawler)");
        }
        else
        {
          LocalFree(v8);
          *((_QWORD *)this + 94) = 0;
        }
      }
    }
    return (const unsigned __int16 *)*((_QWORD *)this + 94);
  }
  return result;
}

```

## disassembly

```asm
0x18000703c  push    rbx
0x18000703e  push    rbp
0x18000703f  push    rsi
0x180007040  push    rdi
0x180007041  sub     rsp, 458h
0x180007048  mov     rax, cs:__security_cookie
0x18000704f  xor     rax, rsp
0x180007052  mov     [rsp+478h+var_38], rax
0x18000705a  mov     rax, [rcx+2F0h]
0x180007061  mov     rbx, rcx
0x180007064  test    rax, rax
0x180007067  jnz     loc_180007157
0x18000706d  lea     r9, [rsp+478h+pdwBufferLengthOut]; pdwBufferLengthOut
0x180007072  mov     [rsp+478h+pdwBufferLengthOut], eax
0x180007076  mov     r8d, 400h; dwBufferLength
0x18000707c  mov     [rsp+478h+pBuffer], al
0x180007080  lea     rdx, [rsp+478h+pBuffer]; pBuffer
0x180007085  mov     [rsp+478h+dwReserved], eax; dwReserved
0x180007089  mov     ecx, 10000001h; dwOption
0x18000708e  call    cs:__imp_UrlMkGetSessionOption
0x180007094  lea     rax, [rsp+478h+pBuffer]
0x180007099  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000709d  inc     rdi
0x1800070a0  cmp     byte ptr [rax+rdi], 0
0x1800070a4  jnz     short loc_18000709D
0x1800070a6  test    edi, edi
0x1800070a8  jle     loc_180007150
0x1800070ae  lea     esi, [rdi+0Fh]
0x1800070b1  xor     ecx, ecx; uFlags
0x1800070b3  movsxd  rdx, esi
0x1800070b6  add     rdx, rdx; uBytes
0x1800070b9  call    cs:__imp_LocalAlloc
0x1800070bf  mov     [rbx+2F0h], rax
0x1800070c6  test    rax, rax
0x1800070c9  jz      loc_180007150
0x1800070cf  xor     ecx, ecx
0x1800070d1  movsxd  rbp, edi
0x1800070d4  mov     [rax], cx
0x1800070d7  mov     r8d, esi; cwchBuf
0x1800070da  mov     rdx, [rbx+2F0h]; pwszDst
0x1800070e1  lea     rcx, [rsp+478h+pBuffer]; pszSrc
0x1800070e6  lea     rdi, [rbp-1]
0x1800070ea  lea     rdi, [rax+rdi*2]
0x1800070ee  call    cs:__imp_SHAnsiToUnicode
0x1800070f4  mov     r8d, 29h ; ')'; wMatch
0x1800070fa  cmp     [rdi], r8w
0x1800070fe  jz      short loc_180007114
0x180007100  mov     rcx, [rbx+2F0h]; pszStart
0x180007107  lea     rdx, [rcx+rbp*2]; pszEnd
0x18000710b  call    cs:__imp_StrRChrW
0x180007111  mov     rdi, rax
0x180007114  mov     rcx, [rbx+2F0h]; hMem
0x18000711b  test    rdi, rdi
0x18000711e  jz      short loc_18000713F
0x180007120  mov     rax, rdi
0x180007123  lea     r8, aMsiecrawler; "; MSIECrawler)"
0x18000712a  sub     rax, rcx
0x18000712d  mov     rcx, rdi; unsigned __int16 *
0x180007130  sar     rax, 1
0x180007133  sub     esi, eax
0x180007135  movsxd  rdx, esi; unsigned __int64
0x180007138  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000713d  jmp     short loc_180007150
0x18000713f  call    cs:__imp_LocalFree
0x180007145  mov     qword ptr [rbx+2F0h], 0
0x180007150  mov     rax, [rbx+2F0h]
0x180007157  mov     rcx, [rsp+478h+var_38]
0x18000715f  xor     rcx, rsp; StackCookie
0x180007162  call    __security_check_cookie
0x180007167  add     rsp, 458h
0x18000716e  pop     rdi
0x18000716f  pop     rsi
0x180007170  pop     rbp
0x180007171  pop     rbx
0x180007172  retn
```
