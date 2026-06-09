# Smb2ContinueUncachedRead

- ea: `0x1400041a0`
- end: `0x140004550`
- name: `Smb2ContinueUncachedRead`
- size: `944`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004060`
- `0x14007f510`
- `0x140080114`

## callees

- `0x1400041a0`
- `0x140004560`
- `0x140004960`
- `0x140005070`
- `0x140007400`
- `0x140007900`
- `0x140008190`
- `0x14000a100`
- `0x140015354`
- `0x140017c10`
- `0x1400222ec`
- `0x140022958`
- `0x140038980`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140004354`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400043b7`
- `ntoskrnl!IoBuildPartialMdl` at `0x140004354`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400043b7`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140004472`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140004472`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a41e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a41e`
- `ntoskrnl!MmUnmapLockedPages` at `0x140004513`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000453f`
- `ntoskrnl!MmUnmapLockedPages` at `0x140004513`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000453f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000448e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000448e`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a45e`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a4c9`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a45e`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14003a4c9`

## string_xrefs

- `0x140004453`: `Srv2PostToThreadPool`
- `0x140004246`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`

## pseudocode

```c
PSLIST_ENTRY __fastcall Smb2ContinueUncachedRead(__int64 a1)
{
  __int64 v2; // rbp
  __int64 v3; // rsi
  __int64 v4; // rax
  int v5; // r14d
  ULONG v6; // ebx
  PSLIST_ENTRY result; // rax
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned __int8 v10; // cl
  unsigned __int8 v11; // al
  __int64 v12; // rax
  ULONG v13; // r15d
  __int64 v14; // r14
  void *v15; // r12
  struct _MDL *v16; // r13
  _QWORD *v17; // rax
  __int64 v18; // rcx
  void *v19; // r15
  __int64 v20; // r14
  struct _MDL *v21; // r12
  __int64 (__fastcall *v22)(_QWORD); // rdx
  __int64 v23; // rbx
  __int64 v24; // rbx
  __int64 v25; // rcx
  int GenericIrpExtension; // eax
  bool v27; // zf
  unsigned int v28; // eax
  unsigned int v29; // esi
  __int64 ExtendedErrorBuffer; // rbx
  __int64 v31; // rcx
  __int16 v32; // kr00_2
  char v33; // cl
  int v34; // [rsp+80h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 312) + 24LL);
  v4 = *(_QWORD *)(a1 + 120);
  v5 = *(_DWORD *)(v4 + 48);
  v6 = *(_DWORD *)(v4 + 56);
  if ( !Smb2EnableInlineSendIOCompletion || v5 >= 0 && v6 >= *(_DWORD *)(v2 + 240) || !KeGetCurrentIrql() )
  {
    Smb2SequentialReadComplete(a1);
    if ( (*(_BYTE *)(v2 + 264) & 0xC) != 0 )
    {
      result = (PSLIST_ENTRY)Srv2MarkWorkItemComplete(a1, Smb2ContinueUncachedRead);
      v5 = (int)result;
      if ( (_DWORD)result == 259 )
        return result;
    }
    if ( (int)(v5 + 0x80000000) < 0 || v5 == -2147483643 )
    {
      if ( v6 >= *(_DWORD *)(v2 + 240) )
      {
        v10 = 80;
        if ( v6 > *(_DWORD *)(v2 + 244) )
          v6 = *(_DWORD *)(v2 + 244);
        v11 = *(_BYTE *)(v2 + 265);
        *(_DWORD *)(v2 + 248) = v6;
        *(_BYTE *)(v3 + 67) = 0;
        if ( v11 > 0x50u )
          v10 = v11;
        *(_DWORD *)(v3 + 76) = 0;
        *(_BYTE *)(v3 + 66) = v10;
        *(_WORD *)(v3 + 64) = 17;
        if ( *(_QWORD *)(v2 + 216) )
        {
          *(_DWORD *)(v3 + 68) = 0;
          *(_DWORD *)(v3 + 72) = v6;
        }
        else
        {
          *(_DWORD *)(v3 + 68) = v6;
          *(_DWORD *)(v3 + 72) = 0;
          memset((void *)(v3 + 80), 0, v10 - 80LL);
        }
        v12 = *(_QWORD *)(a1 + 312);
        v13 = *(unsigned __int8 *)(v3 + 66);
        v14 = *(_QWORD *)(v12 + 80);
        v15 = *(void **)(v12 + 24);
        v16 = *(struct _MDL **)(v12 + 56);
        if ( (*(_BYTE *)(v14 + 10) & 0x20) != 0 )
          MmUnmapLockedPages(*(PVOID *)(v14 + 24), *(PMDL *)(v12 + 80));
        IoBuildPartialMdl(v16, (PMDL)v14, v15, v13);
        *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 312) + 80LL) + 10LL) |= *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 312)
                                                                                             + 56LL)
                                                                                 + 10LL)
                                                                      & 0x1000;
        v17 = *(_QWORD **)(v2 + 160);
        v18 = *(unsigned int *)(v2 + 256);
        v19 = (void *)v17[3];
        v20 = v17[10];
        v21 = (struct _MDL *)v17[7];
        if ( (_DWORD)v18 )
          v19 = (void *)(-(int)v18 & ((unsigned __int64)v19 + v18 - 1));
        if ( (*(_BYTE *)(v20 + 10) & 0x20) != 0 )
          MmUnmapLockedPages(*(PVOID *)(v20 + 24), (PMDL)v20);
        IoBuildPartialMdl(v21, (PMDL)v20, v19, v6);
        **(_QWORD **)(*(_QWORD *)(a1 + 312) + 80LL) = *(_QWORD *)(*(_QWORD *)(v2 + 160) + 80LL);
        Smb2SetSuccess(a1, *(unsigned int *)(*(_QWORD *)(a1 + 120) + 48LL));
        *(_DWORD *)(a1 + 484) |= 4u;
        *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL) = *(_DWORD *)(v3 + 68) + *(unsigned __int8 *)(v3 + 66);
        if ( *(_QWORD *)(v2 + 216) && v6 )
          return (PSLIST_ENTRY)Smb2ContinueReadRdmaTail(a1);
        return (PSLIST_ENTRY)Srv2CompleteWorkItem(a1, 0);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 27, &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
      }
      v8 = 1516;
      v9 = 3221225489LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1, v5);
      }
      if ( **(_BYTE **)(a1 + 64) == 2 )
      {
        v25 = *(_QWORD *)(a1 + 120);
        v34 = 0;
        GenericIrpExtension = IoGetGenericIrpExtension(v25, &v34, 4);
        v27 = GenericIrpExtension < 0 ? GenericIrpExtension == -1073741789 : (v34 & 0x400) == 0;
        if ( v27 )
        {
          v28 = (GenericIrpExtension >> 31) & 0xFFFFFFF8;
          v29 = v28 + 8;
          if ( v28 != -8 )
          {
            ExtendedErrorBuffer = Smb2AllocateExtendedErrorBuffer(a1, 1164730963, v29, 0);
            if ( ExtendedErrorBuffer )
            {
              v31 = *(_QWORD *)(a1 + 120);
              v34 = 0;
              if ( (int)IoGetGenericIrpExtension(v31, &v34, 4) >= 0 && (v34 & 0x400) == 0 )
              {
                if ( (v34 & 0x800) != 0 )
                {
                  v32 = HIWORD(v34);
                  v33 = BYTE1(v34) >> 4;
                }
                else
                {
                  v33 = 0;
                  v32 = 0;
                }
                if ( v29 >= 8 )
                {
                  *(_DWORD *)ExtendedErrorBuffer = 8;
                  *(_BYTE *)(ExtendedErrorBuffer + 4) = v33;
                  *(_WORD *)(ExtendedErrorBuffer + 5) = v32;
                  *(_BYTE *)(ExtendedErrorBuffer + 7) = 0;
                }
              }
            }
          }
        }
      }
      v8 = 1505;
      v9 = (unsigned int)v5;
    }
    Smb2SetError(a1, v9, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c", v8);
    return (PSLIST_ENTRY)Srv2CompleteWorkItem(a1, 0);
  }
  v27 = *(_DWORD *)(a1 + 8) == 5;
  v22 = Smb2ContinueUncachedRead;
  *(_QWORD *)(a1 + 48) = Smb2ContinueUncachedRead;
  *(_DWORD *)(a1 + 72) = 0;
  if ( v27 )
  {
    LOBYTE(v22) = 1;
    SRV2_PERF_ENTER_EX(a1 + 584, v22, 391, "Srv2PostToThreadPool", 1);
  }
  v23 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
  v24 = *(_QWORD *)(v23 + 8LL * KeGetCurrentNodeNumber() + 8);
  result = ExpInterlockedPushEntrySList((PSLIST_HEADER)(v24 + 16), (PSLIST_ENTRY)(a1 + 32));
  if ( !result && *(_WORD *)(v24 + 66) )
    return (PSLIST_ENTRY)RfspThreadPoolNodeWakeIdleWorker(v24);
  return result;
}

```

## disassembly

```asm
0x1400041a0  push    rbx
0x1400041a2  push    rbp
0x1400041a3  push    rsi
0x1400041a4  push    rdi
0x1400041a5  push    r12
0x1400041a7  push    r13
0x1400041a9  push    r14
0x1400041ab  push    r15
0x1400041ad  sub     rsp, 38h
0x1400041b1  mov     rax, [rcx+138h]
0x1400041b8  xor     r15d, r15d
0x1400041bb  cmp     cs:Smb2EnableInlineSendIOCompletion, r15b
0x1400041c2  mov     rdi, rcx
0x1400041c5  mov     rbp, [rcx+230h]
0x1400041cc  mov     rsi, [rax+18h]
0x1400041d0  mov     rax, [rcx+78h]
0x1400041d4  mov     r14d, [rax+30h]
0x1400041d8  mov     ebx, [rax+38h]
0x1400041db  jnz     loc_1400044BE
0x1400041e1  mov     rcx, rdi
0x1400041e4  call    Smb2SequentialReadComplete
0x1400041e9  test    byte ptr [rbp+108h], 0Ch
0x1400041f0  jz      short loc_14000420B
0x1400041f2  lea     rdx, Smb2ContinueUncachedRead
0x1400041f9  mov     rcx, rdi
0x1400041fc  call    Srv2MarkWorkItemComplete
0x140004201  mov     r14d, eax
0x140004204  cmp     eax, 103h
0x140004209  jz      short loc_14000425F
0x14000420b  mov     eax, 80000000h
0x140004210  lea     ecx, [r14+rax]
0x140004214  test    eax, ecx
0x140004216  jz      short loc_140004271
0x140004218  cmp     ebx, [rbp+0F0h]
0x14000421e  jnb     loc_1400042CB
0x140004224  mov     rcx, cs:WPP_GLOBAL_Control
0x14000422b  lea     rax, WPP_GLOBAL_Control
0x140004232  cmp     rcx, rax
0x140004235  jnz     loc_1400044D8
0x14000423b  mov     r9d, 5ECh
0x140004241  mov     edx, 0C0000011h
0x140004246  lea     r8, aOnecoreBaseFsR_9; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14000424d  mov     rcx, rdi
0x140004250  call    _Smb2SetError
0x140004255  xor     edx, edx
0x140004257  mov     rcx, rdi
0x14000425a  call    Srv2CompleteWorkItem
0x14000425f  add     rsp, 38h
0x140004263  pop     r15
0x140004265  pop     r14
0x140004267  pop     r13
0x140004269  pop     r12
0x14000426b  pop     rdi
0x14000426c  pop     rsi
0x14000426d  pop     rbp
0x14000426e  pop     rbx
0x14000426f  retn
0x140004271  cmp     r14d, 80000005h
0x140004278  jz      short loc_140004218
0x14000427a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004281  lea     rax, WPP_GLOBAL_Control
0x140004288  cmp     rcx, rax
0x14000428b  jz      loc_14003A437
0x140004291  test    dword ptr [rcx+2Ch], 800000h
0x140004298  jz      loc_14003A437
0x14000429e  cmp     byte ptr [rcx+29h], 1
0x1400042a2  jb      loc_14003A437
0x1400042a8  mov     rcx, [rcx+18h]
0x1400042ac  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x1400042b3  mov     edx, 1Ah
0x1400042b8  mov     [rsp+78h+var_58], r14d
0x1400042bd  mov     r9, rdi
0x1400042c0  call    WPP_SF_qD
0x1400042c5  nop
0x1400042c6  jmp     loc_14003A437
0x1400042cb  mov     eax, [rbp+0F4h]
0x1400042d1  mov     ecx, 50h ; 'P'
0x1400042d6  cmp     ebx, eax
0x1400042d8  cmova   ebx, eax
0x1400042db  movzx   eax, byte ptr [rbp+109h]
0x1400042e2  mov     [rbp+0F8h], ebx
0x1400042e8  cmp     al, cl
0x1400042ea  mov     [rsi+43h], r15b
0x1400042ee  cmova   ecx, eax
0x1400042f1  mov     [rsi+4Ch], r15d
0x1400042f5  mov     [rsi+42h], cl
0x1400042f8  mov     word ptr [rsi+40h], 11h
0x1400042fe  cmp     [rbp+0D8h], r15
0x140004305  jnz     loc_140004426
0x14000430b  movzx   r8d, cl
0x14000430f  xor     edx, edx; Val
0x140004311  sub     r8, 50h ; 'P'; Size
0x140004315  mov     [rsi+44h], ebx
0x140004318  lea     rcx, [rsi+50h]; void *
0x14000431c  mov     [rsi+48h], r15d
0x140004320  call    memset
0x140004325  mov     rax, [rdi+138h]
0x14000432c  movzx   r15d, byte ptr [rsi+42h]
0x140004331  mov     r14, [rax+50h]
0x140004335  mov     r12, [rax+18h]
0x140004339  mov     r13, [rax+38h]
0x14000433d  test    byte ptr [r14+0Ah], 20h
0x140004342  jnz     loc_14000450C
0x140004348  mov     r9d, r15d; Length
0x14000434b  mov     r8, r12; VirtualAddress
0x14000434e  mov     rdx, r14; TargetMdl
0x140004351  mov     rcx, r13; SourceMdl
0x140004354  call    cs:__imp_IoBuildPartialMdl
0x14000435b  nop     dword ptr [rax+rax+00h]
0x140004360  mov     rax, [rdi+138h]
0x140004367  mov     rdx, [rax+50h]
0x14000436b  mov     rax, [rax+38h]
0x14000436f  movzx   ecx, word ptr [rax+0Ah]
0x140004373  mov     eax, 1000h
0x140004378  and     cx, ax
0x14000437b  or      [rdx+0Ah], cx
0x14000437f  mov     rax, [rbp+0A0h]
0x140004386  mov     ecx, [rbp+100h]
0x14000438c  mov     r15, [rax+18h]
0x140004390  mov     r14, [rax+50h]
0x140004394  mov     r12, [rax+38h]
0x140004398  test    ecx, ecx
0x14000439a  jnz     loc_140004524
0x1400043a0  test    byte ptr [r14+0Ah], 20h
0x1400043a5  jnz     loc_140004538
0x1400043ab  mov     r9d, ebx; Length
0x1400043ae  mov     r8, r15; VirtualAddress
0x1400043b1  mov     rdx, r14; TargetMdl
0x1400043b4  mov     rcx, r12; SourceMdl
0x1400043b7  call    cs:__imp_IoBuildPartialMdl
0x1400043be  nop     dword ptr [rax+rax+00h]
0x1400043c3  mov     rax, [rdi+138h]
0x1400043ca  mov     rdx, [rbp+0A0h]
0x1400043d1  mov     rcx, [rax+50h]
0x1400043d5  mov     rax, [rdx+50h]
0x1400043d9  mov     [rcx], rax
0x1400043dc  mov     rcx, rdi
0x1400043df  mov     rdx, [rdi+78h]
0x1400043e3  mov     edx, [rdx+30h]
0x1400043e6  call    Smb2SetSuccess
0x1400043eb  or      dword ptr [rdi+1E4h], 4
0x1400043f2  movzx   ecx, byte ptr [rsi+42h]
0x1400043f6  add     ecx, [rsi+44h]
0x1400043f9  mov     rax, [rdi+138h]
0x140004400  mov     [rax+24h], ecx
0x140004403  cmp     qword ptr [rbp+0D8h], 0
0x14000440b  jz      loc_140004255
0x140004411  test    ebx, ebx
0x140004413  jz      loc_140004255
0x140004419  mov     rcx, rdi
0x14000441c  call    Smb2ContinueReadRdmaTail
0x140004421  jmp     loc_14000425F
0x140004426  mov     [rsi+44h], r15d
0x14000442a  mov     [rsi+48h], ebx
0x14000442d  jmp     loc_140004325
0x140004432  cmp     dword ptr [rdi+8], 5
0x140004436  lea     rdx, Smb2ContinueUncachedRead
0x14000443d  mov     [rdi+30h], rdx
0x140004441  mov     [rdi+48h], r15d
0x140004445  jnz     short loc_140004467
0x140004447  lea     rcx, [rdi+248h]
0x14000444e  mov     byte ptr [rsp+78h+var_58], 1
0x140004453  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14000445a  mov     r8d, 187h
0x140004460  mov     dl, 1
0x140004462  call    SRV2_PERF_ENTER_EX
0x140004467  mov     rax, [rdi+40h]
0x14000446b  mov     rbx, [rax+88h]
0x140004472  call    cs:__imp_KeGetCurrentNodeNumber
0x140004479  nop     dword ptr [rax+rax+00h]
0x14000447e  movzx   eax, ax
0x140004481  lea     rdx, [rdi+20h]; ListEntry
0x140004485  mov     rbx, [rbx+rax*8+8]
0x14000448a  lea     rcx, [rbx+10h]; ListHead
0x14000448e  call    cs:__imp_ExpInterlockedPushEntrySList
0x140004495  nop     dword ptr [rax+rax+00h]
0x14000449a  test    rax, rax
0x14000449d  jnz     loc_14000425F
0x1400044a3  movzx   edx, word ptr [rbx+42h]
0x1400044a7  cmp     r15w, dx
0x1400044ab  jz      loc_14000425F
0x1400044b1  mov     rcx, rbx
0x1400044b4  call    RfspThreadPoolNodeWakeIdleWorker
0x1400044b9  jmp     loc_14000425F
0x1400044be  test    r14d, r14d
0x1400044c1  js      loc_14003A41E
0x1400044c7  cmp     ebx, [rbp+0F0h]
0x1400044cd  jnb     loc_1400041E1
0x1400044d3  jmp     loc_14003A41E
0x1400044d8  test    dword ptr [rcx+2Ch], 800000h
0x1400044df  jz      loc_14000423B
0x1400044e5  cmp     byte ptr [rcx+29h], 1
0x1400044e9  jb      loc_14000423B
0x1400044ef  mov     rcx, [rcx+18h]
0x1400044f3  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x1400044fa  mov     edx, 1Bh
0x1400044ff  mov     r9, rdi
0x140004502  call    WPP_SF_q
0x140004507  jmp     loc_14000423B
0x14000450c  mov     rcx, [r14+18h]; BaseAddress
0x140004510  mov     rdx, r14; MemoryDescriptorList
0x140004513  call    cs:__imp_MmUnmapLockedPages
0x14000451a  nop     dword ptr [rax+rax+00h]
0x14000451f  jmp     loc_140004348
0x140004524  lea     rax, [rcx-1]
0x140004528  neg     ecx
0x14000452a  add     r15, rax
0x14000452d  movsxd  rax, ecx
0x140004530  and     r15, rax
0x140004533  jmp     loc_1400043A0
0x140004538  mov     rcx, [r14+18h]; BaseAddress
0x14000453c  mov     rdx, r14; MemoryDescriptorList
0x14000453f  call    cs:__imp_MmUnmapLockedPages
0x140004546  nop     dword ptr [rax+rax+00h]
0x14000454b  jmp     loc_1400043AB
0x14003a41e  call    cs:__imp_KeGetCurrentIrql
0x14003a425  nop     dword ptr [rax+rax+00h]
0x14003a42a  test    al, al
0x14003a42c  jz      loc_1400041E1
0x14003a432  jmp     loc_140004432
0x14003a437  mov     rax, [rdi+40h]
0x14003a43b  cmp     byte ptr [rax], 2
0x14003a43e  jnz     loc_14003A51E
0x14003a444  mov     rcx, [rdi+78h]
0x14003a448  lea     rdx, [rsp+78h+arg_0]
0x14003a450  mov     r8d, 4
0x14003a456  mov     [rsp+78h+arg_0], r15d
0x14003a45e  call    cs:__imp_IoGetGenericIrpExtension
0x14003a465  nop     dword ptr [rax+rax+00h]
0x14003a46a  test    eax, eax
0x14003a46c  js      short loc_14003A478
0x14003a46e  test    byte ptr [rsp+78h+arg_0+1], 4
0x14003a476  jmp     short loc_14003A47D
0x14003a478  cmp     eax, 0C0000023h
0x14003a47d  jnz     loc_14003A51E
0x14003a483  sar     eax, 1Fh
0x14003a486  and     eax, 0FFFFFFF8h
0x14003a489  lea     esi, [rax+8]
0x14003a48c  test    esi, esi
0x14003a48e  jz      loc_14003A51E
0x14003a494  xor     r9d, r9d
0x14003a497  mov     r8d, esi
0x14003a49a  mov     edx, 456C6253h
0x14003a49f  mov     rcx, rdi
0x14003a4a2  call    Smb2AllocateExtendedErrorBuffer
0x14003a4a7  mov     rbx, rax
0x14003a4aa  test    rax, rax
0x14003a4ad  jz      short loc_14003A51E
0x14003a4af  mov     rcx, [rdi+78h]
0x14003a4b3  lea     rdx, [rsp+78h+arg_0]
0x14003a4bb  mov     r8d, 4
0x14003a4c1  mov     [rsp+78h+arg_0], r15d
0x14003a4c9  call    cs:__imp_IoGetGenericIrpExtension
0x14003a4d0  nop     dword ptr [rax+rax+00h]
0x14003a4d5  test    eax, eax
0x14003a4d7  js      short loc_14003A51E
0x14003a4d9  mov     cl, byte ptr [rsp+78h+arg_0+1]
0x14003a4e0  test    cl, 4
0x14003a4e3  jnz     short loc_14003A51E
0x14003a4e5  test    cl, 8
0x14003a4e8  jz      short loc_14003A4FD
0x14003a4ea  mov     al, byte ptr [rsp+78h+arg_0+2]
0x14003a4f1  mov     dl, byte ptr [rsp+78h+arg_0+3]
0x14003a4f8  shr     cl, 4
0x14003a4fb  jmp     short loc_14003A506
0x14003a4fd  mov     cl, r15b
0x14003a500  mov     dl, r15b
0x14003a503  mov     al, r15b
0x14003a506  cmp     esi, 8
0x14003a509  jb      short loc_14003A51E
0x14003a50b  mov     dword ptr [rbx], 8
0x14003a511  mov     [rbx+4], cl
0x14003a514  mov     [rbx+5], al
0x14003a517  mov     [rbx+6], dl
0x14003a51a  mov     [rbx+7], r15b
0x14003a51e  mov     r9d, 5E1h
0x14003a524  mov     edx, r14d
0x14003a527  jmp     loc_140004246
```
