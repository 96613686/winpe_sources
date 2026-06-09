# MoveCaptureNode

- ea: `0x180023d60`
- end: `0x180023ef1`
- name: `MoveCaptureNode`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800219c4`
- `0x180023d60`
- `0x180060e42`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180023dca`
- `KERNEL32!HeapAlloc` at `0x180023dca`
- `KERNEL32!GetProcessHeap` at `0x180023db6`
- `KERNEL32!GetProcessHeap` at `0x180023db6`

## string_xrefs

- `0x180023de3`: `MoveCaptureNode`
- `0x180023ec5`: `MoveCaptureNode`

## pseudocode

```c
__int64 __fastcall MoveCaptureNode(__int64 a1, _QWORD *a2)
{
  unsigned int v2; // edi
  unsigned __int64 v5; // rsi
  HANDLE ProcessHeap; // rax
  __int64 v7; // rdx
  _OWORD *v8; // rbx
  unsigned int v9; // r8d

  v2 = 0;
  if ( *(_DWORD *)(a1 + 24) )
  {
    *a2 = a1;
    return v2;
  }
  v5 = 16LL * *(unsigned int *)(a1 + 184);
  if ( v5 > 0xFFFFFFFF )
  {
    v9 = 169;
    goto LABEL_11;
  }
  if ( (int)v5 + 192 < (unsigned int)v5 )
  {
    v9 = 172;
LABEL_11:
    v2 = -2147024362;
    UtilReportError((__int64)L"MoveCaptureNode", (__int64)a2, v9, -2147024362);
    return v2;
  }
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 0, (unsigned int)(v5 + 192));
  if ( !v8 )
  {
    v2 = -2147024882;
    UtilReportError((__int64)L"MoveCaptureNode", v7, 0xB6u, -2147024882);
  }
  if ( (v2 & 0x80000000) == 0 )
  {
    *v8 = *(_OWORD *)a1;
    v8[1] = *(_OWORD *)(a1 + 16);
    v8[2] = *(_OWORD *)(a1 + 32);
    v8[3] = *(_OWORD *)(a1 + 48);
    v8[4] = *(_OWORD *)(a1 + 64);
    v8[5] = *(_OWORD *)(a1 + 80);
    v8[6] = *(_OWORD *)(a1 + 96);
    v8[7] = *(_OWORD *)(a1 + 112);
    v8[8] = *(_OWORD *)(a1 + 128);
    v8[9] = *(_OWORD *)(a1 + 144);
    v8[10] = *(_OWORD *)(a1 + 160);
    v8[11] = *(_OWORD *)(a1 + 176);
    *((_DWORD *)v8 + 6) = 1;
    *((_QWORD *)v8 + 22) = v8 + 12;
    memcpy_0(v8 + 12, *(const void **)(a1 + 176), (unsigned int)v5);
    *(_QWORD *)(a1 + 64) = 0;
    *(_QWORD *)(a1 + 56) = 0;
    *(_QWORD *)(a1 + 144) = 0;
    *(_QWORD *)(a1 + 48) = -1;
    *(_QWORD *)(a1 + 40) = -1;
    *a2 = v8;
  }
  return v2;
}

```

## disassembly

```asm
0x180023d60  mov     rax, rsp
0x180023d63  mov     [rax+8], rbx
0x180023d67  mov     [rax+10h], rbp
0x180023d6b  mov     [rax+18h], rsi
0x180023d6f  mov     [rax+20h], rdi
0x180023d73  push    r14
0x180023d75  sub     rsp, 20h
0x180023d79  xor     edi, edi
0x180023d7b  mov     r14, rdx
0x180023d7e  mov     rbp, rcx
0x180023d81  cmp     [rcx+18h], edi
0x180023d84  jz      short loc_180023D8E
0x180023d86  mov     [rdx], rcx
0x180023d89  jmp     loc_180023ED4
0x180023d8e  mov     esi, [rcx+0B8h]
0x180023d94  mov     eax, 0FFFFFFFFh
0x180023d99  shl     rsi, 4
0x180023d9d  cmp     rsi, rax
0x180023da0  ja      loc_180023EB9
0x180023da6  lea     eax, [rsi+0C0h]
0x180023dac  cmp     eax, esi
0x180023dae  jb      loc_180023EB1
0x180023db4  mov     ebx, eax
0x180023db6  call    cs:__imp_GetProcessHeap
0x180023dbd  nop     dword ptr [rax+rax+00h]
0x180023dc2  mov     r8d, ebx; dwBytes
0x180023dc5  xor     edx, edx; dwFlags
0x180023dc7  mov     rcx, rax; hHeap
0x180023dca  call    cs:__imp_HeapAlloc
0x180023dd1  nop     dword ptr [rax+rax+00h]
0x180023dd6  mov     rbx, rax
0x180023dd9  test    rax, rax
0x180023ddc  jnz     short loc_180023DF8
0x180023dde  mov     edi, 8007000Eh
0x180023de3  lea     rcx, aMovecapturenod; "MoveCaptureNode"
0x180023dea  mov     r9d, edi
0x180023ded  mov     r8d, 0B6h
0x180023df3  call    UtilReportError
0x180023df8  test    edi, edi
0x180023dfa  js      loc_180023ED4
0x180023e00  movups  xmm0, xmmword ptr [rbp+0]
0x180023e04  mov     edx, 80h
0x180023e09  mov     r8d, esi; Size
0x180023e0c  movups  xmmword ptr [rbx], xmm0
0x180023e0f  movups  xmm1, xmmword ptr [rbp+10h]
0x180023e13  lea     rcx, [rdx+rbx]
0x180023e17  lea     rax, [rdx+rbp]
0x180023e1b  movups  xmmword ptr [rbx+10h], xmm1
0x180023e1f  movups  xmm0, xmmword ptr [rbp+20h]
0x180023e23  movups  xmmword ptr [rbx+20h], xmm0
0x180023e27  movups  xmm1, xmmword ptr [rbp+30h]
0x180023e2b  movups  xmmword ptr [rbx+30h], xmm1
0x180023e2f  movups  xmm0, xmmword ptr [rbp+40h]
0x180023e33  movups  xmmword ptr [rbx+40h], xmm0
0x180023e37  movups  xmm1, xmmword ptr [rbp+50h]
0x180023e3b  movups  xmmword ptr [rbx+50h], xmm1
0x180023e3f  movups  xmm0, xmmword ptr [rbp+60h]
0x180023e43  movups  xmmword ptr [rbx+60h], xmm0
0x180023e47  movups  xmm0, xmmword ptr [rbp+70h]
0x180023e4b  movups  xmmword ptr [rcx-10h], xmm0
0x180023e4f  movups  xmm1, xmmword ptr [rax]
0x180023e52  movups  xmmword ptr [rcx], xmm1
0x180023e55  movups  xmm0, xmmword ptr [rax+10h]
0x180023e59  movups  xmmword ptr [rcx+10h], xmm0
0x180023e5d  movups  xmm1, xmmword ptr [rax+20h]
0x180023e61  movups  xmmword ptr [rcx+20h], xmm1
0x180023e65  movups  xmm0, xmmword ptr [rax+30h]
0x180023e69  movups  xmmword ptr [rcx+30h], xmm0
0x180023e6d  lea     rcx, [rbx+0C0h]; void *
0x180023e74  mov     dword ptr [rbx+18h], 1
0x180023e7b  mov     [rbx+0B0h], rcx
0x180023e82  mov     rdx, [rbp+0B0h]; Src
0x180023e89  call    memcpy_0
0x180023e8e  and     qword ptr [rbp+40h], 0
0x180023e93  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023e97  and     qword ptr [rbp+38h], 0
0x180023e9c  and     qword ptr [rbp+90h], 0
0x180023ea4  mov     [rbp+30h], rax
0x180023ea8  mov     [rbp+28h], rax
0x180023eac  mov     [r14], rbx
0x180023eaf  jmp     short loc_180023ED4
0x180023eb1  mov     r8d, 0ACh
0x180023eb7  jmp     short loc_180023EBF
0x180023eb9  mov     r8d, 0A9h
0x180023ebf  mov     r9d, 80070216h
0x180023ec5  lea     rcx, aMovecapturenod; "MoveCaptureNode"
0x180023ecc  mov     edi, r9d
0x180023ecf  call    UtilReportError
0x180023ed4  mov     rbx, [rsp+28h+arg_0]
0x180023ed9  mov     eax, edi
0x180023edb  mov     rdi, [rsp+28h+arg_18]
0x180023ee0  mov     rbp, [rsp+28h+arg_8]
0x180023ee5  mov     rsi, [rsp+28h+arg_10]
0x180023eea  add     rsp, 20h
0x180023eee  pop     r14
0x180023ef0  retn
```
