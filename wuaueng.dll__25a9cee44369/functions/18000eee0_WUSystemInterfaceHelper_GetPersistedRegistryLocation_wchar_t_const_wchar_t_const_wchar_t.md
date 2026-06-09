# WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x18000eee0`
- end: `0x18000ef68`
- name: `?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z`
- size: `136`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e460`

## callees

- `0x180003760`
- `0x18000ecac`
- `0x18000eee0`
- `0x1800159b0`

## pseudocode

```c
__int64 __fastcall WUSystemInterfaceHelper::GetPersistedRegistryLocation(
        WUSystemInterfaceHelper *this,
        const wchar_t *a2,
        const wchar_t *a3,
        wchar_t **a4)
{
  int WUSystemInterface; // ebx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface(this);
  if ( WUSystemInterface < 0 )
  {
    v8 = 328;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
      (const char *)(unsigned int)WUSystemInterface,
      v10);
    return (unsigned int)WUSystemInterface;
  }
  WUSystemInterface = (*(__int64 (__fastcall **)(__int64, WUSystemInterfaceHelper *, const wchar_t *, const wchar_t *))(*(_QWORD *)g_WUSystemInterface + 240LL))(
                        g_WUSystemInterface,
                        this,
                        a2,
                        a3);
  if ( WUSystemInterface < 0 )
  {
    v8 = 329;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000eee0  mov     [rsp+arg_0], rbx
0x18000eee5  mov     [rsp+arg_8], rbp
0x18000eeea  mov     [rsp+arg_10], rsi
0x18000eeef  push    rdi
0x18000eef0  sub     rsp, 30h
0x18000eef4  mov     rdi, r8
0x18000eef7  mov     rsi, rdx
0x18000eefa  mov     rbp, rcx
0x18000eefd  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x18000ef02  mov     ebx, eax
0x18000ef04  test    eax, eax
0x18000ef06  jns     short loc_18000EF25
0x18000ef08  mov     edx, 148h; void *
0x18000ef0d  mov     rcx, [rsp+38h]; this
0x18000ef12  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18000ef19  mov     r9d, ebx; char *
0x18000ef1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef21  mov     eax, ebx
0x18000ef23  jmp     short loc_18000EF53
0x18000ef25  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ef2c  mov     r9, rdi
0x18000ef2f  mov     r8, rsi
0x18000ef32  mov     rdx, rbp
0x18000ef35  mov     rax, [rcx]
0x18000ef38  mov     rax, [rax+0F0h]
0x18000ef3f  call    _guard_dispatch_icall
0x18000ef44  mov     ebx, eax
0x18000ef46  test    eax, eax
0x18000ef48  jns     short loc_18000EF51
0x18000ef4a  mov     edx, 149h
0x18000ef4f  jmp     short loc_18000EF0D
0x18000ef51  xor     eax, eax
0x18000ef53  mov     rbx, [rsp+38h+arg_0]
0x18000ef58  mov     rbp, [rsp+38h+arg_8]
0x18000ef5d  mov     rsi, [rsp+38h+arg_10]
0x18000ef62  add     rsp, 30h
0x18000ef66  pop     rdi
0x18000ef67  retn
```
