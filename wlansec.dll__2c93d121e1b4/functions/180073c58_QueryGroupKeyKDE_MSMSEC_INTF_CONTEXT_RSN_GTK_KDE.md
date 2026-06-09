# QueryGroupKeyKDE(MSMSEC_INTF_CONTEXT *,RSN_GTK_KDE *)

- ea: `0x180073c58`
- end: `0x180073d6c`
- name: `?QueryGroupKeyKDE@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAURSN_GTK_KDE@@@Z`
- size: `276`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *, struct RSN_GTK_KDE *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18006dc68`
- `0x18006ed94`

## callees

- `0x18000c19c`
- `0x1800169c0`
- `0x18001c968`
- `0x180044554`
- `0x180051bd4`
- `0x180073c58`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180073d45`
- `MobileNetworking!ReleaseWriteLock` at `0x180073d45`
- `MobileNetworking!AcquireWriteLock` at `0x180073c9b`
- `MobileNetworking!AcquireWriteLock` at `0x180073c9b`

## pseudocode

```c
__int64 __fastcall QueryGroupKeyKDE(struct MSMSEC_INTF_CONTEXT *a1, struct RSN_GTK_KDE *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // esi
  void *Src[2]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)Src = 0;
  TraceAdapterId(*((_DWORD *)a1 + 624), ">>> Locking >>>");
  AcquireWriteLock(a1, (char *)a1 + 2512, "QueryGroupKeyKDE", 629);
  v4 = DecryptKeyMaterial(*((unsigned int *)a1 + 820), *((_QWORD *)a1 + 411), Src);
  v5 = v4;
  if ( v4 )
  {
    wil::details::in1diag3::Return_Win32(
      retaddr,
      (void *)0x27F,
      (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\rsncmn.cpp",
      (const char *)v4,
      (unsigned int)Src[0]);
  }
  else
  {
    *(_WORD *)a2 = 5853;
    *((_WORD *)a2 + 1) = (_WORD)RSN_KEY_DATA_OUI;
    *((_BYTE *)a2 + 4) = byte_1800AE906;
    *((_BYTE *)a2 + 5) = 1;
    *((_BYTE *)a2 + 6) = *((_BYTE *)a1 + 3276) & 3;
    *((_BYTE *)a2 + 7) = 0;
    memcpy_0((char *)a2 + 8, Src[1], LODWORD(Src[0]));
    v5 = 0;
  }
  TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
  ReleaseWriteLock(a1, (char *)a1 + 2512, "QueryGroupKeyKDE::<lambda_1>::operator ()", 632);
  ScrubAndFreeKeyMaterial(&Src[1], Src);
  return v5;
}

```

## disassembly

```asm
0x180073c58  push    rbx
0x180073c5a  push    rbp
0x180073c5b  push    rsi
0x180073c5c  push    rdi
0x180073c5d  sub     rsp, 38h
0x180073c61  mov     rbx, rdx
0x180073c64  mov     rdi, rcx
0x180073c67  xorps   xmm0, xmm0
0x180073c6a  movups  xmmword ptr [rsp+58h+Src], xmm0; unsigned int
0x180073c6f  lea     rdx, aLocking; ">>> Locking >>>"
0x180073c76  mov     ecx, [rcx+9C0h]; unsigned int
0x180073c7c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180073c81  lea     rbp, [rdi+9D0h]
0x180073c88  mov     r9d, 275h
0x180073c8e  lea     r8, aQuerygroupkeyk; "QueryGroupKeyKDE"
0x180073c95  mov     rdx, rbp
0x180073c98  mov     rcx, rdi
0x180073c9b  call    cs:__imp_AcquireWriteLock
0x180073ca2  nop     dword ptr [rax+rax+00h]
0x180073ca7  lea     r8, [rsp+58h+Src]
0x180073cac  mov     rdx, [rdi+0CD8h]
0x180073cb3  mov     ecx, [rdi+0CD0h]
0x180073cb9  call    DecryptKeyMaterial
0x180073cbe  mov     esi, eax
0x180073cc0  test    eax, eax
0x180073cc2  jz      short loc_180073CDF
0x180073cc4  mov     rcx, [rsp+58h]; this
0x180073cc9  mov     r9d, eax; char *
0x180073ccc  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\msmsec\\src\\rsn"...
0x180073cd3  mov     edx, 27Fh; void *
0x180073cd8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180073cdd  jmp     short loc_180073D20
0x180073cdf  mov     word ptr [rbx], 16DDh
0x180073ce4  movzx   eax, cs:?RSN_KEY_DATA_OUI@@3PAEA; uchar near * RSN_KEY_DATA_OUI
0x180073ceb  mov     [rbx+2], ax
0x180073cef  mov     al, cs:byte_1800AE906
0x180073cf5  mov     [rbx+4], al
0x180073cf8  mov     byte ptr [rbx+5], 1
0x180073cfc  mov     al, [rdi+0CCCh]
0x180073d02  and     al, 3
0x180073d04  mov     [rbx+6], al
0x180073d07  mov     byte ptr [rbx+7], 0
0x180073d0b  mov     r8d, dword ptr [rsp+58h+Src]; Size
0x180073d10  lea     rcx, [rbx+8]; void *
0x180073d14  mov     rdx, [rsp+58h+Src+8]; Src
0x180073d19  call    memcpy_0
0x180073d1e  xor     esi, esi
0x180073d20  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180073d27  mov     ecx, [rdi+9C0h]; unsigned int
0x180073d2d  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180073d32  mov     r9d, 278h
0x180073d38  lea     r8, aQuerygroupkeyk_0; "QueryGroupKeyKDE::<lambda_1>::operator "...
0x180073d3f  mov     rdx, rbp
0x180073d42  mov     rcx, rdi
0x180073d45  call    cs:__imp_ReleaseWriteLock
0x180073d4c  nop     dword ptr [rax+rax+00h]
0x180073d51  lea     rdx, [rsp+58h+Src]
0x180073d56  lea     rcx, [rsp+58h+Src+8]
0x180073d5b  call    ScrubAndFreeKeyMaterial
0x180073d60  mov     eax, esi
0x180073d62  add     rsp, 38h
0x180073d66  pop     rdi
0x180073d67  pop     rsi
0x180073d68  pop     rbp
0x180073d69  pop     rbx
0x180073d6a  retn
```
