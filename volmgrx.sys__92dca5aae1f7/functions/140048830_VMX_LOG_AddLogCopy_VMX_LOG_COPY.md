# VMX_LOG::AddLogCopy(VMX_LOG_COPY *)

- ea: `0x140048830`
- end: `0x140048978`
- name: `?AddLogCopy@VMX_LOG@@QEAAXPEAVVMX_LOG_COPY@@@Z`
- size: `328`
- prototype: `void __fastcall(VMX_LOG *this, VMX_LOG **)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002f1e4`
- `0x140033278`
- `0x14004b3dc`
- `0x14004bbe4`

## callees

- `0x140008b38`
- `0x140048830`
- `0x140048980`
- `0x140049b84`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14004891f`
- `ntoskrnl!KeInitializeEvent` at `0x14004891f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048960`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048960`

## pseudocode

```c
void __fastcall VMX_LOG::AddLogCopy(VMX_LOG *this, VMX_LOG **a2)
{
  unsigned int v4; // r10d
  unsigned int v5; // edx
  unsigned int i; // r8d
  __int64 v7; // rcx
  VMX_LOG **v8; // rcx
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( a2[2] == this )
    return;
  v4 = *((_DWORD *)a2 + 10);
  a2[2] = this;
  *((_WORD *)a2 + 22) = 256;
  v5 = 0;
  if ( v4 )
  {
    for ( i = 0; i < v4; ++i )
    {
      v7 = 16LL * i;
      v5 += *(_DWORD *)((char *)a2[4] + v7 + 8) * (*((_DWORD *)a2[3] + 9) >> 9);
    }
  }
  if ( !*((_DWORD *)this + 8) )
    goto LABEL_10;
  if ( v5 < *((_DWORD *)this + 10) )
  {
    if ( *((_BYTE *)this + 96) && v5 < *((_DWORD *)this + 11) )
    {
      *((_BYTE *)a2 + 45) = 0;
      goto LABEL_11;
    }
LABEL_10:
    *((_DWORD *)this + 10) = v5;
  }
LABEL_11:
  v8 = (VMX_LOG **)*((_QWORD *)this + 3);
  if ( *v8 != (VMX_LOG *)((char *)this + 16) )
    __fastfail(3u);
  *a2 = (VMX_LOG *)((char *)this + 16);
  a2[1] = (VMX_LOG *)v8;
  *v8 = (VMX_LOG *)a2;
  *((_QWORD *)this + 3) = a2;
  ++*((_DWORD *)this + 8);
  if ( *((_BYTE *)this + 96) )
  {
    if ( (int)VMX_LOG::AllocateFlushSequentialMemory(this) < 0 )
      *((_BYTE *)a2 + 45) = 0;
    if ( (int)VMX_LOG::SetBlocksCount(this, *((_DWORD *)this + 11)) < 0 )
      *((_BYTE *)a2 + 45) = 0;
    if ( *((_BYTE *)a2 + 45) )
    {
      ++*((_DWORD *)this + 9);
      KeInitializeEvent(&Event, NotificationEvent, 0);
      VMX_LOG::Flush(this, (struct VMX_LOG_COPY *)a2, 1u, (void (*)(void *, int))VmxpSynchLogFlushCompletion, &Event);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x140048830  mov     [rsp+arg_0], rbx
0x140048835  push    rdi
0x140048836  sub     rsp, 50h
0x14004883a  xor     eax, eax
0x14004883c  xorps   xmm0, xmm0
0x14004883f  mov     rbx, rdx
0x140048842  mov     rdi, rcx
0x140048845  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x14004884a  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x14004884f  cmp     [rdx+10h], rcx
0x140048853  jz      loc_14004896C
0x140048859  mov     r10d, [rbx+28h]
0x14004885d  mov     [rdx+10h], rcx
0x140048861  mov     word ptr [rdx+2Ch], 100h
0x140048867  xor     edx, edx
0x140048869  test    r10d, r10d
0x14004886c  jz      short loc_14004889B
0x14004886e  mov     rax, [rbx+18h]
0x140048872  xor     r8d, r8d
0x140048875  mov     r11, [rbx+20h]
0x140048879  mov     r9d, [rax+24h]
0x14004887d  shr     r9d, 9
0x140048881  mov     ecx, r8d
0x140048884  mov     eax, r9d
0x140048887  shl     rcx, 4
0x14004888b  inc     r8d
0x14004888e  imul    eax, [rcx+r11+8]
0x140048894  add     edx, eax
0x140048896  cmp     r8d, r10d
0x140048899  jb      short loc_140048881
0x14004889b  cmp     dword ptr [rdi+20h], 0
0x14004889f  jz      short loc_1400488B7
0x1400488a1  cmp     edx, [rdi+28h]
0x1400488a4  jnb     short loc_1400488BA
0x1400488a6  cmp     byte ptr [rdi+60h], 0
0x1400488aa  jz      short loc_1400488B7
0x1400488ac  cmp     edx, [rdi+2Ch]
0x1400488af  jnb     short loc_1400488B7
0x1400488b1  mov     byte ptr [rbx+2Dh], 0
0x1400488b5  jmp     short loc_1400488BA
0x1400488b7  mov     [rdi+28h], edx
0x1400488ba  lea     rax, [rdi+10h]
0x1400488be  mov     rcx, [rax+8]
0x1400488c2  cmp     [rcx], rax
0x1400488c5  jz      short loc_1400488CE
0x1400488c7  mov     ecx, 3
0x1400488cc  int     29h; Win8: RtlFailFast(ecx)
0x1400488ce  mov     [rbx], rax
0x1400488d1  mov     [rbx+8], rcx
0x1400488d5  mov     [rcx], rbx
0x1400488d8  mov     [rax+8], rbx
0x1400488dc  inc     dword ptr [rdi+20h]
0x1400488df  cmp     byte ptr [rdi+60h], 0
0x1400488e3  jz      loc_14004896C
0x1400488e9  mov     rcx, rdi; this
0x1400488ec  call    ?AllocateFlushSequentialMemory@VMX_LOG@@AEAAJXZ; VMX_LOG::AllocateFlushSequentialMemory(void)
0x1400488f1  test    eax, eax
0x1400488f3  jns     short loc_1400488F9
0x1400488f5  mov     byte ptr [rbx+2Dh], 0
0x1400488f9  mov     edx, [rdi+2Ch]; unsigned int
0x1400488fc  mov     rcx, rdi; this
0x1400488ff  call    ?SetBlocksCount@VMX_LOG@@QEAAJK@Z; VMX_LOG::SetBlocksCount(ulong)
0x140048904  test    eax, eax
0x140048906  jns     short loc_14004890C
0x140048908  mov     byte ptr [rbx+2Dh], 0
0x14004890c  cmp     byte ptr [rbx+2Dh], 0
0x140048910  jz      short loc_14004896C
0x140048912  inc     dword ptr [rdi+24h]
0x140048915  lea     rcx, [rsp+58h+Event]; Event
0x14004891a  xor     r8d, r8d; State
0x14004891d  xor     edx, edx; Type
0x14004891f  call    cs:__imp_KeInitializeEvent
0x140048926  nop     dword ptr [rax+rax+00h]
0x14004892b  lea     rax, [rsp+58h+Event]
0x140048930  mov     r8b, 1; unsigned __int8
0x140048933  lea     r9, ?VmxpSynchLogFlushCompletion@@YAXPEAXJ@Z; void (*)(void *, int)
0x14004893a  mov     [rsp+58h+Timeout], rax; void *
0x14004893f  mov     rdx, rbx; struct VMX_LOG_COPY *
0x140048942  mov     rcx, rdi; this
0x140048945  call    ?Flush@VMX_LOG@@QEAAXPEAVVMX_LOG_COPY@@EP6AXPEAXJ@Z1@Z; VMX_LOG::Flush(VMX_LOG_COPY *,uchar,void (*)(void *,long),void *)
0x14004894a  xor     r9d, r9d; Alertable
0x14004894d  mov     [rsp+58h+Timeout], 0; Timeout
0x140048956  xor     r8d, r8d; WaitMode
0x140048959  lea     rcx, [rsp+58h+Event]; Object
0x14004895e  xor     edx, edx; WaitReason
0x140048960  call    cs:__imp_KeWaitForSingleObject
0x140048967  nop     dword ptr [rax+rax+00h]
0x14004896c  mov     rbx, [rsp+58h+arg_0]
0x140048971  add     rsp, 50h
0x140048975  pop     rdi
0x140048976  retn
```
