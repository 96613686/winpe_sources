# CLatticeWrapper::PackageAlternates(ulong *)

- ea: `0x18007afec`
- end: `0x18007b152`
- name: `?PackageAlternates@CLatticeWrapper@@IEAAPEAUtagSPPHRASEALT@@PEAK@Z`
- size: `358`
- prototype: `struct tagSPPHRASEALT *__fastcall(CLatticeWrapper *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180077e44`

## callees

- `0x18007afec`
- `0x180082b8c`
- `0x180083dfc`
- `0x180084764`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b03b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b03b`

## pseudocode

```c
struct tagSPPHRASEALT *__fastcall CLatticeWrapper::PackageAlternates(CLatticeWrapper *this, unsigned int *a2)
{
  __int64 v2; // rsi
  unsigned int v3; // edi
  __int64 i; // rbx
  struct tagSPPHRASEALT *v7; // rbx
  unsigned int v8; // r14d
  __int16 v9; // r13
  __int64 v10; // r12
  __int64 v11; // rdx
  __int16 v12; // di
  unsigned int v14; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+18h] BYREF

  v2 = *a2;
  v3 = 0;
  v14 = 0;
  for ( i = 0; (unsigned int)i < (unsigned int)v2; i = (unsigned int)(i + 1) )
  {
    if ( (int)CPhrase::UpdatePhraseBuilder(*(CPhrase **)(*((_QWORD *)this + 118) + 8 * i)) < 0 )
      return 0;
  }
  v7 = (struct tagSPPHRASEALT *)CoTaskMemAlloc(40 * v2);
  if ( v7 )
  {
    v8 = 0;
    v9 = *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 116) + 16LL) + 6LL);
    if ( (_DWORD)v2 )
    {
      v10 = 0;
      do
      {
        v15 = 0;
        v11 = v3;
        v7[v11].pPhrase = *(ISpPhraseBuilder **)(*(_QWORD *)(*((_QWORD *)this + 118) + 8 * v10) + 24LL);
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 118) + 8 * v10) + 24LL) = 0;
        v7[v11].ulStartElementInParent = 0;
        v7[v11].cElementsInParent = *(_DWORD *)(*((_QWORD *)this + 116) + 816LL);
        v7[v11].cElementsInAlternate = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 118) + 8 * v10) + 816LL);
        v7[v11].cbAltExtra = 0;
        v7[v11].pvAltExtra = 0;
        v12 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 118) + 8 * v10) + 16LL) + 6LL);
        if ( !ConfirmOrFreeLastCFGAlternate(0, v7, &v14, &v15) && v12 == v9 )
          CPhrase::CheckAndUpdateHomophoneGroupId((CPhrase *)(5LL * v15), &v7[v15], v12);
        v3 = v14;
        ++v8;
        ++v10;
      }
      while ( v8 < (unsigned int)v2 );
    }
    *a2 = v3;
  }
  return v7;
}

```

## disassembly

```asm
0x18007afec  mov     [rsp+arg_0], rbx
0x18007aff1  push    rbp
0x18007aff2  push    rsi
0x18007aff3  push    rdi
0x18007aff4  push    r12
0x18007aff6  push    r13
0x18007aff8  push    r14
0x18007affa  push    r15
0x18007affc  sub     rsp, 20h
0x18007b000  mov     esi, [rdx]
0x18007b002  xor     edi, edi
0x18007b004  mov     [rsp+58h+arg_8], edi
0x18007b008  xor     ebx, ebx
0x18007b00a  mov     r15, rdx
0x18007b00d  mov     rbp, rcx
0x18007b010  cmp     ebx, esi
0x18007b012  jnb     short loc_18007B033
0x18007b014  mov     rcx, [rbp+3B0h]
0x18007b01b  mov     rcx, [rcx+rbx*8]; this
0x18007b01f  call    ?UpdatePhraseBuilder@CPhrase@@QEAAJXZ; CPhrase::UpdatePhraseBuilder(void)
0x18007b024  test    eax, eax
0x18007b026  js      short loc_18007B02C
0x18007b028  inc     ebx
0x18007b02a  jmp     short loc_18007B010
0x18007b02c  xor     ebx, ebx
0x18007b02e  jmp     loc_18007B13A
0x18007b033  lea     rcx, [rsi+rsi*4]
0x18007b037  shl     rcx, 3; cb
0x18007b03b  call    cs:__imp_CoTaskMemAlloc
0x18007b041  mov     rbx, rax
0x18007b044  test    rax, rax
0x18007b047  jz      loc_18007B13A
0x18007b04d  mov     rcx, [rbp+3A0h]
0x18007b054  xor     r14d, r14d
0x18007b057  mov     rdx, [rcx+10h]
0x18007b05b  movzx   r13d, word ptr [rdx+6]
0x18007b060  test    esi, esi
0x18007b062  jz      loc_18007B137
0x18007b068  xor     r12d, r12d
0x18007b06b  mov     eax, edi
0x18007b06d  lea     r9, [rsp+58h+arg_10]; unsigned int *
0x18007b072  lea     r8, [rsp+58h+arg_8]; unsigned int *
0x18007b077  mov     [rsp+58h+arg_10], 0
0x18007b07f  lea     rdx, [rax+rax*4]
0x18007b083  mov     rax, [rbp+3B0h]
0x18007b08a  mov     rcx, [rax+r12*8]
0x18007b08e  mov     rax, [rcx+18h]
0x18007b092  mov     [rbx+rdx*8], rax
0x18007b096  mov     rax, [rbp+3B0h]
0x18007b09d  mov     rcx, [rax+r12*8]
0x18007b0a1  mov     qword ptr [rcx+18h], 0
0x18007b0a9  mov     dword ptr [rbx+rdx*8+8], 0
0x18007b0b1  mov     rax, [rbp+3A0h]
0x18007b0b8  mov     ecx, [rax+330h]
0x18007b0be  mov     [rbx+rdx*8+0Ch], ecx
0x18007b0c2  mov     rax, [rbp+3B0h]
0x18007b0c9  mov     rcx, [rax+r12*8]
0x18007b0cd  mov     eax, [rcx+330h]
0x18007b0d3  mov     [rbx+rdx*8+10h], eax
0x18007b0d7  mov     dword ptr [rbx+rdx*8+20h], 0
0x18007b0df  mov     qword ptr [rbx+rdx*8+18h], 0
0x18007b0e8  mov     rdx, rbx; struct tagSPPHRASEALT *
0x18007b0eb  mov     rax, [rbp+3B0h]
0x18007b0f2  mov     rcx, [rax+r12*8]
0x18007b0f6  mov     rax, [rcx+10h]
0x18007b0fa  xor     ecx, ecx; struct tagSPPHRASEALTREQUEST *
0x18007b0fc  movzx   edi, word ptr [rax+6]
0x18007b100  call    ?ConfirmOrFreeLastCFGAlternate@@YA_NPEAUtagSPPHRASEALTREQUEST@@PEAUtagSPPHRASEALT@@PEAK2@Z; ConfirmOrFreeLastCFGAlternate(tagSPPHRASEALTREQUEST *,tagSPPHRASEALT *,ulong *,ulong *)
0x18007b105  test    al, al
0x18007b107  jnz     short loc_18007B124
0x18007b109  cmp     di, r13w
0x18007b10d  jnz     short loc_18007B124
0x18007b10f  mov     eax, [rsp+58h+arg_10]
0x18007b113  movzx   r8d, di; unsigned __int16
0x18007b117  lea     rcx, [rax+rax*4]; this
0x18007b11b  lea     rdx, [rbx+rcx*8]; struct tagSPPHRASEALT *
0x18007b11f  call    ?CheckAndUpdateHomophoneGroupId@CPhrase@@QEAAJPEAUtagSPPHRASEALT@@G@Z; CPhrase::CheckAndUpdateHomophoneGroupId(tagSPPHRASEALT *,ushort)
0x18007b124  mov     edi, [rsp+58h+arg_8]
0x18007b128  inc     r14d
0x18007b12b  inc     r12
0x18007b12e  cmp     r14d, esi
0x18007b131  jb      loc_18007B06B
0x18007b137  mov     [r15], edi
0x18007b13a  mov     rax, rbx
0x18007b13d  mov     rbx, [rsp+58h+arg_0]
0x18007b142  add     rsp, 20h
0x18007b146  pop     r15
0x18007b148  pop     r14
0x18007b14a  pop     r13
0x18007b14c  pop     r12
0x18007b14e  pop     rdi
0x18007b14f  pop     rsi
0x18007b150  pop     rbp
0x18007b151  retn
```
