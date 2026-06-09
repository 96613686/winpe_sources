# CSpClassFactory::RemoveAll(void)

- ea: `0x18000e06c`
- end: `0x18000e0d2`
- name: `?RemoveAll@CSpClassFactory@@QEAAJXZ`
- size: `102`
- prototype: `__int64 __fastcall(CSpClassFactory *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000afe0`

## callees

- `0x180004cfc`
- `0x18000b670`
- `0x18000e06c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CSpClassFactory::RemoveAll(CSpClassFactory *this)
{
  char *v2; // rdi
  __int64 v3; // rax
  void (__fastcall ***v4)(_QWORD, __int64); // r11

  if ( *((int *)this + 6) <= 0 )
  {
    v2 = (char *)this + 8;
  }
  else
  {
    do
    {
      v2 = (char *)this + 8;
      v3 = *((_QWORD *)this + 1);
      if ( *(_QWORD *)(v3 + 16)
        && (int)CSpClassFactory::DetachProduct(this, *(struct CSpClassFactoryProduct **)(v3 + 16)) >= 0 )
      {
        (**v4)(v4, 1);
      }
    }
    while ( *((int *)this + 6) > 0 );
  }
  CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll((__int64)v2);
  return 0;
}

```

## disassembly

```asm
0x18000e06c  mov     [rsp+arg_0], rbx
0x18000e071  push    rdi
0x18000e072  sub     rsp, 20h
0x18000e076  cmp     dword ptr [rcx+18h], 0
0x18000e07a  mov     rbx, rcx
0x18000e07d  jle     short loc_18000E0B9
0x18000e07f  lea     rdi, [rbx+8]
0x18000e083  mov     rax, [rdi]
0x18000e086  mov     r11, [rax+10h]
0x18000e08a  test    r11, r11
0x18000e08d  jz      short loc_18000E0B1
0x18000e08f  mov     rdx, r11; struct CSpClassFactoryProduct *
0x18000e092  mov     rcx, rbx; this
0x18000e095  call    ?DetachProduct@CSpClassFactory@@IEAAJPEAVCSpClassFactoryProduct@@@Z; CSpClassFactory::DetachProduct(CSpClassFactoryProduct *)
0x18000e09a  test    eax, eax
0x18000e09c  js      short loc_18000E0B1
0x18000e09e  mov     rax, [r11]
0x18000e0a1  mov     edx, 1
0x18000e0a6  mov     rcx, r11
0x18000e0a9  mov     rax, [rax]
0x18000e0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0b1  cmp     dword ptr [rbx+18h], 0
0x18000e0b5  jg      short loc_18000E07F
0x18000e0b7  jmp     short loc_18000E0BD
0x18000e0b9  lea     rdi, [rcx+8]
0x18000e0bd  mov     rcx, rdi
0x18000e0c0  call    ?RemoveAll@?$CSPList@PEAVCAgreementElement@@PEAV1@@@QEAAXXZ; CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(void)
0x18000e0c5  mov     rbx, [rsp+28h+arg_0]
0x18000e0ca  xor     eax, eax
0x18000e0cc  add     rsp, 20h
0x18000e0d0  pop     rdi
0x18000e0d1  retn
```
