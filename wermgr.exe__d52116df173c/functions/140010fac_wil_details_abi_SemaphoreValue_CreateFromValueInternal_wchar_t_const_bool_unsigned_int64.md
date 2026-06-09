# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x140010fac`
- end: `0x1400111f4`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `584`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140010778`
- `0x140010b80`

## callees

- `0x140003200`
- `0x14000a070`
- `0x14000a62c`
- `0x14000d7c8`
- `0x140010fac`
- `0x140011a34`
- `0x1400148d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001115c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001116b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001115c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001116b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400110df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400110df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400110ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011176`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400110ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011176`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140011070`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14001111b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140011070`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14001111b`

## string_xrefs

- `0x140011091`: `wil::details_abi::SemaphoreValue::CreateFromValueInternal`
- `0x14001113c`: `wil::details_abi::SemaphoreValue::CreateFromValueInternal`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  __int64 v21; // r8
  unsigned __int64 v22; // rbp
  wil::details *v23; // rcx
  HANDLE v24; // rsi
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // ebp
  __int64 v29; // r8
  char *dwFlags; // [rsp+20h] [rbp-258h]
  char *dwFlagsa; // [rsp+20h] [rbp-258h]
  DWORD dwDesiredAccess; // [rsp+28h] [rbp-250h]
  DWORD dwDesiredAccessa; // [rsp+28h] [rbp-250h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag4::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(Name, v9, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v19 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v19) )
        wil::details::in1diag4::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          v21,
          "wil::details::CloseHandle",
          dwFlags);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v17 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      LODWORD(dwFlags) = LastErrorFailHr;
      wil::details::in1diag4::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        "wil::details_abi::SemaphoreValue::CreateFromValueInternal",
        (wil::details *)dwFlags,
        dwDesiredAccess);
      return v17;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag4::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          v29,
          "wil::details::CloseHandle",
          dwFlagsa);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      LODWORD(dwFlagsa) = v25;
      wil::details::in1diag4::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        "wil::details_abi::SemaphoreValue::CreateFromValueInternal",
        (wil::details *)dwFlagsa,
        dwDesiredAccessa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140010fac  mov     [rsp+arg_8], rbx
0x140010fb1  mov     [rsp+arg_10], rbp
0x140010fb6  push    rsi
0x140010fb7  push    rdi
0x140010fb8  push    r12
0x140010fba  push    r14
0x140010fbc  push    r15
0x140010fbe  sub     rsp, 250h
0x140010fc5  mov     rax, cs:__security_cookie
0x140010fcc  xor     rax, rsp
0x140010fcf  mov     [rsp+278h+var_38], rax
0x140010fd7  mov     rax, 0C000000000000000h
0x140010fe1  mov     rbp, r9
0x140010fe4  mov     r8, rdx
0x140010fe7  mov     rbx, rcx
0x140010fea  test    rax, r9
0x140010fed  jnz     loc_1400111D4
0x140010ff3  xor     r12d, r12d
0x140010ff6  lea     rax, [rsp+278h+Name]
0x140010ffb  mov     ecx, 7FFFFFFEh
0x140011000  mov     edx, 104h
0x140011005  lea     esi, [r12+1]
0x14001100a  test    rcx, rcx
0x14001100d  jz      short loc_14001102D
0x14001100f  movzx   r9d, word ptr [r8]
0x140011013  test    r9w, r9w
0x140011017  jz      short loc_14001102D
0x140011019  mov     [rax], r9w
0x14001101d  add     r8, 2
0x140011021  add     rax, 2
0x140011025  sub     rcx, rsi
0x140011028  sub     rdx, rsi; unsigned __int64
0x14001102b  jnz     short loc_14001100A
0x14001102d  test    rdx, rdx
0x140011030  lea     rcx, [rax-2]
0x140011034  lea     r8, aP0; "_p0"
0x14001103b  cmovnz  rcx, rax
0x14001103f  mov     [rcx], r12w
0x140011043  lea     rcx, [rsp+278h+Name]; wchar_t *
0x140011048  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001104d  mov     edx, ebp
0x14001104f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; int
0x140011057  and     edx, 7FFFFFFFh; lInitialCount
0x14001105d  mov     dword ptr [rsp+278h+dwFlags], r12d; char *
0x140011062  mov     r8d, esi
0x140011065  lea     r9, [rsp+278h+Name]; lpName
0x14001106a  cmova   r8d, edx; lMaximumCount
0x14001106e  xor     ecx, ecx; lpSemaphoreAttributes
0x140011070  call    cs:__imp_CreateSemaphoreExW
0x140011076  mov     r15, rax
0x140011079  test    rax, rax
0x14001107c  jnz     short loc_1400110B4
0x14001107e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140011083  mov     edi, eax
0x140011085  test    eax, eax
0x140011087  jns     short loc_1400110E8
0x140011089  mov     rcx, [rsp+278h]; this
0x140011091  lea     r9, aWilDetailsAbiS_3; "wil::details_abi::SemaphoreValue::Creat"...
0x140011098  lea     r8, aWil; "wil"
0x14001109f  mov     dword ptr [rsp+278h+dwFlags], eax; wil::details *
0x1400110a3  mov     edx, 8Bh; void *
0x1400110a8  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x1400110ad  mov     eax, edi
0x1400110af  jmp     loc_14001118E
0x1400110b4  call    cs:__imp_GetLastError
0x1400110ba  mov     rdi, [rbx]
0x1400110bd  test    rdi, rdi
0x1400110c0  jz      short loc_1400110E5
0x1400110c2  call    cs:__imp_GetLastError
0x1400110c8  mov     rcx, rdi; hObject
0x1400110cb  mov     r14d, eax
0x1400110ce  call    cs:__imp_CloseHandle
0x1400110d4  test    eax, eax
0x1400110d6  jz      loc_1400111DA
0x1400110dc  mov     ecx, r14d; dwErrCode
0x1400110df  call    cs:__imp_SetLastError
0x1400110e5  mov     [rbx], r15
0x1400110e8  lea     r8, asc_1400245D4; "h"
0x1400110ef  shr     rbp, 1Fh
0x1400110f3  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1400110f8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400110fd  test    ebp, ebp
0x1400110ff  mov     [rsp+278h+dwDesiredAccess], 1F0003h; int
0x140011107  lea     r9, [rsp+278h+Name]; lpName
0x14001110c  mov     dword ptr [rsp+278h+dwFlags], r12d; char *
0x140011111  cmovnz  esi, ebp
0x140011114  mov     edx, ebp; lInitialCount
0x140011116  mov     r8d, esi; lMaximumCount
0x140011119  xor     ecx, ecx; lpSemaphoreAttributes
0x14001111b  call    cs:__imp_CreateSemaphoreExW
0x140011121  mov     rsi, rax
0x140011124  test    rax, rax
0x140011127  jnz     short loc_14001115C
0x140011129  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14001112e  mov     ebx, eax
0x140011130  test    eax, eax
0x140011132  jns     short loc_14001118C
0x140011134  mov     rcx, [rsp+278h]; this
0x14001113c  lea     r9, aWilDetailsAbiS_3; "wil::details_abi::SemaphoreValue::Creat"...
0x140011143  lea     r8, aWil; "wil"
0x14001114a  mov     dword ptr [rsp+278h+dwFlags], eax; wil::details *
0x14001114e  mov     edx, 90h; void *
0x140011153  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140011158  mov     eax, ebx
0x14001115a  jmp     short loc_14001118E
0x14001115c  call    cs:__imp_GetLastError
0x140011162  mov     rdi, [rbx+8]
0x140011166  test    rdi, rdi
0x140011169  jz      short loc_140011188
0x14001116b  call    cs:__imp_GetLastError
0x140011171  mov     rcx, rdi; hObject
0x140011174  mov     ebp, eax
0x140011176  call    cs:__imp_CloseHandle
0x14001117c  test    eax, eax
0x14001117e  jz      short loc_1400111BA
0x140011180  mov     ecx, ebp; dwErrCode
0x140011182  call    cs:__imp_SetLastError
0x140011188  mov     [rbx+8], rsi
0x14001118c  xor     eax, eax
0x14001118e  mov     rcx, [rsp+278h+var_38]
0x140011196  xor     rcx, rsp; StackCookie
0x140011199  call    __security_check_cookie
0x14001119e  lea     r11, [rsp+278h+var_28]
0x1400111a6  mov     rbx, [r11+38h]
0x1400111aa  mov     rbp, [r11+40h]
0x1400111ae  mov     rsp, r11
0x1400111b1  pop     r15
0x1400111b3  pop     r14
0x1400111b5  pop     r12
0x1400111b7  pop     rdi
0x1400111b8  pop     rsi
0x1400111b9  retn
0x1400111ba  mov     rcx, [rsp+278h]; this
0x1400111c2  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x1400111c9  mov     edx, 0A0Bh; void *
0x1400111ce  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x1400111d4  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
0x1400111da  mov     rcx, [rsp+278h]; this
0x1400111e2  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x1400111e9  mov     edx, 0A0Bh; void *
0x1400111ee  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
```
