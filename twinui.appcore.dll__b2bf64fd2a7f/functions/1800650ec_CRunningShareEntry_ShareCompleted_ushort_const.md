# CRunningShareEntry::_ShareCompleted(ushort const *)

- ea: `0x1800650ec`
- end: `0x1800652ac`
- name: `?_ShareCompleted@CRunningShareEntry@@AEAAJPEBG@Z`
- size: `448`
- prototype: `__int64 __fastcall(CRunningShareEntry *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180063f50`
- `0x180065020`

## callees

- `0x180003d24`
- `0x18000c8e0`
- `0x18000c90c`
- `0x180012360`
- `0x180016fb4`
- `0x180029454`
- `0x1800366a0`
- `0x180064da0`
- `0x1800650ec`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065224`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065224`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x1800651be`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x1800651be`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CRunningShareEntry::_ShareCompleted(CRunningShareEntry *this, const unsigned __int16 *a2)
{
  int v4; // ebx
  char *v5; // r15
  int v6; // r12d
  void *v7; // rbx
  __int64 (__fastcall *v8)(void *, GUID *, __int64 *); // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // r14d
  __int64 v12; // rbx
  void *v14; // [rsp+60h] [rbp+40h] BYREF
  __int64 v15; // [rsp+68h] [rbp+48h] BYREF
  HWND hWnd; // [rsp+70h] [rbp+50h] BYREF
  char v17; // [rsp+78h] [rbp+58h] BYREF

  v4 = 0;
  v5 = (char *)this + 232;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&v17, (char *)this + 232);
  if ( *((_QWORD *)this + 24) )
  {
    v6 = *((_DWORD *)this + 29);
    v14 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    if ( (int)AgileGitPtr::CopyLocal(
                (CRunningShareEntry *)((char *)this + 192),
                &GUID_4c747ac4_149c_46f6_b313_3f25e22ef67e,
                &v14) >= 0 )
    {
      Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v17);
      v15 = 0;
      v7 = v14;
      v8 = **(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v14;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
      v4 = v8(v7, &GUID_00000114_0000_0000_c000_000000000046, &v15);
      if ( v4 >= 0 )
      {
        hWnd = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v15 + 24LL))(v15, &hWnd);
        if ( v4 >= 0 && (v6 != 7 || !IsWindowVisible(hWnd)) )
          v4 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v14 + 296LL))(v14);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v17);
  if ( v4 >= 0 && *((_DWORD *)this + 16) == 2 )
    v4 = CRunningShareEntry::_OnUIDestroy(this);
  wil::AcquireSRWLockExclusive(&v14, v5);
  if ( a2 )
  {
    CoTaskMemFree(*((LPVOID *)this + 9));
    v4 = _AllocString<CTCoAllocPolicy>(v10, v9, a2, (char *)this + 72);
  }
  v11 = *((_DWORD *)this + 29);
  if ( ((v11 - 5) & 0xFFFFFFFD) != 0 )
  {
    v12 = *((_QWORD *)this + 27);
    v15 = v12;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v14);
    v4 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v12 + 56LL))(v12, (char *)this + 48, v11);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800650ec  push    rbp
0x1800650ee  push    rbx
0x1800650ef  push    rsi
0x1800650f0  push    rdi
0x1800650f1  push    r12
0x1800650f3  push    r14
0x1800650f5  push    r15
0x1800650f7  mov     rbp, rsp
0x1800650fa  sub     rsp, 20h
0x1800650fe  mov     r14, rdx
0x180065101  mov     rsi, rcx
0x180065104  xor     ebx, ebx
0x180065106  lea     r15, [rcx+0E8h]
0x18006510d  mov     rdx, r15
0x180065110  lea     rcx, [rbp+arg_18]
0x180065114  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180065119  nop
0x18006511a  lea     rdi, [rsi+0C0h]
0x180065121  cmp     [rdi], rbx
0x180065124  jz      loc_1800651F1
0x18006512a  mov     r12d, [rsi+74h]
0x18006512e  mov     [rbp+arg_0], rbx
0x180065132  lea     rcx, [rbp+arg_0]
0x180065136  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006513b  lea     r8, [rbp+arg_0]; void **
0x18006513f  lea     rdx, _GUID_4c747ac4_149c_46f6_b313_3f25e22ef67e; struct _GUID *
0x180065146  mov     rcx, rdi; this
0x180065149  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x18006514e  test    eax, eax
0x180065150  js      loc_1800651E7
0x180065156  lea     rcx, [rbp+arg_18]; this
0x18006515a  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x18006515f  mov     [rbp+arg_8], rbx
0x180065163  mov     rbx, [rbp+arg_0]
0x180065167  mov     rax, [rbx]
0x18006516a  mov     rdi, [rax]
0x18006516d  lea     rcx, [rbp+arg_8]
0x180065171  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065176  lea     r8, [rbp+arg_8]
0x18006517a  lea     rdx, _GUID_00000114_0000_0000_c000_000000000046
0x180065181  mov     rcx, rbx
0x180065184  mov     rax, rdi
0x180065187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006518c  mov     ebx, eax
0x18006518e  test    eax, eax
0x180065190  js      short loc_1800651DD
0x180065192  mov     [rbp+hWnd], 0
0x18006519a  mov     rcx, [rbp+arg_8]
0x18006519e  mov     rax, [rcx]
0x1800651a1  lea     rdx, [rbp+hWnd]
0x1800651a5  mov     rax, [rax+18h]
0x1800651a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651ae  mov     ebx, eax
0x1800651b0  test    eax, eax
0x1800651b2  js      short loc_1800651DD
0x1800651b4  cmp     r12d, 7
0x1800651b8  jnz     short loc_1800651C8
0x1800651ba  mov     rcx, [rbp+hWnd]; hWnd
0x1800651be  call    cs:__imp_IsWindowVisible
0x1800651c4  test    eax, eax
0x1800651c6  jnz     short loc_1800651DD
0x1800651c8  mov     rcx, [rbp+arg_0]
0x1800651cc  mov     rax, [rcx]
0x1800651cf  mov     rax, [rax+128h]
0x1800651d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651db  mov     ebx, eax
0x1800651dd  lea     rcx, [rbp+arg_8]
0x1800651e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800651e6  nop
0x1800651e7  lea     rcx, [rbp+arg_0]
0x1800651eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800651f0  nop
0x1800651f1  lea     rcx, [rbp+arg_18]; this
0x1800651f5  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800651fa  test    ebx, ebx
0x1800651fc  js      short loc_18006520E
0x1800651fe  cmp     dword ptr [rsi+40h], 2
0x180065202  jnz     short loc_18006520E
0x180065204  mov     rcx, rsi; this
0x180065207  call    ?_OnUIDestroy@CRunningShareEntry@@AEAAJXZ; CRunningShareEntry::_OnUIDestroy(void)
0x18006520c  mov     ebx, eax
0x18006520e  mov     rdx, r15
0x180065211  lea     rcx, [rbp+arg_0]
0x180065215  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18006521a  nop
0x18006521b  test    r14, r14
0x18006521e  jz      short loc_180065238
0x180065220  mov     rcx, [rsi+48h]; pv
0x180065224  call    cs:__imp_CoTaskMemFree
0x18006522a  lea     r9, [rsi+48h]
0x18006522e  mov     r8, r14
0x180065231  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180065236  mov     ebx, eax
0x180065238  mov     r14d, [rsi+74h]
0x18006523c  lea     eax, [r14-5]
0x180065240  test    eax, 0FFFFFFFDh
0x180065245  jz      short loc_180065292
0x180065247  mov     rbx, [rsi+0D8h]
0x18006524e  mov     [rbp+arg_8], rbx
0x180065252  test    rbx, rbx
0x180065255  jz      short loc_180065267
0x180065257  mov     rax, [rbx]
0x18006525a  mov     rcx, rbx
0x18006525d  mov     rax, [rax+8]
0x180065261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065266  nop
0x180065267  lea     rcx, [rbp+arg_0]; this
0x18006526b  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x180065270  mov     rax, [rbx]
0x180065273  mov     r8d, r14d
0x180065276  lea     rdx, [rsi+30h]
0x18006527a  mov     rcx, rbx
0x18006527d  mov     rax, [rax+38h]
0x180065281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065286  mov     ebx, eax
0x180065288  lea     rcx, [rbp+arg_8]
0x18006528c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065291  nop
0x180065292  lea     rcx, [rbp+arg_0]; this
0x180065296  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18006529b  mov     eax, ebx
0x18006529d  add     rsp, 20h
0x1800652a1  pop     r15
0x1800652a3  pop     r14
0x1800652a5  pop     r12
0x1800652a7  pop     rdi
0x1800652a8  pop     rsi
0x1800652a9  pop     rbx
0x1800652aa  pop     rbp
0x1800652ab  retn
```
