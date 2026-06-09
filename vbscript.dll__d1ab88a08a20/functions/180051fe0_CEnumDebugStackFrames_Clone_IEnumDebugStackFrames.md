# CEnumDebugStackFrames::Clone(IEnumDebugStackFrames * *)

- ea: `0x180051fe0`
- end: `0x18005209b`
- name: `?Clone@CEnumDebugStackFrames@@UEAAJPEAPEAUIEnumDebugStackFrames@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, struct IEnumDebugStackFrames **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180046884`
- `0x180051bf0`
- `0x180051fe0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005200e`
- `KERNEL32!GetCurrentThreadId` at `0x18005200e`

## pseudocode

```c
__int64 __fastcall CEnumDebugStackFrames::Clone(CEnumDebugStackFrames *this, struct IEnumDebugStackFrames **a2)
{
  int v5; // ebx
  CEnumDebugStackFrames *v6; // rax
  CEnumDebugStackFrames *v7; // rax
  struct IEnumDebugStackFrames *v8; // rdx
  unsigned int v9; // ecx
  __int64 v10; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v5 )
    return 2147549183LL;
  v6 = (CEnumDebugStackFrames *)operator new(0x30u);
  if ( !v6 )
    return 2147942414LL;
  v7 = CEnumDebugStackFrames::CEnumDebugStackFrames(v6, *((_QWORD *)this + 2), *((struct CSession **)this + 5));
  v8 = (struct IEnumDebugStackFrames *)v7;
  if ( !v7 )
    return 2147942414LL;
  v9 = *((_DWORD *)this + 7) ^ (*((_DWORD *)v7 + 7) ^ *((_DWORD *)this + 7)) & 0xFFFFFFFE;
  *((_DWORD *)v7 + 7) = v9;
  *((_DWORD *)v7 + 7) = *((_DWORD *)this + 7) ^ (*((_DWORD *)this + 7) ^ v9) & 0xFFFFFFFD;
  *((_DWORD *)v7 + 6) = *((_DWORD *)this + 6);
  v10 = *((_QWORD *)this + 4);
  v8[4].lpVtbl = (struct IEnumDebugStackFramesVtbl *)v10;
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 40));
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x180051fe0  mov     [rsp+arg_0], rbx
0x180051fe5  mov     [rsp+arg_8], rsi
0x180051fea  push    rdi
0x180051feb  sub     rsp, 20h
0x180051fef  mov     rsi, rdx
0x180051ff2  mov     rdi, rcx
0x180051ff5  test    rdx, rdx
0x180051ff8  jnz     short loc_180052004
0x180051ffa  mov     eax, 80004003h
0x180051fff  jmp     loc_18005208A
0x180052004  mov     qword ptr [rdx], 0
0x18005200b  mov     ebx, [rcx+0Ch]
0x18005200e  call    cs:__imp_GetCurrentThreadId
0x180052015  nop     dword ptr [rax+rax+00h]
0x18005201a  cmp     eax, ebx
0x18005201c  jz      short loc_180052025
0x18005201e  mov     eax, 8000FFFFh
0x180052023  jmp     short loc_18005208A
0x180052025  mov     ecx, 30h ; '0'; Size
0x18005202a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005202f  test    rax, rax
0x180052032  jz      short loc_180052085
0x180052034  mov     r8, [rdi+28h]; struct CSession *
0x180052038  mov     rcx, rax; this
0x18005203b  mov     rdx, [rdi+10h]; unsigned __int64
0x18005203f  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x180052044  mov     rdx, rax
0x180052047  test    rax, rax
0x18005204a  jz      short loc_180052085
0x18005204c  mov     ecx, [rdi+1Ch]
0x18005204f  xor     ecx, [rax+1Ch]
0x180052052  and     ecx, 0FFFFFFFEh
0x180052055  xor     ecx, [rdi+1Ch]
0x180052058  mov     [rax+1Ch], ecx
0x18005205b  xor     ecx, [rdi+1Ch]
0x18005205e  and     ecx, 0FFFFFFFDh
0x180052061  xor     ecx, [rdi+1Ch]
0x180052064  mov     [rax+1Ch], ecx
0x180052067  mov     eax, [rdi+18h]
0x18005206a  mov     [rdx+18h], eax
0x18005206d  mov     rax, [rdi+20h]
0x180052071  mov     [rdx+20h], rax
0x180052075  test    rax, rax
0x180052078  jz      short loc_18005207E
0x18005207a  lock inc dword ptr [rax+28h]
0x18005207e  mov     [rsi], rdx
0x180052081  xor     eax, eax
0x180052083  jmp     short loc_18005208A
0x180052085  mov     eax, 8007000Eh
0x18005208a  mov     rbx, [rsp+28h+arg_0]
0x18005208f  mov     rsi, [rsp+28h+arg_8]
0x180052094  add     rsp, 20h
0x180052098  pop     rdi
0x180052099  retn
```
