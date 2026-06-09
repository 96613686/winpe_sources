# VmbusPipeClientWaitChannelInternal(_GUID const *,_GUID const *,uint,_VMBUS_PIPE_CHANNEL_INFO *)

- ea: `0x180001d30`
- end: `0x180001f5e`
- name: `?VmbusPipeClientWaitChannelInternal@@YAJPEBU_GUID@@0IPEAU_VMBUS_PIPE_CHANNEL_INFO@@@Z`
- size: `558`
- prototype: `int(const struct _GUID *, const struct _GUID *, unsigned int, struct _VMBUS_PIPE_CHANNEL_INFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x180007490`

## callees

- `0x1800017e0`
- `0x180001b44`
- `0x180001d30`
- `0x180001f64`
- `0x1800024e0`
- `0x1800030ae`
- `0x180004014`
- `0x18000526c`
- `0x180005d94`
- `0x180005db8`
- `0x180006eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001d97`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001d97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001ee4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001ee4`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180001e4b`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180001e4b`

## string_xrefs

- `0x180001d75`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180001db7`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180001e72`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180001eb8`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180001ef5`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall VmbusPipeClientWaitChannelInternal(
        const struct _GUID *a1,
        const struct _GUID *a2,
        DWORD a3,
        const struct _GUID *a4)
{
  HANDLE EventW; // rbx
  const char *v10; // r9
  int v11; // ebx
  int v12; // eax
  int LastError; // eax
  int v14; // eax
  int v15; // edi
  DWORD v16; // eax
  const char *v17; // r9
  unsigned int v18; // [rsp+20h] [rbp-E0h]
  char *v19; // [rsp+28h] [rbp-D8h]
  bool v20; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v21; // [rsp+38h] [rbp-C8h] BYREF
  const struct _GUID *v22[3]; // [rsp+40h] [rbp-C0h] BYREF
  char v23; // [rsp+58h] [rbp-A8h]
  int v24; // [rsp+59h] [rbp-A7h]
  __int16 v25; // [rsp+5Dh] [rbp-A3h]
  char v26; // [rsp+5Fh] [rbp-A1h]
  HANDLE v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v29[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v30; // [rsp+80h] [rbp-80h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  if ( !a4 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x210,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
             (const char *)0x57,
             v18);
  EventW = CreateEventW(0, 1, 0, 0);
  v21 = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v22[0] = a4;
    v22[1] = a1;
    v22[2] = a2;
    v27 = EventW;
    memset_0(v29, 0, 0x1A0u);
    v29[0] = 416;
    v29[2] = 0;
    v30 = *a1;
    v28 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
      &v28,
      0);
    v12 = CM_Register_Notification(v29, v22, OnDeviceNotification, &v28);
    if ( v12 )
    {
      LODWORD(v19) = v12;
      LastError = wil::details::in1diag3::Return_Win32Msg(
                    retaddr,
                    (void *)0x229,
                    (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
                    (const char *)0x1F,
                    (unsigned int)"%d",
                    v19);
    }
    else
    {
      v20 = 0;
      v14 = IsChannelOffered(v22, &v20);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22D,
          (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
          (const char *)(unsigned int)v14,
          v18);
        wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>(&v28);
        v11 = v15;
        goto LABEL_16;
      }
      if ( v20 || (v16 = WaitForSingleObject(EventW, a3)) == 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>(&v28);
        v11 = 0;
        goto LABEL_16;
      }
      if ( v16 == 258 )
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x236,
                      (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
                      (const char *)0x5B4,
                      v18);
      else
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x23C,
                      (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
                      v17);
    }
    v11 = LastError;
    wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>(&v28);
  }
  else
  {
    v11 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x214,
            (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
            v10);
  }
LABEL_16:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
  return v11;
}

```

## disassembly

```asm
0x180001d30  push    rbp
0x180001d32  push    rbx
0x180001d33  push    rsi
0x180001d34  push    rdi
0x180001d35  push    r14
0x180001d37  push    r15
0x180001d39  lea     rbp, [rsp-128h]
0x180001d41  sub     rsp, 228h
0x180001d48  mov     rax, cs:__security_cookie
0x180001d4f  xor     rax, rsp
0x180001d52  mov     [rbp+150h+var_40], rax
0x180001d59  mov     rdi, r9
0x180001d5c  mov     esi, r8d
0x180001d5f  mov     r15, rdx
0x180001d62  mov     r14, rcx
0x180001d65  test    r9, r9
0x180001d68  jnz     short loc_180001D8B
0x180001d6a  mov     rcx, [rbp+158h]; this
0x180001d71  lea     r9d, [rdi+57h]; char *
0x180001d75  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180001d7c  mov     edx, 210h; void *
0x180001d81  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180001d86  jmp     loc_180001F3F
0x180001d8b  xor     r9d, r9d; lpName
0x180001d8e  xor     r8d, r8d; bInitialState
0x180001d91  lea     edx, [r9+1]; bManualReset
0x180001d95  xor     ecx, ecx; lpEventAttributes
0x180001d97  call    cs:__imp_CreateEventW
0x180001d9d  mov     rbx, rax
0x180001da0  mov     [rsp+250h+var_218], rax
0x180001da5  inc     rax
0x180001da8  test    rax, 0FFFFFFFFFFFFFFFEh
0x180001dae  jnz     short loc_180001DCF
0x180001db0  mov     rcx, [rbp+158h]; this
0x180001db7  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180001dbe  mov     edx, 214h; void *
0x180001dc3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180001dc8  mov     ebx, eax
0x180001dca  jmp     loc_180001F33
0x180001dcf  mov     [rsp+250h+var_1F8], 0
0x180001dd4  xor     eax, eax
0x180001dd6  mov     [rsp+250h+var_1F7], eax
0x180001dda  mov     [rsp+250h+var_1F3], ax
0x180001ddf  mov     [rsp+250h+var_1F1], al
0x180001de3  mov     [rsp+250h+var_210], rdi
0x180001de8  mov     [rsp+250h+var_208], r14
0x180001ded  mov     [rsp+250h+var_200], r15
0x180001df2  mov     [rsp+250h+var_1F0], rbx
0x180001df7  mov     edi, 1A0h
0x180001dfc  mov     r8d, edi; Size
0x180001dff  xor     edx, edx; Val
0x180001e01  lea     rcx, [rsp+250h+var_1E0]; void *
0x180001e06  call    memset_0
0x180001e0b  mov     [rsp+250h+var_1E0], edi
0x180001e0f  mov     [rsp+250h+var_1D8], 0
0x180001e17  movups  xmm0, xmmword ptr [r14]
0x180001e1b  movdqu  [rbp+150h+var_1D0], xmm0
0x180001e20  mov     [rsp+250h+var_1E8], 0
0x180001e29  xor     edx, edx
0x180001e2b  lea     rcx, [rsp+250h+var_1E8]
0x180001e30  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)
0x180001e35  lea     r9, [rsp+250h+var_1E8]
0x180001e3a  lea     r8, OnDeviceNotification
0x180001e41  lea     rdx, [rsp+250h+var_210]
0x180001e46  lea     rcx, [rsp+250h+var_1E0]
0x180001e4b  call    cs:__imp_CM_Register_Notification
0x180001e51  test    eax, eax
0x180001e53  jz      short loc_180001E94
0x180001e55  mov     rcx, [rbp+158h]; this
0x180001e5c  mov     dword ptr [rsp+250h+var_228], eax; char *
0x180001e60  lea     rax, aD; "%d"
0x180001e67  mov     qword ptr [rsp+250h+var_230], rax; unsigned int
0x180001e6c  mov     r9d, 1Fh; char *
0x180001e72  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180001e79  mov     edx, 229h; void *
0x180001e7e  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180001e83  mov     ebx, eax
0x180001e85  lea     rcx, [rsp+250h+var_1E8]
0x180001e8a  call    ??1?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>(void)
0x180001e8f  jmp     loc_180001F33
0x180001e94  mov     [rsp+250h+var_220], 0
0x180001e99  lea     rdx, [rsp+250h+var_220]; bool *
0x180001e9e  lea     rcx, [rsp+250h+var_210]; struct ClientChannelParameters *
0x180001ea3  call    ?IsChannelOffered@@YAJPEAUClientChannelParameters@@PEA_N@Z; IsChannelOffered(ClientChannelParameters *,bool *)
0x180001ea8  mov     edi, eax
0x180001eaa  test    eax, eax
0x180001eac  jns     short loc_180001ED8
0x180001eae  mov     rcx, [rbp+158h]; this
0x180001eb5  mov     r9d, eax; char *
0x180001eb8  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180001ebf  mov     edx, 22Dh; void *
0x180001ec4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001ec9  nop
0x180001eca  lea     rcx, [rsp+250h+var_1E8]
0x180001ecf  call    ??1?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>(void)
0x180001ed4  mov     ebx, edi
0x180001ed6  jmp     short loc_180001F33
0x180001ed8  cmp     [rsp+250h+var_220], 0
0x180001edd  jnz     short loc_180001F27
0x180001edf  mov     edx, esi; dwMilliseconds
0x180001ee1  mov     rcx, rbx; hHandle
0x180001ee4  call    cs:__imp_WaitForSingleObject
0x180001eea  test    eax, eax
0x180001eec  jz      short loc_180001F27
0x180001eee  mov     rcx, [rbp+158h]; this
0x180001ef5  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180001efc  cmp     eax, 102h
0x180001f01  jz      short loc_180001F12
0x180001f03  mov     edx, 23Ch; void *
0x180001f08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180001f0d  jmp     loc_180001E83
0x180001f12  mov     r9d, 5B4h; char *
0x180001f18  mov     edx, 236h; void *
0x180001f1d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180001f22  jmp     loc_180001E83
0x180001f27  lea     rcx, [rsp+250h+var_1E8]
0x180001f2c  call    ??1?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>(void)
0x180001f31  xor     ebx, ebx
0x180001f33  lea     rcx, [rsp+250h+var_218]
0x180001f38  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180001f3d  mov     eax, ebx
0x180001f3f  mov     rcx, [rbp+150h+var_40]
0x180001f46  xor     rcx, rsp; StackCookie
0x180001f49  call    __security_check_cookie
0x180001f4e  add     rsp, 228h
0x180001f55  pop     r15
0x180001f57  pop     r14
0x180001f59  pop     rdi
0x180001f5a  pop     rsi
0x180001f5b  pop     rbx
0x180001f5c  pop     rbp
0x180001f5d  retn
```
