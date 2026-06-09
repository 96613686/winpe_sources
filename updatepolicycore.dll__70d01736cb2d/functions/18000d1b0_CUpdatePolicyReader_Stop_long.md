# CUpdatePolicyReader::Stop(long *)

- ea: `0x18000d1b0`
- end: `0x18000d1e9`
- name: `?Stop@CUpdatePolicyReader@@UEAAJPEAJ@Z`
- size: `57`
- prototype: `__int64 __fastcall(CUpdatePolicyReader *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000aac0`
- `0x18000d1b0`

## string_xrefs

- `0x18000d1be`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`

## pseudocode

```c
__int64 __fastcall CUpdatePolicyReader::Stop(CUpdatePolicyReader *this, int *a2)
{
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    *a2 = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
      (const char *)0x80004003LL,
      v3);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000d1b0  sub     rsp, 28h
0x18000d1b4  test    rdx, rdx
0x18000d1b7  jnz     short loc_18000D1DC
0x18000d1b9  mov     rcx, [rsp+28h]; this
0x18000d1be  lea     r8, aCW1SSrcClientP_7; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18000d1c5  mov     r9d, 80004003h; char *
0x18000d1cb  mov     edx, 144h; void *
0x18000d1d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d1d5  mov     eax, 80004003h
0x18000d1da  jmp     short loc_18000D1E4
0x18000d1dc  mov     dword ptr [rdx], 0
0x18000d1e2  xor     eax, eax
0x18000d1e4  add     rsp, 28h
0x18000d1e8  retn
```
