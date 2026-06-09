# CEnumImageGroups::GetAt(CImageGroup * *)

- ea: `0x180007720`
- end: `0x1800077f0`
- name: `?GetAt@CEnumImageGroups@@QEAAJPEAPEAVCImageGroup@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(CEnumImageGroups *__hidden this, struct CImageGroup **)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007d60`
- `0x18000d950`
- `0x18000da10`

## callees

- `0x180001588`
- `0x180006470`
- `0x180007720`
- `0x1800077f8`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CEnumImageGroups::GetAt(CEnumImageGroups *this, struct CImageGroup **a2)
{
  __int64 v4; // rdi
  const unsigned __int16 *v5; // rsi
  struct CImageGroup *v6; // rax
  struct CImageGroup *v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8

  if ( *((_DWORD *)this + 11) )
  {
    v5 = (const unsigned __int16 *)**((_QWORD **)this + 4);
    v6 = (struct CImageGroup *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      *((_QWORD *)v6 + 4) = 0;
      *((_QWORD *)v6 + 3) = 0;
      *((_QWORD *)v6 + 5) = 0;
      *((_DWORD *)v6 + 2) = 1;
      *((_DWORD *)v6 + 4) = 2;
      *(_QWORD *)v6 = &CImageGroup::`vftable';
      v4 = (unsigned int)CImageGroup::Initialize((unsigned __int16 **)v6, *((struct CImageStore **)this + 3), v5);
      if ( (int)ElValidateHr_3(v4, v8, v9, 200) < 0 )
        (*(void (__fastcall **)(struct CImageGroup *, __int64))(*(_QWORD *)v7 + 16LL))(v7, 1);
      else
        *a2 = v7;
    }
    else
    {
      LODWORD(v4) = -2147024882;
    }
  }
  else
  {
    LODWORD(v4) = -1056833017;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007720  mov     [rsp+arg_0], rbx
0x180007725  mov     [rsp+arg_8], rsi
0x18000772a  mov     [rsp+arg_10], rdi
0x18000772f  push    r14
0x180007731  sub     rsp, 20h
0x180007735  xor     esi, esi
0x180007737  mov     r14, rdx
0x18000773a  mov     rdi, rcx
0x18000773d  cmp     [rcx+2Ch], esi
0x180007740  jnz     short loc_18000774C
0x180007742  mov     edi, 0C1020207h
0x180007747  jmp     loc_1800077D7
0x18000774c  jbe     short loc_180007755
0x18000774e  mov     rax, [rcx+20h]
0x180007752  mov     rsi, [rax]
0x180007755  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000775c  mov     ecx, 30h ; '0'; unsigned __int64
0x180007761  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007766  mov     rbx, rax
0x180007769  test    rax, rax
0x18000776c  jz      short loc_1800077D2
0x18000776e  and     qword ptr [rbx+20h], 0
0x180007773  mov     r8, rsi; unsigned __int16 *
0x180007776  and     qword ptr [rbx+18h], 0
0x18000777b  mov     rcx, rbx; this
0x18000777e  and     qword ptr [rbx+28h], 0
0x180007783  mov     dword ptr [rax+8], 1
0x18000778a  mov     dword ptr [rax+10h], 2
0x180007791  lea     rax, ??_7CImageGroup@@6B@; const CImageGroup::`vftable'
0x180007798  mov     [rbx], rax
0x18000779b  mov     rdx, [rdi+18h]; struct CImageStore *
0x18000779f  call    ?Initialize@CImageGroup@@QEAAJPEAVCImageStore@@PEBG@Z; CImageGroup::Initialize(CImageStore *,ushort const *)
0x1800077a4  mov     r9d, 0C8h
0x1800077aa  mov     ecx, eax
0x1800077ac  mov     edi, eax
0x1800077ae  call    ElValidateHr_3
0x1800077b3  test    eax, eax
0x1800077b5  js      short loc_1800077BC
0x1800077b7  mov     [r14], rbx
0x1800077ba  jmp     short loc_1800077D7
0x1800077bc  mov     rax, [rbx]
0x1800077bf  mov     edx, 1
0x1800077c4  mov     rcx, rbx
0x1800077c7  mov     rax, [rax+10h]
0x1800077cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077d0  jmp     short loc_1800077D7
0x1800077d2  mov     edi, 8007000Eh
0x1800077d7  mov     rbx, [rsp+28h+arg_0]
0x1800077dc  mov     eax, edi
0x1800077de  mov     rdi, [rsp+28h+arg_10]
0x1800077e3  mov     rsi, [rsp+28h+arg_8]
0x1800077e8  add     rsp, 20h
0x1800077ec  pop     r14
0x1800077ee  retn
```
