# CASFScriptCommandObject::Persist(CASFArchive &)

- ea: `0x18001ecf0`
- end: `0x18001ee8c`
- name: `?Persist@CASFScriptCommandObject@@UEAAJAEAVCASFArchive@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(CASFScriptCommandObject *__hidden this, struct CASFArchive *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001e900`
- `0x18001ecf0`
- `0x1800265b0`
- `0x1800266d8`
- `0x180026748`
- `0x180026824`
- `0x18002b010`

## pseudocode

```c
int __fastcall CASFScriptCommandObject::Persist(CASFScriptCommandObject *this, struct CASFArchive *a2)
{
  int result; // eax
  unsigned int i; // esi
  __int64 v6; // rcx
  unsigned __int64 v7; // r10
  int v8; // r10d
  __int64 v9; // r11
  unsigned int j; // esi
  __int64 v11; // r11
  __int64 v12; // r11
  __int64 v13; // rcx
  unsigned __int64 v14; // r10
  int v15; // r10d
  __int64 v16; // r11

  *((_QWORD *)this + 4) = (*(unsigned int (__fastcall **)(CASFScriptCommandObject *))(*(_QWORD *)this + 24LL))(this);
  result = CASFLonghandObject::Persist(this, a2);
  if ( result >= 0 )
  {
    result = CASFArchive::StoreGUID(a2, (const struct _GUID *)((char *)this + 56));
    if ( result >= 0 )
    {
      result = CASFArchive::StoreWORD(a2, *((_WORD *)this + 36));
      if ( result >= 0 )
      {
        result = CASFArchive::StoreWORD(a2, *((_WORD *)this + 37));
        if ( result >= 0 )
        {
          for ( i = 0; i < *((unsigned __int16 *)this + 37); ++i )
          {
            v6 = *(_QWORD *)(*((_QWORD *)this + 10) + 8LL * i);
            if ( v6 )
            {
              v7 = -1;
              do
                ++v7;
              while ( *(_WORD *)(v6 + 2 * v7) );
              if ( v7 > 0xFFFF )
                return -2147418113;
              result = CASFArchive::StoreWORD(a2, v7);
              if ( result < 0 )
                return result;
              result = CASFArchive::StoreBytes(a2, *(const unsigned __int8 **)(*((_QWORD *)this + 10) + 8 * v9), 2 * v8);
            }
            else
            {
              result = CASFArchive::StoreWORD(a2, 0);
            }
            if ( result < 0 )
              return result;
          }
          for ( j = 0; j < *((unsigned __int16 *)this + 36); ++j )
          {
            result = CASFArchive::StoreDWORD(a2, *(_DWORD *)(14LL * j + *((_QWORD *)this + 11)));
            if ( result < 0 )
              return result;
            result = CASFArchive::StoreWORD(a2, *(_WORD *)(v11 + *((_QWORD *)this + 11) + 4));
            if ( result < 0 )
              return result;
            v13 = *(_QWORD *)(v12 + *((_QWORD *)this + 11) + 6);
            if ( v13 )
            {
              v14 = -1;
              do
                ++v14;
              while ( *(_WORD *)(v13 + 2 * v14) );
              if ( v14 > 0xFFFF )
                return -2147418113;
              result = CASFArchive::StoreWORD(a2, v14);
              if ( result < 0 )
                return result;
              result = CASFArchive::StoreBytes(
                         a2,
                         *(const unsigned __int8 **)(v16 + *((_QWORD *)this + 11) + 6),
                         2 * v15);
            }
            else
            {
              result = CASFArchive::StoreWORD(a2, 0);
            }
            if ( result < 0 )
              return result;
          }
          return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ecf0  push    rbx
0x18001ecf2  push    rbp
0x18001ecf3  push    rsi
0x18001ecf4  push    rdi
0x18001ecf5  sub     rsp, 28h
0x18001ecf9  mov     rax, [rcx]
0x18001ecfc  mov     rdi, rdx
0x18001ecff  mov     rbx, rcx
0x18001ed02  mov     rax, [rax+18h]
0x18001ed06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed0b  mov     eax, eax
0x18001ed0d  mov     rdx, rdi; struct CASFArchive *
0x18001ed10  mov     rcx, rbx; this
0x18001ed13  mov     [rbx+20h], rax
0x18001ed17  call    ?Persist@CASFLonghandObject@@UEAAJAEAVCASFArchive@@@Z; CASFLonghandObject::Persist(CASFArchive &)
0x18001ed1c  xor     ebp, ebp
0x18001ed1e  test    eax, eax
0x18001ed20  js      loc_18001EE83
0x18001ed26  lea     rdx, [rbx+38h]; struct _GUID *
0x18001ed2a  mov     rcx, rdi; this
0x18001ed2d  call    ?StoreGUID@CASFArchive@@QEAAJAEBU_GUID@@@Z; CASFArchive::StoreGUID(_GUID const &)
0x18001ed32  test    eax, eax
0x18001ed34  js      loc_18001EE83
0x18001ed3a  movzx   edx, word ptr [rbx+48h]; unsigned __int16
0x18001ed3e  mov     rcx, rdi; this
0x18001ed41  call    ?StoreWORD@CASFArchive@@QEAAJG@Z; CASFArchive::StoreWORD(ushort)
0x18001ed46  test    eax, eax
0x18001ed48  js      loc_18001EE83
0x18001ed4e  movzx   edx, word ptr [rbx+4Ah]; unsigned __int16
0x18001ed52  mov     rcx, rdi; this
0x18001ed55  call    ?StoreWORD@CASFArchive@@QEAAJG@Z; CASFArchive::StoreWORD(ushort)
0x18001ed5a  test    eax, eax
0x18001ed5c  js      loc_18001EE83
0x18001ed62  mov     esi, ebp
0x18001ed64  movzx   eax, word ptr [rbx+4Ah]
0x18001ed68  cmp     esi, eax
0x18001ed6a  jnb     short loc_18001EDD7
0x18001ed6c  mov     rax, [rbx+50h]
0x18001ed70  mov     r11d, esi
0x18001ed73  mov     rcx, [rax+r11*8]
0x18001ed77  test    rcx, rcx
0x18001ed7a  jz      short loc_18001EDC1
0x18001ed7c  or      r10, 0FFFFFFFFFFFFFFFFh
0x18001ed80  inc     r10
0x18001ed83  cmp     [rcx+r10*2], bp
0x18001ed88  jnz     short loc_18001ED80
0x18001ed8a  cmp     r10, 0FFFFh
0x18001ed91  ja      loc_18001EE7A
0x18001ed97  movzx   edx, r10w; unsigned __int16
0x18001ed9b  mov     rcx, rdi; this
0x18001ed9e  call    ?StoreWORD@CASFArchive@@QEAAJG@Z; CASFArchive::StoreWORD(ushort)
0x18001eda3  test    eax, eax
0x18001eda5  js      loc_18001EE83
0x18001edab  mov     rdx, [rbx+50h]
0x18001edaf  lea     r8d, [r10+r10]; unsigned int
0x18001edb3  mov     rcx, rdi; this
0x18001edb6  mov     rdx, [rdx+r11*8]; unsigned __int8 *
0x18001edba  call    ?StoreBytes@CASFArchive@@QEAAJPEBEK@Z; CASFArchive::StoreBytes(uchar const *,ulong)
0x18001edbf  jmp     short loc_18001EDCB
0x18001edc1  xor     edx, edx; unsigned __int16
0x18001edc3  mov     rcx, rdi; this
0x18001edc6  call    ?StoreWORD@CASFArchive@@QEAAJG@Z; CASFArchive::StoreWORD(ushort)
0x18001edcb  test    eax, eax
0x18001edcd  js      loc_18001EE83
0x18001edd3  inc     esi
0x18001edd5  jmp     short loc_18001ED64
0x18001edd7  mov     esi, ebp
0x18001edd9  movzx   eax, word ptr [rbx+48h]
0x18001eddd  cmp     esi, eax
0x18001eddf  jnb     loc_18001EE81
0x18001ede5  mov     rdx, [rbx+58h]
0x18001ede9  mov     rcx, rdi; this
0x18001edec  mov     eax, esi
0x18001edee  imul    r11, rax, 0Eh
0x18001edf2  mov     edx, [r11+rdx]; unsigned int
0x18001edf6  call    ?StoreDWORD@CASFArchive@@QEAAJK@Z; CASFArchive::StoreDWORD(ulong)
0x18001edfb  test    eax, eax
0x18001edfd  js      loc_18001EE83
0x18001ee03  mov     rdx, [rbx+58h]
0x18001ee07  mov     rcx, rdi; this
0x18001ee0a  movzx   edx, word ptr [r11+rdx+4]; unsigned __int16
0x18001ee10  call    ?StoreWORD@CASFArchive@@QEAAJG@Z; CASFArchive::StoreWORD(ushort)
0x18001ee15  test    eax, eax
0x18001ee17  js      short loc_18001EE83
0x18001ee19  mov     rax, [rbx+58h]
0x18001ee1d  mov     rcx, [r11+rax+6]
0x18001ee22  test    rcx, rcx
0x18001ee25  jz      short loc_18001EE65
0x18001ee27  or      r10, 0FFFFFFFFFFFFFFFFh
0x18001ee2b  inc     r10
0x18001ee2e  cmp     [rcx+r10*2], bp
0x18001ee33  jnz     short loc_18001EE2B
0x18001ee35  cmp     r10, 0FFFFh
0x18001ee3c  ja      short loc_18001EE7A
0x18001ee3e  movzx   edx, r10w; unsigned __int16
0x18001ee42  mov     rcx, rdi; this
0x18001ee45  call    ?StoreWORD@CASFArchive@@QEAAJG@Z; CASFArchive::StoreWORD(ushort)
0x18001ee4a  test    eax, eax
0x18001ee4c  js      short loc_18001EE83
0x18001ee4e  mov     rdx, [rbx+58h]
0x18001ee52  lea     r8d, [r10+r10]; unsigned int
0x18001ee56  mov     rcx, rdi; this
0x18001ee59  mov     rdx, [r11+rdx+6]; unsigned __int8 *
0x18001ee5e  call    ?StoreBytes@CASFArchive@@QEAAJPEBEK@Z; CASFArchive::StoreBytes(uchar const *,ulong)
0x18001ee63  jmp     short loc_18001EE6F
0x18001ee65  xor     edx, edx; unsigned __int16
0x18001ee67  mov     rcx, rdi; this
0x18001ee6a  call    ?StoreWORD@CASFArchive@@QEAAJG@Z; CASFArchive::StoreWORD(ushort)
0x18001ee6f  test    eax, eax
0x18001ee71  js      short loc_18001EE83
0x18001ee73  inc     esi
0x18001ee75  jmp     loc_18001EDD9
0x18001ee7a  mov     eax, 8000FFFFh
0x18001ee7f  jmp     short loc_18001EE83
0x18001ee81  xor     eax, eax
0x18001ee83  add     rsp, 28h
0x18001ee87  pop     rdi
0x18001ee88  pop     rsi
0x18001ee89  pop     rbp
0x18001ee8a  pop     rbx
0x18001ee8b  retn
```
