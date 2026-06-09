# CEnumDebugStackFrames::Clone(IEnumDebugStackFrames * *)

- ea: `0x180050800`
- end: `0x1800508b4`
- name: `?Clone@CEnumDebugStackFrames@@UEAAJPEAPEAUIEnumDebugStackFrames@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, struct IEnumDebugStackFrames **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180045490`
- `0x18005042c`
- `0x180050800`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005082e`
- `KERNEL32!GetCurrentThreadId` at `0x18005082e`

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
0x180050800  mov     [rsp+arg_0], rbx
0x180050805  mov     [rsp+arg_8], rsi
0x18005080a  push    rdi
0x18005080b  sub     rsp, 20h
0x18005080f  mov     rsi, rdx
0x180050812  mov     rdi, rcx
0x180050815  test    rdx, rdx
0x180050818  jnz     short loc_180050824
0x18005081a  mov     eax, 80004003h
0x18005081f  jmp     loc_1800508A4
0x180050824  mov     qword ptr [rdx], 0
0x18005082b  mov     ebx, [rcx+0Ch]
0x18005082e  call    cs:__imp_GetCurrentThreadId
0x180050834  cmp     eax, ebx
0x180050836  jz      short loc_18005083F
0x180050838  mov     eax, 8000FFFFh
0x18005083d  jmp     short loc_1800508A4
0x18005083f  mov     ecx, 30h ; '0'; Size
0x180050844  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050849  test    rax, rax
0x18005084c  jz      short loc_18005089F
0x18005084e  mov     r8, [rdi+28h]; struct CSession *
0x180050852  mov     rcx, rax; this
0x180050855  mov     rdx, [rdi+10h]; unsigned __int64
0x180050859  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x18005085e  mov     rdx, rax
0x180050861  test    rax, rax
0x180050864  jz      short loc_18005089F
0x180050866  mov     ecx, [rdi+1Ch]
0x180050869  xor     ecx, [rax+1Ch]
0x18005086c  and     ecx, 0FFFFFFFEh
0x18005086f  xor     ecx, [rdi+1Ch]
0x180050872  mov     [rax+1Ch], ecx
0x180050875  xor     ecx, [rdi+1Ch]
0x180050878  and     ecx, 0FFFFFFFDh
0x18005087b  xor     ecx, [rdi+1Ch]
0x18005087e  mov     [rax+1Ch], ecx
0x180050881  mov     eax, [rdi+18h]
0x180050884  mov     [rdx+18h], eax
0x180050887  mov     rax, [rdi+20h]
0x18005088b  mov     [rdx+20h], rax
0x18005088f  test    rax, rax
0x180050892  jz      short loc_180050898
0x180050894  lock inc dword ptr [rax+28h]
0x180050898  mov     [rsi], rdx
0x18005089b  xor     eax, eax
0x18005089d  jmp     short loc_1800508A4
0x18005089f  mov     eax, 8007000Eh
0x1800508a4  mov     rbx, [rsp+28h+arg_0]
0x1800508a9  mov     rsi, [rsp+28h+arg_8]
0x1800508ae  add     rsp, 20h
0x1800508b2  pop     rdi
0x1800508b3  retn
```
