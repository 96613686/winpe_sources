# _RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory17AcquireEntryIndex

- ea: `0x140013670`
- end: `0x14001387c`
- name: `_RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory17AcquireEntryIndex`
- size: `524`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400096c0`

## callees

- `0x1400133c0`
- `0x140013670`
- `0x140013a70`
- `0x140013e50`
- `0x140017a10`
- `0x140018450`
- `0x1400184d7`

## pseudocode

```c
__int64 __fastcall RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory17AcquireEntryIndex(
        __int64 a1,
        int *a2)
{
  unsigned int v2; // ebp
  unsigned __int64 v4; // rbx
  __int64 *v5; // r12
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned __int64 v8; // rdi
  __int64 v9; // r15
  __int64 v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // ecx
  int *v14; // rax
  __int64 v16; // rbx
  __int64 v17; // [rsp+0h] [rbp-88h] BYREF
  int *v18; // [rsp+20h] [rbp-68h]
  int v19; // [rsp+2Ch] [rbp-5Ch] BYREF
  _DWORD v20[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+38h] [rbp-50h]
  __int64 v22; // [rsp+40h] [rbp-48h]

  v2 = 14;
  if ( !*(_BYTE *)(a1 + 30) )
  {
    v19 = 0;
    v4 = *(_QWORD *)(a1 + 16);
    if ( !v4 )
      goto LABEL_31;
    v5 = *(__int64 **)(a1 + 8);
    v6 = *v5;
    if ( !*v5 )
      RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001C118);
    v18 = a2;
    if ( (unsigned int)RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable17AcquireEntryIndex(
                         v6,
                         &v19) )
    {
      if ( !*v5 )
        RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001C130);
      v2 = 14;
      if ( *(_DWORD *)(*v5 + 72) == *(_DWORD *)(*v5 + 76) )
      {
        v8 = *(unsigned __int16 *)(a1 + 28);
        v9 = (unsigned __int16)(((_WORD)v8 == 0) + *(_WORD *)(a1 + 28));
        v10 = 1;
        while ( v9 != v10 )
        {
          if ( v4 == v10 )
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v4, v4, &off_14001C160);
          v11 = v5[v10];
          if ( !v11 )
            RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001C178);
          if ( !(unsigned int)RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable17AcquireEntryIndex(
                                v11,
                                &v19) )
          {
            LODWORD(v8) = v10;
LABEL_18:
            v14 = v18;
            v13 = ((_DWORD)v8 << 16) + *(_DWORD *)(a1 + 24) + v19 - 0x10000;
            goto LABEL_19;
          }
          v12 = v5[v10++];
          if ( *(_DWORD *)(v12 + 72) != *(_DWORD *)(v12 + 76) )
            goto LABEL_20;
        }
        if ( (unsigned __int16)v8 == 256 )
        {
          *(_BYTE *)(a1 + 30) = 1;
          goto LABEL_20;
        }
        LOBYTE(v7) = 1;
        RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable7__Create_llvm_14523797218057561932(
          v20,
          0x10000,
          v7);
        if ( v20[0] == 1 )
        {
          v2 = v20[1];
        }
        else
        {
          if ( v4 <= v8 )
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v8, v4, &off_14001C148);
          v16 = v21;
          core::ptr::drop_in_place_enum2__core::option::Option_alloc::boxed::Box_handle_manager::GdiHandleEntryTable::GdiHandleEntryTable_gdi_alloc::TaggedAllocator_1668572487_________(v5[v8]);
          v5[v8] = v16;
          v2 = RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable17AcquireEntryIndex(
                 v16,
                 &v19);
          if ( !v2 )
          {
            *(_WORD *)(a1 + 28) = v8 + 1;
            goto LABEL_18;
          }
        }
      }
    }
    else
    {
      v13 = v19;
      v14 = v18;
LABEL_19:
      *v14 = v13;
      v2 = 0;
    }
  }
LABEL_20:
  if ( _security_cookie != ((unsigned __int64)&v17 ^ v22) )
LABEL_31:
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(0, 0, &off_14001C100);
  return v2;
}

```

## disassembly

```asm
0x140013670  push    r15
0x140013672  push    r14
0x140013674  push    r13
0x140013676  push    r12
0x140013678  push    rsi
0x140013679  push    rdi
0x14001367a  push    rbp
0x14001367b  push    rbx
0x14001367c  sub     rsp, 48h
0x140013680  mov     rax, cs:__security_cookie
0x140013687  xor     rax, rsp
0x14001368a  mov     [rsp+88h+var_48], rax
0x14001368f  mov     ebp, 0Eh
0x140013694  cmp     byte ptr [rcx+1Eh], 0
0x140013698  jnz     loc_140013791
0x14001369e  mov     rsi, rcx
0x1400136a1  mov     [rsp+88h+var_5C], 0
0x1400136a9  mov     rbx, [rcx+10h]
0x1400136ad  test    rbx, rbx
0x1400136b0  jz      loc_140013859
0x1400136b6  mov     r12, [rsi+8]
0x1400136ba  mov     rcx, [r12]
0x1400136be  test    rcx, rcx
0x1400136c1  jz      loc_140013822
0x1400136c7  mov     [rsp+88h+var_68], rdx
0x1400136cc  lea     rdx, [rsp+88h+var_5C]
0x1400136d1  call    _RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable17AcquireEntryIndex
0x1400136d6  test    eax, eax
0x1400136d8  jz      short loc_140013758
0x1400136da  mov     rax, [r12]
0x1400136de  test    rax, rax
0x1400136e1  jz      loc_14001382E
0x1400136e7  mov     ecx, [rax+48h]
0x1400136ea  mov     ebp, 0Eh
0x1400136ef  cmp     ecx, [rax+4Ch]
0x1400136f2  jnz     loc_140013791
0x1400136f8  movzx   edi, word ptr [rsi+1Ch]
0x1400136fc  cmp     di, 1
0x140013700  mov     eax, edi
0x140013702  adc     eax, 0
0x140013705  movzx   r15d, ax
0x140013709  mov     r13d, 1
0x14001370f  lea     r14, [rsp+88h+var_5C]
0x140013714  nop     word ptr [rax+rax+00000000h]
0x140013720  cmp     r15, r13
0x140013723  jz      short loc_140013763
0x140013725  cmp     rbx, r13
0x140013728  jz      loc_14001383A
0x14001372e  mov     rcx, [r12+r13*8]
0x140013732  test    rcx, rcx
0x140013735  jz      loc_140013816
0x14001373b  mov     rdx, r14
0x14001373e  call    _RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable17AcquireEntryIndex
0x140013743  test    eax, eax
0x140013745  jz      short loc_140013773
0x140013747  mov     rax, [r12+r13*8]
0x14001374b  mov     ecx, [rax+48h]
0x14001374e  inc     r13
0x140013751  cmp     ecx, [rax+4Ch]
0x140013754  jz      short loc_140013720
0x140013756  jmp     short loc_140013791
0x140013758  mov     ecx, [rsp+88h+var_5C]
0x14001375c  mov     rax, [rsp+88h+var_68]
0x140013761  jmp     short loc_14001378D
0x140013763  movzx   eax, di
0x140013766  cmp     eax, 100h
0x14001376b  jnz     short loc_1400137BC
0x14001376d  mov     byte ptr [rsi+1Eh], 1
0x140013771  jmp     short loc_140013791
0x140013773  mov     edi, r13d
0x140013776  mov     rax, [rsp+88h+var_68]
0x14001377b  mov     ecx, [rsp+88h+var_5C]
0x14001377f  add     ecx, [rsi+18h]
0x140013782  shl     edi, 10h
0x140013785  add     ecx, edi
0x140013787  add     ecx, 0FFFF0000h
0x14001378d  mov     [rax], ecx
0x14001378f  xor     ebp, ebp
0x140013791  mov     rax, [rsp+88h+var_48]
0x140013796  xor     rax, rsp
0x140013799  mov     rcx, cs:__security_cookie
0x1400137a0  cmp     rcx, rax
0x1400137a3  jnz     loc_14001384C
0x1400137a9  mov     eax, ebp
0x1400137ab  add     rsp, 48h
0x1400137af  pop     rbx
0x1400137b0  pop     rbp
0x1400137b1  pop     rdi
0x1400137b2  pop     rsi
0x1400137b3  pop     r12
0x1400137b5  pop     r13
0x1400137b7  pop     r14
0x1400137b9  pop     r15
0x1400137bb  retn
0x1400137bc  lea     rcx, [rsp+88h+var_58]
0x1400137c1  mov     edx, 10000h
0x1400137c6  mov     r8b, 1
0x1400137c9  call    _RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable7__Create_llvm_14523797218057561932
0x1400137ce  cmp     [rsp+88h+var_58], 1
0x1400137d3  jnz     short loc_1400137DB
0x1400137d5  mov     ebp, [rsp+88h+var_54]
0x1400137d9  jmp     short loc_140013791
0x1400137db  cmp     rbx, rdi
0x1400137de  jbe     loc_140013869
0x1400137e4  mov     rbx, [rsp+88h+var_50]
0x1400137e9  mov     rcx, [r12+rdi*8]
0x1400137ed  call    core__ptr__drop_in_place_enum2$_core__option__Option_alloc__boxed__Box_handle_manager__GdiHandleEntryTable__GdiHandleEntryTable_gdi_alloc__TaggedAllocator_1668572487_________
0x1400137f2  mov     [r12+rdi*8], rbx
0x1400137f6  lea     rdx, [rsp+88h+var_5C]
0x1400137fb  mov     rcx, rbx
0x1400137fe  call    _RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable17AcquireEntryIndex
0x140013803  mov     ebp, eax
0x140013805  test    eax, eax
0x140013807  jnz     short loc_140013791
0x140013809  mov     eax, edi
0x14001380b  inc     eax
0x14001380d  mov     [rsi+1Ch], ax
0x140013811  jmp     loc_140013776
0x140013816  lea     rcx, off_14001C178; "handle_manager\\src\\GdiHandleEntryDire"...
0x14001381d  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x140013822  lea     rcx, off_14001C118; "handle_manager\\src\\GdiHandleEntryDire"...
0x140013829  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x14001382e  lea     rcx, off_14001C130; "handle_manager\\src\\GdiHandleEntryDire"...
0x140013835  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x14001383a  lea     r8, off_14001C160; "handle_manager\\src\\GdiHandleEntryDire"...
0x140013841  mov     rcx, rbx
0x140013844  mov     rdx, rbx
0x140013847  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14001384c  mov     rcx, [rsp+88h+var_48]
0x140013851  xor     rcx, rsp; StackCookie
0x140013854  call    __security_check_cookie
0x140013859  lea     r8, off_14001C100; "handle_manager\\src\\GdiHandleEntryDire"...
0x140013860  xor     ecx, ecx
0x140013862  xor     edx, edx
0x140013864  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140013869  lea     r8, off_14001C148; "handle_manager\\src\\GdiHandleEntryDire"...
0x140013870  mov     rcx, rdi
0x140013873  mov     rdx, rbx
0x140013876  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
