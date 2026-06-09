# WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x140010e78`
- end: `0x140010f00`
- name: `?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z`
- size: `136`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400109ec`

## callees

- `0x140002ac0`
- `0x140010c44`
- `0x140010e78`
- `0x1400206e0`

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
0x140010e78  mov     [rsp+arg_0], rbx
0x140010e7d  mov     [rsp+arg_8], rbp
0x140010e82  mov     [rsp+arg_10], rsi
0x140010e87  push    rdi
0x140010e88  sub     rsp, 30h
0x140010e8c  mov     rdi, r8
0x140010e8f  mov     rsi, rdx
0x140010e92  mov     rbp, rcx
0x140010e95  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x140010e9a  mov     ebx, eax
0x140010e9c  test    eax, eax
0x140010e9e  jns     short loc_140010EBD
0x140010ea0  mov     edx, 148h; void *
0x140010ea5  mov     rcx, [rsp+38h]; this
0x140010eaa  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x140010eb1  mov     r9d, ebx; char *
0x140010eb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010eb9  mov     eax, ebx
0x140010ebb  jmp     short loc_140010EEB
0x140010ebd  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140010ec4  mov     r9, rdi
0x140010ec7  mov     r8, rsi
0x140010eca  mov     rdx, rbp
0x140010ecd  mov     rax, [rcx]
0x140010ed0  mov     rax, [rax+0F0h]
0x140010ed7  call    _guard_dispatch_icall
0x140010edc  mov     ebx, eax
0x140010ede  test    eax, eax
0x140010ee0  jns     short loc_140010EE9
0x140010ee2  mov     edx, 149h
0x140010ee7  jmp     short loc_140010EA5
0x140010ee9  xor     eax, eax
0x140010eeb  mov     rbx, [rsp+38h+arg_0]
0x140010ef0  mov     rbp, [rsp+38h+arg_8]
0x140010ef5  mov     rsi, [rsp+38h+arg_10]
0x140010efa  add     rsp, 30h
0x140010efe  pop     rdi
0x140010eff  retn
```
