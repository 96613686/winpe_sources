# CWmpDecoderFrame::HrClearCache(void)

- ea: `0x180039c70`
- end: `0x180039d3f`
- name: `?HrClearCache@CWmpDecoderFrame@@MEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ab98`
- `0x18002e43c`
- `0x180031850`
- `0x18003a7a0`

## callees

- `0x180039c70`
- `0x180045010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180039ca1`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180039ca1`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::HrClearCache(CWmpDecoderFrame *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *((_DWORD *)this + 16646) = 0;
  *(_OWORD *)((char *)this + 66568) = 0;
  *(_OWORD *)((char *)this + 66552) = 0;
  v2 = (void *)*((_QWORD *)this + 8324);
  if ( v2 )
  {
    _aligned_free(v2);
    *((_QWORD *)this + 8324) = 0;
  }
  v3 = *((_QWORD *)this + 8337);
  *((_QWORD *)this + 8325) = 0;
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 8337) = 0;
  }
  v4 = *((_QWORD *)this + 8338);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 8338) = 0;
  }
  v5 = *((_QWORD *)this + 8340);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 8340) = 0;
  }
  *((_DWORD *)this + 16679) = 0;
  return 0;
}

```

## disassembly

```asm
0x180039c70  push    rbx
0x180039c72  sub     rsp, 20h
0x180039c76  xor     eax, eax
0x180039c78  xorps   xmm0, xmm0
0x180039c7b  mov     [rcx+10418h], eax
0x180039c81  xorps   xmm1, xmm1
0x180039c84  movups  xmmword ptr [rcx+10408h], xmm0
0x180039c8b  mov     rbx, rcx
0x180039c8e  movups  xmmword ptr [rcx+103F8h], xmm1
0x180039c95  mov     rcx, [rcx+10420h]; Block
0x180039c9c  test    rcx, rcx
0x180039c9f  jz      short loc_180039CB8
0x180039ca1  call    cs:__imp__aligned_free
0x180039ca8  nop     dword ptr [rax+rax+00h]
0x180039cad  mov     qword ptr [rbx+10420h], 0
0x180039cb8  mov     rcx, [rbx+10488h]
0x180039cbf  mov     qword ptr [rbx+10428h], 0
0x180039cca  test    rcx, rcx
0x180039ccd  jz      short loc_180039CE6
0x180039ccf  mov     rax, [rcx]
0x180039cd2  mov     rax, [rax+10h]
0x180039cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cdb  mov     qword ptr [rbx+10488h], 0
0x180039ce6  mov     rcx, [rbx+10490h]
0x180039ced  test    rcx, rcx
0x180039cf0  jz      short loc_180039D09
0x180039cf2  mov     rax, [rcx]
0x180039cf5  mov     rax, [rax+10h]
0x180039cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cfe  mov     qword ptr [rbx+10490h], 0
0x180039d09  mov     rcx, [rbx+104A0h]
0x180039d10  test    rcx, rcx
0x180039d13  jz      short loc_180039D2C
0x180039d15  mov     rax, [rcx]
0x180039d18  mov     rax, [rax+10h]
0x180039d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d21  mov     qword ptr [rbx+104A0h], 0
0x180039d2c  mov     dword ptr [rbx+1049Ch], 0
0x180039d36  xor     eax, eax
0x180039d38  add     rsp, 20h
0x180039d3c  pop     rbx
0x180039d3d  retn
```
