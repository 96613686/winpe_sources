# IIS_VDIR_CONFIG::InitializeVDir(IHttpServer *,ushort const *,INativeConfigurationElement *)

- ea: `0x18001cdd0`
- end: `0x18001d078`
- name: `?InitializeVDir@IIS_VDIR_CONFIG@@AEAAJPEAVIHttpServer@@PEBGPEAVINativeConfigurationElement@@@Z`
- size: `680`
- prototype: `__int64 __fastcall(IIS_VDIR_CONFIG *__hidden this, struct IHttpServer *, const unsigned __int16 *, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001ca08`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x1800043b0`
- `0x180004808`
- `0x180019d58`
- `0x18001c610`
- `0x18001c7a8`
- `0x18001c854`
- `0x18001cdd0`
- `0x1800224c2`
- `0x180022520`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001cfcc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001cfcc`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ce17`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ce21`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ce2e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ce3b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ce48`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001cecd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001cfaf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ce17`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ce21`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ce2e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ce3b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ce48`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001cecd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001cfaf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cf40`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d02d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cf40`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d02d`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001cf2f`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001cf2f`

## pseudocode

```c
__int64 __fastcall IIS_VDIR_CONFIG::InitializeVDir(
        IIS_VDIR_CONFIG *this,
        struct IHttpServer *a2,
        const unsigned __int16 *a3,
        struct INativeConfigurationElement *a4)
{
  char *v8; // rax
  char *v9; // rbx
  int v10; // edi
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  const unsigned __int16 *i; // r8
  int v15; // r8d
  unsigned __int16 *v16; // rbp
  struct STATIC_WSTRING_HASH_RECORD *Key; // rdi
  char *v18; // rax
  _BYTE v19[32]; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int16 *v20; // [rsp+40h] [rbp-58h]

  v8 = (char *)operator new(0x170u);
  v9 = v8;
  if ( !v8 )
    return (unsigned int)-2147024888;
  STRU::STRU((STRU *)(v8 + 48));
  STRU::STRU((STRU *)(v9 + 104));
  STRU::STRU((STRU *)(v9 + 160));
  STRU::STRU((STRU *)(v9 + 216));
  STRU::STRU((STRU *)(v9 + 272));
  *((_QWORD *)v9 + 42) = a2;
  *(_QWORD *)v9 = 0;
  *((_QWORD *)v9 + 3) = 0;
  *((_QWORD *)v9 + 41) = 0;
  *((_DWORD *)v9 + 86) = -1;
  *(_QWORD *)(v9 + 348) = 0;
  *(_QWORD *)(v9 + 356) = 0;
  v10 = IIS_VDIR::Initialize((const wchar_t **)v9, a3, a4);
  if ( v10 >= 0 )
  {
    if ( *((_DWORD *)v9 + 89) )
    {
      if ( *((_QWORD *)this + 271) )
      {
        IIS_VDIR::~IIS_VDIR((IIS_VDIR *)v9);
        operator delete(v9);
        return 0;
      }
      *((_QWORD *)this + 271) = v9;
LABEL_33:
      STATIC_WSTRING_HASH::InsertRecord(this, (struct STATIC_WSTRING_HASH_RECORD *)v9);
      ++*((_DWORD *)this + 540);
      *((_DWORD *)this + 541) |= *((_DWORD *)v9 + 90);
      return 0;
    }
    STRU::STRU((STRU *)v19);
    v12 = (const unsigned __int16 *)*((_QWORD *)v9 + 10);
    if ( *v12 != 47 )
    {
      v10 = -2147024809;
LABEL_20:
      STRU::~STRU((STRU *)v19);
      goto LABEL_21;
    }
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    for ( i = &v12[v13 - 1]; i > v12; --i )
    {
      if ( *i != 47 )
      {
        do
          --i;
        while ( i > v12 && *i != 47 );
        break;
      }
    }
    v10 = STRU::Copy((STRU *)v19, v12, i - v12 + 1);
    if ( v10 < 0 )
      goto LABEL_20;
    v16 = v20;
    Key = STATIC_WSTRING_HASH::FindKey((IIS_VDIR_CONFIG *)((char *)this + 1056), v20, v15);
    if ( Key )
    {
LABEL_32:
      STATIC_WSTRING_HASH::InsertRecord(
        (struct STATIC_WSTRING_HASH_RECORD *)((char *)Key + 24),
        (struct STATIC_WSTRING_HASH_RECORD *)(v9 + 24));
      STRU::~STRU((STRU *)v19);
      goto LABEL_33;
    }
    v18 = (char *)operator new(0x470u);
    Key = (struct STATIC_WSTRING_HASH_RECORD *)v18;
    if ( v18 )
    {
      *((_DWORD *)v18 + 268) = 0;
      memset_0(v18 + 24, 0, 0x418u);
      STRU::STRU((struct STATIC_WSTRING_HASH_RECORD *)((char *)Key + 1080));
      *(_QWORD *)Key = 0;
      if ( *v16 == 47
        && (int)STRU::Copy((struct STATIC_WSTRING_HASH_RECORD *)((char *)Key + 1080), v16) >= 0
        && (int)EnsureUriPathIsSlashTerminated((struct STATIC_WSTRING_HASH_RECORD *)((char *)Key + 1080)) >= 0 )
      {
        *(_QWORD *)Key = *((_QWORD *)Key + 139);
        STATIC_WSTRING_HASH::InsertRecord((IIS_VDIR_CONFIG *)((char *)this + 1056), Key);
        goto LABEL_30;
      }
      IIS_VDIR_PARENT::~IIS_VDIR_PARENT(Key);
      operator delete(Key);
    }
    Key = 0;
LABEL_30:
    if ( !Key )
    {
      v10 = -2147024888;
      goto LABEL_20;
    }
    goto LABEL_32;
  }
LABEL_21:
  IIS_VDIR::~IIS_VDIR((IIS_VDIR *)v9);
  operator delete(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001cdd0  push    rbx
0x18001cdd2  push    rbp
0x18001cdd3  push    rsi
0x18001cdd4  push    rdi
0x18001cdd5  push    r12
0x18001cdd7  push    r14
0x18001cdd9  push    r15
0x18001cddb  sub     rsp, 60h
0x18001cddf  mov     rax, cs:__security_cookie
0x18001cde6  xor     rax, rsp
0x18001cde9  mov     [rsp+98h+var_40], rax
0x18001cdee  mov     rsi, rcx
0x18001cdf1  mov     r14, r9
0x18001cdf4  mov     ecx, 170h; Size
0x18001cdf9  mov     rbp, r8
0x18001cdfc  mov     rdi, rdx
0x18001cdff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ce04  xor     r12d, r12d
0x18001ce07  mov     rbx, rax
0x18001ce0a  test    rax, rax
0x18001ce0d  jz      loc_18001D055
0x18001ce13  lea     rcx, [rax+30h]
0x18001ce17  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001ce1d  lea     rcx, [rbx+68h]
0x18001ce21  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001ce27  lea     rcx, [rbx+0A0h]
0x18001ce2e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001ce34  lea     rcx, [rbx+0D8h]
0x18001ce3b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001ce41  lea     rcx, [rbx+110h]
0x18001ce48  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001ce4e  mov     r8, r14; struct INativeConfigurationElement *
0x18001ce51  mov     [rbx+150h], rdi
0x18001ce58  mov     rdx, rbp; unsigned __int16 *
0x18001ce5b  mov     [rbx], r12
0x18001ce5e  mov     rcx, rbx; this
0x18001ce61  mov     [rbx+18h], r12
0x18001ce65  mov     [rbx+148h], r12
0x18001ce6c  mov     dword ptr [rbx+158h], 0FFFFFFFFh
0x18001ce76  mov     [rbx+15Ch], r12
0x18001ce7d  mov     [rbx+164h], r12
0x18001ce84  call    ?Initialize@IIS_VDIR@@QEAAJPEBGPEAVINativeConfigurationElement@@@Z; IIS_VDIR::Initialize(ushort const *,INativeConfigurationElement *)
0x18001ce89  mov     edi, eax
0x18001ce8b  test    eax, eax
0x18001ce8d  js      loc_18001CF46
0x18001ce93  cmp     [rbx+164h], r12d
0x18001ce9a  jz      short loc_18001CEC8
0x18001ce9c  cmp     [rsi+878h], r12
0x18001cea3  jnz     short loc_18001CEB1
0x18001cea5  mov     [rsi+878h], rbx
0x18001ceac  jmp     loc_18001D033
0x18001ceb1  mov     rcx, rbx; this
0x18001ceb4  call    ??1IIS_VDIR@@QEAA@XZ; IIS_VDIR::~IIS_VDIR(void)
0x18001ceb9  mov     rcx, rbx; Block
0x18001cebc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cec1  xor     eax, eax
0x18001cec3  jmp     loc_18001D05C
0x18001cec8  lea     rcx, [rsp+98h+var_78]
0x18001cecd  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001ced3  mov     rdx, [rbx+50h]
0x18001ced7  mov     r14w, 2Fh ; '/'
0x18001cedc  cmp     [rdx], r14w
0x18001cee0  jz      short loc_18001CEE9
0x18001cee2  mov     edi, 80070057h
0x18001cee7  jmp     short loc_18001CF3B
0x18001cee9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ceed  inc     rax
0x18001cef0  cmp     [rdx+rax*2], r12w
0x18001cef5  jnz     short loc_18001CEED
0x18001cef7  lea     r8, [rdx-2]
0x18001cefb  lea     r8, [r8+rax*2]
0x18001ceff  jmp     short loc_18001CF0B
0x18001cf01  cmp     [r8], r14w
0x18001cf05  jnz     short loc_18001CF18
0x18001cf07  sub     r8, 2
0x18001cf0b  cmp     r8, rdx
0x18001cf0e  ja      short loc_18001CF01
0x18001cf10  jmp     short loc_18001CF21
0x18001cf12  cmp     [r8], r14w
0x18001cf16  jz      short loc_18001CF21
0x18001cf18  sub     r8, 2
0x18001cf1c  cmp     r8, rdx
0x18001cf1f  ja      short loc_18001CF12
0x18001cf21  sub     r8, rdx
0x18001cf24  lea     rcx, [rsp+98h+var_78]
0x18001cf29  sar     r8, 1
0x18001cf2c  inc     r8d
0x18001cf2f  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001cf35  mov     edi, eax
0x18001cf37  test    eax, eax
0x18001cf39  jns     short loc_18001CF5B
0x18001cf3b  lea     rcx, [rsp+98h+var_78]
0x18001cf40  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001cf46  mov     rcx, rbx; this
0x18001cf49  call    ??1IIS_VDIR@@QEAA@XZ; IIS_VDIR::~IIS_VDIR(void)
0x18001cf4e  mov     rcx, rbx; Block
0x18001cf51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cf56  jmp     loc_18001D05A
0x18001cf5b  mov     rbp, [rsp+98h+var_58]
0x18001cf60  lea     r15, [rsi+420h]
0x18001cf67  mov     rdx, rbp; unsigned __int16 *
0x18001cf6a  mov     rcx, r15; this
0x18001cf6d  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x18001cf72  mov     rdi, rax
0x18001cf75  test    rax, rax
0x18001cf78  jnz     loc_18001D01B
0x18001cf7e  mov     ecx, 470h; Size
0x18001cf83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cf88  mov     rdi, rax
0x18001cf8b  test    rax, rax
0x18001cf8e  jz      short loc_18001D009
0x18001cf90  lea     rcx, [rax+18h]; void *
0x18001cf94  xor     edx, edx; Val
0x18001cf96  mov     r8d, 418h; Size
0x18001cf9c  mov     [rcx+418h], r12d
0x18001cfa3  call    memset_0
0x18001cfa8  lea     rcx, [rdi+438h]
0x18001cfaf  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001cfb5  mov     [rdi], r12
0x18001cfb8  cmp     [rbp+0], r14w
0x18001cfbd  jnz     short loc_18001CFF9
0x18001cfbf  lea     r14, [rdi+438h]
0x18001cfc6  mov     rdx, rbp
0x18001cfc9  mov     rcx, r14
0x18001cfcc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001cfd2  test    eax, eax
0x18001cfd4  js      short loc_18001CFF9
0x18001cfd6  mov     rcx, r14; struct STRU *
0x18001cfd9  call    ?EnsureUriPathIsSlashTerminated@@YAJPEAVSTRU@@@Z; EnsureUriPathIsSlashTerminated(STRU *)
0x18001cfde  test    eax, eax
0x18001cfe0  js      short loc_18001CFF9
0x18001cfe2  mov     rax, [rdi+458h]
0x18001cfe9  mov     rdx, rdi; struct STATIC_WSTRING_HASH_RECORD *
0x18001cfec  mov     rcx, r15; this
0x18001cfef  mov     [rdi], rax
0x18001cff2  call    ?InsertRecord@STATIC_WSTRING_HASH@@QEAAXPEAUSTATIC_WSTRING_HASH_RECORD@@@Z; STATIC_WSTRING_HASH::InsertRecord(STATIC_WSTRING_HASH_RECORD *)
0x18001cff7  jmp     short loc_18001D00C
0x18001cff9  mov     rcx, rdi; this
0x18001cffc  call    ??1IIS_VDIR_PARENT@@QEAA@XZ; IIS_VDIR_PARENT::~IIS_VDIR_PARENT(void)
0x18001d001  mov     rcx, rdi; Block
0x18001d004  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d009  mov     rdi, r12
0x18001d00c  test    rdi, rdi
0x18001d00f  jnz     short loc_18001D01B
0x18001d011  mov     edi, 80070008h
0x18001d016  jmp     loc_18001CF3B
0x18001d01b  lea     rdx, [rbx+18h]; struct STATIC_WSTRING_HASH_RECORD *
0x18001d01f  lea     rcx, [rdi+18h]; this
0x18001d023  call    ?InsertRecord@STATIC_WSTRING_HASH@@QEAAXPEAUSTATIC_WSTRING_HASH_RECORD@@@Z; STATIC_WSTRING_HASH::InsertRecord(STATIC_WSTRING_HASH_RECORD *)
0x18001d028  lea     rcx, [rsp+98h+var_78]
0x18001d02d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001d033  mov     rdx, rbx; struct STATIC_WSTRING_HASH_RECORD *
0x18001d036  mov     rcx, rsi; this
0x18001d039  call    ?InsertRecord@STATIC_WSTRING_HASH@@QEAAXPEAUSTATIC_WSTRING_HASH_RECORD@@@Z; STATIC_WSTRING_HASH::InsertRecord(STATIC_WSTRING_HASH_RECORD *)
0x18001d03e  inc     dword ptr [rsi+870h]
0x18001d044  mov     eax, [rbx+168h]
0x18001d04a  or      [rsi+874h], eax
0x18001d050  jmp     loc_18001CEC1
0x18001d055  mov     edi, 80070008h
0x18001d05a  mov     eax, edi
0x18001d05c  mov     rcx, [rsp+98h+var_40]
0x18001d061  xor     rcx, rsp; StackCookie
0x18001d064  call    __security_check_cookie
0x18001d069  add     rsp, 60h
0x18001d06d  pop     r15
0x18001d06f  pop     r14
0x18001d071  pop     r12
0x18001d073  pop     rdi
0x18001d074  pop     rsi
0x18001d075  pop     rbp
0x18001d076  pop     rbx
0x18001d077  retn
```
