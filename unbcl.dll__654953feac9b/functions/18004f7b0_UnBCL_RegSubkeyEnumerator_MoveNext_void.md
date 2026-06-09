# UnBCL::RegSubkeyEnumerator::MoveNext(void)

- ea: `0x18004f7b0`
- end: `0x18004f94d`
- name: `?MoveNext@RegSubkeyEnumerator@UnBCL@@UEAAHXZ`
- size: `413`
- prototype: `__int64 __fastcall(UnBCL::RegSubkeyEnumerator *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x18003f618`
- `0x18004f7b0`
- `0x18006f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004f928`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f928`
- `ADVAPI32!RegEnumKeyExW` at `0x18004f873`
- `ADVAPI32!RegEnumKeyExW` at `0x18004f873`
- `KERNEL32!GetLastError` at `0x18004f8eb`
- `KERNEL32!GetLastError` at `0x18004f8eb`
- `KERNEL32!SetLastError` at `0x18004f8a7`
- `KERNEL32!SetLastError` at `0x18004f8a7`

## string_xrefs

- `0x18004f902`: `UnBCL::RegSubkeyEnumerator::MoveNext`
- `0x18004f8c3`: `UnBCL::RegSubkeyEnumerator::MoveNext`

## pseudocode

```c
__int64 __fastcall UnBCL::RegSubkeyEnumerator::MoveNext(UnBCL::RegSubkeyEnumerator *this)
{
  DWORD v1; // edx
  DWORD v3; // eax
  __int64 v4; // rcx
  WCHAR *v5; // r8
  __int64 v6; // rdx
  DWORD v7; // eax
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  LSTATUS v11; // eax
  LSTATUS v12; // ebp
  __int64 result; // rax
  struct UnBCL::_LOG_DATA *v14; // r14
  struct ILogHandler *v15; // rdi
  void (__fastcall *v16)(struct ILogHandler *, _QWORD, char *, __int64, const wchar_t *, const wchar_t *, DWORD); // rbx
  DWORD LastError; // eax
  DWORD cchName; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 10);
  if ( v1 == -1 )
    return 0;
  v3 = *((_DWORD *)this + 9);
  v4 = *((_QWORD *)this + 2);
  v5 = (WCHAR *)*((_QWORD *)this + 3);
  while ( 1 )
  {
    cchName = v3;
    v11 = RegEnumKeyExW(*(HKEY *)(v4 + 8), v1, v5, &cchName, 0, 0, 0, 0);
    v12 = v11;
    if ( !v11 )
    {
      result = 1;
      *((_DWORD *)this + 11) = 0;
      ++*((_DWORD *)this + 10);
      return result;
    }
    if ( v11 == 259 )
    {
      *((_DWORD *)this + 11) = 0;
      return 0;
    }
    if ( v11 != 234 )
      break;
    v6 = *((_QWORD *)this + 3);
    v7 = cchName + 1;
    *((_DWORD *)this + 9) = cchName + 1;
    v7 *= 2;
    *((_DWORD *)this + 8) = v7;
    v8 = v7;
    v9 = (__int64)*UnBCL::Allocator::s_Manager;
    if ( v6 )
      v10 = (*(__int64 (__fastcall **)(struct IHeapMemory * near *, __int64, __int64))(v9 + 24))(
              UnBCL::Allocator::s_Manager,
              v6,
              v8);
    else
      v10 = (*(__int64 (__fastcall **)(struct IHeapMemory * near *, __int64))(v9 + 8))(UnBCL::Allocator::s_Manager, v8);
    *((_QWORD *)this + 3) = v10;
    v5 = (WCHAR *)v10;
    v3 = *((_DWORD *)this + 9);
    v4 = *((_QWORD *)this + 2);
    v1 = *((_DWORD *)this + 10);
  }
  SetLastError(v11);
  if ( UnBCL::Logging::s_Handler )
  {
    v14 = UnBCL::BclLogFormat(
            (UnBCL *)0x2000000,
            (unsigned int)"%s: %s failed",
            "UnBCL::RegSubkeyEnumerator::MoveNext",
            "RegEnumKeyEx");
    if ( v14 )
    {
      v15 = UnBCL::Logging::s_Handler;
      v16 = **(void (__fastcall ***)(struct ILogHandler *, _QWORD, char *, __int64, const wchar_t *, const wchar_t *, DWORD))UnBCL::Logging::s_Handler;
      LastError = GetLastError();
      v16(
        v15,
        *(unsigned int *)v14,
        (char *)v14 + 4,
        125,
        L"base\\ntsetup\\unbcl\\src\\regsubkeyenum.cpp",
        L"UnBCL::RegSubkeyEnumerator::MoveNext",
        LastError);
      operator delete(v14);
    }
  }
  result = 1;
  *((_DWORD *)this + 11) = 1;
  if ( v12 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18004f7b0  mov     [rsp+arg_8], rbx
0x18004f7b5  mov     [rsp+arg_10], rbp
0x18004f7ba  push    rsi
0x18004f7bb  push    rdi
0x18004f7bc  push    r14
0x18004f7be  sub     rsp, 40h
0x18004f7c2  mov     edx, [rcx+28h]
0x18004f7c5  mov     rsi, rcx
0x18004f7c8  cmp     edx, 0FFFFFFFFh
0x18004f7cb  jz      loc_18004F946
0x18004f7d1  mov     eax, [rcx+24h]
0x18004f7d4  mov     rcx, [rcx+10h]
0x18004f7d8  mov     r8, [rsi+18h]
0x18004f7dc  jmp     short loc_18004F842
0x18004f7de  cmp     ebp, 103h
0x18004f7e4  jz      loc_18004F93F
0x18004f7ea  cmp     ebp, 0EAh
0x18004f7f0  jnz     loc_18004F8A5
0x18004f7f6  mov     eax, [rsp+58h+cchName]
0x18004f7fa  mov     rdx, [rsi+18h]
0x18004f7fe  inc     eax
0x18004f800  mov     [rsi+24h], eax
0x18004f803  add     eax, eax
0x18004f805  mov     [rsi+20h], eax
0x18004f808  mov     rcx, cs:?s_Manager@Allocator@UnBCL@@0PAPEAUIHeapMemory@@A; IHeapMemory * near * UnBCL::Allocator::s_Manager
0x18004f80f  mov     r8d, eax
0x18004f812  mov     rax, [rcx]
0x18004f815  test    rdx, rdx
0x18004f818  jz      short loc_18004F825
0x18004f81a  mov     rax, [rax+18h]
0x18004f81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f823  jmp     short loc_18004F831
0x18004f825  mov     rax, [rax+8]
0x18004f829  mov     rdx, r8
0x18004f82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f831  mov     [rsi+18h], rax
0x18004f835  mov     r8, rax; lpName
0x18004f838  mov     eax, [rsi+24h]
0x18004f83b  mov     rcx, [rsi+10h]
0x18004f83f  mov     edx, [rsi+28h]; dwIndex
0x18004f842  mov     [rsp+58h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18004f84b  lea     r9, [rsp+58h+cchName]; lpcchName
0x18004f850  mov     [rsp+58h+lpcchClass], 0; lpcchClass
0x18004f859  mov     [rsp+58h+cchName], eax
0x18004f85d  mov     rcx, [rcx+8]; hKey
0x18004f861  mov     [rsp+58h+lpClass], 0; lpClass
0x18004f86a  mov     [rsp+58h+lpReserved], 0; lpReserved
0x18004f873  call    cs:__imp_RegEnumKeyExW
0x18004f879  mov     ebp, eax
0x18004f87b  test    eax, eax
0x18004f87d  jnz     loc_18004F7DE
0x18004f883  mov     eax, 1
0x18004f888  mov     dword ptr [rsi+2Ch], 0
0x18004f88f  add     [rsi+28h], eax
0x18004f892  mov     rbx, [rsp+58h+arg_8]
0x18004f897  mov     rbp, [rsp+58h+arg_10]
0x18004f89c  add     rsp, 40h
0x18004f8a0  pop     r14
0x18004f8a2  pop     rdi
0x18004f8a3  pop     rsi
0x18004f8a4  retn
0x18004f8a5  mov     ecx, ebp; dwErrCode
0x18004f8a7  call    cs:__imp_SetLastError
0x18004f8ad  cmp     cs:?s_Handler@Logging@UnBCL@@0PEAUILogHandler@@EA, 0; ILogHandler * UnBCL::Logging::s_Handler
0x18004f8b5  jz      short loc_18004F92E
0x18004f8b7  lea     r9, aRegenumkeyex; "RegEnumKeyEx"
0x18004f8be  mov     ecx, 2000000h; this
0x18004f8c3  lea     r8, aUnbclRegsubkey_1; "UnBCL::RegSubkeyEnumerator::MoveNext"
0x18004f8ca  lea     rdx, aSSFailed; "%s: %s failed"
0x18004f8d1  call    ?BclLogFormat@UnBCL@@YAPEAU_LOG_DATA@1@KPEBDZZ; UnBCL::BclLogFormat(ulong,char const *,...)
0x18004f8d6  mov     r14, rax
0x18004f8d9  test    rax, rax
0x18004f8dc  jz      short loc_18004F92E
0x18004f8de  mov     rdi, cs:?s_Handler@Logging@UnBCL@@0PEAUILogHandler@@EA; ILogHandler * UnBCL::Logging::s_Handler
0x18004f8e5  mov     rdx, [rdi]
0x18004f8e8  mov     rbx, [rdx]
0x18004f8eb  call    cs:__imp_GetLastError
0x18004f8f1  mov     edx, [r14]
0x18004f8f4  lea     r8, [r14+4]
0x18004f8f8  mov     dword ptr [rsp+58h+lpcchClass], eax
0x18004f8fc  mov     r9d, 7Dh ; '}'
0x18004f902  lea     rax, aUnbclRegsubkey_2; "UnBCL::RegSubkeyEnumerator::MoveNext"
0x18004f909  mov     rcx, rdi
0x18004f90c  mov     [rsp+58h+lpClass], rax
0x18004f911  lea     rax, aBaseNtsetupUnb_11; "base\\ntsetup\\unbcl\\src\\regsubkeyenu"...
0x18004f918  mov     [rsp+58h+lpReserved], rax
0x18004f91d  mov     rax, rbx
0x18004f920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f925  mov     rcx, r14
0x18004f928  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004f92e  mov     eax, 1
0x18004f933  mov     [rsi+2Ch], eax
0x18004f936  test    ebp, ebp
0x18004f938  jnz     short loc_18004F946
0x18004f93a  jmp     loc_18004F892
0x18004f93f  mov     dword ptr [rsi+2Ch], 0
0x18004f946  xor     eax, eax
0x18004f948  jmp     loc_18004F892
```
