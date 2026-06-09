# WdipHandleInstance

- ea: `0x180001010`
- end: `0x18000106d`
- name: `WdipHandleInstance`
- size: `93`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800063d0`
- `0x18000d228`

## callees

- `0x180001010`
- `0x180001080`
- `0x1800011d0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall WdipHandleInstance(unsigned int a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  unsigned int v4; // edi
  int v9; // [rsp+58h] [rbp+10h] BYREF

  v3 = (*(_BYTE *)(a2 + 80) & 0x10) == 0;
  v4 = 255;
  v9 = 255;
  if ( v3 )
  {
    WdipLowerPagePriorityThread(&v9);
    v4 = v9;
  }
  *(_DWORD *)(*(_QWORD *)(a3 + 40) + 112LL) = (*(__int64 (__fastcall **)(__int64, _QWORD))(a2 + 40))(a3, a1);
  if ( (*(_BYTE *)(a2 + 80) & 0x10) == 0 )
    WdipRevertPagePriorityThread(v4);
  return 0;
}

```

## disassembly

```asm
0x180001010  push    rbx
0x180001012  push    rbp
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  sub     rsp, 28h
0x180001019  test    byte ptr [rdx+50h], 10h
0x18000101d  mov     edi, 0FFh
0x180001022  mov     [rsp+48h+arg_8], edi
0x180001026  mov     rsi, r8
0x180001029  mov     rbx, rdx
0x18000102c  mov     ebp, ecx
0x18000102e  jz      short loc_18000105D
0x180001030  mov     rax, [rbx+28h]
0x180001034  mov     edx, ebp
0x180001036  mov     rcx, rsi
0x180001039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000103e  mov     rdx, [rsi+28h]
0x180001042  mov     [rdx+70h], eax
0x180001045  test    byte ptr [rbx+50h], 10h
0x180001049  jnz     short loc_180001052
0x18000104b  mov     ecx, edi
0x18000104d  call    WdipRevertPagePriorityThread
0x180001052  xor     eax, eax
0x180001054  add     rsp, 28h
0x180001058  pop     rdi
0x180001059  pop     rsi
0x18000105a  pop     rbp
0x18000105b  pop     rbx
0x18000105c  retn
0x18000105d  lea     rcx, [rsp+48h+arg_8]
0x180001062  call    WdipLowerPagePriorityThread
0x180001067  mov     edi, [rsp+48h+arg_8]
0x18000106b  jmp     short loc_180001030
```
