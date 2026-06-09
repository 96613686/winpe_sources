# SxspDeleteDirectory(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)

- ea: `0x1800683a4`
- end: `0x180068508`
- name: `?SxspDeleteDirectory@@YAHAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z`
- size: `356`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18005db38`
- `0x180063a20`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180014260`
- `0x18001c270`
- `0x180029380`
- `0x180033b50`
- `0x180060e14`
- `0x1800683a4`
- `0x180068510`
- `0x18006a0f5`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006843f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068477`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800684c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006843f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068477`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800684c1`

## pseudocode

```c
__int64 __fastcall SxspDeleteDirectory(__int64 a1)
{
  char **v2; // rcx
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-E0h] BYREF
  DWORD v6; // [rsp+24h] [rbp-DCh] BYREF
  int v7; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v8; // [rsp+30h] [rbp-D0h]
  __int64 *v9; // [rsp+38h] [rbp-C8h]
  __int64 v10; // [rsp+40h] [rbp-C0h]
  int v11; // [rsp+48h] [rbp-B8h]
  int *v12; // [rsp+50h] [rbp-B0h]
  _BYTE v13[560]; // [rsp+60h] [rbp-A0h] BYREF
  struct _WIN32_FIND_DATAW v14; // [rsp+290h] [rbp+190h] BYREF

  v5 = 0;
  v9 = &qword_18007CB80;
  v7 = 1;
  v12 = &v5;
  v8 = 0;
  v10 = 544438355;
  v11 = 369;
  CFrame::BaseEnter((CFrame *)&v7);
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v13);
  memset_0(&v14, 0, sizeof(v14));
  v6 = 0;
  SetLastError(0);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v13, a1) )
  {
    v2 = off_18007CB40;
LABEL_3:
    *v12 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v2);
    goto LABEL_8;
  }
  SetLastError(0);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveTrailingPathSeparators(v13) )
  {
    v2 = off_18007CAA0;
    goto LABEL_3;
  }
  SxspDeleteDirectoryHelper((__int64)v13, &v14, &v6);
  if ( !v6 )
  {
    v5 = 1;
    SetLastError(0);
  }
LABEL_8:
  v3 = v5;
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v13);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v7);
  return v3;
}

```

## disassembly

```asm
0x1800683a4  mov     [rsp-8+arg_8], rbx
0x1800683a9  push    rbp
0x1800683aa  lea     rbp, [rsp-3F0h]
0x1800683b2  sub     rsp, 4F0h
0x1800683b9  mov     rax, cs:__security_cookie
0x1800683c0  xor     rax, rsp
0x1800683c3  mov     [rbp+3F0h+var_10], rax
0x1800683ca  lea     rax, qword_18007CB80
0x1800683d1  mov     [rsp+4F0h+var_4D0], 0
0x1800683d9  mov     [rsp+4F0h+var_4B8], rax
0x1800683de  mov     rbx, rcx
0x1800683e1  lea     rax, [rsp+4F0h+var_4D0]
0x1800683e6  mov     [rsp+4F0h+var_4C8], 1
0x1800683ee  lea     rcx, [rsp+4F0h+var_4C8]; this
0x1800683f3  mov     [rsp+4F0h+var_4A0], rax
0x1800683f8  mov     [rsp+4F0h+var_4C0], 0
0x180068401  mov     [rsp+4F0h+var_4B0], 20737853h
0x18006840a  mov     [rsp+4F0h+var_4A8], 171h
0x180068412  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180068417  lea     rcx, [rsp+4F0h+var_490]; void *
0x18006841c  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180068421  xor     edx, edx; Val
0x180068423  lea     rcx, [rbp+3F0h+var_260]; void *
0x18006842a  mov     r8d, 250h; Size
0x180068430  call    memset_0
0x180068435  xor     ecx, ecx; dwErrCode
0x180068437  mov     [rsp+4F0h+var_4CC], 0
0x18006843f  call    cs:__imp_SetLastError
0x180068446  nop     dword ptr [rax+rax+00h]
0x18006844b  mov     rdx, rbx
0x18006844e  lea     rcx, [rsp+4F0h+var_490]
0x180068453  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEBV1@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x180068458  test    eax, eax
0x18006845a  jnz     short loc_180068475
0x18006845c  lea     rcx, off_18007CB40; struct _CALL_SITE_INFO *
0x180068463  mov     rax, [rsp+4F0h+var_4A0]
0x180068468  mov     dword ptr [rax], 0
0x18006846e  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180068473  jmp     short loc_1800684CD
0x180068475  xor     ecx, ecx; dwErrCode
0x180068477  call    cs:__imp_SetLastError
0x18006847e  nop     dword ptr [rax+rax+00h]
0x180068483  lea     rcx, [rsp+4F0h+var_490]
0x180068488  call    ?Win32RemoveTrailingPathSeparators@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveTrailingPathSeparators(void)
0x18006848d  test    eax, eax
0x18006848f  jnz     short loc_18006849A
0x180068491  lea     rcx, off_18007CAA0; "clientcore\\base\\win32\\fusion\\utils"...
0x180068498  jmp     short loc_180068463
0x18006849a  lea     r8, [rsp+4F0h+var_4CC]
0x18006849f  lea     rdx, [rbp+3F0h+var_260]
0x1800684a6  lea     rcx, [rsp+4F0h+var_490]
0x1800684ab  call    SxspDeleteDirectoryHelper
0x1800684b0  cmp     [rsp+4F0h+var_4CC], 0
0x1800684b5  jnz     short loc_1800684CD
0x1800684b7  xor     ecx, ecx; dwErrCode
0x1800684b9  mov     [rsp+4F0h+var_4D0], 1
0x1800684c1  call    cs:__imp_SetLastError
0x1800684c8  nop     dword ptr [rax+rax+00h]
0x1800684cd  mov     ebx, [rsp+4F0h+var_4D0]
0x1800684d1  lea     rcx, [rsp+4F0h+var_490]; void *
0x1800684d6  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x1800684db  lea     rcx, [rsp+4F0h+var_4C8]; this
0x1800684e0  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x1800684e5  mov     eax, ebx
0x1800684e7  mov     rcx, [rbp+3F0h+var_10]
0x1800684ee  xor     rcx, rsp; StackCookie
0x1800684f1  call    __security_check_cookie
0x1800684f6  mov     rbx, [rsp+4F0h+arg_8]
0x1800684fe  add     rsp, 4F0h
0x180068505  pop     rbp
0x180068506  retn
```
