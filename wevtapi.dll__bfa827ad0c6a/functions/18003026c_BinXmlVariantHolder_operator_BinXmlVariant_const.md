# BinXmlVariantHolder::operator=(BinXmlVariant const &)

- ea: `0x18003026c`
- end: `0x180030422`
- name: `??4BinXmlVariantHolder@@QEAAAEAV0@AEBUBinXmlVariant@@@Z`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180027fac`

## callees

- `0x18000a020`
- `0x18000b6a0`
- `0x180023548`
- `0x18003026c`
- `0x180038fa4`
- `0x180038fbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x1800303bb`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x1800303bb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800302d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800302d7`

## pseudocode

```c
__int64 __fastcall BinXmlVariantHolder::operator=(__int64 a1, const void **a2)
{
  unsigned int v4; // eax
  HLOCAL v5; // rax
  _OWORD *v6; // rax
  unsigned int v7; // eax
  __int64 v8; // rax
  void *v9; // rax
  __int64 v10; // r9
  __int64 v11; // rax
  void *v12; // rax
  __int64 v13; // r8
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v16; // [rsp+30h] [rbp-28h]
  int v17; // [rsp+38h] [rbp-20h]
  int v18; // [rsp+3Ch] [rbp-1Ch]
  int v19; // [rsp+40h] [rbp-18h]

  BinXmlVariantHolder::Clear((void **)a1);
  switch ( *((_DWORD *)a2 + 3) )
  {
    case 1:
      v11 = *((unsigned int *)a2 + 2);
      *(_DWORD *)(a1 + 8) = v11;
      v12 = operator new(saturated_mul(v11 + 1, 2u));
      v13 = *(unsigned int *)(a1 + 8);
      *(_QWORD *)a1 = v12;
      memcpy_0(v12, *a2, 2 * v13);
      *(_WORD *)(*(_QWORD *)a1 + 2LL * *(unsigned int *)(a1 + 8)) = 0;
      goto LABEL_19;
    case 2:
      v8 = *((unsigned int *)a2 + 2);
      *(_DWORD *)(a1 + 8) = v8;
      v9 = operator new(v8 + 1);
      v10 = *(unsigned int *)(a1 + 8);
      *(_QWORD *)a1 = v9;
      _o_strncpy_s(v9, v10 + 1, *a2);
      goto LABEL_19;
    case 0xE:
      v7 = *((_DWORD *)a2 + 2);
      *(_DWORD *)(a1 + 8) = v7;
      v5 = operator new(v7);
      *(_QWORD *)a1 = v5;
LABEL_16:
      memcpy_0(v5, *a2, *(unsigned int *)(a1 + 8));
      goto LABEL_19;
    case 0xF:
    case 0x12:
      *(_DWORD *)(a1 + 8) = -1;
      v6 = operator new(0x10u);
      *(_QWORD *)a1 = v6;
      *v6 = *(_OWORD *)*a2;
      goto LABEL_19;
    case 0x13:
      v4 = *((_DWORD *)a2 + 2);
      *(_DWORD *)(a1 + 8) = v4;
      v5 = LocalAlloc(0, v4);
      *(_QWORD *)a1 = v5;
      if ( !v5 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 14);
        }
        v16 = 0;
        v17 = 14;
        v18 = -1;
        pExceptionObject = 0;
        v19 = 59;
        throw (EvtException *)&pExceptionObject;
      }
      goto LABEL_16;
  }
  *(_DWORD *)(a1 + 8) = -1;
  *(_QWORD *)a1 = *a2;
LABEL_19:
  *(_DWORD *)(a1 + 12) = *((_DWORD *)a2 + 3);
  return a1;
}

```

## disassembly

```asm
0x18003026c  mov     [rsp+arg_0], rbx
0x180030271  mov     [rsp+arg_8], rsi
0x180030276  push    rdi
0x180030277  sub     rsp, 50h
0x18003027b  mov     rdi, rdx
0x18003027e  mov     rbx, rcx
0x180030281  call    ?Clear@BinXmlVariantHolder@@QEAAXXZ; BinXmlVariantHolder::Clear(void)
0x180030286  mov     ecx, [rdi+0Ch]
0x180030289  sub     ecx, 1
0x18003028c  jz      loc_1800303C3
0x180030292  sub     ecx, 1
0x180030295  jz      loc_18003039B
0x18003029b  sub     ecx, 0Ch
0x18003029e  jz      loc_18003037A
0x1800302a4  sub     ecx, 1
0x1800302a7  jz      loc_180030357
0x1800302ad  sub     ecx, 3
0x1800302b0  jz      loc_180030357
0x1800302b6  cmp     ecx, 1
0x1800302b9  jz      short loc_1800302CD
0x1800302bb  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x1800302c2  mov     rax, [rdi]
0x1800302c5  mov     [rbx], rax
0x1800302c8  jmp     loc_180030409
0x1800302cd  mov     eax, [rdi+8]
0x1800302d0  xor     ecx, ecx; uFlags
0x1800302d2  mov     edx, eax; uBytes
0x1800302d4  mov     [rbx+8], eax
0x1800302d7  call    cs:__imp_LocalAlloc
0x1800302dd  xor     esi, esi
0x1800302df  mov     [rbx], rax
0x1800302e2  test    rax, rax
0x1800302e5  jnz     loc_18003038A
0x1800302eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800302f2  lea     rax, WPP_GLOBAL_Control
0x1800302f9  lea     ebx, [rsi+0Eh]
0x1800302fc  cmp     rcx, rax
0x1800302ff  jz      short loc_180030323
0x180030301  test    byte ptr [rcx+1Ch], 2
0x180030305  jz      short loc_180030323
0x180030307  cmp     byte ptr [rcx+19h], 2
0x18003030b  jb      short loc_180030323
0x18003030d  mov     rcx, [rcx+10h]
0x180030311  lea     edx, [rsi+0Ah]
0x180030314  mov     r9d, ebx
0x180030317  lea     r8, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids
0x18003031e  call    WPP_SF_D
0x180030323  xorps   xmm0, xmm0
0x180030326  mov     [rsp+58h+var_28], rsi
0x18003032b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180030332  mov     [rsp+58h+var_20], ebx
0x180030336  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18003033b  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x180030343  movdqu  [rsp+58h+pExceptionObject], xmm0
0x180030349  mov     [rsp+58h+var_18], 3Bh ; ';'
0x180030351  call    _CxxThrowException_0
0x180030357  mov     ecx, 10h; dwBytes
0x18003035c  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x180030363  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030368  mov     [rbx], rax
0x18003036b  mov     rcx, [rdi]
0x18003036e  movups  xmm0, xmmword ptr [rcx]
0x180030371  movdqu  xmmword ptr [rax], xmm0
0x180030375  jmp     loc_180030409
0x18003037a  mov     eax, [rdi+8]
0x18003037d  mov     ecx, eax; dwBytes
0x18003037f  mov     [rbx+8], eax
0x180030382  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030387  mov     [rbx], rax
0x18003038a  mov     r8d, [rbx+8]; Size
0x18003038e  mov     rcx, rax; void *
0x180030391  mov     rdx, [rdi]; Src
0x180030394  call    memcpy_0
0x180030399  jmp     short loc_180030409
0x18003039b  mov     eax, [rdi+8]
0x18003039e  mov     [rbx+8], eax
0x1800303a1  lea     rcx, [rax+1]; dwBytes
0x1800303a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800303aa  mov     r9d, [rbx+8]
0x1800303ae  mov     rcx, rax
0x1800303b1  mov     [rbx], rax
0x1800303b4  mov     r8, [rdi]
0x1800303b7  lea     rdx, [r9+1]
0x1800303bb  call    cs:__imp__o_strncpy_s
0x1800303c1  jmp     short loc_180030409
0x1800303c3  mov     eax, [rdi+8]
0x1800303c6  mov     [rbx+8], eax
0x1800303c9  lea     rcx, [rax+1]
0x1800303cd  mov     eax, 2
0x1800303d2  mul     rcx
0x1800303d5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800303dc  cmovb   rax, rcx
0x1800303e0  mov     rcx, rax; dwBytes
0x1800303e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800303e8  mov     r8d, [rbx+8]
0x1800303ec  mov     rcx, rax; void *
0x1800303ef  mov     [rbx], rax
0x1800303f2  add     r8, r8; Size
0x1800303f5  mov     rdx, [rdi]; Src
0x1800303f8  call    memcpy_0
0x1800303fd  mov     ecx, [rbx+8]
0x180030400  xor     esi, esi
0x180030402  mov     rax, [rbx]
0x180030405  mov     [rax+rcx*2], si
0x180030409  mov     eax, [rdi+0Ch]
0x18003040c  mov     rsi, [rsp+58h+arg_8]
0x180030411  mov     [rbx+0Ch], eax
0x180030414  mov     rax, rbx
0x180030417  mov     rbx, [rsp+58h+arg_0]
0x18003041c  add     rsp, 50h
0x180030420  pop     rdi
0x180030421  retn
```
