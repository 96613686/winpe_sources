# wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)

- ea: `0x18000b4dc`
- end: `0x18000b561`
- name: `?SetStopResult@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z`
- size: `133`
- prototype: `void __fastcall(__int64, int, RTL_SRWLOCK *)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

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
- `0x180009644`
- `0x18000b4dc`
- `0x18001a1d6`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b52d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b52d`

## pseudocode

```c
void __fastcall wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        __int64 a1,
        int a2,
        RTL_SRWLOCK *a3)
{
  __int64 v5; // rcx
  int v6; // eax
  const struct wil::FailureInfo *v7; // rdx
  _BYTE v8[168]; // [rsp+20h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+E0h] [rbp+18h] BYREF

  SRWLock = a3;
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v5 = *(_QWORD *)(a1 + 272);
  v6 = *(_DWORD *)(v5 + 248);
  if ( v6 < 1 )
  {
    memset_0(v8, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v8, v7);
  }
  if ( *(int *)(v5 + 72) >= 0 )
    *(_DWORD *)(v5 + 72) = a2;
  *(_DWORD *)(v5 + 248) = v6 - 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
}

```

## disassembly

```asm
0x18000b4dc  mov     rax, rsp
0x18000b4df  mov     [rax+8], rbx
0x18000b4e3  mov     [rax+18h], r8
0x18000b4e7  push    rdi
0x18000b4e8  sub     rsp, 0C0h
0x18000b4ef  mov     edi, edx
0x18000b4f1  mov     rbx, rcx
0x18000b4f4  lea     rdx, [rax+18h]
0x18000b4f8  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b4fd  mov     rcx, [rbx+110h]
0x18000b504  mov     eax, [rcx+0F8h]
0x18000b50a  cmp     eax, 1
0x18000b50d  jl      short loc_18000B544
0x18000b50f  cmp     dword ptr [rcx+48h], 0
0x18000b513  jl      short loc_18000B518
0x18000b515  mov     [rcx+48h], edi
0x18000b518  dec     eax
0x18000b51a  mov     [rcx+0F8h], eax
0x18000b520  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x18000b528  test    rcx, rcx
0x18000b52b  jz      short loc_18000B533
0x18000b52d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b533  mov     rbx, [rsp+0C8h+arg_0]
0x18000b53b  add     rsp, 0C0h
0x18000b542  pop     rdi
0x18000b543  retn
0x18000b544  xor     edx, edx; Val
0x18000b546  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000b54b  mov     r8d, 98h; Size
0x18000b551  call    memset_0
0x18000b556  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000b55b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
