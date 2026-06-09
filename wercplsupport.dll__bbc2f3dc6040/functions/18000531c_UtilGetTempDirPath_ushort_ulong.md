# UtilGetTempDirPath(ushort *,ulong)

- ea: `0x18000531c`
- end: `0x18000565c`
- name: `?UtilGetTempDirPath@@YAJPEAGK@Z`
- size: `832`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x180002c98`

## callees

- `0x180001270`
- `0x18000131c`
- `0x180001680`
- `0x1800045cc`
- `0x18000531c`
- `0x180012172`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000538a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000538a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005372`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005517`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180005357`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180005357`

## pseudocode

```c
__int64 __fastcall UtilGetTempDirPath(wchar_t *String1)
{
  DWORD FileAttributesW; // eax
  signed int v3; // eax
  int v4; // r8d
  int v5; // r9d
  signed int v6; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  signed int LastError; // eax
  __int64 v10; // rcx
  int v12; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *v13; // [rsp+38h] [rbp-31h] BYREF
  void *Block; // [rsp+40h] [rbp-29h]
  char *v15; // [rsp+48h] [rbp-21h]
  _WORD v16[8]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-9h] BYREF
  int *v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]

  if ( String1 )
  {
    *String1 = 0;
    if ( !(unsigned int)GetTempPath2W(260, String1) || !*String1 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
      {
        v12 = v6;
        v18 = &v12;
        v19 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, &unk_180018580, 0, 0, 3, v17);
      }
      goto LABEL_36;
    }
    FileAttributesW = GetFileAttributesW(String1);
    if ( (FileAttributesW == -1 || (FileAttributesW & 0x10) == 0) && !CreateDirectoryW(String1, 0) )
    {
      v3 = GetLastError();
      v6 = v3;
      if ( v3 > 0 )
        v6 = (unsigned __int16)v3 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
      {
        v12 = v6;
        v13 = String1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          qword_18001C020,
          (unsigned int)byte_1800183BD,
          v4,
          v5,
          (__int64)&v13,
          (__int64)&v12);
      }
      *String1 = 0;
LABEL_36:
      if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 )
      {
        v10 = qword_18001C020 & 8;
        if ( v10 == qword_18001C020 )
        {
          v12 = v6;
          v13 = String1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)&dword_1800189DC,
            v4,
            v5,
            (__int64)&v13,
            (__int64)&v12);
        }
      }
      return (unsigned int)v6;
    }
    v16[0] = 0;
    Block = v16;
    v15 = (char *)v16;
    if ( (unsigned int)UtilGetFinalPath(String1) )
    {
      v7 = (v15 - (_BYTE *)Block) >> 1;
      if ( v7 >= 0x104 )
      {
        *String1 = 0;
        v6 = -2147024809;
        if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
        {
          v12 = -2147024809;
          v18 = &v12;
          v19 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, byte_180018453, 0, 0, 3, v17);
        }
        if ( Block != v16 )
          operator delete(Block);
        goto LABEL_36;
      }
      v8 = v7;
      memcpy_0(String1, Block, v8 * 2);
      String1[v8] = 0;
    }
    if ( Block != v16 )
      operator delete(Block);
    v6 = 0;
    goto LABEL_36;
  }
  if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, word_18001871A, 0, 0, 2, v17);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000531c  push    rbp
0x18000531e  push    rbx
0x18000531f  push    rdi
0x180005320  push    r14
0x180005322  lea     rbp, [rsp-3Fh]
0x180005327  sub     rsp, 0A8h
0x18000532e  mov     rax, cs:__security_cookie
0x180005335  xor     rax, rsp
0x180005338  mov     [rbp+57h+var_30], rax
0x18000533c  xor     r14d, r14d
0x18000533f  mov     rdi, rcx
0x180005342  test    rcx, rcx
0x180005345  jz      loc_1800055EC
0x18000534b  mov     [rcx], r14w
0x18000534f  mov     rdx, rcx
0x180005352  mov     ecx, 104h
0x180005357  call    cs:__imp_GetTempPath2W
0x18000535d  test    eax, eax
0x18000535f  jz      loc_180005517
0x180005365  cmp     [rdi], r14w
0x180005369  jz      loc_180005517
0x18000536f  mov     rcx, rdi; lpFileName
0x180005372  call    cs:__imp_GetFileAttributesW
0x180005378  cmp     eax, 0FFFFFFFFh
0x18000537b  jz      short loc_180005385
0x18000537d  test    al, 10h
0x18000537f  jnz     loc_180005409
0x180005385  xor     edx, edx; lpSecurityAttributes
0x180005387  mov     rcx, rdi; lpPathName
0x18000538a  call    cs:__imp_CreateDirectoryW
0x180005390  test    eax, eax
0x180005392  jnz     short loc_180005409
0x180005394  call    cs:__imp_GetLastError
0x18000539a  mov     ebx, eax
0x18000539c  test    eax, eax
0x18000539e  jle     short loc_1800053A9
0x1800053a0  movzx   ebx, ax
0x1800053a3  or      ebx, 80070000h
0x1800053a9  test    ebx, ebx
0x1800053ab  mov     eax, 80004005h
0x1800053b0  cmovns  ebx, eax
0x1800053b3  mov     eax, cs:dword_18001C008
0x1800053b9  cmp     eax, 2
0x1800053bc  jbe     short loc_180005400
0x1800053be  mov     rcx, cs:qword_18001C020
0x1800053c5  mov     rax, cs:qword_18001C018
0x1800053cc  test    al, 8
0x1800053ce  jz      short loc_180005400
0x1800053d0  mov     rax, rcx
0x1800053d3  and     eax, 8
0x1800053d6  cmp     rax, rcx
0x1800053d9  jnz     short loc_180005400
0x1800053db  lea     rax, [rbp+57h+var_90]
0x1800053df  mov     [rbp+57h+var_90], ebx
0x1800053e2  mov     [rsp+0C0h+var_98], rax
0x1800053e7  lea     rdx, byte_1800183BD
0x1800053ee  lea     rax, [rbp+57h+var_88]
0x1800053f2  mov     [rbp+57h+var_88], rdi
0x1800053f6  mov     [rsp+0C0h+var_A0], rax
0x1800053fb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180005400  mov     [rdi], r14w
0x180005404  jmp     loc_18000559B
0x180005409  lea     rax, [rbp+57h+var_70]
0x18000540d  mov     [rbp+57h+var_70], r14w
0x180005412  mov     [rbp+57h+Block], rax
0x180005416  lea     rdx, [rbp+57h+Block]
0x18000541a  lea     rax, [rbp+57h+var_70]
0x18000541e  mov     rcx, rdi; String1
0x180005421  mov     [rbp+57h+var_78], rax
0x180005425  call    ?UtilGetFinalPath@@YAHPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; UtilGetFinalPath(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000542a  test    eax, eax
0x18000542c  jz      loc_1800054F5
0x180005432  mov     rbx, [rbp+57h+var_78]
0x180005436  sub     rbx, [rbp+57h+Block]
0x18000543a  sar     rbx, 1
0x18000543d  cmp     rbx, 104h
0x180005444  jb      loc_1800054DE
0x18000544a  mov     [rdi], r14w
0x18000544e  mov     ebx, 80070057h
0x180005453  mov     eax, cs:dword_18001C008
0x180005459  cmp     eax, 2
0x18000545c  jbe     short loc_1800054BC
0x18000545e  mov     rcx, cs:qword_18001C020
0x180005465  mov     rax, cs:qword_18001C018
0x18000546c  test    al, 8
0x18000546e  jz      short loc_1800054BC
0x180005470  mov     rax, rcx
0x180005473  and     eax, 8
0x180005476  cmp     rax, rcx
0x180005479  jnz     short loc_1800054BC
0x18000547b  lea     rax, [rbp+57h+var_90]
0x18000547f  mov     [rbp+57h+var_90], 80070057h
0x180005486  mov     [rbp+57h+var_40], rax
0x18000548a  lea     rdx, byte_180018453
0x180005491  lea     rax, [rbp+57h+var_60]
0x180005495  mov     [rbp+57h+var_38], 4
0x18000549d  mov     [rsp+0C0h+var_98], rax
0x1800054a2  lea     rcx, dword_18001C008
0x1800054a9  xor     r9d, r9d
0x1800054ac  mov     dword ptr [rsp+0C0h+var_A0], 3
0x1800054b4  xor     r8d, r8d
0x1800054b7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800054bc  mov     rcx, [rbp+57h+Block]; Block
0x1800054c0  lea     rax, [rbp+57h+var_70]
0x1800054c4  cmp     rcx, rax
0x1800054c7  jz      loc_18000559B
0x1800054cd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800054d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800054d9  jmp     loc_18000559B
0x1800054de  mov     rdx, [rbp+57h+Block]; Src
0x1800054e2  add     rbx, rbx
0x1800054e5  mov     r8, rbx; Size
0x1800054e8  mov     rcx, rdi; void *
0x1800054eb  call    memcpy_0
0x1800054f0  mov     [rbx+rdi], r14w
0x1800054f5  lea     rax, [rbp+57h+var_70]
0x1800054f9  cmp     [rbp+57h+Block], rax
0x1800054fd  jz      short loc_18000550F
0x1800054ff  mov     rcx, [rbp+57h+Block]; Block
0x180005503  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000550a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000550f  mov     ebx, r14d
0x180005512  jmp     loc_18000559B
0x180005517  call    cs:__imp_GetLastError
0x18000551d  mov     ebx, eax
0x18000551f  test    eax, eax
0x180005521  jle     short loc_18000552C
0x180005523  movzx   ebx, ax
0x180005526  or      ebx, 80070000h
0x18000552c  test    ebx, ebx
0x18000552e  mov     eax, 80004005h
0x180005533  cmovns  ebx, eax
0x180005536  mov     eax, cs:dword_18001C008
0x18000553c  cmp     eax, 2
0x18000553f  jbe     short loc_18000559B
0x180005541  mov     rcx, cs:qword_18001C020
0x180005548  mov     rax, cs:qword_18001C018
0x18000554f  test    al, 8
0x180005551  jz      short loc_18000559B
0x180005553  mov     rax, rcx
0x180005556  and     eax, 8
0x180005559  cmp     rax, rcx
0x18000555c  jnz     short loc_18000559B
0x18000555e  lea     rax, [rbp+57h+var_90]
0x180005562  mov     [rbp+57h+var_90], ebx
0x180005565  mov     [rbp+57h+var_40], rax
0x180005569  lea     rdx, unk_180018580
0x180005570  lea     rax, [rbp+57h+var_60]
0x180005574  mov     [rbp+57h+var_38], 4
0x18000557c  mov     [rsp+0C0h+var_98], rax
0x180005581  lea     rcx, dword_18001C008
0x180005588  xor     r9d, r9d
0x18000558b  mov     dword ptr [rsp+0C0h+var_A0], 3
0x180005593  xor     r8d, r8d
0x180005596  call    _tlgWriteTransfer_EventWriteTransfer
0x18000559b  mov     eax, cs:dword_18001C008
0x1800055a1  cmp     eax, 2
0x1800055a4  jbe     short loc_1800055E8
0x1800055a6  mov     rdx, cs:qword_18001C020
0x1800055ad  mov     rax, cs:qword_18001C018
0x1800055b4  test    al, 8
0x1800055b6  jz      short loc_1800055E8
0x1800055b8  mov     rcx, rdx
0x1800055bb  and     ecx, 8
0x1800055be  cmp     rcx, rdx
0x1800055c1  jnz     short loc_1800055E8
0x1800055c3  lea     rax, [rbp+57h+var_90]
0x1800055c7  mov     [rbp+57h+var_90], ebx
0x1800055ca  mov     [rsp+0C0h+var_98], rax
0x1800055cf  lea     rdx, dword_1800189DC
0x1800055d6  lea     rax, [rbp+57h+var_88]
0x1800055da  mov     [rbp+57h+var_88], rdi
0x1800055de  mov     [rsp+0C0h+var_A0], rax
0x1800055e3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800055e8  mov     eax, ebx
0x1800055ea  jmp     short loc_180005643
0x1800055ec  mov     eax, cs:dword_18001C008
0x1800055f2  cmp     eax, 2
0x1800055f5  jbe     short loc_18000563E
0x1800055f7  mov     rcx, cs:qword_18001C020
0x1800055fe  mov     rax, cs:qword_18001C018
0x180005605  test    al, 8
0x180005607  jz      short loc_18000563E
0x180005609  mov     rax, rcx
0x18000560c  and     eax, 8
0x18000560f  cmp     rax, rcx
0x180005612  jnz     short loc_18000563E
0x180005614  lea     rax, [rbp+57h+var_60]
0x180005618  xor     r9d, r9d
0x18000561b  mov     [rsp+0C0h+var_98], rax
0x180005620  lea     rdx, word_18001871A
0x180005627  xor     r8d, r8d
0x18000562a  mov     dword ptr [rsp+0C0h+var_A0], 2
0x180005632  lea     rcx, dword_18001C008
0x180005639  call    _tlgWriteTransfer_EventWriteTransfer
0x18000563e  mov     eax, 80070057h
0x180005643  mov     rcx, [rbp+57h+var_30]
0x180005647  xor     rcx, rsp; StackCookie
0x18000564a  call    __security_check_cookie
0x18000564f  add     rsp, 0A8h
0x180005656  pop     r14
0x180005658  pop     rdi
0x180005659  pop     rbx
0x18000565a  pop     rbp
0x18000565b  retn
```
