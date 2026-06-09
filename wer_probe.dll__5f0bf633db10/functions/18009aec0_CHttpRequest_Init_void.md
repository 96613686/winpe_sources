# CHttpRequest::Init(void *)

- ea: `0x18009aec0`
- end: `0x18009b077`
- name: `?Init@CHttpRequest@@QEAAJPEAX@Z`
- size: `439`
- prototype: `__int64 __fastcall(CHttpRequest *__hidden this, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18009322c`
- `0x1800a1b20`

## callees

- `0x18000716c`
- `0x180007e34`
- `0x18001fe24`
- `0x18009aec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009affd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009affd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009aef2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009af70`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009afe1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009aef2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009af70`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009afe1`

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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v7);
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
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, &WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v7);
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
0x18009aec0  push    rbx
0x18009aec2  push    rbp
0x18009aec3  push    rsi
0x18009aec4  push    rdi
0x18009aec5  push    r14
0x18009aec7  push    r15
0x18009aec9  sub     rsp, 28h
0x18009aecd  mov     r15d, 1
0x18009aed3  lea     r14, [rcx+18h]
0x18009aed7  mov     rax, [r14]
0x18009aeda  mov     rbp, rdx
0x18009aedd  add     rax, r15
0x18009aee0  mov     rsi, rcx
0x18009aee3  cmp     rax, r15
0x18009aee6  ja      short loc_18009AF56
0x18009aee8  xor     r9d, r9d; lpName
0x18009aeeb  xor     r8d, r8d; bInitialState
0x18009aeee  xor     edx, edx; bManualReset
0x18009aef0  xor     ecx, ecx; lpEventAttributes
0x18009aef2  call    cs:__imp_CreateEventW
0x18009aef8  mov     rdx, rax
0x18009aefb  mov     rcx, r14
0x18009aefe  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009af03  mov     rax, [r14]
0x18009af06  add     rax, r15
0x18009af09  cmp     rax, r15
0x18009af0c  ja      short loc_18009AF56
0x18009af0e  call    cs:__imp_GetLastError
0x18009af14  mov     ecx, eax; unsigned int
0x18009af16  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009af1b  mov     ebx, eax
0x18009af1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009af24  lea     rax, WPP_GLOBAL_Control
0x18009af2b  cmp     rcx, rax
0x18009af2e  jz      short loc_18009AF4D
0x18009af30  test    [rcx+1Ch], r15b
0x18009af34  jz      short loc_18009AF4D
0x18009af36  mov     rcx, [rcx+10h]
0x18009af3a  lea     edx, [r15+9]
0x18009af3e  mov     r9d, ebx
0x18009af41  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009af48  call    WPP_SF_d
0x18009af4d  lea     rdi, [rsi+20h]
0x18009af51  jmp     loc_18009B03D
0x18009af56  lea     rdi, [rsi+20h]
0x18009af5a  mov     rax, [rdi]
0x18009af5d  add     rax, r15
0x18009af60  cmp     rax, r15
0x18009af63  ja      short loc_18009AFC3
0x18009af65  xor     r9d, r9d; lpName
0x18009af68  xor     r8d, r8d; bInitialState
0x18009af6b  mov     edx, r15d; bManualReset
0x18009af6e  xor     ecx, ecx; lpEventAttributes
0x18009af70  call    cs:__imp_CreateEventW
0x18009af76  mov     rdx, rax
0x18009af79  mov     rcx, rdi
0x18009af7c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009af81  mov     rax, [rdi]
0x18009af84  add     rax, r15
0x18009af87  cmp     rax, r15
0x18009af8a  ja      short loc_18009AFC3
0x18009af8c  call    cs:__imp_GetLastError
0x18009af92  mov     ecx, eax; unsigned int
0x18009af94  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009af99  mov     ebx, eax
0x18009af9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009afa2  lea     rax, WPP_GLOBAL_Control
0x18009afa9  cmp     rcx, rax
0x18009afac  jz      loc_18009B03D
0x18009afb2  test    [rcx+1Ch], r15b
0x18009afb6  jz      loc_18009B03D
0x18009afbc  mov     edx, 0Bh
0x18009afc1  jmp     short loc_18009B02A
0x18009afc3  lea     rbx, [rsi+30h]
0x18009afc7  mov     rax, [rbx]
0x18009afca  add     rax, r15
0x18009afcd  cmp     rax, r15
0x18009afd0  ja      loc_18009B062
0x18009afd6  xor     r9d, r9d; lpName
0x18009afd9  xor     r8d, r8d; bInitialState
0x18009afdc  mov     edx, r15d; bManualReset
0x18009afdf  xor     ecx, ecx; lpEventAttributes
0x18009afe1  call    cs:__imp_CreateEventW
0x18009afe7  mov     rdx, rax
0x18009afea  mov     rcx, rbx
0x18009afed  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009aff2  mov     rax, [rbx]
0x18009aff5  add     rax, r15
0x18009aff8  cmp     rax, r15
0x18009affb  ja      short loc_18009B062
0x18009affd  call    cs:__imp_GetLastError
0x18009b003  mov     ecx, eax; unsigned int
0x18009b005  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009b00a  mov     ebx, eax
0x18009b00c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b013  lea     rax, WPP_GLOBAL_Control
0x18009b01a  cmp     rcx, rax
0x18009b01d  jz      short loc_18009B03D
0x18009b01f  test    [rcx+1Ch], r15b
0x18009b023  jz      short loc_18009B03D
0x18009b025  mov     edx, 0Ch
0x18009b02a  mov     rcx, [rcx+10h]
0x18009b02e  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009b035  mov     r9d, ebx
0x18009b038  call    WPP_SF_d
0x18009b03d  test    ebx, ebx
0x18009b03f  jns     short loc_18009B068
0x18009b041  xor     edx, edx
0x18009b043  mov     rcx, r14
0x18009b046  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009b04b  xor     edx, edx
0x18009b04d  mov     rcx, rdi
0x18009b050  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009b055  lea     rcx, [rsi+30h]
0x18009b059  xor     edx, edx
0x18009b05b  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009b060  jmp     short loc_18009B068
0x18009b062  mov     [rsi+28h], rbp
0x18009b066  xor     ebx, ebx
0x18009b068  mov     eax, ebx
0x18009b06a  add     rsp, 28h
0x18009b06e  pop     r15
0x18009b070  pop     r14
0x18009b072  pop     rdi
0x18009b073  pop     rsi
0x18009b074  pop     rbp
0x18009b075  pop     rbx
0x18009b076  retn
```
