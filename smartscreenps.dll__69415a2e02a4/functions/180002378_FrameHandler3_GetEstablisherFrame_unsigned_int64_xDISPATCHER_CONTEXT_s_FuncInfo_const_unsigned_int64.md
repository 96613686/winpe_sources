# __FrameHandler3::GetEstablisherFrame(unsigned __int64 *,_xDISPATCHER_CONTEXT *,_s_FuncInfo const *,unsigned __int64 *)

- ea: `0x180002378`
- end: `0x18000244a`
- name: `?GetEstablisherFrame@__FrameHandler3@@SAPEA_KPEA_KPEAU_xDISPATCHER_CONTEXT@@PEBU_s_FuncInfo@@0@Z`
- size: `210`
- prototype: `static unsigned __int64 *(unsigned __int64 *, struct _xDISPATCHER_CONTEXT *, const struct _s_FuncInfo *, unsigned __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800022cc`
- `0x18000356c`
- `0x1800035b8`
- `0x180003c80`
- `0x180003e48`
- `0x180006214`

## callees

- `0x180002378`
- `0x180003604`

## import_xrefs

- `ntdll!RtlLookupFunctionEntry` at `0x1800023e0`
- `ntdll!RtlLookupFunctionEntry` at `0x1800023e0`

## pseudocode

```c
unsigned __int64 *__fastcall __FrameHandler3::GetEstablisherFrame(
        unsigned __int64 *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        const struct _s_FuncInfo *a3,
        unsigned __int64 *a4)
{
  __int64 v4; // rbx
  int v9; // ebp
  __int64 v10; // rsi
  __int64 v11; // rdi
  PRUNTIME_FUNCTION v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // r9
  unsigned int v15; // r8d
  unsigned __int64 ImageBase; // [rsp+70h] [rbp+8h] BYREF

  LODWORD(v4) = a3->nTryBlocks;
  ImageBase = 0;
  v9 = __FrameHandler3::StateFromControlPc(a3, a2);
  *a4 = *a1;
  while ( (_DWORD)v4 )
  {
    v4 = (unsigned int)(v4 - 1);
    v10 = a2->ImageBase;
    v11 = a3->dispTryBlockMap + 20 * v4;
    if ( v9 > *(_DWORD *)(v11 + v10 + 4) && v9 <= *(_DWORD *)(v11 + v10 + 8) )
    {
      v12 = RtlLookupFunctionEntry(a2->ControlPc, &ImageBase, 0);
      v13 = 0;
      v14 = ImageBase + *(int *)(v11 + v10 + 16);
      v15 = *(_DWORD *)(v11 + v10 + 12);
      if ( v15 )
      {
        while ( *(_DWORD *)(v14 + 20 * v13 + 12) != (unsigned __int64)v12->BeginAddress )
        {
          v13 = (unsigned int)(v13 + 1);
          if ( (unsigned int)v13 >= v15 )
            goto LABEL_7;
        }
LABEL_10:
        _mm_lfence();
        *a4 = *(_QWORD *)(*(int *)(v14 + 20 * v13 + 16) + *a1);
        return a4;
      }
LABEL_7:
      if ( (unsigned int)v13 < v15 )
        goto LABEL_10;
    }
  }
  return a4;
}

```

## disassembly

```asm
0x180002378  push    rbx
0x18000237a  push    rbp
0x18000237b  push    rsi
0x18000237c  push    rdi
0x18000237d  push    r12
0x18000237f  push    r13
0x180002381  push    r14
0x180002383  push    r15
0x180002385  sub     rsp, 28h
0x180002389  mov     ebx, [r8+0Ch]
0x18000238d  mov     r13, rcx
0x180002390  mov     rcx, r8; struct _s_FuncInfo *
0x180002393  mov     [rsp+68h+ImageBase], 0
0x18000239c  mov     r14, r9
0x18000239f  mov     r15, r8
0x1800023a2  mov     r12, rdx
0x1800023a5  call    ?StateFromControlPc@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@@Z; __FrameHandler3::StateFromControlPc(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *)
0x1800023aa  mov     r10, [r13+0]
0x1800023ae  mov     ebp, eax
0x1800023b0  mov     [r14], r10
0x1800023b3  jmp     short loc_180002419
0x1800023b5  movsxd  rax, dword ptr [r15+10h]
0x1800023b9  dec     ebx
0x1800023bb  mov     rsi, [r12+8]
0x1800023c0  lea     rdx, [rbx+rbx*4]
0x1800023c4  lea     rdi, [rax+rdx*4]
0x1800023c8  cmp     ebp, [rdi+rsi+4]
0x1800023cc  jle     short loc_180002419
0x1800023ce  cmp     ebp, [rdi+rsi+8]
0x1800023d2  jg      short loc_180002419
0x1800023d4  mov     rcx, [r12]; ControlPc
0x1800023d8  lea     rdx, [rsp+68h+ImageBase]; ImageBase
0x1800023dd  xor     r8d, r8d; HistoryTable
0x1800023e0  call    cs:__imp_RtlLookupFunctionEntry
0x1800023e6  movsxd  r9, dword ptr [rdi+rsi+10h]
0x1800023eb  xor     edx, edx
0x1800023ed  add     r9, [rsp+68h+ImageBase]
0x1800023f2  mov     r8d, [rdi+rsi+0Ch]
0x1800023f7  mov     r10d, [rax]
0x1800023fa  test    r8d, r8d
0x1800023fd  jz      short loc_180002414
0x1800023ff  lea     rcx, [rdx+rdx*4]
0x180002403  movsxd  rax, dword ptr [r9+rcx*4+0Ch]
0x180002408  cmp     rax, r10
0x18000240b  jz      short loc_18000241F
0x18000240d  inc     edx
0x18000240f  cmp     edx, r8d
0x180002412  jb      short loc_1800023FF
0x180002414  cmp     edx, r8d
0x180002417  jb      short loc_18000241F
0x180002419  test    ebx, ebx
0x18000241b  jnz     short loc_1800023B5
0x18000241d  jmp     short loc_180002436
0x18000241f  lfence
0x180002422  mov     rax, [r13+0]
0x180002426  lea     rcx, [rdx+rdx*4]
0x18000242a  movsxd  rcx, dword ptr [r9+rcx*4+10h]
0x18000242f  mov     rcx, [rcx+rax]
0x180002433  mov     [r14], rcx
0x180002436  mov     rax, r14
0x180002439  add     rsp, 28h
0x18000243d  pop     r15
0x18000243f  pop     r14
0x180002441  pop     r13
0x180002443  pop     r12
0x180002445  pop     rdi
0x180002446  pop     rsi
0x180002447  pop     rbp
0x180002448  pop     rbx
0x180002449  retn
```
