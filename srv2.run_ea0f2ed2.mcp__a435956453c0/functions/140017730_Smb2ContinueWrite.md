# Smb2ContinueWrite

- ea: `0x140017730`
- end: `0x140017c03`
- name: `Smb2ContinueWrite`
- size: `1235`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14006c1a0`
- `0x14007e390`
- `0x14007eaa0`

## callees

- `0x140004960`
- `0x140005070`
- `0x140007400`
- `0x140007900`
- `0x140008190`
- `0x140015354`
- `0x140017730`
- `0x140017c10`
- `0x140022958`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400178e7`
- `ntoskrnl!IoFreeMdl` at `0x14001798b`
- `ntoskrnl!IoFreeMdl` at `0x1400178e7`
- `ntoskrnl!IoFreeMdl` at `0x14001798b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140017804`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140017804`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400177b4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400177b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017882`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001793b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017882`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001793b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140017820`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140017820`
- `ntoskrnl!MmUnlockPages` at `0x1400178d8`
- `ntoskrnl!MmUnlockPages` at `0x14001797c`
- `ntoskrnl!MmUnlockPages` at `0x1400178d8`
- `ntoskrnl!MmUnlockPages` at `0x14001797c`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x140017a4d`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x140017aba`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x140017a4d`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x140017aba`

## string_xrefs

- `0x140017b12`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x1400177e5`: `Srv2PostToThreadPool`

## pseudocode

```c
PSLIST_ENTRY __fastcall Smb2ContinueWrite(__int64 a1)
{
  __int64 v1; // r13
  __int64 v2; // rax
  __int64 v4; // rsi
  int v5; // ebx
  PSLIST_ENTRY result; // rax
  int v7; // ebp
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // r15
  __int64 *v13; // r14
  void *v14; // rcx
  __int64 *v15; // r12
  __int64 *v16; // rbx
  struct _MDL *v17; // r14
  CSHORT MdlFlags; // ax
  unsigned int v19; // r15d
  __int64 v20; // r12
  __int64 v21; // r13
  __int64 *v22; // r14
  void *v23; // rcx
  struct _MDL *v24; // rbx
  struct _MDL *v25; // r14
  CSHORT v26; // ax
  __int64 v27; // rax
  int GenericIrpExtension; // eax
  bool v29; // zf
  unsigned int v30; // eax
  unsigned int v31; // esi
  __int64 ExtendedErrorBuffer; // rbx
  __int16 v33; // kr00_2
  char v34; // cl
  __int64 v35; // r9
  unsigned int v36; // r11d
  __int64 v37; // rdx
  __int64 v38; // r8
  int v39; // [rsp+80h] [rbp+8h] BYREF
  __int64 v40; // [rsp+88h] [rbp+10h]
  __int64 v41; // [rsp+90h] [rbp+18h]
  __int64 v42; // [rsp+98h] [rbp+20h]

  v1 = *(_QWORD *)(a1 + 120);
  v2 = *(_QWORD *)(a1 + 312);
  v4 = *(_QWORD *)(a1 + 560);
  v40 = v1;
  v5 = *(_DWORD *)(v1 + 56);
  v29 = (*(_BYTE *)(v4 + 280) & 0x18) == 0;
  v42 = *(_QWORD *)(v2 + 24);
  v39 = v5;
  if ( !v29 )
  {
    result = (PSLIST_ENTRY)Srv2MarkWorkItemComplete(a1, Smb2ContinueWrite);
    if ( (_DWORD)result == 259 )
      return result;
  }
  v7 = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL);
  if ( !Smb2EnableInlineSendIOCompletion || v7 >= 0 || !KeGetCurrentIrql() )
  {
    v11 = *(_DWORD *)(v4 + 272);
    if ( v11 == 1 )
    {
      v12 = *(_QWORD *)(a1 + 120);
      v13 = *(__int64 **)(v4 + 200);
      v14 = *(void **)(v12 + 160);
      v15 = *(__int64 **)(*(_QWORD *)(a1 + 304) + 80LL);
      if ( v14 )
      {
        ExFreePoolWithTag(v14, 0);
        *(_QWORD *)(v12 + 160) = 0;
      }
      v16 = *(__int64 **)(v12 + 8);
      if ( v16 && v16 != v15 && v16 != v13 && (*((_BYTE *)v16 + 10) & 4) == 0 )
      {
        do
        {
          v17 = (struct _MDL *)v16;
          v16 = (__int64 *)*v16;
          MdlFlags = v17->MdlFlags;
          if ( (MdlFlags & 2) != 0 || (MdlFlags & 0x20) != 0 )
            MmUnlockPages(v17);
          IoFreeMdl(v17);
        }
        while ( v16 );
        *(_QWORD *)(v12 + 8) = 0;
      }
    }
    else
    {
      v7 = 0;
      v19 = 0;
      if ( !v11 )
        goto LABEL_60;
      do
      {
        v20 = 32LL * v19;
        v41 = *(_QWORD *)(v4 + 240);
        v21 = *(_QWORD *)(v20 + v41);
        v22 = *(__int64 **)(v20 + v41 + 8);
        v23 = *(void **)(v21 + 160);
        if ( v23 )
        {
          ExFreePoolWithTag(v23, 0);
          *(_QWORD *)(v21 + 160) = 0;
        }
        v24 = *(struct _MDL **)(v21 + 8);
        if ( v24 && v24 != (struct _MDL *)v22 && (v24->MdlFlags & 4) == 0 )
        {
          do
          {
            v25 = v24;
            v24 = v24->Next;
            v26 = v25->MdlFlags;
            if ( (v26 & 2) != 0 || (v26 & 0x20) != 0 )
              MmUnlockPages(v25);
            IoFreeMdl(v25);
          }
          while ( v24 );
          *(_QWORD *)(v21 + 8) = 0;
        }
        if ( v7 < 0 || (v27 = *(_QWORD *)(v20 + v41), *(int *)(v27 + 48) >= 0) )
        {
          v1 = v40;
        }
        else
        {
          v7 = *(_DWORD *)(v27 + 48);
          v40 = *(_QWORD *)(v20 + v41);
          v1 = v27;
        }
        ++v19;
      }
      while ( v19 < *(_DWORD *)(v4 + 272) );
    }
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 55, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1, v7);
      }
      if ( **(_BYTE **)(a1 + 64) == 2 )
      {
        v39 = 0;
        GenericIrpExtension = IoGetGenericIrpExtension(v1, &v39, 4);
        v29 = GenericIrpExtension >= 0 ? (v39 & 0x400) == 0 : GenericIrpExtension == -1073741789;
        if ( v29 )
        {
          v30 = (GenericIrpExtension >> 31) & 0xFFFFFFF8;
          v31 = v30 + 8;
          if ( v30 != -8 )
          {
            ExtendedErrorBuffer = Smb2AllocateExtendedErrorBuffer(a1, 1164730963, v31, 0);
            if ( ExtendedErrorBuffer )
            {
              v39 = 0;
              if ( (int)IoGetGenericIrpExtension(v1, &v39, 4) >= 0 && (v39 & 0x400) == 0 )
              {
                if ( (v39 & 0x800) != 0 )
                {
                  v33 = HIWORD(v39);
                  v34 = BYTE1(v39) >> 4;
                }
                else
                {
                  v34 = 0;
                  v33 = 0;
                }
                if ( v31 >= 8 )
                {
                  *(_DWORD *)ExtendedErrorBuffer = 8;
                  *(_BYTE *)(ExtendedErrorBuffer + 4) = v34;
                  *(_WORD *)(ExtendedErrorBuffer + 5) = v33;
                  *(_BYTE *)(ExtendedErrorBuffer + 7) = 0;
                }
              }
            }
          }
        }
      }
      Smb2SetError(a1, (unsigned int)v7, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1796);
      return (PSLIST_ENTRY)Srv2CompleteWorkItem(a1, 0);
    }
    v5 = v39;
LABEL_60:
    v35 = v42 + 64;
    if ( *(_DWORD *)(v4 + 272) == 1 )
    {
      *(_DWORD *)(v4 + 260) += v5;
      *(_DWORD *)v35 = 17;
      *(_DWORD *)(v35 + 4) = *(_DWORD *)(v4 + 260);
      *(_QWORD *)(v35 + 8) = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL) = 80;
    }
    else
    {
      v36 = 0;
      for ( *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL) = 64;
            v36 < *(_DWORD *)(v4 + 272);
            *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL) += 16 )
      {
        v37 = *(_QWORD *)(v4 + 240);
        v38 = v36++;
        v38 *= 32;
        *(_DWORD *)(v4 + 260) += *(_DWORD *)(*(_QWORD *)(v38 + v37) + 56LL);
        *(_DWORD *)v35 = 17;
        v35 += 16;
        *(_DWORD *)(v35 - 12) = *(_DWORD *)(*(_QWORD *)(v38 + v37) + 56LL);
        *(_QWORD *)(v35 - 8) = 0;
      }
    }
    Smb2SetSuccess(a1, (unsigned int)v7);
    return (PSLIST_ENTRY)Srv2CompleteWorkItem(a1, 0);
  }
  v29 = *(_DWORD *)(a1 + 8) == 5;
  *(_QWORD *)(a1 + 48) = Smb2ContinueWrite;
  *(_DWORD *)(a1 + 72) = 0;
  if ( v29 )
  {
    LOBYTE(v8) = 1;
    SRV2_PERF_ENTER_EX(a1 + 584, v8, 391, "Srv2PostToThreadPool", 1);
  }
  v9 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
  v10 = *(_QWORD *)(v9 + 8LL * KeGetCurrentNodeNumber() + 8);
  result = ExpInterlockedPushEntrySList((PSLIST_HEADER)(v10 + 16), (PSLIST_ENTRY)(a1 + 32));
  if ( !result )
  {
    if ( *(_WORD *)(v10 + 66) )
      return (PSLIST_ENTRY)RfspThreadPoolNodeWakeIdleWorker(v10);
  }
  return result;
}

```

## disassembly

```asm
0x140017730  push    rbx
0x140017732  push    rbp
0x140017733  push    rsi
0x140017734  push    rdi
0x140017735  push    r12
0x140017737  push    r13
0x140017739  push    r14
0x14001773b  push    r15
0x14001773d  sub     rsp, 38h
0x140017741  mov     r13, [rcx+78h]
0x140017745  lea     r14, Smb2ContinueWrite
0x14001774c  mov     rax, [rcx+138h]
0x140017753  mov     rdi, rcx
0x140017756  mov     rsi, [rcx+230h]
0x14001775d  mov     [rsp+78h+arg_8], r13
0x140017765  mov     ebx, [r13+38h]
0x140017769  mov     rax, [rax+18h]
0x14001776d  test    byte ptr [rsi+118h], 18h
0x140017774  mov     [rsp+78h+arg_18], rax
0x14001777c  mov     [rsp+78h+arg_0], ebx
0x140017783  jz      short loc_140017798
0x140017785  mov     rdx, r14
0x140017788  call    Srv2MarkWorkItemComplete
0x14001778d  cmp     eax, 103h
0x140017792  jz      loc_140017BF1
0x140017798  cmp     cs:Smb2EnableInlineSendIOCompletion, 0
0x14001779f  mov     rax, [rdi+78h]
0x1400177a3  mov     ebp, [rax+30h]
0x1400177a6  jz      loc_14001784F
0x1400177ac  test    ebp, ebp
0x1400177ae  jns     loc_14001784F
0x1400177b4  call    cs:__imp_KeGetCurrentIrql
0x1400177bb  nop     dword ptr [rax+rax+00h]
0x1400177c0  test    al, al
0x1400177c2  jz      loc_14001784F
0x1400177c8  cmp     dword ptr [rdi+8], 5
0x1400177cc  mov     [rdi+30h], r14
0x1400177d0  mov     dword ptr [rdi+48h], 0
0x1400177d7  jnz     short loc_1400177F9
0x1400177d9  lea     rcx, [rdi+248h]
0x1400177e0  mov     byte ptr [rsp+78h+var_58], 1
0x1400177e5  lea     r9, SourceString; "Srv2PostToThreadPool"
0x1400177ec  mov     r8d, 187h
0x1400177f2  mov     dl, 1
0x1400177f4  call    SRV2_PERF_ENTER_EX
0x1400177f9  mov     rax, [rdi+40h]
0x1400177fd  mov     rbx, [rax+88h]
0x140017804  call    cs:__imp_KeGetCurrentNodeNumber
0x14001780b  nop     dword ptr [rax+rax+00h]
0x140017810  movzx   eax, ax
0x140017813  lea     rdx, [rdi+20h]; ListEntry
0x140017817  mov     rbx, [rbx+rax*8+8]
0x14001781c  lea     rcx, [rbx+10h]; ListHead
0x140017820  call    cs:__imp_ExpInterlockedPushEntrySList
0x140017827  nop     dword ptr [rax+rax+00h]
0x14001782c  test    rax, rax
0x14001782f  jnz     loc_140017BF1
0x140017835  movzx   edx, word ptr [rbx+42h]
0x140017839  cmp     ax, dx
0x14001783c  jz      loc_140017BF1
0x140017842  mov     rcx, rbx
0x140017845  call    RfspThreadPoolNodeWakeIdleWorker
0x14001784a  jmp     loc_140017BF1
0x14001784f  mov     eax, [rsi+110h]
0x140017855  cmp     eax, 1
0x140017858  jnz     loc_140017901
0x14001785e  mov     r15, [rdi+78h]
0x140017862  mov     rax, [rdi+130h]
0x140017869  mov     r14, [rsi+0C8h]
0x140017870  mov     rcx, [r15+0A0h]; P
0x140017877  mov     r12, [rax+50h]
0x14001787b  test    rcx, rcx
0x14001787e  jz      short loc_140017899
0x140017880  xor     edx, edx; Tag
0x140017882  call    cs:__imp_ExFreePoolWithTag
0x140017889  nop     dword ptr [rax+rax+00h]
0x14001788e  mov     qword ptr [r15+0A0h], 0
0x140017899  mov     rbx, [r15+8]
0x14001789d  test    rbx, rbx
0x1400178a0  jz      loc_1400179DE
0x1400178a6  cmp     rbx, r12
0x1400178a9  jz      loc_1400179DE
0x1400178af  cmp     rbx, r14
0x1400178b2  jz      loc_1400179DE
0x1400178b8  test    byte ptr [rbx+0Ah], 4
0x1400178bc  jnz     loc_1400179DE
0x1400178c2  mov     r14, rbx
0x1400178c5  mov     rbx, [rbx]
0x1400178c8  movzx   eax, word ptr [r14+0Ah]
0x1400178cd  test    al, 2
0x1400178cf  jnz     short loc_1400178D5
0x1400178d1  test    al, 20h
0x1400178d3  jz      short loc_1400178E4
0x1400178d5  mov     rcx, r14; MemoryDescriptorList
0x1400178d8  call    cs:__imp_MmUnlockPages
0x1400178df  nop     dword ptr [rax+rax+00h]
0x1400178e4  mov     rcx, r14; Mdl
0x1400178e7  call    cs:__imp_IoFreeMdl
0x1400178ee  nop     dword ptr [rax+rax+00h]
0x1400178f3  test    rbx, rbx
0x1400178f6  jnz     short loc_1400178C2
0x1400178f8  mov     [r15+8], rbx
0x1400178fc  jmp     loc_1400179DE
0x140017901  xor     ebp, ebp
0x140017903  xor     r15d, r15d
0x140017906  test    eax, eax
0x140017908  jz      loc_140017B2F
0x14001790e  mov     rax, [rsi+0F0h]
0x140017915  mov     r12d, r15d
0x140017918  shl     r12, 5
0x14001791c  mov     [rsp+78h+arg_10], rax
0x140017924  mov     r13, [r12+rax]
0x140017928  mov     r14, [r12+rax+8]
0x14001792d  mov     rcx, [r13+0A0h]; P
0x140017934  test    rcx, rcx
0x140017937  jz      short loc_140017952
0x140017939  xor     edx, edx; Tag
0x14001793b  call    cs:__imp_ExFreePoolWithTag
0x140017942  nop     dword ptr [rax+rax+00h]
0x140017947  mov     qword ptr [r13+0A0h], 0
0x140017952  mov     rbx, [r13+8]
0x140017956  test    rbx, rbx
0x140017959  jz      short loc_1400179A0
0x14001795b  cmp     rbx, r14
0x14001795e  jz      short loc_1400179A0
0x140017960  test    byte ptr [rbx+0Ah], 4
0x140017964  jnz     short loc_1400179A0
0x140017966  mov     r14, rbx
0x140017969  mov     rbx, [rbx]
0x14001796c  movzx   eax, word ptr [r14+0Ah]
0x140017971  test    al, 2
0x140017973  jnz     short loc_140017979
0x140017975  test    al, 20h
0x140017977  jz      short loc_140017988
0x140017979  mov     rcx, r14; MemoryDescriptorList
0x14001797c  call    cs:__imp_MmUnlockPages
0x140017983  nop     dword ptr [rax+rax+00h]
0x140017988  mov     rcx, r14; Mdl
0x14001798b  call    cs:__imp_IoFreeMdl
0x140017992  nop     dword ptr [rax+rax+00h]
0x140017997  test    rbx, rbx
0x14001799a  jnz     short loc_140017966
0x14001799c  mov     [r13+8], rbx
0x1400179a0  test    ebp, ebp
0x1400179a2  js      short loc_1400179C6
0x1400179a4  mov     rax, [rsp+78h+arg_10]
0x1400179ac  mov     rax, [r12+rax]
0x1400179b0  mov     ecx, [rax+30h]
0x1400179b3  test    ecx, ecx
0x1400179b5  jns     short loc_1400179C6
0x1400179b7  mov     ebp, ecx
0x1400179b9  mov     [rsp+78h+arg_8], rax
0x1400179c1  mov     r13, rax
0x1400179c4  jmp     short loc_1400179CE
0x1400179c6  mov     r13, [rsp+78h+arg_8]
0x1400179ce  inc     r15d
0x1400179d1  cmp     r15d, [rsi+110h]
0x1400179d8  jb      loc_14001790E
0x1400179de  test    ebp, ebp
0x1400179e0  jns     loc_140017B28
0x1400179e6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400179ed  lea     rax, WPP_GLOBAL_Control
0x1400179f4  cmp     rcx, rax
0x1400179f7  jz      short loc_140017A24
0x1400179f9  test    dword ptr [rcx+2Ch], 800000h
0x140017a00  jz      short loc_140017A24
0x140017a02  cmp     byte ptr [rcx+29h], 1
0x140017a06  jb      short loc_140017A24
0x140017a08  mov     rcx, [rcx+18h]
0x140017a0c  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x140017a13  mov     edx, 37h ; '7'
0x140017a18  mov     [rsp+78h+var_58], ebp
0x140017a1c  mov     r9, rdi
0x140017a1f  call    WPP_SF_qD
0x140017a24  mov     rax, [rdi+40h]
0x140017a28  cmp     byte ptr [rax], 2
0x140017a2b  jnz     loc_140017B0C
0x140017a31  mov     r8d, 4
0x140017a37  mov     [rsp+78h+arg_0], 0
0x140017a42  lea     rdx, [rsp+78h+arg_0]
0x140017a4a  mov     rcx, r13
0x140017a4d  call    cs:__imp_IoGetGenericIrpExtension
0x140017a54  nop     dword ptr [rax+rax+00h]
0x140017a59  test    eax, eax
0x140017a5b  jns     short loc_140017A64
0x140017a5d  cmp     eax, 0C0000023h
0x140017a62  jmp     short loc_140017A6C
0x140017a64  test    byte ptr [rsp+78h+arg_0+1], 4
0x140017a6c  jnz     loc_140017B0C
0x140017a72  sar     eax, 1Fh
0x140017a75  and     eax, 0FFFFFFF8h
0x140017a78  lea     esi, [rax+8]
0x140017a7b  test    esi, esi
0x140017a7d  jz      loc_140017B0C
0x140017a83  xor     r9d, r9d
0x140017a86  mov     r8d, esi
0x140017a89  mov     edx, 456C6253h
0x140017a8e  mov     rcx, rdi
0x140017a91  call    Smb2AllocateExtendedErrorBuffer
0x140017a96  mov     rbx, rax
0x140017a99  test    rax, rax
0x140017a9c  jz      short loc_140017B0C
0x140017a9e  mov     r8d, 4
0x140017aa4  mov     [rsp+78h+arg_0], 0
0x140017aaf  lea     rdx, [rsp+78h+arg_0]
0x140017ab7  mov     rcx, r13
0x140017aba  call    cs:__imp_IoGetGenericIrpExtension
0x140017ac1  nop     dword ptr [rax+rax+00h]
0x140017ac6  test    eax, eax
0x140017ac8  js      short loc_140017B0C
0x140017aca  mov     cl, byte ptr [rsp+78h+arg_0+1]
0x140017ad1  test    cl, 4
0x140017ad4  jnz     short loc_140017B0C
0x140017ad6  test    cl, 8
0x140017ad9  jz      short loc_140017AEE
0x140017adb  mov     al, byte ptr [rsp+78h+arg_0+2]
0x140017ae2  mov     dl, byte ptr [rsp+78h+arg_0+3]
0x140017ae9  shr     cl, 4
0x140017aec  jmp     short loc_140017AF4
0x140017aee  xor     cl, cl
0x140017af0  xor     dl, dl
0x140017af2  xor     al, al
0x140017af4  cmp     esi, 8
0x140017af7  jb      short loc_140017B0C
0x140017af9  mov     dword ptr [rbx], 8
0x140017aff  mov     [rbx+4], cl
0x140017b02  mov     [rbx+5], al
0x140017b05  mov     [rbx+6], dl
0x140017b08  mov     byte ptr [rbx+7], 0
0x140017b0c  mov     r9d, 704h
0x140017b12  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140017b19  mov     edx, ebp
0x140017b1b  mov     rcx, rdi
0x140017b1e  call    _Smb2SetError
0x140017b23  jmp     loc_140017BE7
0x140017b28  mov     ebx, [rsp+78h+arg_0]
0x140017b2f  mov     r9, [rsp+78h+arg_18]
0x140017b37  add     r9, 40h ; '@'
0x140017b3b  cmp     dword ptr [rsi+110h], 1
0x140017b42  jnz     short loc_140017B73
0x140017b44  add     [rsi+104h], ebx
0x140017b4a  mov     dword ptr [r9], 11h
0x140017b51  mov     eax, [rsi+104h]
0x140017b57  mov     [r9+4], eax
0x140017b5b  mov     qword ptr [r9+8], 0
0x140017b63  mov     rax, [rdi+138h]
0x140017b6a  mov     dword ptr [rax+24h], 50h ; 'P'
0x140017b71  jmp     short loc_140017BDD
0x140017b73  mov     rax, [rdi+138h]
0x140017b7a  xor     r11d, r11d
0x140017b7d  mov     dword ptr [rax+24h], 40h ; '@'
0x140017b84  cmp     [rsi+110h], r11d
0x140017b8b  jbe     short loc_140017BDD
0x140017b8d  mov     rdx, [rsi+0F0h]
0x140017b94  mov     r8d, r11d
0x140017b97  inc     r11d
0x140017b9a  shl     r8, 5
0x140017b9e  mov     rax, [r8+rdx]
0x140017ba2  mov     ecx, [rax+38h]
0x140017ba5  add     [rsi+104h], ecx
0x140017bab  mov     dword ptr [r9], 11h
0x140017bb2  lea     r9, [r9+10h]
0x140017bb6  mov     rax, [r8+rdx]
0x140017bba  mov     ecx, [rax+38h]
0x140017bbd  mov     [r9-0Ch], ecx
0x140017bc1  mov     qword ptr [r9-8], 0
0x140017bc9  mov     rax, [rdi+138h]
0x140017bd0  add     dword ptr [rax+24h], 10h
0x140017bd4  cmp     r11d, [rsi+110h]
0x140017bdb  jb      short loc_140017B8D
0x140017bdd  mov     edx, ebp
0x140017bdf  mov     rcx, rdi
0x140017be2  call    Smb2SetSuccess
0x140017be7  xor     edx, edx
0x140017be9  mov     rcx, rdi
0x140017bec  call    Srv2CompleteWorkItem
0x140017bf1  add     rsp, 38h
0x140017bf5  pop     r15
0x140017bf7  pop     r14
0x140017bf9  pop     r13
0x140017bfb  pop     r12
0x140017bfd  pop     rdi
0x140017bfe  pop     rsi
0x140017bff  pop     rbp
0x140017c00  pop     rbx
0x140017c01  retn
```
