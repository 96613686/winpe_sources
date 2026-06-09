# WdsImgOpenBootImageGroup

- ea: `0x180006d60`
- end: `0x180006e62`
- name: `WdsImgOpenBootImageGroup`
- size: `258`
- prototype: `__int64 __fastcall(struct CImageStore *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001588`
- `0x180006470`
- `0x180006714`
- `0x180006d60`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall WdsImgOpenBootImageGroup(struct CImageStore *a1, unsigned __int16 *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8

  if ( a2 && a3 && a1 )
  {
    if ( *((_DWORD *)a1 + 4) == 1 )
    {
      v7 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      v8 = v7;
      if ( v7 )
      {
        *((_QWORD *)v7 + 4) = 0;
        *((_QWORD *)v7 + 3) = 0;
        *((_QWORD *)v7 + 5) = 0;
        v7[2] = 1;
        v7[4] = 2;
        *(_QWORD *)v7 = &CImageGroup::`vftable';
        v6 = (unsigned int)CImageGroup::Initialize((unsigned __int16 **)v7, a1, a2);
        if ( (int)ElValidateHr_1(v6, v9, v10, 183) >= 0 )
          v8[4] = 3;
        if ( (int)ElValidateHr_1((unsigned int)v6, v11, v12, 677) >= 0 )
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
0x180006d60  mov     [rsp+arg_0], rbx
0x180006d65  mov     [rsp+arg_8], rbp
0x180006d6a  mov     [rsp+arg_10], rsi
0x180006d6f  push    rdi
0x180006d70  sub     rsp, 20h
0x180006d74  mov     rsi, r8
0x180006d77  mov     rbp, rdx
0x180006d7a  mov     rbx, rcx
0x180006d7d  test    rdx, rdx
0x180006d80  jz      loc_180006E45
0x180006d86  test    r8, r8
0x180006d89  jz      loc_180006E45
0x180006d8f  test    rcx, rcx
0x180006d92  jz      loc_180006E45
0x180006d98  cmp     dword ptr [rcx+10h], 1
0x180006d9c  jz      short loc_180006DA8
0x180006d9e  mov     ebx, 0C1020205h
0x180006da3  jmp     loc_180006E4A
0x180006da8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006daf  mov     ecx, 30h ; '0'; unsigned __int64
0x180006db4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006db9  mov     rdi, rax
0x180006dbc  test    rax, rax
0x180006dbf  jz      short loc_180006E3E
0x180006dc1  and     qword ptr [rdi+20h], 0
0x180006dc6  mov     r8, rbp; unsigned __int16 *
0x180006dc9  and     qword ptr [rdi+18h], 0
0x180006dce  mov     rdx, rbx; struct CImageStore *
0x180006dd1  and     qword ptr [rdi+28h], 0
0x180006dd6  mov     rcx, rdi; this
0x180006dd9  mov     dword ptr [rax+8], 1
0x180006de0  mov     dword ptr [rax+10h], 2
0x180006de7  lea     rax, ??_7CImageGroup@@6B@; const CImageGroup::`vftable'
0x180006dee  mov     [rdi], rax
0x180006df1  call    ?Initialize@CImageGroup@@QEAAJPEAVCImageStore@@PEBG@Z; CImageGroup::Initialize(CImageStore *,ushort const *)
0x180006df6  mov     r9d, 0B7h
0x180006dfc  mov     ecx, eax
0x180006dfe  mov     ebx, eax
0x180006e00  call    ElValidateHr_1
0x180006e05  test    eax, eax
0x180006e07  js      short loc_180006E10
0x180006e09  mov     dword ptr [rdi+10h], 3
0x180006e10  mov     r9d, 2A5h
0x180006e16  mov     ecx, ebx
0x180006e18  call    ElValidateHr_1
0x180006e1d  test    eax, eax
0x180006e1f  js      short loc_180006E24
0x180006e21  mov     [rsi], rdi
0x180006e24  test    ebx, ebx
0x180006e26  jns     short loc_180006E4A
0x180006e28  mov     rax, [rdi]
0x180006e2b  mov     edx, 1
0x180006e30  mov     rcx, rdi
0x180006e33  mov     rax, [rax+10h]
0x180006e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3c  jmp     short loc_180006E4A
0x180006e3e  mov     ebx, 8007000Eh
0x180006e43  jmp     short loc_180006E4A
0x180006e45  mov     ebx, 80070057h
0x180006e4a  mov     rbp, [rsp+28h+arg_8]
0x180006e4f  mov     eax, ebx
0x180006e51  mov     rbx, [rsp+28h+arg_0]
0x180006e56  mov     rsi, [rsp+28h+arg_10]
0x180006e5b  add     rsp, 20h
0x180006e5f  pop     rdi
0x180006e60  retn
```
