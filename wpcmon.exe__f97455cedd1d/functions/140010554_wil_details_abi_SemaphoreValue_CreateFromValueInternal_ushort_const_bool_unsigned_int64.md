# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140010554`
- end: `0x14001077e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14000fc78`
- `0x14001004c`

## callees

- `0x140005530`
- `0x140010554`
- `0x140011fec`
- `0x140016854`
- `0x1400185d0`
- `0x14001b500`
- `0x14001b510`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001066e`
- `KERNEL32!CloseHandle` at `0x14001070e`
- `KERNEL32!CloseHandle` at `0x14001066e`
- `KERNEL32!CloseHandle` at `0x14001070e`
- `KERNEL32!GetLastError` at `0x140010654`
- `KERNEL32!GetLastError` at `0x140010662`
- `KERNEL32!GetLastError` at `0x1400106f4`
- `KERNEL32!GetLastError` at `0x140010703`
- `KERNEL32!GetLastError` at `0x140010654`
- `KERNEL32!GetLastError` at `0x140010662`
- `KERNEL32!GetLastError` at `0x1400106f4`
- `KERNEL32!GetLastError` at `0x140010703`
- `KERNEL32!SetLastError` at `0x14001067f`
- `KERNEL32!SetLastError` at `0x14001071a`
- `KERNEL32!SetLastError` at `0x14001067f`
- `KERNEL32!SetLastError` at `0x14001071a`
- `KERNEL32!CreateSemaphoreExW` at `0x140010618`
- `KERNEL32!CreateSemaphoreExW` at `0x1400106bb`
- `KERNEL32!CreateSemaphoreExW` at `0x140010618`
- `KERNEL32!CreateSemaphoreExW` at `0x1400106bb`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  unsigned int v30; // r8d
  const char *v31; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v28 = (void *)*((_QWORD *)this + 1);
    if ( v28 )
    {
      v29 = GetLastError();
      if ( !CloseHandle(v28) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
      SetLastError(v29);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v26,
        dwFlagsa);
      return v27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140010554  mov     [rsp+arg_8], rbx
0x140010559  mov     [rsp+arg_10], rbp
0x14001055e  push    rsi
0x14001055f  push    rdi
0x140010560  push    r12
0x140010562  push    r14
0x140010564  push    r15
0x140010566  sub     rsp, 250h
0x14001056d  mov     rax, cs:__security_cookie
0x140010574  xor     rax, rsp
0x140010577  mov     [rsp+278h+var_38], rax
0x14001057f  mov     rax, 0C000000000000000h
0x140010589  mov     rbp, r9
0x14001058c  mov     r8, rdx
0x14001058f  mov     rbx, rcx
0x140010592  test    rax, r9
0x140010595  jnz     loc_140010765
0x14001059b  xor     r12d, r12d
0x14001059e  lea     rax, [rsp+278h+Name]
0x1400105a3  mov     ecx, 7FFFFFFEh
0x1400105a8  mov     edx, 104h
0x1400105ad  lea     esi, [r12+1]
0x1400105b2  test    rcx, rcx
0x1400105b5  jz      short loc_1400105D5
0x1400105b7  movzx   r9d, word ptr [r8]
0x1400105bb  test    r9w, r9w
0x1400105bf  jz      short loc_1400105D5
0x1400105c1  mov     [rax], r9w
0x1400105c5  add     r8, 2
0x1400105c9  add     rax, 2
0x1400105cd  sub     rcx, rsi
0x1400105d0  sub     rdx, rsi; unsigned __int64
0x1400105d3  jnz     short loc_1400105B2
0x1400105d5  test    rdx, rdx
0x1400105d8  lea     rcx, [rax-2]
0x1400105dc  lea     r8, aP0; "_p0"
0x1400105e3  cmovnz  rcx, rax
0x1400105e7  mov     [rcx], r12w
0x1400105eb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400105f0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400105f5  mov     edx, ebp
0x1400105f7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400105ff  and     edx, 7FFFFFFFh; lInitialCount
0x140010605  mov     [rsp+278h+dwFlags], r12d; int
0x14001060a  mov     r8d, esi
0x14001060d  lea     r9, [rsp+278h+Name]; lpName
0x140010612  cmova   r8d, edx; lMaximumCount
0x140010616  xor     ecx, ecx; lpSemaphoreAttributes
0x140010618  call    cs:__imp_CreateSemaphoreExW
0x14001061e  mov     r15, rax
0x140010621  test    rax, rax
0x140010624  jnz     short loc_140010654
0x140010626  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14001062b  mov     edi, eax
0x14001062d  test    eax, eax
0x14001062f  jns     short loc_140010688
0x140010631  mov     rcx, [rsp+278h]; this
0x140010639  lea     r8, aWil; "wil"
0x140010640  mov     r9d, eax; char *
0x140010643  mov     edx, 8Bh; void *
0x140010648  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001064d  mov     eax, edi
0x14001064f  jmp     loc_140010726
0x140010654  call    cs:__imp_GetLastError
0x14001065a  mov     rdi, [rbx]
0x14001065d  test    rdi, rdi
0x140010660  jz      short loc_140010685
0x140010662  call    cs:__imp_GetLastError
0x140010668  mov     rcx, rdi; hObject
0x14001066b  mov     r14d, eax
0x14001066e  call    cs:__imp_CloseHandle
0x140010674  test    eax, eax
0x140010676  jz      loc_14001076B
0x14001067c  mov     ecx, r14d; dwErrCode
0x14001067f  call    cs:__imp_SetLastError
0x140010685  mov     [rbx], r15
0x140010688  lea     r8, asc_1400B3FD8; "h"
0x14001068f  shr     rbp, 1Fh
0x140010693  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140010698  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001069d  test    ebp, ebp
0x14001069f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400106a7  lea     r9, [rsp+278h+Name]; lpName
0x1400106ac  mov     [rsp+278h+dwFlags], r12d; int
0x1400106b1  cmovnz  esi, ebp
0x1400106b4  mov     edx, ebp; lInitialCount
0x1400106b6  mov     r8d, esi; lMaximumCount
0x1400106b9  xor     ecx, ecx; lpSemaphoreAttributes
0x1400106bb  call    cs:__imp_CreateSemaphoreExW
0x1400106c1  mov     rsi, rax
0x1400106c4  test    rax, rax
0x1400106c7  jnz     short loc_1400106F4
0x1400106c9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400106ce  mov     ebx, eax
0x1400106d0  test    eax, eax
0x1400106d2  jns     short loc_140010724
0x1400106d4  mov     rcx, [rsp+278h]; this
0x1400106dc  lea     r8, aWil; "wil"
0x1400106e3  mov     r9d, eax; char *
0x1400106e6  mov     edx, 90h; void *
0x1400106eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400106f0  mov     eax, ebx
0x1400106f2  jmp     short loc_140010726
0x1400106f4  call    cs:__imp_GetLastError
0x1400106fa  mov     rdi, [rbx+8]
0x1400106fe  test    rdi, rdi
0x140010701  jz      short loc_140010720
0x140010703  call    cs:__imp_GetLastError
0x140010709  mov     rcx, rdi; hObject
0x14001070c  mov     ebp, eax
0x14001070e  call    cs:__imp_CloseHandle
0x140010714  test    eax, eax
0x140010716  jz      short loc_140010752
0x140010718  mov     ecx, ebp; dwErrCode
0x14001071a  call    cs:__imp_SetLastError
0x140010720  mov     [rbx+8], rsi
0x140010724  xor     eax, eax
0x140010726  mov     rcx, [rsp+278h+var_38]
0x14001072e  xor     rcx, rsp; StackCookie
0x140010731  call    __security_check_cookie
0x140010736  lea     r11, [rsp+278h+var_28]
0x14001073e  mov     rbx, [r11+38h]
0x140010742  mov     rbp, [r11+40h]
0x140010746  mov     rsp, r11
0x140010749  pop     r15
0x14001074b  pop     r14
0x14001074d  pop     r12
0x14001074f  pop     rdi
0x140010750  pop     rsi
0x140010751  retn
0x140010752  mov     rcx, [rsp+278h]; this
0x14001075a  mov     edx, 0A0Bh; void *
0x14001075f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140010765  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14001076b  mov     rcx, [rsp+278h]; this
0x140010773  mov     edx, 0A0Bh; void *
0x140010778  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
