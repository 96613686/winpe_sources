# WaitForEventIfPresent(ushort const *,ulong)

- ea: `0x18001815c`
- end: `0x1800181e6`
- name: `?WaitForEventIfPresent@@YAJPEBGK@Z`
- size: `138`
- prototype: `int(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800183f4`

## callees

- `0x180005cd8`
- `0x180007528`
- `0x18000934c`
- `0x18000b82c`
- `0x18001815c`
- `0x1800183b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001817d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001817d`

## string_xrefs

- `0x1800181d0`: `shell\lib\comtaskserverutil.cpp`
- `0x180018166`: `Global\ShellCreateObjectTaskReadyEvent`

## pseudocode

```c
__int64 __fastcall WaitForEventIfPresent(const unsigned __int16 *a1)
{
  wil::details *v1; // rax
  wil::details *v2; // rcx
  void *v3; // rdx
  int v4; // ebx
  int LastErrorFailHr; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  wil::details *v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  v1 = (wil::details *)OpenEventW(0x100002u, 0, L"Global\\ShellCreateObjectTaskReadyEvent");
  if ( v1 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v8,
      v1);
    v4 = 0;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v2);
    v4 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 && LastErrorFailHr != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (int)"shell\\lib\\comtaskserverutil.cpp",
        (const char *)(unsigned int)LastErrorFailHr);
      goto LABEL_6;
    }
  }
  if ( v4 >= 0 )
    _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(&v8);
  v4 = 0;
LABEL_6:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v8,
    v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001815c  mov     [rsp+arg_0], rcx
0x180018161  push    rbx; int
0x180018162  sub     rsp, 20h
0x180018166  lea     r8, aGlobalShellcre; "Global\\ShellCreateObjectTaskReadyEvent"
0x18001816d  mov     [rsp+28h+arg_0], 0
0x180018176  xor     edx, edx; bInheritHandle
0x180018178  mov     ecx, 100002h; dwDesiredAccess
0x18001817d  call    cs:__imp_OpenEventW
0x180018183  test    rax, rax
0x180018186  jz      short loc_1800181B9
0x180018188  mov     rdx, rax
0x18001818b  lea     rcx, [rsp+28h+arg_0]
0x180018190  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180018195  xor     ebx, ebx
0x180018197  test    ebx, ebx
0x180018199  js      short loc_1800181A5
0x18001819b  lea     rcx, [rsp+28h+arg_0]
0x1800181a0  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x1800181a5  xor     ebx, ebx
0x1800181a7  lea     rcx, [rsp+28h+arg_0]
0x1800181ac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800181b1  mov     eax, ebx
0x1800181b3  add     rsp, 20h
0x1800181b7  pop     rbx
0x1800181b8  retn
0x1800181b9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800181be  mov     ebx, eax
0x1800181c0  test    eax, eax
0x1800181c2  jns     short loc_180018197
0x1800181c4  cmp     eax, 80070002h
0x1800181c9  jz      short loc_180018197
0x1800181cb  mov     rcx, [rsp+28h]; this
0x1800181d0  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x1800181d7  mov     r9d, eax; char *
0x1800181da  mov     edx, 47h ; 'G'; void *
0x1800181df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181e4  jmp     short loc_1800181A7
```
