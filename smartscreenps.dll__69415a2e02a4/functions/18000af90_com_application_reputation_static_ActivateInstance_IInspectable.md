# com::application_reputation_static::ActivateInstance(IInspectable * *)

- ea: `0x18000af90`
- end: `0x18000afd5`
- name: `?ActivateInstance@application_reputation_static@com@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(com::application_reputation_static *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001590`
- `0x18000a77c`
- `0x18000a824`

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
0x18000af90  sub     rsp, 48h
0x18000af94  mov     rax, cs:__security_cookie
0x18000af9b  xor     rax, rsp
0x18000af9e  mov     [rsp+48h+var_10], rax
0x18000afa3  mov     [rsp+48h+var_18], rdx
0x18000afa8  lea     r8, [rsp+48h+var_18]; struct IInspectable ***
0x18000afad  mov     rdx, rcx; struct com::application_reputation_static *
0x18000afb0  lea     rcx, [rsp+48h+var_28]; this
0x18000afb5  call    ??0_lambda_2ea365fc3ebadc6e39f186d083e465ed_@@QEAA@PEAVapplication_reputation_static@com@@AEAPEAPEAUIInspectable@@@Z; _lambda_2ea365fc3ebadc6e39f186d083e465ed_::_lambda_2ea365fc3ebadc6e39f186d083e465ed_(com::application_reputation_static *,IInspectable * * &)
0x18000afba  mov     rdx, rax
0x18000afbd  call    ??$invoke_function_and_handle_exception@AEAV_lambda_2ea365fc3ebadc6e39f186d083e465ed_@@@api_guard@@QEBA?A_PAEAV_lambda_2ea365fc3ebadc6e39f186d083e465ed_@@@Z
0x18000afc2  mov     rcx, [rsp+48h+var_10]
0x18000afc7  xor     rcx, rsp; StackCookie
0x18000afca  call    __security_check_cookie
0x18000afcf  add     rsp, 48h
0x18000afd3  retn
```
