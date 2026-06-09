# SxspGetFullPathName(ushort const *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,CGenericBaseStringBuffer<CUnicodeCharTraits> *)

- ea: `0x1800605d4`
- end: `0x1800607a5`
- name: `?SxspGetFullPathName@@YAHPEBGAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAV1@@Z`
- size: `465`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x180059f28`
- `0x180062568`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180023260`
- `0x18002d630`
- `0x18002de34`
- `0x18002def0`
- `0x180030480`
- `0x18005d2b0`
- `0x18005d38c`
- `0x1800605d4`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006071b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006071b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060657`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800606da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060758`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060657`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800606da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060758`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800606b7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800606b7`

## pseudocode

```c
__int64 __fastcall SxspGetFullPathName(LPCWSTR lpFileName, __int64 a2)
{
  const char *v4; // rcx
  DWORD v5; // edx
  DWORD FullPathNameW; // eax
  DWORD v7; // edi
  DWORD LastError; // eax
  unsigned int v9; // ebx
  LPWSTR lpBuffer[2]; // [rsp+20h] [rbp-60h] BYREF
  unsigned __int64 v12; // [rsp+30h] [rbp-50h]
  LPWSTR FilePart; // [rsp+38h] [rbp-48h] BYREF
  int v14; // [rsp+40h] [rbp-40h] BYREF
  int v15; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+50h] [rbp-30h]
  __int64 *v17; // [rsp+58h] [rbp-28h]
  __int64 v18; // [rsp+60h] [rbp-20h]
  int v19; // [rsp+68h] [rbp-18h]
  unsigned int *v20; // [rsp+70h] [rbp-10h]

  v14 = 0;
  v17 = &qword_180074F10;
  v15 = 1;
  v20 = (unsigned int *)&v14;
  v16 = 0;
  v18 = 544438355;
  v19 = 4119;
  CFrame::BaseEnter((CFrame *)&v15);
  if ( lpFileName )
  {
    CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(a2);
    while ( 1 )
    {
      v12 = 0;
      FilePart = 0;
      *(_OWORD *)lpBuffer = 0;
      CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(lpBuffer, a2);
      v5 = v12;
      if ( v12 > 0xFFFFFFFF )
        v5 = -1;
      FullPathNameW = GetFullPathNameW(lpFileName, v5, lpBuffer[1], &FilePart);
      v7 = FullPathNameW;
      if ( !FullPathNameW )
        break;
      if ( FullPathNameW < v12 )
        goto LABEL_14;
      CGenericStringBufferAccessor<CUnicodeCharTraits>::Detach(lpBuffer);
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(a2, v7 + 1) )
      {
        *v20 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074ED0);
LABEL_13:
        CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(lpBuffer);
        goto LABEL_15;
      }
      CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(lpBuffer);
    }
    LastError = GetLastError();
    if ( LastError )
    {
      CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v15, LastError);
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180074EF0);
      goto LABEL_13;
    }
LABEL_14:
    CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(lpBuffer);
    SetLastError(0);
    *v20 = 1;
  }
  else
  {
    v19 = 4121;
    FusionpTraceParameterCheck(v4);
    SetLastError(0x57u);
    *v20 = 0;
  }
LABEL_15:
  v9 = *v20;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v15);
  return v9;
}

```

## disassembly

```asm
0x1800605d4  mov     [rsp-18h+arg_10], rbx
0x1800605d9  mov     [rsp-18h+arg_18], rdi
0x1800605de  push    rbp
0x1800605df  push    r13
0x1800605e1  push    r14
0x1800605e3  mov     rbp, rsp
0x1800605e6  sub     rsp, 80h
0x1800605ed  mov     rax, cs:__security_cookie
0x1800605f4  xor     rax, rsp
0x1800605f7  mov     [rbp+var_8], rax
0x1800605fb  lea     rax, qword_180074F10
0x180060602  mov     [rbp+var_40], 0
0x180060609  mov     [rbp+var_28], rax
0x18006060d  mov     r14, rcx
0x180060610  lea     rax, [rbp+var_40]
0x180060614  mov     [rbp+var_38], 1
0x18006061b  lea     rcx, [rbp+var_38]; this
0x18006061f  mov     [rbp+var_10], rax
0x180060623  mov     rbx, rdx
0x180060626  mov     [rbp+var_30], 0
0x18006062e  mov     [rbp+var_20], 20737853h
0x180060636  mov     [rbp+var_18], 1017h
0x18006063d  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180060642  test    r14, r14
0x180060645  jnz     short loc_18006066F
0x180060647  mov     [rbp+var_18], 1019h
0x18006064e  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180060653  lea     ecx, [r14+57h]; dwErrCode
0x180060657  call    cs:__imp_SetLastError
0x18006065e  nop     dword ptr [rax+rax+00h]
0x180060663  mov     rax, [rbp+var_10]
0x180060667  mov     [rax], r14d
0x18006066a  jmp     loc_18006076E
0x18006066f  mov     rcx, rbx
0x180060672  call    ?Clear@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAX_N@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(bool)
0x180060677  mov     r13d, 0FFFFFFFFh
0x18006067d  xorps   xmm0, xmm0
0x180060680  mov     [rbp+var_50], 0
0x180060688  mov     rdx, rbx
0x18006068b  mov     [rbp+FilePart], 0
0x180060693  lea     rcx, [rbp+lpBuffer]
0x180060697  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x18006069c  call    ?Attach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXPEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(CGenericBaseStringBuffer<CUnicodeCharTraits> *)
0x1800606a1  mov     edx, dword ptr [rbp+var_50]
0x1800606a4  lea     r9, [rbp+FilePart]; lpFilePart
0x1800606a8  cmp     [rbp+var_50], r13
0x1800606ac  mov     rcx, r14; lpFileName
0x1800606af  mov     r8, [rbp+lpBuffer+8]; lpBuffer
0x1800606b3  cmova   edx, r13d; nBufferLength
0x1800606b7  call    cs:__imp_GetFullPathNameW
0x1800606be  nop     dword ptr [rax+rax+00h]
0x1800606c3  mov     edi, eax
0x1800606c5  test    eax, eax
0x1800606c7  jz      short loc_18006071B
0x1800606c9  cmp     rdi, [rbp+var_50]
0x1800606cd  jb      short loc_18006074D
0x1800606cf  lea     rcx, [rbp+lpBuffer]
0x1800606d3  call    ?Detach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXXZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::Detach(void)
0x1800606d8  xor     ecx, ecx; dwErrCode
0x1800606da  call    cs:__imp_SetLastError
0x1800606e1  nop     dword ptr [rax+rax+00h]
0x1800606e6  lea     edx, [rdi+1]
0x1800606e9  mov     rcx, rbx
0x1800606ec  call    ?Win32ResizeBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAH_KW4EPreserveContents@@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(unsigned __int64,EPreserveContents)
0x1800606f1  test    eax, eax
0x1800606f3  jz      short loc_180060703
0x1800606f5  lea     rcx, [rbp+lpBuffer]
0x1800606f9  call    ??1?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(void)
0x1800606fe  jmp     loc_18006067D
0x180060703  mov     rax, [rbp+var_10]
0x180060707  lea     rcx, off_180074ED0; struct _CALL_SITE_INFO *
0x18006070e  mov     dword ptr [rax], 0
0x180060714  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180060719  jmp     short loc_180060742
0x18006071b  call    cs:__imp_GetLastError
0x180060722  nop     dword ptr [rax+rax+00h]
0x180060727  test    eax, eax
0x180060729  jz      short loc_18006074D
0x18006072b  mov     edx, eax; unsigned int
0x18006072d  lea     rcx, [rbp+var_38]; this
0x180060731  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180060736  lea     rcx, off_180074EF0; struct _CALL_SITE_INFO *
0x18006073d  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180060742  lea     rcx, [rbp+lpBuffer]
0x180060746  call    ??1?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(void)
0x18006074b  jmp     short loc_18006076E
0x18006074d  lea     rcx, [rbp+lpBuffer]
0x180060751  call    ??1?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(void)
0x180060756  xor     ecx, ecx; dwErrCode
0x180060758  call    cs:__imp_SetLastError
0x18006075f  nop     dword ptr [rax+rax+00h]
0x180060764  mov     rax, [rbp+var_10]
0x180060768  mov     dword ptr [rax], 1
0x18006076e  mov     rax, [rbp+var_10]
0x180060772  lea     rcx, [rbp+var_38]; this
0x180060776  mov     ebx, [rax]
0x180060778  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18006077d  mov     eax, ebx
0x18006077f  mov     rcx, [rbp+var_8]
0x180060783  xor     rcx, rsp; StackCookie
0x180060786  call    __security_check_cookie
0x18006078b  lea     r11, [rsp+80h+var_s0]
0x180060793  mov     rbx, [r11+30h]
0x180060797  mov     rdi, [r11+38h]
0x18006079b  mov     rsp, r11
0x18006079e  pop     r14
0x1800607a0  pop     r13
0x1800607a2  pop     rbp
0x1800607a3  retn
```
