# __FrameHandler3::GetEstablisherFrame(unsigned __int64 *,_xDISPATCHER_CONTEXT *,_s_FuncInfo const *,unsigned __int64 *)

- ea: `0x180010fc4`
- end: `0x1800110b4`
- name: `?GetEstablisherFrame@__FrameHandler3@@SAPEA_KPEA_KPEAU_xDISPATCHER_CONTEXT@@PEBU_s_FuncInfo@@0@Z`
- size: `240`
- prototype: `unsigned __int64 *__fastcall(unsigned __int64 *, struct _xDISPATCHER_CONTEXT *, const struct _s_FuncInfo *, unsigned __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180010f18`
- `0x180012138`
- `0x180012184`
- `0x1800128d4`
- `0x180012a9c`
- `0x180014f84`

## callees

- `0x180010fc4`
- `0x1800121d0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18001103c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18001103c`

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
0x180010fc4  mov     rax, rsp
0x180010fc7  mov     [rax+10h], rbx
0x180010fcb  mov     [rax+18h], rbp
0x180010fcf  mov     [rax+20h], rsi
0x180010fd3  push    rdi
0x180010fd4  push    r12
0x180010fd6  push    r13
0x180010fd8  push    r14
0x180010fda  push    r15
0x180010fdc  sub     rsp, 20h
0x180010fe0  mov     ebp, [r8+0Ch]
0x180010fe4  mov     r13, rcx
0x180010fe7  mov     rcx, r8; struct _s_FuncInfo *
0x180010fea  mov     qword ptr [rax+8], 0
0x180010ff2  mov     rsi, r9
0x180010ff5  mov     r15, r8
0x180010ff8  mov     r12, rdx
0x180010ffb  call    ?StateFromControlPc@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@@Z; __FrameHandler3::StateFromControlPc(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *)
0x180011000  mov     r10, [r13+0]
0x180011004  mov     r14d, eax
0x180011007  mov     [rsi], r10
0x18001100a  jmp     short loc_180011077
0x18001100c  movsxd  rax, dword ptr [r15+10h]
0x180011010  lea     ecx, [rbp-1]
0x180011013  mov     rdi, [r12+8]
0x180011018  lea     rdx, [rcx+rcx*4]
0x18001101c  mov     ebp, ecx
0x18001101e  lea     rbx, [rax+rdx*4]
0x180011022  cmp     r14d, [rbx+rdi+4]
0x180011027  jle     short loc_180011077
0x180011029  cmp     r14d, [rbx+rdi+8]
0x18001102e  jg      short loc_180011077
0x180011030  mov     rcx, [r12]; ControlPc
0x180011034  lea     rdx, [rsp+48h+ImageBase]; ImageBase
0x180011039  xor     r8d, r8d; HistoryTable
0x18001103c  call    cs:__imp_RtlLookupFunctionEntry
0x180011042  movsxd  r8, dword ptr [rbx+rdi+10h]
0x180011047  xor     ecx, ecx
0x180011049  add     r8, [rsp+48h+ImageBase]
0x18001104e  mov     r9d, [rbx+rdi+0Ch]
0x180011053  mov     r10d, [rax]
0x180011056  test    r9d, r9d
0x180011059  jz      short loc_180011072
0x18001105b  lea     rdx, [r8+0Ch]
0x18001105f  movsxd  rax, dword ptr [rdx]
0x180011062  cmp     rax, r10
0x180011065  jz      short loc_18001107D
0x180011067  inc     ecx
0x180011069  add     rdx, 14h
0x18001106d  cmp     ecx, r9d
0x180011070  jb      short loc_18001105F
0x180011072  cmp     ecx, r9d
0x180011075  jb      short loc_18001107D
0x180011077  test    ebp, ebp
0x180011079  jnz     short loc_18001100C
0x18001107b  jmp     short loc_180011094
0x18001107d  lfence
0x180011080  mov     rax, [r13+0]
0x180011084  lea     rcx, [rcx+rcx*4]
0x180011088  movsxd  rcx, dword ptr [r8+rcx*4+10h]
0x18001108d  mov     rcx, [rcx+rax]
0x180011091  mov     [rsi], rcx
0x180011094  mov     rbx, [rsp+48h+arg_8]
0x180011099  mov     rax, rsi
0x18001109c  mov     rsi, [rsp+48h+arg_18]
0x1800110a1  mov     rbp, [rsp+48h+arg_10]
0x1800110a6  add     rsp, 20h
0x1800110aa  pop     r15
0x1800110ac  pop     r14
0x1800110ae  pop     r13
0x1800110b0  pop     r12
0x1800110b2  pop     rdi
0x1800110b3  retn
```
