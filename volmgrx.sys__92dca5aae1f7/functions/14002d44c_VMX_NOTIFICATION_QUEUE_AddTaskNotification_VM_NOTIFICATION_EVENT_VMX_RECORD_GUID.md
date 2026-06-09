# VMX_NOTIFICATION_QUEUE::AddTaskNotification(_VM_NOTIFICATION_EVENT,VMX_RECORD *,_GUID *)

- ea: `0x14002d44c`
- end: `0x14002d755`
- name: `?AddTaskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_RECORD@@PEAU_GUID@@@Z`
- size: `777`
- prototype: `void __fastcall(__int64, int, __int64, struct _GUID *)`
- caller_count: `23`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x14002a3f4`
- `0x14002b7bc`
- `0x14002d3ec`
- `0x14002d75c`
- `0x14002dcb0`
- `0x14002e230`
- `0x14002f1e4`
- `0x14002fcfc`
- `0x140031180`
- `0x1400358f4`
- `0x140038468`
- `0x140051db4`
- `0x1400531c8`
- `0x1400534d8`
- `0x1400535cc`
- `0x140054b48`
- `0x140055878`
- `0x140057448`
- `0x1400578d0`
- `0x14005b250`
- `0x14005b3fc`
- `0x14005b4f8`
- `0x14005b62c`

## callees

- `0x140005f80`
- `0x140006584`
- `0x140006a90`
- `0x14001be80`
- `0x14002d44c`
- `0x14005ad20`
- `0x14005aea4`
- `0x14005afa8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002d6f2`
- `ntoskrnl!ExAllocatePool2` at `0x14002d6f2`

## pseudocode

```c
void __fastcall VMX_NOTIFICATION_QUEUE::AddTaskNotification(__int64 a1, int a2, __int64 a3, struct _GUID *a4)
{
  struct _GUID *v8; // rax
  struct _GUID *v9; // rbx
  VMX_NOTIFICATION_QUEUE *v10; // rcx
  struct _GUID v11; // xmm0
  struct _VM_QUERY_PACK_INFO_OUTPUT *v12; // rax
  struct _GUID v13; // xmm0
  __int64 v14; // rax
  __int64 v15; // rcx
  struct _GUID *v16; // r8
  __int64 v17; // rcx
  struct _GUID v18; // xmm0
  __int64 v19; // rdx
  struct _GUID v20; // xmm0
  __int64 v21; // rax
  struct _GUID v22; // xmm0
  struct _GUID v23; // xmm0
  __int64 v24; // rax
  __int64 v25; // rcx
  struct _GUID v26; // xmm0
  unsigned int VolumeInfoOutputSize; // esi
  struct _VM_QUERY_VOLUME_INFO_OUTPUT *Pool2; // rax
  struct _VM_QUERY_VOLUME_INFO_OUTPUT *v29; // r14
  struct _GUID **v30; // rdx
  struct _VM_QUERY_DISK_INFO_OUTPUT *v31; // [rsp+30h] [rbp-18h] BYREF
  struct _VM_QUERY_PACK_INFO_OUTPUT *v32; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v33; // [rsp+80h] [rbp+38h] BYREF

  v33 = 0;
  v32 = 0;
  v31 = 0;
  if ( *(_QWORD *)(a1 + 40) == a1 + 40 )
    return;
  v8 = (struct _GUID *)VMX_ALLOCATED_OBJECT::operator new(0x78u, 0x102u, 0x654E6D56u);
  v9 = v8;
  if ( !v8 )
    goto LABEL_42;
  memset(v8, 0, 0x78u);
  if ( a3 )
  {
    if ( *(_WORD *)(a3 + 32) != 1 )
    {
      if ( *(_WORD *)(a3 + 32) == 3 )
      {
        *(_DWORD *)v9[1].Data4 = 2;
        v19 = *(_QWORD *)(*(_QWORD *)(a3 + 8LL * (*(_WORD *)(a3 + 64) & 1) + 40) + 152LL);
        v20 = *(struct _GUID *)(*(_QWORD *)(v19 + 8LL * (*(_WORD *)(v19 + 64) & 1) + 40) + 72LL);
        v9[2] = v20;
        v21 = *(_QWORD *)(v19 + 40);
        if ( v21 )
          v20 = *(struct _GUID *)(v21 + 72);
        v16 = v9 + 5;
        v9[3] = v20;
        v17 = *(_QWORD *)(*(_QWORD *)(a3 + 16) + 8LL);
        v22 = *(struct _GUID *)(v17 + 8);
        v9[5] = v22;
        if ( a4 )
          v22 = *a4;
        v9[4] = v22;
        *(_DWORD *)&v9[1].Data4[4] = 3;
        goto LABEL_28;
      }
      v10 = (VMX_NOTIFICATION_QUEUE *)((unsigned int)*(unsigned __int16 *)(a3 + 32) - 4);
      if ( *(_WORD *)(a3 + 32) != 4 )
      {
        if ( *(_WORD *)(a3 + 32) != 5 )
          goto LABEL_39;
        *(_DWORD *)v9[1].Data4 = 1;
        v11 = *(struct _GUID *)(*(_QWORD *)(a3 + 8LL * (*(_WORD *)(a3 + 64) & 1) + 40) + 72LL);
        v9[2] = v11;
        if ( a4 )
          v11 = *a4;
        *(_DWORD *)&v9[1].Data4[4] = a2;
        v9[3] = v11;
        if ( ((a2 - 1) & 0xFFFFFFFD) != 0 )
          goto LABEL_39;
        if ( VMX_NOTIFICATION_QUEUE::GetPackAdditionalInfo(v10, v9 + 2, &v32, &v33) != -1073741670 )
        {
          v12 = v32;
LABEL_14:
          *(_QWORD *)v9[6].Data4 = v12;
          v9[7].Data1 = v33;
          goto LABEL_39;
        }
        goto LABEL_42;
      }
      *(_DWORD *)v9[1].Data4 = 2;
      v13 = *(struct _GUID *)(*(_QWORD *)(a3 + 8LL * (*(_WORD *)(a3 + 64) & 1) + 40) + 72LL);
      v9[2] = v13;
      v14 = *(_QWORD *)(a3 + 40);
      if ( !v14 )
      {
        v15 = *(_QWORD *)(a3 + 56);
        if ( !v15 )
        {
LABEL_19:
          v16 = v9 + 5;
          v9[3] = v13;
          v17 = *(_QWORD *)(*(_QWORD *)(a3 + 16) + 8LL);
          v18 = *(struct _GUID *)(v17 + 8);
          v9[5] = v18;
          if ( a4 )
            v18 = *a4;
          *(_DWORD *)&v9[1].Data4[4] = a2;
          v9[4] = v18;
          if ( ((a2 - 1) & 0xFFFFFFFD) != 0 )
            goto LABEL_39;
          v19 = a3;
LABEL_28:
          if ( VMX_NOTIFICATION_QUEUE::GetDiskAdditionalInfo(
                 (VMX_NOTIFICATION_QUEUE *)v17,
                 (struct VMX_RECORD *)v19,
                 v16,
                 &v31,
                 &v33) != -1073741670 )
          {
            v12 = v31;
            goto LABEL_14;
          }
LABEL_42:
          VMX_NOTIFICATION_QUEUE::ResetNotificationQueue((VMX_NOTIFICATION_QUEUE *)a1);
          return;
        }
        v14 = *(_QWORD *)(v15 + 8LL * (*(_WORD *)(v15 + 64) & 1) + 40);
      }
      v13 = *(struct _GUID *)(v14 + 72);
      goto LABEL_19;
    }
    *(_DWORD *)v9[1].Data4 = 3;
    v23 = *(struct _GUID *)(*(_QWORD *)(a3 + 8LL * (*(_WORD *)(a3 + 64) & 1) + 40) + 232LL);
    v9[2] = v23;
    v24 = *(_QWORD *)(a3 + 40);
    if ( !v24 )
    {
      v25 = *(_QWORD *)(a3 + 56);
      if ( !v25 )
        goto LABEL_34;
      v24 = *(_QWORD *)(v25 + 8LL * (*(_WORD *)(v25 + 64) & 1) + 40);
    }
    v23 = *(struct _GUID *)(v24 + 232);
LABEL_34:
    v9[3] = v23;
    v26 = *(struct _GUID *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 8LL) + 8LL);
    v9[5] = v26;
    if ( a4 )
      v26 = *a4;
    *(_DWORD *)&v9[1].Data4[4] = a2;
    v9[4] = v26;
    if ( ((a2 - 1) & 0xFFFFFFFD) != 0 )
      goto LABEL_39;
    VolumeInfoOutputSize = VmxpGetVolumeInfoOutputSize((struct VMX_RECORD *)a3);
    Pool2 = (struct _VM_QUERY_VOLUME_INFO_OUTPUT *)ExAllocatePool2(258, VolumeInfoOutputSize, 1699638614);
    v29 = Pool2;
    if ( Pool2 )
    {
      VmxpFillVolumeInfoOutputBuffer((struct VMX_RECORD *)a3, Pool2, VolumeInfoOutputSize);
      *(_QWORD *)v9[6].Data4 = v29;
      v9[7].Data1 = VolumeInfoOutputSize;
      goto LABEL_39;
    }
    goto LABEL_42;
  }
  *(_DWORD *)v9[1].Data4 = 4;
  v9[2].Data1 = *(_DWORD *)(a1 + 4);
  *(_DWORD *)&v9[1].Data4[4] = a2;
LABEL_39:
  v30 = *(struct _GUID ***)(a1 + 16);
  if ( *v30 != (struct _GUID *)(a1 + 8) )
    __fastfail(3u);
  *(_QWORD *)&v9->Data1 = a1 + 8;
  *(_QWORD *)v9->Data4 = v30;
  *v30 = v9;
  *(_QWORD *)(a1 + 16) = v9;
}

```

## disassembly

```asm
0x14002d44c  push    rbp
0x14002d44e  push    rbx
0x14002d44f  push    rsi
0x14002d450  push    rdi
0x14002d451  push    r14
0x14002d453  push    r15
0x14002d455  mov     rbp, rsp
0x14002d458  sub     rsp, 48h
0x14002d45c  lea     rax, [rcx+28h]
0x14002d460  mov     [rbp+arg_0], 0
0x14002d467  mov     r14, r9
0x14002d46a  mov     rdi, r8
0x14002d46d  mov     esi, edx
0x14002d46f  mov     r15, rcx
0x14002d472  mov     [rbp+var_10], 0
0x14002d47a  mov     [rbp+var_18], 0
0x14002d482  cmp     [rax], rax
0x14002d485  jz      loc_14002D747
0x14002d48b  mov     edx, 102h; unsigned __int64
0x14002d490  mov     ecx, 78h ; 'x'; unsigned __int64
0x14002d495  mov     r8d, 654E6D56h; unsigned int
0x14002d49b  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002d4a0  mov     rbx, rax
0x14002d4a3  test    rax, rax
0x14002d4a6  jz      loc_14002D73F
0x14002d4ac  xor     edx, edx; Val
0x14002d4ae  mov     rcx, rax; void *
0x14002d4b1  lea     r8d, [rdx+78h]; Size
0x14002d4b5  call    memset
0x14002d4ba  test    rdi, rdi
0x14002d4bd  jnz     short loc_14002D4D5
0x14002d4bf  mov     dword ptr [rbx+18h], 4
0x14002d4c6  mov     ecx, [r15+4]
0x14002d4ca  mov     [rbx+20h], ecx
0x14002d4cd  mov     [rbx+1Ch], esi
0x14002d4d0  jmp     loc_14002D71B
0x14002d4d5  movzx   ecx, word ptr [rdi+20h]
0x14002d4d9  sub     ecx, 1
0x14002d4dc  jz      loc_14002D666
0x14002d4e2  mov     eax, 2
0x14002d4e7  sub     ecx, eax
0x14002d4e9  jz      loc_14002D5D9
0x14002d4ef  sub     ecx, 1; this
0x14002d4f2  jz      short loc_14002D561
0x14002d4f4  cmp     ecx, 1
0x14002d4f7  jnz     loc_14002D71B
0x14002d4fd  mov     [rbx+18h], ecx
0x14002d500  lea     rdx, [rbx+20h]; struct _GUID *
0x14002d504  movzx   eax, word ptr [rdi+40h]
0x14002d508  and     eax, ecx
0x14002d50a  mov     rax, [rdi+rax*8+28h]
0x14002d50f  movups  xmm0, xmmword ptr [rax+48h]
0x14002d513  movdqu  xmmword ptr [rdx], xmm0
0x14002d517  test    r14, r14
0x14002d51a  jz      short loc_14002D520
0x14002d51c  movups  xmm0, xmmword ptr [r14]
0x14002d520  lea     eax, [rsi-1]
0x14002d523  mov     [rbx+1Ch], esi
0x14002d526  movdqu  xmmword ptr [rbx+30h], xmm0
0x14002d52b  test    eax, 0FFFFFFFDh
0x14002d530  jnz     loc_14002D71B
0x14002d536  lea     r9, [rbp+arg_0]; unsigned int *
0x14002d53a  lea     r8, [rbp+var_10]; struct _VM_QUERY_PACK_INFO_OUTPUT **
0x14002d53e  call    ?GetPackAdditionalInfo@VMX_NOTIFICATION_QUEUE@@AEAAJPEAU_GUID@@PEAPEAU_VM_QUERY_PACK_INFO_OUTPUT@@PEAK@Z; VMX_NOTIFICATION_QUEUE::GetPackAdditionalInfo(_GUID *,_VM_QUERY_PACK_INFO_OUTPUT * *,ulong *)
0x14002d543  cmp     eax, 0C000009Ah
0x14002d548  jz      loc_14002D73F
0x14002d54e  mov     rax, [rbp+var_10]
0x14002d552  mov     [rbx+68h], rax
0x14002d556  mov     eax, [rbp+arg_0]
0x14002d559  mov     [rbx+70h], eax
0x14002d55c  jmp     loc_14002D71B
0x14002d561  mov     [rbx+18h], eax
0x14002d564  movzx   eax, word ptr [rdi+40h]
0x14002d568  and     eax, 1
0x14002d56b  mov     rax, [rdi+rax*8+28h]
0x14002d570  movups  xmm0, xmmword ptr [rax+48h]
0x14002d574  movdqu  xmmword ptr [rbx+20h], xmm0
0x14002d579  mov     rax, [rdi+28h]
0x14002d57d  test    rax, rax
0x14002d580  jnz     short loc_14002D597
0x14002d582  mov     rcx, [rdi+38h]
0x14002d586  test    rcx, rcx
0x14002d589  jz      short loc_14002D59B
0x14002d58b  movzx   eax, word ptr [rcx+40h]
0x14002d58f  and     eax, 1
0x14002d592  mov     rax, [rcx+rax*8+28h]
0x14002d597  movups  xmm0, xmmword ptr [rax+48h]
0x14002d59b  lea     r8, [rbx+50h]
0x14002d59f  movdqu  xmmword ptr [rbx+30h], xmm0
0x14002d5a4  mov     rax, [rdi+10h]
0x14002d5a8  mov     rcx, [rax+8]
0x14002d5ac  movups  xmm0, xmmword ptr [rcx+8]
0x14002d5b0  movdqu  xmmword ptr [r8], xmm0
0x14002d5b5  test    r14, r14
0x14002d5b8  jz      short loc_14002D5BE
0x14002d5ba  movups  xmm0, xmmword ptr [r14]
0x14002d5be  lea     eax, [rsi-1]
0x14002d5c1  mov     [rbx+1Ch], esi
0x14002d5c4  movdqu  xmmword ptr [rbx+40h], xmm0
0x14002d5c9  test    eax, 0FFFFFFFDh
0x14002d5ce  jnz     loc_14002D71B
0x14002d5d4  mov     rdx, rdi
0x14002d5d7  jmp     short loc_14002D640
0x14002d5d9  mov     [rbx+18h], eax
0x14002d5dc  movzx   eax, word ptr [rdi+40h]
0x14002d5e0  and     eax, 1
0x14002d5e3  mov     rax, [rdi+rax*8+28h]
0x14002d5e8  mov     rdx, [rax+98h]; struct VMX_RECORD *
0x14002d5ef  movzx   eax, word ptr [rdx+40h]
0x14002d5f3  and     eax, 1
0x14002d5f6  mov     rax, [rdx+rax*8+28h]
0x14002d5fb  movups  xmm0, xmmword ptr [rax+48h]
0x14002d5ff  movdqu  xmmword ptr [rbx+20h], xmm0
0x14002d604  mov     rax, [rdx+28h]
0x14002d608  test    rax, rax
0x14002d60b  jz      short loc_14002D611
0x14002d60d  movups  xmm0, xmmword ptr [rax+48h]
0x14002d611  lea     r8, [rbx+50h]; struct _GUID *
0x14002d615  movdqu  xmmword ptr [rbx+30h], xmm0
0x14002d61a  mov     rax, [rdi+10h]
0x14002d61e  mov     rcx, [rax+8]; this
0x14002d622  movups  xmm0, xmmword ptr [rcx+8]
0x14002d626  movdqu  xmmword ptr [r8], xmm0
0x14002d62b  test    r14, r14
0x14002d62e  jz      short loc_14002D634
0x14002d630  movups  xmm0, xmmword ptr [r14]
0x14002d634  movdqu  xmmword ptr [rbx+40h], xmm0
0x14002d639  mov     dword ptr [rbx+1Ch], 3
0x14002d640  lea     rax, [rbp+arg_0]
0x14002d644  lea     r9, [rbp+var_18]; struct _VM_QUERY_DISK_INFO_OUTPUT **
0x14002d648  mov     [rsp+48h+var_28], rax; unsigned int *
0x14002d64d  call    ?GetDiskAdditionalInfo@VMX_NOTIFICATION_QUEUE@@AEAAJPEAVVMX_RECORD@@PEAU_GUID@@PEAPEAU_VM_QUERY_DISK_INFO_OUTPUT@@PEAK@Z; VMX_NOTIFICATION_QUEUE::GetDiskAdditionalInfo(VMX_RECORD *,_GUID *,_VM_QUERY_DISK_INFO_OUTPUT * *,ulong *)
0x14002d652  cmp     eax, 0C000009Ah
0x14002d657  jz      loc_14002D73F
0x14002d65d  mov     rax, [rbp+var_18]
0x14002d661  jmp     loc_14002D552
0x14002d666  mov     dword ptr [rbx+18h], 3
0x14002d66d  movzx   eax, word ptr [rdi+40h]
0x14002d671  and     eax, 1
0x14002d674  mov     rax, [rdi+rax*8+28h]
0x14002d679  movups  xmm0, xmmword ptr [rax+0E8h]
0x14002d680  movdqu  xmmword ptr [rbx+20h], xmm0
0x14002d685  mov     rax, [rdi+28h]
0x14002d689  test    rax, rax
0x14002d68c  jnz     short loc_14002D6A3
0x14002d68e  mov     rcx, [rdi+38h]
0x14002d692  test    rcx, rcx
0x14002d695  jz      short loc_14002D6AA
0x14002d697  movzx   eax, word ptr [rcx+40h]
0x14002d69b  and     eax, 1
0x14002d69e  mov     rax, [rcx+rax*8+28h]
0x14002d6a3  movups  xmm0, xmmword ptr [rax+0E8h]
0x14002d6aa  movdqu  xmmword ptr [rbx+30h], xmm0
0x14002d6af  mov     rax, [rdi+10h]
0x14002d6b3  mov     rcx, [rax+8]
0x14002d6b7  movups  xmm0, xmmword ptr [rcx+8]
0x14002d6bb  movdqu  xmmword ptr [rbx+50h], xmm0
0x14002d6c0  test    r14, r14
0x14002d6c3  jz      short loc_14002D6C9
0x14002d6c5  movups  xmm0, xmmword ptr [r14]
0x14002d6c9  lea     eax, [rsi-1]
0x14002d6cc  mov     [rbx+1Ch], esi
0x14002d6cf  movdqu  xmmword ptr [rbx+40h], xmm0
0x14002d6d4  test    eax, 0FFFFFFFDh
0x14002d6d9  jnz     short loc_14002D71B
0x14002d6db  mov     rcx, rdi; struct VMX_RECORD *
0x14002d6de  call    ?VmxpGetVolumeInfoOutputSize@@YAKPEAVVMX_RECORD@@@Z; VmxpGetVolumeInfoOutputSize(VMX_RECORD *)
0x14002d6e3  mov     edx, eax
0x14002d6e5  mov     ecx, 102h
0x14002d6ea  mov     r8d, 654E6D56h
0x14002d6f0  mov     esi, eax
0x14002d6f2  call    cs:__imp_ExAllocatePool2
0x14002d6f9  nop     dword ptr [rax+rax+00h]
0x14002d6fe  mov     r14, rax
0x14002d701  test    rax, rax
0x14002d704  jz      short loc_14002D73F
0x14002d706  mov     r8d, esi; unsigned int
0x14002d709  mov     rdx, rax; struct _VM_QUERY_VOLUME_INFO_OUTPUT *
0x14002d70c  mov     rcx, rdi; struct VMX_RECORD *
0x14002d70f  call    ?VmxpFillVolumeInfoOutputBuffer@@YAJPEAVVMX_RECORD@@PEAU_VM_QUERY_VOLUME_INFO_OUTPUT@@K@Z; VmxpFillVolumeInfoOutputBuffer(VMX_RECORD *,_VM_QUERY_VOLUME_INFO_OUTPUT *,ulong)
0x14002d714  mov     [rbx+68h], r14
0x14002d718  mov     [rbx+70h], esi
0x14002d71b  lea     rax, [r15+8]
0x14002d71f  mov     rdx, [rax+8]
0x14002d723  cmp     [rdx], rax
0x14002d726  jz      short loc_14002D72F
0x14002d728  mov     ecx, 3
0x14002d72d  int     29h; Win8: RtlFailFast(ecx)
0x14002d72f  mov     [rbx], rax
0x14002d732  mov     [rbx+8], rdx
0x14002d736  mov     [rdx], rbx
0x14002d739  mov     [rax+8], rbx
0x14002d73d  jmp     short loc_14002D747
0x14002d73f  mov     rcx, r15; this
0x14002d742  call    ?ResetNotificationQueue@VMX_NOTIFICATION_QUEUE@@QEAAXXZ; VMX_NOTIFICATION_QUEUE::ResetNotificationQueue(void)
0x14002d747  add     rsp, 48h
0x14002d74b  pop     r15
0x14002d74d  pop     r14
0x14002d74f  pop     rdi
0x14002d750  pop     rsi
0x14002d751  pop     rbx
0x14002d752  pop     rbp
0x14002d753  retn
```
