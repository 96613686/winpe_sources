# DllGetActivationFactory

- ea: `0x18000bc90`
- end: `0x18000bd8f`
- name: `DllGetActivationFactory`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180001590`
- `0x18000a7bc`
- `0x18000a838`
- `0x18000aba0`
- `0x18000bc08`
- `0x18000bc90`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
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
0x18000bc90  mov     r11, rsp
0x18000bc93  mov     [r11+10h], rdx
0x18000bc97  mov     [r11+8], rcx
0x18000bc9b  push    rbx
0x18000bc9c  sub     rsp, 160h
0x18000bca3  mov     rax, cs:__security_cookie
0x18000bcaa  xor     rax, rsp
0x18000bcad  mov     [rsp+168h+var_18], rax
0x18000bcb5  lea     rax, off_18000F130
0x18000bcbc  mov     [r11-0E8h], rax
0x18000bcc3  lea     rax, [r11-0E8h]
0x18000bcca  mov     [r11-0B0h], rax
0x18000bcd1  lea     rax, off_18000F160
0x18000bcd8  mov     [rsp+168h+var_128], rax
0x18000bcdd  lea     rax, [rsp+168h+var_128]
0x18000bce2  mov     [rsp+168h+var_F0], rax
0x18000bce7  lea     rdx, [rsp+168h+var_128]
0x18000bcec  lea     rcx, [r11-0A8h]
0x18000bcf3  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18000bcf8  lea     rdx, [rsp+168h+var_E8]
0x18000bd00  lea     rcx, [rsp+168h+var_68]
0x18000bd08  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18000bd0d  mov     [rsp+168h+var_28], 1
0x18000bd15  lea     rcx, [rsp+168h+var_128]
0x18000bd1a  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18000bd1f  lea     rcx, [rsp+168h+var_E8]
0x18000bd27  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18000bd2c  nop
0x18000bd2d  lea     rax, [rsp+168h+arg_0]
0x18000bd35  mov     [rsp+168h+var_140], rax
0x18000bd3a  lea     rax, [rsp+168h+var_A8]
0x18000bd42  mov     [rsp+168h+var_138], rax
0x18000bd47  lea     rax, [rsp+168h+arg_8]
0x18000bd4f  mov     [rsp+168h+var_130], rax
0x18000bd54  lea     rdx, [rsp+168h+var_140]
0x18000bd59  call    api_guard__invoke_function_and_handle_exception__lambda_da1a1a09eda2cd8259e2f9e0eaa5a077____
0x18000bd5e  mov     ebx, eax
0x18000bd60  lea     rcx, [rsp+168h+var_A8]; this
0x18000bd68  call    ??1api_guard@@QEAA@XZ; api_guard::~api_guard(void)
0x18000bd6d  mov     eax, ebx
0x18000bd6f  jmp     short loc_18000BD75
0x18000bd71  mov     eax, [rsp+168h+var_148]
0x18000bd75  mov     rcx, [rsp+168h+var_18]
0x18000bd7d  xor     rcx, rsp; StackCookie
0x18000bd80  call    __security_check_cookie
0x18000bd85  add     rsp, 160h
0x18000bd8c  pop     rbx
0x18000bd8d  retn
```
