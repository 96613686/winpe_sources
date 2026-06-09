# EnumUri(void *,IIS_VDIR_CONFIG *,IBaseFileSystem *,IUriEnumerator *,ushort const *,ushort const *,ulong)

- ea: `0x18001f128`
- end: `0x18001f353`
- name: `?EnumUri@@YAJPEAXPEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEAVIUriEnumerator@@PEBG4K@Z`
- size: `555`
- prototype: `__int64 __fastcall(void *, struct IIS_VDIR_CONFIG *, struct IBaseFileSystem *, struct IUriEnumerator *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000ed10`
- `0x18001b368`
- `0x18001b60c`
- `0x18001b8c0`

## callees

- `0x180001214`
- `0x180019d58`
- `0x18001f128`
- `0x18001f3f0`
- `0x18001f934`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f21b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f21b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f23c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f24f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f23c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f24f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f172`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f17c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f172`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f17c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f31f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f32a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f31f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f32a`

## pseudocode

```c
__int64 __fastcall EnumUri(
        void *a1,
        struct IIS_VDIR_CONFIG *a2,
        struct IBaseFileSystem *a3,
        struct IUriEnumerator *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned int a7)
{
  __int64 v11; // rax
  unsigned int (__fastcall *v12)(struct IBaseFileSystem *, const unsigned __int16 *, _QWORD, unsigned int *); // rax
  signed int IsSlashTerminated; // ebx
  signed int LastError; // eax
  int v15; // eax
  _QWORD *v16; // rcx
  void *v18; // [rsp+30h] [rbp-D0h] BYREF
  void *Block; // [rsp+38h] [rbp-C8h]
  _QWORD v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[56]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[56]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v23; // [rsp+D0h] [rbp-30h]
  int v24; // [rsp+D4h] [rbp-2Ch]
  int v25; // [rsp+D8h] [rbp-28h]
  BOOL v26; // [rsp+DCh] [rbp-24h]
  BOOL v27; // [rsp+E0h] [rbp-20h]
  unsigned int v28[4]; // [rsp+340h] [rbp+240h] BYREF
  __int128 v29; // [rsp+350h] [rbp+250h]
  int v30; // [rsp+360h] [rbp+260h]

  STRU::STRU((STRU *)v21);
  STRU::STRU((STRU *)v22);
  v20[0] = a2;
  v30 = 0;
  Block = 0;
  v18 = a1;
  v20[3] = &v18;
  v20[1] = a3;
  v20[2] = a4;
  v23 = a7;
  v27 = (a7 & 0x4000) == 0;
  v26 = v27;
  v11 = *(_QWORD *)a3;
  *(_OWORD *)v28 = 0;
  v24 = 0;
  v29 = 0;
  v12 = *(unsigned int (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *, _QWORD, unsigned int *))(v11 + 88);
  v25 = 1;
  if ( v12(a3, a6, 0, v28) )
  {
    IsSlashTerminated = (v28[0] & 0x10) == 0 ? 0x80070057 : 0;
  }
  else
  {
    LastError = GetLastError();
    IsSlashTerminated = LastError;
    if ( LastError > 0 )
      IsSlashTerminated = (unsigned __int16)LastError | 0x80070000;
  }
  if ( IsSlashTerminated >= 0 )
  {
    IsSlashTerminated = STRU::Copy((STRU *)v21, a5);
    if ( IsSlashTerminated >= 0 )
    {
      IsSlashTerminated = STRU::Copy((STRU *)v22, a6);
      if ( IsSlashTerminated >= 0 )
      {
        IsSlashTerminated = EnsureUriPathIsSlashTerminated((struct STRU *)v21);
        if ( IsSlashTerminated >= 0 )
        {
          IsSlashTerminated = (**(__int64 (__fastcall ***)(struct IUriEnumerator *))a4)(a4);
          if ( IsSlashTerminated >= 0 && (a7 & 2) == 0 )
            MakeRootUriCallback((struct URI_ENUM_DATA *)v20, v28[0]);
        }
      }
    }
  }
  v15 = ++v24;
  if ( IsSlashTerminated >= 0 && v25 )
  {
    IsSlashTerminated = EnumUriWorker((struct URI_ENUM_DATA *)v20);
    v15 = v24;
  }
  v24 = v15 - 1;
  if ( IsSlashTerminated >= 0 )
  {
    if ( (a7 & 2) != 0 && v25 )
      MakeRootUriCallback((struct URI_ENUM_DATA *)v20, v28[0]);
    IsSlashTerminated = (*(__int64 (__fastcall **)(struct IUriEnumerator *))(*(_QWORD *)a4 + 32LL))(a4);
  }
  (*(void (__fastcall **)(struct IUriEnumerator *))(*(_QWORD *)a4 + 40LL))(a4);
  while ( 1 )
  {
    v16 = Block;
    if ( !Block )
      break;
    Block = *(void **)Block;
    *v16 = 0;
    operator delete(v16);
  }
  STRU::~STRU((STRU *)v22);
  STRU::~STRU((STRU *)v21);
  return (unsigned int)IsSlashTerminated;
}

```

## disassembly

```asm
0x18001f128  push    rbp
0x18001f12a  push    rbx
0x18001f12b  push    rsi
0x18001f12c  push    rdi
0x18001f12d  push    r12
0x18001f12f  push    r14
0x18001f131  push    r15
0x18001f133  lea     rbp, [rsp-270h]
0x18001f13b  sub     rsp, 370h
0x18001f142  mov     rax, cs:__security_cookie
0x18001f149  xor     rax, rsp
0x18001f14c  mov     [rbp+2A0h+var_38], rax
0x18001f153  mov     r12, [rbp+2A0h+arg_20]
0x18001f15a  mov     rbx, rcx
0x18001f15d  mov     r15, [rbp+2A0h+arg_28]
0x18001f164  lea     rcx, [rsp+3A0h+var_340]
0x18001f169  mov     r14, r9
0x18001f16c  mov     rsi, r8
0x18001f16f  mov     rdi, rdx
0x18001f172  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001f178  lea     rcx, [rbp+2A0h+var_308]
0x18001f17c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001f182  xor     eax, eax
0x18001f184  mov     [rsp+3A0h+var_360], rdi
0x18001f189  mov     edi, [rbp+2A0h+arg_30]
0x18001f18f  lea     r9, [rbp+2A0h+var_60]
0x18001f196  mov     [rbp+2A0h+var_40], eax
0x18001f19c  xorps   xmm0, xmm0
0x18001f19f  mov     [rsp+3A0h+Block], rax
0x18001f1a4  xor     r8d, r8d
0x18001f1a7  lea     rax, [rsp+3A0h+var_370]
0x18001f1ac  mov     [rsp+3A0h+var_370], rbx
0x18001f1b1  mov     [rsp+3A0h+var_348], rax
0x18001f1b6  mov     rdx, r15
0x18001f1b9  mov     eax, edi
0x18001f1bb  mov     [rsp+3A0h+var_358], rsi
0x18001f1c0  shr     eax, 0Eh
0x18001f1c3  mov     rcx, rsi
0x18001f1c6  not     eax
0x18001f1c8  mov     [rsp+3A0h+var_350], r14
0x18001f1cd  and     eax, 1
0x18001f1d0  mov     [rbp+2A0h+var_2D0], edi
0x18001f1d3  mov     [rbp+2A0h+var_2C0], eax
0x18001f1d6  mov     [rbp+2A0h+var_2C4], eax
0x18001f1d9  mov     rax, [rsi]
0x18001f1dc  movups  xmmword ptr [rbp+2A0h+var_60], xmm0
0x18001f1e3  mov     [rbp+2A0h+var_2CC], 0
0x18001f1ea  movups  [rbp+2A0h+var_50], xmm0
0x18001f1f1  mov     rax, [rax+58h]
0x18001f1f5  mov     [rbp+2A0h+var_2C8], 1
0x18001f1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f201  test    eax, eax
0x18001f203  jz      short loc_18001F21B
0x18001f205  mov     eax, [rbp+2A0h+var_60]
0x18001f20b  and     al, 10h
0x18001f20d  neg     al
0x18001f20f  sbb     ebx, ebx
0x18001f211  not     ebx
0x18001f213  and     ebx, 80070057h
0x18001f219  jmp     short loc_18001F230
0x18001f21b  call    cs:__imp_GetLastError
0x18001f221  mov     ebx, eax
0x18001f223  test    eax, eax
0x18001f225  jle     short loc_18001F230
0x18001f227  movzx   ebx, ax
0x18001f22a  or      ebx, 80070000h
0x18001f230  test    ebx, ebx
0x18001f232  js      short loc_18001F295
0x18001f234  mov     rdx, r12
0x18001f237  lea     rcx, [rsp+3A0h+var_340]
0x18001f23c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f242  mov     ebx, eax
0x18001f244  test    eax, eax
0x18001f246  js      short loc_18001F295
0x18001f248  mov     rdx, r15
0x18001f24b  lea     rcx, [rbp+2A0h+var_308]
0x18001f24f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f255  mov     ebx, eax
0x18001f257  test    eax, eax
0x18001f259  js      short loc_18001F295
0x18001f25b  lea     rcx, [rsp+3A0h+var_340]; struct STRU *
0x18001f260  call    ?EnsureUriPathIsSlashTerminated@@YAJPEAVSTRU@@@Z; EnsureUriPathIsSlashTerminated(STRU *)
0x18001f265  mov     ebx, eax
0x18001f267  test    eax, eax
0x18001f269  js      short loc_18001F295
0x18001f26b  mov     rax, [r14]
0x18001f26e  mov     rcx, r14
0x18001f271  mov     rax, [rax]
0x18001f274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f279  mov     ebx, eax
0x18001f27b  test    eax, eax
0x18001f27d  js      short loc_18001F295
0x18001f27f  test    dil, 2
0x18001f283  jnz     short loc_18001F295
0x18001f285  mov     edx, [rbp+2A0h+var_60]; unsigned int
0x18001f28b  lea     rcx, [rsp+3A0h+var_360]; struct URI_ENUM_DATA *
0x18001f290  call    ?MakeRootUriCallback@@YAXPEAVURI_ENUM_DATA@@K@Z; MakeRootUriCallback(URI_ENUM_DATA *,ulong)
0x18001f295  mov     eax, [rbp+2A0h+var_2CC]
0x18001f298  inc     eax
0x18001f29a  mov     [rbp+2A0h+var_2CC], eax
0x18001f29d  test    ebx, ebx
0x18001f29f  js      short loc_18001F2B6
0x18001f2a1  cmp     [rbp+2A0h+var_2C8], 0
0x18001f2a5  jz      short loc_18001F2B6
0x18001f2a7  lea     rcx, [rsp+3A0h+var_360]; struct URI_ENUM_DATA *
0x18001f2ac  call    ?EnumUriWorker@@YAJPEAVURI_ENUM_DATA@@@Z; EnumUriWorker(URI_ENUM_DATA *)
0x18001f2b1  mov     ebx, eax
0x18001f2b3  mov     eax, [rbp+2A0h+var_2CC]
0x18001f2b6  dec     eax
0x18001f2b8  mov     [rbp+2A0h+var_2CC], eax
0x18001f2bb  test    ebx, ebx
0x18001f2bd  js      short loc_18001F2EC
0x18001f2bf  test    dil, 2
0x18001f2c3  jz      short loc_18001F2DB
0x18001f2c5  cmp     [rbp+2A0h+var_2C8], 0
0x18001f2c9  jz      short loc_18001F2DB
0x18001f2cb  mov     edx, [rbp+2A0h+var_60]; unsigned int
0x18001f2d1  lea     rcx, [rsp+3A0h+var_360]; struct URI_ENUM_DATA *
0x18001f2d6  call    ?MakeRootUriCallback@@YAXPEAVURI_ENUM_DATA@@K@Z; MakeRootUriCallback(URI_ENUM_DATA *,ulong)
0x18001f2db  mov     rax, [r14]
0x18001f2de  mov     rcx, r14
0x18001f2e1  mov     rax, [rax+20h]
0x18001f2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2ea  mov     ebx, eax
0x18001f2ec  mov     rax, [r14]
0x18001f2ef  mov     rcx, r14
0x18001f2f2  mov     rax, [rax+28h]
0x18001f2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2fb  mov     rcx, [rsp+3A0h+Block]; Block
0x18001f300  test    rcx, rcx
0x18001f303  jz      short loc_18001F31B
0x18001f305  mov     rax, [rcx]
0x18001f308  mov     [rsp+3A0h+Block], rax
0x18001f30d  mov     qword ptr [rcx], 0
0x18001f314  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f319  jmp     short loc_18001F2FB
0x18001f31b  lea     rcx, [rbp+2A0h+var_308]
0x18001f31f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f325  lea     rcx, [rsp+3A0h+var_340]
0x18001f32a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f330  mov     eax, ebx
0x18001f332  mov     rcx, [rbp+2A0h+var_38]
0x18001f339  xor     rcx, rsp; StackCookie
0x18001f33c  call    __security_check_cookie
0x18001f341  add     rsp, 370h
0x18001f348  pop     r15
0x18001f34a  pop     r14
0x18001f34c  pop     r12
0x18001f34e  pop     rdi
0x18001f34f  pop     rsi
0x18001f350  pop     rbx
0x18001f351  pop     rbp
0x18001f352  retn
```
