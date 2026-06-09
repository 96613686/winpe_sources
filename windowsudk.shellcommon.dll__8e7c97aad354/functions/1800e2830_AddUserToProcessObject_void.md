# AddUserToProcessObject(void *)

- ea: `0x1800e2830`
- end: `0x1800e2980`
- name: `?AddUserToProcessObject@@YAJPEAX@Z`
- size: `336`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180033cd4`
- `0x1800e4ec8`
- `0x1800e7960`

## callees

- `0x18005200c`
- `0x180086f44`
- `0x1800a14f8`
- `0x1800e2830`
- `0x1800e2988`
- `0x1800e34bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e2842`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e2842`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e28f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e28f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e2894`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e2894`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e2852`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e2852`

## string_xrefs

- `0x1800e2870`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800e28bb`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800e2905`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800e2942`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
__int64 __fastcall AddUserToProcessObject(void *a1)
{
  DWORD CurrentProcessId; // eax
  char *v3; // rbx
  const char *v4; // r9
  unsigned int LastError; // edi
  int v6; // eax
  const char *v7; // r9
  int v8; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  char *v13; // [rsp+40h] [rbp+18h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  v3 = (char *)OpenProcess(0x60400u, 0, CurrentProcessId);
  v13 = v3;
  if ( ((unsigned __int64)(v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v6 = AddUserToHandle(v3, a1, 0x101400u);
    LastError = v6;
    if ( v6 >= 0 )
    {
      TokenHandle = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      if ( OpenProcessToken(v3, 0x60008u, &TokenHandle) )
      {
        v8 = AddUserToHandle(TokenHandle, a1, 0xEu);
        LastError = v8;
        if ( v8 >= 0 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          LastError = 0;
          goto LABEL_12;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x87,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
          (const char *)(unsigned int)v8,
          v10);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x85,
                      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                      v7);
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
        (const char *)(unsigned int)v6,
        v10);
    }
LABEL_12:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
    return LastError;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x80,
                (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                v4);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  return LastError;
}

```

## disassembly

```asm
0x1800e2830  mov     [rsp+arg_0], rbx
0x1800e2835  mov     [rsp+arg_18], rsi
0x1800e283a  push    rdi; int
0x1800e283b  sub     rsp, 20h
0x1800e283f  mov     rsi, rcx
0x1800e2842  call    cs:__imp_GetCurrentProcessId
0x1800e2848  xor     edx, edx; bInheritHandle
0x1800e284a  mov     ecx, 60400h; dwDesiredAccess
0x1800e284f  mov     r8d, eax; dwProcessId
0x1800e2852  call    cs:__imp_OpenProcess
0x1800e2858  mov     rbx, rax
0x1800e285b  mov     [rsp+28h+arg_10], rax
0x1800e2860  inc     rax
0x1800e2863  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e2869  jnz     short loc_1800E289F
0x1800e286b  mov     rcx, [rsp+28h]; this
0x1800e2870  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800e2877  mov     edx, 80h; void *
0x1800e287c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e2881  lea     rcx, [rbx-1]
0x1800e2885  mov     edi, eax
0x1800e2887  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800e288b  ja      loc_1800E296E
0x1800e2891  mov     rcx, rbx; hObject
0x1800e2894  call    cs:__imp_CloseHandle
0x1800e289a  jmp     loc_1800E296E
0x1800e289f  mov     r8d, 101400h; unsigned int
0x1800e28a5  mov     rdx, rsi; void *
0x1800e28a8  mov     rcx, rbx; Handle
0x1800e28ab  call    ?AddUserToHandle@@YAJPEAX0K@Z; AddUserToHandle(void *,void *,ulong)
0x1800e28b0  mov     edi, eax
0x1800e28b2  test    eax, eax
0x1800e28b4  jns     short loc_1800E28D4
0x1800e28b6  mov     rcx, [rsp+28h]; this
0x1800e28bb  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800e28c2  mov     r9d, eax; char *
0x1800e28c5  mov     edx, 82h; void *
0x1800e28ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e28cf  jmp     loc_1800E2964
0x1800e28d4  xor     edx, edx
0x1800e28d6  mov     [rsp+28h+TokenHandle], 0
0x1800e28df  lea     rcx, [rsp+28h+TokenHandle]
0x1800e28e4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800e28e9  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800e28ee  mov     edx, 60008h; DesiredAccess
0x1800e28f3  mov     rcx, rbx; ProcessHandle
0x1800e28f6  call    cs:__imp_OpenProcessToken
0x1800e28fc  test    eax, eax
0x1800e28fe  jnz     short loc_1800E2924
0x1800e2900  mov     rcx, [rsp+28h]; this
0x1800e2905  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800e290c  mov     edx, 85h; void *
0x1800e2911  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e2916  mov     edi, eax
0x1800e2918  lea     rcx, [rsp+28h+TokenHandle]
0x1800e291d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e2922  jmp     short loc_1800E2964
0x1800e2924  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x1800e2929  mov     r8d, 0Eh; unsigned int
0x1800e292f  mov     rdx, rsi; void *
0x1800e2932  call    ?AddUserToHandle@@YAJPEAX0K@Z; AddUserToHandle(void *,void *,ulong)
0x1800e2937  mov     edi, eax
0x1800e2939  test    eax, eax
0x1800e293b  jns     short loc_1800E2958
0x1800e293d  mov     rcx, [rsp+28h]; this
0x1800e2942  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800e2949  mov     r9d, eax; char *
0x1800e294c  mov     edx, 87h; void *
0x1800e2951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2956  jmp     short loc_1800E2918
0x1800e2958  lea     rcx, [rsp+28h+TokenHandle]
0x1800e295d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e2962  xor     edi, edi
0x1800e2964  lea     rcx, [rsp+28h+arg_10]
0x1800e2969  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e296e  mov     rbx, [rsp+28h+arg_0]
0x1800e2973  mov     eax, edi
0x1800e2975  mov     rsi, [rsp+28h+arg_18]
0x1800e297a  add     rsp, 20h
0x1800e297e  pop     rdi
0x1800e297f  retn
```
