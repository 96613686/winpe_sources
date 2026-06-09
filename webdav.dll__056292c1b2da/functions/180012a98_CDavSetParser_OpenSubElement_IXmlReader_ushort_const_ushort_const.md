# CDavSetParser::OpenSubElement(IXmlReader *,ushort const *,ushort const *)

- ea: `0x180012a98`
- end: `0x180012c4c`
- name: `?OpenSubElement@CDavSetParser@@AEAAJPEAUIXmlReader@@PEBG1@Z`
- size: `436`
- prototype: `__int64 __fastcall(CDavSetParser *__hidden this, struct IXmlReader *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180012970`

## callees

- `0x1800122e0`
- `0x180012a98`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180012bf9`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180012bf9`
- `iisutil!SAFE_snwprintf` at `0x180012b8d`
- `iisutil!SAFE_snwprintf` at `0x180012bcd`
- `iisutil!SAFE_snwprintf` at `0x180012bdc`
- `iisutil!SAFE_snwprintf` at `0x180012b8d`
- `iisutil!SAFE_snwprintf` at `0x180012bcd`
- `iisutil!SAFE_snwprintf` at `0x180012bdc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012b5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012b5b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012ad5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012adf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012aea`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012ad5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012adf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012aea`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012c12`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012c1c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012c26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012c12`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012c1c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012c26`

## string_xrefs

- `0x180012b54`: ` xmlns=""`

## pseudocode

```c
__int64 __fastcall CDavSetParser::OpenSubElement(
        CDavSetParser *this,
        struct IXmlReader *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int appended; // ebx
  const wchar_t *v9; // rsi
  int v10; // eax
  __int64 v11; // rax
  int v12; // r14d
  int v13; // eax
  __int64 v15; // [rsp+30h] [rbp-99h] BYREF
  _BYTE v16[32]; // [rsp+38h] [rbp-91h] BYREF
  __int64 v17; // [rsp+58h] [rbp-71h]
  _BYTE v18[32]; // [rsp+70h] [rbp-59h] BYREF
  __int64 v19; // [rsp+90h] [rbp-39h]
  _BYTE v20[56]; // [rsp+A8h] [rbp-21h] BYREF

  v15 = 0;
  STRU::STRU((STRU *)v20);
  STRU::STRU((STRU *)v18);
  STRU::STRU((STRU *)v16);
  appended = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, __int64 *, __int64))(*((_QWORD *)this + 39)
                                                                                             + 24LL))(
               (char *)this + 312,
               a3,
               &v15,
               1);
  if ( appended >= 0 )
  {
    appended = CDavSetParser::AppendOtherAttributes(this, a2, (struct STRU *)v18, 0);
    if ( appended >= 0 )
    {
      if ( *(_WORD *)(**(__int64 (__fastcall ***)(__int64))v15)(v15) )
      {
        v9 = &Src;
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
        v10 = SAFE_snwprintf((struct STRU *)v16, L"%s:%s", v11, a4);
      }
      else
      {
        v9 = L" xmlns=\"\"";
        v10 = STRU::Copy((STRU *)v16, a4);
      }
      appended = v10;
      if ( v10 >= 0 )
      {
        if ( ((unsigned int (__fastcall *)(struct IXmlReader *))a2->lpVtbl->IsEmptyElement)(a2) )
        {
          v12 = 0;
          v13 = SAFE_snwprintf((struct STRU *)v20, L"<%s%s%s/>", v17, v9, v19);
        }
        else
        {
          v13 = SAFE_snwprintf((struct STRU *)v20, L"<%s%s%s>", v17, v9, v19);
          v12 = 1;
        }
        appended = v13;
        if ( v13 >= 0 )
        {
          appended = STRU::Append((CDavSetParser *)((char *)this + 200), (const struct STRU *)v20);
          if ( appended >= 0 )
          {
            if ( v12 )
              ++*((_DWORD *)this + 4);
          }
        }
      }
    }
  }
  STRU::~STRU((STRU *)v16);
  STRU::~STRU((STRU *)v18);
  STRU::~STRU((STRU *)v20);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180012a98  push    rbp
0x180012a9a  push    rbx
0x180012a9b  push    rsi
0x180012a9c  push    rdi
0x180012a9d  push    r12
0x180012a9f  push    r14
0x180012aa1  push    r15
0x180012aa3  lea     rbp, [rsp-27h]
0x180012aa8  sub     rsp, 0F0h
0x180012aaf  mov     rax, cs:__security_cookie
0x180012ab6  xor     rax, rsp
0x180012ab9  mov     [rbp+57h+var_40], rax
0x180012abd  mov     rdi, rcx
0x180012ac0  xor     r12d, r12d
0x180012ac3  lea     rcx, [rbp+57h+var_78]
0x180012ac7  mov     [rsp+120h+var_F0], r12
0x180012acc  mov     r15, r9
0x180012acf  mov     rbx, r8
0x180012ad2  mov     r14, rdx
0x180012ad5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012adb  lea     rcx, [rbp+57h+var_B0]
0x180012adf  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012ae5  lea     rcx, [rsp+120h+var_E8]
0x180012aea  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012af0  lea     rcx, [rdi+138h]
0x180012af7  mov     rdx, rbx
0x180012afa  mov     rax, [rcx]
0x180012afd  lea     r9d, [r12+1]
0x180012b02  lea     r8, [rsp+120h+var_F0]
0x180012b07  mov     rax, [rax+18h]
0x180012b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b10  mov     ebx, eax
0x180012b12  test    eax, eax
0x180012b14  js      loc_180012C0D
0x180012b1a  xor     r9d, r9d; int
0x180012b1d  lea     r8, [rbp+57h+var_B0]; struct STRU *
0x180012b21  mov     rdx, r14; struct IXmlReader *
0x180012b24  mov     rcx, rdi; this
0x180012b27  call    ?AppendOtherAttributes@CDavSetParser@@AEAAJPEAUIXmlReader@@PEAVSTRU@@H@Z; CDavSetParser::AppendOtherAttributes(IXmlReader *,STRU *,int)
0x180012b2c  mov     ebx, eax
0x180012b2e  test    eax, eax
0x180012b30  js      loc_180012C0D
0x180012b36  mov     rcx, [rsp+120h+var_F0]
0x180012b3b  mov     rax, [rcx]
0x180012b3e  mov     rax, [rax]
0x180012b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b46  cmp     [rax], r12w
0x180012b4a  jnz     short loc_180012B63
0x180012b4c  mov     rdx, r15
0x180012b4f  lea     rcx, [rsp+120h+var_E8]
0x180012b54  lea     rsi, aXmlns; " xmlns=\"\""
0x180012b5b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012b61  jmp     short loc_180012B93
0x180012b63  mov     rcx, [rsp+120h+var_F0]
0x180012b68  lea     rsi, Src
0x180012b6f  mov     rax, [rcx]
0x180012b72  mov     rax, [rax+8]
0x180012b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b7b  mov     r8, rax
0x180012b7e  lea     rdx, aSS_2; "%s:%s"
0x180012b85  mov     r9, r15
0x180012b88  lea     rcx, [rsp+120h+var_E8]
0x180012b8d  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180012b93  mov     ebx, eax
0x180012b95  test    eax, eax
0x180012b97  js      short loc_180012C0D
0x180012b99  mov     rax, [r14]
0x180012b9c  mov     rcx, r14
0x180012b9f  mov     rax, [rax+0A0h]
0x180012ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bab  mov     r8, [rbp+57h+var_C8]
0x180012baf  lea     rcx, [rbp+57h+var_78]
0x180012bb3  test    eax, eax
0x180012bb5  mov     r9, rsi
0x180012bb8  mov     rax, [rbp+57h+var_90]
0x180012bbc  mov     [rsp+120h+var_100], rax
0x180012bc1  jz      short loc_180012BD5
0x180012bc3  lea     rdx, aSSS_0; "<%s%s%s/>"
0x180012bca  mov     r14d, r12d
0x180012bcd  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180012bd3  jmp     short loc_180012BE8
0x180012bd5  lea     rdx, aSSS_1; "<%s%s%s>"
0x180012bdc  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180012be2  mov     r14d, 1
0x180012be8  mov     ebx, eax
0x180012bea  test    eax, eax
0x180012bec  js      short loc_180012C0D
0x180012bee  lea     rcx, [rdi+0C8h]
0x180012bf5  lea     rdx, [rbp+57h+var_78]
0x180012bf9  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180012bff  mov     ebx, eax
0x180012c01  test    eax, eax
0x180012c03  js      short loc_180012C0D
0x180012c05  test    r14d, r14d
0x180012c08  jz      short loc_180012C0D
0x180012c0a  inc     dword ptr [rdi+10h]
0x180012c0d  lea     rcx, [rsp+120h+var_E8]
0x180012c12  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012c18  lea     rcx, [rbp+57h+var_B0]
0x180012c1c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012c22  lea     rcx, [rbp+57h+var_78]
0x180012c26  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012c2c  mov     eax, ebx
0x180012c2e  mov     rcx, [rbp+57h+var_40]
0x180012c32  xor     rcx, rsp; StackCookie
0x180012c35  call    __security_check_cookie
0x180012c3a  add     rsp, 0F0h
0x180012c41  pop     r15
0x180012c43  pop     r14
0x180012c45  pop     r12
0x180012c47  pop     rdi
0x180012c48  pop     rsi
0x180012c49  pop     rbx
0x180012c4a  pop     rbp
0x180012c4b  retn
```
