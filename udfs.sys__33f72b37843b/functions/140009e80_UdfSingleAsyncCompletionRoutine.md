# UdfSingleAsyncCompletionRoutine

- ea: `0x140009e80`
- end: `0x140009f5a`
- name: `UdfSingleAsyncCompletionRoutine`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140009e80`
- `0x14000a2e8`
- `0x140012034`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009f42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009f42`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140009eda`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140009f31`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140009eda`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140009f31`

## pseudocode

```c
__int64 __fastcall UdfSingleAsyncCompletionRoutine(__int64 a1, __int64 a2, __int64 a3)
{
  ERESOURCE_THREAD *v4; // rbx
  __int64 v5; // rdx
  __int64 v7; // r9
  ERESOURCE_THREAD *v8; // rsi
  struct _ERESOURCE *v9; // rcx
  struct _ERESOURCE *v10; // rcx

  v4 = (ERESOURCE_THREAD *)(a3 + 48);
  v5 = *(_QWORD *)(a3 + 24);
  if ( (*(_DWORD *)(v5 + 48) & 0x200000) != 0 )
    UdfReleaseDevice(a1, v5, *v4);
  v7 = *(unsigned int *)(a2 + 48);
  *(_QWORD *)(a2 + 56) = 0;
  if ( (int)v7 >= 0 )
  {
    *(_QWORD *)(a2 + 56) = *(unsigned int *)(a3 + 56);
LABEL_5:
    v8 = v4;
    goto LABEL_6;
  }
  if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) == 0 )
  {
    goto LABEL_5;
  }
  WPP_SF_Dq(
    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
    27,
    WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids,
    v7,
    a2);
  v8 = (ERESOURCE_THREAD *)(a3 + 48);
LABEL_6:
  *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  v9 = *(struct _ERESOURCE **)(a3 + 32);
  if ( v9 )
    ExReleaseResourceForThreadLite(v9, *v4);
  else
    v8 = v4;
  v10 = *(struct _ERESOURCE **)(a3 + 40);
  if ( v10 )
    ExReleaseResourceForThreadLite(v10, *v8);
  ExFreePoolWithTag((PVOID)a3, 0);
  return 0;
}

```

## disassembly

```asm
0x140009e80  push    rbx
0x140009e82  push    rbp
0x140009e83  push    rsi
0x140009e84  push    rdi
0x140009e85  sub     rsp, 38h
0x140009e89  mov     rbp, rdx
0x140009e8c  lea     rbx, [r8+30h]
0x140009e90  mov     rdx, [r8+18h]
0x140009e94  mov     rdi, r8
0x140009e97  test    dword ptr [rdx+30h], 200000h
0x140009e9e  jz      short loc_140009EA8
0x140009ea0  mov     r8, [rbx]
0x140009ea3  call    UdfReleaseDevice
0x140009ea8  mov     r9d, [rbp+30h]
0x140009eac  mov     qword ptr [rbp+38h], 0
0x140009eb4  test    r9d, r9d
0x140009eb7  js      short loc_140009EE8
0x140009eb9  mov     eax, [rdi+38h]
0x140009ebc  mov     [rbp+38h], rax
0x140009ec0  mov     rsi, rbx
0x140009ec3  mov     rax, [rbp+0B8h]
0x140009eca  or      byte ptr [rax+3], 1
0x140009ece  mov     rcx, [rdi+20h]; Resource
0x140009ed2  test    rcx, rcx
0x140009ed5  jz      short loc_140009F22
0x140009ed7  mov     rdx, [rbx]; ResourceThreadId
0x140009eda  call    cs:__imp_ExReleaseResourceForThreadLite
0x140009ee1  nop     dword ptr [rax+rax+00h]
0x140009ee6  jmp     short loc_140009F25
0x140009ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x140009eef  lea     rax, WPP_GLOBAL_Control
0x140009ef6  cmp     rcx, rax
0x140009ef9  jz      short loc_140009EC0
0x140009efb  mov     eax, [rcx+2Ch]
0x140009efe  test    al, 40h
0x140009f00  jz      short loc_140009EC0
0x140009f02  mov     rcx, [rcx+18h]
0x140009f06  lea     r8, WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids
0x140009f0d  mov     edx, 1Bh
0x140009f12  mov     [rsp+58h+var_38], rbp
0x140009f17  call    WPP_SF_Dq
0x140009f1c  lea     rsi, [rdi+30h]
0x140009f20  jmp     short loc_140009EC3
0x140009f22  mov     rsi, rbx
0x140009f25  mov     rcx, [rdi+28h]; Resource
0x140009f29  test    rcx, rcx
0x140009f2c  jz      short loc_140009F3D
0x140009f2e  mov     rdx, [rsi]; ResourceThreadId
0x140009f31  call    cs:__imp_ExReleaseResourceForThreadLite
0x140009f38  nop     dword ptr [rax+rax+00h]
0x140009f3d  xor     edx, edx; Tag
0x140009f3f  mov     rcx, rdi; P
0x140009f42  call    cs:__imp_ExFreePoolWithTag
0x140009f49  nop     dword ptr [rax+rax+00h]
0x140009f4e  xor     eax, eax
0x140009f50  add     rsp, 38h
0x140009f54  pop     rdi
0x140009f55  pop     rsi
0x140009f56  pop     rbp
0x140009f57  pop     rbx
0x140009f58  retn
```
