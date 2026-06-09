# HUBHTX_CompleteGetPortStatusWithFailedStatus

- ea: `0x14000329c`
- end: `0x14000338b`
- name: `HUBHTX_CompleteGetPortStatusWithFailedStatus`
- size: `239`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400089e0`
- `0x14000b3ac`

## callees

- `0x14000329c`
- `0x140045530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBHTX_CompleteGetPortStatusWithFailedStatus(__int64 a1, unsigned int a2)
{
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int128 v7; // [rsp+20h] [rbp-38h] BYREF
  __int128 v8; // [rsp+30h] [rbp-28h]
  __int64 v9; // [rsp+40h] [rbp-18h]

  v9 = 0;
  v4 = *(_QWORD *)(a1 + 2544);
  v7 = 0;
  v8 = 0;
  if ( *(_DWORD *)(*(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2280))(
                                 WdfDriverGlobals,
                                 v4)
                             + 184)
                 + 24LL) == 2228243 )
  {
    v5 = *(_QWORD *)(a1 + 2544);
    v9 = 0;
    v7 = 0;
    LOWORD(v7) = 40;
    v8 = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2128))(
      WdfDriverGlobals,
      v5,
      &v7);
    **((_DWORD **)&v7 + 1) = 0;
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2104))(
           WdfDriverGlobals,
           *(_QWORD *)(a1 + 2544),
           a2);
}

```

## disassembly

```asm
0x14000329c  mov     [rsp+arg_10], rbx
0x1400032a1  push    rdi
0x1400032a2  sub     rsp, 50h
0x1400032a6  mov     rax, cs:__security_cookie
0x1400032ad  xor     rax, rsp
0x1400032b0  mov     [rsp+58h+var_10], rax
0x1400032b5  xor     eax, eax
0x1400032b7  xorps   xmm0, xmm0
0x1400032ba  mov     [rsp+58h+var_18], rax
0x1400032bf  mov     edi, edx
0x1400032c1  mov     rax, cs:WdfFunctions_01015
0x1400032c8  mov     rbx, rcx
0x1400032cb  mov     rdx, [rcx+9F0h]
0x1400032d2  mov     rcx, cs:WdfDriverGlobals
0x1400032d9  movups  [rsp+58h+var_38], xmm0
0x1400032de  movups  [rsp+58h+var_28], xmm0
0x1400032e3  mov     rax, [rax+8E8h]
0x1400032ea  call    _guard_dispatch_icall
0x1400032ef  mov     rcx, [rax+0B8h]
0x1400032f6  cmp     dword ptr [rcx+18h], 220013h
0x1400032fd  jnz     short loc_14000334E
0x1400032ff  mov     rdx, [rbx+9F0h]
0x140003306  lea     r8, [rsp+58h+var_38]
0x14000330b  mov     rcx, cs:WdfDriverGlobals
0x140003312  xor     eax, eax
0x140003314  mov     [rsp+58h+var_18], rax
0x140003319  xorps   xmm0, xmm0
0x14000331c  movups  [rsp+58h+var_38], xmm0
0x140003321  mov     eax, 28h ; '('
0x140003326  mov     word ptr [rsp+58h+var_38], ax
0x14000332b  mov     rax, cs:WdfFunctions_01015
0x140003332  movups  [rsp+58h+var_28], xmm0
0x140003337  mov     rax, [rax+850h]
0x14000333e  call    _guard_dispatch_icall
0x140003343  mov     rax, qword ptr [rsp+58h+var_38+8]
0x140003348  mov     dword ptr [rax], 0
0x14000334e  mov     rax, cs:WdfFunctions_01015
0x140003355  mov     r8d, edi
0x140003358  mov     rdx, [rbx+9F0h]
0x14000335f  mov     rcx, cs:WdfDriverGlobals
0x140003366  mov     rax, [rax+838h]
0x14000336d  call    _guard_dispatch_icall
0x140003372  mov     rcx, [rsp+58h+var_10]
0x140003377  xor     rcx, rsp; StackCookie
0x14000337a  call    __security_check_cookie
0x14000337f  mov     rbx, [rsp+58h+arg_10]
0x140003384  add     rsp, 50h
0x140003388  pop     rdi
0x140003389  retn
```
