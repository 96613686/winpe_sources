# TpmDevice::CreateContext(void * *)

- ea: `0x140007a94`
- end: `0x140007b55`
- name: `?CreateContext@TpmDevice@@QEAAJPEAPEAX@Z`
- size: `193`
- prototype: `__int64 __fastcall(TpmDevice *__hidden this, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140008a5c`
- `0x140013bf0`
- `0x140021a60`

## callees

- `0x140007a94`
- `0x140019c2c`
- `0x1400454cc`
- `0x1400454f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140007ad3`
- `ntoskrnl!ExAllocatePool2` at `0x140007ad3`

## pseudocode

```c
__int64 __fastcall TpmDevice::CreateContext(TpmDevice *this, TpmContext **a2)
{
  GuardedMutex *v2; // rsi
  int v5; // edi
  _QWORD *Pool2; // rax
  TpmContext *v7; // rcx
  TpmContext *v9; // rax
  TpmContext *v10; // r8
  TpmDevice **v11; // rdx
  TpmDevice *v12; // rax
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h]

  v2 = (TpmDevice *)((char *)this + 1176);
  GuardedMutex::Acquire((TpmDevice *)((char *)this + 1176));
  v5 = *((_DWORD *)this + 242);
  if ( v5 >= 0 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(257, 72, 1349349460);
    v7 = (TpmContext *)Pool2;
    if ( Pool2 )
    {
      *Pool2 = retaddr;
      Pool2[1] = retaddr;
      v7 = (TpmContext *)(Pool2 + 2);
    }
    if ( v7 && (v9 = TpmContext::TpmContext(v7), (v10 = v9) != 0) )
    {
      v11 = (TpmDevice **)*((_QWORD *)this + 149);
      if ( *v11 != (TpmDevice *)((char *)this + 1184) )
        __fastfail(3u);
      v12 = (TpmContext *)((char *)v9 + 16);
      *a2 = v10;
      *((_QWORD *)v12 + 1) = v11;
      *(_QWORD *)v12 = (char *)this + 1184;
      *v11 = v12;
      *((_QWORD *)this + 149) = v12;
      ++*((_DWORD *)this + 3);
    }
    else
    {
      v5 = -1073741670;
    }
  }
  GuardedMutex::Release(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140007a94  push    rbx
0x140007a96  push    rbp
0x140007a97  push    rsi
0x140007a98  push    rdi
0x140007a99  push    r14
0x140007a9b  sub     rsp, 20h
0x140007a9f  lea     rsi, [rcx+498h]
0x140007aa6  mov     rbx, rcx
0x140007aa9  mov     rcx, rsi; this
0x140007aac  mov     r14, rdx
0x140007aaf  call    ?Acquire@GuardedMutex@@QEAAXXZ; GuardedMutex::Acquire(void)
0x140007ab4  mov     edi, [rbx+3C8h]
0x140007aba  test    edi, edi
0x140007abc  js      short loc_140007B01
0x140007abe  mov     rbp, [rsp+48h]
0x140007ac3  mov     edx, 48h ; 'H'
0x140007ac8  mov     ecx, 101h
0x140007acd  mov     r8d, 506D7054h
0x140007ad3  call    cs:__imp_ExAllocatePool2
0x140007ada  nop     dword ptr [rax+rax+00h]
0x140007adf  mov     rcx, rax
0x140007ae2  test    rax, rax
0x140007ae5  jz      short loc_140007AF7
0x140007ae7  mov     [rax], rbp
0x140007aea  mov     rax, [rsp+48h]
0x140007aef  mov     [rcx+8], rax
0x140007af3  add     rcx, 10h; this
0x140007af7  test    rcx, rcx
0x140007afa  jnz     short loc_140007B17
0x140007afc  mov     edi, 0C000009Ah
0x140007b01  mov     rcx, rsi; this
0x140007b04  call    ?Release@GuardedMutex@@QEAAXXZ; GuardedMutex::Release(void)
0x140007b09  mov     eax, edi
0x140007b0b  add     rsp, 20h
0x140007b0f  pop     r14
0x140007b11  pop     rdi
0x140007b12  pop     rsi
0x140007b13  pop     rbp
0x140007b14  pop     rbx
0x140007b15  retn
0x140007b17  call    ??0TpmContext@@AEAA@XZ; TpmContext::TpmContext(void)
0x140007b1c  mov     r8, rax
0x140007b1f  test    rax, rax
0x140007b22  jz      short loc_140007AFC
0x140007b24  lea     rcx, [rbx+4A0h]
0x140007b2b  mov     rdx, [rcx+8]
0x140007b2f  cmp     [rdx], rcx
0x140007b32  jnz     short loc_140007B4E
0x140007b34  add     rax, 10h
0x140007b38  mov     [r14], r8
0x140007b3b  mov     [rax+8], rdx
0x140007b3f  mov     [rax], rcx
0x140007b42  mov     [rdx], rax
0x140007b45  mov     [rcx+8], rax
0x140007b49  inc     dword ptr [rbx+0Ch]
0x140007b4c  jmp     short loc_140007B01
0x140007b4e  mov     ecx, 3
0x140007b53  int     29h; Win8: RtlFailFast(ecx)
```
