# NfsMemMgrpStructureAllocateInternal

- ea: `0x140012e58`
- end: `0x14001303c`
- name: `NfsMemMgrpStructureAllocateInternal`
- size: `484`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400128ac`
- `0x140012950`

## callees

- `0x140012684`
- `0x140012bbc`
- `0x140012e58`
- `0x1400150f0`
- `0x1400151b0`
- `0x140015680`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140012fe9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012fe9`
- `ntoskrnl!ExAllocatePool2` at `0x140012f13`
- `ntoskrnl!ExAllocatePool2` at `0x140012f13`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140012ed8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140012ed8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012fd3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012fd3`

## pseudocode

```c
__int64 __fastcall NfsMemMgrpStructureAllocateInternal(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rdi
  int Internal; // esi
  int v7; // eax
  unsigned int v8; // ebp
  _QWORD *Pool2; // rax
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 (__fastcall *v12)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD *); // rax
  void (__fastcall *v13)(_QWORD, _QWORD, _QWORD); // rax
  __int64 result; // rax
  __int64 v15; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  if ( (*(_DWORD *)(a1 + 48) & 2) == 0 )
  {
    Internal = -1073741811;
    goto LABEL_25;
  }
  Internal = NfsPolMgrpResourceAllocateInternal();
  if ( Internal < 0 )
    goto LABEL_25;
  if ( (*(_DWORD *)(a1 + 152) & 0x100) != 0 )
    v7 = *(_DWORD *)(a1 + 232);
  else
    v7 = 1;
  v8 = v7 * *(unsigned __int16 *)(a1 + 156);
  if ( v8 > 0xFFFF )
  {
    Internal = -1073741789;
LABEL_24:
    NfsPolMgrpResourceDeallocateInternal(a1);
    goto LABEL_25;
  }
  if ( (*(_DWORD *)(a1 + 384) & 1) != 0 )
  {
    Pool2 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 288));
  }
  else
  {
    v10 = *(unsigned int *)(a1 + 160);
    v15 = 0;
    if ( (int)NfsMemMgrpMapPoolTypeWithPoolFlag(v10, &v15) < 0 )
      goto LABEL_22;
    Pool2 = (_QWORD *)ExAllocatePool2(v15 | 2, (unsigned __int16)v8, *(unsigned int *)(a1 + 40));
  }
  v3 = Pool2;
  if ( !Pool2 )
  {
LABEL_22:
    v13 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 208);
    Internal = -1073741670;
    if ( v13 )
      v13(*(_QWORD *)(a1 + 168), *(unsigned int *)(a1 + 40), (unsigned __int16)v8);
    goto LABEL_24;
  }
  Internal = 0;
  NfsMemMgrAllocationPoison(*(unsigned int *)(a1 + 40), Pool2, v8, *(unsigned int *)(a1 + 216), *(_DWORD *)(a1 + 224));
  if ( (*(_DWORD *)(a1 + 152) & 1) == 0 )
  {
    v11 = *(_DWORD *)(a1 + 40);
    v3[2] = 0;
    *v3 = v11;
    *((_WORD *)v3 + 4) = v8;
  }
  v12 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD *))(a1 + 176);
  if ( v12 )
  {
    Internal = v12(*(_QWORD *)(a1 + 168), *(unsigned int *)(a1 + 40), (unsigned __int16)v8, 0, 0, v3);
    if ( Internal < 0 )
    {
      NfsMemMgrAllocationPoison(*(unsigned int *)(a1 + 40), v3, v8, *(unsigned int *)(a1 + 220), *(_DWORD *)(a1 + 228));
      if ( (*(_DWORD *)(a1 + 384) & 1) != 0 )
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 288), v3);
      else
        ExFreePoolWithTag(v3, *(_DWORD *)(a1 + 40));
      v3 = 0;
      goto LABEL_24;
    }
  }
LABEL_25:
  result = (unsigned int)Internal;
  *a3 = v3;
  return result;
}

```

## disassembly

```asm
0x140012e58  mov     [rsp+arg_8], rbx
0x140012e5d  mov     [rsp+arg_10], rbp
0x140012e62  push    rsi
0x140012e63  push    rdi
0x140012e64  push    r14
0x140012e66  sub     rsp, 40h
0x140012e6a  mov     eax, [rcx+30h]
0x140012e6d  xor     edi, edi
0x140012e6f  mov     r14, r8
0x140012e72  mov     rbx, rcx
0x140012e75  test    al, 2
0x140012e77  jnz     short loc_140012E83
0x140012e79  mov     esi, 0C000000Dh
0x140012e7e  jmp     loc_140013023
0x140012e83  call    NfsPolMgrpResourceAllocateInternal
0x140012e88  mov     esi, eax
0x140012e8a  test    eax, eax
0x140012e8c  js      loc_140013023
0x140012e92  test    dword ptr [rbx+98h], 100h
0x140012e9c  movzx   ebp, word ptr [rbx+9Ch]
0x140012ea3  jz      short loc_140012EAD
0x140012ea5  mov     eax, [rbx+0E8h]
0x140012eab  jmp     short loc_140012EB2
0x140012ead  mov     eax, 1
0x140012eb2  imul    ebp, eax
0x140012eb5  cmp     ebp, 0FFFFh
0x140012ebb  jbe     short loc_140012EC7
0x140012ebd  mov     esi, 0C0000023h
0x140012ec2  jmp     loc_14001301B
0x140012ec7  mov     eax, [rbx+180h]
0x140012ecd  test    al, 1
0x140012ecf  jz      short loc_140012EE6
0x140012ed1  lea     rcx, [rbx+120h]; Lookaside
0x140012ed8  call    cs:__imp_ExAllocateFromLookasideListEx
0x140012edf  nop     dword ptr [rax+rax+00h]
0x140012ee4  jmp     short loc_140012F1F
0x140012ee6  mov     ecx, [rbx+0A0h]
0x140012eec  lea     rdx, [rsp+58h+arg_0]
0x140012ef1  mov     [rsp+58h+arg_0], rdi
0x140012ef6  call    NfsMemMgrpMapPoolTypeWithPoolFlag
0x140012efb  test    eax, eax
0x140012efd  js      loc_140012FF7
0x140012f03  mov     rcx, [rsp+58h+arg_0]
0x140012f08  mov     r8d, [rbx+28h]
0x140012f0c  or      rcx, 2
0x140012f10  movzx   edx, bp
0x140012f13  call    cs:__imp_ExAllocatePool2
0x140012f1a  nop     dword ptr [rax+rax+00h]
0x140012f1f  mov     rdi, rax
0x140012f22  test    rax, rax
0x140012f25  jz      loc_140012FF7
0x140012f2b  mov     eax, [rbx+0E0h]
0x140012f31  mov     r8d, ebp
0x140012f34  mov     r9d, [rbx+0D8h]
0x140012f3b  mov     rdx, rdi
0x140012f3e  mov     ecx, [rbx+28h]
0x140012f41  xor     esi, esi
0x140012f43  mov     dword ptr [rsp+58h+var_38], eax
0x140012f47  call    NfsMemMgrAllocationPoison
0x140012f4c  mov     eax, [rbx+98h]
0x140012f52  test    al, 1
0x140012f54  jnz     short loc_140012F66
0x140012f56  mov     eax, [rbx+28h]
0x140012f59  mov     [rdi+10h], rsi
0x140012f5d  mov     [rdi], eax
0x140012f5f  mov     [rdi+4], esi
0x140012f62  mov     [rdi+8], bp
0x140012f66  mov     rax, [rbx+0B0h]
0x140012f6d  test    rax, rax
0x140012f70  jz      loc_140013023
0x140012f76  mov     edx, [rbx+28h]
0x140012f79  xor     r9d, r9d
0x140012f7c  mov     rcx, [rbx+0A8h]
0x140012f83  movzx   r8d, bp
0x140012f87  mov     [rsp+58h+var_30], rdi
0x140012f8c  mov     [rsp+58h+var_38], rsi
0x140012f91  call    _guard_dispatch_icall
0x140012f96  mov     esi, eax
0x140012f98  test    eax, eax
0x140012f9a  jns     loc_140013023
0x140012fa0  mov     eax, [rbx+0E4h]
0x140012fa6  mov     r8d, ebp
0x140012fa9  mov     r9d, [rbx+0DCh]
0x140012fb0  mov     rdx, rdi
0x140012fb3  mov     ecx, [rbx+28h]
0x140012fb6  mov     dword ptr [rsp+58h+var_38], eax
0x140012fba  call    NfsMemMgrAllocationPoison
0x140012fbf  mov     eax, [rbx+180h]
0x140012fc5  test    al, 1
0x140012fc7  jz      short loc_140012FE3
0x140012fc9  lea     rcx, [rbx+120h]; Lookaside
0x140012fd0  mov     rdx, rdi; Entry
0x140012fd3  call    cs:__imp_ExFreeToLookasideListEx
0x140012fda  nop     dword ptr [rax+rax+00h]
0x140012fdf  xor     edi, edi
0x140012fe1  jmp     short loc_14001301B
0x140012fe3  mov     edx, [rbx+28h]; Tag
0x140012fe6  mov     rcx, rdi; P
0x140012fe9  call    cs:__imp_ExFreePoolWithTag
0x140012ff0  nop     dword ptr [rax+rax+00h]
0x140012ff5  jmp     short loc_140012FDF
0x140012ff7  mov     rax, [rbx+0D0h]
0x140012ffe  mov     esi, 0C000009Ah
0x140013003  test    rax, rax
0x140013006  jz      short loc_14001301B
0x140013008  mov     edx, [rbx+28h]
0x14001300b  movzx   r8d, bp
0x14001300f  mov     rcx, [rbx+0A8h]
0x140013016  call    _guard_dispatch_icall
0x14001301b  mov     rcx, rbx
0x14001301e  call    NfsPolMgrpResourceDeallocateInternal
0x140013023  mov     rbx, [rsp+58h+arg_8]
0x140013028  mov     eax, esi
0x14001302a  mov     rbp, [rsp+58h+arg_10]
0x14001302f  mov     [r14], rdi
0x140013032  add     rsp, 40h
0x140013036  pop     r14
0x140013038  pop     rdi
0x140013039  pop     rsi
0x14001303a  retn
```
