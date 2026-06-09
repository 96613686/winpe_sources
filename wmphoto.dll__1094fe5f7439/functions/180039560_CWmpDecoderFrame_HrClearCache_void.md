# CWmpDecoderFrame::HrClearCache(void)

- ea: `0x180039560`
- end: `0x180039628`
- name: `?HrClearCache@CWmpDecoderFrame@@MEAAJXZ`
- size: `200`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a9e8`
- `0x18002e11c`
- `0x1800314f0`
- `0x18003a070`

## callees

- `0x180039560`
- `0x180044010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180039591`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180039591`

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
0x180039560  push    rbx
0x180039562  sub     rsp, 20h
0x180039566  xor     eax, eax
0x180039568  xorps   xmm0, xmm0
0x18003956b  mov     [rcx+10418h], eax
0x180039571  xorps   xmm1, xmm1
0x180039574  movups  xmmword ptr [rcx+10408h], xmm0
0x18003957b  mov     rbx, rcx
0x18003957e  movups  xmmword ptr [rcx+103F8h], xmm1
0x180039585  mov     rcx, [rcx+10420h]; Block
0x18003958c  test    rcx, rcx
0x18003958f  jz      short loc_1800395A2
0x180039591  call    cs:__imp__aligned_free
0x180039597  mov     qword ptr [rbx+10420h], 0
0x1800395a2  mov     rcx, [rbx+10488h]
0x1800395a9  mov     qword ptr [rbx+10428h], 0
0x1800395b4  test    rcx, rcx
0x1800395b7  jz      short loc_1800395D0
0x1800395b9  mov     rax, [rcx]
0x1800395bc  mov     rax, [rax+10h]
0x1800395c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395c5  mov     qword ptr [rbx+10488h], 0
0x1800395d0  mov     rcx, [rbx+10490h]
0x1800395d7  test    rcx, rcx
0x1800395da  jz      short loc_1800395F3
0x1800395dc  mov     rax, [rcx]
0x1800395df  mov     rax, [rax+10h]
0x1800395e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395e8  mov     qword ptr [rbx+10490h], 0
0x1800395f3  mov     rcx, [rbx+104A0h]
0x1800395fa  test    rcx, rcx
0x1800395fd  jz      short loc_180039616
0x1800395ff  mov     rax, [rcx]
0x180039602  mov     rax, [rax+10h]
0x180039606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003960b  mov     qword ptr [rbx+104A0h], 0
0x180039616  mov     dword ptr [rbx+1049Ch], 0
0x180039620  xor     eax, eax
0x180039622  add     rsp, 20h
0x180039626  pop     rbx
0x180039627  retn
```
