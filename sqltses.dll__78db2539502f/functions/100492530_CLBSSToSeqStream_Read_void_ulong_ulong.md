# CLBSSToSeqStream::Read(void *,ulong,ulong *)

- ea: `0x100492530`
- end: `0x1004926ef`
- name: `?Read@CLBSSToSeqStream@@UEAAJPEAXKPEAK@Z`
- size: `447`
- prototype: `__int64 __fastcall(CLBSSToSeqStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x100492530`
- `0x100493f10`
- `0x100493fc0`
- `0x1004940c0`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x100492584`
- `sqldk!SystemThread_TlsIndex` at `0x100492676`
- `sqldk!SystemThread_TlsOffset` at `0x10049258d`
- `sqldk!SystemThread_TlsOffset` at `0x10049267f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004925a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049269a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004925a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049269a`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CLBSSToSeqStream::Read(CLBSSToSeqStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  __int64 v9; // rdi
  __int64 v10; // rbx
  int v11; // esi
  int *v12; // rcx
  __int64 *v13; // rcx
  unsigned int v14; // r15d
  __int64 v15; // rdi
  __int64 v16; // rdx
  _BYTE v17[4]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+54h] [rbp-1Ch] BYREF
  int *v19; // [rsp+60h] [rbp-10h]
  __int64 *v20; // [rsp+68h] [rbp-8h]

  if ( !*((_QWORD *)this + 1) )
    return 1;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v11 = !(*(_BYTE *)(v10 + 616) & 1);
  *(_DWORD *)(v10 + 616) |= 1u;
  v18 = 0;
  HIDWORD(v18) = ExtIntCodeProtector<0>::Pre(v17);
  v12 = (int *)v17;
  if ( v18 < 0 )
    v12 = 0;
  v19 = v12;
  if ( v18 < 0 )
  {
    v20 = 0;
  }
  else
  {
    HIDWORD(v18) = NonPreemptiveSetter::Pre((NonPreemptiveSetter *)&v18);
    v13 = &v18;
    if ( v18 < 0 )
      v13 = 0;
    v20 = v13;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, _QWORD, unsigned int *))(**((_QWORD **)this + 1) + 24LL))(
          *((_QWORD *)this + 1),
          *((_QWORD *)this + 3),
          a2,
          a3,
          a4);
  *((_QWORD *)this + 3) += *a4;
  if ( v20 && *(_DWORD *)v20 )
  {
    v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v16 = *(_QWORD *)(v15 + 256);
    if ( !v16 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v16 = *(_QWORD *)(v15 + 256);
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v16 + 608) + 8LL))(*(_QWORD *)(v16 + 608));
  }
  if ( v19 )
    SOS_Task::SetInExternalCode(*v19);
  *(_DWORD *)(v10 + 616) &= ~v11;
  return v14;
}

```

## disassembly

```asm
0x100492530  mov     rax, rsp
0x100492533  push    rbp
0x100492534  push    r12
0x100492536  push    r13
0x100492538  push    r14
0x10049253a  push    r15
0x10049253c  mov     rbp, rsp
0x10049253f  sub     rsp, 70h
0x100492543  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x10049254b  mov     [rax+10h], rbx
0x10049254f  mov     [rax+18h], rsi
0x100492553  mov     [rax+20h], rdi
0x100492557  mov     r12, r9
0x10049255a  mov     r15d, r8d
0x10049255d  mov     r13, rdx
0x100492560  mov     r14, rcx
0x100492563  cmp     qword ptr [rcx+8], 0
0x100492568  jnz     short loc_100492574
0x10049256a  mov     eax, 1
0x10049256f  jmp     loc_1004926D1
0x100492574  mov     [rbp+var_30], 0
0x10049257b  mov     rdx, gs:58h
0x100492584  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049258b  mov     ecx, [rax]
0x10049258d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100492594  mov     edi, [rax]
0x100492596  add     rdi, [rdx+rcx*8]
0x10049259a  mov     rbx, [rdi+100h]
0x1004925a1  test    rbx, rbx
0x1004925a4  jnz     short loc_1004925B5
0x1004925a6  xor     ecx, ecx
0x1004925a8  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004925ae  mov     rbx, [rdi+100h]
0x1004925b5  mov     [rbp+var_28], rbx
0x1004925b9  mov     eax, [rbx+268h]
0x1004925bf  mov     esi, eax
0x1004925c1  and     esi, 1
0x1004925c4  xor     esi, 1
0x1004925c7  mov     [rbp+var_30], esi
0x1004925ca  or      eax, 1
0x1004925cd  mov     [rbx+268h], eax
0x1004925d3  xor     edi, edi
0x1004925d5  mov     [rbp+var_1C], rdi
0x1004925d9  lea     rax, [rbp+var_10]
0x1004925dd  mov     [rbp+arg_0], rax
0x1004925e1  mov     dword ptr [rbp+var_1C+4], edi
0x1004925e4  lea     rcx, [rbp+var_20]
0x1004925e8  call    ?Pre@?$ExtIntCodeProtector@$0A@@@QEAAJXZ; ExtIntCodeProtector<0>::Pre(void)
0x1004925ed  mov     dword ptr [rbp+var_1C+4], eax
0x1004925f0  lea     rcx, [rbp+var_20]
0x1004925f4  test    eax, eax
0x1004925f6  cmovs   rcx, rdi
0x1004925fa  mov     [rbp+var_10], rcx
0x1004925fe  lea     rax, [rbp+var_8]
0x100492602  mov     [rbp+var_38], rax
0x100492606  cmp     dword ptr [rbp+var_1C+4], edi
0x100492609  jl      short loc_100492627
0x10049260b  lea     rcx, [rbp+var_1C]; this
0x10049260f  call    ?Pre@NonPreemptiveSetter@@QEAAJXZ; NonPreemptiveSetter::Pre(void)
0x100492614  mov     dword ptr [rbp+var_1C+4], eax
0x100492617  lea     rcx, [rbp+var_1C]
0x10049261b  test    eax, eax
0x10049261d  cmovs   rcx, rdi
0x100492621  mov     [rbp+var_8], rcx
0x100492625  jmp     short loc_10049262B
0x100492627  mov     [rbp+var_8], rdi
0x10049262b  mov     rcx, [r14+8]
0x10049262f  mov     rax, [rcx]
0x100492632  mov     [rsp+70h+var_50], r12
0x100492637  mov     r9d, r15d
0x10049263a  mov     r8, r13
0x10049263d  mov     rdx, [r14+18h]
0x100492641  call    qword ptr [rax+18h]
0x100492644  mov     r15d, eax
0x100492647  mov     ecx, [r12]
0x10049264b  add     [r14+18h], rcx
0x10049264f  lea     rax, [rbp+var_10]
0x100492653  mov     [rbp+arg_0], rax
0x100492657  lea     rax, [rbp+var_8]
0x10049265b  mov     [rbp+var_38], rax
0x10049265f  mov     rax, [rbp+var_8]
0x100492663  test    rax, rax
0x100492666  jz      short loc_1004926B5
0x100492668  cmp     dword ptr [rax], 0
0x10049266b  jz      short loc_1004926B5
0x10049266d  mov     rdx, gs:58h
0x100492676  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049267d  mov     ecx, [rax]
0x10049267f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100492686  mov     edi, [rax]
0x100492688  add     rdi, [rdx+rcx*8]
0x10049268c  mov     rdx, [rdi+100h]
0x100492693  test    rdx, rdx
0x100492696  jnz     short loc_1004926A7
0x100492698  xor     ecx, ecx
0x10049269a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004926a0  mov     rdx, [rdi+100h]
0x1004926a7  mov     rcx, [rdx+260h]
0x1004926ae  mov     rax, [rcx]
0x1004926b1  call    qword ptr [rax+8]
0x1004926b4  nop
0x1004926b5  mov     rax, [rbp+var_10]
0x1004926b9  test    rax, rax
0x1004926bc  jz      short loc_1004926C6
0x1004926be  mov     ecx, [rax]; int
0x1004926c0  call    ?SetInExternalCode@SOS_Task@@SAXH@Z; SOS_Task::SetInExternalCode(int)
0x1004926c5  nop
0x1004926c6  not     esi
0x1004926c8  and     [rbx+268h], esi
0x1004926ce  mov     eax, r15d
0x1004926d1  lea     r11, [rsp+70h+var_s0]
0x1004926d6  mov     rbx, [r11+38h]
0x1004926da  mov     rsi, [r11+40h]
0x1004926de  mov     rdi, [r11+48h]
0x1004926e2  mov     rsp, r11
0x1004926e5  pop     r15
0x1004926e7  pop     r14
0x1004926e9  pop     r13
0x1004926eb  pop     r12
0x1004926ed  pop     rbp
0x1004926ee  retn
```
