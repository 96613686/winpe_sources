# CKeyString::GetCompleteString(ushort * *)

- ea: `0x18001e9f0`
- end: `0x18001eb85`
- name: `?GetCompleteString@CKeyString@@QEAAKPEAPEAG@Z`
- size: `405`
- prototype: `unsigned int __fastcall(CKeyString *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000214c`
- `0x18000d888`
- `0x18001e9f0`
- `0x18001f080`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001eb77`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001eb77`

## pseudocode

```c
__int64 __fastcall CKeyString::GetCompleteString(const unsigned __int16 ***this, unsigned __int16 **a2)
{
  const unsigned __int16 **v2; // r8
  unsigned int v3; // ebx
  __int64 v4; // rbp
  __int64 *v7; // rax
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rax
  unsigned __int64 v12; // rbp
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  const unsigned __int16 **v16; // r14
  const unsigned __int16 **v17; // r15
  const unsigned __int16 *v18; // r8
  int v19; // edi
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8

  v2 = *this;
  v3 = 0;
  v4 = 0;
  while ( v2 )
  {
    v7 = (__int64 *)v2;
    v8 = -1;
    v9 = v2[1];
    v2 = (const unsigned __int16 **)v2[2];
    do
      ++v8;
    while ( v9[v8] );
    v10 = *v7;
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(v10 + 2 * v11) );
    v4 += v8 + v11 + 2;
  }
  v12 = v4 + 1;
  v13 = 2 * v12;
  if ( !is_mul_ok(v12, 2u) )
    v13 = -1;
  v14 = (unsigned __int16 *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( v14 )
  {
    *v14 = 0;
    v16 = *this;
    do
    {
      if ( !v16 )
      {
        *a2 = v15;
        return v3;
      }
      v17 = v16;
      v18 = *v16;
      v16 = (const unsigned __int16 **)v16[2];
      v19 = StringCchCatW(v15, v12, v18);
      if ( (int)ElValidateHr_6(v19, v20, v21, 0x1B1u) < 0 )
        break;
      v19 = StringCchCatW(v15, v12, L"=");
      if ( (int)ElValidateHr_6(v19, v22, v23, 0x1B6u) < 0 )
        break;
      v19 = StringCchCatW(v15, v12, v17[1]);
      if ( (int)ElValidateHr_6(v19, v24, v25, 0x1BBu) < 0 )
        break;
      v19 = StringCchCatW(v15, v12, L";");
    }
    while ( (int)ElValidateHr_6(v19, v26, v27, 0x1C0u) >= 0 );
    if ( v19 >= 0 || (v3 = (unsigned __int16)v19, (v19 & 0x1FFF0000) != 0x70000) )
      v3 = v19;
    if ( v3 )
      operator delete(v15);
  }
  else
  {
    return 8;
  }
  return v3;
}

```

## disassembly

```asm
0x18001e9f0  mov     [rsp+arg_0], rbx
0x18001e9f5  mov     [rsp+arg_8], rbp
0x18001e9fa  mov     [rsp+arg_10], rsi
0x18001e9ff  push    rdi
0x18001ea00  push    r12
0x18001ea02  push    r13
0x18001ea04  push    r14
0x18001ea06  push    r15
0x18001ea08  sub     rsp, 20h
0x18001ea0c  mov     r8, [rcx]
0x18001ea0f  xor     r13d, r13d
0x18001ea12  mov     ebx, r13d
0x18001ea15  mov     ebp, r13d
0x18001ea18  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001ea1c  mov     r12, rdx
0x18001ea1f  mov     r14, rcx
0x18001ea22  jmp     short loc_18001EA56
0x18001ea24  lea     rax, [r8]
0x18001ea27  mov     rcx, r9
0x18001ea2a  mov     rdx, [rax+8]
0x18001ea2e  mov     r8, [r8+10h]
0x18001ea32  inc     rcx
0x18001ea35  cmp     [rdx+rcx*2], r13w
0x18001ea3a  jnz     short loc_18001EA32
0x18001ea3c  mov     rdx, [rax]
0x18001ea3f  mov     rax, r9
0x18001ea42  inc     rax
0x18001ea45  cmp     [rdx+rax*2], r13w
0x18001ea4a  jnz     short loc_18001EA42
0x18001ea4c  add     rbp, 2
0x18001ea50  add     rbp, rax
0x18001ea53  add     rbp, rcx
0x18001ea56  test    r8, r8
0x18001ea59  jnz     short loc_18001EA24
0x18001ea5b  lea     eax, [r8+2]
0x18001ea5f  inc     rbp
0x18001ea62  mul     rbp
0x18001ea65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ea6c  cmovo   rax, r9
0x18001ea70  mov     rcx, rax; unsigned __int64
0x18001ea73  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ea78  mov     rsi, rax
0x18001ea7b  test    rax, rax
0x18001ea7e  jnz     short loc_18001EA88
0x18001ea80  lea     ebx, [rax+8]
0x18001ea83  jmp     loc_18001EB39
0x18001ea88  mov     [rax], r13w
0x18001ea8c  mov     r14, [r14]
0x18001ea8f  jmp     loc_18001EB2C
0x18001ea94  lea     r15, [r14]
0x18001ea97  mov     rdx, rbp; unsigned __int64
0x18001ea9a  mov     r8, [r15]; unsigned __int16 *
0x18001ea9d  mov     rcx, rsi; unsigned __int16 *
0x18001eaa0  mov     r14, [r14+10h]
0x18001eaa4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001eaa9  mov     r9d, 1B1h
0x18001eaaf  mov     ecx, eax
0x18001eab1  mov     edi, eax
0x18001eab3  call    ElValidateHr_6
0x18001eab8  test    eax, eax
0x18001eaba  js      loc_18001EB59
0x18001eac0  lea     r8, asc_180036B58; "="
0x18001eac7  mov     rdx, rbp; unsigned __int64
0x18001eaca  mov     rcx, rsi; unsigned __int16 *
0x18001eacd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001ead2  mov     r9d, 1B6h
0x18001ead8  mov     ecx, eax
0x18001eada  mov     edi, eax
0x18001eadc  call    ElValidateHr_6
0x18001eae1  test    eax, eax
0x18001eae3  js      short loc_18001EB59
0x18001eae5  mov     r8, [r15+8]; unsigned __int16 *
0x18001eae9  mov     rdx, rbp; unsigned __int64
0x18001eaec  mov     rcx, rsi; unsigned __int16 *
0x18001eaef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001eaf4  mov     r9d, 1BBh
0x18001eafa  mov     ecx, eax
0x18001eafc  mov     edi, eax
0x18001eafe  call    ElValidateHr_6
0x18001eb03  test    eax, eax
0x18001eb05  js      short loc_18001EB59
0x18001eb07  lea     r8, asc_180036B5C; ";"
0x18001eb0e  mov     rdx, rbp; unsigned __int64
0x18001eb11  mov     rcx, rsi; unsigned __int16 *
0x18001eb14  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001eb19  mov     r9d, 1C0h
0x18001eb1f  mov     ecx, eax
0x18001eb21  mov     edi, eax
0x18001eb23  call    ElValidateHr_6
0x18001eb28  test    eax, eax
0x18001eb2a  js      short loc_18001EB59
0x18001eb2c  test    r14, r14
0x18001eb2f  jnz     loc_18001EA94
0x18001eb35  mov     [r12], rsi
0x18001eb39  mov     rbp, [rsp+48h+arg_8]
0x18001eb3e  mov     eax, ebx
0x18001eb40  mov     rbx, [rsp+48h+arg_0]
0x18001eb45  mov     rsi, [rsp+48h+arg_10]
0x18001eb4a  add     rsp, 20h
0x18001eb4e  pop     r15
0x18001eb50  pop     r14
0x18001eb52  pop     r13
0x18001eb54  pop     r12
0x18001eb56  pop     rdi
0x18001eb57  retn
0x18001eb59  test    edi, edi
0x18001eb5b  jns     short loc_18001EB6E
0x18001eb5d  mov     eax, edi
0x18001eb5f  movzx   ebx, di
0x18001eb62  and     eax, 1FFF0000h
0x18001eb67  cmp     eax, 70000h
0x18001eb6c  jz      short loc_18001EB70
0x18001eb6e  mov     ebx, edi
0x18001eb70  test    ebx, ebx
0x18001eb72  jz      short loc_18001EB39
0x18001eb74  mov     rcx, rsi
0x18001eb77  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001eb7e  nop     dword ptr [rax+rax+00h]
0x18001eb83  jmp     short loc_18001EB39
```
