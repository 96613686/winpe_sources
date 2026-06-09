# UndockedModuleForwarder::LoadDll(void)

- ea: `0x180007b64`
- end: `0x180007cf8`
- name: `?LoadDll@UndockedModuleForwarder@@AEAAJXZ`
- size: `404`
- prototype: `__int64 __fastcall(UndockedModuleForwarder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007fd0`
- `0x180008364`

## callees

- `0x180003760`
- `0x180007308`
- `0x180007b64`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007c48`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007c9c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007cbc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007c48`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007c9c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007cbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ca4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c91`

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
    v1 = UndockedModuleLoader::Load(
           &word_180022278,
           (__int64)&Src,
           (byte_1800224B8 != 0) | 2u,
           &qword_180022480,
           (HMODULE *)&v11);
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
0x180007b64  mov     rax, rsp
0x180007b67  mov     [rax+8], rbx
0x180007b6b  mov     [rax+10h], rsi
0x180007b6f  mov     [rax+18h], rdi
0x180007b73  mov     [rax+20h], r13
0x180007b77  push    rbp
0x180007b78  push    r14
0x180007b7a  push    r15
0x180007b7c  mov     rbp, rsp
0x180007b7f  sub     rsp, 70h
0x180007b83  mov     rax, cs:__security_cookie
0x180007b8a  xor     rax, rsp
0x180007b8d  mov     [rbp+var_8], rax
0x180007b91  lea     r13, CriticalSection
0x180007b98  mov     rcx, r13; lpCriticalSection
0x180007b9b  call    cs:__imp_EnterCriticalSection
0x180007ba1  mov     [rbp+var_18], r13
0x180007ba5  cmp     cs:hLibModule, 0
0x180007bad  jz      short loc_180007BB6
0x180007baf  xor     edi, edi
0x180007bb1  jmp     loc_180007CC3
0x180007bb6  mov     [rbp+hLibModule], 0
0x180007bbe  xor     r8d, r8d
0x180007bc1  lea     ecx, [r8+1]
0x180007bc5  cmp     cs:byte_1800224B8, r8b
0x180007bcc  cmovnz  r8d, ecx
0x180007bd0  or      r8d, 2
0x180007bd4  lea     rax, [rbp+hLibModule]
0x180007bd8  mov     [rbp+var_30], rax
0x180007bdc  mov     [rbp+var_28], 0
0x180007be4  mov     [rbp+var_20], cl
0x180007be7  mov     [rsp+70h+var_38], 0
0x180007bf0  mov     [rsp+70h+var_40], 0
0x180007bf9  mov     [rsp+70h+var_48], 0
0x180007c02  lea     rax, [rbp+var_28]
0x180007c06  mov     [rsp+70h+var_50], rax; int
0x180007c0b  lea     r9, qword_180022480
0x180007c12  lea     rdx, Src
0x180007c19  lea     rcx, word_180022278; wchar_t *
0x180007c20  call    UndockedModuleLoader__Load
0x180007c25  mov     edi, eax
0x180007c27  cmp     [rbp+var_20], 0
0x180007c2b  jz      short loc_180007C59
0x180007c2d  mov     r15, [rbp+var_28]
0x180007c31  mov     rsi, [rbp+var_30]
0x180007c35  mov     r14, [rsi]
0x180007c38  test    r14, r14
0x180007c3b  jz      short loc_180007C56
0x180007c3d  call    cs:__imp_GetLastError
0x180007c43  mov     ebx, eax
0x180007c45  mov     rcx, r14; hLibModule
0x180007c48  call    cs:__imp_FreeLibrary
0x180007c4e  mov     ecx, ebx; dwErrCode
0x180007c50  call    cs:__imp_SetLastError
0x180007c56  mov     [rsi], r15
0x180007c59  test    edi, edi
0x180007c5b  jns     short loc_180007C7B
0x180007c5d  mov     rcx, [rbp+18h]; this
0x180007c61  mov     r9d, edi; char *
0x180007c64  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180007c6b  mov     edx, 63h ; 'c'; void *
0x180007c70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c75  mov     rcx, [rbp+hLibModule]
0x180007c79  jmp     short loc_180007CB7
0x180007c7b  mov     rsi, [rbp+hLibModule]
0x180007c7f  xor     ecx, ecx
0x180007c81  mov     [rbp+hLibModule], rcx
0x180007c85  mov     rdi, cs:hLibModule
0x180007c8c  test    rdi, rdi
0x180007c8f  jz      short loc_180007CAE
0x180007c91  call    cs:__imp_GetLastError
0x180007c97  mov     ebx, eax
0x180007c99  mov     rcx, rdi; hLibModule
0x180007c9c  call    cs:__imp_FreeLibrary
0x180007ca2  mov     ecx, ebx; dwErrCode
0x180007ca4  call    cs:__imp_SetLastError
0x180007caa  mov     rcx, [rbp+hLibModule]; hLibModule
0x180007cae  mov     cs:hLibModule, rsi
0x180007cb5  xor     edi, edi
0x180007cb7  test    rcx, rcx
0x180007cba  jz      short loc_180007CC3
0x180007cbc  call    cs:__imp_FreeLibrary
0x180007cc2  nop
0x180007cc3  mov     rcx, r13; lpCriticalSection
0x180007cc6  call    cs:__imp_LeaveCriticalSection
0x180007ccc  mov     eax, edi
0x180007cce  mov     rcx, [rbp+var_8]
0x180007cd2  xor     rcx, rsp; StackCookie
0x180007cd5  call    __security_check_cookie
0x180007cda  lea     r11, [rsp+70h+var_s0]
0x180007cdf  mov     rbx, [r11+20h]
0x180007ce3  mov     rsi, [r11+28h]
0x180007ce7  mov     rdi, [r11+30h]
0x180007ceb  mov     r13, [r11+38h]
0x180007cef  mov     rsp, r11
0x180007cf2  pop     r15
0x180007cf4  pop     r14
0x180007cf6  pop     rbp
0x180007cf7  retn
```
