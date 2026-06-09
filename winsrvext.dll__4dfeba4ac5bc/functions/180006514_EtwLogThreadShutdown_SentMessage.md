# EtwLogThreadShutdown_SentMessage

- ea: `0x180006514`
- end: `0x1800065cd`
- name: `EtwLogThreadShutdown_SentMessage`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008c10`

## callees

- `0x180006514`
- `0x1800138f0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800065a9`
- `ntdll!EtwEventWrite` at `0x1800065a9`
- `ntdll!EtwEventEnabled` at `0x18000654e`
- `ntdll!EtwEventEnabled` at `0x18000654e`

## pseudocode

```c
void __fastcall EtwLogThreadShutdown_SentMessage(int a1, int a2, int a3)
{
  int v4; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v5[6]; // [rsp+28h] [rbp-38h] BYREF
  int v6; // [rsp+70h] [rbp+10h] BYREF
  int v7; // [rsp+80h] [rbp+20h] BYREF

  v7 = a3;
  v6 = a1;
  if ( g_EtwRegHandle )
  {
    if ( (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_ThreadShutdown_SentMessage) )
    {
      v5[0] = &v6;
      v4 = a2;
      v5[2] = &v4;
      v5[1] = 4;
      v5[4] = &v7;
      v5[3] = 4;
      v5[5] = 4;
      EtwEventWrite(g_EtwRegHandle, WinSrvEvt_ThreadShutdown_SentMessage, 3, v5);
    }
  }
}

```

## disassembly

```asm
0x180006514  mov     [rsp-8+arg_8], rbx
0x180006519  mov     [rsp-8+arg_10], r8d
0x18000651e  mov     [rsp-8+arg_0], ecx
0x180006522  push    rbp
0x180006523  mov     rbp, rsp
0x180006526  sub     rsp, 60h
0x18000652a  mov     rax, cs:__security_cookie
0x180006531  xor     rax, rsp
0x180006534  mov     [rbp+var_8], rax
0x180006538  mov     rcx, cs:g_EtwRegHandle
0x18000653f  mov     rbx, rdx
0x180006542  test    rcx, rcx
0x180006545  jz      short loc_1800065B5
0x180006547  lea     rdx, WinSrvEvt_ThreadShutdown_SentMessage
0x18000654e  call    cs:__imp_EtwEventEnabled
0x180006555  nop     dword ptr [rax+rax+00h]
0x18000655a  test    al, al
0x18000655c  jz      short loc_1800065B5
0x18000655e  mov     rcx, cs:g_EtwRegHandle
0x180006565  lea     rax, [rbp+arg_0]
0x180006569  mov     [rbp+var_38], rax
0x18000656d  lea     r9, [rbp+var_38]
0x180006571  lea     rax, [rbp+var_40]
0x180006575  mov     [rbp+var_40], ebx
0x180006578  mov     [rbp+var_28], rax
0x18000657c  lea     rdx, WinSrvEvt_ThreadShutdown_SentMessage
0x180006583  lea     rax, [rbp+arg_10]
0x180006587  mov     [rbp+var_30], 4
0x18000658f  mov     r8d, 3
0x180006595  mov     [rbp+var_18], rax
0x180006599  mov     [rbp+var_20], 4
0x1800065a1  mov     [rbp+var_10], 4
0x1800065a9  call    cs:__imp_EtwEventWrite
0x1800065b0  nop     dword ptr [rax+rax+00h]
0x1800065b5  mov     rcx, [rbp+var_8]
0x1800065b9  xor     rcx, rsp; StackCookie
0x1800065bc  call    __security_check_cookie
0x1800065c1  mov     rbx, [rsp+60h+arg_8]
0x1800065c6  add     rsp, 60h
0x1800065ca  pop     rbp
0x1800065cb  retn
```
