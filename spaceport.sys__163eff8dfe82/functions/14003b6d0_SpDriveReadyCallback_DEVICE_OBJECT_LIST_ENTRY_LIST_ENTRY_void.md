# SpDriveReadyCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003b6d0`
- end: `0x14003b982`
- name: `?SpDriveReadyCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `690`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14001d3f0`
- `0x14002e4a8`
- `0x140032354`
- `0x1400325fc`
- `0x14003b6d0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b8e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b8e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003b8d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003b8d6`
- `ntoskrnl!IofCompleteRequest` at `0x14003b923`
- `ntoskrnl!IofCompleteRequest` at `0x14003b923`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003b94f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003b94f`

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
0x14003b6d0  push    rbp
0x14003b6d2  push    rbx
0x14003b6d3  push    rsi
0x14003b6d4  push    rdi
0x14003b6d5  push    r12
0x14003b6d7  push    r13
0x14003b6d9  push    r14
0x14003b6db  push    r15
0x14003b6dd  mov     rbp, rsp
0x14003b6e0  sub     rsp, 58h
0x14003b6e4  lea     rax, [rbp+var_20]
0x14003b6e8  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFE17B80h
0x14003b6f0  mov     [rbp+var_18], rax
0x14003b6f4  xor     ebx, ebx
0x14003b6f6  lea     rax, [rbp+var_20]
0x14003b6fa  mov     [rbp+arg_8], ebx
0x14003b6fd  mov     [rbp+var_20], rax
0x14003b701  mov     r15, rdx
0x14003b704  mov     r13d, 7530h
0x14003b70a  mov     rdx, [r15]
0x14003b70d  cmp     rdx, r15
0x14003b710  jz      short loc_14003B77B
0x14003b712  mov     rax, [rdx+10h]
0x14003b716  mov     r8, [rdx]
0x14003b719  mov     rcx, [rax+28h]
0x14003b71d  mov     rax, [rcx+40h]
0x14003b721  cmp     qword ptr [rax+0CA0h], 0
0x14003b729  jnz     short loc_14003B773
0x14003b72b  mov     dword ptr [rdx-78h], 0C000000Eh
0x14003b732  cmp     [r8+8], rdx
0x14003b736  jnz     loc_14003B967
0x14003b73c  mov     rax, [rdx+8]
0x14003b740  cmp     [rax], rdx
0x14003b743  jnz     loc_14003B967
0x14003b749  mov     [rax], r8
0x14003b74c  lea     rcx, [rbp+var_20]
0x14003b750  mov     [r8+8], rax
0x14003b754  mov     rax, [rbp+var_18]
0x14003b758  cmp     [rax], rcx
0x14003b75b  jnz     loc_14003B967
0x14003b761  mov     [rdx+8], rax
0x14003b765  lea     rcx, [rbp+var_20]
0x14003b769  mov     [rdx], rcx
0x14003b76c  mov     [rax], rdx
0x14003b76f  mov     [rbp+var_18], rdx
0x14003b773  mov     rdx, r8
0x14003b776  cmp     r8, r15
0x14003b779  jnz     short loc_14003B712
0x14003b77b  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003b782  xor     edx, edx; unsigned __int8
0x14003b784  add     rcx, 60h ; '`'; Resource
0x14003b788  xor     r14d, r14d
0x14003b78b  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x14003b790  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003b797  lea     rax, [rcx+0D0h]
0x14003b79e  mov     rdi, [rax]
0x14003b7a1  cmp     rdi, rax
0x14003b7a4  jz      loc_14003B8D2
0x14003b7aa  lea     rsi, [rdi+10h]
0x14003b7ae  mov     r12b, 1
0x14003b7b1  mov     rbx, [rsi]
0x14003b7b4  cmp     rbx, rsi
0x14003b7b7  jz      short loc_14003B82B
0x14003b7b9  cmp     dword ptr [rbx-48h], 1
0x14003b7bd  jnz     short loc_14003B81A
0x14003b7bf  test    r13d, r13d
0x14003b7c2  jg      short loc_14003B814
0x14003b7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b7cb  lea     rax, WPP_GLOBAL_Control
0x14003b7d2  cmp     rcx, rax
0x14003b7d5  jz      short loc_14003B80B
0x14003b7d7  test    dword ptr [rcx+2Ch], 400h
0x14003b7de  jz      short loc_14003B80B
0x14003b7e0  cmp     byte ptr [rcx+29h], 3
0x14003b7e4  jb      short loc_14003B80B
0x14003b7e6  mov     rcx, [rcx+18h]
0x14003b7ea  lea     rax, [rbx-8Ch]
0x14003b7f1  lea     r9, [rbx-7Ch]
0x14003b7f5  mov     [rsp+58h+var_38], rax
0x14003b7fa  mov     edx, 3Ah ; ':'
0x14003b7ff  lea     r8, WPP_c4a5d22d2cc233e7d4f9a274e892dd73_Traceguids
0x14003b806  call    WPP_SF__guid__guid_
0x14003b80b  mov     dword ptr [rbx-48h], 2
0x14003b812  jmp     short loc_14003B81A
0x14003b814  inc     r14d
0x14003b817  xor     r12b, r12b
0x14003b81a  mov     rbx, [rbx]
0x14003b81d  cmp     rbx, rsi
0x14003b820  jnz     short loc_14003B7B9
0x14003b822  test    r12b, r12b
0x14003b825  jz      loc_14003B8B5
0x14003b82b  mov     rdx, [r15]
0x14003b82e  cmp     rdx, r15
0x14003b831  jz      short loc_14003B8A5
0x14003b833  mov     rax, [rdx+10h]
0x14003b837  mov     r8, [rdx]
0x14003b83a  mov     rcx, [rax+28h]
0x14003b83e  mov     r9, [rcx+40h]
0x14003b842  mov     rcx, [r9+20h]
0x14003b846  sub     rcx, [rdi+6Ch]
0x14003b84a  jnz     short loc_14003B854
0x14003b84c  mov     rcx, [r9+28h]
0x14003b850  sub     rcx, [rdi+74h]
0x14003b854  test    rcx, rcx
0x14003b857  jnz     short loc_14003B89D
0x14003b859  mov     [rdx-78h], ecx
0x14003b85c  cmp     [r8+8], rdx
0x14003b860  jnz     loc_14003B967
0x14003b866  mov     rax, [rdx+8]
0x14003b86a  cmp     [rax], rdx
0x14003b86d  jnz     loc_14003B967
0x14003b873  mov     [rax], r8
0x14003b876  lea     rcx, [rbp+var_20]
0x14003b87a  mov     [r8+8], rax
0x14003b87e  mov     rax, [rbp+var_18]
0x14003b882  cmp     [rax], rcx
0x14003b885  jnz     loc_14003B967
0x14003b88b  mov     [rdx+8], rax
0x14003b88f  lea     rcx, [rbp+var_20]
0x14003b893  mov     [rdx], rcx
0x14003b896  mov     [rax], rdx
0x14003b899  mov     [rbp+var_18], rdx
0x14003b89d  mov     rdx, r8
0x14003b8a0  cmp     r8, r15
0x14003b8a3  jnz     short loc_14003B833
0x14003b8a5  mov     rcx, rdi; this
0x14003b8a8  call    ?PauseTasks@SP_POOL@@QEAAXXZ; SP_POOL::PauseTasks(void)
0x14003b8ad  mov     rcx, rdi; this
0x14003b8b0  call    ?ResumeTasks@SP_POOL@@QEAAXXZ; SP_POOL::ResumeTasks(void)
0x14003b8b5  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003b8bc  mov     rdi, [rdi]
0x14003b8bf  lea     rax, [rcx+0D0h]
0x14003b8c6  cmp     rdi, rax
0x14003b8c9  jnz     loc_14003B7AA
0x14003b8cf  mov     ebx, [rbp+arg_8]
0x14003b8d2  add     rcx, 60h ; '`'; Resource
0x14003b8d6  call    cs:__imp_ExReleaseResourceLite
0x14003b8dd  nop     dword ptr [rax+rax+00h]
0x14003b8e2  call    cs:__imp_KeLeaveCriticalRegion
0x14003b8e9  nop     dword ptr [rax+rax+00h]
0x14003b8ee  mov     rcx, [rbp+var_20]
0x14003b8f2  lea     rax, [rbp+var_20]
0x14003b8f6  cmp     rcx, rax
0x14003b8f9  jz      short loc_14003B931
0x14003b8fb  lea     rax, [rbp+var_20]
0x14003b8ff  cmp     [rcx+8], rax
0x14003b903  jnz     short loc_14003B967
0x14003b905  mov     rax, [rcx]
0x14003b908  cmp     [rax+8], rcx
0x14003b90c  jnz     short loc_14003B967
0x14003b90e  lea     rdx, [rbp+var_20]
0x14003b912  mov     [rbp+var_20], rax
0x14003b916  mov     [rax+8], rdx
0x14003b91a  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14003b921  xor     edx, edx; PriorityBoost
0x14003b923  call    cs:__imp_IofCompleteRequest
0x14003b92a  nop     dword ptr [rax+rax+00h]
0x14003b92f  jmp     short loc_14003B8EE
0x14003b931  test    r14d, r14d
0x14003b934  jz      short loc_14003B96E
0x14003b936  cmp     r14d, ebx
0x14003b939  jz      short loc_14003B947
0x14003b93b  mov     ebx, r14d
0x14003b93e  mov     r13d, 7530h
0x14003b944  mov     [rbp+arg_8], ebx
0x14003b947  lea     r8, [rbp+Interval]; Interval
0x14003b94b  xor     edx, edx; Alertable
0x14003b94d  xor     ecx, ecx; WaitMode
0x14003b94f  call    cs:__imp_KeDelayExecutionThread
0x14003b956  nop     dword ptr [rax+rax+00h]
0x14003b95b  sub     r13d, 0C8h
0x14003b962  jmp     loc_14003B70A
0x14003b967  mov     ecx, 3
0x14003b96c  int     29h; Win8: RtlFailFast(ecx)
0x14003b96e  xor     eax, eax
0x14003b970  add     rsp, 58h
0x14003b974  pop     r15
0x14003b976  pop     r14
0x14003b978  pop     r13
0x14003b97a  pop     r12
0x14003b97c  pop     rdi
0x14003b97d  pop     rsi
0x14003b97e  pop     rbx
0x14003b97f  pop     rbp
0x14003b980  retn
```
