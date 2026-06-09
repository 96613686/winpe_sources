# CRdpSettingsFileStream::Write(ushort const *)

- ea: `0x180080f80`
- end: `0x180081225`
- name: `?Write@CRdpSettingsFileStream@@UEAAJPEBG@Z`
- size: `677`
- prototype: `int(CRdpSettingsFileStream *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x180010ba4`
- `0x18001c6e4`
- `0x180080f80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ff5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180081144`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180081144`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800810a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800810a8`
- `KERNEL32!WriteFile` at `0x180080feb`
- `KERNEL32!WriteFile` at `0x18008116d`
- `KERNEL32!WriteFile` at `0x180080feb`
- `KERNEL32!WriteFile` at `0x18008116d`

## pseudocode

```c
int __fastcall CRdpSettingsFileStream::Write(CRdpSettingsFileStream *this, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rsi
  void *v4; // rcx
  int result; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  __int64 v8; // rdi
  DWORD v9; // edi
  __int64 v10; // rax
  unsigned int v11; // ebp
  unsigned int cbMultiByte; // eax
  void *v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // eax
  int v16; // eax
  unsigned int v17; // eax
  __int16 v18; // [rsp+60h] [rbp+8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+18h] BYREF

  v2 = a2;
  NumberOfBytesWritten = 0;
  if ( *((_DWORD *)this + 19) )
  {
    if ( !a2 )
      return -2147467259;
    if ( *((_DWORD *)this + 158) )
    {
      if ( *((_DWORD *)this + 159) )
      {
        v4 = (void *)*((_QWORD *)this + 10);
        v18 = -257;
        if ( !WriteFile(v4, &v18, 2u, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        if ( NumberOfBytesWritten != 2 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return -2147023883;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v7 = 22;
          goto LABEL_13;
        }
        *((_DWORD *)this + 159) = 0;
      }
      v8 = -1;
      do
        ++v8;
      while ( v2[v8] );
      v9 = 2 * v8;
      goto LABEL_33;
    }
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v11 = v10 + 1;
    cbMultiByte = *((_DWORD *)this + 24);
    if ( v11 > cbMultiByte )
    {
      v13 = (void *)*((_QWORD *)this + 11);
      if ( v13 )
      {
        LocalFree(v13);
        *((_QWORD *)this + 11) = 0;
      }
      v14 = PAL_System_MemAlloc(v11);
      *((_QWORD *)this + 11) = v14;
      if ( !v14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
            v15,
            (__int64)"_pAnsiLineBuf");
        }
        return -2147024882;
      }
      *((_DWORD *)this + 24) = v11;
      cbMultiByte = v11;
    }
    v16 = WideCharToMultiByte(0, 0x640u, v2, -1, *((LPSTR *)this + 11), cbMultiByte, 0, 0);
    if ( !v16 )
      goto LABEL_6;
    v2 = (const WCHAR *)*((_QWORD *)this + 11);
    v9 = v16 - 1;
LABEL_33:
    if ( WriteFile(*((HANDLE *)this + 10), v2, v9, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten == v9 )
        return 0;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return -2147023883;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 24;
LABEL_13:
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
        CurrentThreadActivityIdPrefix);
      return -2147023883;
    }
LABEL_6:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v17);
  }
  return -2147024891;
}

```

## disassembly

```asm
0x180080f80  mov     r11, rsp
0x180080f83  mov     [r11+10h], rbx
0x180080f87  mov     [r11+20h], rbp
0x180080f8b  push    rsi
0x180080f8c  push    rdi
0x180080f8d  push    r14
0x180080f8f  sub     rsp, 40h
0x180080f93  xor     r14d, r14d
0x180080f96  mov     rsi, rdx
0x180080f99  mov     rbx, rcx
0x180080f9c  mov     [r11+18h], r14d
0x180080fa0  cmp     [rcx+4Ch], r14d
0x180080fa4  jz      loc_1800811CA
0x180080faa  test    rdx, rdx
0x180080fad  jz      loc_1800811C3
0x180080fb3  cmp     [rcx+278h], r14d
0x180080fba  jz      loc_180081080
0x180080fc0  cmp     [rcx+27Ch], r14d
0x180080fc7  jz      loc_18008106B
0x180080fcd  mov     rcx, [rcx+50h]; hFile
0x180080fd1  lea     r9, [r11+18h]; lpNumberOfBytesWritten
0x180080fd5  mov     eax, 0FEFFh
0x180080fda  mov     [r11-38h], r14
0x180080fde  lea     r8d, [r14+2]; nNumberOfBytesToWrite
0x180080fe2  mov     [rsp+58h+arg_0], ax
0x180080fe7  lea     rdx, [r11+8]; lpBuffer
0x180080feb  call    cs:__imp_WriteFile
0x180080ff1  test    eax, eax
0x180080ff3  jnz     short loc_180081010
0x180080ff5  call    cs:__imp_GetLastError
0x180080ffb  test    eax, eax
0x180080ffd  jle     loc_180081212
0x180081003  movzx   eax, ax
0x180081006  or      eax, 80070000h
0x18008100b  jmp     loc_180081212
0x180081010  cmp     [rsp+58h+NumberOfBytesWritten], 2
0x180081015  jz      short loc_180081064
0x180081017  mov     rcx, cs:WPP_GLOBAL_Control
0x18008101e  lea     rax, WPP_GLOBAL_Control
0x180081025  cmp     rcx, rax
0x180081028  jz      short loc_18008105A
0x18008102a  test    byte ptr [rcx+1Ch], 1
0x18008102e  jz      short loc_18008105A
0x180081030  cmp     byte ptr [rcx+19h], 2
0x180081034  jb      short loc_18008105A
0x180081036  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008103b  mov     edx, 16h
0x180081040  mov     rcx, cs:WPP_GLOBAL_Control
0x180081047  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x18008104e  mov     r9d, eax
0x180081051  mov     rcx, [rcx+10h]
0x180081055  call    WPP_SF_D
0x18008105a  mov     eax, 800703F5h
0x18008105f  jmp     loc_180081212
0x180081064  mov     [rbx+27Ch], r14d
0x18008106b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008106f  inc     rdi
0x180081072  cmp     [rsi+rdi*2], r14w
0x180081077  jnz     short loc_18008106F
0x180081079  add     edi, edi
0x18008107b  jmp     loc_180081159
0x180081080  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180081084  mov     rax, rdi
0x180081087  inc     rax
0x18008108a  cmp     [rdx+rax*2], r14w
0x18008108f  jnz     short loc_180081087
0x180081091  lea     ebp, [rax+1]
0x180081094  mov     eax, [rcx+60h]
0x180081097  cmp     ebp, eax
0x180081099  jbe     loc_180081120
0x18008109f  mov     rcx, [rcx+58h]; hMem
0x1800810a3  test    rcx, rcx
0x1800810a6  jz      short loc_1800810B2
0x1800810a8  call    cs:__imp_LocalFree
0x1800810ae  mov     [rbx+58h], r14
0x1800810b2  mov     ecx, ebp
0x1800810b4  call    PAL_System_MemAlloc
0x1800810b9  mov     [rbx+58h], rax
0x1800810bd  test    rax, rax
0x1800810c0  jnz     short loc_18008111B
0x1800810c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800810c9  lea     rax, WPP_GLOBAL_Control
0x1800810d0  cmp     rcx, rax
0x1800810d3  jz      short loc_180081111
0x1800810d5  test    byte ptr [rcx+1Ch], 8
0x1800810d9  jz      short loc_180081111
0x1800810db  cmp     byte ptr [rcx+19h], 2
0x1800810df  jb      short loc_180081111
0x1800810e1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800810e6  lea     rcx, aPansilinebuf; "_pAnsiLineBuf"
0x1800810ed  mov     edx, 17h
0x1800810f2  mov     [rsp+58h+lpMultiByteStr], rcx
0x1800810f7  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1800810fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180081105  mov     r9d, eax
0x180081108  mov     rcx, [rcx+10h]
0x18008110c  call    WPP_SF_Ds
0x180081111  mov     eax, 8007000Eh
0x180081116  jmp     loc_180081212
0x18008111b  mov     [rbx+60h], ebp
0x18008111e  mov     eax, ebp
0x180081120  mov     [rsp+58h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180081125  mov     r9d, edi; cchWideChar
0x180081128  mov     [rsp+58h+lpDefaultChar], r14; lpDefaultChar
0x18008112d  mov     r8, rsi; lpWideCharStr
0x180081130  mov     [rsp+58h+cbMultiByte], eax; cbMultiByte
0x180081134  mov     edx, 640h; dwFlags
0x180081139  mov     rax, [rbx+58h]
0x18008113d  xor     ecx, ecx; CodePage
0x18008113f  mov     [rsp+58h+lpMultiByteStr], rax; lpMultiByteStr
0x180081144  call    cs:__imp_WideCharToMultiByte
0x18008114a  test    eax, eax
0x18008114c  jz      loc_180080FF5
0x180081152  mov     rsi, [rbx+58h]
0x180081156  lea     edi, [rax-1]
0x180081159  mov     rcx, [rbx+50h]; hFile
0x18008115d  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180081162  mov     r8d, edi; nNumberOfBytesToWrite
0x180081165  mov     [rsp+58h+lpMultiByteStr], r14; lpOverlapped
0x18008116a  mov     rdx, rsi; lpBuffer
0x18008116d  call    cs:__imp_WriteFile
0x180081173  test    eax, eax
0x180081175  jz      loc_180080FF5
0x18008117b  cmp     [rsp+58h+NumberOfBytesWritten], edi
0x18008117f  jnz     short loc_180081189
0x180081181  mov     eax, r14d
0x180081184  jmp     loc_180081212
0x180081189  mov     rcx, cs:WPP_GLOBAL_Control
0x180081190  lea     rax, WPP_GLOBAL_Control
0x180081197  cmp     rcx, rax
0x18008119a  jz      loc_18008105A
0x1800811a0  test    byte ptr [rcx+1Ch], 1
0x1800811a4  jz      loc_18008105A
0x1800811aa  cmp     byte ptr [rcx+19h], 2
0x1800811ae  jb      loc_18008105A
0x1800811b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800811b9  mov     edx, 18h
0x1800811be  jmp     loc_180081040
0x1800811c3  mov     eax, 80004005h
0x1800811c8  jmp     short loc_180081212
0x1800811ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800811d1  lea     rax, WPP_GLOBAL_Control
0x1800811d8  cmp     rcx, rax
0x1800811db  jz      short loc_18008120D
0x1800811dd  test    byte ptr [rcx+1Ch], 1
0x1800811e1  jz      short loc_18008120D
0x1800811e3  cmp     byte ptr [rcx+19h], 2
0x1800811e7  jb      short loc_18008120D
0x1800811e9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800811ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800811f5  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1800811fc  mov     edx, 19h
0x180081201  mov     r9d, eax
0x180081204  mov     rcx, [rcx+10h]
0x180081208  call    WPP_SF_D
0x18008120d  mov     eax, 80070005h
0x180081212  mov     rbx, [rsp+58h+arg_8]
0x180081217  mov     rbp, [rsp+58h+arg_18]
0x18008121c  add     rsp, 40h
0x180081220  pop     r14
0x180081222  pop     rdi
0x180081223  pop     rsi
0x180081224  retn
```
