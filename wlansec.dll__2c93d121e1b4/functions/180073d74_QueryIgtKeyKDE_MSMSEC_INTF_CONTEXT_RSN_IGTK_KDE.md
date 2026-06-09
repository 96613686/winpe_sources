# QueryIgtKeyKDE(MSMSEC_INTF_CONTEXT *,RSN_IGTK_KDE *)

- ea: `0x180073d74`
- end: `0x180073e8d`
- name: `?QueryIgtKeyKDE@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAURSN_IGTK_KDE@@@Z`
- size: `281`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *, struct RSN_IGTK_KDE *)`
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
- `0x180073d74`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180073e66`
- `MobileNetworking!ReleaseWriteLock` at `0x180073e66`
- `MobileNetworking!AcquireWriteLock` at `0x180073db7`
- `MobileNetworking!AcquireWriteLock` at `0x180073db7`

## pseudocode

```c
__int64 __fastcall QueryIgtKeyKDE(struct MSMSEC_INTF_CONTEXT *a1, struct RSN_IGTK_KDE *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // esi
  void *Src[2]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)Src = 0;
  TraceAdapterId(*((_DWORD *)a1 + 624), ">>> Locking >>>");
  AcquireWriteLock(a1, (char *)a1 + 2512, "QueryIgtKeyKDE", 666);
  v4 = DecryptKeyMaterial(*((unsigned int *)a1 + 820), *((_QWORD *)a1 + 411), Src);
  v5 = v4;
  if ( v4 )
  {
    wil::details::in1diag3::Return_Win32(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\rsncmn.cpp",
      (const char *)v4,
      (unsigned int)Src[0]);
  }
  else
  {
    *(_WORD *)a2 = 7389;
    *((_WORD *)a2 + 1) = (_WORD)RSN_KEY_DATA_OUI;
    *((_BYTE *)a2 + 4) = byte_1800AE906;
    *((_BYTE *)a2 + 5) = 9;
    *((_WORD *)a2 + 3) = *((unsigned __int8 *)a1 + 3296);
    *((_DWORD *)a2 + 2) = 0;
    *((_WORD *)a2 + 6) = 0;
    memcpy_0((char *)a2 + 14, Src[1], LODWORD(Src[0]));
    v5 = 0;
  }
  TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
  ReleaseWriteLock(a1, (char *)a1 + 2512, "QueryIgtKeyKDE::<lambda_1>::operator ()", 669);
  ScrubAndFreeKeyMaterial(&Src[1], Src);
  return v5;
}

```

## disassembly

```asm
0x180073d74  push    rbx
0x180073d76  push    rbp
0x180073d77  push    rsi
0x180073d78  push    rdi
0x180073d79  sub     rsp, 38h
0x180073d7d  mov     rbx, rdx
0x180073d80  mov     rdi, rcx
0x180073d83  xorps   xmm0, xmm0
0x180073d86  movups  xmmword ptr [rsp+58h+Src], xmm0; unsigned int
0x180073d8b  lea     rdx, aLocking; ">>> Locking >>>"
0x180073d92  mov     ecx, [rcx+9C0h]; unsigned int
0x180073d98  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180073d9d  lea     rbp, [rdi+9D0h]
0x180073da4  mov     r9d, 29Ah
0x180073daa  lea     r8, aQueryigtkeykde_0; "QueryIgtKeyKDE"
0x180073db1  mov     rdx, rbp
0x180073db4  mov     rcx, rdi
0x180073db7  call    cs:__imp_AcquireWriteLock
0x180073dbe  nop     dword ptr [rax+rax+00h]
0x180073dc3  lea     r8, [rsp+58h+Src]
0x180073dc8  mov     rdx, [rdi+0CD8h]
0x180073dcf  mov     ecx, [rdi+0CD0h]
0x180073dd5  call    DecryptKeyMaterial
0x180073dda  mov     esi, eax
0x180073ddc  test    eax, eax
0x180073dde  jz      short loc_180073DFB
0x180073de0  mov     rcx, [rsp+58h]; this
0x180073de5  mov     r9d, eax; char *
0x180073de8  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\msmsec\\src\\rsn"...
0x180073def  mov     edx, 2A4h; void *
0x180073df4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180073df9  jmp     short loc_180073E41
0x180073dfb  mov     word ptr [rbx], 1CDDh
0x180073e00  movzx   eax, cs:?RSN_KEY_DATA_OUI@@3PAEA; uchar near * RSN_KEY_DATA_OUI
0x180073e07  mov     [rbx+2], ax
0x180073e0b  mov     al, cs:byte_1800AE906
0x180073e11  mov     [rbx+4], al
0x180073e14  mov     byte ptr [rbx+5], 9
0x180073e18  movzx   eax, byte ptr [rdi+0CE0h]
0x180073e1f  mov     [rbx+6], ax
0x180073e23  xor     eax, eax
0x180073e25  mov     [rbx+8], eax
0x180073e28  mov     [rbx+0Ch], ax
0x180073e2c  mov     r8d, dword ptr [rsp+58h+Src]; Size
0x180073e31  lea     rcx, [rbx+0Eh]; void *
0x180073e35  mov     rdx, [rsp+58h+Src+8]; Src
0x180073e3a  call    memcpy_0
0x180073e3f  xor     esi, esi
0x180073e41  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180073e48  mov     ecx, [rdi+9C0h]; unsigned int
0x180073e4e  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180073e53  mov     r9d, 29Dh
0x180073e59  lea     r8, aQueryigtkeykde; "QueryIgtKeyKDE::<lambda_1>::operator ()"
0x180073e60  mov     rdx, rbp
0x180073e63  mov     rcx, rdi
0x180073e66  call    cs:__imp_ReleaseWriteLock
0x180073e6d  nop     dword ptr [rax+rax+00h]
0x180073e72  lea     rdx, [rsp+58h+Src]
0x180073e77  lea     rcx, [rsp+58h+Src+8]
0x180073e7c  call    ScrubAndFreeKeyMaterial
0x180073e81  mov     eax, esi
0x180073e83  add     rsp, 38h
0x180073e87  pop     rdi
0x180073e88  pop     rsi
0x180073e89  pop     rbp
0x180073e8a  pop     rbx
0x180073e8b  retn
```
