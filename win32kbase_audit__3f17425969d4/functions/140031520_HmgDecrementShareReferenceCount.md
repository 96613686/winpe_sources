# HmgDecrementShareReferenceCount

- ea: `0x140031520`
- end: `0x140031748`
- name: `HmgDecrementShareReferenceCount`
- size: `552`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `66`
- callee_count: `5`
- tags: ``

## callers

- `0x14000f9b0`
- `0x140010190`
- `0x140010464`
- `0x140011ecc`
- `0x140012820`
- `0x140012ff8`
- `0x1400130f0`
- `0x14001520c`
- `0x14001a99c`
- `0x14001ac50`
- `0x14001afc0`
- `0x14001bf50`
- `0x14001f37c`
- `0x14001f55c`
- `0x140023b54`
- `0x140026644`
- `0x140027d70`
- `0x14002bbe0`
- `0x14002bed0`
- `0x14002c810`
- `0x14002e5a0`
- `0x14002eef0`
- `0x14002f970`
- `0x140031020`
- `0x140039f10`
- `0x14003ad20`
- `0x14003b980`
- `0x14003bb50`
- `0x14003c230`
- `0x14003c570`
- `0x14003d160`
- `0x14003da30`
- `0x14003db08`
- `0x14003db48`
- `0x14003dee0`
- `0x14003e600`
- `0x14003ea80`
- `0x14003eb30`
- `0x14003ec5c`
- `0x14003f05c`
- `0x14003f340`
- `0x14006f818`
- `0x140074870`
- `0x1400dcd50`
- `0x1400efe00`
- `0x1401028b0`
- `0x14010e4c0`
- `0x14011ed20`
- `0x140149cf8`
- `0x140167fc0`

## callees

- `0x14001e034`
- `0x140031520`
- `0x140031750`
- `0x140079330`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140031700`
- `ntoskrnl!PsGetCurrentProcess` at `0x140031700`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003163f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003169a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003163f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003169a`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003170f`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003172c`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003170f`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003172c`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003171d`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003171d`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003157a`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003157a`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14003156b`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14003156b`

## pseudocode

```c
__int64 __fastcall HmgDecrementShareReferenceCount(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // eax
  unsigned int v4; // edi
  __int64 v5; // r13
  unsigned int v6; // edi
  _QWORD *CurrentThreadWin32ThreadAndEnterCriticalRegion; // rsi
  __int64 v9; // rcx
  __int64 v10; // r15
  __int64 v11; // rcx
  int v12; // ebx
  unsigned int *v13; // rax
  unsigned int *v14; // rsi
  char v15; // al
  unsigned int v16; // r15d
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 *v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rax
  ThreadRestrictNewHandlesRegion *v23; // rcx
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v27; // [rsp+20h] [rbp-48h] BYREF
  int v28; // [rsp+28h] [rbp-40h]
  __int16 v29; // [rsp+2Ch] [rbp-3Ch]
  __int64 v30; // [rsp+30h] [rbp-38h]
  __int64 v31; // [rsp+70h] [rbp+8h] BYREF

  v2 = *a2;
  v4 = *a2;
  v30 = a1;
  v5 = a1;
  v29 = 0;
  v6 = (unsigned __int16)v2 | (v4 >> 8) & 0xFF0000;
  v31 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (_QWORD *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v31);
  if ( (!(unsigned __int8)KeIsAttachedProcess()
     || (CurrentProcess = PsGetCurrentProcess(v9),
         ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
         CurrentThreadProcess = PsGetCurrentThreadProcess(),
         ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)))
    && CurrentThreadWin32ThreadAndEnterCriticalRegion
    && *CurrentThreadWin32ThreadAndEnterCriticalRegion )
  {
    v10 = *CurrentThreadWin32ThreadAndEnterCriticalRegion + 8LL;
  }
  else
  {
    v10 = 0;
  }
  v11 = *(_QWORD *)(a1 + 8);
  v12 = 1;
  v28 = 1;
  v13 = (unsigned int *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, v6);
  v27 = v13;
  v14 = v13;
  if ( v13 )
  {
    _m_prefetchw(v13 + 2);
    if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 96LL))(
                       *(_QWORD *)(a1 + 8),
                       *v13)
                   + 14)
        & 0x20) != 0
      && (!v10
       || (v23 = *(ThreadRestrictNewHandlesRegion **)(v10 + 328)) == 0
       || !*((_BYTE *)v23 + 80)
       || !ThreadRestrictNewHandlesRegion::InRegion(v23, v6)) )
    {
      LOBYTE(v29) = 1;
      HANDLELOCK::vUnlock((HANDLELOCK *)&v27);
      v5 = v30;
      v12 = v28;
      v14 = v27;
    }
  }
  else
  {
    v12 = 0;
    KeLeaveCriticalRegion();
  }
  if ( v12 )
  {
    v15 = *((_BYTE *)v14 + 14);
    v16 = a2[2];
    switch ( v15 )
    {
      case 5:
        v17 = *((_QWORD *)a2 + 89);
        v18 = 3;
        break;
      case 4:
        v17 = *((_QWORD *)a2 + 14);
        v18 = 2;
        break;
      case 16:
        v17 = *((_QWORD *)a2 + 17);
        v18 = 0;
        break;
      default:
        goto LABEL_11;
    }
    TrackObjectReferenceDecrement(a1, v18, v17);
LABEL_11:
    --a2[2];
    v19 = *(__int64 **)(v5 + 8);
    v20 = *v19;
    v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v19 + 96))(v19, *v14);
    (*(void (__fastcall **)(__int64 *, __int64))(v20 + 48))(v19, v21);
    KeLeaveCriticalRegion();
    return v16;
  }
  (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8), a2);
  return 0;
}

```

## disassembly

```asm
0x140031520  mov     [rsp+arg_8], rbx
0x140031525  mov     [rsp+arg_10], rbp
0x14003152a  push    rsi
0x14003152b  push    rdi
0x14003152c  push    r13
0x14003152e  push    r14
0x140031530  push    r15
0x140031532  sub     rsp, 40h
0x140031536  mov     eax, [rdx]
0x140031538  mov     rbp, rcx
0x14003153b  mov     edi, eax
0x14003153d  mov     [rsp+68h+var_38], rcx
0x140031542  shr     edi, 8
0x140031545  mov     r13, rcx
0x140031548  movzx   eax, ax
0x14003154b  lea     rcx, [rsp+68h+arg_0]
0x140031550  and     edi, 0FF0000h
0x140031556  mov     [rsp+68h+var_3C], 0
0x14003155d  or      edi, eax
0x14003155f  mov     [rsp+68h+arg_0], 0
0x140031568  mov     r14, rdx
0x14003156b  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x140031572  nop     dword ptr [rax+rax+00h]
0x140031577  mov     rsi, rax
0x14003157a  call    cs:__imp_KeIsAttachedProcess
0x140031581  nop     dword ptr [rax+rax+00h]
0x140031586  test    al, al
0x140031588  jnz     loc_140031700
0x14003158e  test    rsi, rsi
0x140031591  jz      loc_140031740
0x140031597  mov     rax, [rsi]
0x14003159a  test    rax, rax
0x14003159d  jz      loc_140031740
0x1400315a3  lea     r15, [rax+8]
0x1400315a7  mov     rcx, [rbp+8]
0x1400315ab  mov     ebx, 1
0x1400315b0  mov     edx, edi
0x1400315b2  mov     [rsp+68h+var_40], ebx
0x1400315b6  mov     rax, [rcx]
0x1400315b9  mov     rax, [rax+28h]
0x1400315bd  call    _guard_dispatch_icall
0x1400315c2  mov     [rsp+68h+var_48], rax
0x1400315c7  mov     rsi, rax
0x1400315ca  test    rax, rax
0x1400315cd  jz      loc_140031698
0x1400315d3  prefetchw byte ptr [rax+8]
0x1400315d7  mov     rcx, [rbp+8]
0x1400315db  mov     edx, [rsi]
0x1400315dd  mov     rax, [rcx]
0x1400315e0  mov     rax, [rax+60h]
0x1400315e4  call    _guard_dispatch_icall
0x1400315e9  test    byte ptr [rax+0Eh], 20h
0x1400315ed  jnz     loc_1400316B9
0x1400315f3  test    ebx, ebx
0x1400315f5  jz      short loc_140031669
0x1400315f7  movzx   eax, byte ptr [rsi+0Eh]
0x1400315fb  mov     r15d, [r14+8]
0x1400315ff  cmp     al, 5
0x140031601  jnz     short loc_140031682
0x140031603  mov     r8, [r14+2C8h]
0x14003160a  mov     edx, 3
0x14003160f  mov     rcx, rbp
0x140031612  call    ?TrackObjectReferenceDecrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceDecrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x140031617  dec     dword ptr [r14+8]
0x14003161b  mov     rdi, [r13+8]
0x14003161f  mov     edx, [rsi]
0x140031621  mov     rcx, rdi
0x140031624  mov     rbx, [rdi]
0x140031627  mov     rax, [rbx+60h]
0x14003162b  call    _guard_dispatch_icall
0x140031630  mov     rdx, rax
0x140031633  mov     rcx, rdi
0x140031636  mov     rax, [rbx+30h]
0x14003163a  call    _guard_dispatch_icall
0x14003163f  call    cs:__imp_KeLeaveCriticalRegion
0x140031646  nop     dword ptr [rax+rax+00h]
0x14003164b  mov     eax, r15d
0x14003164e  mov     rbx, [rsp+68h+arg_8]
0x140031653  mov     rbp, [rsp+68h+arg_10]
0x14003165b  add     rsp, 40h
0x14003165f  pop     r15
0x140031661  pop     r14
0x140031663  pop     r13
0x140031665  pop     rdi
0x140031666  pop     rsi
0x140031667  retn
0x140031669  mov     rcx, [rbp+8]
0x14003166d  xor     ebx, ebx
0x14003166f  mov     rdx, [rcx]
0x140031672  mov     rax, [rdx+8]
0x140031676  mov     rdx, r14
0x140031679  call    _guard_dispatch_icall
0x14003167e  mov     eax, ebx
0x140031680  jmp     short loc_14003164E
0x140031682  cmp     al, 4
0x140031684  jz      short loc_1400316AB
0x140031686  cmp     al, 10h
0x140031688  jnz     short loc_140031617
0x14003168a  mov     r8, [r14+88h]
0x140031691  xor     edx, edx
0x140031693  jmp     loc_14003160F
0x140031698  xor     ebx, ebx
0x14003169a  call    cs:__imp_KeLeaveCriticalRegion
0x1400316a1  nop     dword ptr [rax+rax+00h]
0x1400316a6  jmp     loc_1400315F3
0x1400316ab  mov     r8, [r14+70h]
0x1400316af  mov     edx, 2
0x1400316b4  jmp     loc_14003160F
0x1400316b9  test    r15, r15
0x1400316bc  jz      short loc_1400316DF
0x1400316be  mov     rcx, [r15+148h]; this
0x1400316c5  test    rcx, rcx
0x1400316c8  jz      short loc_1400316DF
0x1400316ca  cmp     byte ptr [rcx+50h], 0
0x1400316ce  jz      short loc_1400316DF
0x1400316d0  mov     edx, edi; unsigned int
0x1400316d2  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x1400316d7  test    al, al
0x1400316d9  jnz     loc_1400315F3
0x1400316df  mov     byte ptr [rsp+68h+var_3C], bl
0x1400316e3  lea     rcx, [rsp+68h+var_48]; this
0x1400316e8  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x1400316ed  mov     r13, [rsp+68h+var_38]
0x1400316f2  mov     ebx, [rsp+68h+var_40]
0x1400316f6  mov     rsi, [rsp+68h+var_48]
0x1400316fb  jmp     loc_1400315F3
0x140031700  call    cs:__imp_PsGetCurrentProcess
0x140031707  nop     dword ptr [rax+rax+00h]
0x14003170c  mov     rcx, rax
0x14003170f  call    cs:__imp_PsGetProcessSessionIdEx
0x140031716  nop     dword ptr [rax+rax+00h]
0x14003171b  mov     ebx, eax
0x14003171d  call    cs:__imp_PsGetCurrentThreadProcess
0x140031724  nop     dword ptr [rax+rax+00h]
0x140031729  mov     rcx, rax
0x14003172c  call    cs:__imp_PsGetProcessSessionIdEx
0x140031733  nop     dword ptr [rax+rax+00h]
0x140031738  cmp     ebx, eax
0x14003173a  jz      loc_14003158E
0x140031740  xor     r15d, r15d
0x140031743  jmp     loc_1400315A7
```
