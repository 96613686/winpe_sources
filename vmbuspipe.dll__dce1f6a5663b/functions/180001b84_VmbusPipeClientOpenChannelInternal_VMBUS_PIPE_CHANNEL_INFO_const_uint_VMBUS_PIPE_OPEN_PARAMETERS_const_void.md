# VmbusPipeClientOpenChannelInternal(_VMBUS_PIPE_CHANNEL_INFO const *,uint,VMBUS_PIPE_OPEN_PARAMETERS const *,void * *)

- ea: `0x180001b84`
- end: `0x180001cd1`
- name: `?VmbusPipeClientOpenChannelInternal@@YAJPEBU_VMBUS_PIPE_CHANNEL_INFO@@IPEBUVMBUS_PIPE_OPEN_PARAMETERS@@PEAPEAX@Z`
- size: `333`
- prototype: `int __fastcall(const struct _VMBUS_PIPE_CHANNEL_INFO *, int, const struct VMBUS_PIPE_OPEN_PARAMETERS *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800071a0`

## callees

- `0x1800017e0`
- `0x180001b84`
- `0x180001cd8`
- `0x1800024e0`
- `0x180005d94`
- `0x180006390`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001c2b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001c2b`

## string_xrefs

- `0x180001c5c`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180001ca4`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180001be8`: `%s\incoming_size=%#x,outgoing_size=%#x`

## pseudocode

```c
int __fastcall VmbusPipeClientOpenChannelInternal(
        const struct _VMBUS_PIPE_CHANNEL_INFO *a1,
        int a2,
        const struct VMBUS_PIPE_OPEN_PARAMETERS *a3,
        void **a4)
{
  __int64 v6; // rdx
  HANDLE FileW; // rax
  int LastErrorMsg; // ebx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-268h]
  _QWORD v11[2]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( *(_DWORD *)a3 != 1 || *((_DWORD *)a3 + 1) < 0x10u || !a1 || !*(_WORD *)a1 )
  {
    v6 = 335;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
             (const char *)0x57,
             dwCreationDisposition);
  }
  dwCreationDisposition = *((_DWORD *)a3 + 2);
  if ( StringCchPrintfW(FileName, 0x104u, L"%s\\incoming_size=%#x,outgoing_size=%#x", a1) < 0 )
  {
    v6 = 346;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
             (const char *)0x57,
             dwCreationDisposition);
  }
  FileW = CreateFileW(FileName, 0x1F01FFu, 0, 0, 4u, a2 | 0x100000u, 0);
  v11[0] = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v11[0] = -1;
    *a4 = FileW;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v11);
    return 0;
  }
  else
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x167,
                     (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
                     "%ls",
                     (const char *)FileName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v11);
    return LastErrorMsg;
  }
}

```

## disassembly

```asm
0x180001b84  push    rbx
0x180001b86  push    rsi
0x180001b87  push    rdi
0x180001b88  sub     rsp, 270h
0x180001b8f  mov     rax, cs:__security_cookie
0x180001b96  xor     rax, rsp
0x180001b99  mov     [rsp+288h+var_28], rax
0x180001ba1  cmp     dword ptr [r8], 1
0x180001ba5  mov     rdi, r9
0x180001ba8  mov     ebx, edx
0x180001baa  jnz     loc_180001C97
0x180001bb0  cmp     dword ptr [r8+4], 10h
0x180001bb5  jb      loc_180001C97
0x180001bbb  xor     esi, esi
0x180001bbd  test    rcx, rcx
0x180001bc0  jz      loc_180001C97
0x180001bc6  cmp     [rcx], si
0x180001bc9  jz      loc_180001C97
0x180001bcf  mov     eax, [r8+0Ch]
0x180001bd3  mov     r9, rcx
0x180001bd6  mov     [rsp+288h+dwFlagsAndAttributes], eax
0x180001bda  lea     rcx, [rsp+288h+FileName]; unsigned __int16 *
0x180001bdf  mov     eax, [r8+8]
0x180001be3  mov     edx, 104h; unsigned __int64
0x180001be8  lea     r8, aSIncomingSizeX; "%s\\incoming_size=%#x,outgoing_size=%#x"
0x180001bef  mov     [rsp+288h+dwCreationDisposition], eax
0x180001bf3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001bf8  test    eax, eax
0x180001bfa  jns     short loc_180001C06
0x180001bfc  mov     edx, 15Ah
0x180001c01  jmp     loc_180001C9C
0x180001c06  mov     [rsp+288h+hTemplateFile], rsi; hTemplateFile
0x180001c0b  lea     rcx, [rsp+288h+FileName]; lpFileName
0x180001c10  bts     ebx, 14h
0x180001c14  xor     r9d, r9d; lpSecurityAttributes
0x180001c17  mov     [rsp+288h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180001c1b  xor     r8d, r8d; dwShareMode
0x180001c1e  mov     edx, 1F01FFh; dwDesiredAccess
0x180001c23  mov     [rsp+288h+dwCreationDisposition], 4; dwCreationDisposition
0x180001c2b  call    cs:__imp_CreateFileW
0x180001c31  mov     [rsp+288h+var_248], rax
0x180001c36  lea     rcx, [rax+1]
0x180001c3a  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180001c41  jnz     short loc_180001C7D
0x180001c43  mov     rcx, [rsp+288h]; this
0x180001c4b  lea     rax, [rsp+288h+FileName]
0x180001c50  lea     r9, aLs; "%ls"
0x180001c57  mov     qword ptr [rsp+288h+dwCreationDisposition], rax; char *
0x180001c5c  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180001c63  mov     edx, 167h; void *
0x180001c68  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180001c6d  lea     rcx, [rsp+288h+var_248]
0x180001c72  mov     ebx, eax
0x180001c74  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180001c79  mov     eax, ebx
0x180001c7b  jmp     short loc_180001CB6
0x180001c7d  lea     rcx, [rsp+288h+var_248]
0x180001c82  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFFh
0x180001c8b  mov     [rdi], rax
0x180001c8e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180001c93  xor     eax, eax
0x180001c95  jmp     short loc_180001CB6
0x180001c97  mov     edx, 14Fh; void *
0x180001c9c  mov     rcx, [rsp+288h]; this
0x180001ca4  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180001cab  mov     r9d, 57h ; 'W'; char *
0x180001cb1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180001cb6  mov     rcx, [rsp+288h+var_28]
0x180001cbe  xor     rcx, rsp; StackCookie
0x180001cc1  call    __security_check_cookie
0x180001cc6  add     rsp, 270h
0x180001ccd  pop     rdi
0x180001cce  pop     rsi
0x180001ccf  pop     rbx
0x180001cd0  retn
```
