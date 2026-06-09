# WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x18000ef30`
- end: `0x18000efb8`
- name: `?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z`
- size: `136`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e3ec`

## callees

- `0x180003760`
- `0x18000ecfc`
- `0x18000ef30`
- `0x180015a00`

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
0x18000ef30  mov     [rsp+arg_0], rbx
0x18000ef35  mov     [rsp+arg_8], rbp
0x18000ef3a  mov     [rsp+arg_10], rsi
0x18000ef3f  push    rdi
0x18000ef40  sub     rsp, 30h
0x18000ef44  mov     rdi, r8
0x18000ef47  mov     rsi, rdx
0x18000ef4a  mov     rbp, rcx
0x18000ef4d  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x18000ef52  mov     ebx, eax
0x18000ef54  test    eax, eax
0x18000ef56  jns     short loc_18000EF75
0x18000ef58  mov     edx, 148h; void *
0x18000ef5d  mov     rcx, [rsp+38h]; this
0x18000ef62  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18000ef69  mov     r9d, ebx; char *
0x18000ef6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef71  mov     eax, ebx
0x18000ef73  jmp     short loc_18000EFA3
0x18000ef75  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ef7c  mov     r9, rdi
0x18000ef7f  mov     r8, rsi
0x18000ef82  mov     rdx, rbp
0x18000ef85  mov     rax, [rcx]
0x18000ef88  mov     rax, [rax+0F0h]
0x18000ef8f  call    _guard_dispatch_icall
0x18000ef94  mov     ebx, eax
0x18000ef96  test    eax, eax
0x18000ef98  jns     short loc_18000EFA1
0x18000ef9a  mov     edx, 149h
0x18000ef9f  jmp     short loc_18000EF5D
0x18000efa1  xor     eax, eax
0x18000efa3  mov     rbx, [rsp+38h+arg_0]
0x18000efa8  mov     rbp, [rsp+38h+arg_8]
0x18000efad  mov     rsi, [rsp+38h+arg_10]
0x18000efb2  add     rsp, 30h
0x18000efb6  pop     rdi
0x18000efb7  retn
```
