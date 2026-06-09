# PfEvtWdmQueryIdsCompletion

- ea: `0x140009c90`
- end: `0x140009e6f`
- name: `PfEvtWdmQueryIdsCompletion`
- size: `479`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140006060`
- `0x140009c90`
- `0x14000a2e8`
- `0x14000aa30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009e30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e4b`
- `ntoskrnl!ExAllocatePool2` at `0x140009d31`
- `ntoskrnl!ExAllocatePool2` at `0x140009de9`
- `ntoskrnl!ExAllocatePool2` at `0x140009d31`
- `ntoskrnl!ExAllocatePool2` at `0x140009de9`

## pseudocode

```c
__int64 __fastcall PfEvtWdmQueryIdsCompletion(__int64 a1, __int64 a2, int a3)
{
  __int64 v5; // rax
  _QWORD *v6; // rbx
  __int64 v7; // rax
  void *v8; // rdi
  const wchar_t *v9; // rbp
  size_t v10; // r14
  wchar_t *Pool2; // rax
  unsigned int v12; // ebp
  void *v13; // rcx
  size_t pcchLength; // [rsp+58h] [rbp+10h] BYREF

  v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[15].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a1);
  ((void (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    v5,
    off_14000F090);
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  if ( !a3 || a3 == 3 )
  {
    v6 = (_QWORD *)(a2 + 48);
    if ( *(int *)(a2 + 48) < 0 )
      return *(unsigned int *)v6;
    v9 = *(const wchar_t **)(a2 + 56);
    if ( !v9 )
      return *(unsigned int *)v6;
    pcchLength = 0;
    if ( RtlStringLengthWorkerW(v9, 0x7FFFu, &pcchLength) < 0 )
      return *(unsigned int *)v6;
    v10 = 2 * pcchLength + 8;
    Pool2 = (wchar_t *)ExAllocatePool2(256, v10, 1179997012);
    v8 = Pool2;
    if ( !Pool2 )
      return *(unsigned int *)v6;
    if ( RtlStringCbPrintfW(Pool2, v10, L"%ws%ws", L"TS_", v9) < 0 )
    {
      ExFreePoolWithTag(v8, 0);
      return *(unsigned int *)v6;
    }
  }
  else
  {
    if ( (unsigned int)(a3 - 1) > 1 )
    {
      v6 = (_QWORD *)(a2 + 48);
      return *(unsigned int *)v6;
    }
    v7 = ExAllocatePool2(256, 84, 1179997012);
    v6 = (_QWORD *)(a2 + 48);
    v8 = (void *)v7;
    if ( !v7 )
      return *(unsigned int *)v6;
    *(_OWORD *)v7 = *(_OWORD *)L"USB\\d8f87d9c-4ee4-4a61-92d1-3caa420a227b";
    *(_OWORD *)(v7 + 16) = *(_OWORD *)L"7d9c-4ee4-4a61-92d1-3caa420a227b";
    *(_OWORD *)(v7 + 32) = *(_OWORD *)L"4-4a61-92d1-3caa420a227b";
    *(_OWORD *)(v7 + 48) = *(_OWORD *)L"2d1-3caa420a227b";
    *(_OWORD *)(v7 + 64) = *(_OWORD *)L"420a227b";
    *(_DWORD *)(v7 + 80) = *(_DWORD *)L"";
  }
  v12 = *(_DWORD *)v6;
  if ( *(int *)v6 < 0 )
  {
    *(_DWORD *)v6 = v12;
  }
  else
  {
    v13 = (void *)v6[1];
    if ( v13 )
      ExFreePoolWithTag(v13, 0);
  }
  *(_QWORD *)(a2 + 56) = v8;
  return v12;
}

```

## disassembly

```asm
0x140009c90  mov     [rsp+arg_0], rbx
0x140009c95  mov     [rsp+arg_10], rbp
0x140009c9a  push    rsi
0x140009c9b  push    rdi
0x140009c9c  push    r14
0x140009c9e  sub     rsp, 30h
0x140009ca2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140009ca9  mov     rsi, rdx
0x140009cac  mov     rdx, rcx
0x140009caf  mov     rbx, r8
0x140009cb2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140009cb9  mov     rax, [rax+0F0h]
0x140009cc0  call    _guard_dispatch_icall
0x140009cc5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140009ccc  mov     rdx, rax
0x140009ccf  mov     r8, cs:off_14000F090
0x140009cd6  mov     r9, [rcx+650h]
0x140009cdd  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140009ce4  mov     rax, r9
0x140009ce7  call    _guard_dispatch_icall
0x140009cec  cmp     byte ptr [rsi+41h], 0
0x140009cf0  jz      short loc_140009CFD
0x140009cf2  mov     rax, [rsi+0B8h]
0x140009cf9  or      byte ptr [rax+3], 1
0x140009cfd  test    ebx, ebx
0x140009cff  jz      loc_140009D91
0x140009d05  cmp     ebx, 3
0x140009d08  jz      loc_140009D91
0x140009d0e  lea     eax, [rbx-1]
0x140009d11  cmp     eax, 1
0x140009d14  jbe     short loc_140009D21
0x140009d16  lea     rbx, [rsi+30h]
0x140009d1a  mov     eax, [rbx]
0x140009d1c  jmp     loc_140009E57
0x140009d21  mov     edx, 54h ; 'T'
0x140009d26  mov     ecx, 100h
0x140009d2b  mov     r8d, 46555354h
0x140009d31  call    cs:__imp_ExAllocatePool2
0x140009d38  nop     dword ptr [rax+rax+00h]
0x140009d3d  lea     rbx, [rsi+30h]
0x140009d41  mov     rdi, rax
0x140009d44  test    rax, rax
0x140009d47  jz      loc_140009E57
0x140009d4d  movaps  xmm0, xmmword ptr cs:aUsbD8f87d9c4ee; "USB\\d8f87d9c-4ee4-4a61-92d1-3caa420a22"...
0x140009d54  movaps  xmm1, xmmword ptr cs:aUsbD8f87d9c4ee+10h; "7d9c-4ee4-4a61-92d1-3caa420a227b"
0x140009d5b  movups  xmmword ptr [rax], xmm0
0x140009d5e  movaps  xmm0, xmmword ptr cs:aUsbD8f87d9c4ee+20h; "4-4a61-92d1-3caa420a227b"
0x140009d65  movups  xmmword ptr [rax+10h], xmm1
0x140009d69  movaps  xmm1, xmmword ptr cs:aUsbD8f87d9c4ee+30h; "2d1-3caa420a227b"
0x140009d70  movups  xmmword ptr [rax+20h], xmm0
0x140009d74  movaps  xmm0, xmmword ptr cs:aUsbD8f87d9c4ee+40h; "420a227b"
0x140009d7b  movups  xmmword ptr [rax+30h], xmm1
0x140009d7f  movups  xmmword ptr [rax+40h], xmm0
0x140009d83  mov     eax, dword ptr cs:aUsbD8f87d9c4ee+50h; ""
0x140009d89  mov     [rdi+50h], eax
0x140009d8c  jmp     loc_140009E1F
0x140009d91  lea     rbx, [rsi+30h]
0x140009d95  cmp     dword ptr [rbx], 0
0x140009d98  jl      loc_140009E57
0x140009d9e  mov     rbp, [rsi+38h]
0x140009da2  test    rbp, rbp
0x140009da5  jz      loc_140009E57
0x140009dab  lea     r8, [rsp+48h+pcchLength]; pcchLength
0x140009db0  mov     [rsp+48h+pcchLength], 0
0x140009db9  mov     edx, 7FFFh; cchMax
0x140009dbe  mov     rcx, rbp; psz
0x140009dc1  call    RtlStringLengthWorkerW
0x140009dc6  test    eax, eax
0x140009dc8  js      loc_140009E57
0x140009dce  mov     rax, [rsp+48h+pcchLength]
0x140009dd3  mov     r8d, 46555354h
0x140009dd9  mov     ecx, 100h
0x140009dde  lea     r14, ds:8[rax*2]
0x140009de6  mov     rdx, r14
0x140009de9  call    cs:__imp_ExAllocatePool2
0x140009df0  nop     dword ptr [rax+rax+00h]
0x140009df5  mov     rdi, rax
0x140009df8  test    rax, rax
0x140009dfb  jz      short loc_140009E57
0x140009dfd  lea     r9, aTs; "TS_"
0x140009e04  mov     [rsp+48h+var_28], rbp
0x140009e09  lea     r8, aWsWs; "%ws%ws"
0x140009e10  mov     rdx, r14; cbDest
0x140009e13  mov     rcx, rax; pszDest
0x140009e16  call    RtlStringCbPrintfW
0x140009e1b  test    eax, eax
0x140009e1d  js      short loc_140009E46
0x140009e1f  mov     ebp, [rbx]
0x140009e21  test    ebp, ebp
0x140009e23  js      short loc_140009E3E
0x140009e25  mov     rcx, [rbx+8]; P
0x140009e29  test    rcx, rcx
0x140009e2c  jz      short loc_140009E40
0x140009e2e  xor     edx, edx; Tag
0x140009e30  call    cs:__imp_ExFreePoolWithTag
0x140009e37  nop     dword ptr [rax+rax+00h]
0x140009e3c  jmp     short loc_140009E40
0x140009e3e  mov     [rbx], ebp
0x140009e40  mov     [rsi+38h], rdi
0x140009e44  jmp     short loc_140009E59
0x140009e46  xor     edx, edx; Tag
0x140009e48  mov     rcx, rdi; P
0x140009e4b  call    cs:__imp_ExFreePoolWithTag
0x140009e52  nop     dword ptr [rax+rax+00h]
0x140009e57  mov     ebp, [rbx]
0x140009e59  mov     rbx, [rsp+48h+arg_0]
0x140009e5e  mov     eax, ebp
0x140009e60  mov     rbp, [rsp+48h+arg_10]
0x140009e65  add     rsp, 30h
0x140009e69  pop     r14
0x140009e6b  pop     rdi
0x140009e6c  pop     rsi
0x140009e6d  retn
```
