# NotificationServiceImpl::OnAuthError(long)

- ea: `0x18006f2d4`
- end: `0x18006f459`
- name: `?OnAuthError@NotificationServiceImpl@@AEAAXJ@Z`
- size: `389`
- prototype: `void __fastcall(NotificationServiceImpl *__hidden this, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006c280`

## callees

- `0x18000ba54`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18006d890`
- `0x18006f2d4`
- `0x180085634`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f408`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f408`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f3f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f3f8`

## string_xrefs

- `0x18006f3b0`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NotificationServiceImpl::OnAuthError(NotificationServiceImpl *this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // ebx
  unsigned int v6; // esi
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct IConnectionProviderEvents *v13; // [rsp+50h] [rbp+8h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      238,
      &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
      (unsigned int)a2);
  }
  v6 = 2;
  v13 = 0;
  if ( v4 == -2147023665 )
  {
    v6 = 6;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13, a2, a3, a4);
    NotificationServiceImpl::GetConnectionProviderEvents(this, &v13);
    v7 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, __int64, _QWORD, __int64))(*(_QWORD *)v13 + 24LL))(
           v13,
           6,
           0,
           2147943631LL);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          239,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v7);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9D1,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v8);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v8);
    }
  }
  WpnSqmConnectionStatusUpdate(v6, v4);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 54) = v6;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 241, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13, v9, v10, v11);
}

```

## disassembly

```asm
0x18006f2d4  mov     [rsp+arg_8], rbx
0x18006f2d9  mov     [rsp+arg_10], rbp
0x18006f2de  push    rsi
0x18006f2df  push    rdi
0x18006f2e0  push    r12
0x18006f2e2  sub     rsp, 30h
0x18006f2e6  mov     ebx, edx
0x18006f2e8  mov     rbp, rcx
0x18006f2eb  lea     r12, WPP_GLOBAL_Control
0x18006f2f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f2f9  cmp     rcx, r12
0x18006f2fc  jz      short loc_18006F322
0x18006f2fe  test    byte ptr [rcx+1Ch], 2
0x18006f302  jz      short loc_18006F322
0x18006f304  cmp     byte ptr [rcx+19h], 6
0x18006f308  jb      short loc_18006F322
0x18006f30a  mov     edx, 0EEh
0x18006f30f  mov     r9d, ebx
0x18006f312  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f319  mov     rcx, [rcx+10h]
0x18006f31d  call    WPP_SF_d
0x18006f322  mov     esi, 2
0x18006f327  mov     [rsp+48h+arg_0], 0
0x18006f330  mov     edi, 800704CFh
0x18006f335  cmp     ebx, edi
0x18006f337  jnz     loc_18006F3EB
0x18006f33d  mov     esi, 6
0x18006f342  lea     rcx, [rsp+48h+arg_0]
0x18006f347  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f34c  lea     rdx, [rsp+48h+arg_0]; struct IConnectionProviderEvents **
0x18006f351  mov     rcx, rbp; this
0x18006f354  call    ?GetConnectionProviderEvents@NotificationServiceImpl@@AEAAXPEAPEAUIConnectionProviderEvents@@@Z; NotificationServiceImpl::GetConnectionProviderEvents(IConnectionProviderEvents * *)
0x18006f359  mov     rcx, [rsp+48h+arg_0]
0x18006f35e  mov     rax, [rcx]
0x18006f361  mov     r9d, edi
0x18006f364  xor     r8d, r8d
0x18006f367  mov     edx, esi
0x18006f369  mov     rax, [rax+18h]
0x18006f36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f372  mov     edi, eax
0x18006f374  test    eax, eax
0x18006f376  jns     short loc_18006F3EB
0x18006f378  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f37f  cmp     rcx, r12
0x18006f382  jz      short loc_18006F3A8
0x18006f384  test    byte ptr [rcx+1Ch], 2
0x18006f388  jz      short loc_18006F3A8
0x18006f38a  cmp     byte ptr [rcx+19h], 2
0x18006f38e  jb      short loc_18006F3A8
0x18006f390  mov     edx, 0EFh
0x18006f395  mov     r9d, eax
0x18006f398  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f39f  mov     rcx, [rcx+10h]
0x18006f3a3  call    WPP_SF_d
0x18006f3a8  mov     rcx, [rsp+48h]; this
0x18006f3ad  mov     r9d, edi; char *
0x18006f3b0  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006f3b7  mov     edx, 9D1h; void *
0x18006f3bc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f3c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f3c8  cmp     rcx, r12
0x18006f3cb  jz      short loc_18006F3EB
0x18006f3cd  test    byte ptr [rcx+1Ch], 80h
0x18006f3d1  jz      short loc_18006F3EB
0x18006f3d3  mov     edx, 0F0h
0x18006f3d8  mov     r9d, edi
0x18006f3db  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f3e2  mov     rcx, [rcx+10h]
0x18006f3e6  call    WPP_SF_d
0x18006f3eb  mov     edx, ebx
0x18006f3ed  mov     ecx, esi
0x18006f3ef  call    ?WpnSqmConnectionStatusUpdate@@YAXW4_WpnSqmConnectionStatusType@@J@Z; WpnSqmConnectionStatusUpdate(_WpnSqmConnectionStatusType,long)
0x18006f3f4  lea     rcx, [rbp+10h]; lpCriticalSection
0x18006f3f8  call    cs:__imp_EnterCriticalSection
0x18006f3fe  mov     [rbp+0D8h], esi
0x18006f404  lea     rcx, [rbp+10h]; lpCriticalSection
0x18006f408  call    cs:__imp_LeaveCriticalSection
0x18006f40e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f415  cmp     rcx, r12
0x18006f418  jz      short loc_18006F43C
0x18006f41a  test    byte ptr [rcx+1Ch], 2
0x18006f41e  jz      short loc_18006F43C
0x18006f420  cmp     byte ptr [rcx+19h], 6
0x18006f424  jb      short loc_18006F43C
0x18006f426  mov     edx, 0F1h
0x18006f42b  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f432  mov     rcx, [rcx+10h]
0x18006f436  call    WPP_SF_
0x18006f43b  nop
0x18006f43c  lea     rcx, [rsp+48h+arg_0]
0x18006f441  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f446  mov     rbx, [rsp+48h+arg_8]
0x18006f44b  mov     rbp, [rsp+48h+arg_10]
0x18006f450  add     rsp, 30h
0x18006f454  pop     r12
0x18006f456  pop     rdi
0x18006f457  pop     rsi
0x18006f458  retn
```
