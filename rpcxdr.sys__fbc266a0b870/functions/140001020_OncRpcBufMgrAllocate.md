# OncRpcBufMgrAllocate

- ea: `0x140001020`
- end: `0x1400010d3`
- name: `OncRpcBufMgrAllocate`
- size: `179`
- prototype: `__int64 __fastcall(__int64 *, int, int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140002514`
- `0x140003bd4`
- `0x140006850`
- `0x140008988`
- `0x140009700`
- `0x14000df80`
- `0x14000e8e0`

## callees

- `0x140001020`
- `0x1400015ec`
- `0x1400020c0`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrAllocate(__int64 *a1, int a2, int a3)
{
  unsigned int v4; // edi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // [rsp+30h] [rbp-18h] BYREF

  v11 = 0;
  if ( !a2 )
  {
    v4 = -1073741789;
LABEL_3:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_bc787cf5db083b51efc6e85b805038bb_Traceguids, v4);
    return v4;
  }
  v4 = OncRpcBufMgrpAllocate((_DWORD)a1, (unsigned int)&v11, a2, a3);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_3;
  v6 = *a1;
  v7 = v11;
  *(_QWORD *)(v6 + 40) = v11;
  v8 = v6 + 24;
  v9 = *(_QWORD **)(v8 + 8);
  if ( *v9 != v8 )
    __fastfail(3u);
  v10 = (_QWORD *)(v7 + 24);
  *v10 = v8;
  v10[1] = v9;
  *v9 = v10;
  *(_QWORD *)(v8 + 8) = v10;
  return v4;
}

```

## disassembly

```asm
0x140001020  mov     [rsp+arg_0], rbx
0x140001025  push    rdi
0x140001026  sub     rsp, 40h
0x14000102a  mov     [rsp+48h+var_18], 0
0x140001033  mov     rbx, rcx
0x140001036  test    edx, edx
0x140001038  jnz     short loc_14000107F
0x14000103a  mov     edi, 0C0000023h
0x14000103f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001046  lea     rax, WPP_GLOBAL_Control
0x14000104d  cmp     rcx, rax
0x140001050  jz      short loc_140001071
0x140001052  mov     eax, [rcx+2Ch]
0x140001055  test    al, 2
0x140001057  jz      short loc_140001071
0x140001059  mov     rcx, [rcx+18h]
0x14000105d  lea     r8, WPP_bc787cf5db083b51efc6e85b805038bb_Traceguids
0x140001064  mov     edx, 0Fh
0x140001069  mov     r9d, edi
0x14000106c  call    WPP_SF_d
0x140001071  mov     rbx, [rsp+48h+arg_0]
0x140001076  mov     eax, edi
0x140001078  add     rsp, 40h
0x14000107c  pop     rdi
0x14000107d  retn
0x14000107f  mov     rax, [rsp+48h+arg_20]
0x140001084  mov     r9d, r8d
0x140001087  mov     r8d, edx
0x14000108a  mov     [rsp+48h+var_20], rax
0x14000108f  lea     rdx, [rsp+48h+var_18]
0x140001094  call    OncRpcBufMgrpAllocate
0x140001099  mov     edi, eax
0x14000109b  test    eax, eax
0x14000109d  js      short loc_14000103F
0x14000109f  mov     rcx, [rbx]
0x1400010a2  mov     rax, [rsp+48h+var_18]
0x1400010a7  mov     [rcx+28h], rax
0x1400010ab  add     rcx, 18h
0x1400010af  mov     rdx, [rcx+8]
0x1400010b3  cmp     [rdx], rcx
0x1400010b6  jz      short loc_1400010BF
0x1400010b8  mov     ecx, 3
0x1400010bd  int     29h; Win8: RtlFailFast(ecx)
0x1400010bf  add     rax, 18h
0x1400010c3  mov     [rax], rcx
0x1400010c6  mov     [rax+8], rdx
0x1400010ca  mov     [rdx], rax
0x1400010cd  mov     [rcx+8], rax
0x1400010d1  jmp     short loc_140001071
```
