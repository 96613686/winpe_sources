# GetFullPath

- ea: `0x14001a508`
- end: `0x14001a76e`
- name: `GetFullPath`
- size: `614`
- prototype: `__int64 __fastcall(wchar_t *Src, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140019c4c`

## callees

- `0x140010450`
- `0x14001a508`
- `0x14001a774`
- `0x140022cec`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a62f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a62f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14001a556`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14001a621`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14001a556`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14001a621`

## pseudocode

```c
void __fastcall GetFullPath(wchar_t *Src, _QWORD *lpBuffer)
{
  _QWORD *v2; // rbx
  WCHAR *v4; // r8
  DWORD FullPathNameW; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  WCHAR *v8; // r8
  signed int v9; // eax
  unsigned int v10; // ebx
  const char *v11; // [rsp+20h] [rbp-58h]
  _BYTE pExceptionObject[48]; // [rsp+40h] [rbp-38h] BYREF

  v2 = lpBuffer;
  if ( Src && *Src )
  {
    std::wstring::resize(lpBuffer, 260);
    if ( v2[3] <= 7u )
      v4 = (WCHAR *)v2;
    else
      v4 = (WCHAR *)*v2;
    FullPathNameW = GetFullPathNameW(Src, *((_DWORD *)v2 + 4), v4, 0);
    if ( !FullPathNameW )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( !v7 )
        v7 = -2147418113;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, v7);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v7, 0, 0, v11, 31, 1u, Src);
      throw (EvtException *)pExceptionObject;
    }
    if ( FullPathNameW > *((_DWORD *)v2 + 4) )
    {
      std::wstring::resize(v2, FullPathNameW);
      if ( v2[3] <= 7u )
        v8 = (WCHAR *)v2;
      else
        v8 = (WCHAR *)*v2;
      FullPathNameW = GetFullPathNameW(Src, *((_DWORD *)v2 + 4), v8, 0);
      if ( !FullPathNameW )
      {
        v9 = GetLastError();
        v10 = v9;
        if ( v9 > 0 )
          v10 = (unsigned __int16)v9 | 0x80070000;
        if ( !v10 )
          v10 = -2147418113;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, v10);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, v10, 0, 0, v11, 42, 1u, Src);
        throw (EvtException *)pExceptionObject;
      }
      if ( FullPathNameW > *((_DWORD *)v2 + 4) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_2969cf25331937701283eddb1dcf16ae_Traceguids,
            2147942522LL);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0x8007007A, 0, 0, v11, 48, 1u, Src);
        throw (EvtException *)pExceptionObject;
      }
    }
    std::wstring::resize(v2, FullPathNameW);
  }
  else
  {
    lpBuffer[2] = 0;
    if ( lpBuffer[3] > 7u )
      v2 = (_QWORD *)*lpBuffer;
    *(_WORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x14001a508  mov     [rsp+arg_0], rbx
0x14001a50d  mov     [rsp+arg_8], rsi
0x14001a512  push    rdi
0x14001a513  sub     rsp, 70h
0x14001a517  xor     esi, esi
0x14001a519  mov     rbx, rdx
0x14001a51c  mov     rdi, rcx
0x14001a51f  test    rcx, rcx
0x14001a522  jz      loc_14001A74B
0x14001a528  cmp     [rcx], si
0x14001a52b  jz      loc_14001A74B
0x14001a531  mov     edx, 104h
0x14001a536  mov     rcx, rbx
0x14001a539  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x14001a53e  cmp     qword ptr [rbx+18h], 7
0x14001a543  jbe     short loc_14001A54A
0x14001a545  mov     r8, [rbx]
0x14001a548  jmp     short loc_14001A54D
0x14001a54a  mov     r8, rbx; lpBuffer
0x14001a54d  mov     edx, [rbx+10h]; nBufferLength
0x14001a550  xor     r9d, r9d; lpFilePart
0x14001a553  mov     rcx, rdi; lpFileName
0x14001a556  call    cs:__imp_GetFullPathNameW
0x14001a55c  test    eax, eax
0x14001a55e  jnz     loc_14001A5F6
0x14001a564  call    cs:__imp_GetLastError
0x14001a56a  mov     ebx, eax
0x14001a56c  test    eax, eax
0x14001a56e  jle     short loc_14001A579
0x14001a570  movzx   ebx, ax
0x14001a573  or      ebx, 80070000h
0x14001a579  test    ebx, ebx
0x14001a57b  mov     eax, 8000FFFFh
0x14001a580  cmovz   ebx, eax
0x14001a583  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a58a  lea     rax, WPP_GLOBAL_Control
0x14001a591  cmp     rcx, rax
0x14001a594  jz      short loc_14001A5BD
0x14001a596  test    dword ptr [rcx+1Ch], 400000h
0x14001a59d  jz      short loc_14001A5BD
0x14001a59f  cmp     byte ptr [rcx+19h], 2
0x14001a5a3  jb      short loc_14001A5BD
0x14001a5a5  mov     rcx, [rcx+10h]
0x14001a5a9  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x14001a5b0  mov     edx, 0Ah
0x14001a5b5  mov     r9d, ebx
0x14001a5b8  call    WPP_SF_d
0x14001a5bd  mov     [rsp+78h+Src], rdi; Src
0x14001a5c2  lea     rcx, [rsp+78h+pExceptionObject]; this
0x14001a5c7  mov     [rsp+78h+var_48], 1; unsigned int
0x14001a5cf  xor     r9d, r9d; unsigned int
0x14001a5d2  xor     r8d, r8d; unsigned int
0x14001a5d5  mov     [rsp+78h+var_50], 1Fh; int
0x14001a5dd  mov     edx, ebx; unsigned int
0x14001a5df  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001a5e4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001a5eb  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14001a5f0  call    _CxxThrowException_0
0x14001a5f6  cmp     eax, [rbx+10h]
0x14001a5f9  jbe     loc_14001A73F
0x14001a5ff  mov     edx, eax
0x14001a601  mov     rcx, rbx
0x14001a604  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x14001a609  cmp     qword ptr [rbx+18h], 7
0x14001a60e  jbe     short loc_14001A615
0x14001a610  mov     r8, [rbx]
0x14001a613  jmp     short loc_14001A618
0x14001a615  mov     r8, rbx; lpBuffer
0x14001a618  mov     edx, [rbx+10h]; nBufferLength
0x14001a61b  xor     r9d, r9d; lpFilePart
0x14001a61e  mov     rcx, rdi; lpFileName
0x14001a621  call    cs:__imp_GetFullPathNameW
0x14001a627  test    eax, eax
0x14001a629  jnz     loc_14001A6C1
0x14001a62f  call    cs:__imp_GetLastError
0x14001a635  mov     ebx, eax
0x14001a637  test    eax, eax
0x14001a639  jle     short loc_14001A644
0x14001a63b  movzx   ebx, ax
0x14001a63e  or      ebx, 80070000h
0x14001a644  test    ebx, ebx
0x14001a646  mov     eax, 8000FFFFh
0x14001a64b  cmovz   ebx, eax
0x14001a64e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a655  lea     rax, WPP_GLOBAL_Control
0x14001a65c  cmp     rcx, rax
0x14001a65f  jz      short loc_14001A688
0x14001a661  test    dword ptr [rcx+1Ch], 400000h
0x14001a668  jz      short loc_14001A688
0x14001a66a  cmp     byte ptr [rcx+19h], 2
0x14001a66e  jb      short loc_14001A688
0x14001a670  mov     rcx, [rcx+10h]
0x14001a674  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x14001a67b  mov     edx, 0Bh
0x14001a680  mov     r9d, ebx
0x14001a683  call    WPP_SF_d
0x14001a688  mov     [rsp+78h+Src], rdi; Src
0x14001a68d  lea     rcx, [rsp+78h+pExceptionObject]; this
0x14001a692  mov     [rsp+78h+var_48], 1; unsigned int
0x14001a69a  xor     r9d, r9d; unsigned int
0x14001a69d  xor     r8d, r8d; unsigned int
0x14001a6a0  mov     [rsp+78h+var_50], 2Ah ; '*'; int
0x14001a6a8  mov     edx, ebx; unsigned int
0x14001a6aa  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001a6af  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001a6b6  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14001a6bb  call    _CxxThrowException_0
0x14001a6c1  cmp     eax, [rbx+10h]
0x14001a6c4  jbe     short loc_14001A73F
0x14001a6c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6cd  lea     rax, WPP_GLOBAL_Control
0x14001a6d4  cmp     rcx, rax
0x14001a6d7  jz      short loc_14001A703
0x14001a6d9  test    dword ptr [rcx+1Ch], 400000h
0x14001a6e0  jz      short loc_14001A703
0x14001a6e2  cmp     byte ptr [rcx+19h], 2
0x14001a6e6  jb      short loc_14001A703
0x14001a6e8  mov     rcx, [rcx+10h]
0x14001a6ec  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x14001a6f3  mov     edx, 0Ch
0x14001a6f8  mov     r9d, 8007007Ah
0x14001a6fe  call    WPP_SF_d
0x14001a703  mov     [rsp+78h+Src], rdi; Src
0x14001a708  lea     rcx, [rsp+78h+pExceptionObject]; this
0x14001a70d  mov     [rsp+78h+var_48], 1; unsigned int
0x14001a715  xor     r9d, r9d; unsigned int
0x14001a718  xor     r8d, r8d; unsigned int
0x14001a71b  mov     [rsp+78h+var_50], 30h ; '0'; int
0x14001a723  mov     edx, 8007007Ah; unsigned int
0x14001a728  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001a72d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001a734  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14001a739  call    _CxxThrowException_0
0x14001a73f  mov     edx, eax
0x14001a741  mov     rcx, rbx
0x14001a744  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x14001a749  jmp     short loc_14001A75C
0x14001a74b  mov     [rdx+10h], rsi
0x14001a74f  cmp     qword ptr [rdx+18h], 7
0x14001a754  jbe     short loc_14001A759
0x14001a756  mov     rbx, [rdx]
0x14001a759  mov     [rbx], si
0x14001a75c  lea     r11, [rsp+78h+var_8]
0x14001a761  mov     rbx, [r11+10h]
0x14001a765  mov     rsi, [r11+18h]
0x14001a769  mov     rsp, r11
0x14001a76c  pop     rdi
0x14001a76d  retn
```
