# CWMPRichPreviewRemoteService::LaunchFullPlayer(void)

- ea: `0x140005de0`
- end: `0x140005edc`
- name: `?LaunchFullPlayer@CWMPRichPreviewRemoteService@@UEAAJXZ`
- size: `252`
- prototype: `__int64 __fastcall(CWMPRichPreviewRemoteService *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140005de0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewRemoteService::LaunchFullPlayer(CWMPRichPreviewRemoteService *this)
{
  __int64 v1; // rax
  __int64 v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+10h] BYREF
  __int64 v6; // [rsp+38h] [rbp+18h] BYREF
  double v7; // [rsp+40h] [rbp+20h] BYREF

  v1 = *((_QWORD *)this + 4);
  if ( v1 )
  {
    v3 = *(_QWORD *)(v1 + 48);
    if ( v3 )
    {
      v6 = 0;
      v7 = 0.0;
      v5 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 96LL))(v3, &v5) >= 0
        && (*(int (__fastcall **)(__int64, double *))(*(_QWORD *)v5 + 104LL))(v5, &v7) >= 0
        && (***(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 4) + 48LL))(
             *(_QWORD *)(*((_QWORD *)this + 4) + 48LL),
             &GUID_3608a1bb_1883_4cc0_9da8_b4cf25943842,
             &v6) >= 0
        && (*(int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 168LL))(
             v6,
             *(_QWORD *)(*((_QWORD *)this + 4) + 56LL),
             (unsigned int)(int)v7) >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 80LL))(v5);
      }
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140005de0  mov     [rsp-8+arg_18], rbx
0x140005de5  push    rbp
0x140005de6  mov     rbp, rsp
0x140005de9  sub     rsp, 20h
0x140005ded  mov     rax, [rcx+20h]
0x140005df1  mov     rbx, rcx
0x140005df4  test    rax, rax
0x140005df7  jz      loc_140005ECF
0x140005dfd  mov     rcx, [rax+30h]
0x140005e01  test    rcx, rcx
0x140005e04  jz      loc_140005ECF
0x140005e0a  xorps   xmm0, xmm0
0x140005e0d  mov     [rbp+arg_8], 0
0x140005e15  movsd   [rbp+arg_10], xmm0
0x140005e1a  lea     rdx, [rbp+arg_0]
0x140005e1e  mov     [rbp+arg_0], 0
0x140005e26  mov     rax, [rcx]
0x140005e29  mov     rax, [rax+60h]
0x140005e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e32  test    eax, eax
0x140005e34  js      short loc_140005EA5
0x140005e36  mov     rcx, [rbp+arg_0]
0x140005e3a  lea     rdx, [rbp+arg_10]
0x140005e3e  mov     rax, [rcx]
0x140005e41  mov     rax, [rax+68h]
0x140005e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e4a  test    eax, eax
0x140005e4c  js      short loc_140005EA5
0x140005e4e  mov     rax, [rbx+20h]
0x140005e52  lea     r8, [rbp+arg_8]
0x140005e56  lea     rdx, _GUID_3608a1bb_1883_4cc0_9da8_b4cf25943842
0x140005e5d  mov     rcx, [rax+30h]
0x140005e61  mov     rax, [rcx]
0x140005e64  mov     rax, [rax]
0x140005e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e6c  test    eax, eax
0x140005e6e  js      short loc_140005EA5
0x140005e70  mov     rcx, [rbp+arg_8]
0x140005e74  mov     rdx, [rbx+20h]
0x140005e78  cvttsd2si r8, [rbp+arg_10]
0x140005e7e  mov     rax, [rcx]
0x140005e81  mov     rdx, [rdx+38h]
0x140005e85  mov     rax, [rax+0A8h]
0x140005e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e91  test    eax, eax
0x140005e93  js      short loc_140005EA5
0x140005e95  mov     rcx, [rbp+arg_0]
0x140005e99  mov     rax, [rcx]
0x140005e9c  mov     rax, [rax+50h]
0x140005ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ea5  mov     rcx, [rbp+arg_0]
0x140005ea9  test    rcx, rcx
0x140005eac  jz      short loc_140005EBA
0x140005eae  mov     rax, [rcx]
0x140005eb1  mov     rax, [rax+10h]
0x140005eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eba  mov     rcx, [rbp+arg_8]
0x140005ebe  test    rcx, rcx
0x140005ec1  jz      short loc_140005ECF
0x140005ec3  mov     rax, [rcx]
0x140005ec6  mov     rax, [rax+10h]
0x140005eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ecf  mov     rbx, [rsp+20h+arg_18]
0x140005ed4  xor     eax, eax
0x140005ed6  add     rsp, 20h
0x140005eda  pop     rbp
0x140005edb  retn
```
