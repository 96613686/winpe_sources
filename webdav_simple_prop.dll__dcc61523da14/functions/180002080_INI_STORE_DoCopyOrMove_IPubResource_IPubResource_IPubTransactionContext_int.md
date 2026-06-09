# INI_STORE::DoCopyOrMove(IPubResource *,IPubResource *,IPubTransactionContext * *,int)

- ea: `0x180002080`
- end: `0x1800021f5`
- name: `?DoCopyOrMove@INI_STORE@@AEAAJPEAVIPubResource@@0PEAPEAVIPubTransactionContext@@H@Z`
- size: `373`
- prototype: `__int64 __fastcall(INI_STORE *this, struct IPubResource *, struct IPubResource *, struct IPubTransactionContext **, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001c10`
- `0x1800024c0`

## callees

- `0x180002080`
- `0x180002a7c`
- `0x180002fd0`
- `0x1800031e4`
- `0x180003490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000216e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000216e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020b5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020bf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020ca`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020d4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020b5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020bf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020ca`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020d4`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800021a0`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800021a0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800021aa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800021b5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800021bf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800021c9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800021aa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800021b5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800021bf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800021c9`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800020df`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800020df`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180002164`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180002164`

## pseudocode

```c
__int64 __fastcall INI_STORE::DoCopyOrMove(
        INI_STORE *this,
        struct IPubResource *a2,
        struct IPubResource *a3,
        struct IPubTransactionContext **a4,
        int a5)
{
  int IniBinding; // ebx
  signed int LastError; // eax
  _BYTE v11[32]; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpString; // [rsp+40h] [rbp-C0h]
  int v13; // [rsp+54h] [rbp-ACh]
  LPCWSTR v14[7]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[32]; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpAppName; // [rsp+B8h] [rbp-48h]
  LPCWSTR v17[7]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v18[56]; // [rsp+108h] [rbp+8h] BYREF

  STRU::STRU((STRU *)v17);
  STRU::STRU((STRU *)v18);
  STRU::STRU((STRU *)v14);
  STRU::STRU((STRU *)v15);
  MULTISZ::MULTISZ((MULTISZ *)v11);
  if ( *((_DWORD *)this + 3) )
  {
    IniBinding = 0;
  }
  else
  {
    IniBinding = MakeIniBinding(a2, (INI_STORE *)((char *)this + 12), (struct INI_BINDING *)v17, 0);
    if ( IniBinding >= 0 )
    {
      IniBinding = MakeIniBinding(a3, (INI_STORE *)((char *)this + 12), (struct INI_BINDING *)v14, 1);
      if ( IniBinding >= 0 )
      {
        IniBinding = ReadEntireSection((struct INI_BINDING *)v17, (struct MULTISZ *)v11);
        if ( IniBinding >= 0 )
        {
          if ( v13 )
          {
            IniBinding = 0;
            if ( !WritePrivateProfileSectionW(lpAppName, lpString, v14[4]) )
            {
              LastError = GetLastError();
              IniBinding = LastError;
              if ( LastError > 0 )
                IniBinding = (unsigned __int16)LastError | 0x80070000;
            }
          }
          else
          {
            IniBinding = DeleteEntireSection(v14);
          }
          if ( IniBinding >= 0 && a5 )
            IniBinding = DeleteEntireSection(v17);
        }
      }
    }
  }
  MULTISZ::~MULTISZ((MULTISZ *)v11);
  STRU::~STRU((STRU *)v15);
  STRU::~STRU((STRU *)v14);
  STRU::~STRU((STRU *)v18);
  STRU::~STRU((STRU *)v17);
  return (unsigned int)IniBinding;
}

```

## disassembly

```asm
0x180002080  mov     [rsp-8+arg_0], rbx
0x180002085  mov     [rsp-8+arg_18], rsi
0x18000208a  push    rbp
0x18000208b  push    rdi
0x18000208c  push    r14
0x18000208e  lea     rbp, [rsp-50h]
0x180002093  sub     rsp, 150h
0x18000209a  mov     rax, cs:__security_cookie
0x1800020a1  xor     rax, rsp
0x1800020a4  mov     [rbp+60h+var_20], rax
0x1800020a8  mov     rdi, rcx
0x1800020ab  mov     r14, r8
0x1800020ae  lea     rcx, [rbp+60h+var_90]
0x1800020b2  mov     rsi, rdx
0x1800020b5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800020bb  lea     rcx, [rbp+60h+var_58]
0x1800020bf  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800020c5  lea     rcx, [rsp+160h+var_100]
0x1800020ca  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800020d0  lea     rcx, [rbp+60h+var_C8]
0x1800020d4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800020da  lea     rcx, [rsp+160h+var_140]
0x1800020df  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800020e5  cmp     dword ptr [rdi+0Ch], 0
0x1800020e9  jz      short loc_1800020F2
0x1800020eb  xor     ebx, ebx
0x1800020ed  jmp     loc_18000219B
0x1800020f2  xor     r9d, r9d; int
0x1800020f5  lea     r8, [rbp+60h+var_90]; struct INI_BINDING *
0x1800020f9  lea     rdx, [rdi+0Ch]; struct INI_OPTIONS *
0x1800020fd  mov     rcx, rsi; struct IPubResource *
0x180002100  call    ?MakeIniBinding@@YAJPEAVIPubResource@@PEAUINI_OPTIONS@@PEAUINI_BINDING@@H@Z; MakeIniBinding(IPubResource *,INI_OPTIONS *,INI_BINDING *,int)
0x180002105  mov     ebx, eax
0x180002107  test    eax, eax
0x180002109  js      loc_18000219B
0x18000210f  mov     r9d, 1; int
0x180002115  lea     r8, [rsp+160h+var_100]; struct INI_BINDING *
0x18000211a  lea     rdx, [rdi+0Ch]; struct INI_OPTIONS *
0x18000211e  mov     rcx, r14; struct IPubResource *
0x180002121  call    ?MakeIniBinding@@YAJPEAVIPubResource@@PEAUINI_OPTIONS@@PEAUINI_BINDING@@H@Z; MakeIniBinding(IPubResource *,INI_OPTIONS *,INI_BINDING *,int)
0x180002126  mov     ebx, eax
0x180002128  test    eax, eax
0x18000212a  js      short loc_18000219B
0x18000212c  lea     rdx, [rsp+160h+var_140]; struct MULTISZ *
0x180002131  lea     rcx, [rbp+60h+var_90]; struct INI_BINDING *
0x180002135  call    ?ReadEntireSection@@YAJPEAUINI_BINDING@@PEAVMULTISZ@@@Z; ReadEntireSection(INI_BINDING *,MULTISZ *)
0x18000213a  mov     ebx, eax
0x18000213c  test    eax, eax
0x18000213e  js      short loc_18000219B
0x180002140  cmp     [rsp+160h+var_10C], 0
0x180002145  jnz     short loc_180002155
0x180002147  lea     rcx, [rsp+160h+var_100]; struct INI_BINDING *
0x18000214c  call    ?DeleteEntireSection@@YAJPEAUINI_BINDING@@@Z; DeleteEntireSection(INI_BINDING *)
0x180002151  mov     ebx, eax
0x180002153  jmp     short loc_180002183
0x180002155  mov     r8, [rbp+60h+lpFileName]; lpFileName
0x180002159  xor     ebx, ebx
0x18000215b  mov     rdx, [rsp+160h+lpString]; lpString
0x180002160  mov     rcx, [rbp+60h+lpAppName]; lpAppName
0x180002164  call    cs:__imp_WritePrivateProfileSectionW
0x18000216a  test    eax, eax
0x18000216c  jnz     short loc_180002183
0x18000216e  call    cs:__imp_GetLastError
0x180002174  mov     ebx, eax
0x180002176  test    eax, eax
0x180002178  jle     short loc_180002183
0x18000217a  movzx   ebx, ax
0x18000217d  or      ebx, 80070000h
0x180002183  test    ebx, ebx
0x180002185  js      short loc_18000219B
0x180002187  cmp     [rbp+60h+arg_20], 0
0x18000218e  jz      short loc_18000219B
0x180002190  lea     rcx, [rbp+60h+var_90]; struct INI_BINDING *
0x180002194  call    ?DeleteEntireSection@@YAJPEAUINI_BINDING@@@Z; DeleteEntireSection(INI_BINDING *)
0x180002199  mov     ebx, eax
0x18000219b  lea     rcx, [rsp+160h+var_140]
0x1800021a0  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800021a6  lea     rcx, [rbp+60h+var_C8]
0x1800021aa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800021b0  lea     rcx, [rsp+160h+var_100]
0x1800021b5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800021bb  lea     rcx, [rbp+60h+var_58]
0x1800021bf  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800021c5  lea     rcx, [rbp+60h+var_90]
0x1800021c9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800021cf  mov     eax, ebx
0x1800021d1  mov     rcx, [rbp+60h+var_20]
0x1800021d5  xor     rcx, rsp; StackCookie
0x1800021d8  call    __security_check_cookie
0x1800021dd  lea     r11, [rsp+160h+var_10]
0x1800021e5  mov     rbx, [r11+20h]
0x1800021e9  mov     rsi, [r11+38h]
0x1800021ed  mov     rsp, r11
0x1800021f0  pop     r14
0x1800021f2  pop     rdi
0x1800021f3  pop     rbp
0x1800021f4  retn
```
