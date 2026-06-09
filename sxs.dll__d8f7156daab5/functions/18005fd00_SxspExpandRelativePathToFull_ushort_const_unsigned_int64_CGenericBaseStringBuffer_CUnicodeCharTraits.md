# SxspExpandRelativePathToFull(ushort const *,unsigned __int64,CGenericBaseStringBuffer<CUnicodeCharTraits> &)

- ea: `0x18005fd00`
- end: `0x18005fea4`
- name: `?SxspExpandRelativePathToFull@@YAHPEBG_KAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18005ea40`
- `0x18005f1f0`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18002d630`
- `0x18002de34`
- `0x18002def0`
- `0x180030480`
- `0x18005fd00`
- `0x180067700`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fd85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fdcf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fe0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fe54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fd85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fdcf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fe0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fe54`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005fd9e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005fe28`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005fd9e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005fe28`

## pseudocode

```c
__int64 __fastcall SxspExpandRelativePathToFull(LPCWSTR lpFileName, __int64 a2, __int64 a3)
{
  DWORD FullPathNameW; // eax
  const char *v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  unsigned int v9; // ebx
  LPWSTR lpBuffer[2]; // [rsp+20h] [rbp-60h] BYREF
  DWORD nBufferLength[2]; // [rsp+30h] [rbp-50h]
  int v13; // [rsp+38h] [rbp-48h] BYREF
  int v14; // [rsp+40h] [rbp-40h] BYREF
  __int64 v15; // [rsp+48h] [rbp-38h]
  __int64 *v16; // [rsp+50h] [rbp-30h]
  __int64 v17; // [rsp+58h] [rbp-28h]
  int v18; // [rsp+60h] [rbp-20h]
  unsigned int *v19; // [rsp+68h] [rbp-18h]

  v13 = 0;
  v16 = &qword_180075090;
  *(_QWORD *)nBufferLength = 0;
  v19 = (unsigned int *)&v13;
  v14 = 1;
  v15 = 0;
  *(_OWORD *)lpBuffer = 0;
  v17 = 544438355;
  v18 = 3992;
  CFrame::BaseEnter((CFrame *)&v14);
  CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(lpBuffer, a3);
  SetLastError(0);
  FullPathNameW = GetFullPathNameW(lpFileName, nBufferLength[0], lpBuffer[1], 0);
  if ( !FullPathNameW )
    goto LABEL_2;
  v7 = FullPathNameW;
  if ( (unsigned __int64)FullPathNameW <= *(_QWORD *)nBufferLength )
  {
LABEL_9:
    SetLastError(0);
    *v19 = 1;
    goto LABEL_10;
  }
  CGenericStringBufferAccessor<CUnicodeCharTraits>::Detach(lpBuffer);
  SetLastError(0);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(a3, v7) )
  {
    *v19 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075070);
    goto LABEL_10;
  }
  CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(lpBuffer, a3);
  SetLastError(0);
  v8 = GetFullPathNameW(lpFileName, nBufferLength[0], lpBuffer[1], 0);
  if ( v8 )
  {
    if ( (unsigned __int64)v8 > *(_QWORD *)nBufferLength )
    {
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180075050);
      goto LABEL_10;
    }
    goto LABEL_9;
  }
LABEL_2:
  FusionpTraceNull(v6);
LABEL_10:
  v9 = *v19;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v14);
  CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(lpBuffer);
  return v9;
}

```

## disassembly

```asm
0x18005fd00  mov     [rsp-18h+arg_8], rbx
0x18005fd05  push    rbp
0x18005fd06  push    rsi
0x18005fd07  push    rdi
0x18005fd08  mov     rbp, rsp
0x18005fd0b  sub     rsp, 80h
0x18005fd12  mov     rax, cs:__security_cookie
0x18005fd19  xor     rax, rsp
0x18005fd1c  mov     [rbp+var_10], rax
0x18005fd20  lea     rax, qword_180075090
0x18005fd27  mov     [rbp+var_48], 0
0x18005fd2e  mov     [rbp+var_30], rax
0x18005fd32  mov     rsi, rcx
0x18005fd35  lea     rax, [rbp+var_48]
0x18005fd39  mov     qword ptr [rbp+nBufferLength], 0
0x18005fd41  xorps   xmm0, xmm0
0x18005fd44  mov     [rbp+var_18], rax
0x18005fd48  lea     rcx, [rbp+var_40]; this
0x18005fd4c  mov     [rbp+var_40], 1
0x18005fd53  mov     rdi, r8
0x18005fd56  mov     [rbp+var_38], 0
0x18005fd5e  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x18005fd63  mov     [rbp+var_28], 20737853h
0x18005fd6b  mov     [rbp+var_20], 0F98h
0x18005fd72  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005fd77  mov     rdx, rdi
0x18005fd7a  lea     rcx, [rbp+lpBuffer]
0x18005fd7e  call    ?Attach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXPEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(CGenericBaseStringBuffer<CUnicodeCharTraits> *)
0x18005fd83  xor     ecx, ecx; dwErrCode
0x18005fd85  call    cs:__imp_SetLastError
0x18005fd8c  nop     dword ptr [rax+rax+00h]
0x18005fd91  mov     r8, [rbp+lpBuffer+8]; lpBuffer
0x18005fd95  xor     r9d, r9d; lpFilePart
0x18005fd98  mov     edx, [rbp+nBufferLength]; nBufferLength
0x18005fd9b  mov     rcx, rsi; lpFileName
0x18005fd9e  call    cs:__imp_GetFullPathNameW
0x18005fda5  nop     dword ptr [rax+rax+00h]
0x18005fdaa  test    eax, eax
0x18005fdac  jnz     short loc_18005FDB8
0x18005fdae  call    ?FusionpTraceNull@@YAXPEBD@Z; FusionpTraceNull(char const *)
0x18005fdb3  jmp     loc_18005FE6A
0x18005fdb8  mov     ebx, eax
0x18005fdba  cmp     rbx, qword ptr [rbp+nBufferLength]
0x18005fdbe  jbe     loc_18005FE52
0x18005fdc4  lea     rcx, [rbp+lpBuffer]
0x18005fdc8  call    ?Detach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXXZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::Detach(void)
0x18005fdcd  xor     ecx, ecx; dwErrCode
0x18005fdcf  call    cs:__imp_SetLastError
0x18005fdd6  nop     dword ptr [rax+rax+00h]
0x18005fddb  mov     edx, ebx
0x18005fddd  mov     rcx, rdi
0x18005fde0  call    ?Win32ResizeBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAH_KW4EPreserveContents@@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(unsigned __int64,EPreserveContents)
0x18005fde5  test    eax, eax
0x18005fde7  jnz     short loc_18005FE01
0x18005fde9  mov     rax, [rbp+var_18]
0x18005fded  lea     rcx, off_180075070; struct _CALL_SITE_INFO *
0x18005fdf4  mov     dword ptr [rax], 0
0x18005fdfa  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005fdff  jmp     short loc_18005FE6A
0x18005fe01  mov     rdx, rdi
0x18005fe04  lea     rcx, [rbp+lpBuffer]
0x18005fe08  call    ?Attach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXPEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(CGenericBaseStringBuffer<CUnicodeCharTraits> *)
0x18005fe0d  xor     ecx, ecx; dwErrCode
0x18005fe0f  call    cs:__imp_SetLastError
0x18005fe16  nop     dword ptr [rax+rax+00h]
0x18005fe1b  mov     r8, [rbp+lpBuffer+8]; lpBuffer
0x18005fe1f  xor     r9d, r9d; lpFilePart
0x18005fe22  mov     edx, [rbp+nBufferLength]; nBufferLength
0x18005fe25  mov     rcx, rsi; lpFileName
0x18005fe28  call    cs:__imp_GetFullPathNameW
0x18005fe2f  nop     dword ptr [rax+rax+00h]
0x18005fe34  test    eax, eax
0x18005fe36  jz      loc_18005FDAE
0x18005fe3c  mov     eax, eax
0x18005fe3e  cmp     rax, qword ptr [rbp+nBufferLength]
0x18005fe42  jbe     short loc_18005FE52
0x18005fe44  lea     rcx, off_180075050; struct _CALL_SITE_INFO *
0x18005fe4b  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18005fe50  jmp     short loc_18005FE6A
0x18005fe52  xor     ecx, ecx; dwErrCode
0x18005fe54  call    cs:__imp_SetLastError
0x18005fe5b  nop     dword ptr [rax+rax+00h]
0x18005fe60  mov     rax, [rbp+var_18]
0x18005fe64  mov     dword ptr [rax], 1
0x18005fe6a  mov     rax, [rbp+var_18]
0x18005fe6e  lea     rcx, [rbp+var_40]; this
0x18005fe72  mov     ebx, [rax]
0x18005fe74  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18005fe79  lea     rcx, [rbp+lpBuffer]
0x18005fe7d  call    ??1?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(void)
0x18005fe82  mov     eax, ebx
0x18005fe84  mov     rcx, [rbp+var_10]
0x18005fe88  xor     rcx, rsp; StackCookie
0x18005fe8b  call    __security_check_cookie
0x18005fe90  mov     rbx, [rsp+80h+arg_8]
0x18005fe98  add     rsp, 80h
0x18005fe9f  pop     rdi
0x18005fea0  pop     rsi
0x18005fea1  pop     rbp
0x18005fea2  retn
```
