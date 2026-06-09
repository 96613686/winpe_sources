# Telemetry4UpdateCli::RunCmd::~RunCmd(void)

- ea: `0x18000d1cc`
- end: `0x18000d2f0`
- name: `??1RunCmd@Telemetry4UpdateCli@@QEAA@XZ`
- size: `292`
- prototype: `void __fastcall(Telemetry4UpdateCli::RunCmd *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x1800084bc`
- `0x180015880`

## callees

- `0x180004298`
- `0x18000cfc0`
- `0x18000d038`
- `0x18000d14c`
- `0x18000d1cc`
- `0x180010334`
- `0x1800148e0`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d267`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d267`

## pseudocode

```c
void __fastcall Telemetry4UpdateCli::RunCmd::~RunCmd(Telemetry4UpdateCli::RunCmd *this)
{
  char v2; // si
  volatile signed __int32 *v3; // rcx
  void *v4; // rdi
  _DWORD *v5; // rcx
  int v6; // eax
  int v7; // edx
  const struct wil::FailureInfo *v8; // rdx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v10[160]; // [rsp+30h] [rbp-A8h] BYREF

  *(_QWORD *)this = &Telemetry4UpdateCli::RunCmd::`vftable';
  v2 = 1;
  if ( !*((_QWORD *)this + 35) )
    goto LABEL_12;
  SRWLock[0] = 0;
  wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    SRWLock);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 35);
  if ( !v3 || *v3 != 1 )
  {
    v2 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(v3, 0xFFFFFFFF) == 1 )
      {
        v4 = (void *)*((_QWORD *)this + 35);
        if ( v4 )
        {
          wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>((__int64)v4 + 8);
          operator delete(v4, 0x110u);
        }
      }
      *((_QWORD *)this + 35) = 0;
    }
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( v2 )
  {
LABEL_12:
    v5 = (_DWORD *)*((_QWORD *)this + 34);
    if ( *v5 == 1 )
    {
      v6 = -2147024322;
      if ( (int)v5[22] < 0 )
        v6 = v5[22];
      v7 = v5[62];
      if ( v7 < 1 )
      {
        memset(v10, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v10, v8);
      }
      if ( (int)v5[18] >= 0 )
        v5[18] = v6;
      v5[62] = v7 - 1;
      (*(void (__fastcall **)(Telemetry4UpdateCli::RunCmd *))(*(_QWORD *)this + 8LL))(this);
    }
  }
  wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x18000d1cc  mov     [rsp+arg_8], rbx
0x18000d1d1  mov     [rsp+arg_10], rsi
0x18000d1d6  push    rdi
0x18000d1d7  sub     rsp, 0D0h
0x18000d1de  mov     rbx, rcx
0x18000d1e1  lea     rax, ??_7RunCmd@Telemetry4UpdateCli@@6B@; const Telemetry4UpdateCli::RunCmd::`vftable'
0x18000d1e8  mov     [rcx], rax
0x18000d1eb  mov     sil, 1
0x18000d1ee  cmp     qword ptr [rcx+118h], 0
0x18000d1f6  jz      short loc_18000D272
0x18000d1f8  mov     [rsp+0D8h+SRWLock], 0
0x18000d201  lea     rdx, [rsp+0D8h+SRWLock]
0x18000d206  call    ?LockExclusive@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d20b  mov     rcx, [rbx+118h]
0x18000d212  test    rcx, rcx
0x18000d215  jz      short loc_18000D21C
0x18000d217  cmp     dword ptr [rcx], 1
0x18000d21a  jz      short loc_18000D25D
0x18000d21c  xor     sil, sil
0x18000d21f  test    rcx, rcx
0x18000d222  jz      short loc_18000D25D
0x18000d224  or      eax, 0FFFFFFFFh
0x18000d227  lock xadd [rcx], eax
0x18000d22b  cmp     eax, 1
0x18000d22e  jnz     short loc_18000D252
0x18000d230  mov     rdi, [rbx+118h]
0x18000d237  test    rdi, rdi
0x18000d23a  jz      short loc_18000D252
0x18000d23c  lea     rcx, [rdi+8]
0x18000d240  call    ??1?$ActivityData@VTelemetry4UpdateCli@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000d245  mov     edx, 110h; unsigned __int64
0x18000d24a  mov     rcx, rdi; void *
0x18000d24d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d252  mov     qword ptr [rbx+118h], 0
0x18000d25d  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x18000d262  test    rcx, rcx
0x18000d265  jz      short loc_18000D26D
0x18000d267  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d26d  test    sil, sil
0x18000d270  jz      short loc_18000D2B7
0x18000d272  mov     rcx, [rbx+110h]
0x18000d279  cmp     dword ptr [rcx], 1
0x18000d27c  jnz     short loc_18000D2B7
0x18000d27e  mov     eax, 8007023Eh
0x18000d283  cmp     dword ptr [rcx+58h], 0
0x18000d287  cmovl   eax, [rcx+58h]
0x18000d28b  mov     edx, [rcx+0F8h]
0x18000d291  cmp     edx, 1
0x18000d294  jl      short loc_18000D2D3
0x18000d296  cmp     dword ptr [rcx+48h], 0
0x18000d29a  jl      short loc_18000D29F
0x18000d29c  mov     [rcx+48h], eax
0x18000d29f  lea     eax, [rdx-1]
0x18000d2a2  mov     [rcx+0F8h], eax
0x18000d2a8  mov     rax, [rbx]
0x18000d2ab  mov     rcx, rbx
0x18000d2ae  mov     rax, [rax+8]
0x18000d2b2  call    _guard_dispatch_icall
0x18000d2b7  mov     rcx, rbx
0x18000d2ba  lea     r11, [rsp+0D8h+var_8]
0x18000d2c2  mov     rbx, [r11+18h]
0x18000d2c6  mov     rsi, [r11+20h]
0x18000d2ca  mov     rsp, r11
0x18000d2cd  pop     rdi
0x18000d2ce  jmp     ??1?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000d2d3  xor     edx, edx; Val
0x18000d2d5  mov     r8d, 98h; Size
0x18000d2db  lea     rcx, [rsp+0D8h+var_A8]; void *
0x18000d2e0  call    memset
0x18000d2e5  lea     rcx, [rsp+0D8h+var_A8]; this
0x18000d2ea  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
