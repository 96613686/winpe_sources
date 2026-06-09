# UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(void)

- ea: `0x180007fc4`
- end: `0x1800080dd`
- name: `??1ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAA@XZ`
- size: `281`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `10`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180008ee0`
- `0x1800091c0`
- `0x18000d2d0`
- `0x18000dcb0`
- `0x18000e300`
- `0x18000e610`
- `0x18000e9f0`
- `0x18000ed30`
- `0x18000f340`
- `0x18000f8a0`

## callees

- `0x1800070a0`
- `0x180007c58`
- `0x180007ccc`
- `0x180007fc4`
- `0x180009644`
- `0x18001a1d6`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008039`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008039`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008054`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008054`

## pseudocode

```c
__int64 __fastcall UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(_QWORD *a1)
{
  bool v1; // zf
  volatile signed __int32 *v3; // rcx
  char v4; // si
  char *v5; // rdi
  _DWORD *v6; // rcx
  int v7; // eax
  int v8; // edx
  const struct wil::FailureInfo *v10; // rdx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v12[160]; // [rsp+30h] [rbp-A8h] BYREF

  v1 = a1[35] == 0;
  *a1 = &UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable';
  if ( v1 )
    goto LABEL_13;
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    SRWLock);
  v3 = (volatile signed __int32 *)a1[35];
  if ( v3 && *v3 == 1 )
  {
    v4 = 1;
  }
  else
  {
    v4 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(v3, 0xFFFFFFFF) == 1 )
      {
        v5 = (char *)a1[35];
        if ( v5 )
        {
          wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UwfTraceLoggingProvider<2>,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UwfTraceLoggingProvider<2>,_TlgReflectorTag_Param0IsProviderType>(v5 + 8);
          operator delete(v5);
        }
      }
      a1[35] = 0;
    }
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( v4 )
  {
LABEL_13:
    v6 = (_DWORD *)a1[34];
    if ( *v6 == 1 )
    {
      v7 = -2147024322;
      v8 = v6[62];
      if ( (int)v6[22] < 0 )
        v7 = v6[22];
      if ( v8 < 1 )
      {
        memset_0(v12, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v12, v10);
      }
      if ( (int)v6[18] >= 0 )
        v6[18] = v7;
      v6[62] = v8 - 1;
      (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
    }
  }
  return wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(a1);
}

```

## disassembly

```asm
0x180007fc4  mov     [rsp+arg_8], rbx
0x180007fc9  mov     [rsp+arg_10], rsi
0x180007fce  push    rdi
0x180007fcf  sub     rsp, 0D0h
0x180007fd6  cmp     qword ptr [rcx+118h], 0
0x180007fde  lea     rax, ??_7ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable'
0x180007fe5  mov     [rcx], rax
0x180007fe8  mov     rbx, rcx
0x180007feb  jz      short loc_18000805F
0x180007fed  lea     rdx, [rsp+0D8h+SRWLock]
0x180007ff2  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180007ff7  mov     rcx, [rbx+118h]
0x180007ffe  test    rcx, rcx
0x180008001  jz      short loc_18000800D
0x180008003  cmp     dword ptr [rcx], 1
0x180008006  jnz     short loc_18000800D
0x180008008  mov     sil, 1
0x18000800b  jmp     short loc_18000804A
0x18000800d  xor     sil, sil
0x180008010  test    rcx, rcx
0x180008013  jz      short loc_18000804A
0x180008015  or      eax, 0FFFFFFFFh
0x180008018  lock xadd [rcx], eax
0x18000801c  cmp     eax, 1
0x18000801f  jnz     short loc_18000803F
0x180008021  mov     rdi, [rbx+118h]
0x180008028  test    rdi, rdi
0x18000802b  jz      short loc_18000803F
0x18000802d  lea     rcx, [rdi+8]
0x180008031  call    ??1?$ActivityData@V?$UwfTraceLoggingProvider@$01@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UwfTraceLoggingProvider<2>,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UwfTraceLoggingProvider<2>,_TlgReflectorTag_Param0IsProviderType>(void)
0x180008036  mov     rcx, rdi
0x180008039  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000803f  mov     qword ptr [rbx+118h], 0
0x18000804a  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x18000804f  test    rcx, rcx
0x180008052  jz      short loc_18000805A
0x180008054  call    cs:__imp_ReleaseSRWLockExclusive
0x18000805a  test    sil, sil
0x18000805d  jz      short loc_1800080A4
0x18000805f  mov     rcx, [rbx+110h]
0x180008066  cmp     dword ptr [rcx], 1
0x180008069  jnz     short loc_1800080A4
0x18000806b  cmp     dword ptr [rcx+58h], 0
0x18000806f  mov     eax, 8007023Eh
0x180008074  mov     edx, [rcx+0F8h]
0x18000807a  cmovl   eax, [rcx+58h]
0x18000807e  cmp     edx, 1
0x180008081  jl      short loc_1800080C0
0x180008083  cmp     dword ptr [rcx+48h], 0
0x180008087  jl      short loc_18000808C
0x180008089  mov     [rcx+48h], eax
0x18000808c  lea     eax, [rdx-1]
0x18000808f  mov     [rcx+0F8h], eax
0x180008095  mov     rcx, rbx
0x180008098  mov     rax, [rbx]
0x18000809b  mov     rax, [rax+8]
0x18000809f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080a4  mov     rcx, rbx
0x1800080a7  lea     r11, [rsp+0D8h+var_8]
0x1800080af  mov     rbx, [r11+18h]
0x1800080b3  mov     rsi, [r11+20h]
0x1800080b7  mov     rsp, r11
0x1800080ba  pop     rdi
0x1800080bb  jmp     ??1?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800080c0  xor     edx, edx; Val
0x1800080c2  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800080c7  mov     r8d, 98h; Size
0x1800080cd  call    memset_0
0x1800080d2  lea     rcx, [rsp+0D8h+var_A8]; this
0x1800080d7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
