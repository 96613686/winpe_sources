# UserAssistImpl::GetUserAssistWorker(_GUID const &)

- ea: `0x18007a364`
- end: `0x18007a3fe`
- name: `?GetUserAssistWorker@UserAssistImpl@@YAPEAUIShellUserAssist@@AEBU_GUID@@@Z`
- size: `154`
- prototype: `struct IShellUserAssist *__fastcall(UserAssistImpl *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007c918`

## callees

- `0x18007a364`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007a39d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007a39d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHPinDllOfCLSID` at `0x18007a3ae`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHPinDllOfCLSID` at `0x18007a3ae`

## pseudocode

```c
struct IShellUserAssist *__fastcall UserAssistImpl::GetUserAssistWorker(UserAssistImpl *this, const struct _GUID *a2)
{
  struct IShellUserAssist *result; // rax
  signed __int64 v3; // rcx
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF

  v4 = (__int64)this;
  result = UserAssistImpl::g_cachedUserAssist;
  if ( !UserAssistImpl::g_cachedUserAssist )
  {
    v4 = 0;
    if ( CoCreateInstance(
           &GUID_dd313e04_feff_11d1_8ecd_0000f87a470c,
           0,
           0x403u,
           &GUID_49b36d57_5fd2_45a7_981b_06028d577a47,
           (LPVOID *)&v4) < 0 )
    {
      v3 = -1;
      v4 = -1;
    }
    else
    {
      SHPinDllOfCLSID(&GUID_dd313e04_feff_11d1_8ecd_0000f87a470c);
      v3 = v4;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&UserAssistImpl::g_cachedUserAssist, v3, 0)
      && v4 != -1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    result = UserAssistImpl::g_cachedUserAssist;
  }
  if ( result == (struct IShellUserAssist *)-1LL )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18007a364  mov     r11, rsp
0x18007a367  mov     [r11+8], rcx
0x18007a36b  sub     rsp, 38h
0x18007a36f  mov     rax, cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x18007a376  test    rax, rax
0x18007a379  jnz     short loc_18007A3EF
0x18007a37b  mov     [r11+8], rax
0x18007a37f  lea     r9, _GUID_49b36d57_5fd2_45a7_981b_06028d577a47; riid
0x18007a386  lea     rax, [r11+8]
0x18007a38a  xor     edx, edx; pUnkOuter
0x18007a38c  mov     r8d, 403h; dwClsContext
0x18007a392  mov     [r11-18h], rax
0x18007a396  lea     rcx, _GUID_dd313e04_feff_11d1_8ecd_0000f87a470c; rclsid
0x18007a39d  call    cs:__imp_CoCreateInstance
0x18007a3a3  test    eax, eax
0x18007a3a5  js      short loc_18007A3BB
0x18007a3a7  lea     rcx, _GUID_dd313e04_feff_11d1_8ecd_0000f87a470c
0x18007a3ae  call    cs:__imp_SHPinDllOfCLSID
0x18007a3b4  mov     rcx, [rsp+38h+arg_0]
0x18007a3b9  jmp     short loc_18007A3C4
0x18007a3bb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007a3bf  mov     [rsp+38h+arg_0], rcx
0x18007a3c4  xor     eax, eax
0x18007a3c6  lock cmpxchg cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA, rcx; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x18007a3cf  jz      short loc_18007A3E8
0x18007a3d1  mov     rcx, [rsp+38h+arg_0]
0x18007a3d6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007a3da  jz      short loc_18007A3E8
0x18007a3dc  mov     rax, [rcx]
0x18007a3df  mov     rax, [rax+10h]
0x18007a3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3e8  mov     rax, cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x18007a3ef  xor     ecx, ecx
0x18007a3f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007a3f5  cmovz   rax, rcx
0x18007a3f9  add     rsp, 38h
0x18007a3fd  retn
```
