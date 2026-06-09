# SharedMemory::SharedMemory(std::vector<uchar,AlignedStore::AlignedAllocator<uchar,16>> const &)

- ea: `0x18000cd88`
- end: `0x18000cf79`
- name: `??0SharedMemory@@QEAA@AEBV?$vector@EV?$AlignedAllocator@E$0BA@@AlignedStore@@@std@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000c9a8`

## callees

- `0x1800056e4`
- `0x180007468`
- `0x18000cd88`
- `0x18000d400`
- `0x18000d75c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ceff`
- `msvcrt!memcpy_s` at `0x18000ceff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cea6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ceb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ceb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce61`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000ce8c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000ce8c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000ce17`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000ce17`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000ceb1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000cecc`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000ceb1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000cecc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf1a`

## string_xrefs

- `0x18000cf3d`: `avcore\xaudio\hrtf\Inc\CommonHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SharedMemory::SharedMemory(__int64 a1, __int64 a2)
{
  char *v4; // r14
  char *v5; // rsi
  const char *v6; // r9
  void *v7; // r15
  DWORD LastError; // ebx
  const void *v9; // rsi
  const char *v10; // r9
  const void *v11; // r15
  DWORD v12; // ebx
  void *v13; // rcx
  rsize_t v14; // rdx
  const char *v15; // r9
  HLOCAL v16; // rcx
  char v18; // [rsp+30h] [rbp-40h] BYREF
  char v19; // [rsp+38h] [rbp-38h] BYREF
  __int128 v20; // [rsp+40h] [rbp-30h]
  __int64 v21; // [rsp+50h] [rbp-20h]
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  HLOCAL hMem; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)a1 = 0;
  v4 = (char *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  GetSecurityDescriptor(&hMem);
  *(_QWORD *)&v20 = 24;
  v21 = 1;
  *((_QWORD *)&v20 + 1) = hMem;
  *(_OWORD *)&FileMappingAttributes.nLength = v20;
  *(_QWORD *)&FileMappingAttributes.bInheritHandle = 1;
  v5 = (char *)CreateFileMappingW(
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 &FileMappingAttributes,
                 4u,
                 0,
                 *(_DWORD *)(a2 + 8) - *(_DWORD *)a2,
                 0);
  if ( (char *)a1 == &v18 )
  {
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
  }
  else
  {
    v7 = *(void **)a1;
    if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v7);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v5;
  }
  if ( *(_QWORD *)a1 == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x21,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      v6);
  v9 = MapViewOfFile(*(HANDLE *)a1, 0xF001Fu, 0, 0, 0);
  if ( v4 == &v19 )
  {
    if ( v9 )
      UnmapViewOfFile(v9);
  }
  else
  {
    v11 = *(const void **)v4;
    if ( *(_QWORD *)v4 )
    {
      v12 = GetLastError();
      UnmapViewOfFile(v11);
      SetLastError(v12);
    }
    *(_QWORD *)v4 = v9;
  }
  v13 = *(void **)v4;
  if ( !*(_QWORD *)v4 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x24,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      v10);
  v14 = (unsigned int)(*(_DWORD *)(a2 + 8) - *(_DWORD *)a2);
  *(_DWORD *)(a1 + 16) = v14;
  if ( memcpy_s(v13, v14, *(const void *const *)a2, *(_QWORD *)(a2 + 8) - *(_QWORD *)a2) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x7B,
      (unsigned int)"avcore\\xaudio\\hrtf\\Inc\\CommonHelpers.h",
      v15);
  v16 = hMem;
  hMem = 0;
  if ( v16 )
    LocalFree(v16);
  return a1;
}

```

## disassembly

```asm
0x18000cd88  mov     [rsp-28h+arg_10], rbx
0x18000cd8d  mov     [rsp-28h+arg_18], rsi
0x18000cd92  mov     [rsp-28h+arg_0], rcx
0x18000cd97  push    rbp
0x18000cd98  push    rdi
0x18000cd99  push    r12
0x18000cd9b  push    r14
0x18000cd9d  push    r15
0x18000cd9f  mov     rbp, rsp
0x18000cda2  sub     rsp, 70h
0x18000cda6  mov     r12, rdx
0x18000cda9  mov     rdi, rcx
0x18000cdac  mov     qword ptr [rcx], 0
0x18000cdb3  lea     r14, [rcx+8]
0x18000cdb7  mov     qword ptr [r14], 0
0x18000cdbe  lea     rcx, [rbp+hMem]
0x18000cdc2  call    ?GetSecurityDescriptor@@YA?AV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@PEB_W@Z; GetSecurityDescriptor(wchar_t const *)
0x18000cdc7  nop
0x18000cdc8  mov     qword ptr [rbp+var_30], 18h
0x18000cdd0  mov     [rbp+var_20], 1
0x18000cdd8  mov     rax, [rbp+hMem]
0x18000cddc  mov     qword ptr [rbp+var_30+8], rax
0x18000cde0  movups  xmm0, [rbp+var_30]
0x18000cde4  movups  xmmword ptr [rbp+FileMappingAttributes.nLength], xmm0
0x18000cde8  movsd   xmm1, [rbp+var_20]
0x18000cded  movsd   qword ptr [rbp+FileMappingAttributes.bInheritHandle], xmm1
0x18000cdf2  mov     eax, [r12+8]
0x18000cdf7  sub     eax, [r12]
0x18000cdfb  mov     [rsp+70h+lpName], 0; lpName
0x18000ce04  mov     [rsp+70h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18000ce08  xor     r9d, r9d; dwMaximumSizeHigh
0x18000ce0b  lea     r8d, [r9+4]; flProtect
0x18000ce0f  lea     rdx, [rbp+FileMappingAttributes]; lpFileMappingAttributes
0x18000ce13  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000ce17  call    cs:__imp_CreateFileMappingW
0x18000ce1d  mov     rsi, rax
0x18000ce20  lea     rax, [rbp+var_40]
0x18000ce24  cmp     rdi, rax
0x18000ce27  jz      short loc_18000CE54
0x18000ce29  mov     r15, [rdi]
0x18000ce2c  lea     rdx, [r15-1]
0x18000ce30  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000ce34  ja      short loc_18000CE4F
0x18000ce36  call    cs:__imp_GetLastError
0x18000ce3c  mov     ebx, eax
0x18000ce3e  mov     rcx, r15; hObject
0x18000ce41  call    cs:__imp_CloseHandle
0x18000ce47  mov     ecx, ebx; dwErrCode
0x18000ce49  call    cs:__imp_SetLastError
0x18000ce4f  mov     [rdi], rsi
0x18000ce52  jmp     short loc_18000CE67
0x18000ce54  lea     rax, [rsi-1]
0x18000ce58  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ce5c  ja      short loc_18000CE67
0x18000ce5e  mov     rcx, rsi; hObject
0x18000ce61  call    cs:__imp_CloseHandle
0x18000ce67  mov     rcx, [rbp+28h]; this
0x18000ce6b  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18000ce6f  jz      loc_18000CF52
0x18000ce75  mov     qword ptr [rsp+70h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18000ce7e  xor     r9d, r9d; dwFileOffsetLow
0x18000ce81  xor     r8d, r8d; dwFileOffsetHigh
0x18000ce84  mov     edx, 0F001Fh; dwDesiredAccess
0x18000ce89  mov     rcx, [rdi]; hFileMappingObject
0x18000ce8c  call    cs:__imp_MapViewOfFile
0x18000ce92  mov     rsi, rax
0x18000ce95  lea     rax, [rbp+var_38]
0x18000ce99  cmp     r14, rax
0x18000ce9c  jz      short loc_18000CEC4
0x18000ce9e  mov     r15, [r14]
0x18000cea1  test    r15, r15
0x18000cea4  jz      short loc_18000CEBF
0x18000cea6  call    cs:__imp_GetLastError
0x18000ceac  mov     ebx, eax
0x18000ceae  mov     rcx, r15; lpBaseAddress
0x18000ceb1  call    cs:__imp_UnmapViewOfFile
0x18000ceb7  mov     ecx, ebx; dwErrCode
0x18000ceb9  call    cs:__imp_SetLastError
0x18000cebf  mov     [r14], rsi
0x18000cec2  jmp     short loc_18000CED2
0x18000cec4  test    rsi, rsi
0x18000cec7  jz      short loc_18000CED2
0x18000cec9  mov     rcx, rsi; lpBaseAddress
0x18000cecc  call    cs:__imp_UnmapViewOfFile
0x18000ced2  mov     rax, [rbp+28h]
0x18000ced6  mov     rcx, [r14]; Destination
0x18000ced9  test    rcx, rcx
0x18000cedc  jz      loc_18000CF64
0x18000cee2  mov     edx, [r12+8]
0x18000cee7  sub     edx, [r12]; DestinationSize
0x18000ceeb  mov     [rdi+10h], edx
0x18000ceee  mov     rbx, [rbp+28h]
0x18000cef2  mov     r9, [r12+8]
0x18000cef7  sub     r9, [r12]; SourceSize
0x18000cefb  mov     r8, [r12]; Source
0x18000ceff  call    cs:__imp_memcpy_s
0x18000cf05  test    eax, eax
0x18000cf07  jnz     short loc_18000CF3D
0x18000cf09  mov     rcx, [rbp+hMem]; hMem
0x18000cf0d  mov     [rbp+hMem], 0
0x18000cf15  test    rcx, rcx
0x18000cf18  jz      short loc_18000CF21
0x18000cf1a  call    cs:__imp_LocalFree
0x18000cf20  nop
0x18000cf21  mov     rax, rdi
0x18000cf24  lea     r11, [rsp+70h+var_s0]
0x18000cf29  mov     rbx, [r11+40h]
0x18000cf2d  mov     rsi, [r11+48h]
0x18000cf31  mov     rsp, r11
0x18000cf34  pop     r15
0x18000cf36  pop     r14
0x18000cf38  pop     r12
0x18000cf3a  pop     rdi
0x18000cf3b  pop     rbp
0x18000cf3c  retn
0x18000cf3d  lea     r8, aAvcoreXaudioHr; "avcore\\xaudio\\hrtf\\Inc\\CommonHelper"...
0x18000cf44  mov     edx, 7Bh ; '{'; void *
0x18000cf49  mov     rcx, rbx; this
0x18000cf4c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000cf52  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000cf59  mov     edx, 21h ; '!'; void *
0x18000cf5e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000cf64  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000cf6b  mov     edx, 24h ; '$'; void *
0x18000cf70  mov     rcx, rax; this
0x18000cf73  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
