# OncRpcBufMgrAllocate

- ea: `0x140001020`
- end: `0x1400010d3`
- name: `OncRpcBufMgrAllocate`
- size: `179`
- prototype: ``
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
__int64 __fastcall OncRpcBufMgrAllocate(__int64 *a1, int a2, unsigned int a3, __int64 a4, __int64 a5)
{
  int v6; // edi
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  _QWORD *v12; // rax
  int v13; // [rsp+20h] [rbp-28h]
  _QWORD v14[3]; // [rsp+30h] [rbp-18h] BYREF

  v14[0] = 0;
  if ( !a2 )
  {
    v6 = -1073741789;
LABEL_3:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xFu,
        (__int64)WPP_bc787cf5db083b51efc6e85b805038bb_Traceguids,
        v6);
    return (unsigned int)v6;
  }
  v6 = OncRpcBufMgrpAllocate(a1, v14, a2, a3, v13, a5);
  if ( v6 < 0 )
    goto LABEL_3;
  v8 = *a1;
  v9 = v14[0];
  *(_QWORD *)(v8 + 40) = v14[0];
  v10 = v8 + 24;
  v11 = *(_QWORD **)(v10 + 8);
  if ( *v11 != v10 )
    __fastfail(3u);
  v12 = (_QWORD *)(v9 + 24);
  *v12 = v10;
  v12[1] = v11;
  *v11 = v12;
  *(_QWORD *)(v10 + 8) = v12;
  return (unsigned int)v6;
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
