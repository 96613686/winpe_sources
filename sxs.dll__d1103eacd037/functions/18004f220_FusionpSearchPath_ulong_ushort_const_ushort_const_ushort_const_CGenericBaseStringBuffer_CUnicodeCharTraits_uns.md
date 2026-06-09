# FusionpSearchPath(ulong,ushort const *,ushort const *,ushort const *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,unsigned __int64 *,void *)

- ea: `0x18004f220`
- end: `0x18004f41f`
- name: `?FusionpSearchPath@@YAHKPEBG00AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEA_KPEAX@Z`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18005c304`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180023260`
- `0x18002def0`
- `0x180030480`
- `0x18004f220`
- `0x180050428`
- `0x180053a04`
- `0x18005d620`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f2ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f2ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f327`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f37b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f3a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f2ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f2ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f327`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f37b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f3a9`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18004f358`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18004f358`

## pseudocode

```c
__int64 __fastcall FusionpSearchPath(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        void *a7)
{
  char **v8; // rcx
  DWORD v9; // r9d
  DWORD v10; // eax
  DWORD v11; // ebx
  unsigned int v12; // ebx
  _BYTE v14[8]; // [rsp+30h] [rbp-41h] BYREF
  LPWSTR lpBuffer; // [rsp+38h] [rbp-39h]
  unsigned __int64 v16; // [rsp+40h] [rbp-31h]
  LPWSTR FilePart; // [rsp+48h] [rbp-29h] BYREF
  int v18; // [rsp+50h] [rbp-21h] BYREF
  int v19; // [rsp+58h] [rbp-19h] BYREF
  __int64 v20; // [rsp+60h] [rbp-11h]
  __int64 *v21; // [rsp+68h] [rbp-9h]
  __int64 v22; // [rsp+70h] [rbp-1h]
  int v23; // [rsp+78h] [rbp+7h]
  unsigned int *v24; // [rsp+80h] [rbp+Fh]
  _DWORD v25[4]; // [rsp+88h] [rbp+17h] BYREF

  v21 = &qword_1800720C0;
  v18 = 0;
  v24 = (unsigned int *)&v18;
  v19 = 1;
  v20 = 0;
  v22 = 544438355;
  v23 = 358;
  CFrame::BaseEnter((CFrame *)&v19);
  FilePart = 0;
  v25[0] = 0;
  CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(a5);
  SetLastError(0);
  if ( !(unsigned int)CFusionActCtxScope::Win32Activate((CFusionActCtxScope *)v25, a7) )
  {
    v8 = off_18007C920;
LABEL_3:
    *v24 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v8);
    goto LABEL_15;
  }
  if ( !*(_QWORD *)(a5 + 24) )
  {
    SetLastError(0);
    if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(a5, 260) )
    {
      v8 = off_1800720A0;
      goto LABEL_3;
    }
  }
  while ( 1 )
  {
    CGenericStringBufferAccessor<CUnicodeCharTraits>::CGenericStringBufferAccessor<CUnicodeCharTraits>(v14, a5);
    SetLastError(0);
    v9 = v16;
    if ( v16 > 0xFFFFFFFF )
      v9 = -1;
    v10 = SearchPathW(0, a3, 0, v9, lpBuffer, &FilePart);
    v11 = v10;
    if ( !v10 )
      break;
    if ( (unsigned __int64)v10 < *(_QWORD *)(a5 + 24) )
    {
      CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(v14);
      SetLastError(0);
      *v24 = 1;
      goto LABEL_15;
    }
    CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(v14);
    SetLastError(0);
    if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(a5, v11 + 1) )
    {
      v8 = off_18007C880;
      goto LABEL_3;
    }
  }
  *v24 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007C8E0);
  CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(v14);
LABEL_15:
  v12 = *v24;
  CFusionActCtxScope::~CFusionActCtxScope((CFusionActCtxScope *)v25);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v19);
  return v12;
}

```

## disassembly

```asm
0x18004f220  mov     [rsp-8+arg_0], rbx
0x18004f225  mov     [rsp-8+arg_8], rsi
0x18004f22a  push    rbp
0x18004f22b  push    rdi
0x18004f22c  push    r12
0x18004f22e  lea     rbp, [rsp-2Fh]
0x18004f233  sub     rsp, 0A0h
0x18004f23a  mov     rax, cs:__security_cookie
0x18004f241  xor     rax, rsp
0x18004f244  mov     [rbp+3Fh+var_18], rax
0x18004f248  mov     rdi, [rbp+3Fh+arg_20]
0x18004f24c  lea     rax, qword_1800720C0
0x18004f253  mov     rbx, [rbp+3Fh+arg_30]
0x18004f257  lea     rcx, [rbp+3Fh+var_58]; this
0x18004f25b  mov     [rbp+3Fh+var_48], rax
0x18004f25f  mov     rsi, r8
0x18004f262  lea     rax, [rbp+3Fh+var_60]
0x18004f266  mov     [rbp+3Fh+var_60], 0
0x18004f26d  mov     [rbp+3Fh+var_30], rax
0x18004f271  mov     [rbp+3Fh+var_58], 1
0x18004f278  mov     [rbp+3Fh+var_50], 0
0x18004f280  mov     [rbp+3Fh+var_40], 20737853h
0x18004f288  mov     [rbp+3Fh+var_38], 166h
0x18004f28f  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004f294  mov     rcx, rdi
0x18004f297  mov     [rbp+3Fh+FilePart], 0
0x18004f29f  mov     [rbp+3Fh+var_28], 0
0x18004f2a6  call    ?Clear@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAX_N@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(bool)
0x18004f2ab  xor     ecx, ecx; dwErrCode
0x18004f2ad  call    cs:__imp_SetLastError
0x18004f2b4  nop     dword ptr [rax+rax+00h]
0x18004f2b9  mov     rdx, rbx; void *
0x18004f2bc  lea     rcx, [rbp+3Fh+var_28]; this
0x18004f2c0  call    ?Win32Activate@CFusionActCtxScope@@QEAAHPEAX@Z; CFusionActCtxScope::Win32Activate(void *)
0x18004f2c5  test    eax, eax
0x18004f2c7  jnz     short loc_18004F2E4
0x18004f2c9  lea     rcx, off_18007C920; struct _CALL_SITE_INFO *
0x18004f2d0  mov     rax, [rbp+3Fh+var_30]
0x18004f2d4  mov     dword ptr [rax], 0
0x18004f2da  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004f2df  jmp     loc_18004F3E0
0x18004f2e4  cmp     qword ptr [rdi+18h], 0
0x18004f2e9  jnz     short loc_18004F313
0x18004f2eb  xor     ecx, ecx; dwErrCode
0x18004f2ed  call    cs:__imp_SetLastError
0x18004f2f4  nop     dword ptr [rax+rax+00h]
0x18004f2f9  mov     edx, 104h
0x18004f2fe  mov     rcx, rdi
0x18004f301  call    ?Win32ResizeBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAH_KW4EPreserveContents@@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(unsigned __int64,EPreserveContents)
0x18004f306  test    eax, eax
0x18004f308  jnz     short loc_18004F313
0x18004f30a  lea     rcx, off_1800720A0; "clientcore\\base\\win32\\fusion\\utils"...
0x18004f311  jmp     short loc_18004F2D0
0x18004f313  mov     r12d, 0FFFFFFFFh
0x18004f319  mov     rdx, rdi
0x18004f31c  lea     rcx, [rbp+3Fh+var_80]
0x18004f320  call    ??0?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAA@PEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CGenericStringBufferAccessor<CUnicodeCharTraits>::CGenericStringBufferAccessor<CUnicodeCharTraits>(CGenericBaseStringBuffer<CUnicodeCharTraits> *)
0x18004f325  xor     ecx, ecx; dwErrCode
0x18004f327  call    cs:__imp_SetLastError
0x18004f32e  nop     dword ptr [rax+rax+00h]
0x18004f333  mov     r9, [rbp+3Fh+var_70]
0x18004f337  lea     rcx, [rbp+3Fh+FilePart]
0x18004f33b  mov     rax, [rbp+3Fh+var_78]
0x18004f33f  cmp     r9, r12
0x18004f342  mov     [rsp+0B0h+lpFilePart], rcx; lpFilePart
0x18004f347  mov     rdx, rsi; lpFileName
0x18004f34a  cmova   r9d, r12d; nBufferLength
0x18004f34e  mov     [rsp+0B0h+lpBuffer], rax; lpBuffer
0x18004f353  xor     r8d, r8d; lpExtension
0x18004f356  xor     ecx, ecx; lpPath
0x18004f358  call    cs:__imp_SearchPathW
0x18004f35f  nop     dword ptr [rax+rax+00h]
0x18004f364  mov     ebx, eax
0x18004f366  test    eax, eax
0x18004f368  jz      short loc_18004F3C1
0x18004f36a  lea     rcx, [rbp+3Fh+var_80]
0x18004f36e  cmp     rbx, [rdi+18h]
0x18004f372  jb      short loc_18004F3A2
0x18004f374  call    ??1?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(void)
0x18004f379  xor     ecx, ecx; dwErrCode
0x18004f37b  call    cs:__imp_SetLastError
0x18004f382  nop     dword ptr [rax+rax+00h]
0x18004f387  lea     edx, [rbx+1]
0x18004f38a  mov     rcx, rdi
0x18004f38d  call    ?Win32ResizeBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAH_KW4EPreserveContents@@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(unsigned __int64,EPreserveContents)
0x18004f392  test    eax, eax
0x18004f394  jnz     short loc_18004F319
0x18004f396  lea     rcx, off_18007C880; "clientcore\\base\\win32\\fusion\\utils"...
0x18004f39d  jmp     loc_18004F2D0
0x18004f3a2  call    ??1?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(void)
0x18004f3a7  xor     ecx, ecx; dwErrCode
0x18004f3a9  call    cs:__imp_SetLastError
0x18004f3b0  nop     dword ptr [rax+rax+00h]
0x18004f3b5  mov     rax, [rbp+3Fh+var_30]
0x18004f3b9  mov     dword ptr [rax], 1
0x18004f3bf  jmp     short loc_18004F3E0
0x18004f3c1  mov     rax, [rbp+3Fh+var_30]
0x18004f3c5  lea     rcx, off_18007C8E0; struct _CALL_SITE_INFO *
0x18004f3cc  mov     dword ptr [rax], 0
0x18004f3d2  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004f3d7  lea     rcx, [rbp+3Fh+var_80]
0x18004f3db  call    ??1?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(void)
0x18004f3e0  mov     rax, [rbp+3Fh+var_30]
0x18004f3e4  lea     rcx, [rbp+3Fh+var_28]; this
0x18004f3e8  mov     ebx, [rax]
0x18004f3ea  call    ??1CFusionActCtxScope@@QEAA@XZ; CFusionActCtxScope::~CFusionActCtxScope(void)
0x18004f3ef  lea     rcx, [rbp+3Fh+var_58]; this
0x18004f3f3  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18004f3f8  mov     eax, ebx
0x18004f3fa  mov     rcx, [rbp+3Fh+var_18]
0x18004f3fe  xor     rcx, rsp; StackCookie
0x18004f401  call    __security_check_cookie
0x18004f406  lea     r11, [rsp+0B0h+var_10]
0x18004f40e  mov     rbx, [r11+20h]
0x18004f412  mov     rsi, [r11+28h]
0x18004f416  mov     rsp, r11
0x18004f419  pop     r12
0x18004f41b  pop     rdi
0x18004f41c  pop     rbp
0x18004f41d  retn
```
