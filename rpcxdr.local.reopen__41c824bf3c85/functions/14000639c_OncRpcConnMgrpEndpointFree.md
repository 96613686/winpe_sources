# OncRpcConnMgrpEndpointFree

- ea: `0x14000639c`
- end: `0x140006425`
- name: `OncRpcConnMgrpEndpointFree`
- size: `137`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005c54`
- `0x140005dc8`
- `0x140006170`
- `0x1400083b8`
- `0x140010080`

## callees

- `0x1400059a4`
- `0x14000639c`
- `0x14000642c`
- `0x14000dd98`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpEndpointFree(_DWORD *P)
{
  int v3; // [rsp+20h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    v3 = P[12];
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids, P, v3);
  }
  if ( !*((_QWORD *)P + 12) )
    return OncRpcConnMgrpEndpointFreeInternal(P);
  P[28] &= ~1u;
  *((_QWORD *)P + 19) = *((_QWORD *)P + 13);
  *((_QWORD *)P + 15) = 0;
  *((_QWORD *)P + 16) = 0;
  *((_QWORD *)P + 20) = OncRpcConnMgrpEndpointClosePostIrpCompletionCallback;
  *((_QWORD *)P + 21) = P;
  return OncRpcConnMgrpWskEndpointSocketClose(P);
}

```

## disassembly

```asm
0x14000639c  push    rbx
0x14000639e  sub     rsp, 30h
0x1400063a2  mov     rbx, rcx
0x1400063a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400063ac  lea     rax, WPP_GLOBAL_Control
0x1400063b3  cmp     rcx, rax
0x1400063b6  jz      short loc_1400063DE
0x1400063b8  mov     eax, [rcx+2Ch]
0x1400063bb  test    al, 8
0x1400063bd  jz      short loc_1400063DE
0x1400063bf  mov     eax, [rbx+30h]
0x1400063c2  lea     r8, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids
0x1400063c9  mov     rcx, [rcx+18h]
0x1400063cd  mov     edx, 0Eh
0x1400063d2  mov     r9, rbx
0x1400063d5  mov     [rsp+38h+var_18], eax
0x1400063d9  call    WPP_SF_qd
0x1400063de  xor     ecx, ecx
0x1400063e0  cmp     [rbx+60h], rcx
0x1400063e4  jz      short loc_140006416
0x1400063e6  lea     rdx, [rbx+70h]
0x1400063ea  and     dword ptr [rdx], 0FFFFFFFEh
0x1400063ed  mov     rax, [rbx+68h]
0x1400063f1  mov     [rdx+28h], rax
0x1400063f5  lea     rax, OncRpcConnMgrpEndpointClosePostIrpCompletionCallback
0x1400063fc  mov     [rdx+8], rcx
0x140006400  mov     [rdx+10h], rcx
0x140006404  mov     rcx, rbx
0x140006407  mov     [rdx+30h], rax
0x14000640b  mov     [rdx+38h], rbx
0x14000640f  call    OncRpcConnMgrpWskEndpointSocketClose
0x140006414  jmp     short loc_14000641E
0x140006416  mov     rcx, rbx; P
0x140006419  call    OncRpcConnMgrpEndpointFreeInternal
0x14000641e  add     rsp, 30h
0x140006422  pop     rbx
0x140006423  retn
```
