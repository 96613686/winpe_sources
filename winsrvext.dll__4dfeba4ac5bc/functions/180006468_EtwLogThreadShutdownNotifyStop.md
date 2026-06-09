# EtwLogThreadShutdownNotifyStop

- ea: `0x180006468`
- end: `0x18000650c`
- name: `EtwLogThreadShutdownNotifyStop`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009688`

## callees

- `0x180006468`
- `0x1800138f0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800064ec`
- `ntdll!EtwEventWrite` at `0x1800064ec`
- `ntdll!EtwEventEnabled` at `0x180006496`
- `ntdll!EtwEventEnabled` at `0x180006496`

## pseudocode

```c
void __fastcall EtwLogThreadShutdownNotifyStop(int a1, __int64 a2)
{
  int v3; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v4[4]; // [rsp+28h] [rbp-30h] BYREF
  int v5; // [rsp+60h] [rbp+8h] BYREF

  v5 = a1;
  if ( g_EtwRegHandle )
  {
    if ( (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_ThreadShutdown_Stop) )
    {
      v3 = *(_DWORD *)(a2 + 48);
      v4[1] = 4;
      v4[0] = &v5;
      v4[2] = &v3;
      v4[3] = 4;
      EtwEventWrite(g_EtwRegHandle, WinSrvEvt_ThreadShutdown_Stop, 2, v4);
    }
  }
}

```

## disassembly

```asm
0x180006468  mov     [rsp+arg_0], ecx
0x18000646c  push    rbx
0x18000646d  sub     rsp, 50h
0x180006471  mov     rax, cs:__security_cookie
0x180006478  xor     rax, rsp
0x18000647b  mov     [rsp+58h+var_10], rax
0x180006480  mov     rcx, cs:g_EtwRegHandle
0x180006487  mov     rbx, rdx
0x18000648a  test    rcx, rcx
0x18000648d  jz      short loc_1800064F8
0x18000648f  lea     rdx, WinSrvEvt_ThreadShutdown_Stop
0x180006496  call    cs:__imp_EtwEventEnabled
0x18000649d  nop     dword ptr [rax+rax+00h]
0x1800064a2  test    al, al
0x1800064a4  jz      short loc_1800064F8
0x1800064a6  mov     eax, [rbx+30h]
0x1800064a9  lea     r9, [rsp+58h+var_30]
0x1800064ae  mov     rcx, cs:g_EtwRegHandle
0x1800064b5  lea     rdx, WinSrvEvt_ThreadShutdown_Stop
0x1800064bc  mov     [rsp+58h+var_38], eax
0x1800064c0  mov     r8d, 2
0x1800064c6  lea     rax, [rsp+58h+arg_0]
0x1800064cb  mov     [rsp+58h+var_28], 4
0x1800064d4  mov     [rsp+58h+var_30], rax
0x1800064d9  lea     rax, [rsp+58h+var_38]
0x1800064de  mov     [rsp+58h+var_20], rax
0x1800064e3  mov     [rsp+58h+var_18], 4
0x1800064ec  call    cs:__imp_EtwEventWrite
0x1800064f3  nop     dword ptr [rax+rax+00h]
0x1800064f8  mov     rcx, [rsp+58h+var_10]
0x1800064fd  xor     rcx, rsp; StackCookie
0x180006500  call    __security_check_cookie
0x180006505  add     rsp, 50h
0x180006509  pop     rbx
0x18000650a  retn
```
