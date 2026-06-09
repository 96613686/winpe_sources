# CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocateNone>::AddItem(CWdsDeviceControllerManager::CQueryEntry *)

- ea: `0x180006ab0`
- end: `0x180006b7c`
- name: `?AddItem@?$CDynArray@PEAUCQueryEntry@CWdsDeviceControllerManager@@VCDeallocateNone@@@@QEAAKPEAUCQueryEntry@CWdsDeviceControllerManager@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003acc`
- `0x1800042f4`
- `0x1800051e8`
- `0x1800063b4`
- `0x18000aaac`
- `0x18000b228`

## callees

- `0x180006ab0`
- `0x1800150b8`
- `0x1800157a4`
- `0x180015c91`

## pseudocode

```c
__int64 __fastcall CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocateNone>::AddItem(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // edi
  unsigned int v4; // ecx
  int v6; // eax
  unsigned int v7; // edx
  unsigned int v8; // ebp
  unsigned __int64 v9; // rax
  void *v10; // rax
  void *v11; // rsi

  v3 = 0;
  v4 = *(_DWORD *)(a1 + 8);
  if ( *(_DWORD *)(a1 + 12) != v4 )
    goto LABEL_13;
  v6 = v4 >> 1;
  if ( v4 >> 1 < 0x20 )
    v6 = 32;
  v7 = v4 + v6;
  if ( v4 + v6 < v4 )
  {
    v3 = v7 < v4 ? 0x216 : 0;
    goto LABEL_12;
  }
  v8 = v4 + v6;
  v9 = 8LL * v7;
  if ( !is_mul_ok(v7, 8u) )
    v9 = -1;
  v10 = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    memmove_0(v10, *(const void **)a1, 8LL * *(unsigned int *)(a1 + 8));
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = v11;
    *(_DWORD *)(a1 + 8) = v8;
LABEL_12:
    if ( v3 )
      return v3;
LABEL_13:
    *(_QWORD *)(*(_QWORD *)a1 + 8LL * (unsigned int)(*(_DWORD *)(a1 + 12))++) = a2;
    return v3;
  }
  return 8;
}

```

## disassembly

```asm
0x180006ab0  mov     rax, rsp
0x180006ab3  mov     [rax+8], rbx
0x180006ab7  mov     [rax+10h], rbp
0x180006abb  mov     [rax+18h], rsi
0x180006abf  mov     [rax+20h], rdi
0x180006ac3  push    r14
0x180006ac5  sub     rsp, 20h
0x180006ac9  mov     rbx, rcx
0x180006acc  xor     edi, edi
0x180006ace  mov     ecx, [rcx+8]
0x180006ad1  mov     r14, rdx
0x180006ad4  cmp     [rbx+0Ch], ecx
0x180006ad7  jnz     short loc_180006B52
0x180006ad9  lea     edx, [rdi+20h]
0x180006adc  mov     eax, ecx
0x180006ade  shr     eax, 1
0x180006ae0  cmp     eax, edx
0x180006ae2  cmovb   eax, edx
0x180006ae5  or      ebp, 0FFFFFFFFh
0x180006ae8  lea     edx, [rcx+rax]
0x180006aeb  cmp     edx, ecx
0x180006aed  cmovnb  ebp, edx
0x180006af0  jnb     short loc_180006AFC
0x180006af2  sbb     edi, edi
0x180006af4  and     edi, 216h
0x180006afa  jmp     short loc_180006B4E
0x180006afc  mov     ecx, ebp
0x180006afe  mov     eax, 8
0x180006b03  mul     rcx
0x180006b06  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006b0d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006b14  cmovo   rax, rcx
0x180006b18  mov     rcx, rax; unsigned __int64
0x180006b1b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006b20  mov     rsi, rax
0x180006b23  test    rax, rax
0x180006b26  jnz     short loc_180006B2D
0x180006b28  lea     edi, [rax+8]
0x180006b2b  jmp     short loc_180006B5F
0x180006b2d  mov     r8d, [rbx+8]
0x180006b31  mov     rcx, rsi; void *
0x180006b34  mov     rdx, [rbx]; Src
0x180006b37  shl     r8, 3; Size
0x180006b3b  call    memmove_0
0x180006b40  mov     rcx, [rbx]; Block
0x180006b43  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006b48  mov     [rbx], rsi
0x180006b4b  mov     [rbx+8], ebp
0x180006b4e  test    edi, edi
0x180006b50  jnz     short loc_180006B5F
0x180006b52  mov     edx, [rbx+0Ch]
0x180006b55  mov     rcx, [rbx]
0x180006b58  mov     [rcx+rdx*8], r14
0x180006b5c  inc     dword ptr [rbx+0Ch]
0x180006b5f  mov     rbx, [rsp+28h+arg_0]
0x180006b64  mov     eax, edi
0x180006b66  mov     rdi, [rsp+28h+arg_18]
0x180006b6b  mov     rbp, [rsp+28h+arg_8]
0x180006b70  mov     rsi, [rsp+28h+arg_10]
0x180006b75  add     rsp, 20h
0x180006b79  pop     r14
0x180006b7b  retn
```
