# ExeTask::SetRealTarget(void)

- ea: `0x18002ff98`
- end: `0x1800301e7`
- name: `?SetRealTarget@ExeTask@@IEAAJXZ`
- size: `591`
- prototype: `__int64 __fastcall(ExeTask *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002fc90`

## callees

- `0x18002ff98`
- `0x180030620`
- `0x18004d340`
- `0x180057e84`
- `0x1800621f4`
- `0x1800622a4`
- `0x180082a40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180030156`
- `msvcrt!_wcsicmp` at `0x180030156`
- `msvcrt!wcsrchr` at `0x18002ffe2`
- `msvcrt!wcsrchr` at `0x18003011a`
- `msvcrt!wcsrchr` at `0x18002ffe2`
- `msvcrt!wcsrchr` at `0x18003011a`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800300a1`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800300e1`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800300a1`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800300e1`

## pseudocode

```c
__int64 __fastcall ExeTask::SetRealTarget(ExeTask *this)
{
  const wchar_t ***v1; // rbx
  const wchar_t **v2; // rax
  const wchar_t *v4; // rcx
  wchar_t *v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 result; // rax
  unsigned int i; // ebp
  const WCHAR *v10; // rdx
  const WCHAR **v11; // rax
  const WCHAR *v12; // rcx
  const WCHAR *v13; // rdx
  const wchar_t *v14; // rcx
  wchar_t *v15; // rax
  LPWSTR v16; // rbx
  LPWSTR FilePart[2]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-248h] BYREF

  v1 = (const wchar_t ***)((char *)this + 48);
  v2 = (const wchar_t **)*((_QWORD *)this + 6);
  if ( v2 )
    v4 = *v2;
  else
    v4 = 0;
  v5 = wcsrchr(v4, 0x2Eu);
  v6 = -1;
  *((_DWORD *)this + 10) = 0;
  if ( v5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v5[v7] );
    if ( v7 == 1 )
      return 1;
  }
  else
  {
    FilePart[0] = 0;
    for ( i = 0; i < ExtsFound; ++i )
    {
      if ( *v1 )
        v10 = **v1;
      else
        v10 = 0;
      v11 = (const WCHAR **)*((_QWORD *)this + 8);
      if ( v11 )
        v12 = *v11;
      else
        v12 = 0;
      if ( !SearchPathW(v12, v10, (LPCWSTR)(&PathExts)[i], 0x105u, Buffer, FilePart) )
      {
        v13 = *v1 ? **v1 : 0LL;
        if ( !SearchPathW(0, v13, (LPCWSTR)(&PathExts)[i], 0x105u, Buffer, FilePart) )
          continue;
      }
      _bstr_t::operator=(v1, Buffer);
      break;
    }
  }
  if ( *v1 )
    v14 = **v1;
  else
    v14 = 0;
  v15 = wcsrchr(v14, 0x2Eu);
  FilePart[0] = v15;
  v16 = v15;
  if ( !v15 )
    return 1;
  do
    ++v6;
  while ( v15[v6] );
  if ( v6 == 1 )
    return 1;
  if ( _wcsicmp(v15 + 1, L"LNK") )
    goto LABEL_35;
  result = ExeTask::ResolveLink(this, FilePart);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result == 1 )
      return 0;
    v16 = FilePart[0];
LABEL_35:
    if ( !IsOnList(v16 + 1, (const unsigned __int16 **)&off_1800C0008, 2) )
    {
      if ( IsOnList(v16 + 1, (const unsigned __int16 **)&off_1800C0340, 3) )
      {
        if ( (int)ExeTask::SetBatchLaunchCommand(this) >= 0 )
          *((_DWORD *)this + 10) = 1;
      }
      else if ( (int)ExeTask::ResolveDocRunAssociation(this, v16) >= 0 )
      {
        *((_DWORD *)this + 10) = 2;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002ff98  mov     [rsp+arg_8], rbx
0x18002ff9d  mov     [rsp+arg_10], rbp
0x18002ffa2  push    rsi
0x18002ffa3  push    rdi
0x18002ffa4  push    r12
0x18002ffa6  push    r14
0x18002ffa8  push    r15
0x18002ffaa  sub     rsp, 260h
0x18002ffb1  mov     rax, cs:__security_cookie
0x18002ffb8  xor     rax, rsp
0x18002ffbb  mov     [rsp+288h+var_38], rax
0x18002ffc3  lea     rbx, [rcx+30h]
0x18002ffc7  xor     r15d, r15d
0x18002ffca  mov     rax, [rbx]
0x18002ffcd  mov     rdi, rcx
0x18002ffd0  test    rax, rax
0x18002ffd3  jz      short loc_18002FFDA
0x18002ffd5  mov     rcx, [rax]
0x18002ffd8  jmp     short loc_18002FFDD
0x18002ffda  mov     rcx, r15; Str
0x18002ffdd  mov     edx, 2Eh ; '.'; Ch
0x18002ffe2  call    cs:__imp_wcsrchr
0x18002ffe9  nop     dword ptr [rax+rax+00h]
0x18002ffee  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002fff2  mov     [rdi+28h], r15d
0x18002fff6  test    rax, rax
0x18002fff9  jz      short loc_180030044
0x18002fffb  mov     rcx, rsi
0x18002fffe  inc     rcx
0x180030001  cmp     [rax+rcx*2], r15w
0x180030006  jnz     short loc_18002FFFE
0x180030008  cmp     rcx, 1
0x18003000c  jnz     loc_180030105
0x180030012  mov     eax, 1
0x180030017  mov     rcx, [rsp+288h+var_38]
0x18003001f  xor     rcx, rsp; StackCookie
0x180030022  call    __security_check_cookie
0x180030027  lea     r11, [rsp+288h+var_28]
0x18003002f  mov     rbx, [r11+38h]
0x180030033  mov     rbp, [r11+40h]
0x180030037  mov     rsp, r11
0x18003003a  pop     r15
0x18003003c  pop     r14
0x18003003e  pop     r12
0x180030040  pop     rdi
0x180030041  pop     rsi
0x180030042  retn
0x180030044  mov     [rsp+288h+FilePart], r15
0x180030049  mov     ebp, r15d
0x18003004c  cmp     ebp, cs:?ExtsFound@@3KA; ulong ExtsFound
0x180030052  jnb     loc_180030105
0x180030058  mov     rax, [rbx]
0x18003005b  lea     r12, ?PathExts@@3PAPEAGA; ushort * near * PathExts
0x180030062  mov     r14d, ebp
0x180030065  test    rax, rax
0x180030068  jz      short loc_18003006F
0x18003006a  mov     rdx, [rax]
0x18003006d  jmp     short loc_180030072
0x18003006f  mov     rdx, r15; lpFileName
0x180030072  mov     rax, [rdi+40h]
0x180030076  test    rax, rax
0x180030079  jz      short loc_180030080
0x18003007b  mov     rcx, [rax]
0x18003007e  jmp     short loc_180030083
0x180030080  mov     rcx, r15; lpPath
0x180030083  mov     r8, [r12+r14*8]; lpExtension
0x180030087  lea     rax, [rsp+288h+FilePart]
0x18003008c  mov     [rsp+288h+lpFilePart], rax; lpFilePart
0x180030091  mov     r9d, 105h; nBufferLength
0x180030097  lea     rax, [rsp+288h+Buffer]
0x18003009c  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x1800300a1  call    cs:__imp_SearchPathW
0x1800300a8  nop     dword ptr [rax+rax+00h]
0x1800300ad  test    eax, eax
0x1800300af  jnz     short loc_1800300F8
0x1800300b1  mov     rax, [rbx]
0x1800300b4  test    rax, rax
0x1800300b7  jz      short loc_1800300BE
0x1800300b9  mov     rdx, [rax]
0x1800300bc  jmp     short loc_1800300C1
0x1800300be  mov     rdx, r15; lpFileName
0x1800300c1  mov     r8, [r12+r14*8]; lpExtension
0x1800300c5  lea     rax, [rsp+288h+FilePart]
0x1800300ca  mov     [rsp+288h+lpFilePart], rax; lpFilePart
0x1800300cf  mov     r9d, 105h; nBufferLength
0x1800300d5  lea     rax, [rsp+288h+Buffer]
0x1800300da  xor     ecx, ecx; lpPath
0x1800300dc  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x1800300e1  call    cs:__imp_SearchPathW
0x1800300e8  nop     dword ptr [rax+rax+00h]
0x1800300ed  test    eax, eax
0x1800300ef  jnz     short loc_1800300F8
0x1800300f1  inc     ebp
0x1800300f3  jmp     loc_18003004C
0x1800300f8  lea     rdx, [rsp+288h+Buffer]
0x1800300fd  mov     rcx, rbx
0x180030100  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180030105  mov     rax, [rbx]
0x180030108  test    rax, rax
0x18003010b  jz      short loc_180030112
0x18003010d  mov     rcx, [rax]
0x180030110  jmp     short loc_180030115
0x180030112  mov     rcx, r15; Str
0x180030115  mov     edx, 2Eh ; '.'; Ch
0x18003011a  call    cs:__imp_wcsrchr
0x180030121  nop     dword ptr [rax+rax+00h]
0x180030126  mov     [rsp+288h+FilePart], rax
0x18003012b  mov     rbx, rax
0x18003012e  test    rax, rax
0x180030131  jz      loc_180030012
0x180030137  inc     rsi
0x18003013a  cmp     [rax+rsi*2], r15w
0x18003013f  jnz     short loc_180030137
0x180030141  cmp     rsi, 1
0x180030145  jz      loc_180030012
0x18003014b  lea     rcx, [rax+2]; String1
0x18003014f  lea     rdx, aLnk; "LNK"
0x180030156  call    cs:__imp__wcsicmp
0x18003015d  nop     dword ptr [rax+rax+00h]
0x180030162  test    eax, eax
0x180030164  jnz     short loc_180030185
0x180030166  lea     rdx, [rsp+288h+FilePart]; unsigned __int16 **
0x18003016b  mov     rcx, rdi; this
0x18003016e  call    ?ResolveLink@ExeTask@@IEAAJAEAPEAG@Z; ExeTask::ResolveLink(ushort * &)
0x180030173  test    eax, eax
0x180030175  js      loc_180030017
0x18003017b  cmp     eax, 1
0x18003017e  jz      short loc_1800301E0
0x180030180  mov     rbx, [rsp+288h+FilePart]
0x180030185  mov     ebp, 2
0x18003018a  lea     rdx, off_1800C0008; unsigned __int16 **
0x180030191  mov     r8d, ebp; int
0x180030194  lea     rcx, [rbx+2]; String2
0x180030198  call    ?IsOnList@@YA_NPEBGPEAPEBGH@Z; IsOnList(ushort const *,ushort const * *,int)
0x18003019d  test    al, al
0x18003019f  jnz     short loc_1800301E0
0x1800301a1  lea     r8d, [rbp+1]; int
0x1800301a5  lea     rdx, off_1800C0340; unsigned __int16 **
0x1800301ac  lea     rcx, [rbx+2]; String2
0x1800301b0  call    ?IsOnList@@YA_NPEBGPEAPEBGH@Z; IsOnList(ushort const *,ushort const * *,int)
0x1800301b5  test    al, al
0x1800301b7  jz      short loc_1800301CE
0x1800301b9  mov     rcx, rdi; this
0x1800301bc  call    ?SetBatchLaunchCommand@ExeTask@@IEAAJXZ; ExeTask::SetBatchLaunchCommand(void)
0x1800301c1  test    eax, eax
0x1800301c3  js      short loc_1800301E0
0x1800301c5  mov     dword ptr [rdi+28h], 1
0x1800301cc  jmp     short loc_1800301E0
0x1800301ce  mov     rdx, rbx; pszAssoc
0x1800301d1  mov     rcx, rdi; this
0x1800301d4  call    ?ResolveDocRunAssociation@ExeTask@@IEAAJPEBG@Z; ExeTask::ResolveDocRunAssociation(ushort const *)
0x1800301d9  test    eax, eax
0x1800301db  js      short loc_1800301E0
0x1800301dd  mov     [rdi+28h], ebp
0x1800301e0  xor     eax, eax
0x1800301e2  jmp     loc_180030017
```
