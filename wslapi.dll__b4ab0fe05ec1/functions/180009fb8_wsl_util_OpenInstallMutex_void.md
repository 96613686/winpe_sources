# wsl::util::OpenInstallMutex(void)

- ea: `0x180009fb8`
- end: `0x18000a021`
- name: `?OpenInstallMutex@util@wsl@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `105`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000a054`

## callees

- `0x180009058`
- `0x180009fb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009fe4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009fe4`

## pseudocode

```c
_QWORD *__fastcall wsl::util::OpenInstallMutex(_QWORD *a1)
{
  HANDLE Mutex; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  Mutex = CreateMutexExW(0, L"Global\\LiftedWslInstalMutex", 0, 0x100000u);
  *a1 = Mutex;
  if ( (((unsigned __int64)Mutex + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xC5,
      (int)"onecore\\vm\\wsl\\lxss\\wslutil\\wslutil.cpp",
      v3);
  return a1;
}

```

## disassembly

```asm
0x180009fb8  mov     [rsp+arg_0], rcx
0x180009fbd  push    rbx
0x180009fbe  sub     rsp, 30h
0x180009fc2  mov     rbx, rcx
0x180009fc5  mov     [rsp+38h+var_18], 0
0x180009fcd  xor     eax, eax
0x180009fcf  mov     [rcx], rax
0x180009fd2  mov     r9d, 100000h; dwDesiredAccess
0x180009fd8  xor     r8d, r8d; dwFlags
0x180009fdb  lea     rdx, Name; "Global\\LiftedWslInstalMutex"
0x180009fe2  xor     ecx, ecx; lpMutexAttributes
0x180009fe4  call    cs:__imp_CreateMutexExW
0x180009fea  mov     [rbx], rax
0x180009fed  mov     [rsp+38h+var_18], 1
0x180009ff5  inc     rax
0x180009ff8  test    rax, 0FFFFFFFFFFFFFFFEh
0x180009ffe  jnz     short loc_18000A017
0x18000a000  mov     rcx, [rsp+38h]; this
0x18000a005  lea     r8, aOnecoreVmWslLx_0; "onecore\\vm\\wsl\\lxss\\wslutil\\wsluti"...
0x18000a00c  mov     edx, 0C5h; void *
0x18000a011  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000a017  mov     rax, rbx
0x18000a01a  add     rsp, 30h
0x18000a01e  pop     rbx
0x18000a01f  retn
```
