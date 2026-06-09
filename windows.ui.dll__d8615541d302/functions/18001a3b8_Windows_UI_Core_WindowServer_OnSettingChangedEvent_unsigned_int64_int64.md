# Windows::UI::Core::WindowServer::OnSettingChangedEvent(unsigned __int64,__int64)

- ea: `0x18001a3b8`
- end: `0x18001a56d`
- name: `?OnSettingChangedEvent@WindowServer@Core@UI@Windows@@QEAAH_K_J@Z`
- size: `437`
- prototype: `int(Windows::UI::Core::WindowServer *__hidden this, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018350`

## callees

- `0x180017a60`
- `0x180017a90`
- `0x18001a3b8`
- `0x18001a574`
- `0x18004e5cc`
- `0x18005f1a4`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a446`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a4cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a446`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a4cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a420`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a4a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a420`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a4a9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a3f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a3f9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18001a55e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18001a55e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::UI::Core::WindowServer::OnSettingChangedEvent(
        Windows::UI::Core::WindowServer *this,
        __int64 a2,
        const WCHAR *a3)
{
  char *v6; // r14
  __int64 v7; // rbx
  CSettingChangedEventArgs *v8; // rdi
  CSettingChangedEventArgs *v9; // rax
  CSettingChangedEventArgs *v10; // rcx
  __int64 v11; // rbx
  volatile int *v12; // rdx
  __int64 v13; // r8
  Windows::UI::Core::WindowServer *v15; // [rsp+30h] [rbp-20h] BYREF
  CSettingChangedEventArgs *v16; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v17[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int8 v18; // [rsp+A0h] [rbp+50h] BYREF
  CSettingChangedEventArgs *v19; // [rsp+A8h] [rbp+58h]

  v18 = 0;
  if ( a3 && CompareStringOrdinal(a3, -1, L"UserInteractionMode", -1, 1) == 2 )
  {
    PostMessageW(*((HWND *)this + 433), 0x720u, 0, 0);
  }
  else
  {
    v6 = (char *)this + 1800;
    if ( *((_QWORD *)this + 225) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)this + 226);
      if ( *(_QWORD *)v6 )
        v7 = (__int64)(*(_QWORD *)(*(_QWORD *)v6 + 24LL) - *(_QWORD *)(*(_QWORD *)v6 + 16LL)) >> 3;
      else
        v7 = 0;
      if ( this != (Windows::UI::Core::WindowServer *)-1808LL )
        ReleaseSRWLockExclusive((PSRWLOCK)this + 226);
      if ( v7 )
      {
        v8 = 0;
        v19 = 0;
        v9 = (CSettingChangedEventArgs *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
        if ( v9 )
        {
          v8 = CSettingChangedEventArgs::CSettingChangedEventArgs(v9);
          v19 = v8;
          v10 = v8;
        }
        else
        {
          v10 = 0;
        }
        if ( v10 )
        {
          (*(void (__fastcall **)(CSettingChangedEventArgs *, __int64, const WCHAR *))(*(_QWORD *)v10 + 72LL))(
            v10,
            a2,
            a3);
          v16 = v8;
          v15 = this;
          v11 = 0;
          AcquireSRWLockExclusive((PSRWLOCK)this + 226);
          if ( *(_QWORD *)v6 )
          {
            Microsoft::WRL::Details::SafeUnknownIncrementReference(
              (Microsoft::WRL::Details *)(*(_QWORD *)v6 + 12LL),
              v12);
            v11 = v13;
          }
          if ( this != (Windows::UI::Core::WindowServer *)-1808LL )
            ReleaseSRWLockExclusive((PSRWLOCK)this + 226);
          if ( v11 )
          {
            v17[0] = &v15;
            v17[1] = &v16;
            Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_20f494fe0baa1532db1c50100a579e9f_,Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowOcclusionChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
              v17,
              v11,
              (char *)this + 1800);
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v11);
          }
          (*(void (__fastcall **)(__int64, unsigned __int8 *))(*((_QWORD *)v8 + 2) + 48LL))((__int64)v8 + 16, &v18);
        }
        if ( v8 )
          (*(void (__fastcall **)(CSettingChangedEventArgs *))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
  }
  return v18;
}

```

## disassembly

```asm
0x18001a3b8  mov     [rsp-38h+arg_0], rbx
0x18001a3bd  push    rbp
0x18001a3be  push    rsi
0x18001a3bf  push    rdi
0x18001a3c0  push    r12
0x18001a3c2  push    r13
0x18001a3c4  push    r14
0x18001a3c6  push    r15
0x18001a3c8  mov     rbp, rsp
0x18001a3cb  sub     rsp, 50h
0x18001a3cf  mov     r12, r8
0x18001a3d2  mov     r13, rdx
0x18001a3d5  mov     r15, rcx
0x18001a3d8  mov     [rbp+arg_10], 0
0x18001a3dc  test    r8, r8
0x18001a3df  jz      short loc_18001A408
0x18001a3e1  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x18001a3e9  or      edx, 0FFFFFFFFh; cchCount1
0x18001a3ec  mov     r9d, edx; cchCount2
0x18001a3ef  lea     r8, String2; "UserInteractionMode"
0x18001a3f6  mov     rcx, r12; lpString1
0x18001a3f9  call    cs:__imp_CompareStringOrdinal
0x18001a3ff  cmp     eax, 2
0x18001a402  jz      loc_18001A54C
0x18001a408  lea     r14, [r15+708h]
0x18001a40f  cmp     qword ptr [r14], 0
0x18001a413  jz      loc_18001A500
0x18001a419  lea     rsi, [r14+8]
0x18001a41d  mov     rcx, rsi; SRWLock
0x18001a420  call    cs:__imp_AcquireSRWLockExclusive
0x18001a426  mov     rax, [r14]
0x18001a429  test    rax, rax
0x18001a42c  jz      loc_18001A566
0x18001a432  mov     rbx, [rax+18h]
0x18001a436  sub     rbx, [rax+10h]
0x18001a43a  sar     rbx, 3
0x18001a43e  test    rsi, rsi
0x18001a441  jz      short loc_18001A44C
0x18001a443  mov     rcx, rsi; SRWLock
0x18001a446  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a44c  test    rbx, rbx
0x18001a44f  jz      loc_18001A500
0x18001a455  xor     edi, edi
0x18001a457  mov     [rbp+arg_18], rdi
0x18001a45b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a462  lea     ecx, [rdi+40h]; unsigned __int64
0x18001a465  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a46a  test    rax, rax
0x18001a46d  jz      loc_18001A545
0x18001a473  mov     rcx, rax; this
0x18001a476  call    ??0CSettingChangedEventArgs@@QEAA@XZ; CSettingChangedEventArgs::CSettingChangedEventArgs(void)
0x18001a47b  mov     rdi, rax
0x18001a47e  mov     [rbp+arg_18], rax
0x18001a482  mov     rcx, rax
0x18001a485  test    rcx, rcx
0x18001a488  jz      short loc_18001A4EB
0x18001a48a  mov     rax, [rcx]
0x18001a48d  mov     r8, r12
0x18001a490  mov     rdx, r13
0x18001a493  mov     rax, [rax+48h]
0x18001a497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a49c  mov     [rbp+var_18], rdi
0x18001a4a0  mov     [rbp+var_20], r15
0x18001a4a4  xor     ebx, ebx
0x18001a4a6  mov     rcx, rsi; SRWLock
0x18001a4a9  call    cs:__imp_AcquireSRWLockExclusive
0x18001a4af  mov     r8, [r14]
0x18001a4b2  test    r8, r8
0x18001a4b5  jz      short loc_18001A4C3
0x18001a4b7  lea     rcx, [r8+0Ch]; this
0x18001a4bb  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18001a4c0  mov     rbx, r8
0x18001a4c3  test    rsi, rsi
0x18001a4c6  jz      short loc_18001A4D1
0x18001a4c8  mov     rcx, rsi; SRWLock
0x18001a4cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a4d1  test    rbx, rbx
0x18001a4d4  jnz     short loc_18001A51C
0x18001a4d6  lea     rcx, [rdi+10h]
0x18001a4da  mov     rax, [rcx]
0x18001a4dd  lea     rdx, [rbp+arg_10]
0x18001a4e1  mov     rax, [rax+30h]
0x18001a4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4ea  nop
0x18001a4eb  test    rdi, rdi
0x18001a4ee  jz      short loc_18001A500
0x18001a4f0  mov     rax, [rdi]
0x18001a4f3  mov     rcx, rdi
0x18001a4f6  mov     rax, [rax+10h]
0x18001a4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4ff  nop
0x18001a500  movzx   eax, [rbp+arg_10]
0x18001a504  mov     rbx, [rsp+50h+arg_0]
0x18001a50c  add     rsp, 50h
0x18001a510  pop     r15
0x18001a512  pop     r14
0x18001a514  pop     r13
0x18001a516  pop     r12
0x18001a518  pop     rdi
0x18001a519  pop     rsi
0x18001a51a  pop     rbp
0x18001a51b  retn
0x18001a51c  lea     rax, [rbp+var_20]
0x18001a520  mov     [rbp+var_10], rax
0x18001a524  lea     rax, [rbp+var_18]
0x18001a528  mov     [rbp+var_8], rax
0x18001a52c  mov     r8, r14
0x18001a52f  mov     rdx, rbx
0x18001a532  lea     rcx, [rbp+var_10]
0x18001a536  call    ??$InvokeDelegates@V_lambda_20f494fe0baa1532db1c50100a579e9f_@@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowOcclusionChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_20f494fe0baa1532db1c50100a579e9f_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowOcclusionChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_20f494fe0baa1532db1c50100a579e9f_,Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowOcclusionChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_20f494fe0baa1532db1c50100a579e9f_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowOcclusionChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x18001a53b  mov     rcx, rbx
0x18001a53e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a543  jmp     short loc_18001A4D6
0x18001a545  xor     ecx, ecx
0x18001a547  jmp     loc_18001A485
0x18001a54c  xor     r9d, r9d; lParam
0x18001a54f  xor     r8d, r8d; wParam
0x18001a552  mov     edx, 720h; Msg
0x18001a557  mov     rcx, [r15+0D88h]; hWnd
0x18001a55e  call    cs:__imp_PostMessageW
0x18001a564  jmp     short loc_18001A500
0x18001a566  xor     ebx, ebx
0x18001a568  jmp     loc_18001A43E
```
