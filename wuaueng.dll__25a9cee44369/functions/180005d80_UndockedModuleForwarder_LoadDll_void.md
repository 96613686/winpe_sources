# UndockedModuleForwarder::LoadDll(void)

- ea: `0x180005d80`
- end: `0x180005f14`
- name: `?LoadDll@UndockedModuleForwarder@@AEAAJXZ`
- size: `404`
- prototype: `__int64 __fastcall(UndockedModuleForwarder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006790`
- `0x180006840`

## callees

- `0x180003760`
- `0x180005524`
- `0x180005d80`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005e64`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005eb8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005ed8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005e64`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005eb8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005ed8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005db7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005db7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005ee2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005ee2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ec0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ead`

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
  int v11[2]; // [rsp+48h] [rbp-28h] BYREF
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
    *(_QWORD *)v11 = 0;
    v12 = 1;
    v1 = UndockedModuleLoader::Load(&word_180022298, (__int64)v11);
    if ( v12 )
    {
      v2 = *(HMODULE *)v11;
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
0x180005d80  mov     rax, rsp
0x180005d83  mov     [rax+8], rbx
0x180005d87  mov     [rax+10h], rsi
0x180005d8b  mov     [rax+18h], rdi
0x180005d8f  mov     [rax+20h], r13
0x180005d93  push    rbp
0x180005d94  push    r14
0x180005d96  push    r15
0x180005d98  mov     rbp, rsp
0x180005d9b  sub     rsp, 70h
0x180005d9f  mov     rax, cs:__security_cookie
0x180005da6  xor     rax, rsp
0x180005da9  mov     [rbp+var_8], rax
0x180005dad  lea     r13, CriticalSection
0x180005db4  mov     rcx, r13; lpCriticalSection
0x180005db7  call    cs:__imp_EnterCriticalSection
0x180005dbd  mov     [rbp+var_18], r13
0x180005dc1  cmp     cs:hLibModule, 0
0x180005dc9  jz      short loc_180005DD2
0x180005dcb  xor     edi, edi
0x180005dcd  jmp     loc_180005EDF
0x180005dd2  mov     [rbp+hLibModule], 0
0x180005dda  xor     r8d, r8d
0x180005ddd  lea     ecx, [r8+1]
0x180005de1  cmp     cs:byte_1800224D8, r8b
0x180005de8  cmovnz  r8d, ecx
0x180005dec  or      r8d, 2
0x180005df0  lea     rax, [rbp+hLibModule]
0x180005df4  mov     [rbp+var_30], rax
0x180005df8  mov     qword ptr [rbp+var_28], 0
0x180005e00  mov     [rbp+var_20], cl
0x180005e03  mov     [rsp+70h+var_38], 0
0x180005e0c  mov     [rsp+70h+var_40], 0
0x180005e15  mov     [rsp+70h+var_48], 0
0x180005e1e  lea     rax, [rbp+var_28]
0x180005e22  mov     qword ptr [rsp+70h+var_50], rax; int
0x180005e27  lea     r9, qword_1800224A0
0x180005e2e  lea     rdx, Src
0x180005e35  lea     rcx, word_180022298
0x180005e3c  call    UndockedModuleLoader__Load
0x180005e41  mov     edi, eax
0x180005e43  cmp     [rbp+var_20], 0
0x180005e47  jz      short loc_180005E75
0x180005e49  mov     r15, qword ptr [rbp+var_28]
0x180005e4d  mov     rsi, [rbp+var_30]
0x180005e51  mov     r14, [rsi]
0x180005e54  test    r14, r14
0x180005e57  jz      short loc_180005E72
0x180005e59  call    cs:__imp_GetLastError
0x180005e5f  mov     ebx, eax
0x180005e61  mov     rcx, r14; hLibModule
0x180005e64  call    cs:__imp_FreeLibrary
0x180005e6a  mov     ecx, ebx; dwErrCode
0x180005e6c  call    cs:__imp_SetLastError
0x180005e72  mov     [rsi], r15
0x180005e75  test    edi, edi
0x180005e77  jns     short loc_180005E97
0x180005e79  mov     rcx, [rbp+18h]; this
0x180005e7d  mov     r9d, edi; char *
0x180005e80  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180005e87  mov     edx, 63h ; 'c'; void *
0x180005e8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e91  mov     rcx, [rbp+hLibModule]
0x180005e95  jmp     short loc_180005ED3
0x180005e97  mov     rsi, [rbp+hLibModule]
0x180005e9b  xor     ecx, ecx
0x180005e9d  mov     [rbp+hLibModule], rcx
0x180005ea1  mov     rdi, cs:hLibModule
0x180005ea8  test    rdi, rdi
0x180005eab  jz      short loc_180005ECA
0x180005ead  call    cs:__imp_GetLastError
0x180005eb3  mov     ebx, eax
0x180005eb5  mov     rcx, rdi; hLibModule
0x180005eb8  call    cs:__imp_FreeLibrary
0x180005ebe  mov     ecx, ebx; dwErrCode
0x180005ec0  call    cs:__imp_SetLastError
0x180005ec6  mov     rcx, [rbp+hLibModule]; hLibModule
0x180005eca  mov     cs:hLibModule, rsi
0x180005ed1  xor     edi, edi
0x180005ed3  test    rcx, rcx
0x180005ed6  jz      short loc_180005EDF
0x180005ed8  call    cs:__imp_FreeLibrary
0x180005ede  nop
0x180005edf  mov     rcx, r13; lpCriticalSection
0x180005ee2  call    cs:__imp_LeaveCriticalSection
0x180005ee8  mov     eax, edi
0x180005eea  mov     rcx, [rbp+var_8]
0x180005eee  xor     rcx, rsp; StackCookie
0x180005ef1  call    __security_check_cookie
0x180005ef6  lea     r11, [rsp+70h+var_s0]
0x180005efb  mov     rbx, [r11+20h]
0x180005eff  mov     rsi, [r11+28h]
0x180005f03  mov     rdi, [r11+30h]
0x180005f07  mov     r13, [r11+38h]
0x180005f0b  mov     rsp, r11
0x180005f0e  pop     r15
0x180005f10  pop     r14
0x180005f12  pop     rbp
0x180005f13  retn
```
