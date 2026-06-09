# LOG_WRITER::ExpandDirPathAndCreateLowestDirectory(void)

- ea: `0x180004878`
- end: `0x180004b21`
- name: `?ExpandDirPathAndCreateLowestDirectory@LOG_WRITER@@AEAAJXZ`
- size: `681`
- prototype: `__int64 __fastcall(LOG_WRITER *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005458`

## callees

- `0x180002b14`
- `0x180003078`
- `0x1800031d0`
- `0x180004878`
- `0x180005880`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `msvcrt!wcsstr` at `0x180004963`
- `msvcrt!wcsstr` at `0x180004977`
- `msvcrt!wcsstr` at `0x180004963`
- `msvcrt!wcsstr` at `0x180004977`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800049ec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800049f8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004aad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004ab9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004aee`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004afa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800049ec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800049f8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004aad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004ab9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004aee`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004afa`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800048cf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800048f6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800048cf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800048f6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004997`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004a17`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004997`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004a17`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800049b4`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800049b4`
- `iisutil!?ExpandEnvironmentVariables@STRU@@SAJPEBGPEAV1@@Z` at `0x18000492a`
- `iisutil!?ExpandEnvironmentVariables@STRU@@SAJPEBGPEAV1@@Z` at `0x18000492a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800049a6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800049a6`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180004a73`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180004a73`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180004a87`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180004a87`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::ExpandDirPathAndCreateLowestDirectory(LOG_WRITER *this)
{
  int appended; // ebx
  const wchar_t **v3; // rsi
  __int64 v4; // rcx
  struct _SECURITY_ATTRIBUTES *v5; // rdx
  int v6; // r14d
  _WORD *v7; // rax
  wchar_t *v8; // rbx
  wchar_t *v9; // rax
  __int64 v10; // rbx
  int DirectoryRecursively; // eax
  LOG_WRITER *v12; // rcx
  _BYTE v14[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[56]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v16[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v17; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v18[32]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v19[256]; // [rsp+110h] [rbp+10h] BYREF

  appended = 0;
  v3 = (const wchar_t **)((char *)this + 72);
  if ( *((_DWORD *)this + 30) )
    return (unsigned int)appended;
  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v15, v18, 0x20u);
  memset_0(v19, 0, sizeof(v19));
  STRU::STRU((STRU *)v14, v19, 0x100u);
  *(_OWORD *)v16 = 0;
  v17 = 0;
  v4 = *((_QWORD *)this + 1);
  if ( !*(_DWORD *)(v4 + 152) )
  {
    appended = -2147024809;
LABEL_23:
    STRU::~STRU((STRU *)v14);
    STRU::~STRU((STRU *)v15);
LABEL_24:
    LOG_WRITER::LogW3LogSvcEvent(this, 3221231474LL, *((_QWORD *)this + 13), (unsigned int)appended, 1);
    **((_WORD **)this + 13) = 0;
    *((_DWORD *)this + 30) = 0;
    return (unsigned int)appended;
  }
  appended = STRU::ExpandEnvironmentVariables(*(const unsigned __int16 **)(v4 + 136), (struct STRU *)v3);
  if ( appended < 0 )
    goto LABEL_23;
  v6 = 0;
  if ( *((_DWORD *)this + 30) > 2u )
  {
    v7 = (_WORD *)*((_QWORD *)this + 13);
    if ( *v7 == 92 && v7[1] == 92 )
    {
      v8 = wcsstr(v3[4], L"\\\\?\\UNC");
      v9 = wcsstr(*((const wchar_t **)this + 13), L"\\\\?");
      if ( !v8 )
      {
        if ( v9 )
          goto LABEL_12;
        v10 = *((_QWORD *)this + 13);
        STRU::Copy((STRU *)v14, L"\\\\?\\UNC\\");
        STRU::Append((STRU *)v14, (const unsigned __int16 *)(v10 + 4));
        STRU::Copy((STRU *)v3, (const struct STRU *)v14);
      }
      v6 = 1;
    }
  }
LABEL_12:
  DirectoryRecursively = CREATE_DIRECTORY_HELPER::CreateDirectoryRecursively(v3[4], v5);
  appended = DirectoryRecursively;
  if ( !DirectoryRecursively || DirectoryRecursively == -2147024713 || DirectoryRecursively == -2147024816 )
  {
    appended = STRU::Copy((STRU *)v15, L"W3SVC");
    if ( appended >= 0 )
    {
      appended = LOG_WRITER::AppendNum(
                   v12,
                   (struct STRU *)v15,
                   *(unsigned int *)(*((_QWORD *)this + 1) + 32LL),
                   v16,
                   0xCu,
                   0,
                   0);
      if ( appended >= 0 )
      {
        if ( *(_WORD *)(*((_QWORD *)this + 13) + 2LL * (unsigned int)(*((_DWORD *)this + 30) - 1)) == 92
          || (appended = STRU::Append((STRU *)v3, 0x5Cu), appended >= 0) )
        {
          appended = STRU::Append((STRU *)v3, (const struct STRU *)v15);
          if ( appended >= 0 )
          {
            appended = LOG_WRITER::CreateLogDirectory(this, *((const unsigned __int16 **)this + 13), v6);
            if ( appended >= 0 )
            {
              STRU::~STRU((STRU *)v14);
              STRU::~STRU((STRU *)v15);
              return (unsigned int)appended;
            }
          }
        }
      }
    }
    goto LABEL_23;
  }
  *((_DWORD *)this + 169) = 1;
  STRU::~STRU((STRU *)v14);
  STRU::~STRU((STRU *)v15);
  if ( appended < 0 )
    goto LABEL_24;
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180004878  push    rbp
0x18000487a  push    rbx
0x18000487b  push    rsi
0x18000487c  push    rdi
0x18000487d  push    r12
0x18000487f  push    r14
0x180004881  lea     rbp, [rsp-228h]
0x180004889  sub     rsp, 328h
0x180004890  mov     rax, cs:__security_cookie
0x180004897  xor     rax, rsp
0x18000489a  mov     [rbp+250h+var_40], rax
0x1800048a1  mov     rdi, rcx
0x1800048a4  xor     ebx, ebx
0x1800048a6  lea     rsi, [rcx+48h]
0x1800048aa  cmp     [rsi+30h], ebx
0x1800048ad  jnz     loc_180004B00
0x1800048b3  xor     edx, edx; Val
0x1800048b5  lea     r8d, [rbx+40h]; Size
0x1800048b9  lea     rcx, [rbp+250h+var_280]; void *
0x1800048bd  call    memset_0
0x1800048c2  lea     r8d, [rbx+20h]
0x1800048c6  lea     rdx, [rbp+250h+var_280]
0x1800048ca  lea     rcx, [rsp+350h+var_2D8]
0x1800048cf  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800048d5  nop
0x1800048d6  xor     edx, edx; Val
0x1800048d8  mov     r8d, 200h; Size
0x1800048de  lea     rcx, [rbp+250h+var_240]; void *
0x1800048e2  call    memset_0
0x1800048e7  mov     r8d, 100h
0x1800048ed  lea     rdx, [rbp+250h+var_240]
0x1800048f1  lea     rcx, [rsp+350h+var_310]
0x1800048f6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800048fc  nop
0x1800048fd  xorps   xmm0, xmm0
0x180004900  xor     eax, eax
0x180004902  movups  xmmword ptr [rbp+250h+var_2A0], xmm0
0x180004906  mov     [rbp+250h+var_290], rax
0x18000490a  mov     rcx, [rdi+8]
0x18000490e  cmp     [rcx+98h], eax
0x180004914  ja      short loc_180004920
0x180004916  mov     ebx, 80070057h
0x18000491b  jmp     loc_180004AA8
0x180004920  mov     rdx, rsi
0x180004923  mov     rcx, [rcx+88h]
0x18000492a  call    cs:__imp_?ExpandEnvironmentVariables@STRU@@SAJPEBGPEAV1@@Z; STRU::ExpandEnvironmentVariables(ushort const *,STRU *)
0x180004930  mov     ebx, eax
0x180004932  test    eax, eax
0x180004934  js      loc_180004AA8
0x18000493a  xor     r14d, r14d
0x18000493d  lea     r12d, [r14+5Ch]
0x180004941  cmp     dword ptr [rdi+78h], 2
0x180004945  jbe     short loc_1800049C0
0x180004947  mov     rax, [rdi+68h]
0x18000494b  cmp     [rax], r12w
0x18000494f  jnz     short loc_1800049C0
0x180004951  cmp     [rax+2], r12w
0x180004956  jnz     short loc_1800049C0
0x180004958  lea     rdx, aUnc; "\\\\?\\UNC"
0x18000495f  mov     rcx, [rsi+20h]; Str
0x180004963  call    cs:__imp_wcsstr
0x180004969  mov     rbx, rax
0x18000496c  lea     rdx, asc_1800120A0; "\\\\?"
0x180004973  mov     rcx, [rdi+68h]; Str
0x180004977  call    cs:__imp_wcsstr
0x18000497d  test    rbx, rbx
0x180004980  jnz     short loc_1800049BA
0x180004982  test    rax, rax
0x180004985  jnz     short loc_1800049C0
0x180004987  mov     rbx, [rdi+68h]
0x18000498b  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x180004992  lea     rcx, [rsp+350h+var_310]
0x180004997  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000499d  lea     rdx, [rbx+4]
0x1800049a1  lea     rcx, [rsp+350h+var_310]
0x1800049a6  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800049ac  lea     rdx, [rsp+350h+var_310]
0x1800049b1  mov     rcx, rsi
0x1800049b4  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800049ba  mov     r14d, 1
0x1800049c0  mov     rcx, [rsi+20h]; unsigned __int16 *
0x1800049c4  call    ?CreateDirectoryRecursively@CREATE_DIRECTORY_HELPER@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CREATE_DIRECTORY_HELPER::CreateDirectoryRecursively(ushort const *,_SECURITY_ATTRIBUTES *)
0x1800049c9  mov     ebx, eax
0x1800049cb  test    eax, eax
0x1800049cd  jz      short loc_180004A0B
0x1800049cf  cmp     eax, 800700B7h
0x1800049d4  jz      short loc_180004A0B
0x1800049d6  cmp     eax, 80070050h
0x1800049db  jz      short loc_180004A0B
0x1800049dd  mov     dword ptr [rdi+2A4h], 1
0x1800049e7  lea     rcx, [rsp+350h+var_310]
0x1800049ec  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800049f2  nop
0x1800049f3  lea     rcx, [rsp+350h+var_2D8]
0x1800049f8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800049fe  test    ebx, ebx
0x180004a00  jns     loc_180004B00
0x180004a06  jmp     loc_180004ABF
0x180004a0b  lea     rdx, aW3svc; "W3SVC"
0x180004a12  lea     rcx, [rsp+350h+var_2D8]
0x180004a17  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004a1d  mov     ebx, eax
0x180004a1f  test    eax, eax
0x180004a21  js      loc_180004AA8
0x180004a27  mov     rax, [rdi+8]
0x180004a2b  mov     r8d, [rax+20h]; unsigned __int64
0x180004a2f  mov     [rsp+350h+var_320], 0; int
0x180004a37  mov     [rsp+350h+var_328], 0; unsigned __int16 *
0x180004a40  mov     [rsp+350h+var_330], 0Ch; unsigned __int64
0x180004a49  lea     r9, [rbp+250h+var_2A0]; unsigned __int16 *
0x180004a4d  lea     rdx, [rsp+350h+var_2D8]; struct STRU *
0x180004a52  call    ?AppendNum@LOG_WRITER@@AEAAJPEAVSTRU@@_KPEAG1PEBGH@Z; LOG_WRITER::AppendNum(STRU *,unsigned __int64,ushort *,unsigned __int64,ushort const *,int)
0x180004a57  mov     ebx, eax
0x180004a59  test    eax, eax
0x180004a5b  js      short loc_180004AA8
0x180004a5d  mov     ecx, [rdi+78h]
0x180004a60  dec     ecx
0x180004a62  mov     rax, [rdi+68h]
0x180004a66  cmp     [rax+rcx*2], r12w
0x180004a6b  jz      short loc_180004A7F
0x180004a6d  mov     edx, r12d
0x180004a70  mov     rcx, rsi
0x180004a73  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180004a79  mov     ebx, eax
0x180004a7b  test    eax, eax
0x180004a7d  js      short loc_180004AA8
0x180004a7f  lea     rdx, [rsp+350h+var_2D8]
0x180004a84  mov     rcx, rsi
0x180004a87  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180004a8d  mov     ebx, eax
0x180004a8f  test    eax, eax
0x180004a91  js      short loc_180004AA8
0x180004a93  mov     r8d, r14d; int
0x180004a96  mov     rdx, [rdi+68h]; unsigned __int16 *
0x180004a9a  mov     rcx, rdi; this
0x180004a9d  call    ?CreateLogDirectory@LOG_WRITER@@AEAAJPEBGH@Z; LOG_WRITER::CreateLogDirectory(ushort const *,int)
0x180004aa2  mov     ebx, eax
0x180004aa4  test    eax, eax
0x180004aa6  jns     short loc_180004AE9
0x180004aa8  lea     rcx, [rsp+350h+var_310]
0x180004aad  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004ab3  nop
0x180004ab4  lea     rcx, [rsp+350h+var_2D8]
0x180004ab9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004abf  mov     dword ptr [rsp+350h+var_330], 1
0x180004ac7  mov     r9d, ebx
0x180004aca  mov     r8, [rdi+68h]
0x180004ace  mov     edx, 0C0001772h
0x180004ad3  mov     rcx, rdi
0x180004ad6  call    ?LogW3LogSvcEvent@LOG_WRITER@@AEAAXKPEBGKW4LOG_SVC_EVENT@@@Z; LOG_WRITER::LogW3LogSvcEvent(ulong,ushort const *,ulong,LOG_SVC_EVENT)
0x180004adb  mov     rcx, [rdi+68h]
0x180004adf  xor     eax, eax
0x180004ae1  mov     [rcx], ax
0x180004ae4  mov     [rdi+78h], eax
0x180004ae7  jmp     short loc_180004B00
0x180004ae9  lea     rcx, [rsp+350h+var_310]
0x180004aee  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004af4  nop
0x180004af5  lea     rcx, [rsp+350h+var_2D8]
0x180004afa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004b00  mov     eax, ebx
0x180004b02  mov     rcx, [rbp+250h+var_40]
0x180004b09  xor     rcx, rsp; StackCookie
0x180004b0c  call    __security_check_cookie
0x180004b11  add     rsp, 328h
0x180004b18  pop     r14
0x180004b1a  pop     r12
0x180004b1c  pop     rdi
0x180004b1d  pop     rsi
0x180004b1e  pop     rbx
0x180004b1f  pop     rbp
0x180004b20  retn
```
