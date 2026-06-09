# ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)

- ea: `0x100401010`
- end: `0x1004010a9`
- name: `??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z`
- size: `153`
- prototype: `ExcHandler *__fastcall(ExcHandler *__hidden this, unsigned __int16, unsigned __int8, unsigned __int8, int (*)(int, int, int, int, char *), struct Worker *)`
- caller_count: `13`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100401160`
- `0x1004052b0`
- `0x100405500`
- `0x100405b20`
- `0x10040c8d0`
- `0x10040cda0`
- `0x10040d5d0`
- `0x100418d20`
- `0x10041ef70`
- `0x100429dc0`
- `0x1004369a0`
- `0x100438960`
- `0x100439f60`

## callees

- `0x100401010`

## import_xrefs

- `sqldk!?sm_excGlobalCookie@SOS_PublicGlobals@@2_KA` at `0x100401089`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405452`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405452`
- `sqldk!SystemThread_TlsOffset` at `0x10040105c`
- `sqldk!SystemThread_TlsIndex` at `0x10040104e`

## pseudocode

```c
ExcHandler *__fastcall ExcHandler::ExcHandler(
        ExcHandler *this,
        __int16 a2,
        unsigned __int8 a3,
        char a4,
        int (*a5)(int, int, int, int, char *),
        struct Worker *a6)
{
  struct Worker *v7; // rcx
  __int64 v8; // rdi
  ExcHandler *result; // rax

  *((_QWORD *)this + 2) = a5;
  *((_BYTE *)this + 26) = a4;
  *((_WORD *)this + 12) = a3 + 100 * a2;
  v7 = a6;
  *((_QWORD *)this + 4) = a6;
  if ( !a6 )
  {
    v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v7 = *(struct Worker **)(v8 + 256);
    if ( !v7 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v7 = *(struct Worker **)(v8 + 256);
    }
  }
  *((_QWORD *)this + 1) = *((_QWORD *)v7 + 24);
  *((_QWORD *)v7 + 24) = this;
  result = this;
  *(_QWORD *)this = SOS_PublicGlobals::sm_excGlobalCookie ^ (unsigned __int64)this;
  return result;
}

```

## disassembly

```asm
0x100401010  push    rbx
0x100401012  sub     rsp, 20h
0x100401016  mov     rax, [rsp+28h+arg_20]
0x10040101b  mov     rbx, rcx
0x10040101e  mov     [rcx+10h], rax
0x100401022  movzx   eax, dx
0x100401025  imul    edx, eax, 64h ; 'd'
0x100401028  movzx   eax, r8b
0x10040102c  mov     [rcx+1Ah], r9b
0x100401030  add     dx, ax
0x100401033  mov     [rcx+18h], dx
0x100401037  mov     rcx, [rsp+28h+arg_28]
0x10040103c  mov     [rbx+20h], rcx
0x100401040  test    rcx, rcx
0x100401043  jnz     short loc_10040107E
0x100401045  mov     rdx, gs:58h
0x10040104e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100401055  mov     [rsp+28h+arg_0], rdi
0x10040105a  mov     ecx, [rax]
0x10040105c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100401063  mov     edi, [rax]
0x100401065  add     rdi, [rdx+rcx*8]
0x100401069  mov     rcx, [rdi+100h]
0x100401070  test    rcx, rcx
0x100401073  jz      loc_100405452
0x100401079  mov     rdi, [rsp+28h+arg_0]
0x10040107e  mov     rax, [rcx+0C0h]
0x100401085  mov     [rbx+8], rax
0x100401089  mov     rax, cs:__imp_?sm_excGlobalCookie@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_excGlobalCookie
0x100401090  mov     [rcx+0C0h], rbx
0x100401097  mov     rcx, rbx
0x10040109a  xor     rcx, [rax]
0x10040109d  mov     rax, rbx
0x1004010a0  mov     [rbx], rcx
0x1004010a3  add     rsp, 20h
0x1004010a7  pop     rbx
0x1004010a8  retn
0x100405452  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100405458  mov     rcx, [rdi+100h]
0x10040545f  jmp     loc_100401079
```
