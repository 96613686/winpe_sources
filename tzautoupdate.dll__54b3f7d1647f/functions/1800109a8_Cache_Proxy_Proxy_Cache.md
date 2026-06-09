# Cache::Proxy::Proxy(Cache *)

- ea: `0x1800109a8`
- end: `0x180010a44`
- name: `??0Proxy@Cache@@AEAA@PEAV1@@Z`
- size: `156`
- prototype: `Cache::Proxy *__fastcall(Cache::Proxy *this, struct Cache *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011b0c`

## callees

- `0x180011b30`

## pseudocode

```c
Cache::Proxy *__fastcall Cache::Proxy::Proxy(Cache::Proxy *this, struct Cache *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx

  *(_QWORD *)this = a2;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive((char *)this + 8);
  v3 = *(_QWORD *)this;
  *((_QWORD *)this + 3) = *(_QWORD *)this;
  *((_QWORD *)this + 2) = v3 + 40;
  v4 = *(_QWORD *)this;
  *((_QWORD *)this + 5) = *(_QWORD *)this;
  *((_QWORD *)this + 4) = v4 + 72;
  v5 = *(_QWORD *)this;
  *((_QWORD *)this + 7) = *(_QWORD *)this;
  *((_QWORD *)this + 6) = v5 + 74;
  v6 = *(_QWORD *)this;
  *((_QWORD *)this + 9) = *(_QWORD *)this;
  *((_QWORD *)this + 8) = v6 + 76;
  v7 = *(_QWORD *)this;
  *((_QWORD *)this + 11) = *(_QWORD *)this;
  *((_QWORD *)this + 10) = v7 + 80;
  v8 = *(_QWORD *)this;
  *((_QWORD *)this + 13) = *(_QWORD *)this;
  *((_QWORD *)this + 12) = v8 + 88;
  v9 = *(_QWORD *)this;
  *((_QWORD *)this + 15) = *(_QWORD *)this;
  *((_QWORD *)this + 14) = v9 + 96;
  v10 = *(_QWORD *)this;
  *((_QWORD *)this + 17) = *(_QWORD *)this;
  *((_QWORD *)this + 16) = v10 + 104;
  return this;
}

```

## disassembly

```asm
0x1800109a8  push    rbx
0x1800109aa  sub     rsp, 20h
0x1800109ae  mov     rbx, rcx
0x1800109b1  mov     [rcx], rdx
0x1800109b4  add     rcx, 8
0x1800109b8  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800109bd  mov     rdx, [rbx]
0x1800109c0  mov     [rbx+18h], rdx
0x1800109c4  lea     rax, [rdx+28h]
0x1800109c8  mov     [rbx+10h], rax
0x1800109cc  mov     rdx, [rbx]
0x1800109cf  mov     [rbx+28h], rdx
0x1800109d3  lea     rax, [rdx+48h]
0x1800109d7  mov     [rbx+20h], rax
0x1800109db  mov     rcx, [rbx]
0x1800109de  mov     [rbx+38h], rcx
0x1800109e2  lea     rax, [rcx+4Ah]
0x1800109e6  mov     [rbx+30h], rax
0x1800109ea  mov     rcx, [rbx]
0x1800109ed  mov     [rbx+48h], rcx
0x1800109f1  lea     rax, [rcx+4Ch]
0x1800109f5  mov     [rbx+40h], rax
0x1800109f9  mov     rcx, [rbx]
0x1800109fc  mov     [rbx+58h], rcx
0x180010a00  lea     rax, [rcx+50h]
0x180010a04  mov     [rbx+50h], rax
0x180010a08  mov     rcx, [rbx]
0x180010a0b  mov     [rbx+68h], rcx
0x180010a0f  lea     rax, [rcx+58h]
0x180010a13  mov     [rbx+60h], rax
0x180010a17  mov     rcx, [rbx]
0x180010a1a  mov     [rbx+78h], rcx
0x180010a1e  lea     rax, [rcx+60h]
0x180010a22  mov     [rbx+70h], rax
0x180010a26  mov     rcx, [rbx]
0x180010a29  mov     [rbx+88h], rcx
0x180010a30  lea     rax, [rcx+68h]
0x180010a34  mov     [rbx+80h], rax
0x180010a3b  mov     rax, rbx
0x180010a3e  add     rsp, 20h
0x180010a42  pop     rbx
0x180010a43  retn
```
