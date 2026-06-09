# EtwLogThreadShutdownNotifyStart

- ea: `0x1800063a0`
- end: `0x180006460`
- name: `EtwLogThreadShutdownNotifyStart`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009688`

## callees

- `0x1800063a0`
- `0x1800138f0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000643c`
- `ntdll!EtwEventWrite` at `0x18000643c`
- `ntdll!EtwEventEnabled` at `0x1800063d5`
- `ntdll!EtwEventEnabled` at `0x1800063d5`

## pseudocode

```c
void __fastcall EtwLogThreadShutdownNotifyStart(int a1, __int64 a2)
{
  int v3; // ecx
  int v4; // [rsp+20h] [rbp-40h] BYREF
  int v5; // [rsp+24h] [rbp-3Ch] BYREF
  _QWORD v6[6]; // [rsp+28h] [rbp-38h] BYREF
  int v7; // [rsp+70h] [rbp+10h] BYREF

  v7 = a1;
  if ( g_EtwRegHandle )
  {
    if ( (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_ThreadShutdown_Start) )
    {
      v4 = *(_DWORD *)(a2 + 48);
      v3 = **(_DWORD **)(a2 + 56);
      v6[0] = &v4;
      v6[2] = &v7;
      v5 = v3;
      v6[4] = &v5;
      v6[1] = 4;
      v6[3] = 4;
      v6[5] = 4;
      EtwEventWrite(g_EtwRegHandle, WinSrvEvt_ThreadShutdown_Start, 3, v6);
    }
  }
}

```

## disassembly

```asm
0x1800063a0  mov     [rsp-8+arg_8], rbx
0x1800063a5  mov     [rsp-8+arg_0], ecx
0x1800063a9  push    rbp
0x1800063aa  mov     rbp, rsp
0x1800063ad  sub     rsp, 60h
0x1800063b1  mov     rax, cs:__security_cookie
0x1800063b8  xor     rax, rsp
0x1800063bb  mov     [rbp+var_8], rax
0x1800063bf  mov     rcx, cs:g_EtwRegHandle
0x1800063c6  mov     rbx, rdx
0x1800063c9  test    rcx, rcx
0x1800063cc  jz      short loc_180006448
0x1800063ce  lea     rdx, WinSrvEvt_ThreadShutdown_Start
0x1800063d5  call    cs:__imp_EtwEventEnabled
0x1800063dc  nop     dword ptr [rax+rax+00h]
0x1800063e1  test    al, al
0x1800063e3  jz      short loc_180006448
0x1800063e5  mov     eax, [rbx+30h]
0x1800063e8  lea     r9, [rbp+var_38]
0x1800063ec  mov     [rbp+var_40], eax
0x1800063ef  lea     rdx, WinSrvEvt_ThreadShutdown_Start
0x1800063f6  mov     rax, [rbx+38h]
0x1800063fa  mov     r8d, 3
0x180006400  mov     ecx, [rax]
0x180006402  lea     rax, [rbp+var_40]
0x180006406  mov     [rbp+var_38], rax
0x18000640a  lea     rax, [rbp+arg_0]
0x18000640e  mov     [rbp+var_28], rax
0x180006412  lea     rax, [rbp+var_3C]
0x180006416  mov     [rbp+var_3C], ecx
0x180006419  mov     rcx, cs:g_EtwRegHandle
0x180006420  mov     [rbp+var_18], rax
0x180006424  mov     [rbp+var_30], 4
0x18000642c  mov     [rbp+var_20], 4
0x180006434  mov     [rbp+var_10], 4
0x18000643c  call    cs:__imp_EtwEventWrite
0x180006443  nop     dword ptr [rax+rax+00h]
0x180006448  mov     rcx, [rbp+var_8]
0x18000644c  xor     rcx, rsp; StackCookie
0x18000644f  call    __security_check_cookie
0x180006454  mov     rbx, [rsp+60h+arg_8]
0x180006459  add     rsp, 60h
0x18000645d  pop     rbp
0x18000645e  retn
```
