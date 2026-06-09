# CSpNGramRule::GetRuntimeHeader(CSpCfgData *,ulong,SPNGRAMRUNTIMEHEADER *)

- ea: `0x1800d4b58`
- end: `0x1800d4c5d`
- name: `?GetRuntimeHeader@CSpNGramRule@@AEAAJPEAVCSpCfgData@@KPEAUSPNGRAMRUNTIMEHEADER@@@Z`
- size: `261`
- prototype: `int(CSpNGramRule *__hidden this, struct CSpCfgData *, unsigned int, struct SPNGRAMRUNTIMEHEADER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d3e48`

## callees

- `0x1800d4a2c`
- `0x1800d4b58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d4bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d4bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d4c12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d4c12`

## pseudocode

```c
__int64 __fastcall CSpNGramRule::GetRuntimeHeader(
        CSpNGramRule *this,
        struct CSpCfgData *a2,
        unsigned int a3,
        struct SPNGRAMRUNTIMEHEADER *a4)
{
  __int64 v4; // rdi
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  void *v11; // rcx
  SIZE_T v12; // rcx
  LPVOID v13; // rax
  __int64 v15; // rdx
  int i; // r8d
  _BYTE v17[16]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v18; // [rsp+30h] [rbp-18h]

  v4 = *((_QWORD *)a2 + 28);
  v18 = 0;
  CSpCfgData::GetRuleDataByIndex(a2, a3, (struct SPRULEDATA *)v17);
  v6 = v4 + HIDWORD(v18);
  v7 = 0;
  *(_OWORD *)((char *)this + 8) = *(_OWORD *)v6;
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)(v6 + 16);
  *(_OWORD *)((char *)this + 40) = *(_OWORD *)(v6 + 32);
  *(_OWORD *)((char *)this + 56) = *(_OWORD *)(v6 + 48);
  *((_DWORD *)this + 18) = *(_DWORD *)(v6 + 64);
  do
  {
    *((_QWORD *)this + v7 + 10) = v4 + *((unsigned int *)this + v7 + 3);
    ++v7;
  }
  while ( v7 != 4 );
  v8 = *((unsigned int *)this + 16);
  *((_QWORD *)this + 14) = v6 + 68;
  v9 = v6 + 68 + v8;
  v10 = v9 + *((unsigned int *)this + 17);
  *((_QWORD *)this + 16) = v9;
  v11 = (void *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 17) = v10;
  CoTaskMemFree(v11);
  v12 = 4LL * *((unsigned __int8 *)this + 36);
  *((_QWORD *)this + 15) = 0;
  v13 = CoTaskMemAlloc(v12);
  *((_QWORD *)this + 15) = v13;
  if ( !v13 )
    return 2147942414LL;
  v15 = 0;
  for ( i = 1; (unsigned int)v15 < *((unsigned __int8 *)this + 36); v15 = (unsigned int)(v15 + 1) )
  {
    *(_DWORD *)(*((_QWORD *)this + 15) + 4 * v15) = i;
    i += *(_DWORD *)(*((_QWORD *)this + 14) + 4 * v15);
  }
  return 0;
}

```

## disassembly

```asm
0x1800d4b58  mov     [rsp+arg_0], rbx
0x1800d4b5d  push    rdi
0x1800d4b5e  sub     rsp, 40h
0x1800d4b62  mov     rdi, [rdx+0E0h]
0x1800d4b69  mov     eax, r8d
0x1800d4b6c  mov     r9, rdx
0x1800d4b6f  lea     r8, [rsp+48h+var_28]; struct SPRULEDATA *
0x1800d4b74  mov     rbx, rcx
0x1800d4b77  xorps   xmm0, xmm0
0x1800d4b7a  mov     edx, eax; unsigned int
0x1800d4b7c  mov     rcx, r9; this
0x1800d4b7f  movups  [rsp+48h+var_18], xmm0
0x1800d4b84  call    ?GetRuleDataByIndex@CSpCfgData@@QEAAXKPEAUSPRULEDATA@@@Z; CSpCfgData::GetRuleDataByIndex(ulong,SPRULEDATA *)
0x1800d4b89  mov     r8d, dword ptr [rsp+48h+var_18+0Ch]
0x1800d4b8e  add     r8, rdi
0x1800d4b91  xor     ecx, ecx
0x1800d4b93  movups  xmm0, xmmword ptr [r8]
0x1800d4b97  movups  xmmword ptr [rbx+8], xmm0
0x1800d4b9b  movups  xmm1, xmmword ptr [r8+10h]
0x1800d4ba0  movups  xmmword ptr [rbx+18h], xmm1
0x1800d4ba4  movups  xmm0, xmmword ptr [r8+20h]
0x1800d4ba9  movups  xmmword ptr [rbx+28h], xmm0
0x1800d4bad  movups  xmm1, xmmword ptr [r8+30h]
0x1800d4bb2  movups  xmmword ptr [rbx+38h], xmm1
0x1800d4bb6  mov     eax, [r8+40h]
0x1800d4bba  mov     [rbx+48h], eax
0x1800d4bbd  mov     eax, [rbx+rcx*4+0Ch]
0x1800d4bc1  add     rax, rdi
0x1800d4bc4  mov     [rbx+rcx*8+50h], rax
0x1800d4bc9  inc     rcx
0x1800d4bcc  cmp     rcx, 4
0x1800d4bd0  jnz     short loc_1800D4BBD
0x1800d4bd2  mov     ecx, [rbx+40h]
0x1800d4bd5  lea     rax, [r8+44h]
0x1800d4bd9  mov     [rbx+70h], rax
0x1800d4bdd  add     r8, 44h ; 'D'
0x1800d4be1  mov     eax, [rbx+44h]
0x1800d4be4  add     rcx, r8
0x1800d4be7  add     rax, rcx
0x1800d4bea  mov     [rbx+80h], rcx
0x1800d4bf1  mov     rcx, [rbx+78h]; pv
0x1800d4bf5  mov     [rbx+88h], rax
0x1800d4bfc  call    cs:__imp_CoTaskMemFree
0x1800d4c02  movzx   ecx, byte ptr [rbx+24h]
0x1800d4c06  shl     rcx, 2; cb
0x1800d4c0a  mov     qword ptr [rbx+78h], 0
0x1800d4c12  call    cs:__imp_CoTaskMemAlloc
0x1800d4c18  mov     [rbx+78h], rax
0x1800d4c1c  test    rax, rax
0x1800d4c1f  jnz     short loc_1800D4C28
0x1800d4c21  mov     eax, 8007000Eh
0x1800d4c26  jmp     short loc_1800D4C52
0x1800d4c28  movzx   eax, byte ptr [rbx+24h]
0x1800d4c2c  xor     edx, edx
0x1800d4c2e  lea     r8d, [rdx+1]
0x1800d4c32  test    eax, eax
0x1800d4c34  jz      short loc_1800D4C50
0x1800d4c36  mov     rax, [rbx+78h]
0x1800d4c3a  mov     [rax+rdx*4], r8d
0x1800d4c3e  mov     rax, [rbx+70h]
0x1800d4c42  add     r8d, [rax+rdx*4]
0x1800d4c46  inc     edx
0x1800d4c48  movzx   eax, byte ptr [rbx+24h]
0x1800d4c4c  cmp     edx, eax
0x1800d4c4e  jb      short loc_1800D4C36
0x1800d4c50  xor     eax, eax
0x1800d4c52  mov     rbx, [rsp+48h+arg_0]
0x1800d4c57  add     rsp, 40h
0x1800d4c5b  pop     rdi
0x1800d4c5c  retn
```
