# SHIsCurrentAppElevated

- ea: `0x18000fb88`
- end: `0x18000fc35`
- name: `SHIsCurrentAppElevated`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002bb0`

## callees

- `0x18000e9b0`
- `0x18000fb88`
- `0x18000fc3c`
- `0x180012550`

## import_xrefs

- `ntdll!NtClose` at `0x18000fc15`
- `ntdll!NtClose` at `0x18000fc15`
- `ntdll!NtOpenProcessToken` at `0x18000fbc1`
- `ntdll!NtOpenProcessToken` at `0x18000fbc1`

## pseudocode

```c
__int64 __fastcall SHIsCurrentAppElevated(_DWORD *a1)
{
  NTSTATUS v2; // eax
  int v3; // ebx
  void *v4; // rcx
  NTSTATUS v5; // eax
  bool v7; // [rsp+20h] [rbp-28h] BYREF
  bool v8; // [rsp+21h] [rbp-27h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-20h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  v2 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  v3 = ResultFromWin32FromStatus(v2);
  if ( v3 >= 0 )
  {
    v4 = TokenHandle;
    *a1 = 0;
    v7 = 0;
    v8 = 0;
    v5 = _LUAIsElevatedToken(v4, &v7, &v8);
    v3 = ResultFromWin32FromStatus(v5);
    if ( v3 >= 0 )
      *a1 = v7;
    NtClose(TokenHandle);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000fb88  mov     [rsp+arg_8], rbx
0x18000fb8d  push    rdi
0x18000fb8e  sub     rsp, 40h
0x18000fb92  mov     rax, cs:__security_cookie
0x18000fb99  xor     rax, rsp
0x18000fb9c  mov     [rsp+48h+var_18], rax
0x18000fba1  mov     rdi, rcx
0x18000fba4  mov     dword ptr [rcx], 0
0x18000fbaa  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000fbae  mov     [rsp+48h+TokenHandle], 0
0x18000fbb7  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18000fbbc  mov     edx, 8; DesiredAccess
0x18000fbc1  call    cs:__imp_NtOpenProcessToken
0x18000fbc7  mov     ecx, eax; int
0x18000fbc9  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18000fbce  mov     ebx, eax
0x18000fbd0  test    eax, eax
0x18000fbd2  js      short loc_18000FC1B
0x18000fbd4  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18000fbd9  lea     r8, [rsp+48h+var_27]; bool *
0x18000fbde  lea     rdx, [rsp+48h+var_28]; bool *
0x18000fbe3  mov     dword ptr [rdi], 0
0x18000fbe9  mov     [rsp+48h+var_28], 0
0x18000fbee  mov     [rsp+48h+var_27], 0
0x18000fbf3  call    ?_LUAIsElevatedToken@@YAJPEAXPEA_N1@Z; _LUAIsElevatedToken(void *,bool *,bool *)
0x18000fbf8  mov     ecx, eax; int
0x18000fbfa  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18000fbff  mov     ebx, eax
0x18000fc01  test    eax, eax
0x18000fc03  js      short loc_18000FC10
0x18000fc05  xor     eax, eax
0x18000fc07  cmp     [rsp+48h+var_28], al
0x18000fc0b  setnz   al
0x18000fc0e  mov     [rdi], eax
0x18000fc10  mov     rcx, [rsp+48h+TokenHandle]; Handle
0x18000fc15  call    cs:__imp_NtClose
0x18000fc1b  mov     eax, ebx
0x18000fc1d  mov     rcx, [rsp+48h+var_18]
0x18000fc22  xor     rcx, rsp; StackCookie
0x18000fc25  call    __security_check_cookie
0x18000fc2a  mov     rbx, [rsp+48h+arg_8]
0x18000fc2f  add     rsp, 40h
0x18000fc33  pop     rdi
0x18000fc34  retn
```
