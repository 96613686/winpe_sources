# IsBinaryFileContainManifestInResource(ushort const *,bool &)

- ea: `0x18005533c`
- end: `0x1800554bd`
- name: `?IsBinaryFileContainManifestInResource@@YAHPEBGAEA_N@Z`
- size: `385`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000bc20`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18005533c`
- `0x1800554c4`
- `0x180055538`
- `0x180055574`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055416`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800553af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800553f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800553af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800553f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055440`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800553ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800553ca`

## pseudocode

```c
__int64 __fastcall IsBinaryFileContainManifestInResource(const unsigned __int16 *a1, bool *a2)
{
  CResourceStream *v4; // rax
  bool v5; // bl
  const unsigned __int16 *v6; // r8
  DWORD LastError; // eax
  __int64 i; // rdx
  char **v9; // rcx
  unsigned int v10; // ebx
  CResourceStream *v12; // [rsp+20h] [rbp-50h] BYREF
  char v13; // [rsp+28h] [rbp-48h]
  int v14; // [rsp+30h] [rbp-40h] BYREF
  int v15; // [rsp+38h] [rbp-38h] BYREF
  __int64 v16; // [rsp+40h] [rbp-30h]
  __int64 *v17; // [rsp+48h] [rbp-28h]
  __int64 v18; // [rsp+50h] [rbp-20h]
  int v19; // [rsp+58h] [rbp-18h]
  unsigned int *v20; // [rsp+60h] [rbp-10h]

  v14 = 0;
  v17 = &qword_180072570;
  v15 = 1;
  v20 = (unsigned int *)&v14;
  v16 = 0;
  v18 = 544438355;
  v19 = 40;
  CFrame::BaseEnter((CFrame *)&v15);
  *a2 = 0;
  v13 = 0;
  SetLastError(0);
  v4 = (CResourceStream *)HeapAlloc(g_hHeap, 0, 0x260u);
  if ( !v4 )
  {
    v12 = 0;
    goto LABEL_13;
  }
  v12 = CResourceStream::CResourceStream(v4);
  if ( !v12 )
  {
LABEL_13:
    v9 = off_180072550;
    *v20 = 0;
    goto LABEL_14;
  }
  v13 = 1;
  SetLastError(0);
  v5 = 1;
  if ( !(unsigned int)CResourceStream::Initialize(v12, a1, v6) )
  {
    LastError = GetLastError();
    for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
    {
      if ( LastError == *((_DWORD *)&qword_180087C90 + i) )
      {
        v5 = 0;
        goto LABEL_9;
      }
    }
    if ( (_DWORD)i == 2 )
    {
      v9 = off_1800789E8;
LABEL_14:
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v9);
      goto LABEL_15;
    }
  }
LABEL_9:
  *a2 = v5;
  SetLastError(0);
  *v20 = 1;
LABEL_15:
  v10 = *v20;
  CSmartPtr<CResourceStream,CSmartPtrBaseTypeHelper<CResourceStream>>::~CSmartPtr<CResourceStream,CSmartPtrBaseTypeHelper<CResourceStream>>(&v12);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v15);
  return v10;
}

```

## disassembly

```asm
0x18005533c  mov     [rsp-18h+arg_10], rbx
0x180055341  mov     [rsp-18h+arg_18], rsi
0x180055346  push    rbp
0x180055347  push    rdi
0x180055348  push    r14
0x18005534a  mov     rbp, rsp
0x18005534d  sub     rsp, 70h
0x180055351  mov     rax, cs:__security_cookie
0x180055358  xor     rax, rsp
0x18005535b  mov     [rbp+var_8], rax
0x18005535f  lea     rax, qword_180072570
0x180055366  mov     [rbp+var_40], 0
0x18005536d  mov     [rbp+var_28], rax
0x180055371  mov     r14, rcx
0x180055374  lea     rax, [rbp+var_40]
0x180055378  mov     [rbp+var_38], 1
0x18005537f  lea     rcx, [rbp+var_38]; this
0x180055383  mov     [rbp+var_10], rax
0x180055387  mov     rsi, rdx
0x18005538a  mov     [rbp+var_30], 0
0x180055392  mov     [rbp+var_20], 20737853h
0x18005539a  mov     [rbp+var_18], 28h ; '('
0x1800553a1  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800553a6  xor     ecx, ecx; dwErrCode
0x1800553a8  mov     byte ptr [rsi], 0
0x1800553ab  mov     [rbp+var_48], 0
0x1800553af  call    cs:__imp_SetLastError
0x1800553b6  nop     dword ptr [rax+rax+00h]
0x1800553bb  mov     rcx, cs:g_hHeap; hHeap
0x1800553c2  xor     edx, edx; dwFlags
0x1800553c4  mov     r8d, 260h; dwBytes
0x1800553ca  call    cs:__imp_HeapAlloc
0x1800553d1  nop     dword ptr [rax+rax+00h]
0x1800553d6  test    rax, rax
0x1800553d9  jz      loc_180055463
0x1800553df  mov     rcx, rax; this
0x1800553e2  call    ??0CResourceStream@@QEAA@XZ; CResourceStream::CResourceStream(void)
0x1800553e7  mov     [rbp+var_50], rax
0x1800553eb  mov     rdi, rax
0x1800553ee  test    rax, rax
0x1800553f1  jz      short loc_18005546B
0x1800553f3  mov     [rbp+var_48], 1
0x1800553f7  xor     ecx, ecx; dwErrCode
0x1800553f9  call    cs:__imp_SetLastError
0x180055400  nop     dword ptr [rax+rax+00h]
0x180055405  mov     rdx, r14; unsigned __int16 *
0x180055408  mov     rcx, rdi; this
0x18005540b  mov     bl, 1
0x18005540d  call    ?Initialize@CResourceStream@@QEAAHPEBG0@Z; CResourceStream::Initialize(ushort const *,ushort const *)
0x180055412  test    eax, eax
0x180055414  jnz     short loc_18005543C
0x180055416  call    cs:__imp_GetLastError
0x18005541d  nop     dword ptr [rax+rax+00h]
0x180055422  xor     edx, edx
0x180055424  cmp     edx, 2
0x180055427  jnb     short loc_180055458
0x180055429  lea     r8, qword_180087C90
0x180055430  cmp     eax, [r8+rdx*4]
0x180055434  jz      short loc_18005543A
0x180055436  inc     edx
0x180055438  jmp     short loc_180055424
0x18005543a  xor     bl, bl
0x18005543c  xor     ecx, ecx; dwErrCode
0x18005543e  mov     [rsi], bl
0x180055440  call    cs:__imp_SetLastError
0x180055447  nop     dword ptr [rax+rax+00h]
0x18005544c  mov     rax, [rbp+var_10]
0x180055450  mov     dword ptr [rax], 1
0x180055456  jmp     short loc_180055481
0x180055458  jnz     short loc_18005543C
0x18005545a  lea     rcx, off_1800789E8; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x180055461  jmp     short loc_18005547C
0x180055463  mov     [rbp+var_50], 0
0x18005546b  mov     rax, [rbp+var_10]
0x18005546f  lea     rcx, off_180072550; struct _CALL_SITE_INFO *
0x180055476  mov     dword ptr [rax], 0
0x18005547c  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180055481  mov     rax, [rbp+var_10]
0x180055485  lea     rcx, [rbp+var_50]
0x180055489  mov     ebx, [rax]
0x18005548b  call    ??1?$CSmartPtr@VCResourceStream@@V?$CSmartPtrBaseTypeHelper@VCResourceStream@@@@@@QEAA@XZ; CSmartPtr<CResourceStream,CSmartPtrBaseTypeHelper<CResourceStream>>::~CSmartPtr<CResourceStream,CSmartPtrBaseTypeHelper<CResourceStream>>(void)
0x180055490  lea     rcx, [rbp+var_38]; this
0x180055494  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180055499  mov     eax, ebx
0x18005549b  mov     rcx, [rbp+var_8]
0x18005549f  xor     rcx, rsp; StackCookie
0x1800554a2  call    __security_check_cookie
0x1800554a7  lea     r11, [rsp+70h+var_s0]
0x1800554ac  mov     rbx, [r11+30h]
0x1800554b0  mov     rsi, [r11+38h]
0x1800554b4  mov     rsp, r11
0x1800554b7  pop     r14
0x1800554b9  pop     rdi
0x1800554ba  pop     rbp
0x1800554bb  retn
```
