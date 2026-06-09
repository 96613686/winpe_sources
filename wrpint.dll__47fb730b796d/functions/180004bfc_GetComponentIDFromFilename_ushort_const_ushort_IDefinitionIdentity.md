# GetComponentIDFromFilename(ushort const *,ushort *,IDefinitionIdentity * *)

- ea: `0x180004bfc`
- end: `0x180004fc7`
- name: `?GetComponentIDFromFilename@@YAJPEBGPEAGPEAPEAUIDefinitionIdentity@@@Z`
- size: `971`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, struct IDefinitionIdentity **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180003a40`

## callees

- `0x1800012f4`
- `0x180001300`
- `0x180001de0`
- `0x1800048bc`
- `0x180004abc`
- `0x180004bfc`
- `0x18001560c`
- `0x1800157f4`
- `0x180015e00`
- `0x180016750`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ced`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f24`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004cdd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004cdd`
- `ntdll!RtlFreeHeap` at `0x180004f14`
- `ntdll!RtlFreeHeap` at `0x180004f14`

## pseudocode

```c
__int64 __fastcall GetComponentIDFromFilename(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        struct IDefinitionIdentity **a3)
{
  __int64 v4; // rdi
  __int64 v5; // r13
  __int64 v6; // rsi
  _BYTE *v7; // r14
  int v8; // ebx
  LPCWSTR v9; // r15
  signed int LastError; // eax
  int v11; // ebx
  __int64 v12; // rcx
  int IdentityAttributes; // eax
  __int64 v14; // rcx
  unsigned __int64 v15; // r12
  int CdfString; // eax
  int v17; // eax
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  struct IDefinitionIdentity **v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  void **v27; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-78h]
  PVOID P[2]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v30[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-58h]
  int v32; // [rsp+B0h] [rbp-50h]
  int v33; // [rsp+B4h] [rbp-4Ch]
  unsigned int v34; // [rsp+B8h] [rbp-48h]
  _UNICODE_STRING v35; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v36[240]; // [rsp+D0h] [rbp-30h] BYREF

  v25 = a3;
  hObject = (HANDLE)-1LL;
  v27 = &LuaLookupContext::`vftable';
  v30[0] = 0;
  v30[1] = -1;
  v32 = -1;
  v33 = -1;
  v34 = -1;
  v31 = 0;
  *(_OWORD *)P = 0;
  lpFileName = 0;
  v4 = 0;
  v35 = 0;
  v23 = 0;
  v5 = 0;
  v24 = 0;
  v6 = 0;
  v19 = 0;
  v7 = 0;
  v26 = 0;
  v21 = 0;
  v8 = FilemapNameAndLeaf((unsigned __int16 **)&lpFileName, &v35, a1, a2);
  if ( v8 < 0 )
    goto LABEL_29;
  v9 = lpFileName;
  hObject = CreateFileW(lpFileName, 0x120089u, 1u, 0, 3u, 0x80u, 0);
  if ( hObject != (HANDLE)-1LL )
  {
    *(_OWORD *)P = 0;
    v11 = CdfInitializeContext(&v27, P);
    if ( v11 < 0 )
      goto LABEL_6;
    v11 = LuaCdfLookupFileEntry(P, &v35, v30);
    if ( v11 < 0 )
      goto LABEL_6;
    v8 = ((__int64 (__fastcall *)(__int64 *))vpfnGetIdentityAuthority)(&v26);
    if ( v8 < 0 )
      goto LABEL_30;
    v8 = (*(__int64 (__fastcall **)(__int64, struct IDefinitionIdentity **))(*(_QWORD *)v26 + 152LL))(v26, a3);
    if ( v8 < 0 || v34 == -1 )
      goto LABEL_30;
    v22 = 0;
    IdentityAttributes = CdfGetIdentityAttributes(v12, P[0], v34, 20, v36, &v22);
    if ( IdentityAttributes == -1073741789 )
    {
      v7 = operator new(saturated_mul(v22, 0xCu));
      if ( !v7 )
      {
        v8 = -2147024882;
        goto LABEL_30;
      }
      v21 = 1;
      IdentityAttributes = CdfGetIdentityAttributes(v14, P[0], v34, v22, v7, &v22);
    }
    else
    {
      v7 = v36;
    }
    if ( IdentityAttributes < 0 )
    {
      v11 = IdentityAttributes;
LABEL_6:
      v8 = v11 | 0x10000000;
      goto LABEL_30;
    }
    v15 = v22;
    if ( !v22 )
    {
      v6 = v19;
      goto LABEL_30;
    }
    while ( 1 )
    {
      if ( *(_DWORD *)&v7[12 * v6] == -1 )
      {
        if ( v4 )
        {
          operator delete((void *)(v4 - 8));
          v4 = 0;
          v23 = 0;
        }
      }
      else
      {
        CdfString = GetCdfString(P[0], *(unsigned int *)&v7[12 * v6], &v23);
        v4 = v23;
        v8 = CdfString;
        if ( CdfString < 0 )
          goto LABEL_28;
      }
      v8 = GetCdfString(P[0], *(unsigned int *)&v7[12 * v6 + 4], &v24);
      if ( v8 < 0 )
        break;
      v17 = GetCdfString(P[0], *(unsigned int *)&v7[12 * v6 + 8], &v19);
      v5 = v24;
      v8 = v17;
      if ( v17 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(struct IDefinitionIdentity *, __int64, __int64, __int64))(*(_QWORD *)*v25 + 32LL))(
               *v25,
               v4,
               v24,
               v19);
        if ( v8 >= 0 && ++v6 < v15 )
          continue;
      }
      goto LABEL_28;
    }
    v5 = v24;
LABEL_28:
    v6 = v19;
LABEL_29:
    v9 = lpFileName;
    goto LABEL_30;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_30:
  if ( P[0] )
    CdfFreeContext();
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v9 )
    operator delete((void *)(v9 - 4));
  if ( v4 )
    operator delete((void *)(v4 - 8));
  if ( v6 )
    operator delete((void *)(v6 - 8));
  if ( v5 )
    operator delete((void *)(v5 - 8));
  if ( v21 )
    operator delete(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004bfc  mov     [rsp-8+arg_18], rbx
0x180004c01  push    rbp
0x180004c02  push    rsi
0x180004c03  push    rdi
0x180004c04  push    r12
0x180004c06  push    r13
0x180004c08  push    r14
0x180004c0a  push    r15
0x180004c0c  lea     rbp, [rsp-0D0h]
0x180004c14  sub     rsp, 1D0h
0x180004c1b  mov     rax, cs:__security_cookie
0x180004c22  xor     rax, rsp
0x180004c25  mov     [rbp+100h+var_40], rax
0x180004c2c  xor     r15d, r15d
0x180004c2f  mov     [rsp+200h+var_190], r8
0x180004c34  lea     rax, ??_7LuaLookupContext@@6B@; const LuaLookupContext::`vftable'
0x180004c3b  mov     [rbp+100h+hObject], 0FFFFFFFFFFFFFFFFh
0x180004c43  xorps   xmm0, xmm0
0x180004c46  mov     [rbp+100h+var_180], rax
0x180004c4a  or      eax, 0FFFFFFFFh
0x180004c4d  mov     [rbp+100h+var_160], r15d
0x180004c51  mov     r12, r8
0x180004c54  mov     [rbp+100h+var_15C], eax
0x180004c57  mov     r9, rdx; unsigned __int16 *
0x180004c5a  mov     [rbp+100h+var_150], eax
0x180004c5d  mov     r8, rcx; unsigned __int16 *
0x180004c60  mov     [rbp+100h+var_14C], eax
0x180004c63  lea     rdx, [rbp+100h+var_140]; struct _UNICODE_STRING *
0x180004c67  mov     [rbp+100h+var_148], eax
0x180004c6a  lea     rcx, [rsp+200h+lpFileName]; unsigned __int16 **
0x180004c6f  mov     [rbp+100h+var_158], r15
0x180004c73  movups  xmmword ptr [rbp+100h+P], xmm0
0x180004c77  mov     [rsp+200h+lpFileName], r15
0x180004c7c  mov     edi, r15d
0x180004c7f  movups  xmmword ptr [rbp+100h+var_140.Length], xmm0
0x180004c83  mov     [rsp+200h+var_1A0], r15
0x180004c88  mov     r13d, r15d
0x180004c8b  mov     [rsp+200h+var_198], r15
0x180004c90  mov     esi, r15d
0x180004c93  mov     [rsp+200h+var_1C0], r15
0x180004c98  mov     r14d, r15d
0x180004c9b  mov     [rsp+200h+var_188], r15
0x180004ca0  mov     [rsp+200h+var_1B0], r15d
0x180004ca5  call    ?FilemapNameAndLeaf@@YAJPEAPEAGPEAU_UNICODE_STRING@@PEBG2@Z; FilemapNameAndLeaf(ushort * *,_UNICODE_STRING *,ushort const *,ushort const *)
0x180004caa  mov     ebx, eax
0x180004cac  test    eax, eax
0x180004cae  js      loc_180004EE9
0x180004cb4  mov     [rsp+200h+hTemplateFile], r15; hTemplateFile
0x180004cb9  lea     r8d, [r15+1]; dwShareMode
0x180004cbd  mov     r15, [rsp+200h+lpFileName]
0x180004cc2  xor     r9d, r9d; lpSecurityAttributes
0x180004cc5  mov     rcx, r15; lpFileName
0x180004cc8  mov     [rsp+200h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004cd0  mov     edx, 120089h; dwDesiredAccess
0x180004cd5  mov     [rsp+200h+dwCreationDisposition], 3; dwCreationDisposition
0x180004cdd  call    cs:__imp_CreateFileW
0x180004ce3  mov     [rbp+100h+hObject], rax
0x180004ce7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004ceb  jnz     short loc_180004D0B
0x180004ced  call    cs:__imp_GetLastError
0x180004cf3  mov     ebx, eax
0x180004cf5  test    eax, eax
0x180004cf7  jle     loc_180004EEE
0x180004cfd  movzx   ebx, ax
0x180004d00  or      ebx, 80070000h
0x180004d06  jmp     loc_180004EEE
0x180004d0b  xorps   xmm0, xmm0
0x180004d0e  lea     rdx, [rbp+100h+P]
0x180004d12  lea     rcx, [rbp+100h+var_180]
0x180004d16  movdqu  xmmword ptr [rbp+100h+P], xmm0
0x180004d1b  call    CdfInitializeContext
0x180004d20  mov     ebx, eax
0x180004d22  test    eax, eax
0x180004d24  jns     short loc_180004D2F
0x180004d26  bts     ebx, 1Ch
0x180004d2a  jmp     loc_180004EEE
0x180004d2f  lea     r8, [rbp+100h+var_160]
0x180004d33  lea     rdx, [rbp+100h+var_140]
0x180004d37  lea     rcx, [rbp+100h+P]
0x180004d3b  call    LuaCdfLookupFileEntry
0x180004d40  mov     ebx, eax
0x180004d42  test    eax, eax
0x180004d44  js      short loc_180004D26
0x180004d46  mov     rax, cs:?vpfnGetIdentityAuthority@@3P6AJPEAPEAUIIdentityAuthority@@@ZEA; long (*vpfnGetIdentityAuthority)(IIdentityAuthority * *)
0x180004d4d  lea     rcx, [rsp+200h+var_188]
0x180004d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d57  mov     ebx, eax
0x180004d59  test    eax, eax
0x180004d5b  js      loc_180004EEE
0x180004d61  mov     rcx, [rsp+200h+var_188]
0x180004d66  mov     rdx, r12
0x180004d69  mov     rax, [rcx]
0x180004d6c  mov     rax, [rax+98h]
0x180004d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d78  mov     ebx, eax
0x180004d7a  test    eax, eax
0x180004d7c  js      loc_180004EEE
0x180004d82  mov     r8d, [rbp+100h+var_148]
0x180004d86  cmp     r8d, 0FFFFFFFFh
0x180004d8a  jz      loc_180004EEE
0x180004d90  mov     rdx, [rbp+100h+P]
0x180004d94  lea     rax, [rsp+200h+var_1A8]
0x180004d99  mov     qword ptr [rsp+200h+dwFlagsAndAttributes], rax
0x180004d9e  mov     r9d, 14h
0x180004da4  lea     rax, [rbp+100h+var_130]
0x180004da8  mov     [rsp+200h+var_1A8], rsi
0x180004dad  mov     qword ptr [rsp+200h+dwCreationDisposition], rax
0x180004db2  call    CdfGetIdentityAttributes
0x180004db7  cmp     eax, 0C0000023h
0x180004dbc  jnz     short loc_180004E18
0x180004dbe  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180004dc5  mov     eax, 0Ch
0x180004dca  mul     [rsp+200h+var_1A8]
0x180004dcf  cmovb   rax, rcx
0x180004dd3  mov     rcx, rax; Size
0x180004dd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ddb  mov     r14, rax
0x180004dde  test    rax, rax
0x180004de1  jnz     short loc_180004DED
0x180004de3  mov     ebx, 8007000Eh
0x180004de8  jmp     loc_180004EEE
0x180004ded  mov     r9, [rsp+200h+var_1A8]
0x180004df2  lea     rax, [rsp+200h+var_1A8]
0x180004df7  mov     r8d, [rbp+100h+var_148]
0x180004dfb  mov     rdx, [rbp+100h+P]
0x180004dff  mov     qword ptr [rsp+200h+dwFlagsAndAttributes], rax
0x180004e04  mov     qword ptr [rsp+200h+dwCreationDisposition], r14
0x180004e09  mov     [rsp+200h+var_1B0], 1
0x180004e11  call    CdfGetIdentityAttributes
0x180004e16  jmp     short loc_180004E1C
0x180004e18  lea     r14, [rbp+100h+var_130]
0x180004e1c  test    eax, eax
0x180004e1e  jns     short loc_180004E27
0x180004e20  mov     ebx, eax
0x180004e22  jmp     loc_180004D26
0x180004e27  mov     r12, [rsp+200h+var_1A8]
0x180004e2c  test    r12, r12
0x180004e2f  jz      loc_180004FBD
0x180004e35  lea     r15, [rsi+rsi*2]
0x180004e39  cmp     dword ptr [r14+r15*4], 0FFFFFFFFh
0x180004e3e  jz      short loc_180004E63
0x180004e40  mov     edx, [r14+r15*4]
0x180004e44  lea     r8, [rsp+200h+var_1A0]
0x180004e49  mov     rcx, [rbp+100h+P]
0x180004e4d  call    ?GetCdfString@@YAJPEAU_CDF_CONTEXT@@U_CDF_STRINGID@@PEAPEAG@Z; GetCdfString(_CDF_CONTEXT *,_CDF_STRINGID,ushort * *)
0x180004e52  mov     rdi, [rsp+200h+var_1A0]
0x180004e57  mov     ebx, eax
0x180004e59  test    eax, eax
0x180004e5b  js      loc_180004EE4
0x180004e61  jmp     short loc_180004E78
0x180004e63  test    rdi, rdi
0x180004e66  jz      short loc_180004E78
0x180004e68  lea     rcx, [rdi-8]; Block
0x180004e6c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004e71  xor     edi, edi
0x180004e73  mov     [rsp+200h+var_1A0], rdi
0x180004e78  mov     edx, [r14+r15*4+4]
0x180004e7d  lea     r8, [rsp+200h+var_198]
0x180004e82  mov     rcx, [rbp+100h+P]
0x180004e86  call    ?GetCdfString@@YAJPEAU_CDF_CONTEXT@@U_CDF_STRINGID@@PEAPEAG@Z; GetCdfString(_CDF_CONTEXT *,_CDF_STRINGID,ushort * *)
0x180004e8b  mov     ebx, eax
0x180004e8d  test    eax, eax
0x180004e8f  js      loc_180004FB3
0x180004e95  mov     edx, [r14+r15*4+8]
0x180004e9a  lea     r8, [rsp+200h+var_1C0]
0x180004e9f  mov     rcx, [rbp+100h+P]
0x180004ea3  call    ?GetCdfString@@YAJPEAU_CDF_CONTEXT@@U_CDF_STRINGID@@PEAPEAG@Z; GetCdfString(_CDF_CONTEXT *,_CDF_STRINGID,ushort * *)
0x180004ea8  mov     r13, [rsp+200h+var_198]
0x180004ead  mov     ebx, eax
0x180004eaf  test    eax, eax
0x180004eb1  js      short loc_180004EE4
0x180004eb3  mov     rax, [rsp+200h+var_190]
0x180004eb8  mov     r8, r13
0x180004ebb  mov     r9, [rsp+200h+var_1C0]
0x180004ec0  mov     rdx, rdi
0x180004ec3  mov     rcx, [rax]
0x180004ec6  mov     rax, [rcx]
0x180004ec9  mov     rax, [rax+20h]
0x180004ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed2  mov     ebx, eax
0x180004ed4  test    eax, eax
0x180004ed6  js      short loc_180004EE4
0x180004ed8  inc     rsi
0x180004edb  cmp     rsi, r12
0x180004ede  jb      loc_180004E35
0x180004ee4  mov     rsi, [rsp+200h+var_1C0]
0x180004ee9  mov     r15, [rsp+200h+lpFileName]
0x180004eee  mov     rcx, [rbp+100h+P]
0x180004ef2  test    rcx, rcx
0x180004ef5  jz      short loc_180004EFC
0x180004ef7  call    CdfFreeContext
0x180004efc  mov     r8, [rbp+100h+P+8]; P
0x180004f00  test    r8, r8
0x180004f03  jz      short loc_180004F1A
0x180004f05  mov     rcx, gs:60h
0x180004f0e  xor     edx, edx; Flags
0x180004f10  mov     rcx, [rcx+30h]; HeapHandle
0x180004f14  call    cs:__imp_RtlFreeHeap
0x180004f1a  mov     rcx, [rbp+100h+hObject]; hObject
0x180004f1e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004f22  jz      short loc_180004F2A
0x180004f24  call    cs:__imp_CloseHandle
0x180004f2a  mov     rcx, [rsp+200h+var_188]
0x180004f2f  test    rcx, rcx
0x180004f32  jz      short loc_180004F40
0x180004f34  mov     rax, [rcx]
0x180004f37  mov     rax, [rax+10h]
0x180004f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f40  test    r15, r15
0x180004f43  jz      short loc_180004F4E
0x180004f45  lea     rcx, [r15-8]; Block
0x180004f49  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004f4e  test    rdi, rdi
0x180004f51  jz      short loc_180004F5C
0x180004f53  lea     rcx, [rdi-8]; Block
0x180004f57  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004f5c  test    rsi, rsi
0x180004f5f  jz      short loc_180004F6A
0x180004f61  lea     rcx, [rsi-8]; Block
0x180004f65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004f6a  test    r13, r13
0x180004f6d  jz      short loc_180004F78
0x180004f6f  lea     rcx, [r13-8]; Block
0x180004f73  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004f78  cmp     [rsp+200h+var_1B0], 0
0x180004f7d  jz      short loc_180004F87
0x180004f7f  mov     rcx, r14; Block
0x180004f82  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f87  mov     eax, ebx
0x180004f89  mov     rcx, [rbp+100h+var_40]
0x180004f90  xor     rcx, rsp; StackCookie
0x180004f93  call    __security_check_cookie
0x180004f98  mov     rbx, [rsp+200h+arg_18]
0x180004fa0  add     rsp, 1D0h
0x180004fa7  pop     r15
0x180004fa9  pop     r14
0x180004fab  pop     r13
0x180004fad  pop     r12
0x180004faf  pop     rdi
0x180004fb0  pop     rsi
0x180004fb1  pop     rbp
0x180004fb2  retn
0x180004fb3  mov     r13, [rsp+200h+var_198]
0x180004fb8  jmp     loc_180004EE4
0x180004fbd  mov     rsi, [rsp+200h+var_1C0]
0x180004fc2  jmp     loc_180004EEE
```
