# UndockedModuleForwarder::LoadDll(void)

- ea: `0x180003984`
- end: `0x180003b18`
- name: `?LoadDll@UndockedModuleForwarder@@AEAAJXZ`
- size: `404`
- prototype: `__int64 __fastcall(UndockedModuleForwarder *__hidden this)`
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003b40`
- `0x180003c70`
- `0x180003d20`
- `0x180003dd0`
- `0x180003e70`
- `0x180003f20`
- `0x180003fd0`
- `0x180004080`
- `0x1800043f8`
- `0x18000448c`

## callees

- `0x180003128`
- `0x180003984`
- `0x180006858`
- `0x18000ed40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ab1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ac4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ac4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003a68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003abc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003adc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003a68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003abc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003adc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ae6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ae6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800039bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800039bb`

## pseudocode

```c
__int64 __fastcall UndockedModuleForwarder::LoadDll(UndockedModuleForwarder *this)
{
  int v1; // edi
  HMODULE v2; // r15
  HMODULE v3; // r14
  DWORD LastError; // ebx
  HMODULE v5; // rcx
  HMODULE v6; // rsi
  HMODULE v7; // rdi
  DWORD v8; // ebx
  int v10; // [rsp+20h] [rbp-50h]
  __int64 v11; // [rsp+48h] [rbp-28h] BYREF
  char v12; // [rsp+50h] [rbp-20h]
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+58h] [rbp-18h]
  HMODULE hLibModule; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  EnterCriticalSection(&CriticalSection);
  v13 = &CriticalSection;
  if ( ::hLibModule )
  {
    v1 = 0;
  }
  else
  {
    hLibModule = 0;
    v11 = 0;
    v12 = 1;
    v1 = UndockedModuleLoader::Load(&word_180020288, (__int64)&v11);
    if ( v12 )
    {
      v2 = (HMODULE)v11;
      v3 = hLibModule;
      if ( hLibModule )
      {
        LastError = GetLastError();
        FreeLibrary(v3);
        SetLastError(LastError);
      }
      hLibModule = v2;
    }
    if ( v1 >= 0 )
    {
      v6 = hLibModule;
      v5 = 0;
      hLibModule = 0;
      v7 = ::hLibModule;
      if ( ::hLibModule )
      {
        v8 = GetLastError();
        FreeLibrary(v7);
        SetLastError(v8);
        v5 = hLibModule;
      }
      ::hLibModule = v6;
      v1 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
        (const char *)(unsigned int)v1,
        v10);
      v5 = hLibModule;
    }
    if ( v5 )
      FreeLibrary(v5);
  }
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180003984  mov     rax, rsp
0x180003987  mov     [rax+8], rbx
0x18000398b  mov     [rax+10h], rsi
0x18000398f  mov     [rax+18h], rdi
0x180003993  mov     [rax+20h], r13
0x180003997  push    rbp
0x180003998  push    r14
0x18000399a  push    r15
0x18000399c  mov     rbp, rsp
0x18000399f  sub     rsp, 70h
0x1800039a3  mov     rax, cs:__security_cookie
0x1800039aa  xor     rax, rsp
0x1800039ad  mov     [rbp+var_8], rax
0x1800039b1  lea     r13, CriticalSection
0x1800039b8  mov     rcx, r13; lpCriticalSection
0x1800039bb  call    cs:__imp_EnterCriticalSection
0x1800039c1  mov     [rbp+var_18], r13
0x1800039c5  cmp     cs:hLibModule, 0
0x1800039cd  jz      short loc_1800039D6
0x1800039cf  xor     edi, edi
0x1800039d1  jmp     loc_180003AE3
0x1800039d6  mov     [rbp+hLibModule], 0
0x1800039de  xor     r8d, r8d
0x1800039e1  lea     ecx, [r8+1]
0x1800039e5  cmp     cs:byte_1800204C8, r8b
0x1800039ec  cmovnz  r8d, ecx
0x1800039f0  or      r8d, 2
0x1800039f4  lea     rax, [rbp+hLibModule]
0x1800039f8  mov     [rbp+var_30], rax
0x1800039fc  mov     [rbp+var_28], 0
0x180003a04  mov     [rbp+var_20], cl
0x180003a07  mov     [rsp+70h+var_38], 0
0x180003a10  mov     [rsp+70h+var_40], 0
0x180003a19  mov     [rsp+70h+var_48], 0
0x180003a22  lea     rax, [rbp+var_28]
0x180003a26  mov     [rsp+70h+var_50], rax; int
0x180003a2b  lea     r9, qword_180020490
0x180003a32  lea     rdx, Src
0x180003a39  lea     rcx, word_180020288; wchar_t *
0x180003a40  call    UndockedModuleLoader__Load
0x180003a45  mov     edi, eax
0x180003a47  cmp     [rbp+var_20], 0
0x180003a4b  jz      short loc_180003A79
0x180003a4d  mov     r15, [rbp+var_28]
0x180003a51  mov     rsi, [rbp+var_30]
0x180003a55  mov     r14, [rsi]
0x180003a58  test    r14, r14
0x180003a5b  jz      short loc_180003A76
0x180003a5d  call    cs:__imp_GetLastError
0x180003a63  mov     ebx, eax
0x180003a65  mov     rcx, r14; hLibModule
0x180003a68  call    cs:__imp_FreeLibrary
0x180003a6e  mov     ecx, ebx; dwErrCode
0x180003a70  call    cs:__imp_SetLastError
0x180003a76  mov     [rsi], r15
0x180003a79  test    edi, edi
0x180003a7b  jns     short loc_180003A9B
0x180003a7d  mov     rcx, [rbp+18h]; this
0x180003a81  mov     r9d, edi; char *
0x180003a84  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180003a8b  mov     edx, 63h ; 'c'; void *
0x180003a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a95  mov     rcx, [rbp+hLibModule]
0x180003a99  jmp     short loc_180003AD7
0x180003a9b  mov     rsi, [rbp+hLibModule]
0x180003a9f  xor     ecx, ecx
0x180003aa1  mov     [rbp+hLibModule], rcx
0x180003aa5  mov     rdi, cs:hLibModule
0x180003aac  test    rdi, rdi
0x180003aaf  jz      short loc_180003ACE
0x180003ab1  call    cs:__imp_GetLastError
0x180003ab7  mov     ebx, eax
0x180003ab9  mov     rcx, rdi; hLibModule
0x180003abc  call    cs:__imp_FreeLibrary
0x180003ac2  mov     ecx, ebx; dwErrCode
0x180003ac4  call    cs:__imp_SetLastError
0x180003aca  mov     rcx, [rbp+hLibModule]; hLibModule
0x180003ace  mov     cs:hLibModule, rsi
0x180003ad5  xor     edi, edi
0x180003ad7  test    rcx, rcx
0x180003ada  jz      short loc_180003AE3
0x180003adc  call    cs:__imp_FreeLibrary
0x180003ae2  nop
0x180003ae3  mov     rcx, r13; lpCriticalSection
0x180003ae6  call    cs:__imp_LeaveCriticalSection
0x180003aec  mov     eax, edi
0x180003aee  mov     rcx, [rbp+var_8]
0x180003af2  xor     rcx, rsp; StackCookie
0x180003af5  call    __security_check_cookie
0x180003afa  lea     r11, [rsp+70h+var_s0]
0x180003aff  mov     rbx, [r11+20h]
0x180003b03  mov     rsi, [r11+28h]
0x180003b07  mov     rdi, [r11+30h]
0x180003b0b  mov     r13, [r11+38h]
0x180003b0f  mov     rsp, r11
0x180003b12  pop     r15
0x180003b14  pop     r14
0x180003b16  pop     rbp
0x180003b17  retn
```
