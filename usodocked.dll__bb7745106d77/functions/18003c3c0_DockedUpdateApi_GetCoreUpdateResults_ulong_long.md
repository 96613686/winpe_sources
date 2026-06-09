# DockedUpdateApi::GetCoreUpdateResults(ulong *,long *)

- ea: `0x18003c3c0`
- end: `0x18003c496`
- name: `?GetCoreUpdateResults@DockedUpdateApi@@UEAAJPEAKPEAJ@Z`
- size: `214`
- prototype: `__int64 __fastcall(DockedUpdateApi *__hidden this, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x1800209fc`
- `0x18003c3c0`

## import_xrefs

- `UpdateAPI!GetUpdateResults` at `0x18003c445`
- `UpdateAPI!GetUpdateResults` at `0x18003c445`

## string_xrefs

- `0x18003c3f1`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedupdateapi.cpp`
- `0x18003c418`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedupdateapi.cpp`
- `0x18003c483`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedupdateapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall DockedUpdateApi::GetCoreUpdateResults(DockedUpdateApi *this, unsigned int *a2, int *a3)
{
  const char *v5; // r9
  __int64 result; // rax
  int UpdateResults; // eax
  int v8; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v9; // [rsp+24h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 )
  {
    if ( a3 )
    {
      v9 = 5;
      v8 = 0;
      UpdateResults = GetUpdateResults(&v9, &v8);
      if ( UpdateResults < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedupdateapi.cpp",
          (const char *)(unsigned int)UpdateResults,
          v8);
      *a2 = v9;
      *a3 = v8;
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedupdateapi.cpp",
        (const char *)0x80004003LL,
        v8);
      result = 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedupdateapi.cpp",
      (const char *)0x80004003LL,
      v8);
    result = 2147500035LL;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v8 = wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x57,
             (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedupdateapi.cpp",
             v5);
      result = (unsigned int)v8;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18003c3c0  mov     [rsp+arg_0], rbx
0x18003c3c5  push    rdi
0x18003c3c6  sub     rsp, 30h
0x18003c3ca  mov     rax, cs:__security_cookie
0x18003c3d1  xor     rax, rsp
0x18003c3d4  mov     [rsp+38h+var_10], rax
0x18003c3d9  mov     rdi, r8
0x18003c3dc  mov     rbx, rdx
0x18003c3df  test    rdx, rdx
0x18003c3e2  jnz     short loc_18003C406
0x18003c3e4  mov     rcx, [rsp+38h]; this
0x18003c3e9  mov     ebx, 80004003h
0x18003c3ee  mov     r9d, ebx; char *
0x18003c3f1  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003c3f8  mov     edx, 4Bh ; 'K'; void *
0x18003c3fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c402  mov     eax, ebx
0x18003c404  jmp     short loc_18003C468
0x18003c406  test    rdi, rdi
0x18003c409  jnz     short loc_18003C42B
0x18003c40b  mov     rcx, [rsp+38h]; this
0x18003c410  mov     ebx, 80004003h
0x18003c415  mov     r9d, ebx; char *
0x18003c418  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003c41f  lea     edx, [rdi+4Ch]; void *
0x18003c422  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c427  mov     eax, ebx
0x18003c429  jmp     short loc_18003C468
0x18003c42b  mov     [rsp+38h+var_14], 5
0x18003c433  mov     [rsp+38h+var_18], 0; int
0x18003c43b  lea     rdx, [rsp+38h+var_18]
0x18003c440  lea     rcx, [rsp+38h+var_14]
0x18003c445  call    cs:__imp_GetUpdateResults
0x18003c44b  mov     rcx, [rsp+38h]; this
0x18003c450  test    eax, eax
0x18003c452  js      short loc_18003C480
0x18003c454  mov     eax, [rsp+38h+var_14]
0x18003c458  mov     [rbx], eax
0x18003c45a  mov     eax, [rsp+38h+var_18]
0x18003c45e  mov     [rdi], eax
0x18003c460  xor     eax, eax
0x18003c462  jmp     short loc_18003C468
0x18003c464  mov     eax, [rsp+38h+var_18]
0x18003c468  mov     rcx, [rsp+38h+var_10]
0x18003c46d  xor     rcx, rsp; StackCookie
0x18003c470  call    __security_check_cookie
0x18003c475  mov     rbx, [rsp+38h+arg_0]
0x18003c47a  add     rsp, 30h
0x18003c47e  pop     rdi
0x18003c47f  retn
0x18003c480  mov     r9d, eax; char *
0x18003c483  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003c48a  mov     edx, 50h ; 'P'; void *
0x18003c48f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
