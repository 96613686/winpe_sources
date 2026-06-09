# UdfCommonFlushBuffers

- ea: `0x140035794`
- end: `0x140035bbd`
- name: `UdfCommonFlushBuffers`
- size: `1065`
- prototype: `__int64 __fastcall(int, PVOID Context2)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x140009014`
- `0x14000ba88`
- `0x14000ca10`
- `0x140010c5c`
- `0x140016994`
- `0x14002dc10`
- `0x140035794`
- `0x14003b730`
- `0x1400444c4`
- `0x140045f10`
- `0x14004ce50`
- `0x140052864`
- `0x140054460`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140035a3f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035adc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035af4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be38`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be61`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be82`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035a3f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035adc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035af4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be38`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be61`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be82`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140035a0d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140035a0d`
- `ntoskrnl!CcFlushCache` at `0x140035953`
- `ntoskrnl!CcFlushCache` at `0x140035953`
- `ntoskrnl!CcPurgeCacheSection` at `0x14003599f`
- `ntoskrnl!CcPurgeCacheSection` at `0x14003599f`
- `ntoskrnl!MmFlushImageSection` at `0x14003592d`
- `ntoskrnl!MmFlushImageSection` at `0x14003592d`
- `ntoskrnl!IofCallDriver` at `0x140035b4f`
- `ntoskrnl!IofCallDriver` at `0x140035b4f`

## pseudocode

```c
__int64 __fastcall UdfCommonFlushBuffers(__int64 a1, struct _IO_STATUS_BLOCK *Context2)
{
  unsigned int Status; // ebx
  __int64 v5; // r14
  ULONG_PTR Information; // r13
  int v7; // esi
  __int64 v8; // r11
  int v9; // eax
  __int64 result; // rax
  char v11; // cl
  char v12; // r12
  int v13; // esi
  int v14; // esi
  int v15; // esi
  __int64 v16; // rsi
  __int64 v17; // rcx
  SECTION_OBJECT_POINTERS *v18; // rcx
  __int64 v19; // r8
  ULONG_PTR v20; // rax
  ULONG_PTR v21; // rcx
  NTSTATUS v22; // eax
  char v23; // [rsp+31h] [rbp-47h]
  __int64 v24; // [rsp+80h] [rbp+8h] BYREF
  __int64 v25; // [rsp+88h] [rbp+10h] BYREF
  __int64 v26; // [rsp+90h] [rbp+18h]

  Status = 0;
  v24 = 0;
  v5 = *(_QWORD *)(a1 + 16);
  v25 = 0;
  Information = Context2[11].Information;
  v7 = UdfDecodeFileObject(*(_QWORD *)(Information + 48), &v24, &v25);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x8000000) != 0 )
  {
    WPP_SF_qq(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      10,
      WPP_dfdd884fd2a539582ed6ef57b513599a_Traceguids,
      v8,
      v24);
  }
  v9 = *(_DWORD *)(v5 + 48);
  if ( (v9 & 0x10) != 0 )
  {
    if ( (v9 & 0x80u) == 0 )
      Status = (v9 & 0x20) != 0 ? -1073739770 : -1073741790;
    else
      Status = -1073741662;
    goto LABEL_8;
  }
  if ( *(_BYTE *)(Information + 1) == 1 && LOBYTE(Context2[4].Status) )
  {
    Status = -1073741811;
LABEL_8:
    UdfCompleteRequest(a1, Context2, Status);
    return Status;
  }
  v26 = v5;
  if ( (*(_DWORD *)(a1 + 28) & 4) != 0 )
  {
    v11 = 0;
    v23 = 0;
    v12 = 0;
    if ( !v7 )
      goto LABEL_44;
    v13 = v7 - 1;
    if ( !v13 )
      goto LABEL_44;
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( v15 != 1 )
        {
          Status = -1073741811;
LABEL_44:
          if ( v11 )
            ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v24 + 136) + 80LL) + 8LL));
          if ( v12 )
            ExReleaseResourceLite((PERESOURCE)(v5 + 1480));
          v20 = Context2[11].Information;
          *(_OWORD *)(v20 - 72) = *(_OWORD *)v20;
          *(_OWORD *)(v20 - 56) = *(_OWORD *)(v20 + 16);
          *(_OWORD *)(v20 - 40) = *(_OWORD *)(v20 + 32);
          *(_QWORD *)(v20 - 24) = *(_QWORD *)(v20 + 48);
          *(_BYTE *)(v20 - 69) = 0;
          v21 = Context2[11].Information;
          *(_QWORD *)(v21 - 16) = UdfFlushCompletionRoutine;
          *(_QWORD *)(v21 - 8) = Status;
          *(_BYTE *)(v21 - 69) = -32;
          v22 = IofCallDriver(*(PDEVICE_OBJECT *)(v5 + 24), (PIRP)Context2);
          if ( v22 == 259 || v22 < 0 && v22 != -1073741808 )
            Status = v22;
          UdfCompleteRequest(a1, 0, 0);
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x8000000) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              11,
              WPP_dfdd884fd2a539582ed6ef57b513599a_Traceguids);
          }
          return Status;
        }
        v16 = v24;
        UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(v24 + 136) + 80LL) + 8LL, 0, 0);
        v23 = 1;
        UdfVerifyScbOperation(a1, v16, v25);
        v17 = *(_QWORD *)(v16 + 424);
        if ( *(_QWORD *)(v17 + 24) )
          MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v17 + 8), MmFlushForWrite);
        v18 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(v16 + 424) + 8LL);
        if ( v18->DataSectionObject )
        {
          CcFlushCache(v18, 0, 0, Context2 + 3);
          Status = Context2[3].Status;
          if ( Status == -2147483626 && *(_BYTE *)(a1 + 57) != 2 )
            UdfRaiseStatusEx(a1, 2147483670LL, 0);
          if ( (Status & 0x80000000) == 0
            && *(_BYTE *)(Information + 1) == 1
            && !CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v16 + 424) + 8LL), 0, 0, 0) )
          {
            Status = -1073741797;
          }
        }
        if ( (*(_QWORD *)(v5 + 352) || (*(_DWORD *)(v5 + 48) & 0x20000000) != 0) && *(_DWORD *)(v24 + 376) )
          UdfSeqCacheFlush(a1, v5);
        UdfFlushIcbForScb(a1, v24);
        if ( (*(_DWORD *)(v5 + 48) & 0x2000) != 0 )
        {
          ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v5 + 104) + 128LL), 1u);
          Status = UdfRmwFlushCache(a1);
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v5 + 104) + 128LL));
        }
LABEL_43:
        v11 = v23;
        goto LABEL_44;
      }
      if ( v24 != *(_QWORD *)(v5 + 288) )
        goto LABEL_44;
      v25 = 0;
    }
    UdfAcquireResource(a1, v5 + 1480, 0, 0);
    v12 = 1;
    UdfVerifyVcb(a1, v5, v19);
    Status = UdfFlushVolume(a1, v5, 0, 1, 0, 0);
    goto LABEL_43;
  }
  result = UdfFsdPostRequest((PVOID)a1, Context2);
  Status = result;
  if ( (int)result < 0 )
    goto LABEL_8;
  return result;
}

```

## disassembly

```asm
0x140035794  mov     rax, rsp
0x140035797  push    rbx
0x140035798  push    rsi
0x140035799  push    rdi
0x14003579a  push    r12
0x14003579c  push    r13
0x14003579e  push    r14
0x1400357a0  push    r15
0x1400357a2  sub     rsp, 40h
0x1400357a6  mov     r15, rdx
0x1400357a9  mov     rdi, rcx
0x1400357ac  xor     ebx, ebx
0x1400357ae  mov     [rax+8], rbx
0x1400357b2  mov     r14, [rcx+10h]
0x1400357b6  mov     [rax+10h], rbx
0x1400357ba  mov     r13, [rdx+0B8h]
0x1400357c1  mov     r11, [r13+30h]
0x1400357c5  lea     r8, [rax+10h]
0x1400357c9  lea     rdx, [rax+8]
0x1400357cd  mov     rcx, r11
0x1400357d0  call    UdfDecodeFileObject
0x1400357d5  mov     esi, eax
0x1400357d7  lea     rax, WPP_GLOBAL_Control
0x1400357de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400357e5  cmp     rcx, rax
0x1400357e8  jz      short loc_140035816
0x1400357ea  test    dword ptr [rcx+2Ch], 8000000h
0x1400357f1  jz      short loc_140035816
0x1400357f3  lea     edx, [rbx+0Ah]
0x1400357f6  mov     rax, [rsp+78h+arg_0]
0x1400357fe  mov     qword ptr [rsp+78h+var_58], rax
0x140035803  mov     r9, r11
0x140035806  lea     r8, WPP_dfdd884fd2a539582ed6ef57b513599a_Traceguids
0x14003580d  mov     rcx, [rcx+18h]
0x140035811  call    WPP_SF_qq
0x140035816  mov     eax, [r14+30h]
0x14003581a  test    al, 10h
0x14003581c  jz      short loc_14003585C
0x14003581e  test    al, al
0x140035820  jns     short loc_140035829
0x140035822  mov     ebx, 0C00000A2h
0x140035827  jmp     short loc_14003583B
0x140035829  and     al, 20h
0x14003582b  neg     al
0x14003582d  sbb     ebx, ebx
0x14003582f  and     ebx, 7E4h
0x140035835  add     ebx, 0C0000022h
0x14003583b  mov     r8d, ebx
0x14003583e  mov     rdx, r15
0x140035841  mov     rcx, rdi
0x140035844  call    UdfCompleteRequest
0x140035849  mov     eax, ebx
0x14003584b  add     rsp, 40h
0x14003584f  pop     r15
0x140035851  pop     r14
0x140035853  pop     r13
0x140035855  pop     r12
0x140035857  pop     rdi
0x140035858  pop     rsi
0x140035859  pop     rbx
0x14003585a  retn
0x14003585c  cmp     byte ptr [r13+1], 1
0x140035861  jnz     short loc_140035870
0x140035863  cmp     [r15+40h], bl
0x140035867  jz      short loc_140035870
0x140035869  mov     ebx, 0C000000Dh
0x14003586e  jmp     short loc_14003583B
0x140035870  mov     [rsp+78h+arg_10], r14
0x140035878  mov     eax, [rdi+1Ch]
0x14003587b  test    al, 4
0x14003587d  jnz     short loc_140035892
0x14003587f  mov     rdx, r15; Context2
0x140035882  mov     rcx, rdi; Context1
0x140035885  call    UdfFsdPostRequest
0x14003588a  mov     ebx, eax
0x14003588c  test    eax, eax
0x14003588e  jns     short loc_14003584B
0x140035890  jmp     short loc_14003583B
0x140035892  mov     cl, bl
0x140035894  mov     [rsp+78h+var_47], bl
0x140035898  mov     r12b, bl
0x14003589b  mov     [rsp+78h+var_46], bl
0x14003589f  mov     [rsp+78h+var_48], bl
0x1400358a3  test    esi, esi
0x1400358a5  jz      loc_140035AC1
0x1400358ab  sub     esi, 1
0x1400358ae  jz      loc_140035AC1
0x1400358b4  sub     esi, 1
0x1400358b7  jz      loc_140035A74
0x1400358bd  sub     esi, 1
0x1400358c0  jz      loc_140035A57
0x1400358c6  cmp     esi, 1
0x1400358c9  jz      short loc_1400358D9
0x1400358cb  mov     ebx, 0C000000Dh
0x1400358d0  mov     [rsp+78h+var_44], ebx
0x1400358d4  jmp     loc_140035AC1
0x1400358d9  mov     rsi, [rsp+78h+arg_0]
0x1400358e1  mov     rax, [rsi+88h]
0x1400358e8  mov     rdx, [rax+50h]
0x1400358ec  add     rdx, 8
0x1400358f0  xor     r9d, r9d
0x1400358f3  xor     r8d, r8d
0x1400358f6  mov     rcx, rdi
0x1400358f9  call    UdfAcquireResource
0x1400358fe  mov     [rsp+78h+var_47], 1
0x140035903  mov     r8, [rsp+78h+arg_8]
0x14003590b  mov     rdx, rsi
0x14003590e  mov     rcx, rdi
0x140035911  call    UdfVerifyScbOperation
0x140035916  mov     rcx, [rsi+1A8h]
0x14003591d  cmp     qword ptr [rcx+18h], 0
0x140035922  jz      short loc_140035939
0x140035924  add     rcx, 8; SectionObjectPointer
0x140035928  mov     edx, 1; FlushType
0x14003592d  call    cs:__imp_MmFlushImageSection
0x140035934  nop     dword ptr [rax+rax+00h]
0x140035939  mov     rax, [rsi+1A8h]
0x140035940  lea     rcx, [rax+8]; SectionObjectPointer
0x140035944  cmp     qword ptr [rcx], 0
0x140035948  jz      short loc_1400359B9
0x14003594a  lea     r9, [r15+30h]; IoStatus
0x14003594e  xor     r8d, r8d; Length
0x140035951  xor     edx, edx; FileOffset
0x140035953  call    cs:__imp_CcFlushCache
0x14003595a  nop     dword ptr [rax+rax+00h]
0x14003595f  mov     ebx, [r15+30h]
0x140035963  mov     [rsp+78h+var_44], ebx
0x140035967  mov     edx, 80000016h
0x14003596c  cmp     ebx, edx
0x14003596e  jnz     short loc_140035981
0x140035970  cmp     byte ptr [rdi+39h], 2
0x140035974  jz      short loc_140035981
0x140035976  xor     r8d, r8d
0x140035979  mov     rcx, rdi
0x14003597c  call    UdfRaiseStatusEx
0x140035981  test    ebx, ebx
0x140035983  js      short loc_1400359B9
0x140035985  cmp     byte ptr [r13+1], 1
0x14003598a  jnz     short loc_1400359B9
0x14003598c  mov     rcx, [rsi+1A8h]
0x140035993  add     rcx, 8; SectionObjectPointer
0x140035997  xor     r9d, r9d; Flags
0x14003599a  xor     r8d, r8d; Length
0x14003599d  xor     edx, edx; FileOffset
0x14003599f  call    cs:__imp_CcPurgeCacheSection
0x1400359a6  nop     dword ptr [rax+rax+00h]
0x1400359ab  mov     ecx, 0C000001Bh
0x1400359b0  test    al, al
0x1400359b2  cmovz   ebx, ecx
0x1400359b5  mov     [rsp+78h+var_44], ebx
0x1400359b9  cmp     qword ptr [r14+160h], 0
0x1400359c1  jnz     short loc_1400359CD
0x1400359c3  test    dword ptr [r14+30h], 20000000h
0x1400359cb  jz      short loc_1400359E9
0x1400359cd  mov     rax, [rsp+78h+arg_0]
0x1400359d5  cmp     dword ptr [rax+178h], 0
0x1400359dc  jz      short loc_1400359E9
0x1400359de  mov     rdx, r14
0x1400359e1  mov     rcx, rdi
0x1400359e4  call    UdfSeqCacheFlush
0x1400359e9  mov     rdx, [rsp+78h+arg_0]
0x1400359f1  mov     rcx, rdi
0x1400359f4  call    UdfFlushIcbForScb
0x1400359f9  mov     eax, [r14+30h]
0x1400359fd  bt      eax, 0Dh
0x140035a01  jnb     short loc_140035A50
0x140035a03  mov     rcx, [r14+68h]
0x140035a07  sub     rcx, 0FFFFFFFFFFFFFF80h; Resource
0x140035a0b  mov     dl, 1; Wait
0x140035a0d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140035a14  nop     dword ptr [rax+rax+00h]
0x140035a19  mov     [rsp+78h+var_48], 1
0x140035a1e  xor     r9d, r9d
0x140035a21  lea     r8d, [r9+0Ch]
0x140035a25  mov     rdx, [r14+68h]
0x140035a29  mov     rcx, rdi; int
0x140035a2c  call    UdfRmwFlushCache
0x140035a31  mov     ebx, eax
0x140035a33  mov     [rsp+78h+var_44], eax
0x140035a37  mov     rcx, [r14+68h]
0x140035a3b  sub     rcx, 0FFFFFFFFFFFFFF80h; Resource
0x140035a3f  call    cs:__imp_ExReleaseResourceLite
0x140035a46  nop     dword ptr [rax+rax+00h]
0x140035a4b  mov     [rsp+78h+var_48], 0
0x140035a50  mov     [rsp+78h+var_48], 0
0x140035a55  jmp     short loc_140035ABD
0x140035a57  mov     rax, [r14+120h]
0x140035a5e  cmp     [rsp+78h+arg_0], rax
0x140035a66  jnz     short loc_140035AC1
0x140035a68  mov     [rsp+78h+arg_8], 0
0x140035a74  lea     rdx, [r14+5C8h]
0x140035a7b  xor     r9d, r9d
0x140035a7e  xor     r8d, r8d
0x140035a81  mov     rcx, rdi
0x140035a84  call    UdfAcquireResource
0x140035a89  mov     r12b, 1
0x140035a8c  mov     [rsp+78h+var_46], r12b
0x140035a91  mov     rdx, r14
0x140035a94  mov     rcx, rdi
0x140035a97  call    UdfVerifyVcb
0x140035a9c  mov     [rsp+78h+var_50], 0; char
0x140035aa1  mov     [rsp+78h+var_58], 0; char
0x140035aa6  mov     r9b, r12b
0x140035aa9  xor     r8d, r8d
0x140035aac  mov     rdx, r14
0x140035aaf  mov     rcx, rdi; int
0x140035ab2  call    UdfFlushVolume
0x140035ab7  mov     ebx, eax
0x140035ab9  mov     [rsp+78h+var_44], eax
0x140035abd  mov     cl, [rsp+78h+var_47]
0x140035ac1  test    cl, cl
0x140035ac3  jz      short loc_140035AE8
0x140035ac5  mov     rax, [rsp+78h+arg_0]
0x140035acd  mov     rcx, [rax+88h]
0x140035ad4  mov     rcx, [rcx+50h]
0x140035ad8  add     rcx, 8; Resource
0x140035adc  call    cs:__imp_ExReleaseResourceLite
0x140035ae3  nop     dword ptr [rax+rax+00h]
0x140035ae8  test    r12b, r12b
0x140035aeb  jz      short loc_140035B00
0x140035aed  lea     rcx, [r14+5C8h]; Resource
0x140035af4  call    cs:__imp_ExReleaseResourceLite
0x140035afb  nop     dword ptr [rax+rax+00h]
0x140035b00  mov     rax, [r15+0B8h]
0x140035b07  movups  xmm0, xmmword ptr [rax]
0x140035b0a  movups  xmmword ptr [rax-48h], xmm0
0x140035b0e  movups  xmm1, xmmword ptr [rax+10h]
0x140035b12  movups  xmmword ptr [rax-38h], xmm1
0x140035b16  movups  xmm0, xmmword ptr [rax+20h]
0x140035b1a  movups  xmmword ptr [rax-28h], xmm0
0x140035b1e  movsd   xmm1, qword ptr [rax+30h]
0x140035b23  movsd   qword ptr [rax-18h], xmm1
0x140035b28  mov     byte ptr [rax-45h], 0
0x140035b2c  mov     rcx, [r15+0B8h]
0x140035b33  lea     rax, UdfFlushCompletionRoutine
0x140035b3a  mov     [rcx-10h], rax
0x140035b3e  mov     eax, ebx
0x140035b40  mov     [rcx-8], rax
0x140035b44  mov     byte ptr [rcx-45h], 0E0h
0x140035b48  mov     rdx, r15; Irp
0x140035b4b  mov     rcx, [r14+18h]; DeviceObject
0x140035b4f  call    cs:__imp_IofCallDriver
0x140035b56  nop     dword ptr [rax+rax+00h]
0x140035b5b  cmp     eax, 103h
0x140035b60  jz      short loc_140035B6D
0x140035b62  test    eax, eax
0x140035b64  jns     short loc_140035B6F
0x140035b66  cmp     eax, 0C0000010h
0x140035b6b  jz      short loc_140035B6F
0x140035b6d  mov     ebx, eax
0x140035b6f  xor     r8d, r8d
0x140035b72  xor     edx, edx
0x140035b74  mov     rcx, rdi
0x140035b77  call    UdfCompleteRequest
0x140035b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035b83  lea     rax, WPP_GLOBAL_Control
0x140035b8a  cmp     rcx, rax
0x140035b8d  jz      loc_140035849
0x140035b93  test    dword ptr [rcx+2Ch], 8000000h
0x140035b9a  jz      loc_140035849
0x140035ba0  mov     edx, 0Bh
0x140035ba5  mov     r9d, ebx
0x140035ba8  lea     r8, WPP_dfdd884fd2a539582ed6ef57b513599a_Traceguids
0x140035baf  mov     rcx, [rcx+18h]
0x140035bb3  call    WPP_SF_d
0x140035bb8  jmp     loc_140035849
0x14005be1a  push    rbp
0x14005be1c  sub     rsp, 30h
0x14005be20  mov     rbp, rdx
0x14005be23  cmp     byte ptr [rbp+30h], 0
0x14005be27  jz      short loc_14005BE45
0x14005be29  mov     rax, [rbp+90h]
0x14005be30  mov     rcx, [rax+68h]
0x14005be34  sub     rcx, 0FFFFFFFFFFFFFF80h; Resource
0x14005be38  call    cs:__imp_ExReleaseResourceLite
0x14005be3f  nop     dword ptr [rax+rax+00h]
0x14005be44  nop
0x14005be45  cmp     byte ptr [rbp+31h], 0
0x14005be49  jz      short loc_14005BE6E
0x14005be4b  mov     rax, [rbp+80h]
0x14005be52  mov     rcx, [rax+88h]
0x14005be59  mov     rcx, [rcx+50h]
0x14005be5d  add     rcx, 8; Resource
0x14005be61  call    cs:__imp_ExReleaseResourceLite
0x14005be68  nop     dword ptr [rax+rax+00h]
0x14005be6d  nop
0x14005be6e  cmp     byte ptr [rbp+32h], 0
0x14005be72  jz      short loc_14005BE8F
0x14005be74  mov     rcx, [rbp+90h]
0x14005be7b  add     rcx, 5C8h; Resource
0x14005be82  call    cs:__imp_ExReleaseResourceLite
0x14005be89  nop     dword ptr [rax+rax+00h]
0x14005be8e  nop
0x14005be8f  add     rsp, 30h
0x14005be93  pop     rbp
0x14005be94  retn
```
