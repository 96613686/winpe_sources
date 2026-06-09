# SpDriveReadyCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003b610`
- end: `0x14003b8c2`
- name: `?SpDriveReadyCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `690`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14001d3f0`
- `0x14002e4a8`
- `0x1400322e4`
- `0x14003258c`
- `0x14003b610`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b822`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b822`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003b816`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003b816`
- `ntoskrnl!IofCompleteRequest` at `0x14003b863`
- `ntoskrnl!IofCompleteRequest` at `0x14003b863`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003b88f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003b88f`

## pseudocode

```c
__int64 __fastcall SpDriveReadyCallback(
        struct _DEVICE_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        void *a4)
{
  int v4; // ebx
  int i; // r13d
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY *v8; // r8
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY **p_Flink; // rax
  int v11; // r14d
  char *DeviceExtension; // rcx
  _QWORD *v13; // rdi
  char v14; // r12
  _QWORD *v15; // rbx
  struct _LIST_ENTRY *v16; // rdx
  struct _LIST_ENTRY *v17; // r8
  struct _LIST_ENTRY *v18; // r9
  char *v19; // rcx
  struct _LIST_ENTRY *v20; // rax
  struct _LIST_ENTRY **v21; // rax
  __int64 *v22; // rcx
  __int64 *v23; // rax
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp-28h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-20h] BYREF
  struct _LIST_ENTRY *v27; // [rsp+40h] [rbp-18h]
  int v28; // [rsp+A8h] [rbp+50h]

  Interval.QuadPart = -2000000;
  v27 = (struct _LIST_ENTRY *)&v26;
  v4 = 0;
  v28 = 0;
  v26 = (__int64 *)&v26;
  for ( i = 30000; ; i -= 200 )
  {
    Flink = a2->Flink;
    if ( a2->Flink != a2 )
    {
      do
      {
        v8 = Flink->Flink;
        if ( !Flink[1].Flink[2].Blink[4].Flink[202].Flink )
        {
          LODWORD(Flink[-8].Blink) = -1073741810;
          if ( v8->Blink != Flink
            || (Blink = Flink->Blink, Blink->Flink != Flink)
            || (Blink->Flink = v8, v8->Blink = Blink, p_Flink = &v27->Flink, (__int64 **)v27->Flink != &v26) )
          {
LABEL_42:
            __fastfail(3u);
          }
          Flink->Blink = v27;
          Flink->Flink = (struct _LIST_ENTRY *)&v26;
          *p_Flink = Flink;
          v27 = Flink;
        }
        Flink = v8;
      }
      while ( v8 != a2 );
    }
    v11 = 0;
    SpAcquireResourceShared((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96), 0);
    DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
    v13 = (_QWORD *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 26);
    if ( v13 != (_QWORD *)WPP_MAIN_CB.DeviceExtension + 26 )
    {
      do
      {
        v14 = 1;
        v15 = (_QWORD *)v13[2];
        if ( v15 == v13 + 2 )
          goto LABEL_21;
        do
        {
          if ( *((_DWORD *)v15 - 18) == 1 )
          {
            if ( i > 0 )
            {
              ++v11;
              v14 = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              {
                WPP_SF__guid__guid_(
                  WPP_GLOBAL_Control->AttachedDevice,
                  58,
                  (unsigned int)WPP_c4a5d22d2cc233e7d4f9a274e892dd73_Traceguids,
                  (_DWORD)v15 - 124,
                  (__int64)v15 - 140);
              }
              *((_DWORD *)v15 - 18) = 2;
            }
          }
          v15 = (_QWORD *)*v15;
        }
        while ( v15 != v13 + 2 );
        if ( v14 )
        {
LABEL_21:
          v16 = a2->Flink;
          if ( a2->Flink != a2 )
          {
            do
            {
              v17 = v16->Flink;
              v18 = v16[1].Flink[2].Blink[4].Flink;
              v19 = (char *)v18[2].Flink - *(_QWORD *)((char *)v13 + 108);
              if ( !v19 )
                v19 = (char *)v18[2].Blink - *(_QWORD *)((char *)v13 + 116);
              if ( !v19 )
              {
                LODWORD(v16[-8].Blink) = 0;
                if ( v17->Blink != v16 )
                  goto LABEL_42;
                v20 = v16->Blink;
                if ( v20->Flink != v16 )
                  goto LABEL_42;
                v20->Flink = v17;
                v17->Blink = v20;
                v21 = &v27->Flink;
                if ( (__int64 **)v27->Flink != &v26 )
                  goto LABEL_42;
                v16->Blink = v27;
                v16->Flink = (struct _LIST_ENTRY *)&v26;
                *v21 = v16;
                v27 = v16;
              }
              v16 = v17;
            }
            while ( v17 != a2 );
          }
          SP_POOL::PauseTasks((SP_POOL *)v13);
          SP_POOL::ResumeTasks((SP_POOL *)v13);
        }
        DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
        v13 = (_QWORD *)*v13;
      }
      while ( v13 != (_QWORD *)WPP_MAIN_CB.DeviceExtension + 26 );
      v4 = v28;
    }
    ExReleaseResourceLite((PERESOURCE)(DeviceExtension + 96));
    KeLeaveCriticalRegion();
    while ( 1 )
    {
      v22 = v26;
      if ( v26 == (__int64 *)&v26 )
        break;
      if ( (__int64 **)v26[1] != &v26 )
        goto LABEL_42;
      v23 = (__int64 *)*v26;
      if ( *(__int64 **)(*v26 + 8) != v26 )
        goto LABEL_42;
      v26 = (__int64 *)*v26;
      v23[1] = (__int64)&v26;
      IofCompleteRequest((PIRP)(v22 - 21), 0);
    }
    if ( !v11 )
      break;
    if ( v11 != v4 )
    {
      v4 = v11;
      i = 30000;
      v28 = v11;
    }
    KeDelayExecutionThread(0, 0, &Interval);
  }
  return 0;
}

```

## disassembly

```asm
0x14003b610  push    rbp
0x14003b612  push    rbx
0x14003b613  push    rsi
0x14003b614  push    rdi
0x14003b615  push    r12
0x14003b617  push    r13
0x14003b619  push    r14
0x14003b61b  push    r15
0x14003b61d  mov     rbp, rsp
0x14003b620  sub     rsp, 58h
0x14003b624  lea     rax, [rbp+var_20]
0x14003b628  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFE17B80h
0x14003b630  mov     [rbp+var_18], rax
0x14003b634  xor     ebx, ebx
0x14003b636  lea     rax, [rbp+var_20]
0x14003b63a  mov     [rbp+arg_8], ebx
0x14003b63d  mov     [rbp+var_20], rax
0x14003b641  mov     r15, rdx
0x14003b644  mov     r13d, 7530h
0x14003b64a  mov     rdx, [r15]
0x14003b64d  cmp     rdx, r15
0x14003b650  jz      short loc_14003B6BB
0x14003b652  mov     rax, [rdx+10h]
0x14003b656  mov     r8, [rdx]
0x14003b659  mov     rcx, [rax+28h]
0x14003b65d  mov     rax, [rcx+40h]
0x14003b661  cmp     qword ptr [rax+0CA0h], 0
0x14003b669  jnz     short loc_14003B6B3
0x14003b66b  mov     dword ptr [rdx-78h], 0C000000Eh
0x14003b672  cmp     [r8+8], rdx
0x14003b676  jnz     loc_14003B8A7
0x14003b67c  mov     rax, [rdx+8]
0x14003b680  cmp     [rax], rdx
0x14003b683  jnz     loc_14003B8A7
0x14003b689  mov     [rax], r8
0x14003b68c  lea     rcx, [rbp+var_20]
0x14003b690  mov     [r8+8], rax
0x14003b694  mov     rax, [rbp+var_18]
0x14003b698  cmp     [rax], rcx
0x14003b69b  jnz     loc_14003B8A7
0x14003b6a1  mov     [rdx+8], rax
0x14003b6a5  lea     rcx, [rbp+var_20]
0x14003b6a9  mov     [rdx], rcx
0x14003b6ac  mov     [rax], rdx
0x14003b6af  mov     [rbp+var_18], rdx
0x14003b6b3  mov     rdx, r8
0x14003b6b6  cmp     r8, r15
0x14003b6b9  jnz     short loc_14003B652
0x14003b6bb  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003b6c2  xor     edx, edx; unsigned __int8
0x14003b6c4  add     rcx, 60h ; '`'; Resource
0x14003b6c8  xor     r14d, r14d
0x14003b6cb  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x14003b6d0  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003b6d7  lea     rax, [rcx+0D0h]
0x14003b6de  mov     rdi, [rax]
0x14003b6e1  cmp     rdi, rax
0x14003b6e4  jz      loc_14003B812
0x14003b6ea  lea     rsi, [rdi+10h]
0x14003b6ee  mov     r12b, 1
0x14003b6f1  mov     rbx, [rsi]
0x14003b6f4  cmp     rbx, rsi
0x14003b6f7  jz      short loc_14003B76B
0x14003b6f9  cmp     dword ptr [rbx-48h], 1
0x14003b6fd  jnz     short loc_14003B75A
0x14003b6ff  test    r13d, r13d
0x14003b702  jg      short loc_14003B754
0x14003b704  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b70b  lea     rax, WPP_GLOBAL_Control
0x14003b712  cmp     rcx, rax
0x14003b715  jz      short loc_14003B74B
0x14003b717  test    dword ptr [rcx+2Ch], 400h
0x14003b71e  jz      short loc_14003B74B
0x14003b720  cmp     byte ptr [rcx+29h], 3
0x14003b724  jb      short loc_14003B74B
0x14003b726  mov     rcx, [rcx+18h]
0x14003b72a  lea     rax, [rbx-8Ch]
0x14003b731  lea     r9, [rbx-7Ch]
0x14003b735  mov     [rsp+58h+var_38], rax
0x14003b73a  mov     edx, 3Ah ; ':'
0x14003b73f  lea     r8, WPP_c4a5d22d2cc233e7d4f9a274e892dd73_Traceguids
0x14003b746  call    WPP_SF__guid__guid_
0x14003b74b  mov     dword ptr [rbx-48h], 2
0x14003b752  jmp     short loc_14003B75A
0x14003b754  inc     r14d
0x14003b757  xor     r12b, r12b
0x14003b75a  mov     rbx, [rbx]
0x14003b75d  cmp     rbx, rsi
0x14003b760  jnz     short loc_14003B6F9
0x14003b762  test    r12b, r12b
0x14003b765  jz      loc_14003B7F5
0x14003b76b  mov     rdx, [r15]
0x14003b76e  cmp     rdx, r15
0x14003b771  jz      short loc_14003B7E5
0x14003b773  mov     rax, [rdx+10h]
0x14003b777  mov     r8, [rdx]
0x14003b77a  mov     rcx, [rax+28h]
0x14003b77e  mov     r9, [rcx+40h]
0x14003b782  mov     rcx, [r9+20h]
0x14003b786  sub     rcx, [rdi+6Ch]
0x14003b78a  jnz     short loc_14003B794
0x14003b78c  mov     rcx, [r9+28h]
0x14003b790  sub     rcx, [rdi+74h]
0x14003b794  test    rcx, rcx
0x14003b797  jnz     short loc_14003B7DD
0x14003b799  mov     [rdx-78h], ecx
0x14003b79c  cmp     [r8+8], rdx
0x14003b7a0  jnz     loc_14003B8A7
0x14003b7a6  mov     rax, [rdx+8]
0x14003b7aa  cmp     [rax], rdx
0x14003b7ad  jnz     loc_14003B8A7
0x14003b7b3  mov     [rax], r8
0x14003b7b6  lea     rcx, [rbp+var_20]
0x14003b7ba  mov     [r8+8], rax
0x14003b7be  mov     rax, [rbp+var_18]
0x14003b7c2  cmp     [rax], rcx
0x14003b7c5  jnz     loc_14003B8A7
0x14003b7cb  mov     [rdx+8], rax
0x14003b7cf  lea     rcx, [rbp+var_20]
0x14003b7d3  mov     [rdx], rcx
0x14003b7d6  mov     [rax], rdx
0x14003b7d9  mov     [rbp+var_18], rdx
0x14003b7dd  mov     rdx, r8
0x14003b7e0  cmp     r8, r15
0x14003b7e3  jnz     short loc_14003B773
0x14003b7e5  mov     rcx, rdi; this
0x14003b7e8  call    ?PauseTasks@SP_POOL@@QEAAXXZ; SP_POOL::PauseTasks(void)
0x14003b7ed  mov     rcx, rdi; this
0x14003b7f0  call    ?ResumeTasks@SP_POOL@@QEAAXXZ; SP_POOL::ResumeTasks(void)
0x14003b7f5  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003b7fc  mov     rdi, [rdi]
0x14003b7ff  lea     rax, [rcx+0D0h]
0x14003b806  cmp     rdi, rax
0x14003b809  jnz     loc_14003B6EA
0x14003b80f  mov     ebx, [rbp+arg_8]
0x14003b812  add     rcx, 60h ; '`'; Resource
0x14003b816  call    cs:__imp_ExReleaseResourceLite
0x14003b81d  nop     dword ptr [rax+rax+00h]
0x14003b822  call    cs:__imp_KeLeaveCriticalRegion
0x14003b829  nop     dword ptr [rax+rax+00h]
0x14003b82e  mov     rcx, [rbp+var_20]
0x14003b832  lea     rax, [rbp+var_20]
0x14003b836  cmp     rcx, rax
0x14003b839  jz      short loc_14003B871
0x14003b83b  lea     rax, [rbp+var_20]
0x14003b83f  cmp     [rcx+8], rax
0x14003b843  jnz     short loc_14003B8A7
0x14003b845  mov     rax, [rcx]
0x14003b848  cmp     [rax+8], rcx
0x14003b84c  jnz     short loc_14003B8A7
0x14003b84e  lea     rdx, [rbp+var_20]
0x14003b852  mov     [rbp+var_20], rax
0x14003b856  mov     [rax+8], rdx
0x14003b85a  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14003b861  xor     edx, edx; PriorityBoost
0x14003b863  call    cs:__imp_IofCompleteRequest
0x14003b86a  nop     dword ptr [rax+rax+00h]
0x14003b86f  jmp     short loc_14003B82E
0x14003b871  test    r14d, r14d
0x14003b874  jz      short loc_14003B8AE
0x14003b876  cmp     r14d, ebx
0x14003b879  jz      short loc_14003B887
0x14003b87b  mov     ebx, r14d
0x14003b87e  mov     r13d, 7530h
0x14003b884  mov     [rbp+arg_8], ebx
0x14003b887  lea     r8, [rbp+Interval]; Interval
0x14003b88b  xor     edx, edx; Alertable
0x14003b88d  xor     ecx, ecx; WaitMode
0x14003b88f  call    cs:__imp_KeDelayExecutionThread
0x14003b896  nop     dword ptr [rax+rax+00h]
0x14003b89b  sub     r13d, 0C8h
0x14003b8a2  jmp     loc_14003B64A
0x14003b8a7  mov     ecx, 3
0x14003b8ac  int     29h; Win8: RtlFailFast(ecx)
0x14003b8ae  xor     eax, eax
0x14003b8b0  add     rsp, 58h
0x14003b8b4  pop     r15
0x14003b8b6  pop     r14
0x14003b8b8  pop     r13
0x14003b8ba  pop     r12
0x14003b8bc  pop     rdi
0x14003b8bd  pop     rsi
0x14003b8be  pop     rbx
0x14003b8bf  pop     rbp
0x14003b8c0  retn
```
