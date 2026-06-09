# NotificationServiceImpl::Disconnect(void)

- ea: `0x18006cd00`
- end: `0x18006cf7c`
- name: `?Disconnect@NotificationServiceImpl@@UEAAJXZ`
- size: `636`
- prototype: `__int64 __fastcall(NotificationServiceImpl *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007440`
- `0x18000ba54`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001bde4`
- `0x18006cd00`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006ce07`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006ce07`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006cf17`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006cf17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cdc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cdc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006cd6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006cd6c`

## string_xrefs

- `0x18006ce5f`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006cecd`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall NotificationServiceImpl::Disconnect(NotificationServiceImpl *this)
{
  void *v2; // r14
  __int64 v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // ebx
  PVOID *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v18; // [rsp+20h] [rbp-58h]
  __int64 v19; // [rsp+30h] [rbp-48h] BYREF
  int v20[2]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  v19 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 8LL))(*((_QWORD *)this + 13));
  v2 = (void *)*((_QWORD *)this + 17);
  v3 = *((_QWORD *)this + 14);
  v4 = 0;
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    *(_QWORD *)v20 = 0;
    v19 = v3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20, v5, v6, v7);
    v4 = v3;
  }
  *((_DWORD *)this + 36) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 )
  {
    if ( (byte_1800AFD82 & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(&WPNCORE_PROVIDER_GUID_Context, WPNPRV_NOTSVC_DISCONNECT, v8, 1, v20);
    ResetEvent(v2);
    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, 21);
    v13 = v9;
    if ( v9 >= 0 )
      goto LABEL_28;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v9);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4EE,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v13,
      v18);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_26;
    v15 = 107;
    v16 = v13;
    goto LABEL_25;
  }
  v13 = -2147019873;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, 2147947423LL);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x4F4,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
    (const char *)0x8007139FLL,
    v18);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v15 = 109;
    v16 = 2147947423LL;
LABEL_25:
    WPP_SF_d(v14[2], v15, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v16);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_26:
  if ( v2 != (void *)-1LL )
  {
    SetEvent(v2);
LABEL_28:
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 && *((_BYTE *)v14 + 25) >= 6u )
    WPP_SF_d(v14[2], 110, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19, v10, v11, v12);
  return v13;
}

```

## disassembly

```asm
0x18006cd00  mov     [rsp+arg_8], rbx
0x18006cd05  mov     [rsp+arg_10], rbp
0x18006cd0a  push    rsi
0x18006cd0b  push    rdi
0x18006cd0c  push    r12
0x18006cd0e  push    r13
0x18006cd10  push    r14
0x18006cd12  sub     rsp, 50h
0x18006cd16  mov     rax, cs:__security_cookie
0x18006cd1d  xor     rax, rsp
0x18006cd20  mov     [rsp+78h+var_30], rax
0x18006cd25  mov     rbx, rcx
0x18006cd28  lea     r12, WPP_GLOBAL_Control
0x18006cd2f  lea     r13, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006cd36  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cd3d  cmp     rcx, r12
0x18006cd40  jz      short loc_18006CD5F
0x18006cd42  test    byte ptr [rcx+1Ch], 2
0x18006cd46  jz      short loc_18006CD5F
0x18006cd48  cmp     byte ptr [rcx+19h], 6
0x18006cd4c  jb      short loc_18006CD5F
0x18006cd4e  mov     edx, 69h ; 'i'
0x18006cd53  mov     r8, r13
0x18006cd56  mov     rcx, [rcx+10h]
0x18006cd5a  call    WPP_SF_
0x18006cd5f  mov     [rsp+78h+var_48], 0
0x18006cd68  lea     rcx, [rbx+10h]; lpCriticalSection
0x18006cd6c  call    cs:__imp_EnterCriticalSection
0x18006cd72  mov     rcx, [rbx+68h]
0x18006cd76  mov     rax, [rcx]
0x18006cd79  mov     rax, [rax+8]
0x18006cd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cd82  mov     r14, [rbx+88h]
0x18006cd89  mov     rdi, [rbx+70h]
0x18006cd8d  xor     esi, esi
0x18006cd8f  test    rdi, rdi
0x18006cd92  jz      short loc_18006CDBB
0x18006cd94  mov     rax, [rdi]
0x18006cd97  mov     rcx, rdi
0x18006cd9a  mov     rax, [rax+8]
0x18006cd9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cda3  nop
0x18006cda4  mov     qword ptr [rsp+78h+var_40], rsi
0x18006cda9  mov     [rsp+78h+var_48], rdi
0x18006cdae  lea     rcx, [rsp+78h+var_40]
0x18006cdb3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cdb8  mov     rsi, rdi
0x18006cdbb  mov     dword ptr [rbx+90h], 0
0x18006cdc5  lea     rcx, [rbx+10h]; lpCriticalSection
0x18006cdc9  call    cs:__imp_LeaveCriticalSection
0x18006cdcf  test    rsi, rsi
0x18006cdd2  jz      loc_18006CE94
0x18006cdd8  test    cs:byte_1800AFD82, 10h
0x18006cddf  jz      short loc_18006CE04
0x18006cde1  lea     rax, [rsp+78h+var_40]
0x18006cde6  mov     qword ptr [rsp+78h+var_58], rax; int
0x18006cdeb  mov     r9d, 1
0x18006cdf1  lea     rdx, WPNPRV_NOTSVC_DISCONNECT
0x18006cdf8  lea     rcx, WPNCORE_PROVIDER_GUID_Context
0x18006cdff  call    McGenEventWrite_EventWriteTransfer
0x18006ce04  mov     rcx, r14; hEvent
0x18006ce07  call    cs:__imp_ResetEvent
0x18006ce0d  mov     rax, [rsi]
0x18006ce10  mov     edx, 15h
0x18006ce15  mov     rcx, rsi
0x18006ce18  mov     rax, [rax+20h]
0x18006ce1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce21  mov     ebx, eax
0x18006ce23  test    eax, eax
0x18006ce25  jns     loc_18006CF1D
0x18006ce2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ce32  cmp     rcx, r12
0x18006ce35  jz      short loc_18006CE57
0x18006ce37  test    byte ptr [rcx+1Ch], 2
0x18006ce3b  jz      short loc_18006CE57
0x18006ce3d  cmp     byte ptr [rcx+19h], 2
0x18006ce41  jb      short loc_18006CE57
0x18006ce43  mov     edx, 6Ah ; 'j'
0x18006ce48  mov     r9d, eax
0x18006ce4b  mov     r8, r13
0x18006ce4e  mov     rcx, [rcx+10h]
0x18006ce52  call    WPP_SF_d
0x18006ce57  mov     rcx, [rsp+78h]; this
0x18006ce5c  mov     r9d, ebx; char *
0x18006ce5f  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006ce66  mov     edx, 4EEh; void *
0x18006ce6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006ce70  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ce77  cmp     rcx, r12
0x18006ce7a  jz      loc_18006CF0E
0x18006ce80  test    byte ptr [rcx+1Ch], 80h
0x18006ce84  jz      loc_18006CF0E
0x18006ce8a  mov     edx, 6Bh ; 'k'
0x18006ce8f  mov     r9d, ebx
0x18006ce92  jmp     short loc_18006CEFB
0x18006ce94  mov     ebx, 8007139Fh
0x18006ce99  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cea0  cmp     rcx, r12
0x18006cea3  jz      short loc_18006CEC5
0x18006cea5  test    byte ptr [rcx+1Ch], 2
0x18006cea9  jz      short loc_18006CEC5
0x18006ceab  cmp     byte ptr [rcx+19h], 2
0x18006ceaf  jb      short loc_18006CEC5
0x18006ceb1  mov     edx, 6Ch ; 'l'
0x18006ceb6  mov     r9d, ebx
0x18006ceb9  mov     r8, r13
0x18006cebc  mov     rcx, [rcx+10h]
0x18006cec0  call    WPP_SF_d
0x18006cec5  mov     rcx, [rsp+78h]; this
0x18006ceca  mov     r9d, ebx; char *
0x18006cecd  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006ced4  mov     edx, 4F4h; void *
0x18006ced9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006cede  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cee5  cmp     rcx, r12
0x18006cee8  jz      short loc_18006CF0E
0x18006ceea  test    byte ptr [rcx+1Ch], 80h
0x18006ceee  jz      short loc_18006CF0E
0x18006cef0  mov     edx, 6Dh ; 'm'
0x18006cef5  mov     r9d, 8007139Fh
0x18006cefb  mov     r8, r13
0x18006cefe  mov     rcx, [rcx+10h]
0x18006cf02  call    WPP_SF_d
0x18006cf07  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cf0e  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18006cf12  jz      short loc_18006CF24
0x18006cf14  mov     rcx, r14; hEvent
0x18006cf17  call    cs:__imp_SetEvent
0x18006cf1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cf24  cmp     rcx, r12
0x18006cf27  jz      short loc_18006CF4A
0x18006cf29  test    byte ptr [rcx+1Ch], 2
0x18006cf2d  jz      short loc_18006CF4A
0x18006cf2f  cmp     byte ptr [rcx+19h], 6
0x18006cf33  jb      short loc_18006CF4A
0x18006cf35  mov     edx, 6Eh ; 'n'
0x18006cf3a  mov     r9d, ebx
0x18006cf3d  mov     r8, r13
0x18006cf40  mov     rcx, [rcx+10h]
0x18006cf44  call    WPP_SF_d
0x18006cf49  nop
0x18006cf4a  lea     rcx, [rsp+78h+var_48]
0x18006cf4f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cf54  mov     eax, ebx
0x18006cf56  mov     rcx, [rsp+78h+var_30]
0x18006cf5b  xor     rcx, rsp; StackCookie
0x18006cf5e  call    __security_check_cookie
0x18006cf63  lea     r11, [rsp+78h+var_28]
0x18006cf68  mov     rbx, [r11+38h]
0x18006cf6c  mov     rbp, [r11+40h]
0x18006cf70  mov     rsp, r11
0x18006cf73  pop     r14
0x18006cf75  pop     r13
0x18006cf77  pop     r12
0x18006cf79  pop     rdi
0x18006cf7a  pop     rsi
0x18006cf7b  retn
```
