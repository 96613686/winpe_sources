# CLBSSToSeqStream::Write(void const *,ulong,ulong *)

- ea: `0x100492700`
- end: `0x1004928bf`
- name: `?Write@CLBSSToSeqStream@@UEAAJPEBXKPEAK@Z`
- size: `447`
- prototype: `__int64 __fastcall(CLBSSToSeqStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x100492700`
- `0x100493f10`
- `0x100493fc0`
- `0x1004940c0`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x100492754`
- `sqldk!SystemThread_TlsIndex` at `0x100492846`
- `sqldk!SystemThread_TlsOffset` at `0x10049275d`
- `sqldk!SystemThread_TlsOffset` at `0x10049284f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100492778`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049286a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100492778`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049286a`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CLBSSToSeqStream::Write(CLBSSToSeqStream *this, const void *a2, unsigned int a3, unsigned int *a4)
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
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const void *, _QWORD, unsigned int *))(**((_QWORD **)this + 1) + 32LL))(
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
0x100492700  mov     rax, rsp
0x100492703  push    rbp
0x100492704  push    r12
0x100492706  push    r13
0x100492708  push    r14
0x10049270a  push    r15
0x10049270c  mov     rbp, rsp
0x10049270f  sub     rsp, 70h
0x100492713  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x10049271b  mov     [rax+10h], rbx
0x10049271f  mov     [rax+18h], rsi
0x100492723  mov     [rax+20h], rdi
0x100492727  mov     r12, r9
0x10049272a  mov     r15d, r8d
0x10049272d  mov     r13, rdx
0x100492730  mov     r14, rcx
0x100492733  cmp     qword ptr [rcx+8], 0
0x100492738  jnz     short loc_100492744
0x10049273a  mov     eax, 1
0x10049273f  jmp     loc_1004928A1
0x100492744  mov     [rbp+var_30], 0
0x10049274b  mov     rdx, gs:58h
0x100492754  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049275b  mov     ecx, [rax]
0x10049275d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100492764  mov     edi, [rax]
0x100492766  add     rdi, [rdx+rcx*8]
0x10049276a  mov     rbx, [rdi+100h]
0x100492771  test    rbx, rbx
0x100492774  jnz     short loc_100492785
0x100492776  xor     ecx, ecx
0x100492778  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049277e  mov     rbx, [rdi+100h]
0x100492785  mov     [rbp+var_28], rbx
0x100492789  mov     eax, [rbx+268h]
0x10049278f  mov     esi, eax
0x100492791  and     esi, 1
0x100492794  xor     esi, 1
0x100492797  mov     [rbp+var_30], esi
0x10049279a  or      eax, 1
0x10049279d  mov     [rbx+268h], eax
0x1004927a3  xor     edi, edi
0x1004927a5  mov     [rbp+var_1C], rdi
0x1004927a9  lea     rax, [rbp+var_10]
0x1004927ad  mov     [rbp+arg_0], rax
0x1004927b1  mov     dword ptr [rbp+var_1C+4], edi
0x1004927b4  lea     rcx, [rbp+var_20]
0x1004927b8  call    ?Pre@?$ExtIntCodeProtector@$0A@@@QEAAJXZ; ExtIntCodeProtector<0>::Pre(void)
0x1004927bd  mov     dword ptr [rbp+var_1C+4], eax
0x1004927c0  lea     rcx, [rbp+var_20]
0x1004927c4  test    eax, eax
0x1004927c6  cmovs   rcx, rdi
0x1004927ca  mov     [rbp+var_10], rcx
0x1004927ce  lea     rax, [rbp+var_8]
0x1004927d2  mov     [rbp+var_38], rax
0x1004927d6  cmp     dword ptr [rbp+var_1C+4], edi
0x1004927d9  jl      short loc_1004927F7
0x1004927db  lea     rcx, [rbp+var_1C]; this
0x1004927df  call    ?Pre@NonPreemptiveSetter@@QEAAJXZ; NonPreemptiveSetter::Pre(void)
0x1004927e4  mov     dword ptr [rbp+var_1C+4], eax
0x1004927e7  lea     rcx, [rbp+var_1C]
0x1004927eb  test    eax, eax
0x1004927ed  cmovs   rcx, rdi
0x1004927f1  mov     [rbp+var_8], rcx
0x1004927f5  jmp     short loc_1004927FB
0x1004927f7  mov     [rbp+var_8], rdi
0x1004927fb  mov     rcx, [r14+8]
0x1004927ff  mov     rax, [rcx]
0x100492802  mov     [rsp+70h+var_50], r12
0x100492807  mov     r9d, r15d
0x10049280a  mov     r8, r13
0x10049280d  mov     rdx, [r14+18h]
0x100492811  call    qword ptr [rax+20h]
0x100492814  mov     r15d, eax
0x100492817  mov     ecx, [r12]
0x10049281b  add     [r14+18h], rcx
0x10049281f  lea     rax, [rbp+var_10]
0x100492823  mov     [rbp+arg_0], rax
0x100492827  lea     rax, [rbp+var_8]
0x10049282b  mov     [rbp+var_38], rax
0x10049282f  mov     rax, [rbp+var_8]
0x100492833  test    rax, rax
0x100492836  jz      short loc_100492885
0x100492838  cmp     dword ptr [rax], 0
0x10049283b  jz      short loc_100492885
0x10049283d  mov     rdx, gs:58h
0x100492846  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049284d  mov     ecx, [rax]
0x10049284f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100492856  mov     edi, [rax]
0x100492858  add     rdi, [rdx+rcx*8]
0x10049285c  mov     rdx, [rdi+100h]
0x100492863  test    rdx, rdx
0x100492866  jnz     short loc_100492877
0x100492868  xor     ecx, ecx
0x10049286a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100492870  mov     rdx, [rdi+100h]
0x100492877  mov     rcx, [rdx+260h]
0x10049287e  mov     rax, [rcx]
0x100492881  call    qword ptr [rax+8]
0x100492884  nop
0x100492885  mov     rax, [rbp+var_10]
0x100492889  test    rax, rax
0x10049288c  jz      short loc_100492896
0x10049288e  mov     ecx, [rax]; int
0x100492890  call    ?SetInExternalCode@SOS_Task@@SAXH@Z; SOS_Task::SetInExternalCode(int)
0x100492895  nop
0x100492896  not     esi
0x100492898  and     [rbx+268h], esi
0x10049289e  mov     eax, r15d
0x1004928a1  lea     r11, [rsp+70h+var_s0]
0x1004928a6  mov     rbx, [r11+38h]
0x1004928aa  mov     rsi, [r11+40h]
0x1004928ae  mov     rdi, [r11+48h]
0x1004928b2  mov     rsp, r11
0x1004928b5  pop     r15
0x1004928b7  pop     r14
0x1004928b9  pop     r13
0x1004928bb  pop     r12
0x1004928bd  pop     rbp
0x1004928be  retn
```
