# WdsImgOpenImageGroup

- ea: `0x180006e70`
- end: `0x180006f6d`
- name: `WdsImgOpenImageGroup`
- size: `253`
- prototype: `__int64 __fastcall(struct CImageStore *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001588`
- `0x180006470`
- `0x180006714`
- `0x180006e70`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall WdsImgOpenImageGroup(struct CImageStore *a1, unsigned __int16 *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8

  if ( a2 && *a2 && a3 && a1 )
  {
    if ( *((_DWORD *)a1 + 4) == 1 )
    {
      v7 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      v8 = v7;
      if ( v7 )
      {
        v7[2] = 1;
        v7[4] = 2;
        *((_QWORD *)v7 + 4) = 0;
        *(_QWORD *)v7 = &CImageGroup::`vftable';
        *((_QWORD *)v7 + 3) = 0;
        *((_QWORD *)v7 + 5) = 0;
        v6 = (unsigned int)CImageGroup::Initialize((unsigned __int16 **)v7, a1, a2);
        if ( (int)ElValidateHr_1(v6, v9, v10, 604) >= 0 )
          *a3 = v8;
        if ( (int)v6 < 0 )
          (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 16LL))(v8, 1);
      }
      else
      {
        LODWORD(v6) = -2147024882;
      }
    }
    else
    {
      LODWORD(v6) = -1056833019;
    }
  }
  else
  {
    LODWORD(v6) = -2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006e70  mov     rax, rsp
0x180006e73  mov     [rax+8], rbx
0x180006e77  mov     [rax+10h], rbp
0x180006e7b  mov     [rax+18h], rsi
0x180006e7f  mov     [rax+20h], rdi
0x180006e83  push    r14
0x180006e85  sub     rsp, 20h
0x180006e89  xor     ebp, ebp
0x180006e8b  mov     r14, r8
0x180006e8e  mov     rsi, rdx
0x180006e91  mov     rbx, rcx
0x180006e94  test    rdx, rdx
0x180006e97  jz      loc_180006F4A
0x180006e9d  cmp     [rdx], bp
0x180006ea0  jz      loc_180006F4A
0x180006ea6  test    r8, r8
0x180006ea9  jz      loc_180006F4A
0x180006eaf  test    rcx, rcx
0x180006eb2  jz      loc_180006F4A
0x180006eb8  cmp     dword ptr [rcx+10h], 1
0x180006ebc  jz      short loc_180006EC8
0x180006ebe  mov     ebx, 0C1020205h
0x180006ec3  jmp     loc_180006F4F
0x180006ec8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006ecf  mov     ecx, 30h ; '0'; unsigned __int64
0x180006ed4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006ed9  mov     rdi, rax
0x180006edc  test    rax, rax
0x180006edf  jz      short loc_180006F43
0x180006ee1  mov     dword ptr [rax+8], 1
0x180006ee8  mov     r8, rsi; unsigned __int16 *
0x180006eeb  mov     dword ptr [rax+10h], 2
0x180006ef2  mov     rdx, rbx; struct CImageStore *
0x180006ef5  lea     rax, ??_7CImageGroup@@6B@; const CImageGroup::`vftable'
0x180006efc  mov     [rdi+20h], rbp
0x180006f00  mov     rcx, rdi; this
0x180006f03  mov     [rdi], rax
0x180006f06  mov     [rdi+18h], rbp
0x180006f0a  mov     [rdi+28h], rbp
0x180006f0e  call    ?Initialize@CImageGroup@@QEAAJPEAVCImageStore@@PEBG@Z; CImageGroup::Initialize(CImageStore *,ushort const *)
0x180006f13  mov     r9d, 25Ch
0x180006f19  mov     ecx, eax
0x180006f1b  mov     ebx, eax
0x180006f1d  call    ElValidateHr_1
0x180006f22  test    eax, eax
0x180006f24  js      short loc_180006F29
0x180006f26  mov     [r14], rdi
0x180006f29  test    ebx, ebx
0x180006f2b  jns     short loc_180006F4F
0x180006f2d  mov     rax, [rdi]
0x180006f30  mov     edx, 1
0x180006f35  mov     rcx, rdi
0x180006f38  mov     rax, [rax+10h]
0x180006f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f41  jmp     short loc_180006F4F
0x180006f43  mov     ebx, 8007000Eh
0x180006f48  jmp     short loc_180006F4F
0x180006f4a  mov     ebx, 80070057h
0x180006f4f  mov     rbp, [rsp+28h+arg_8]
0x180006f54  mov     eax, ebx
0x180006f56  mov     rbx, [rsp+28h+arg_0]
0x180006f5b  mov     rsi, [rsp+28h+arg_10]
0x180006f60  mov     rdi, [rsp+28h+arg_18]
0x180006f65  add     rsp, 20h
0x180006f69  pop     r14
0x180006f6b  retn
```
