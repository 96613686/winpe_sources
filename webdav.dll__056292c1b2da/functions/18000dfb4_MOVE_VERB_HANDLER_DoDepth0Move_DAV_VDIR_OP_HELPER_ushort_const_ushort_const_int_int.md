# MOVE_VERB_HANDLER::DoDepth0Move(DAV_VDIR_OP_HELPER *,ushort const *,ushort const *,int,int *)

- ea: `0x18000dfb4`
- end: `0x18000e1a3`
- name: `?DoDepth0Move@MOVE_VERB_HANDLER@@AEAAJPEAVDAV_VDIR_OP_HELPER@@PEBG1HPEAH@Z`
- size: `495`
- prototype: `__int64 __fastcall(MOVE_VERB_HANDLER *this, struct DAV_VDIR_OP_HELPER *, const unsigned __int16 *, const unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000e1b0`

## callees

- `0x1800025e4`
- `0x180002dc0`
- `0x18000dfb4`
- `0x18000e320`
- `0x1800119c4`
- `0x18001b130`
- `0x18001b814`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x18000e148`
- `iisutil!SAFE_snwprintf` at `0x18000e148`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000e130`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000e130`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e17c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e17c`

## pseudocode

```c
__int64 __fastcall MOVE_VERB_HANDLER::DoDepth0Move(
        MOVE_VERB_HANDLER *this,
        struct DAV_VDIR_OP_HELPER *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        int *a6)
{
  struct IBaseFileSystem **v6; // rsi
  __int64 result; // rax
  struct IValidator *v12; // rdi
  int v13; // esi
  int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // rbx
  int v17; // [rsp+20h] [rbp-98h]
  struct IValidator *v18; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-80h] BYREF
  __int64 v20; // [rsp+58h] [rbp-60h]

  v6 = (struct IBaseFileSystem **)((char *)this + 240);
  v18 = 0;
  if ( a5 && IsVDirParent(this, (struct IIS_VDIR_CONFIG *)(*((_QWORD *)this + 3) + 64LL), *v6, a3) )
    return 2377062704LL;
  result = COPY_MOVE_BASE_HANDLER::HandleOverwrite((struct IBaseFileSystem **)this, a4, a5, a6);
  if ( (int)result >= 0 )
  {
    result = NeedsValidation(
               *((struct IHttpContext **)this + 1),
               *v6,
               (struct IIS_VDIR_CONFIG *)(*((_QWORD *)this + 3) + 64LL),
               a3,
               a4,
               &v18);
    if ( (int)result >= 0 )
    {
      v12 = v18;
      if ( v18 )
      {
        v13 = COPY_MOVE_BASE_HANDLER::DoValidatedCopyOrMove(this, v18, 1);
        (**(void (__fastcall ***)(struct IValidator *, __int64))v12)(v12, 1);
      }
      else
      {
        v13 = MoveFileOrDir(*v6, *((const unsigned __int16 **)this + 23), a4);
      }
      if ( v13 < 0 )
      {
        v15 = *((_QWORD *)this + 23);
        v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 272LL))(*((_QWORD *)this + 1));
        STRU::STRU((STRU *)v19);
        LOBYTE(v17) = 3;
        if ( (int)SAFE_snwprintf((struct STRU *)v19, L"Source: %s, Destination: %s", v15, a4) >= 0 )
          v15 = v20;
        (*(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v16 + 32LL))(
          v16,
          L"Error Moving File",
          v15,
          (unsigned int)v13,
          v17);
        STRU::~STRU((STRU *)v19);
      }
      else
      {
        v14 = (*(__int64 (__fastcall **)(struct DAV_VDIR_OP_HELPER *, _QWORD, _QWORD, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)a2 + 32LL))(
                a2,
                *((_QWORD *)this + 9),
                *((_QWORD *)this + 23),
                a3,
                a4);
        v13 = v14;
        if ( v14 < 0 )
          DAV_TRACE::TracePropertyMoveError(
            *((struct IHttpContext **)this + 1),
            v14,
            *((const unsigned __int16 **)this + 9),
            *((const unsigned __int16 **)this + 23),
            a3,
            a4);
      }
      return (unsigned int)v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000dfb4  push    rbx
0x18000dfb6  push    rbp
0x18000dfb7  push    rsi
0x18000dfb8  push    rdi
0x18000dfb9  push    r12
0x18000dfbb  push    r13
0x18000dfbd  push    r14
0x18000dfbf  sub     rsp, 80h
0x18000dfc6  mov     rax, cs:__security_cookie
0x18000dfcd  xor     rax, rsp
0x18000dfd0  mov     [rsp+0B8h+var_48], rax
0x18000dfd5  cmp     [rsp+0B8h+arg_20], 0
0x18000dfdd  lea     rsi, [rcx+0F0h]
0x18000dfe4  mov     r13, [rsp+0B8h+arg_28]
0x18000dfec  mov     rbp, r9
0x18000dfef  mov     r14, r8
0x18000dff2  mov     [rsp+0B8h+var_88], 0
0x18000dffb  mov     r12, rdx
0x18000dffe  mov     rbx, rcx
0x18000e001  jz      short loc_18000E024
0x18000e003  mov     rdx, [rcx+18h]
0x18000e007  mov     r9, r8; unsigned __int16 *
0x18000e00a  mov     r8, [rsi]; struct IBaseFileSystem *
0x18000e00d  add     rdx, 40h ; '@'; struct IIS_VDIR_CONFIG *
0x18000e011  call    ?IsVDirParent@@YAHPEAVIVDirOperationHelper@@PEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEBG@Z; IsVDirParent(IVDirOperationHelper *,IIS_VDIR_CONFIG *,IBaseFileSystem *,ushort const *)
0x18000e016  test    eax, eax
0x18000e018  jz      short loc_18000E024
0x18000e01a  mov     eax, 8DAF1930h
0x18000e01f  jmp     loc_18000E184
0x18000e024  mov     r8d, [rsp+0B8h+arg_20]; int
0x18000e02c  mov     r9, r13; int *
0x18000e02f  mov     rdx, rbp; unsigned __int16 *
0x18000e032  mov     rcx, rbx; this
0x18000e035  call    ?HandleOverwrite@COPY_MOVE_BASE_HANDLER@@QEAAJPEBGHPEAH@Z; COPY_MOVE_BASE_HANDLER::HandleOverwrite(ushort const *,int,int *)
0x18000e03a  test    eax, eax
0x18000e03c  js      loc_18000E184
0x18000e042  mov     r8, [rbx+18h]
0x18000e046  lea     rax, [rsp+0B8h+var_88]
0x18000e04b  mov     rdx, [rsi]; struct IBaseFileSystem *
0x18000e04e  add     r8, 40h ; '@'; struct IIS_VDIR_CONFIG *
0x18000e052  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000e056  mov     r9, r14; unsigned __int16 *
0x18000e059  mov     [rsp+0B8h+var_90], rax; struct IValidator **
0x18000e05e  mov     [rsp+0B8h+var_98], rbp; unsigned __int16 *
0x18000e063  call    ?NeedsValidation@@YAJPEAVIHttpContext@@PEAVIBaseFileSystem@@PEAVIIS_VDIR_CONFIG@@PEBG3PEAPEAVIValidator@@@Z; NeedsValidation(IHttpContext *,IBaseFileSystem *,IIS_VDIR_CONFIG *,ushort const *,ushort const *,IValidator * *)
0x18000e068  test    eax, eax
0x18000e06a  js      loc_18000E184
0x18000e070  mov     rdi, [rsp+0B8h+var_88]
0x18000e075  test    rdi, rdi
0x18000e078  jnz     short loc_18000E090
0x18000e07a  mov     rdx, [rbx+0B8h]; unsigned __int16 *
0x18000e081  mov     r8, rbp; unsigned __int16 *
0x18000e084  mov     rcx, [rsi]; struct IBaseFileSystem *
0x18000e087  call    ?MoveFileOrDir@@YAJPEAVIBaseFileSystem@@PEBG1@Z; MoveFileOrDir(IBaseFileSystem *,ushort const *,ushort const *)
0x18000e08c  mov     esi, eax
0x18000e08e  jmp     short loc_18000E0BB
0x18000e090  mov     r8d, 1; int
0x18000e096  mov     rdx, rdi; struct IValidator *
0x18000e099  mov     rcx, rbx; this
0x18000e09c  call    ?DoValidatedCopyOrMove@COPY_MOVE_BASE_HANDLER@@QEAAJPEAVIValidator@@H@Z; COPY_MOVE_BASE_HANDLER::DoValidatedCopyOrMove(IValidator *,int)
0x18000e0a1  mov     esi, eax
0x18000e0a3  test    rdi, rdi
0x18000e0a6  jz      short loc_18000E0BB
0x18000e0a8  mov     rax, [rdi]
0x18000e0ab  mov     edx, 1
0x18000e0b0  mov     rcx, rdi
0x18000e0b3  mov     rax, [rax]
0x18000e0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0bb  test    esi, esi
0x18000e0bd  js      short loc_18000E10E
0x18000e0bf  mov     rax, [r12]
0x18000e0c3  mov     r9, r14
0x18000e0c6  mov     r8, [rbx+0B8h]
0x18000e0cd  mov     rcx, r12
0x18000e0d0  mov     rdx, [rbx+48h]
0x18000e0d4  mov     [rsp+0B8h+var_98], rbp
0x18000e0d9  mov     rax, [rax+20h]
0x18000e0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0e2  mov     esi, eax
0x18000e0e4  test    eax, eax
0x18000e0e6  jns     loc_18000E182
0x18000e0ec  mov     r9, [rbx+0B8h]; unsigned __int16 *
0x18000e0f3  mov     edx, eax; int
0x18000e0f5  mov     r8, [rbx+48h]; unsigned __int16 *
0x18000e0f9  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000e0fd  mov     [rsp+0B8h+var_90], rbp; unsigned __int16 *
0x18000e102  mov     [rsp+0B8h+var_98], r14; unsigned __int16 *
0x18000e107  call    ?TracePropertyMoveError@DAV_TRACE@@SAXPEAVIHttpContext@@JPEBG111@Z; DAV_TRACE::TracePropertyMoveError(IHttpContext *,long,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000e10c  jmp     short loc_18000E182
0x18000e10e  mov     rcx, [rbx+8]
0x18000e112  mov     rdi, [rbx+0B8h]
0x18000e119  mov     rax, [rcx]
0x18000e11c  mov     rax, [rax+110h]
0x18000e123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e128  lea     rcx, [rsp+0B8h+var_80]
0x18000e12d  mov     rbx, rax
0x18000e130  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000e136  mov     r9, rbp
0x18000e139  lea     rdx, aSourceSDestina; "Source: %s, Destination: %s"
0x18000e140  mov     r8, rdi
0x18000e143  lea     rcx, [rsp+0B8h+var_80]
0x18000e148  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18000e14e  mov     rcx, [rbx]
0x18000e151  lea     rdx, aErrorMovingFil; "Error Moving File"
0x18000e158  test    eax, eax
0x18000e15a  mov     byte ptr [rsp+0B8h+var_98], 3
0x18000e15f  mov     r9d, esi
0x18000e162  cmovns  rdi, [rsp+0B8h+var_60]
0x18000e168  mov     rax, [rcx+20h]
0x18000e16c  mov     r8, rdi
0x18000e16f  mov     rcx, rbx
0x18000e172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e177  lea     rcx, [rsp+0B8h+var_80]
0x18000e17c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e182  mov     eax, esi
0x18000e184  mov     rcx, [rsp+0B8h+var_48]
0x18000e189  xor     rcx, rsp; StackCookie
0x18000e18c  call    __security_check_cookie
0x18000e191  add     rsp, 80h
0x18000e198  pop     r14
0x18000e19a  pop     r13
0x18000e19c  pop     r12
0x18000e19e  pop     rdi
0x18000e19f  pop     rsi
0x18000e1a0  pop     rbp
0x18000e1a1  pop     rbx
0x18000e1a2  retn
```
