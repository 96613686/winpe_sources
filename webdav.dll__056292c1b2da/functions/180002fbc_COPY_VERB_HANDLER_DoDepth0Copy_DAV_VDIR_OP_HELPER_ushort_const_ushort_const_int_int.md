# COPY_VERB_HANDLER::DoDepth0Copy(DAV_VDIR_OP_HELPER *,ushort const *,ushort const *,int,int *)

- ea: `0x180002fbc`
- end: `0x1800031a8`
- name: `?DoDepth0Copy@COPY_VERB_HANDLER@@AEAAJPEAVDAV_VDIR_OP_HELPER@@PEBG1HPEAH@Z`
- size: `492`
- prototype: `__int64 __fastcall(COPY_VERB_HANDLER *this, struct DAV_VDIR_OP_HELPER *, const unsigned __int16 *, const unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800031b0`

## callees

- `0x1800025e4`
- `0x180002dc0`
- `0x180002fbc`
- `0x18000330c`
- `0x1800119c4`
- `0x18001ac50`
- `0x18001b814`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x18000314d`
- `iisutil!SAFE_snwprintf` at `0x18000314d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003135`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003135`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003181`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003181`

## string_xrefs

- `0x180003156`: `Error Copying File`

## pseudocode

```c
__int64 __fastcall COPY_VERB_HANDLER::DoDepth0Copy(
        COPY_VERB_HANDLER *this,
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
        v13 = COPY_MOVE_BASE_HANDLER::DoValidatedCopyOrMove(this, v18, 0);
        (**(void (__fastcall ***)(struct IValidator *, __int64))v12)(v12, 1);
      }
      else
      {
        v13 = CopyFileOrDir(*v6, *((const unsigned __int16 **)this + 23), a4);
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
          L"Error Copying File",
          v15,
          (unsigned int)v13,
          v17);
        STRU::~STRU((STRU *)v19);
      }
      else
      {
        v14 = (*(__int64 (__fastcall **)(struct DAV_VDIR_OP_HELPER *, _QWORD, _QWORD, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)a2 + 24LL))(
                a2,
                *((_QWORD *)this + 9),
                *((_QWORD *)this + 23),
                a3,
                a4);
        v13 = v14;
        if ( v14 < 0 )
          DAV_TRACE::TracePropertyCopyError(
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
0x180002fbc  push    rbx
0x180002fbe  push    rbp
0x180002fbf  push    rsi
0x180002fc0  push    rdi
0x180002fc1  push    r12
0x180002fc3  push    r13
0x180002fc5  push    r14
0x180002fc7  sub     rsp, 80h
0x180002fce  mov     rax, cs:__security_cookie
0x180002fd5  xor     rax, rsp
0x180002fd8  mov     [rsp+0B8h+var_48], rax
0x180002fdd  cmp     [rsp+0B8h+arg_20], 0
0x180002fe5  lea     rsi, [rcx+0F0h]
0x180002fec  mov     r13, [rsp+0B8h+arg_28]
0x180002ff4  mov     rbp, r9
0x180002ff7  mov     r14, r8
0x180002ffa  mov     [rsp+0B8h+var_88], 0
0x180003003  mov     r12, rdx
0x180003006  mov     rbx, rcx
0x180003009  jz      short loc_18000302C
0x18000300b  mov     rdx, [rcx+18h]
0x18000300f  mov     r9, r8; unsigned __int16 *
0x180003012  mov     r8, [rsi]; struct IBaseFileSystem *
0x180003015  add     rdx, 40h ; '@'; struct IIS_VDIR_CONFIG *
0x180003019  call    ?IsVDirParent@@YAHPEAVIVDirOperationHelper@@PEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEBG@Z; IsVDirParent(IVDirOperationHelper *,IIS_VDIR_CONFIG *,IBaseFileSystem *,ushort const *)
0x18000301e  test    eax, eax
0x180003020  jz      short loc_18000302C
0x180003022  mov     eax, 8DAF1930h
0x180003027  jmp     loc_180003189
0x18000302c  mov     r8d, [rsp+0B8h+arg_20]; int
0x180003034  mov     r9, r13; int *
0x180003037  mov     rdx, rbp; unsigned __int16 *
0x18000303a  mov     rcx, rbx; this
0x18000303d  call    ?HandleOverwrite@COPY_MOVE_BASE_HANDLER@@QEAAJPEBGHPEAH@Z; COPY_MOVE_BASE_HANDLER::HandleOverwrite(ushort const *,int,int *)
0x180003042  test    eax, eax
0x180003044  js      loc_180003189
0x18000304a  mov     r8, [rbx+18h]
0x18000304e  lea     rax, [rsp+0B8h+var_88]
0x180003053  mov     rdx, [rsi]; struct IBaseFileSystem *
0x180003056  add     r8, 40h ; '@'; struct IIS_VDIR_CONFIG *
0x18000305a  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000305e  mov     r9, r14; unsigned __int16 *
0x180003061  mov     [rsp+0B8h+var_90], rax; struct IValidator **
0x180003066  mov     [rsp+0B8h+var_98], rbp; unsigned __int16 *
0x18000306b  call    ?NeedsValidation@@YAJPEAVIHttpContext@@PEAVIBaseFileSystem@@PEAVIIS_VDIR_CONFIG@@PEBG3PEAPEAVIValidator@@@Z; NeedsValidation(IHttpContext *,IBaseFileSystem *,IIS_VDIR_CONFIG *,ushort const *,ushort const *,IValidator * *)
0x180003070  test    eax, eax
0x180003072  js      loc_180003189
0x180003078  mov     rdi, [rsp+0B8h+var_88]
0x18000307d  test    rdi, rdi
0x180003080  jnz     short loc_180003098
0x180003082  mov     rdx, [rbx+0B8h]; unsigned __int16 *
0x180003089  mov     r8, rbp; unsigned __int16 *
0x18000308c  mov     rcx, [rsi]; struct IBaseFileSystem *
0x18000308f  call    ?CopyFileOrDir@@YAJPEAVIBaseFileSystem@@PEBG1@Z; CopyFileOrDir(IBaseFileSystem *,ushort const *,ushort const *)
0x180003094  mov     esi, eax
0x180003096  jmp     short loc_1800030C0
0x180003098  xor     r8d, r8d; int
0x18000309b  mov     rdx, rdi; struct IValidator *
0x18000309e  mov     rcx, rbx; this
0x1800030a1  call    ?DoValidatedCopyOrMove@COPY_MOVE_BASE_HANDLER@@QEAAJPEAVIValidator@@H@Z; COPY_MOVE_BASE_HANDLER::DoValidatedCopyOrMove(IValidator *,int)
0x1800030a6  mov     esi, eax
0x1800030a8  test    rdi, rdi
0x1800030ab  jz      short loc_1800030C0
0x1800030ad  mov     rax, [rdi]
0x1800030b0  mov     edx, 1
0x1800030b5  mov     rcx, rdi
0x1800030b8  mov     rax, [rax]
0x1800030bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c0  test    esi, esi
0x1800030c2  js      short loc_180003113
0x1800030c4  mov     rax, [r12]
0x1800030c8  mov     r9, r14
0x1800030cb  mov     r8, [rbx+0B8h]
0x1800030d2  mov     rcx, r12
0x1800030d5  mov     rdx, [rbx+48h]
0x1800030d9  mov     [rsp+0B8h+var_98], rbp
0x1800030de  mov     rax, [rax+18h]
0x1800030e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e7  mov     esi, eax
0x1800030e9  test    eax, eax
0x1800030eb  jns     loc_180003187
0x1800030f1  mov     r9, [rbx+0B8h]; unsigned __int16 *
0x1800030f8  mov     edx, eax; int
0x1800030fa  mov     r8, [rbx+48h]; unsigned __int16 *
0x1800030fe  mov     rcx, [rbx+8]; struct IHttpContext *
0x180003102  mov     [rsp+0B8h+var_90], rbp; unsigned __int16 *
0x180003107  mov     [rsp+0B8h+var_98], r14; unsigned __int16 *
0x18000310c  call    ?TracePropertyCopyError@DAV_TRACE@@SAXPEAVIHttpContext@@JPEBG111@Z; DAV_TRACE::TracePropertyCopyError(IHttpContext *,long,ushort const *,ushort const *,ushort const *,ushort const *)
0x180003111  jmp     short loc_180003187
0x180003113  mov     rcx, [rbx+8]
0x180003117  mov     rdi, [rbx+0B8h]
0x18000311e  mov     rax, [rcx]
0x180003121  mov     rax, [rax+110h]
0x180003128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000312d  lea     rcx, [rsp+0B8h+var_80]
0x180003132  mov     rbx, rax
0x180003135  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000313b  mov     r9, rbp
0x18000313e  lea     rdx, aSourceSDestina; "Source: %s, Destination: %s"
0x180003145  mov     r8, rdi
0x180003148  lea     rcx, [rsp+0B8h+var_80]
0x18000314d  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180003153  mov     rcx, [rbx]
0x180003156  lea     rdx, aErrorCopyingFi; "Error Copying File"
0x18000315d  test    eax, eax
0x18000315f  mov     byte ptr [rsp+0B8h+var_98], 3
0x180003164  mov     r9d, esi
0x180003167  cmovns  rdi, [rsp+0B8h+var_60]
0x18000316d  mov     rax, [rcx+20h]
0x180003171  mov     r8, rdi
0x180003174  mov     rcx, rbx
0x180003177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000317c  lea     rcx, [rsp+0B8h+var_80]
0x180003181  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003187  mov     eax, esi
0x180003189  mov     rcx, [rsp+0B8h+var_48]
0x18000318e  xor     rcx, rsp; StackCookie
0x180003191  call    __security_check_cookie
0x180003196  add     rsp, 80h
0x18000319d  pop     r14
0x18000319f  pop     r13
0x1800031a1  pop     r12
0x1800031a3  pop     rdi
0x1800031a4  pop     rsi
0x1800031a5  pop     rbp
0x1800031a6  pop     rbx
0x1800031a7  retn
```
