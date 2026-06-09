# CSpObjectToken::GenerateFileName(ushort const *,ushort const *,CSpDynamicString &)

- ea: `0x1800eed80`
- end: `0x1800ef084`
- name: `?GenerateFileName@CSpObjectToken@@AEAAJPEBG0AEAVCSpDynamicString@@@Z`
- size: `772`
- prototype: `int(CSpObjectToken *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct CSpDynamicString *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800eea28`

## callees

- `0x18000a590`
- `0x18000cdb0`
- `0x180011cb0`
- `0x1800123c0`
- `0x180015560`
- `0x180016a10`
- `0x1800190c0`
- `0x180019a50`
- `0x180045938`
- `0x180079e30`
- `0x1800eed80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalnum` at `0x1800eef79`
- `api-ms-win-crt-private-l1-1-0!_o_iswalnum` at `0x1800eef79`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800eedd9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800eeeaf`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800eedd9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800eeeaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eee30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef01a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eee30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef01a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800eef32`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800eef32`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800eef1a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800eef1a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800eee21`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ef00b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800eee21`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ef00b`

## pseudocode

```c
__int64 __fastcall CSpObjectToken::GenerateFileName(
        CSpObjectToken *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct CSpDynamicString *a4)
{
  __int64 v7; // rax
  HRESULT appended; // ebx
  HANDLE v9; // rax
  __int64 v10; // rax
  int v11; // edx
  wchar_t *v12; // rsi
  HRESULT v13; // eax
  unsigned int v14; // eax
  unsigned __int16 *v15; // rbx
  LPOLESTR v16; // rdi
  unsigned __int16 *v17; // rsi
  int v18; // eax
  HANDLE FileW; // rax
  LPCWSTR lpFileName; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR v22; // [rsp+48h] [rbp-38h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v24; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int16 *v25; // [rsp+60h] [rbp-20h] BYREF
  GUID pguid; // [rsp+68h] [rbp-18h] BYREF

  if ( !a3 )
    goto LABEL_13;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  if ( !v7 || wcsstr(a3, L"%d") )
  {
LABEL_13:
    lpFileName = 0;
    v24 = 0;
    if ( !a3 )
      goto LABEL_25;
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    if ( !v10 )
      goto LABEL_25;
    if ( v10 != 2 )
      goto LABEL_22;
    v11 = *a3 - 37;
    if ( *a3 == 37 )
    {
      v11 = a3[1] - 100;
      if ( a3[1] == 100 )
        v11 = a3[2];
    }
    if ( v11 )
    {
LABEL_22:
      v12 = wcsstr(a3, L"%d");
      appended = CSpDynamicString::AppendHR((CSpDynamicString *)&lpFileName, a3, v12 - a3);
      if ( appended < 0 )
        goto LABEL_46;
      appended = CSpDynamicString::AppendHR((CSpDynamicString *)&v24, v12 + 2);
      if ( appended < 0 )
        goto LABEL_46;
    }
    else
    {
LABEL_25:
      CSpDynamicString::operator=(&lpFileName, L"SP_");
      CSpDynamicString::operator=(&v24, L".dat");
    }
    pguid = 0;
    v13 = CoCreateGuid(&pguid);
    lpsz = 0;
    appended = v13;
    if ( v13 >= 0 )
      appended = StringFromCLSID(&pguid, &lpsz);
    v25 = 0;
    if ( appended >= 0 )
    {
      v14 = CSpDynamicString::Length((CSpDynamicString *)&lpsz);
      CSpDynamicString::ClearAndGrowTo((CSpDynamicString *)&v25, v14);
      v15 = v25;
      if ( v25 )
      {
        v16 = lpsz;
        v17 = v25;
        while ( *v16 )
        {
          if ( iswalnum(*v16) )
            *v17++ = *v16;
          ++v16;
        }
        *v17 = 0;
        CSpDynamicString::operator=(a4, &lpFileName);
        if ( *(_QWORD *)a4 )
        {
          v18 = CSpDynamicString::Append2HR(a4, v15, v24);
          v22 = 0;
          appended = v18;
          if ( v18 >= 0 )
          {
            appended = CSpDynamicString::Append2HR((CSpDynamicString *)&v22, a2, *(const unsigned __int16 **)a4);
            if ( appended >= 0 )
            {
              FileW = CreateFileW(v22, 0x40000000u, 0, 0, 1u, 0x80u, 0);
              if ( FileW == (HANDLE)-1LL || !CloseHandle(FileW) )
                appended = SpHrFromLastWin32Error();
            }
          }
        }
        else
        {
          appended = -2147024882;
          v22 = 0;
        }
        SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v22);
        if ( appended >= 0 )
          goto LABEL_45;
      }
      else
      {
        appended = -2147024882;
      }
    }
    SPPIPEINFO::~SPPIPEINFO(a4);
LABEL_45:
    SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v25);
    SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpsz);
LABEL_46:
    SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v24);
    goto LABEL_47;
  }
  lpFileName = 0;
  appended = CSpDynamicString::Append2HR((CSpDynamicString *)&lpFileName, a2, a3);
  if ( appended >= 0 )
  {
    v9 = CreateFileW(lpFileName, 0x40000000u, 0, 0, 1u, 0x80u, 0);
    if ( v9 != (HANDLE)-1LL && !CloseHandle(v9) )
      appended = SpHrFromLastWin32Error();
  }
  CSpDynamicString::operator=(a4, a3);
  if ( !*(_QWORD *)a4 )
    appended = -2147024882;
LABEL_47:
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpFileName);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800eed80  push    rbp
0x1800eed82  push    rbx
0x1800eed83  push    rsi
0x1800eed84  push    rdi
0x1800eed85  push    r12
0x1800eed87  push    r14
0x1800eed89  push    r15
0x1800eed8b  mov     rbp, rsp
0x1800eed8e  sub     rsp, 80h
0x1800eed95  mov     rax, cs:__security_cookie
0x1800eed9c  xor     rax, rsp
0x1800eed9f  mov     [rbp+var_8], rax
0x1800eeda3  xor     r12d, r12d
0x1800eeda6  mov     r14, r9
0x1800eeda9  mov     rdi, r8
0x1800eedac  mov     r15, rdx
0x1800eedaf  test    r8, r8
0x1800eedb2  jz      loc_1800EEE5C
0x1800eedb8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800eedbc  inc     rax
0x1800eedbf  cmp     [r8+rax*2], r12w
0x1800eedc4  jnz     short loc_1800EEDBC
0x1800eedc6  test    rax, rax
0x1800eedc9  jz      loc_1800EEE5C
0x1800eedcf  lea     rdx, aD; "%d"
0x1800eedd6  mov     rcx, rdi; Str
0x1800eedd9  call    cs:__imp_wcsstr
0x1800eeddf  test    rax, rax
0x1800eede2  jnz     short loc_1800EEE5C
0x1800eede4  mov     r8, rdi; unsigned __int16 *
0x1800eede7  mov     [rbp+lpFileName], r12
0x1800eedeb  mov     rdx, r15; unsigned __int16 *
0x1800eedee  lea     rcx, [rbp+lpFileName]; this
0x1800eedf2  call    ?Append2HR@CSpDynamicString@@QEAAJPEBG0@Z; CSpDynamicString::Append2HR(ushort const *,ushort const *)
0x1800eedf7  mov     ebx, eax
0x1800eedf9  test    eax, eax
0x1800eedfb  js      short loc_1800EEE41
0x1800eedfd  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800eee01  xor     r9d, r9d; lpSecurityAttributes
0x1800eee04  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x1800eee09  xor     r8d, r8d; dwShareMode
0x1800eee0c  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800eee14  mov     edx, 40000000h; dwDesiredAccess
0x1800eee19  mov     [rsp+80h+dwCreationDisposition], 1; dwCreationDisposition
0x1800eee21  call    cs:__imp_CreateFileW
0x1800eee27  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800eee2b  jz      short loc_1800EEE41
0x1800eee2d  mov     rcx, rax; hObject
0x1800eee30  call    cs:__imp_CloseHandle
0x1800eee36  test    eax, eax
0x1800eee38  jnz     short loc_1800EEE41
0x1800eee3a  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800eee3f  mov     ebx, eax
0x1800eee41  mov     rdx, rdi
0x1800eee44  mov     rcx, r14
0x1800eee47  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x1800eee4c  cmp     [r14], r12
0x1800eee4f  mov     eax, 8007000Eh
0x1800eee54  cmovz   ebx, eax
0x1800eee57  jmp     loc_1800EF05B
0x1800eee5c  mov     [rbp+lpFileName], r12
0x1800eee60  mov     [rbp+var_28], r12
0x1800eee64  test    rdi, rdi
0x1800eee67  jz      loc_1800EEEEF
0x1800eee6d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800eee71  inc     rax
0x1800eee74  cmp     [rdi+rax*2], r12w
0x1800eee79  jnz     short loc_1800EEE71
0x1800eee7b  test    rax, rax
0x1800eee7e  jz      short loc_1800EEEEF
0x1800eee80  cmp     rax, 2
0x1800eee84  jnz     short loc_1800EEEA5
0x1800eee86  movzx   edx, word ptr [rdi]
0x1800eee89  sub     edx, 25h ; '%'
0x1800eee8c  jnz     short loc_1800EEEA1
0x1800eee8e  movzx   edx, word ptr [rdi+2]
0x1800eee92  sub     edx, 64h ; 'd'
0x1800eee95  jnz     short loc_1800EEEA1
0x1800eee97  movzx   edx, word ptr [rdi+4]
0x1800eee9b  movzx   ecx, r12w
0x1800eee9f  sub     edx, ecx
0x1800eeea1  test    edx, edx
0x1800eeea3  jz      short loc_1800EEEEF
0x1800eeea5  lea     rdx, aD; "%d"
0x1800eeeac  mov     rcx, rdi; Str
0x1800eeeaf  call    cs:__imp_wcsstr
0x1800eeeb5  mov     rdx, rdi; unsigned __int16 *
0x1800eeeb8  lea     rcx, [rbp+lpFileName]; this
0x1800eeebc  mov     r8, rax
0x1800eeebf  mov     rsi, rax
0x1800eeec2  sub     r8, rdi
0x1800eeec5  sar     r8, 1; unsigned int
0x1800eeec8  call    ?AppendHR@CSpDynamicString@@QEAAJPEBGK@Z; CSpDynamicString::AppendHR(ushort const *,ulong)
0x1800eeecd  mov     ebx, eax
0x1800eeecf  test    eax, eax
0x1800eeed1  js      loc_1800EF052
0x1800eeed7  lea     rdx, [rsi+4]; Src
0x1800eeedb  lea     rcx, [rbp+var_28]; this
0x1800eeedf  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x1800eeee4  mov     ebx, eax
0x1800eeee6  test    eax, eax
0x1800eeee8  jns     short loc_1800EEF0F
0x1800eeeea  jmp     loc_1800EF052
0x1800eeeef  lea     rdx, aSp; "SP_"
0x1800eeef6  lea     rcx, [rbp+lpFileName]
0x1800eeefa  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x1800eeeff  lea     rdx, aDat; ".dat"
0x1800eef06  lea     rcx, [rbp+var_28]
0x1800eef0a  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x1800eef0f  xorps   xmm0, xmm0
0x1800eef12  lea     rcx, [rbp+pguid]; pguid
0x1800eef16  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x1800eef1a  call    cs:__imp_CoCreateGuid
0x1800eef20  mov     [rbp+lpsz], r12
0x1800eef24  mov     ebx, eax
0x1800eef26  test    eax, eax
0x1800eef28  js      short loc_1800EEF3A
0x1800eef2a  lea     rdx, [rbp+lpsz]; lplpsz
0x1800eef2e  lea     rcx, [rbp+pguid]; rclsid
0x1800eef32  call    cs:__imp_StringFromCLSID
0x1800eef38  mov     ebx, eax
0x1800eef3a  mov     [rbp+var_20], r12
0x1800eef3e  test    ebx, ebx
0x1800eef40  js      loc_1800EF038
0x1800eef46  lea     rcx, [rbp+lpsz]; this
0x1800eef4a  call    ?Length@CSpDynamicString@@QEBAIXZ; CSpDynamicString::Length(void)
0x1800eef4f  mov     edx, eax; unsigned int
0x1800eef51  lea     rcx, [rbp+var_20]; this
0x1800eef55  call    ?ClearAndGrowTo@CSpDynamicString@@QEAAPEAGK@Z; CSpDynamicString::ClearAndGrowTo(ulong)
0x1800eef5a  mov     rbx, [rbp+var_20]
0x1800eef5e  test    rbx, rbx
0x1800eef61  jnz     short loc_1800EEF6D
0x1800eef63  mov     ebx, 8007000Eh
0x1800eef68  jmp     loc_1800EF038
0x1800eef6d  mov     rdi, [rbp+lpsz]
0x1800eef71  mov     rsi, rbx
0x1800eef74  jmp     short loc_1800EEF91
0x1800eef76  movzx   ecx, ax; C
0x1800eef79  call    cs:__imp_iswalnum
0x1800eef7f  test    eax, eax
0x1800eef81  jz      short loc_1800EEF8D
0x1800eef83  movzx   eax, word ptr [rdi]
0x1800eef86  mov     [rsi], ax
0x1800eef89  add     rsi, 2
0x1800eef8d  add     rdi, 2
0x1800eef91  movzx   eax, word ptr [rdi]
0x1800eef94  test    ax, ax
0x1800eef97  jnz     short loc_1800EEF76
0x1800eef99  lea     rdx, [rbp+lpFileName]
0x1800eef9d  mov     [rsi], r12w
0x1800eefa1  mov     rcx, r14
0x1800eefa4  call    ??4CSpDynamicString@@QEAAPEAGAEBV0@@Z; CSpDynamicString::operator=(CSpDynamicString const &)
0x1800eefa9  cmp     [r14], r12
0x1800eefac  jnz     short loc_1800EEFB9
0x1800eefae  mov     ebx, 8007000Eh
0x1800eefb3  mov     [rbp+var_38], r12
0x1800eefb7  jmp     short loc_1800EF02B
0x1800eefb9  mov     r8, [rbp+var_28]; unsigned __int16 *
0x1800eefbd  mov     rdx, rbx; unsigned __int16 *
0x1800eefc0  mov     rcx, r14; this
0x1800eefc3  call    ?Append2HR@CSpDynamicString@@QEAAJPEBG0@Z; CSpDynamicString::Append2HR(ushort const *,ushort const *)
0x1800eefc8  mov     [rbp+var_38], r12
0x1800eefcc  mov     ebx, eax
0x1800eefce  test    eax, eax
0x1800eefd0  js      short loc_1800EF02B
0x1800eefd2  mov     r8, [r14]; unsigned __int16 *
0x1800eefd5  lea     rcx, [rbp+var_38]; this
0x1800eefd9  mov     rdx, r15; unsigned __int16 *
0x1800eefdc  call    ?Append2HR@CSpDynamicString@@QEAAJPEBG0@Z; CSpDynamicString::Append2HR(ushort const *,ushort const *)
0x1800eefe1  mov     ebx, eax
0x1800eefe3  test    eax, eax
0x1800eefe5  js      short loc_1800EF02B
0x1800eefe7  mov     rcx, [rbp+var_38]; lpFileName
0x1800eefeb  xor     r9d, r9d; lpSecurityAttributes
0x1800eefee  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x1800eeff3  xor     r8d, r8d; dwShareMode
0x1800eeff6  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800eeffe  mov     edx, 40000000h; dwDesiredAccess
0x1800ef003  mov     [rsp+80h+dwCreationDisposition], 1; dwCreationDisposition
0x1800ef00b  call    cs:__imp_CreateFileW
0x1800ef011  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ef015  jz      short loc_1800EF024
0x1800ef017  mov     rcx, rax; hObject
0x1800ef01a  call    cs:__imp_CloseHandle
0x1800ef020  test    eax, eax
0x1800ef022  jnz     short loc_1800EF02B
0x1800ef024  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800ef029  mov     ebx, eax
0x1800ef02b  lea     rcx, [rbp+var_38]; this
0x1800ef02f  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ef034  test    ebx, ebx
0x1800ef036  jns     short loc_1800EF040
0x1800ef038  mov     rcx, r14; this
0x1800ef03b  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ef040  lea     rcx, [rbp+var_20]; this
0x1800ef044  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ef049  lea     rcx, [rbp+lpsz]; this
0x1800ef04d  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ef052  lea     rcx, [rbp+var_28]; this
0x1800ef056  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ef05b  lea     rcx, [rbp+lpFileName]; this
0x1800ef05f  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ef064  mov     eax, ebx
0x1800ef066  mov     rcx, [rbp+var_8]
0x1800ef06a  xor     rcx, rsp; StackCookie
0x1800ef06d  call    __security_check_cookie
0x1800ef072  add     rsp, 80h
0x1800ef079  pop     r15
0x1800ef07b  pop     r14
0x1800ef07d  pop     r12
0x1800ef07f  pop     rdi
0x1800ef080  pop     rsi
0x1800ef081  pop     rbx
0x1800ef082  pop     rbp
0x1800ef083  retn
```
