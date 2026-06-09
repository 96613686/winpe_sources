# VmbusPipeClientRegisterChannelNotificationInternal(_GUID const *,_GUID const *,uint,void (*)(void *,_VMBUS_PIPE_CHANNEL_INFO *,_VMBUS_PIPE_CHANNEL_NOTIFICATION_TYPE),void *,HVMBUS_PIPE_NOTIFICATION__ * *)

- ea: `0x180006a10`
- end: `0x180006bdf`
- name: `?VmbusPipeClientRegisterChannelNotificationInternal@@YAJPEBU_GUID@@0IP6AXPEAXPEAU_VMBUS_PIPE_CHANNEL_INFO@@W4_VMBUS_PIPE_CHANNEL_NOTIFICATION_TYPE@@@Z1PEAPEAUHVMBUS_PIPE_NOTIFICATION__@@@Z`
- size: `463`
- prototype: `int __fastcall(const struct _GUID *, const struct _GUID *, int, void (__high *)(void *, struct _VMBUS_PIPE_CHANNEL_INFO *, enum _VMBUS_PIPE_CHANNEL_NOTIFICATION_TYPE), void *, struct HVMBUS_PIPE_NOTIFICATION__ **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x180007370`

## callees

- `0x180001f64`
- `0x1800024e0`
- `0x180002510`
- `0x1800030ae`
- `0x180003c54`
- `0x180003e54`
- `0x18000414c`
- `0x18000416c`
- `0x180005d94`
- `0x180006a10`
- `0x180006e78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180006af8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180006af8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180006b1a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180006b1a`

## string_xrefs

- `0x180006b3b`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180006b80`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180006bae`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall VmbusPipeClientRegisterChannelNotificationInternal(
        const struct _GUID *a1,
        const struct _GUID *a2,
        int a3,
        void (__high *a4)(void *, struct _VMBUS_PIPE_CHANNEL_INFO *, enum _VMBUS_PIPE_CHANNEL_NOTIFICATION_TYPE),
        void *a5,
        struct HVMBUS_PIPE_NOTIFICATION__ **a6)
{
  ChannelNotificationContext *v10; // rax
  ChannelNotificationContext *v11; // rbx
  ChannelNotificationContext *v12; // rax
  ChannelNotificationContext *v13; // rbx
  PTP_WORK ThreadpoolWork; // rax
  const char *v15; // r9
  struct _TP_WORK *v16; // rsi
  PTP_WORK v17; // rdi
  int LastError; // eax
  int v20; // ebx
  unsigned int v21; // [rsp+20h] [rbp-58h] BYREF
  ChannelNotificationContext *v22; // [rsp+28h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a1 && a2 && a4 )
  {
    v10 = (ChannelNotificationContext *)operator new(0x2E0u, (const struct std::nothrow_t *)std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, 0x2E0u);
      v12 = ChannelNotificationContext::ChannelNotificationContext(v11);
      v22 = v12;
      v13 = v12;
      if ( v12 )
      {
        *((struct _GUID *)v12 + 36) = *a1;
        *((struct _GUID *)v12 + 37) = *a2;
        *((_QWORD *)v12 + 90) = a4;
        *((_QWORD *)v12 + 91) = a5;
        *((_DWORD *)v12 + 152) = a3;
        *((_QWORD *)v12 + 2) = (char *)v12 + 56;
        *((_QWORD *)v12 + 3) = (char *)v12 + 576;
        *((_QWORD *)v12 + 4) = (char *)v12 + 592;
        ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)NotificationDispatcherCallback, v12, 0);
        v16 = (struct _TP_WORK *)*((_QWORD *)v13 + 84);
        v17 = ThreadpoolWork;
        if ( v16 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v21);
          CloseThreadpoolWork(v16);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v21);
        }
        *((_QWORD *)v13 + 84) = v17;
        if ( v17 )
        {
          *a6 = v13;
          wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::operator=((char *)v13 + 656);
          wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(
            &v22,
            0);
          return 0;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x2EC,
                      (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
                      v15);
        goto LABEL_13;
      }
    }
    else
    {
      v22 = 0;
    }
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x2D9,
                  (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
                  (const char *)8,
                  v21);
LABEL_13:
    v20 = LastError;
    wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(&v22, 0);
    return v20;
  }
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x2D3,
           (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
           (const char *)0x57,
           v21);
}

```

## disassembly

```asm
0x180006a10  push    rbx
0x180006a12  push    rbp
0x180006a13  push    rsi
0x180006a14  push    rdi
0x180006a15  push    r14
0x180006a17  push    r15
0x180006a19  sub     rsp, 48h
0x180006a1d  mov     rax, cs:__security_cookie
0x180006a24  xor     rax, rsp
0x180006a27  mov     [rsp+78h+var_48], rax
0x180006a2c  mov     r14, [rsp+78h+arg_28]
0x180006a34  mov     rdi, r9
0x180006a37  mov     r15d, r8d
0x180006a3a  mov     rsi, rdx
0x180006a3d  mov     rbp, rcx
0x180006a40  test    rcx, rcx
0x180006a43  jz      loc_180006BA9
0x180006a49  test    rdx, rdx
0x180006a4c  jz      loc_180006BA9
0x180006a52  test    r9, r9
0x180006a55  jz      loc_180006BA9
0x180006a5b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006a62  mov     ecx, 2E0h; unsigned __int64
0x180006a67  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006a6c  mov     rbx, rax
0x180006a6f  test    rax, rax
0x180006a72  jz      loc_180006B72
0x180006a78  xor     edx, edx; Val
0x180006a7a  mov     r8d, 2E0h; Size
0x180006a80  mov     rcx, rax; void *
0x180006a83  call    memset_0
0x180006a88  mov     rcx, rbx; this
0x180006a8b  call    ??0ChannelNotificationContext@@QEAA@XZ; ChannelNotificationContext::ChannelNotificationContext(void)
0x180006a90  mov     [rsp+78h+var_50], rax
0x180006a95  mov     rbx, rax
0x180006a98  test    rax, rax
0x180006a9b  jz      loc_180006B7B
0x180006aa1  movups  xmm0, xmmword ptr [rbp+0]
0x180006aa5  lea     rdx, [rax+240h]
0x180006aac  xor     r8d, r8d; pcbe
0x180006aaf  lea     rcx, [rax+250h]
0x180006ab6  movdqu  xmmword ptr [rdx], xmm0
0x180006aba  movups  xmm1, xmmword ptr [rsi]
0x180006abd  movdqu  xmmword ptr [rcx], xmm1
0x180006ac1  mov     [rax+2D0h], rdi
0x180006ac8  mov     rax, [rsp+78h+arg_20]
0x180006ad0  mov     [rbx+2D8h], rax
0x180006ad7  lea     rax, [rbx+38h]
0x180006adb  mov     [rbx+260h], r15d
0x180006ae2  mov     [rbx+10h], rax
0x180006ae6  mov     [rbx+18h], rdx
0x180006aea  mov     rdx, rbx; pv
0x180006aed  mov     [rbx+20h], rcx
0x180006af1  lea     rcx, NotificationDispatcherCallback; pfnwk
0x180006af8  call    cs:__imp_CreateThreadpoolWork
0x180006afe  mov     rsi, [rbx+2A0h]
0x180006b05  mov     rdi, rax
0x180006b08  test    rsi, rsi
0x180006b0b  jz      short loc_180006B2A
0x180006b0d  lea     rcx, [rsp+78h+var_58]; this
0x180006b12  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180006b17  mov     rcx, rsi; pwk
0x180006b1a  call    cs:__imp_CloseThreadpoolWork
0x180006b20  lea     rcx, [rsp+78h+var_58]; this
0x180006b25  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006b2a  mov     [rbx+2A0h], rdi
0x180006b31  test    rdi, rdi
0x180006b34  jnz     short loc_180006B4E
0x180006b36  mov     rcx, [rsp+78h]; this
0x180006b3b  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180006b42  mov     edx, 2ECh; void *
0x180006b47  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006b4c  jmp     short loc_180006B97
0x180006b4e  lea     rcx, [rbx+290h]
0x180006b55  mov     [r14], rbx
0x180006b58  lea     rdx, [rsp+78h+var_50]
0x180006b5d  call    ??4?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::operator=(wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>> &&)
0x180006b62  xor     edx, edx
0x180006b64  lea     rcx, [rsp+78h+var_50]
0x180006b69  call    ?reset@?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAAXPEAUChannelNotificationContext@@@Z; wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(ChannelNotificationContext *)
0x180006b6e  xor     eax, eax
0x180006b70  jmp     short loc_180006BC5
0x180006b72  mov     [rsp+78h+var_50], 0
0x180006b7b  mov     rcx, [rsp+78h]; this
0x180006b80  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180006b87  mov     r9d, 8; char *
0x180006b8d  mov     edx, 2D9h; void *
0x180006b92  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006b97  xor     edx, edx
0x180006b99  lea     rcx, [rsp+78h+var_50]
0x180006b9e  mov     ebx, eax
0x180006ba0  call    ?reset@?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAAXPEAUChannelNotificationContext@@@Z; wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(ChannelNotificationContext *)
0x180006ba5  mov     eax, ebx
0x180006ba7  jmp     short loc_180006BC5
0x180006ba9  mov     rcx, [rsp+78h]; this
0x180006bae  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180006bb5  mov     r9d, 57h ; 'W'; char *
0x180006bbb  mov     edx, 2D3h; void *
0x180006bc0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006bc5  mov     rcx, [rsp+78h+var_48]
0x180006bca  xor     rcx, rsp; StackCookie
0x180006bcd  call    __security_check_cookie
0x180006bd2  add     rsp, 48h
0x180006bd6  pop     r15
0x180006bd8  pop     r14
0x180006bda  pop     rdi
0x180006bdb  pop     rsi
0x180006bdc  pop     rbp
0x180006bdd  pop     rbx
0x180006bde  retn
```
