# VmbusPipeClientReadyForChannelNotification

- ea: `0x1800071f0`
- end: `0x180007365`
- name: `VmbusPipeClientReadyForChannelNotification`
- size: `373`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x1800024e0`
- `0x1800030ae`
- `0x180004054`
- `0x18000526c`
- `0x18000565c`
- `0x180006d50`
- `0x180006eac`
- `0x1800071f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180007329`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180007329`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007223`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007223`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18000729b`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18000729b`

## string_xrefs

- `0x1800072ad`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`

## pseudocode

```c
__int64 __fastcall VmbusPipeClientReadyForChannelNotification(__int64 a1, int a2)
{
  __int64 v2; // rbx
  bool v5; // zf
  __int128 v6; // xmm0
  int v7; // eax
  int v8; // eax
  unsigned int v9; // r8d
  struct _TP_WORK *v10; // rcx
  int v12; // [rsp+20h] [rbp-1D8h]
  char *v13; // [rsp+28h] [rbp-1D0h]
  bool v14; // [rsp+30h] [rbp-1C8h] BYREF
  __int64 v15; // [rsp+38h] [rbp-1C0h] BYREF
  _DWORD v16[4]; // [rsp+40h] [rbp-1B8h] BYREF
  __int128 v17; // [rsp+50h] [rbp-1A8h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v2 = a1 + 616;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 616));
  v5 = *(_BYTE *)(a1 + 664) == 0;
  v15 = v2;
  if ( v5 )
  {
    *(_BYTE *)(a1 + 665) = 1;
    if ( *(_QWORD *)(a1 + 8)
      || (memset_0(v16, 0, 0x1A0u),
          v6 = *(_OWORD *)(a1 + 576),
          v16[0] = 416,
          v16[2] = 0,
          v17 = v6,
          wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
            a1 + 8,
            0),
          (v7 = CM_Register_Notification(v16, a1, OnChannelNotification, a1 + 8)) == 0) )
    {
      if ( a2 && !*(_BYTE *)(a1 + 666) )
      {
        v14 = 0;
        v8 = IsChannelOffered((struct ClientChannelParameters *)(a1 + 16), &v14);
        if ( v8 >= 0 )
        {
          if ( v14 )
          {
            v10 = *(struct _TP_WORK **)(a1 + 672);
            *(_DWORD *)(a1 + 668) = 1;
            SubmitThreadpoolWork(v10);
            *(_BYTE *)(a1 + 666) = 1;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x3A1, v9, (const char *)(unsigned int)v8, v12);
        }
      }
    }
    else
    {
      LODWORD(v13) = v7;
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0x395,
        (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
        (const char *)0x1F,
        (unsigned int)"%d",
        v13);
    }
  }
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
}

```

## disassembly

```asm
0x1800071f0  mov     [rsp+arg_8], rbx
0x1800071f5  mov     [rsp+arg_10], rsi
0x1800071fa  push    rdi
0x1800071fb  sub     rsp, 1F0h
0x180007202  mov     rax, cs:__security_cookie
0x180007209  xor     rax, rsp
0x18000720c  mov     [rsp+1F8h+var_18], rax
0x180007214  lea     rbx, [rcx+268h]
0x18000721b  mov     rdi, rcx
0x18000721e  mov     rcx, rbx; lpCriticalSection
0x180007221  mov     esi, edx
0x180007223  call    cs:__imp_EnterCriticalSection
0x180007229  cmp     byte ptr [rdi+298h], 0
0x180007230  mov     [rsp+1F8h+var_1C0], rbx
0x180007235  jnz     loc_180007336
0x18000723b  lea     rbx, [rdi+8]
0x18000723f  mov     byte ptr [rdi+299h], 1
0x180007246  cmp     qword ptr [rbx], 0
0x18000724a  jnz     loc_1800072D6
0x180007250  xor     edx, edx; Val
0x180007252  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x180007257  mov     r8d, 1A0h; Size
0x18000725d  call    memset_0
0x180007262  movups  xmm0, xmmword ptr [rdi+240h]
0x180007269  xor     edx, edx
0x18000726b  mov     [rsp+1F8h+var_1B8], 1A0h
0x180007273  mov     rcx, rbx
0x180007276  mov     [rsp+1F8h+var_1B0], 0
0x18000727e  movdqu  [rsp+1F8h+var_1A8], xmm0
0x180007284  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)
0x180007289  mov     r9, rbx
0x18000728c  lea     r8, OnChannelNotification
0x180007293  mov     rdx, rdi
0x180007296  lea     rcx, [rsp+1F8h+var_1B8]
0x18000729b  call    cs:__imp_CM_Register_Notification
0x1800072a1  test    eax, eax
0x1800072a3  jz      short loc_1800072D6
0x1800072a5  mov     rcx, [rsp+1F8h]; this
0x1800072ad  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x1800072b4  mov     dword ptr [rsp+1F8h+var_1D0], eax; char *
0x1800072b8  mov     r9d, 1Fh; char *
0x1800072be  lea     rax, aD; "%d"
0x1800072c5  mov     edx, 395h; void *
0x1800072ca  mov     qword ptr [rsp+1F8h+var_1D8], rax; unsigned int
0x1800072cf  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800072d4  jmp     short loc_180007336
0x1800072d6  test    esi, esi
0x1800072d8  jz      short loc_180007336
0x1800072da  cmp     byte ptr [rdi+29Ah], 0
0x1800072e1  jnz     short loc_180007336
0x1800072e3  lea     rcx, [rdi+10h]; struct ClientChannelParameters *
0x1800072e7  mov     [rsp+1F8h+var_1C8], 0
0x1800072ec  lea     rdx, [rsp+1F8h+var_1C8]; bool *
0x1800072f1  call    ?IsChannelOffered@@YAJPEAUClientChannelParameters@@PEA_N@Z; IsChannelOffered(ClientChannelParameters *,bool *)
0x1800072f6  test    eax, eax
0x1800072f8  jns     short loc_180007311
0x1800072fa  mov     rcx, [rsp+1F8h]; this
0x180007302  mov     r9d, eax; char *
0x180007305  mov     edx, 3A1h; void *
0x18000730a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000730f  jmp     short loc_180007336
0x180007311  cmp     [rsp+1F8h+var_1C8], 0
0x180007316  jz      short loc_180007336
0x180007318  mov     rcx, [rdi+2A0h]; pwk
0x18000731f  mov     dword ptr [rdi+29Ch], 1
0x180007329  call    cs:__imp_SubmitThreadpoolWork
0x18000732f  mov     byte ptr [rdi+29Ah], 1
0x180007336  lea     rcx, [rsp+1F8h+var_1C0]
0x18000733b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180007340  mov     rcx, [rsp+1F8h+var_18]
0x180007348  xor     rcx, rsp; StackCookie
0x18000734b  call    __security_check_cookie
0x180007350  lea     r11, [rsp+1F8h+var_8]
0x180007358  mov     rbx, [r11+18h]
0x18000735c  mov     rsi, [r11+20h]
0x180007360  mov     rsp, r11
0x180007363  pop     rdi
0x180007364  retn
```
