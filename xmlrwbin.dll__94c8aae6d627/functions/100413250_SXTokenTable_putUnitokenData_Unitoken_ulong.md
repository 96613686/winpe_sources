# SXTokenTable::putUnitokenData(Unitoken *,ulong *)

- ea: `0x100413250`
- end: `0x1004132f0`
- name: `?putUnitokenData@SXTokenTable@@QEAAXPEAVUnitoken@@PEAK@Z`
- size: `160`
- prototype: `void __fastcall(SXTokenTable *__hidden this, struct Unitoken *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100409da0`
- `0x100410010`

## callees

- `0x100401350`
- `0x100406550`
- `0x100413250`
- `0x100413a50`

## pseudocode

```c
void __fastcall SXTokenTable::putUnitokenData(SXTokenTable *this, struct CStringPtr **a2, unsigned int *a3)
{
  unsigned int *v4; // rbx
  unsigned int v5; // ecx
  unsigned int v6; // edx
  _DWORD *v7; // rbx

  if ( a3 )
    *a3 = *((_DWORD *)this + 29);
  v4 = (unsigned int *)((char *)this + 96);
  v5 = *((_DWORD *)this + 29);
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
  {
    MXRRaiseException(-2147352566);
    JUMPOUT(0x1004132EFLL);
  }
  if ( v6 > v4[4] )
  {
    _mm_lfence();
    _varray_base::_ensureCapacity_((_varray_base *)v4, v6, 0x28u);
    v5 = v4[5];
  }
  v4[5] = v5 + 1;
  v7 = (_DWORD *)(*((_QWORD *)v4 + 3) + 40LL * v5);
  RStringPtr::assign((RStringPtr *)v7, *a2);
  RStringPtr::assign((RStringPtr *)(v7 + 2), a2[1]);
  RStringPtr::assign((RStringPtr *)(v7 + 4), a2[2]);
  v7[6] = *((_DWORD *)a2 + 6);
  v7[7] = *((_DWORD *)a2 + 7);
  v7[8] = *((_DWORD *)a2 + 8);
}

```

## disassembly

```asm
0x100413250  mov     [rsp+arg_0], rbx
0x100413255  push    rdi
0x100413256  sub     rsp, 20h
0x10041325a  mov     rdi, rdx
0x10041325d  test    r8, r8
0x100413260  jz      short loc_100413268
0x100413262  mov     eax, [rcx+74h]
0x100413265  mov     [r8], eax
0x100413268  lea     rbx, [rcx+60h]
0x10041326c  mov     ecx, [rcx+74h]
0x10041326f  lea     edx, [rcx+1]; unsigned int
0x100413272  cmp     edx, ecx
0x100413274  jb      short loc_1004132E5
0x100413276  cmp     edx, [rbx+10h]
0x100413279  jbe     short loc_10041328F
0x10041327b  lfence
0x10041327e  mov     r8d, 28h ; '('; unsigned __int64
0x100413284  mov     rcx, rbx; this
0x100413287  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x10041328c  mov     ecx, [rbx+14h]
0x10041328f  lea     eax, [rcx+1]
0x100413292  mov     [rbx+14h], eax
0x100413295  mov     rdx, [rdi]; struct CStringPtr *
0x100413298  mov     eax, ecx
0x10041329a  lea     rcx, [rax+rax*4]
0x10041329e  mov     rax, [rbx+18h]
0x1004132a2  lea     rbx, [rax+rcx*8]
0x1004132a6  mov     rcx, rbx; this
0x1004132a9  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x1004132ae  mov     rdx, [rdi+8]; struct CStringPtr *
0x1004132b2  lea     rcx, [rbx+8]; this
0x1004132b6  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x1004132bb  mov     rdx, [rdi+10h]; struct CStringPtr *
0x1004132bf  lea     rcx, [rbx+10h]; this
0x1004132c3  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x1004132c8  mov     eax, [rdi+18h]
0x1004132cb  mov     [rbx+18h], eax
0x1004132ce  mov     eax, [rdi+1Ch]
0x1004132d1  mov     [rbx+1Ch], eax
0x1004132d4  mov     eax, [rdi+20h]
0x1004132d7  mov     [rbx+20h], eax
0x1004132da  mov     rbx, [rsp+28h+arg_0]
0x1004132df  add     rsp, 20h
0x1004132e3  pop     rdi
0x1004132e4  retn
0x1004132e5  mov     ecx, 8002000Ah; int
0x1004132ea  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
