# NvmeContinueScatterGatherProcessIO

- ea: `0x14004cbb0`
- end: `0x14004cf8f`
- name: `NvmeContinueScatterGatherProcessIO`
- size: `991`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140033454`
- `0x14003348c`
- `0x140042b60`
- `0x140043ca0`
- `0x14004cbb0`
- `0x140060e90`
- `0x140065dc0`
- `0x140066260`
- `0x1400707a0`
- `0x14012f040`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004ccb4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004ccb4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14004cdc0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14004cdc0`
- `ntoskrnl!PoFxIdleComponent` at `0x14004cf38`
- `ntoskrnl!PoFxIdleComponent` at `0x14004cf67`
- `ntoskrnl!PoFxIdleComponent` at `0x14004cf38`
- `ntoskrnl!PoFxIdleComponent` at `0x14004cf67`
- `ntoskrnl!KeLowerIrql` at `0x14004ce9d`
- `ntoskrnl!KeLowerIrql` at `0x14004ce9d`
- `ntoskrnl!KfRaiseIrql` at `0x14004ce58`
- `ntoskrnl!KfRaiseIrql` at `0x14004ce58`
- `ntoskrnl!IofCompleteRequest` at `0x14004cedd`
- `ntoskrnl!IofCompleteRequest` at `0x14004cedd`

## pseudocode

```c
__int64 __fastcall NvmeContinueScatterGatherProcessIO(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // rdi
  char v6; // r12
  __int64 v7; // rsi
  __int64 v8; // rbp
  __int64 v9; // r15
  unsigned __int16 *v10; // rax
  char v11; // bl
  __int64 result; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // r15d
  __int64 v16; // r11
  int v17; // r9d
  PSLIST_ENTRY v18; // rax
  __int64 NewNVMePrpListBufferEntry; // rax
  char v20; // r12
  __int64 v21; // r8
  unsigned __int16 *v22; // rax
  __int64 v23; // rbx
  int v24; // r14d
  bool v25; // zf
  unsigned __int8 v26; // bl
  KIRQL v27; // r12
  __int64 v28; // r8
  __int64 v29; // rbx
  __int64 v30; // rcx
  int v31; // [rsp+60h] [rbp-68h]
  __int64 v32; // [rsp+68h] [rbp-60h]
  __int64 v33; // [rsp+70h] [rbp-58h]
  __int64 v34; // [rsp+78h] [rbp-50h]
  __int64 v35; // [rsp+80h] [rbp-48h]
  __int64 v36; // [rsp+88h] [rbp-40h]
  bool v37; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v38; // [rsp+E0h] [rbp+18h]
  int v39; // [rsp+E8h] [rbp+20h]

  v38 = a3;
  v4 = *(_QWORD **)(a4 + 32);
  v6 = *(_BYTE *)(a4 + 126);
  v7 = *(_QWORD *)(a4 + 40);
  v8 = *(unsigned int *)(a4 + 120);
  v9 = *(_QWORD *)(a4 + 72);
  v36 = *(_QWORD *)(a1 + 64);
  v37 = 0;
  v32 = v4[2];
  v10 = *(unsigned __int16 **)(a4 + 64);
  v33 = (__int64)v10;
  *(_QWORD *)(a4 + 24) = a3;
  if ( (v6 & 2) == 0 )
  {
    v16 = *(unsigned int *)(a4 + 116);
    v39 = *(_DWORD *)(a4 + 112);
    v34 = *(_QWORD *)(a4 + 104);
    v35 = *(_QWORD *)(a4 + 96);
    v31 = v16;
    if ( ((((*(_DWORD *)(*(_QWORD *)(v7 + 8) + 32LL) + *(_DWORD *)(*(_QWORD *)(v7 + 8) + 44LL)) & 0xFFF) + v16 + 4095)
        & 0xFFFFFFFFFFFFF000uLL) > 0x2000 )
    {
      v18 = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v4[2] + 880LL) + 8 * v8));
      v17 = (int)v18;
      if ( !v18 )
      {
        NewNVMePrpListBufferEntry = AllocateNewNVMePrpListBufferEntry(v4[2], (unsigned int)v8);
        v17 = NewNVMePrpListBufferEntry;
        if ( !NewNVMePrpListBufferEntry )
        {
          result = NvmeNamespaceQueueIo(v4, v7, (unsigned int)v8);
          v15 = -2147483631;
LABEL_14:
          v11 = 0;
          goto LABEL_15;
        }
      }
      LODWORD(v16) = v31;
    }
    else
    {
      v17 = 0;
    }
    v20 = v6 & 1;
    if ( !v33 )
    {
      v21 = v4[2];
      if ( (*(_BYTE *)(v21 + 136) & 2) != 0 )
        v9 = *(_QWORD *)(v21 + 728) + 192 * v8;
      else
        LODWORD(v9) = 192 * *(unsigned __int16 *)(*(_QWORD *)(v21 + 872) + 2 * v8) + *(_DWORD *)(v21 + 728) - 192;
    }
    result = NvmeSubmitIoToSQ((_DWORD)v4, v7, v9, v17, v8, 0, v16, v35, v34, v39, v20, v33);
    v15 = result;
    goto LABEL_14;
  }
  v11 = 1;
  result = NvmeSendSplitIo(*(_QWORD *)(a4 + 88), v8, v9, v10, &v37, 0, 0, 0, 1);
  v15 = result;
LABEL_15:
  if ( v15 != 259 )
  {
    v22 = *(unsigned __int16 **)(a4 + 64);
    if ( v22 )
      ExpInterlockedPushEntrySList(
        (PSLIST_HEADER)(*(_QWORD *)(a4 + 72) + 64LL),
        (PSLIST_ENTRY)(*(_QWORD *)(*(_QWORD *)(a4 + 72) + 32LL) + ((unsigned __int64)*v22 << 7)));
    result = v15 + 0x80000000;
    if ( (int)result >= 0 && v15 != -2147483631 )
    {
      if ( v11 )
      {
        if ( !v37 )
          return result;
        v23 = *(_QWORD *)(*(_QWORD *)(v7 + 184) + 24LL);
        v24 = *(_DWORD *)(v23 + 112);
        FreeAllSglAndContextInChainedSplitIoContext(v32, v23, v13, v14);
        FreeNVMeChainedIoSplitContext(v32, (unsigned int)v8, v23, v7);
        v25 = (*(_BYTE *)(v7 + 151) & 1) == 0;
        *(_QWORD *)(v7 + 56) = 0;
        if ( !v25 )
          _InterlockedDecrement(*(volatile signed __int32 **)(v4[87] + 8 * v8));
        *(_DWORD *)(v7 + 48) = v24;
      }
      else
      {
        v26 = *(_BYTE *)(a4 + 126) & 1;
        v27 = KfRaiseIrql(2u);
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(*(_QWORD *)(v36 + 1160) + 8LL) + 96LL))(
          *(_QWORD *)(v36 + 1160),
          v38,
          v26 ^ 1u);
        if ( v27 < 2u )
          KeLowerIrql(v27);
        LOBYTE(v28) = 1;
        FreeNVMeSGLBufferContext(v32, a4, v28);
        v25 = (*(_BYTE *)(v7 + 151) & 1) == 0;
        *(_QWORD *)(v7 + 56) = 0;
        if ( !v25 )
          _InterlockedDecrement(*(volatile signed __int32 **)(v4[87] + 8 * v8));
        *(_DWORD *)(v7 + 48) = v15;
      }
      IofCompleteRequest((PIRP)v7, 0);
      result = v4[16];
      if ( !*(_BYTE *)result )
      {
        result = (unsigned int)_InterlockedExchangeAdd(
                                 *(volatile signed __int32 **)(*(_QWORD *)(result + 24) + 8 * v8),
                                 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
        {
          v29 = *(_QWORD *)(v4[2] + 128LL);
          result = NvmeNamespaceCheckAndAcquirePoFx(v4);
          if ( (_BYTE)result )
          {
            PoFxIdleComponent(**(_QWORD **)(v4[16] + 8LL), 0, 2);
            result = NvmeNamespaceReleasePoFx(v4);
          }
          v30 = *(_QWORD *)(v29 + 168);
          if ( *(_BYTE *)v30 == 1 )
            return PoFxIdleComponent(**(_QWORD **)(v30 + 8), 0, 2);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14004cbb0  mov     r11, rsp
0x14004cbb3  mov     [r11+10h], rbx
0x14004cbb7  mov     [r11+18h], r8
0x14004cbbb  push    rbp
0x14004cbbc  push    rsi
0x14004cbbd  push    rdi
0x14004cbbe  push    r12
0x14004cbc0  push    r13
0x14004cbc2  push    r14
0x14004cbc4  push    r15
0x14004cbc6  sub     rsp, 90h
0x14004cbcd  mov     rax, [rcx+40h]
0x14004cbd1  xor     r13d, r13d
0x14004cbd4  mov     rdi, [r9+20h]
0x14004cbd8  mov     r14, r9
0x14004cbdb  movzx   r12d, byte ptr [r9+7Eh]
0x14004cbe0  mov     rsi, [r9+28h]
0x14004cbe4  mov     ebp, [r9+78h]
0x14004cbe8  mov     r15, [r9+48h]
0x14004cbec  mov     [rsp+0C8h+var_40], rax
0x14004cbf4  mov     byte ptr [r11+8], 0
0x14004cbf9  mov     rax, [rdi+10h]
0x14004cbfd  mov     [rsp+0C8h+var_60], rax
0x14004cc02  mov     rax, [r9+40h]
0x14004cc06  mov     [rsp+0C8h+var_58], rax
0x14004cc0b  mov     [r9+18h], r8
0x14004cc0f  test    r12b, 2
0x14004cc13  jz      short loc_14004CC4C
0x14004cc15  lea     rcx, [r11+8]
0x14004cc19  mov     bl, 1
0x14004cc1b  mov     byte ptr [rsp+0C8h+var_88], bl
0x14004cc1f  mov     r9, rax
0x14004cc22  mov     [rsp+0C8h+var_90], r13
0x14004cc27  mov     r8, r15
0x14004cc2a  mov     [rsp+0C8h+var_98], r13
0x14004cc2f  mov     edx, ebp
0x14004cc31  mov     [rsp+0C8h+var_A0], r13
0x14004cc36  mov     [rsp+0C8h+var_A8], rcx
0x14004cc3b  mov     rcx, [r14+58h]
0x14004cc3f  call    NvmeSendSplitIo
0x14004cc44  mov     r15d, eax
0x14004cc47  jmp     loc_14004CD97
0x14004cc4c  mov     eax, [r9+70h]
0x14004cc50  mov     rbx, rbp
0x14004cc53  mov     r11d, [r9+74h]
0x14004cc57  mov     [rsp+0C8h+arg_18], eax
0x14004cc5e  mov     rax, [r9+68h]
0x14004cc62  mov     [rsp+0C8h+var_50], rax
0x14004cc67  mov     rax, [r9+60h]
0x14004cc6b  mov     [rsp+0C8h+var_48], rax
0x14004cc73  mov     rax, [rsi+8]
0x14004cc77  mov     [rsp+0C8h+var_68], r11
0x14004cc7c  mov     ecx, [rax+2Ch]
0x14004cc7f  add     ecx, [rax+20h]
0x14004cc82  lea     rax, [r11+0FFFh]
0x14004cc89  and     ecx, 0FFFh
0x14004cc8f  add     rax, rcx
0x14004cc92  and     rax, 0FFFFFFFFFFFFF000h
0x14004cc98  cmp     rax, 2000h
0x14004cc9e  ja      short loc_14004CCA5
0x14004cca0  mov     r9, r13
0x14004cca3  jmp     short loc_14004CCF9
0x14004cca5  mov     rax, [rdi+10h]
0x14004cca9  mov     rcx, [rax+370h]
0x14004ccb0  mov     rcx, [rcx+rbp*8]; ListHead
0x14004ccb4  call    cs:__imp_ExpInterlockedPopEntrySList
0x14004ccbb  nop     dword ptr [rax+rax+00h]
0x14004ccc0  mov     r9, rax
0x14004ccc3  test    rax, rax
0x14004ccc6  jnz     short loc_14004CCF4
0x14004ccc8  mov     rcx, [rdi+10h]
0x14004cccc  mov     edx, ebp
0x14004ccce  call    AllocateNewNVMePrpListBufferEntry
0x14004ccd3  mov     r9, rax
0x14004ccd6  test    rax, rax
0x14004ccd9  jnz     short loc_14004CCF4
0x14004ccdb  mov     r8d, ebp
0x14004ccde  mov     rdx, rsi
0x14004cce1  mov     rcx, rdi
0x14004cce4  call    NvmeNamespaceQueueIo
0x14004cce9  mov     r15d, 80000011h
0x14004ccef  jmp     loc_14004CD95
0x14004ccf4  mov     r11, [rsp+0C8h+var_68]
0x14004ccf9  mov     r10, [rsp+0C8h+var_58]
0x14004ccfe  and     r12b, 1
0x14004cd02  test    r10, r10
0x14004cd05  jnz     short loc_14004CD4A
0x14004cd07  mov     r8, [rdi+10h]
0x14004cd0b  test    byte ptr [r8+88h], 2
0x14004cd13  jz      short loc_14004CD26
0x14004cd15  lea     r15, [rbx+rbx*2]
0x14004cd19  shl     r15, 6
0x14004cd1d  add     r15, [r8+2D8h]
0x14004cd24  jmp     short loc_14004CD4A
0x14004cd26  mov     rax, [r8+368h]
0x14004cd2d  mov     r15, [r8+2D8h]
0x14004cd34  add     r15, 0FFFFFFFFFFFFFF40h
0x14004cd3b  movzx   ecx, word ptr [rax+rbx*2]
0x14004cd3f  lea     rdx, [rcx+rcx*2]
0x14004cd43  shl     rdx, 6
0x14004cd47  add     r15, rdx
0x14004cd4a  mov     eax, [rsp+0C8h+arg_18]
0x14004cd51  mov     r8, r15
0x14004cd54  mov     [rsp+0C8h+var_70], r10
0x14004cd59  mov     rdx, rsi
0x14004cd5c  mov     [rsp+0C8h+var_78], r12b
0x14004cd61  mov     rcx, rdi
0x14004cd64  mov     [rsp+0C8h+var_80], eax
0x14004cd68  mov     rax, [rsp+0C8h+var_50]
0x14004cd6d  mov     [rsp+0C8h+var_88], rax
0x14004cd72  mov     rax, [rsp+0C8h+var_48]
0x14004cd7a  mov     [rsp+0C8h+var_90], rax
0x14004cd7f  mov     dword ptr [rsp+0C8h+var_98], r11d
0x14004cd84  mov     byte ptr [rsp+0C8h+var_A0], r13b
0x14004cd89  mov     dword ptr [rsp+0C8h+var_A8], ebp
0x14004cd8d  call    NvmeSubmitIoToSQ
0x14004cd92  mov     r15d, eax
0x14004cd95  xor     bl, bl
0x14004cd97  cmp     r15d, 103h
0x14004cd9e  jz      loc_14004CF73
0x14004cda4  mov     rax, [r14+40h]
0x14004cda8  test    rax, rax
0x14004cdab  jz      short loc_14004CDCC
0x14004cdad  mov     rcx, [r14+48h]
0x14004cdb1  movzx   edx, word ptr [rax]
0x14004cdb4  shl     rdx, 7
0x14004cdb8  add     rdx, [rcx+20h]; ListEntry
0x14004cdbc  add     rcx, 40h ; '@'; ListHead
0x14004cdc0  call    cs:__imp_ExpInterlockedPushEntrySList
0x14004cdc7  nop     dword ptr [rax+rax+00h]
0x14004cdcc  mov     ecx, 80000000h
0x14004cdd1  lea     eax, [r15+rcx]
0x14004cdd5  test    ecx, eax
0x14004cdd7  jnz     loc_14004CF73
0x14004cddd  cmp     r15d, 80000011h
0x14004cde4  jz      loc_14004CF73
0x14004cdea  test    bl, bl
0x14004cdec  jz      short loc_14004CE4E
0x14004cdee  cmp     [rsp+0C8h+arg_0], 0
0x14004cdf6  jz      loc_14004CF73
0x14004cdfc  mov     rax, [rsi+0B8h]
0x14004ce03  mov     rcx, [rsp+0C8h+var_60]
0x14004ce08  mov     rbx, [rax+18h]
0x14004ce0c  mov     rdx, rbx
0x14004ce0f  mov     r14d, [rbx+70h]
0x14004ce13  call    FreeAllSglAndContextInChainedSplitIoContext
0x14004ce18  mov     rcx, [rsp+0C8h+var_60]
0x14004ce1d  mov     r9, rsi
0x14004ce20  mov     r8, rbx
0x14004ce23  mov     edx, ebp
0x14004ce25  call    FreeNVMeChainedIoSplitContext
0x14004ce2a  test    byte ptr [rsi+97h], 1
0x14004ce31  mov     [rsi+38h], r13
0x14004ce35  jz      short loc_14004CE45
0x14004ce37  mov     rax, [rdi+2B8h]
0x14004ce3e  mov     rdx, [rax+rbp*8]
0x14004ce42  lock dec dword ptr [rdx]
0x14004ce45  mov     [rsi+30h], r14d
0x14004ce49  jmp     loc_14004CED8
0x14004ce4e  movzx   ebx, byte ptr [r14+7Eh]
0x14004ce53  mov     cl, 2; NewIrql
0x14004ce55  and     bl, 1
0x14004ce58  call    cs:__imp_KfRaiseIrql
0x14004ce5f  nop     dword ptr [rax+rax+00h]
0x14004ce64  mov     rcx, [rsp+0C8h+var_40]
0x14004ce6c  xor     bl, 1
0x14004ce6f  movzx   r12d, al
0x14004ce73  movzx   r8d, bl
0x14004ce77  mov     rcx, [rcx+488h]
0x14004ce7e  mov     rdx, [rcx+8]
0x14004ce82  mov     rax, [rdx+60h]
0x14004ce86  mov     rdx, [rsp+0C8h+arg_10]
0x14004ce8e  call    _guard_dispatch_icall
0x14004ce93  cmp     r12b, 2
0x14004ce97  jnb     short loc_14004CEA9
0x14004ce99  movzx   ecx, r12b; NewIrql
0x14004ce9d  call    cs:__imp_KeLowerIrql
0x14004cea4  nop     dword ptr [rax+rax+00h]
0x14004cea9  mov     rcx, [rsp+0C8h+var_60]
0x14004ceae  mov     r8b, 1
0x14004ceb1  mov     rdx, r14
0x14004ceb4  call    FreeNVMeSGLBufferContext
0x14004ceb9  test    byte ptr [rsi+97h], 1
0x14004cec0  mov     [rsi+38h], r13
0x14004cec4  jz      short loc_14004CED4
0x14004cec6  mov     rax, [rdi+2B8h]
0x14004cecd  mov     rcx, [rax+rbp*8]
0x14004ced1  lock dec dword ptr [rcx]
0x14004ced4  mov     [rsi+30h], r15d
0x14004ced8  xor     edx, edx; PriorityBoost
0x14004ceda  mov     rcx, rsi; Irp
0x14004cedd  call    cs:__imp_IofCompleteRequest
0x14004cee4  nop     dword ptr [rax+rax+00h]
0x14004cee9  mov     rax, [rdi+80h]
0x14004cef0  cmp     byte ptr [rax], 0
0x14004cef3  jnz     short loc_14004CF73
0x14004cef5  mov     rax, [rax+18h]
0x14004cef9  mov     rdx, [rax+rbp*8]
0x14004cefd  mov     eax, 0FFFFFFFFh
0x14004cf02  lock xadd [rdx], eax
0x14004cf06  cmp     eax, 1
0x14004cf09  jnz     short loc_14004CF73
0x14004cf0b  mov     rax, [rdi+10h]
0x14004cf0f  mov     rcx, rdi
0x14004cf12  mov     rbx, [rax+80h]
0x14004cf19  call    NvmeNamespaceCheckAndAcquirePoFx
0x14004cf1e  test    al, al
0x14004cf20  jz      short loc_14004CF4C
0x14004cf22  mov     rax, [rdi+80h]
0x14004cf29  mov     r8d, 2
0x14004cf2f  xor     edx, edx
0x14004cf31  mov     rcx, [rax+8]
0x14004cf35  mov     rcx, [rcx]
0x14004cf38  call    cs:__imp_PoFxIdleComponent
0x14004cf3f  nop     dword ptr [rax+rax+00h]
0x14004cf44  mov     rcx, rdi
0x14004cf47  call    NvmeNamespaceReleasePoFx
0x14004cf4c  mov     rcx, [rbx+0A8h]
0x14004cf53  cmp     byte ptr [rcx], 1
0x14004cf56  jnz     short loc_14004CF73
0x14004cf58  mov     rcx, [rcx+8]
0x14004cf5c  mov     r8d, 2
0x14004cf62  xor     edx, edx
0x14004cf64  mov     rcx, [rcx]
0x14004cf67  call    cs:__imp_PoFxIdleComponent
0x14004cf6e  nop     dword ptr [rax+rax+00h]
0x14004cf73  mov     rbx, [rsp+0C8h+arg_8]
0x14004cf7b  add     rsp, 90h
0x14004cf82  pop     r15
0x14004cf84  pop     r14
0x14004cf86  pop     r13
0x14004cf88  pop     r12
0x14004cf8a  pop     rdi
0x14004cf8b  pop     rsi
0x14004cf8c  pop     rbp
0x14004cf8d  retn
```
