# __FrameHandler3::GetEstablisherFrame(unsigned __int64 *,_xDISPATCHER_CONTEXT *,_s_FuncInfo const *,unsigned __int64 *)

- ea: `0x180011014`
- end: `0x180011104`
- name: `?GetEstablisherFrame@__FrameHandler3@@SAPEA_KPEA_KPEAU_xDISPATCHER_CONTEXT@@PEBU_s_FuncInfo@@0@Z`
- size: `240`
- prototype: `static unsigned __int64 *(unsigned __int64 *, struct _xDISPATCHER_CONTEXT *, const struct _s_FuncInfo *, unsigned __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180010f68`
- `0x180012188`
- `0x1800121d4`
- `0x180012924`
- `0x180012aec`
- `0x180014fd4`

## callees

- `0x180011014`
- `0x180012220`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18001108c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18001108c`

## pseudocode

```c
unsigned __int64 *__fastcall __FrameHandler3::GetEstablisherFrame(
        unsigned __int64 *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        const struct _s_FuncInfo *a3,
        unsigned __int64 *a4)
{
  unsigned int nTryBlocks; // ebp
  int v9; // r14d
  __int64 v10; // rdi
  __int64 v11; // rbx
  PRUNTIME_FUNCTION v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // r8
  unsigned int v15; // r9d
  _DWORD *v16; // rdx
  unsigned __int64 ImageBase; // [rsp+50h] [rbp+8h] BYREF

  nTryBlocks = a3->nTryBlocks;
  ImageBase = 0;
  v9 = __FrameHandler3::StateFromControlPc(a3, a2);
  *a4 = *a1;
  while ( nTryBlocks )
  {
    v10 = a2->ImageBase;
    v11 = a3->dispTryBlockMap + 20LL * --nTryBlocks;
    if ( v9 > *(_DWORD *)(v11 + v10 + 4) && v9 <= *(_DWORD *)(v11 + v10 + 8) )
    {
      v12 = RtlLookupFunctionEntry(a2->ControlPc, &ImageBase, 0);
      v13 = 0;
      v14 = ImageBase + *(int *)(v11 + v10 + 16);
      v15 = *(_DWORD *)(v11 + v10 + 12);
      if ( v15 )
      {
        v16 = (_DWORD *)(v14 + 12);
        while ( *v16 != (unsigned __int64)v12->BeginAddress )
        {
          v13 = (unsigned int)(v13 + 1);
          v16 += 5;
          if ( (unsigned int)v13 >= v15 )
            goto LABEL_8;
        }
LABEL_11:
        _mm_lfence();
        *a4 = *(_QWORD *)(*(int *)(v14 + 20 * v13 + 16) + *a1);
        return a4;
      }
LABEL_8:
      if ( (unsigned int)v13 < v15 )
        goto LABEL_11;
    }
  }
  return a4;
}

```

## disassembly

```asm
0x180011014  mov     rax, rsp
0x180011017  mov     [rax+10h], rbx
0x18001101b  mov     [rax+18h], rbp
0x18001101f  mov     [rax+20h], rsi
0x180011023  push    rdi
0x180011024  push    r12
0x180011026  push    r13
0x180011028  push    r14
0x18001102a  push    r15
0x18001102c  sub     rsp, 20h
0x180011030  mov     ebp, [r8+0Ch]
0x180011034  mov     r13, rcx
0x180011037  mov     rcx, r8; struct _s_FuncInfo *
0x18001103a  mov     qword ptr [rax+8], 0
0x180011042  mov     rsi, r9
0x180011045  mov     r15, r8
0x180011048  mov     r12, rdx
0x18001104b  call    ?StateFromControlPc@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@@Z; __FrameHandler3::StateFromControlPc(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *)
0x180011050  mov     r10, [r13+0]
0x180011054  mov     r14d, eax
0x180011057  mov     [rsi], r10
0x18001105a  jmp     short loc_1800110C7
0x18001105c  movsxd  rax, dword ptr [r15+10h]
0x180011060  lea     ecx, [rbp-1]
0x180011063  mov     rdi, [r12+8]
0x180011068  lea     rdx, [rcx+rcx*4]
0x18001106c  mov     ebp, ecx
0x18001106e  lea     rbx, [rax+rdx*4]
0x180011072  cmp     r14d, [rbx+rdi+4]
0x180011077  jle     short loc_1800110C7
0x180011079  cmp     r14d, [rbx+rdi+8]
0x18001107e  jg      short loc_1800110C7
0x180011080  mov     rcx, [r12]; ControlPc
0x180011084  lea     rdx, [rsp+48h+ImageBase]; ImageBase
0x180011089  xor     r8d, r8d; HistoryTable
0x18001108c  call    cs:__imp_RtlLookupFunctionEntry
0x180011092  movsxd  r8, dword ptr [rbx+rdi+10h]
0x180011097  xor     ecx, ecx
0x180011099  add     r8, [rsp+48h+ImageBase]
0x18001109e  mov     r9d, [rbx+rdi+0Ch]
0x1800110a3  mov     r10d, [rax]
0x1800110a6  test    r9d, r9d
0x1800110a9  jz      short loc_1800110C2
0x1800110ab  lea     rdx, [r8+0Ch]
0x1800110af  movsxd  rax, dword ptr [rdx]
0x1800110b2  cmp     rax, r10
0x1800110b5  jz      short loc_1800110CD
0x1800110b7  inc     ecx
0x1800110b9  add     rdx, 14h
0x1800110bd  cmp     ecx, r9d
0x1800110c0  jb      short loc_1800110AF
0x1800110c2  cmp     ecx, r9d
0x1800110c5  jb      short loc_1800110CD
0x1800110c7  test    ebp, ebp
0x1800110c9  jnz     short loc_18001105C
0x1800110cb  jmp     short loc_1800110E4
0x1800110cd  lfence
0x1800110d0  mov     rax, [r13+0]
0x1800110d4  lea     rcx, [rcx+rcx*4]
0x1800110d8  movsxd  rcx, dword ptr [r8+rcx*4+10h]
0x1800110dd  mov     rcx, [rcx+rax]
0x1800110e1  mov     [rsi], rcx
0x1800110e4  mov     rbx, [rsp+48h+arg_8]
0x1800110e9  mov     rax, rsi
0x1800110ec  mov     rsi, [rsp+48h+arg_18]
0x1800110f1  mov     rbp, [rsp+48h+arg_10]
0x1800110f6  add     rsp, 20h
0x1800110fa  pop     r15
0x1800110fc  pop     r14
0x1800110fe  pop     r13
0x180011100  pop     r12
0x180011102  pop     rdi
0x180011103  retn
```
