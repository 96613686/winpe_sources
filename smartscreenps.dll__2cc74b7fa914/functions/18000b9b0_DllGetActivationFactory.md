# DllGetActivationFactory

- ea: `0x18000b9b0`
- end: `0x18000baaf`
- name: `DllGetActivationFactory`
- size: `255`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180001590`
- `0x18000a548`
- `0x18000a5c4`
- `0x18000a918`
- `0x18000b938`
- `0x18000b9b0`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  _QWORD v5[3]; // [rsp+28h] [rbp-140h] BYREF
  _QWORD v6[8]; // [rsp+40h] [rbp-128h] BYREF
  _QWORD v7[8]; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE v8[64]; // [rsp+C0h] [rbp-A8h] BYREF
  _BYTE v9[80]; // [rsp+100h] [rbp-68h] BYREF
  __int64 v10; // [rsp+170h] [rbp+8h] BYREF
  __int64 v11; // [rsp+178h] [rbp+10h] BYREF

  v11 = a2;
  v10 = a1;
  v7[0] = off_18000F130;
  v7[7] = v7;
  v6[0] = off_18000F160;
  v6[7] = v6;
  std::function<void (void)>::function<void (void)>(v8, v6);
  std::function<void (void)>::function<void (void)>(v9, v7);
  v9[64] = 1;
  std::_Func_class<void,>::_Tidy(v6);
  std::_Func_class<void,>::_Tidy(v7);
  v5[0] = &v10;
  v5[1] = v8;
  v5[2] = &v11;
  v3 = api_guard::invoke_function_and_handle_exception__lambda_da1a1a09eda2cd8259e2f9e0eaa5a077____(v2, v5);
  api_guard::~api_guard((api_guard *)v8);
  return v3;
}

```

## disassembly

```asm
0x18000b9b0  mov     r11, rsp
0x18000b9b3  mov     [r11+10h], rdx
0x18000b9b7  mov     [r11+8], rcx
0x18000b9bb  push    rbx
0x18000b9bc  sub     rsp, 160h
0x18000b9c3  mov     rax, cs:__security_cookie
0x18000b9ca  xor     rax, rsp
0x18000b9cd  mov     [rsp+168h+var_18], rax
0x18000b9d5  lea     rax, off_18000F130
0x18000b9dc  mov     [r11-0E8h], rax
0x18000b9e3  lea     rax, [r11-0E8h]
0x18000b9ea  mov     [r11-0B0h], rax
0x18000b9f1  lea     rax, off_18000F160
0x18000b9f8  mov     [rsp+168h+var_128], rax
0x18000b9fd  lea     rax, [rsp+168h+var_128]
0x18000ba02  mov     [rsp+168h+var_F0], rax
0x18000ba07  lea     rdx, [rsp+168h+var_128]
0x18000ba0c  lea     rcx, [r11-0A8h]
0x18000ba13  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18000ba18  lea     rdx, [rsp+168h+var_E8]
0x18000ba20  lea     rcx, [rsp+168h+var_68]
0x18000ba28  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18000ba2d  mov     [rsp+168h+var_28], 1
0x18000ba35  lea     rcx, [rsp+168h+var_128]
0x18000ba3a  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18000ba3f  lea     rcx, [rsp+168h+var_E8]
0x18000ba47  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18000ba4c  nop
0x18000ba4d  lea     rax, [rsp+168h+arg_0]
0x18000ba55  mov     [rsp+168h+var_140], rax
0x18000ba5a  lea     rax, [rsp+168h+var_A8]
0x18000ba62  mov     [rsp+168h+var_138], rax
0x18000ba67  lea     rax, [rsp+168h+arg_8]
0x18000ba6f  mov     [rsp+168h+var_130], rax
0x18000ba74  lea     rdx, [rsp+168h+var_140]
0x18000ba79  call    api_guard__invoke_function_and_handle_exception__lambda_da1a1a09eda2cd8259e2f9e0eaa5a077____
0x18000ba7e  mov     ebx, eax
0x18000ba80  lea     rcx, [rsp+168h+var_A8]; this
0x18000ba88  call    ??1api_guard@@QEAA@XZ; api_guard::~api_guard(void)
0x18000ba8d  mov     eax, ebx
0x18000ba8f  jmp     short loc_18000BA95
0x18000ba91  mov     eax, [rsp+168h+var_148]
0x18000ba95  mov     rcx, [rsp+168h+var_18]
0x18000ba9d  xor     rcx, rsp; StackCookie
0x18000baa0  call    __security_check_cookie
0x18000baa5  add     rsp, 160h
0x18000baac  pop     rbx
0x18000baad  retn
```
