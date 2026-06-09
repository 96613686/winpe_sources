# CRegRpcEndpoint::SetSecurity(void *,ulong)

- ea: `0x180015d60`
- end: `0x180015e44`
- name: `?SetSecurity@CRegRpcEndpoint@@QEAAKPEAXK@Z`
- size: `228`
- prototype: `__int64 __fastcall(CRegRpcEndpoint *this, void *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005df0`
- `0x1800159fc`

## callees

- `0x180015d60`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180015e0b`
- `KERNEL32!LeaveCriticalSection` at `0x180015e0b`
- `KERNEL32!EnterCriticalSection` at `0x180015d92`
- `KERNEL32!EnterCriticalSection` at `0x180015d92`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180015db1`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180015dfb`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180015db1`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180015dfb`
- `WdsServerCommonLib!?CreateSelfRelative@CSecDesc@@SAKPEAXPEAPEAX@Z` at `0x180015dd3`
- `WdsServerCommonLib!?CreateSelfRelative@CSecDesc@@SAKPEAXPEAPEAX@Z` at `0x180015dd3`
- `WdsServerCommonLib!?Shutdown@CSecDesc@@QEAAKXZ` at `0x180015e1c`
- `WdsServerCommonLib!?Shutdown@CSecDesc@@QEAAKXZ` at `0x180015e1c`

## pseudocode

```c
__int64 __fastcall CRegRpcEndpoint::SetSecurity(CRegRpcEndpoint *this, void *a2, int a3)
{
  unsigned int v3; // esi
  void *v7; // rcx
  _DWORD *v8; // rbx
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  int v11; // [rsp+28h] [rbp-20h]
  void *v12; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = (void *)*((_QWORD *)this + 226);
  v8 = (_DWORD *)((char *)this + 1816);
  if ( v7 )
  {
    WdsPrivateHpFree(v7);
    *((_QWORD *)this + 226) = 0;
    *v8 = 0;
  }
  if ( a2 )
  {
    v3 = CSecDesc::CreateSelfRelative(a2, &v12);
    if ( v3 )
    {
      if ( v12 )
        WdsPrivateHpFree(v12);
    }
    else
    {
      *((_QWORD *)this + 226) = v12;
      *v8 = a3;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CSecDesc::Shutdown((CSecDesc *)&v10);
  return v3;
}

```

## disassembly

```asm
0x180015d60  mov     rax, rsp
0x180015d63  mov     [rax+10h], rbx
0x180015d67  mov     [rax+18h], rbp
0x180015d6b  mov     [rax+20h], rsi
0x180015d6f  push    rdi
0x180015d70  push    r14
0x180015d72  push    r15
0x180015d74  sub     rsp, 30h
0x180015d78  xor     esi, esi
0x180015d7a  mov     rdi, rcx
0x180015d7d  and     [rax+8], rsi
0x180015d81  add     rcx, 10h; lpCriticalSection
0x180015d85  and     [rax-28h], rsi
0x180015d89  mov     r15d, r8d
0x180015d8c  and     [rax-20h], esi
0x180015d8f  mov     rbp, rdx
0x180015d92  call    cs:__imp_EnterCriticalSection
0x180015d99  nop     dword ptr [rax+rax+00h]
0x180015d9e  mov     rcx, [rdi+710h]
0x180015da5  lea     rbx, [rdi+718h]
0x180015dac  test    rcx, rcx
0x180015daf  jz      short loc_180015DC6
0x180015db1  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180015db8  nop     dword ptr [rax+rax+00h]
0x180015dbd  and     [rdi+710h], rsi
0x180015dc4  and     [rbx], esi
0x180015dc6  test    rbp, rbp
0x180015dc9  jz      short loc_180015E07
0x180015dcb  lea     rdx, [rsp+48h+arg_0]
0x180015dd0  mov     rcx, rbp
0x180015dd3  call    cs:__imp_?CreateSelfRelative@CSecDesc@@SAKPEAXPEAPEAX@Z; CSecDesc::CreateSelfRelative(void *,void * *)
0x180015dda  nop     dword ptr [rax+rax+00h]
0x180015ddf  mov     rcx, [rsp+48h+arg_0]
0x180015de4  mov     esi, eax
0x180015de6  test    eax, eax
0x180015de8  jnz     short loc_180015DF6
0x180015dea  mov     [rdi+710h], rcx
0x180015df1  mov     [rbx], r15d
0x180015df4  jmp     short loc_180015E07
0x180015df6  test    rcx, rcx
0x180015df9  jz      short loc_180015E07
0x180015dfb  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180015e02  nop     dword ptr [rax+rax+00h]
0x180015e07  lea     rcx, [rdi+10h]; lpCriticalSection
0x180015e0b  call    cs:__imp_LeaveCriticalSection
0x180015e12  nop     dword ptr [rax+rax+00h]
0x180015e17  lea     rcx, [rsp+48h+var_28]
0x180015e1c  call    cs:__imp_?Shutdown@CSecDesc@@QEAAKXZ; CSecDesc::Shutdown(void)
0x180015e23  nop     dword ptr [rax+rax+00h]
0x180015e28  mov     rbx, [rsp+48h+arg_8]
0x180015e2d  mov     eax, esi
0x180015e2f  mov     rsi, [rsp+48h+arg_18]
0x180015e34  mov     rbp, [rsp+48h+arg_10]
0x180015e39  add     rsp, 30h
0x180015e3d  pop     r15
0x180015e3f  pop     r14
0x180015e41  pop     rdi
0x180015e42  retn
```
