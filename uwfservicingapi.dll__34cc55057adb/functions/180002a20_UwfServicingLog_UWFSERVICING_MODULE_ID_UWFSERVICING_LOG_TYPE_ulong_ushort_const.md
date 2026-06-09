# UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)

- ea: `0x180002a20`
- end: `0x180002c82`
- name: `?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ`
- size: `610`
- prototype: `__int64(int, int, DWORD, const wchar_t *, ...)`
- caller_count: `10`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180003130`
- `0x1800031c0`
- `0x180003358`
- `0x18000348c`
- `0x180003540`
- `0x18000370c`
- `0x18000399c`
- `0x180003c6c`
- `0x1800045d0`
- `0x180004a70`

## callees

- `0x1800023a0`
- `0x180002410`
- `0x18000266c`
- `0x180002a20`
- `0x180005175`
- `0x1800051a0`

## import_xrefs

- `msvcrt!vswprintf_s` at `0x180002ac6`
- `msvcrt!vswprintf_s` at `0x180002ac6`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002b50`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002b50`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180002b12`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180002b12`

## string_xrefs

- `0x180002bb1`: `UwfUpdateAgent`

## pseudocode

```c
__int64 UwfServicingLog(int a1, int a2, DWORD a3, const wchar_t *a4, ...)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  ULONGLONG v9; // rbx
  signed int v10; // eax
  unsigned int v11; // ebx
  ULONGLONG RegHandle; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v14; // [rsp+38h] [rbp-C8h]
  __int64 v15; // [rsp+40h] [rbp-C0h]
  EVENT_DESCRIPTOR v16; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Buffer[1024]; // [rsp+60h] [rbp-A0h] BYREF
  va_list ArgList; // [rsp+8C0h] [rbp+7C0h] BYREF

  va_start(ArgList, a4);
  v5 = a1;
  v6 = a2;
  if ( dword_18000C83C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18000C83C);
    if ( dword_18000C83C == -1 )
    {
      qword_18000C790 = (__int64)L"UwfServicingXmgr";
      xmmword_18000C770 = UwfServicingXmgrGenInfo;
      qword_18000C7B8 = (__int64)L"UwfUpdateAgent";
      qword_18000C7E0 = (__int64)L"UwfservicingShell";
      xmmword_18000C780 = UwfServicingXmgrGenError;
      qword_18000C808 = (__int64)L"UwfservicingSvc";
      qword_18000C830 = (__int64)L"UwfservicingScr";
      xmmword_18000C798 = UwfServicingWinUpdtGenInfo;
      xmmword_18000C7A8 = UwfServicingWinUpdtGenError;
      xmmword_18000C7C0 = UwfServicingShellGenInfo;
      xmmword_18000C7D0 = UwfServicingShellGenError;
      xmmword_18000C7E8 = UwfServicingSvcGenInfo;
      xmmword_18000C7F8 = UwfServicingSvcGenError;
      xmmword_18000C810 = UwfServicingScrGenInfo;
      xmmword_18000C820 = UwfServicingScrGenError;
      Init_thread_footer(&dword_18000C83C);
    }
  }
  if ( (unsigned int)v6 >= 2 || (unsigned int)v5 >= 5 )
    return 2147942487LL;
  v15 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  vswprintf_s(Buffer, 0x3FFu, a4, ArgList);
  RegHandle = 0;
  v7 = 40 * v5;
  v8 = v7 + 16 * v6;
  v9 = *(_QWORD *)((char *)&xmmword_18000C770 + v7 + 32);
  v16 = *(EVENT_DESCRIPTOR *)((char *)&xmmword_18000C770 + v8);
  v14 = EventRegister(&UWF_ETW_PROVIDER, 0, 0, &RegHandle);
  v10 = mslib::EventLogger<UwfEtwProvider>::Log(&RegHandle, &v16, v9, (__int64)Buffer, a3);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( RegHandle )
    EventUnregister(RegHandle);
  return v11;
}

```

## disassembly

```asm
0x180002a20  mov     [rsp-8+Format], r9
0x180002a25  push    rbp
0x180002a26  push    rbx
0x180002a27  push    rsi
0x180002a28  push    rdi
0x180002a29  push    r14
0x180002a2b  lea     rbp, [rsp-770h]
0x180002a33  sub     rsp, 870h
0x180002a3a  mov     rax, cs:__security_cookie
0x180002a41  xor     rax, rsp
0x180002a44  mov     [rbp+790h+var_30], rax
0x180002a4b  mov     r9d, cs:_tls_index
0x180002a52  mov     esi, r8d
0x180002a55  mov     rax, gs:58h
0x180002a5e  movsxd  rbx, ecx
0x180002a61  mov     ecx, 4
0x180002a66  movsxd  rdi, edx
0x180002a69  mov     rax, [rax+r9*8]
0x180002a6d  mov     r9d, [rcx+rax]
0x180002a71  cmp     cs:dword_18000C83C, r9d
0x180002a78  jg      loc_180002B7C
0x180002a7e  cmp     edi, 2
0x180002a81  jnb     loc_180002B5A
0x180002a87  cmp     ebx, 5
0x180002a8a  jnb     loc_180002B5A
0x180002a90  xor     edx, edx; Val
0x180002a92  mov     [rsp+890h+var_850], 0
0x180002a9b  mov     r8d, 800h; Size
0x180002aa1  lea     rcx, [rsp+890h+Buffer]; void *
0x180002aa6  lea     r14, [rbp+790h+ArgList]
0x180002aad  call    memset_0
0x180002ab2  mov     r8, [rbp+790h+Format]; Format
0x180002ab9  lea     rcx, [rsp+890h+Buffer]; Buffer
0x180002abe  mov     r9, r14; ArgList
0x180002ac1  mov     edx, 3FFh; BufferCount
0x180002ac6  call    cs:__imp_vswprintf_s
0x180002acc  lea     rcx, [rbx+rbx*4]
0x180002ad0  mov     [rsp+890h+RegHandle], 0
0x180002ad9  lea     rbx, ds:0[rcx*8]
0x180002ae1  mov     rax, rdi
0x180002ae4  lea     rcx, xmmword_18000C770
0x180002aeb  shl     rax, 4
0x180002aef  add     rax, rbx
0x180002af2  lea     r9, [rsp+890h+RegHandle]; RegHandle
0x180002af7  mov     rbx, [rbx+rcx+20h]
0x180002afc  xor     r8d, r8d; CallbackContext
0x180002aff  xor     edx, edx; EnableCallback
0x180002b01  movups  xmm0, xmmword ptr [rax+rcx]
0x180002b05  lea     rcx, UWF_ETW_PROVIDER; ProviderId
0x180002b0c  movdqu  xmmword ptr [rsp+890h+var_848.Id], xmm0
0x180002b12  call    cs:__imp_EventRegister
0x180002b18  lea     r9, [rsp+890h+Buffer]
0x180002b1d  mov     [rsp+890h+var_870], esi
0x180002b21  mov     r8, rbx
0x180002b24  mov     [rsp+890h+var_858], eax
0x180002b28  lea     rdx, [rsp+890h+var_848]
0x180002b2d  lea     rcx, [rsp+890h+RegHandle]
0x180002b32  call    ?Log@?$EventLogger@VUwfEtwProvider@@@mslib@@QEBAKAEBU_EVENT_DESCRIPTOR@@PEBG1K@Z; mslib::EventLogger<UwfEtwProvider>::Log(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ulong)
0x180002b37  mov     ebx, eax
0x180002b39  test    eax, eax
0x180002b3b  jle     short loc_180002B46
0x180002b3d  movzx   ebx, ax
0x180002b40  or      ebx, 80070000h
0x180002b46  mov     rcx, [rsp+890h+RegHandle]; RegHandle
0x180002b4b  test    rcx, rcx
0x180002b4e  jz      short loc_180002B56
0x180002b50  call    cs:__imp_EventUnregister
0x180002b56  mov     eax, ebx
0x180002b58  jmp     short loc_180002B5F
0x180002b5a  mov     eax, 80070057h
0x180002b5f  mov     rcx, [rbp+790h+var_30]
0x180002b66  xor     rcx, rsp; StackCookie
0x180002b69  call    __security_check_cookie
0x180002b6e  add     rsp, 870h
0x180002b75  pop     r14
0x180002b77  pop     rdi
0x180002b78  pop     rsi
0x180002b79  pop     rbx
0x180002b7a  pop     rbp
0x180002b7b  retn
0x180002b7c  lea     rcx, dword_18000C83C
0x180002b83  call    _Init_thread_header
0x180002b88  cmp     cs:dword_18000C83C, 0FFFFFFFFh
0x180002b8f  jnz     loc_180002A7E
0x180002b95  movups  xmm0, cs:UwfServicingXmgrGenInfo
0x180002b9c  lea     rax, aUwfservicingxm; "UwfServicingXmgr"
0x180002ba3  movups  xmm1, cs:UwfServicingXmgrGenError
0x180002baa  mov     cs:qword_18000C790, rax
0x180002bb1  lea     rax, aUwfupdateagent; "UwfUpdateAgent"
0x180002bb8  movdqu  cs:xmmword_18000C770, xmm0
0x180002bc0  mov     cs:qword_18000C7B8, rax
0x180002bc7  lea     rax, aUwfservicingsh; "UwfservicingShell"
0x180002bce  movups  xmm0, cs:UwfServicingWinUpdtGenInfo
0x180002bd5  mov     cs:qword_18000C7E0, rax
0x180002bdc  lea     rax, aUwfservicingsv; "UwfservicingSvc"
0x180002be3  movdqu  cs:xmmword_18000C780, xmm1
0x180002beb  mov     cs:qword_18000C808, rax
0x180002bf2  lea     rax, aUwfservicingsc; "UwfservicingScr"
0x180002bf9  movups  xmm1, cs:UwfServicingWinUpdtGenError
0x180002c00  lea     rcx, dword_18000C83C
0x180002c07  mov     cs:qword_18000C830, rax
0x180002c0e  movdqu  cs:xmmword_18000C798, xmm0
0x180002c16  movups  xmm0, cs:UwfServicingShellGenInfo
0x180002c1d  movdqu  cs:xmmword_18000C7A8, xmm1
0x180002c25  movups  xmm1, cs:UwfServicingShellGenError
0x180002c2c  movdqu  cs:xmmword_18000C7C0, xmm0
0x180002c34  movups  xmm0, cs:UwfServicingSvcGenInfo
0x180002c3b  movdqu  cs:xmmword_18000C7D0, xmm1
0x180002c43  movups  xmm1, cs:UwfServicingSvcGenError
0x180002c4a  movdqu  cs:xmmword_18000C7E8, xmm0
0x180002c52  movups  xmm0, cs:UwfServicingScrGenInfo
0x180002c59  movdqu  cs:xmmword_18000C7F8, xmm1
0x180002c61  movups  xmm1, cs:UwfServicingScrGenError
0x180002c68  movdqu  cs:xmmword_18000C810, xmm0
0x180002c70  movdqu  cs:xmmword_18000C820, xmm1
0x180002c78  call    _Init_thread_footer
0x180002c7d  jmp     loc_180002A7E
```
