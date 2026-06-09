# CHttpRequest::Init(void *)

- ea: `0x18009f6d8`
- end: `0x18009f8b4`
- name: `?Init@CHttpRequest@@QEAAJPEAX@Z`
- size: `476`
- prototype: `__int64 __fastcall(CHttpRequest *__hidden this, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180097354`
- `0x1800a6670`

## callees

- `0x180008004`
- `0x18001c368`
- `0x180020680`
- `0x18009f6d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f72c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f7b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f72c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f7b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f833`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f70a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f794`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f811`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f70a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f794`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f811`

## pseudocode

```c
__int64 __fastcall CHttpRequest::Init(CHttpRequest *this, void *a2)
{
  _QWORD *v2; // r14
  HANDLE EventW; // rax
  DWORD LastError; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rdi
  HANDLE v9; // rax
  DWORD v10; // eax
  wchar_t *v11; // rcx
  __int64 v12; // rdx
  HANDLE v13; // rax
  DWORD v14; // eax

  v2 = (_QWORD *)((char *)this + 24);
  if ( (unsigned __int64)(*((_QWORD *)this + 3) + 1LL) <= 1 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(v2, EventW);
    if ( (unsigned __int64)(*v2 + 1LL) <= 1 )
    {
      LastError = GetLastError();
      v7 = ERROR_HR_FROM_WIN32(LastError);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v7);
      v8 = (_QWORD *)((char *)this + 32);
      goto LABEL_18;
    }
  }
  v8 = (_QWORD *)((char *)this + 32);
  if ( (unsigned __int64)(*((_QWORD *)this + 4) + 1LL) > 1
    || (v9 = CreateEventW(0, 1, 0, 0),
        tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 32, v9),
        (unsigned __int64)(*v8 + 1LL) > 1) )
  {
    if ( (unsigned __int64)(*((_QWORD *)this + 6) + 1LL) > 1
      || (v13 = CreateEventW(0, 1, 0, 0),
          tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 48, v13),
          (unsigned __int64)(*((_QWORD *)this + 6) + 1LL) > 1) )
    {
      *((_QWORD *)this + 5) = a2;
      return 0;
    }
    v14 = GetLastError();
    v7 = ERROR_HR_FROM_WIN32(v14);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 12;
      goto LABEL_17;
    }
  }
  else
  {
    v10 = GetLastError();
    v7 = ERROR_HR_FROM_WIN32(v10);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 11;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v7);
    }
  }
LABEL_18:
  if ( (v7 & 0x80000000) != 0 )
  {
    tlx::unique_any<tlx::file_handle_traits>::reset(v2, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(v8, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 48, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x18009f6d8  push    rbx
0x18009f6da  push    rbp
0x18009f6db  push    rsi
0x18009f6dc  push    rdi
0x18009f6dd  push    r14
0x18009f6df  push    r15
0x18009f6e1  sub     rsp, 28h
0x18009f6e5  mov     r15d, 1
0x18009f6eb  lea     r14, [rcx+18h]
0x18009f6ef  mov     rax, [r14]
0x18009f6f2  mov     rbp, rdx
0x18009f6f5  add     rax, r15
0x18009f6f8  mov     rsi, rcx
0x18009f6fb  cmp     rax, r15
0x18009f6fe  ja      short loc_18009F77A
0x18009f700  xor     r9d, r9d; lpName
0x18009f703  xor     r8d, r8d; bInitialState
0x18009f706  xor     edx, edx; bManualReset
0x18009f708  xor     ecx, ecx; lpEventAttributes
0x18009f70a  call    cs:__imp_CreateEventW
0x18009f711  nop     dword ptr [rax+rax+00h]
0x18009f716  mov     rdx, rax
0x18009f719  mov     rcx, r14
0x18009f71c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009f721  mov     rax, [r14]
0x18009f724  add     rax, r15
0x18009f727  cmp     rax, r15
0x18009f72a  ja      short loc_18009F77A
0x18009f72c  call    cs:__imp_GetLastError
0x18009f733  nop     dword ptr [rax+rax+00h]
0x18009f738  mov     ecx, eax; unsigned int
0x18009f73a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009f73f  mov     ebx, eax
0x18009f741  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f748  lea     rax, WPP_GLOBAL_Control
0x18009f74f  cmp     rcx, rax
0x18009f752  jz      short loc_18009F771
0x18009f754  test    [rcx+1Ch], r15b
0x18009f758  jz      short loc_18009F771
0x18009f75a  mov     rcx, [rcx+10h]
0x18009f75e  lea     edx, [r15+9]
0x18009f762  mov     r9d, ebx
0x18009f765  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009f76c  call    WPP_SF_d
0x18009f771  lea     rdi, [rsi+20h]
0x18009f775  jmp     loc_18009F879
0x18009f77a  lea     rdi, [rsi+20h]
0x18009f77e  mov     rax, [rdi]
0x18009f781  add     rax, r15
0x18009f784  cmp     rax, r15
0x18009f787  ja      short loc_18009F7F3
0x18009f789  xor     r9d, r9d; lpName
0x18009f78c  xor     r8d, r8d; bInitialState
0x18009f78f  mov     edx, r15d; bManualReset
0x18009f792  xor     ecx, ecx; lpEventAttributes
0x18009f794  call    cs:__imp_CreateEventW
0x18009f79b  nop     dword ptr [rax+rax+00h]
0x18009f7a0  mov     rdx, rax
0x18009f7a3  mov     rcx, rdi
0x18009f7a6  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009f7ab  mov     rax, [rdi]
0x18009f7ae  add     rax, r15
0x18009f7b1  cmp     rax, r15
0x18009f7b4  ja      short loc_18009F7F3
0x18009f7b6  call    cs:__imp_GetLastError
0x18009f7bd  nop     dword ptr [rax+rax+00h]
0x18009f7c2  mov     ecx, eax; unsigned int
0x18009f7c4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009f7c9  mov     ebx, eax
0x18009f7cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f7d2  lea     rax, WPP_GLOBAL_Control
0x18009f7d9  cmp     rcx, rax
0x18009f7dc  jz      loc_18009F879
0x18009f7e2  test    [rcx+1Ch], r15b
0x18009f7e6  jz      loc_18009F879
0x18009f7ec  mov     edx, 0Bh
0x18009f7f1  jmp     short loc_18009F866
0x18009f7f3  lea     rbx, [rsi+30h]
0x18009f7f7  mov     rax, [rbx]
0x18009f7fa  add     rax, r15
0x18009f7fd  cmp     rax, r15
0x18009f800  ja      loc_18009F89E
0x18009f806  xor     r9d, r9d; lpName
0x18009f809  xor     r8d, r8d; bInitialState
0x18009f80c  mov     edx, r15d; bManualReset
0x18009f80f  xor     ecx, ecx; lpEventAttributes
0x18009f811  call    cs:__imp_CreateEventW
0x18009f818  nop     dword ptr [rax+rax+00h]
0x18009f81d  mov     rdx, rax
0x18009f820  mov     rcx, rbx
0x18009f823  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009f828  mov     rax, [rbx]
0x18009f82b  add     rax, r15
0x18009f82e  cmp     rax, r15
0x18009f831  ja      short loc_18009F89E
0x18009f833  call    cs:__imp_GetLastError
0x18009f83a  nop     dword ptr [rax+rax+00h]
0x18009f83f  mov     ecx, eax; unsigned int
0x18009f841  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009f846  mov     ebx, eax
0x18009f848  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f84f  lea     rax, WPP_GLOBAL_Control
0x18009f856  cmp     rcx, rax
0x18009f859  jz      short loc_18009F879
0x18009f85b  test    [rcx+1Ch], r15b
0x18009f85f  jz      short loc_18009F879
0x18009f861  mov     edx, 0Ch
0x18009f866  mov     rcx, [rcx+10h]
0x18009f86a  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009f871  mov     r9d, ebx
0x18009f874  call    WPP_SF_d
0x18009f879  test    ebx, ebx
0x18009f87b  jns     short loc_18009F8A4
0x18009f87d  xor     edx, edx
0x18009f87f  mov     rcx, r14
0x18009f882  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009f887  xor     edx, edx
0x18009f889  mov     rcx, rdi
0x18009f88c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009f891  lea     rcx, [rsi+30h]
0x18009f895  xor     edx, edx
0x18009f897  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009f89c  jmp     short loc_18009F8A4
0x18009f89e  mov     [rsi+28h], rbp
0x18009f8a2  xor     ebx, ebx
0x18009f8a4  mov     eax, ebx
0x18009f8a6  add     rsp, 28h
0x18009f8aa  pop     r15
0x18009f8ac  pop     r14
0x18009f8ae  pop     rdi
0x18009f8af  pop     rsi
0x18009f8b0  pop     rbp
0x18009f8b1  pop     rbx
0x18009f8b2  retn
```
