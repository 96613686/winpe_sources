# OncRpcConnMgrpConnectionSendPostIrpCompletionCallback

- ea: `0x140008760`
- end: `0x140008805`
- name: `OncRpcConnMgrpConnectionSendPostIrpCompletionCallback`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140008034`
- `0x140008760`
- `0x140008878`
- `0x140015680`

## pseudocode

```c
__int64 (__fastcall *__fastcall OncRpcConnMgrpConnectionSendPostIrpCompletionCallback(
        _QWORD *a1))(_QWORD, _QWORD, _QWORD)
{
  int v2; // esi
  __int64 v3; // rdi
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD); // rax

  v2 = *(_DWORD *)(a1[5] + 48LL);
  if ( v2 )
  {
    v3 = a1[7];
    if ( v3 )
    {
      if ( v2 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      {
        WPP_SF_qdLd(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          *(unsigned int *)(v3 + 4),
          v3,
          *(_DWORD *)(v3 + 4),
          *(_DWORD *)(v3 + 80),
          v2);
      }
      OncRpcConnMgrpConnectionDisconnectBySystem(v3);
    }
  }
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))a1[1];
  if ( result )
    return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))result((unsigned int)v2, *(_QWORD *)(a1[5] + 56LL), a1[2]);
  return result;
}

```

## disassembly

```asm
0x140008760  mov     [rsp+arg_0], rbx
0x140008765  mov     [rsp+arg_8], rsi
0x14000876a  push    rdi
0x14000876b  sub     rsp, 40h
0x14000876f  mov     rax, [rcx+28h]
0x140008773  mov     rbx, rcx
0x140008776  mov     esi, [rax+30h]
0x140008779  test    esi, esi
0x14000877b  jz      short loc_1400087D8
0x14000877d  mov     rdi, [rcx+38h]
0x140008781  test    rdi, rdi
0x140008784  jz      short loc_1400087D8
0x140008786  test    esi, esi
0x140008788  jns     short loc_1400087D0
0x14000878a  mov     rax, cs:WPP_GLOBAL_Control
0x140008791  lea     rcx, WPP_GLOBAL_Control
0x140008798  cmp     rax, rcx
0x14000879b  jz      short loc_1400087D0
0x14000879d  mov     eax, [rax+2Ch]
0x1400087a0  test    al, 8
0x1400087a2  jz      short loc_1400087D0
0x1400087a4  mov     r8d, [rdi+4]
0x1400087a8  mov     edx, 20h ; ' '
0x1400087ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087b4  mov     r9, rdi
0x1400087b7  mov     eax, [rdi+50h]
0x1400087ba  mov     [rsp+48h+var_18], esi
0x1400087be  mov     [rsp+48h+var_20], eax
0x1400087c2  mov     rcx, [rcx+18h]
0x1400087c6  mov     [rsp+48h+var_28], r8d
0x1400087cb  call    WPP_SF_qdLd
0x1400087d0  mov     rcx, rdi
0x1400087d3  call    OncRpcConnMgrpConnectionDisconnectBySystem
0x1400087d8  mov     rax, [rbx+8]
0x1400087dc  test    rax, rax
0x1400087df  jz      short loc_1400087F4
0x1400087e1  mov     rdx, [rbx+28h]
0x1400087e5  mov     ecx, esi
0x1400087e7  mov     r8, [rbx+10h]
0x1400087eb  mov     rdx, [rdx+38h]
0x1400087ef  call    _guard_dispatch_icall
0x1400087f4  mov     rbx, [rsp+48h+arg_0]
0x1400087f9  mov     rsi, [rsp+48h+arg_8]
0x1400087fe  add     rsp, 40h
0x140008802  pop     rdi
0x140008803  retn
```
