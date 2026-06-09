# UbpmpScheduleCalendarRepetitionsAtRegistrationTime

- ea: `0x1800137b0`
- end: `0x1800138da`
- name: `UbpmpScheduleCalendarRepetitionsAtRegistrationTime`
- size: `298`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800138e0`

## callees

- `0x18000f9a0`
- `0x180013244`
- `0x1800137b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800138b8`
- `ntdll!RtlFreeHeap` at `0x1800138b8`
- `DABAPI!DabGetLastScheduledRunTime` at `0x18001383e`
- `DABAPI!DabGetLastScheduledRunTime` at `0x18001383e`

## pseudocode

```c
__int64 __fastcall UbpmpScheduleCalendarRepetitionsAtRegistrationTime(struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  unsigned __int16 v4; // bx
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int LastScheduledRunTime; // ebp
  unsigned __int64 v8; // r8
  struct _FILETIME v10; // [rsp+68h] [rbp+10h] BYREF
  struct _UBPM_REPETITION_CONTEXT *v11; // [rsp+70h] [rbp+18h] BYREF

  v11 = 0;
  v10 = 0;
  v2 = UbpmAlloc(0x3Cu);
  v3 = v2;
  if ( !v2 )
    return 14;
  v4 = 0;
  v2[3] = 0;
  *((_DWORD *)v2 + 4) = 0;
  while ( 1 )
  {
    v5 = *((_QWORD *)a1 + 3);
    if ( (unsigned int)v4 >= *(_DWORD *)(v5 + 20) )
      break;
    v6 = *(_QWORD *)(v5 + 24);
    if ( *(_DWORD *)(v6 + 48LL * v4) == 1 && *(_DWORD *)(*(_QWORD *)(v6 + 48LL * v4 + 8) + 56LL) == 4 )
    {
      LastScheduledRunTime = DabGetLastScheduledRunTime(*((_QWORD *)a1 + 4) + 8 * (v4 + 4 * (v4 + 1LL)), &v10);
      if ( LastScheduledRunTime )
        goto LABEL_13;
      if ( v10.dwLowDateTime || v10.dwHighDateTime )
      {
        v8 = _InterlockedIncrement64((volatile signed __int64 *)&g_ullCollectionId);
        v3[6] = v8;
        LastScheduledRunTime = UbpmpScheduleRepetitionSeries(a1, v4, v8, v3, 0x3Cu, &v10, &v11);
        if ( LastScheduledRunTime )
          goto LABEL_13;
      }
    }
    ++v4;
  }
  LastScheduledRunTime = 0;
LABEL_13:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  return LastScheduledRunTime;
}

```

## disassembly

```asm
0x1800137b0  push    rsi
0x1800137b2  push    rdi
0x1800137b3  push    r14
0x1800137b5  sub     rsp, 40h
0x1800137b9  mov     rsi, rcx
0x1800137bc  xor     r14d, r14d
0x1800137bf  mov     ecx, 3Ch ; '<'; Size
0x1800137c4  mov     [rsp+58h+arg_10], r14
0x1800137c9  mov     qword ptr [rsp+58h+arg_8.dwLowDateTime], r14
0x1800137ce  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800137d3  mov     rdi, rax
0x1800137d6  test    rax, rax
0x1800137d9  jz      loc_1800138D3
0x1800137df  mov     [rsp+58h+arg_0], rbx
0x1800137e4  mov     ebx, r14d
0x1800137e7  mov     [rsp+58h+arg_18], rbp
0x1800137ec  mov     [rax+18h], r14
0x1800137f0  mov     [rax+10h], r14d
0x1800137f4  mov     rax, [rsi+18h]
0x1800137f8  movzx   ecx, bx
0x1800137fb  cmp     ecx, [rax+14h]
0x1800137fe  jnb     loc_1800138A3
0x180013804  mov     rcx, [rax+18h]
0x180013808  movzx   r8d, bx
0x18001380c  lea     rdx, [r8+r8*2]
0x180013810  add     rdx, rdx
0x180013813  cmp     dword ptr [rcx+rdx*8], 1
0x180013817  jz      short loc_18001381E
0x180013819  inc     bx
0x18001381c  jmp     short loc_1800137F4
0x18001381e  mov     rax, [rcx+rdx*8+8]
0x180013823  cmp     dword ptr [rax+38h], 4
0x180013827  jnz     short loc_180013819
0x180013829  mov     rax, [rsi+20h]
0x18001382d  lea     rcx, [r8+1]
0x180013831  lea     rcx, [r8+rcx*4]
0x180013835  lea     rdx, [rsp+58h+arg_8]
0x18001383a  lea     rcx, [rax+rcx*8]
0x18001383e  call    cs:__imp_DabGetLastScheduledRunTime
0x180013844  mov     ebp, eax
0x180013846  test    eax, eax
0x180013848  jnz     short loc_1800138A6
0x18001384a  cmp     [rsp+58h+arg_8.dwLowDateTime], r14d
0x18001384f  jnz     short loc_180013858
0x180013851  cmp     [rsp+58h+arg_8.dwHighDateTime], r14d
0x180013856  jz      short loc_180013819
0x180013858  mov     r8d, 1
0x18001385e  lock xadd cs:?g_ullCollectionId@@3_KC, r8; unsigned __int64 volatile g_ullCollectionId
0x180013867  lea     rax, [rsp+58h+arg_10]
0x18001386c  inc     r8; unsigned __int64
0x18001386f  mov     [rsp+58h+var_28], rax; struct _UBPM_REPETITION_CONTEXT **
0x180013874  mov     r9, rdi; void *
0x180013877  lea     rax, [rsp+58h+arg_8]
0x18001387c  mov     [rdi+30h], r8
0x180013880  mov     [rsp+58h+var_30], rax; struct _FILETIME *
0x180013885  movzx   edx, bx; unsigned __int16
0x180013888  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18001388b  mov     [rsp+58h+var_38], 3Ch ; '<'; unsigned int
0x180013893  call    ?UbpmpScheduleRepetitionSeries@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@G_KPEAXKPEAU_FILETIME@@PEAPEAU_UBPM_REPETITION_CONTEXT@@@Z; UbpmpScheduleRepetitionSeries(_UBPM_TRIGGER_CONSUMER_BLOCK *,ushort,unsigned __int64,void *,ulong,_FILETIME *,_UBPM_REPETITION_CONTEXT * *)
0x180013898  mov     ebp, eax
0x18001389a  test    eax, eax
0x18001389c  jnz     short loc_1800138A6
0x18001389e  jmp     loc_180013819
0x1800138a3  mov     ebp, r14d
0x1800138a6  mov     rcx, gs:60h
0x1800138af  mov     r8, rdi; P
0x1800138b2  xor     edx, edx; Flags
0x1800138b4  mov     rcx, [rcx+30h]; HeapHandle
0x1800138b8  call    cs:__imp_RtlFreeHeap
0x1800138be  mov     rbx, [rsp+58h+arg_0]
0x1800138c3  mov     eax, ebp
0x1800138c5  mov     rbp, [rsp+58h+arg_18]
0x1800138ca  add     rsp, 40h
0x1800138ce  pop     r14
0x1800138d0  pop     rdi
0x1800138d1  pop     rsi
0x1800138d2  retn
0x1800138d3  mov     eax, 0Eh
0x1800138d8  jmp     short loc_1800138CA
```
