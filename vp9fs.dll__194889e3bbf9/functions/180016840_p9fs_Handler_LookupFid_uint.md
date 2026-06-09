# p9fs::Handler::LookupFid(uint)

- ea: `0x180016840`
- end: `0x180016930`
- name: `?LookupFid@Handler@p9fs@@AEAA?AV?$shared_ptr@VFid@p9fs@@@std@@I@Z`
- size: `240`
- prototype: ``
- caller_count: `21`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000f528`
- `0x180010728`
- `0x180011728`
- `0x1800119dc`
- `0x180011dac`
- `0x18001206c`
- `0x18001238c`
- `0x180012ea8`
- `0x1800130f0`
- `0x1800133e0`
- `0x1800138b0`
- `0x180013b88`
- `0x180013ffc`
- `0x180014384`
- `0x180014698`
- `0x1800148ac`
- `0x180014b78`
- `0x18001572c`
- `0x180015ad0`
- `0x180015f80`
- `0x180016310`

## callees

- `0x1800030c0`
- `0x1800030e0`
- `0x180016840`
- `0x18001c75c`

## string_xrefs

- `0x18001691b`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall p9fs::Handler::LookupFid(__int64 a1, _QWORD *a2, unsigned int a3)
{
  _Smtx_t *v6; // rbp
  __int64 *v7; // rdx
  __int64 *v8; // r8
  __int64 *v9; // rcx
  __int64 *v10; // rax
  char v11; // al
  __int64 v12; // rax
  int v14; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v6 = (_Smtx_t *)(a1 + 32);
  Smtx_lock_shared((_Smtx_t *)(a1 + 32));
  v7 = *(__int64 **)(a1 + 40);
  v8 = (__int64 *)v7[1];
  v9 = v7;
  if ( !*((_BYTE *)v8 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v8 + 8) >= a3 )
        v9 = v8;
      v10 = v8 + 2;
      if ( *((_DWORD *)v8 + 8) >= a3 )
        v10 = v8;
      v8 = (__int64 *)*v10;
    }
    while ( !*(_BYTE *)(*v10 + 25) );
  }
  if ( *((_BYTE *)v9 + 25) || a3 < *((_DWORD *)v9 + 8) )
  {
    v9 = *(__int64 **)(a1 + 40);
  }
  else if ( v9 != v7 )
  {
    v11 = 0;
    goto LABEL_13;
  }
  v11 = 1;
LABEL_13:
  if ( v11 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x56C,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
      (const char *)0x8000FFFFLL,
      v14);
  *a2 = 0;
  a2[1] = 0;
  v12 = v9[6];
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  *a2 = v9[5];
  a2[1] = v9[6];
  Smtx_unlock_shared(v6);
  return a2;
}

```

## disassembly

```asm
0x180016840  mov     rax, rsp
0x180016843  mov     [rax+18h], rbx
0x180016847  mov     [rax+10h], rdx
0x18001684b  push    rbp
0x18001684c  push    rsi
0x18001684d  push    rdi
0x18001684e  sub     rsp, 50h
0x180016852  mov     esi, r8d
0x180016855  mov     rdi, rdx
0x180016858  mov     rbx, rcx
0x18001685b  mov     [rsp+68h+var_40], rdx
0x180016860  xorps   xmm0, xmm0
0x180016863  movups  xmmword ptr [rax-40h], xmm0
0x180016867  lea     rbp, [rcx+20h]
0x18001686b  mov     [rax-40h], rbp
0x18001686f  mov     byte ptr [rax-38h], 1
0x180016873  mov     rcx, rbp; _Smtx_t *
0x180016876  call    _Smtx_lock_shared
0x18001687b  nop
0x18001687c  mov     rdx, [rbx+28h]
0x180016880  mov     r8, [rdx+8]
0x180016884  xor     eax, eax
0x180016886  mov     [rsp+68h+var_24], eax
0x18001688a  mov     rcx, rdx
0x18001688d  cmp     [r8+19h], al
0x180016891  jnz     short loc_1800168AD
0x180016893  cmp     [r8+20h], esi
0x180016897  cmovnb  rcx, r8
0x18001689b  lea     rax, [r8+10h]
0x18001689f  cmovnb  rax, r8
0x1800168a3  mov     r8, [rax]
0x1800168a6  cmp     byte ptr [r8+19h], 0
0x1800168ab  jz      short loc_180016893
0x1800168ad  cmp     byte ptr [rcx+19h], 0
0x1800168b1  jnz     short loc_1800168C1
0x1800168b3  cmp     esi, [rcx+20h]
0x1800168b6  jb      short loc_1800168C1
0x1800168b8  cmp     rcx, rdx
0x1800168bb  jz      short loc_1800168C4
0x1800168bd  xor     al, al
0x1800168bf  jmp     short loc_1800168C6
0x1800168c1  mov     rcx, rdx
0x1800168c4  mov     al, 1
0x1800168c6  mov     r10, [rsp+68h]
0x1800168cb  test    al, al
0x1800168cd  jnz     short loc_180016915
0x1800168cf  mov     qword ptr [rdi], 0
0x1800168d6  mov     qword ptr [rdi+8], 0
0x1800168de  mov     rax, [rcx+30h]
0x1800168e2  test    rax, rax
0x1800168e5  jz      short loc_1800168EB
0x1800168e7  lock inc dword ptr [rax+8]
0x1800168eb  mov     rdx, [rcx+28h]
0x1800168ef  mov     [rdi], rdx
0x1800168f2  mov     rdx, [rcx+30h]
0x1800168f6  mov     [rdi+8], rdx
0x1800168fa  mov     rcx, rbp; _Smtx_t *
0x1800168fd  call    _Smtx_unlock_shared
0x180016902  mov     rax, rdi
0x180016905  mov     rbx, [rsp+68h+arg_10]
0x18001690d  add     rsp, 50h
0x180016911  pop     rdi
0x180016912  pop     rsi
0x180016913  pop     rbp
0x180016914  retn
0x180016915  mov     r9d, 8000FFFFh; char *
0x18001691b  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180016922  mov     edx, 56Ch; void *
0x180016927  mov     rcx, r10; this
0x18001692a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
