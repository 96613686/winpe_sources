# com::application_reputation_static::ActivateInstance(IInspectable * *)

- ea: `0x18000ad00`
- end: `0x18000ad44`
- name: `?ActivateInstance@application_reputation_static@com@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `68`
- prototype: `__int64 __fastcall(com::application_reputation_static *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001590`
- `0x18000a508`
- `0x18000a5b0`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::ActivateInstance(
        com::application_reputation_static *this,
        struct IInspectable **a2)
{
  _lambda_2ea365fc3ebadc6e39f186d083e465ed_ *v2; // rax
  __int64 v3; // rcx
  _BYTE v5[16]; // [rsp+20h] [rbp-28h] BYREF
  struct IInspectable **v6; // [rsp+30h] [rbp-18h] BYREF

  v6 = a2;
  v2 = _lambda_2ea365fc3ebadc6e39f186d083e465ed_::_lambda_2ea365fc3ebadc6e39f186d083e465ed_(
         (_lambda_2ea365fc3ebadc6e39f186d083e465ed_ *)v5,
         this,
         &v6);
  return api_guard::invoke_function_and_handle_exception<_lambda_2ea365fc3ebadc6e39f186d083e465ed_ &>(v3, v2);
}

```

## disassembly

```asm
0x18000ad00  sub     rsp, 48h
0x18000ad04  mov     rax, cs:__security_cookie
0x18000ad0b  xor     rax, rsp
0x18000ad0e  mov     [rsp+48h+var_10], rax
0x18000ad13  mov     [rsp+48h+var_18], rdx
0x18000ad18  lea     r8, [rsp+48h+var_18]; struct IInspectable ***
0x18000ad1d  mov     rdx, rcx; struct com::application_reputation_static *
0x18000ad20  lea     rcx, [rsp+48h+var_28]; this
0x18000ad25  call    ??0_lambda_2ea365fc3ebadc6e39f186d083e465ed_@@QEAA@PEAVapplication_reputation_static@com@@AEAPEAPEAUIInspectable@@@Z; _lambda_2ea365fc3ebadc6e39f186d083e465ed_::_lambda_2ea365fc3ebadc6e39f186d083e465ed_(com::application_reputation_static *,IInspectable * * &)
0x18000ad2a  mov     rdx, rax
0x18000ad2d  call    ??$invoke_function_and_handle_exception@AEAV_lambda_2ea365fc3ebadc6e39f186d083e465ed_@@@api_guard@@QEBA?A_PAEAV_lambda_2ea365fc3ebadc6e39f186d083e465ed_@@@Z
0x18000ad32  mov     rcx, [rsp+48h+var_10]
0x18000ad37  xor     rcx, rsp; StackCookie
0x18000ad3a  call    __security_check_cookie
0x18000ad3f  add     rsp, 48h
0x18000ad43  retn
```
