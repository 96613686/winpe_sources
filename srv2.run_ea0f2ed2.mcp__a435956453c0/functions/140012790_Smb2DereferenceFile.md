# Smb2DereferenceFile

- ea: `0x140012790`
- end: `0x1400128aa`
- name: `Smb2DereferenceFile`
- size: `282`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `31`
- callee_count: `6`
- tags: ``

## callers

- `0x14000bbb8`
- `0x140011214`
- `0x140015af8`
- `0x140019c48`
- `0x14001b628`
- `0x14001c8ec`
- `0x140020f78`
- `0x14002143c`
- `0x140021cc0`
- `0x1400220c0`
- `0x140029228`
- `0x14002a740`
- `0x14002b7f8`
- `0x14002be90`
- `0x14002bff0`
- `0x14002c820`
- `0x14002d738`
- `0x14002ddb0`
- `0x140065688`
- `0x1400664c4`
- `0x14006794c`
- `0x140068f48`
- `0x140076130`
- `0x140076e38`
- `0x140078e30`
- `0x14007a89c`
- `0x14007c6b0`
- `0x14007c8d0`
- `0x1400834f0`
- `0x1400876e0`
- `0x1400952cc`

## callees

- `0x140004960`
- `0x140005070`
- `0x140012790`
- `0x140028d34`
- `0x140038490`
- `0x140080a10`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140012857`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140012857`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400127fa`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400127fa`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c1e6`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c1e6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140012872`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140012872`

## string_xrefs

- `0x140012838`: `Srv2PostToThreadPool`

## pseudocode

```c
int __fastcall Smb2DereferenceFile(char *P)
{
  signed __int64 v2; // rbx
  PSLIST_ENTRY v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  bool v6; // zf
  __int64 v7; // rbx
  union _SLIST_HEADER *v8; // rbx
  int v10; // [rsp+20h] [rbp-58h]
  PVOID BackTrace[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v12; // [rsp+60h] [rbp-18h]

  v2 = _InterlockedDecrement64((volatile signed __int64 *)P);
  if ( v2 == -1 )
    __int2c();
  LODWORD(v3) = (_DWORD)WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
  {
    v12 = 0;
    *(_OWORD *)BackTrace = 0;
    RtlCaptureStackBackTrace(0, 3u, BackTrace, 0);
    v3 = (PSLIST_ENTRY)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      LODWORD(v3) = WPP_SF_qPPqqq(
                      WPP_GLOBAL_Control->AttachedDevice,
                      35,
                      &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
                      P,
                      v2 + 1,
                      v2,
                      BackTrace[0],
                      BackTrace[1],
                      v12);
    }
  }
  if ( !v2 )
  {
    if ( KeGetCurrentIrql() )
    {
      v6 = *((_DWORD *)P + 2) == 5;
      *((_QWORD *)P + 6) = Smb2FreeFile;
      *((_DWORD *)P + 18) = 1;
      if ( v6 )
      {
        LOBYTE(v10) = 1;
        LOBYTE(v4) = 1;
        SRV2_PERF_ENTER_EX(P + 584, v4, 391, "Srv2PostToThreadPool", v10);
      }
      v7 = *(_QWORD *)(*((_QWORD *)P + 8) + 144LL);
      v8 = *(union _SLIST_HEADER **)(v7 + 8LL * KeGetCurrentNodeNumber() + 8);
      v3 = ExpInterlockedPushEntrySList(v8, (PSLIST_ENTRY)P + 2);
      if ( !v3 )
      {
        LODWORD(v3) = *((unsigned __int16 *)&v8[4].Header8 + 1);
        if ( (_WORD)v3 )
          LODWORD(v3) = RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v8);
      }
    }
    else
    {
      LODWORD(v3) = Smb2FreeFile(P, v4, v5);
    }
  }
  return (int)v3;
}

```

## disassembly

```asm
0x140012790  mov     [rsp+arg_8], rbx
0x140012795  push    rdi
0x140012796  sub     rsp, 70h
0x14001279a  mov     rax, cs:__security_cookie
0x1400127a1  xor     rax, rsp
0x1400127a4  mov     [rsp+78h+var_10], rax
0x1400127a9  mov     rdi, rcx
0x1400127ac  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400127b3  lock xadd [rcx], rbx
0x1400127b8  dec     rbx
0x1400127bb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400127bf  jnb     loc_1400128A3
0x1400127c5  mov     rax, cs:WPP_GLOBAL_Control
0x1400127cc  test    dword ptr [rax+2Ch], 100000h
0x1400127d3  jnz     loc_14003C1C8
0x1400127d9  test    rbx, rbx
0x1400127dc  jz      short loc_1400127FA
0x1400127de  mov     rcx, [rsp+78h+var_10]
0x1400127e3  xor     rcx, rsp; StackCookie
0x1400127e6  call    __security_check_cookie
0x1400127eb  mov     rbx, [rsp+78h+arg_8]
0x1400127f3  add     rsp, 70h
0x1400127f7  pop     rdi
0x1400127f8  retn
0x1400127fa  call    cs:__imp_KeGetCurrentIrql
0x140012801  nop     dword ptr [rax+rax+00h]
0x140012806  test    al, al
0x140012808  jnz     short loc_140012814
0x14001280a  mov     rcx, rdi; P
0x14001280d  call    Smb2FreeFile
0x140012812  jmp     short loc_1400127DE
0x140012814  cmp     dword ptr [rdi+8], 5
0x140012818  lea     rax, Smb2FreeFile
0x14001281f  mov     [rdi+30h], rax
0x140012823  mov     dword ptr [rdi+48h], 1
0x14001282a  jnz     short loc_14001284C
0x14001282c  lea     rcx, [rdi+248h]
0x140012833  mov     byte ptr [rsp+78h+var_58], 1
0x140012838  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14001283f  mov     r8d, 187h
0x140012845  mov     dl, 1
0x140012847  call    SRV2_PERF_ENTER_EX
0x14001284c  mov     rax, [rdi+40h]
0x140012850  mov     rbx, [rax+90h]
0x140012857  call    cs:__imp_KeGetCurrentNodeNumber
0x14001285e  nop     dword ptr [rax+rax+00h]
0x140012863  movzx   eax, ax
0x140012866  lea     rdx, [rdi+20h]; ListEntry
0x14001286a  mov     rbx, [rbx+rax*8+8]
0x14001286f  mov     rcx, rbx; ListHead
0x140012872  call    cs:__imp_ExpInterlockedPushEntrySList
0x140012879  nop     dword ptr [rax+rax+00h]
0x14001287e  test    rax, rax
0x140012881  jnz     loc_1400127DE
0x140012887  movzx   eax, word ptr [rbx+42h]
0x14001288b  xor     ecx, ecx
0x14001288d  cmp     cx, ax
0x140012890  jz      loc_1400127DE
0x140012896  mov     rcx, rbx
0x140012899  call    RfspThreadPoolNodeWakeIdleWorker
0x14001289e  jmp     loc_1400127DE
0x1400128a3  int     2Ch; Windows NT - assertion failure
0x1400128a5  jmp     loc_1400127C5
0x14003c1c8  xorps   xmm0, xmm0
0x14003c1cb  lea     r8, [rsp+78h+BackTrace]; BackTrace
0x14003c1d0  xor     eax, eax
0x14003c1d2  xor     r9d, r9d; BackTraceHash
0x14003c1d5  mov     edx, 3; FramesToCapture
0x14003c1da  mov     [rsp+78h+var_18], rax
0x14003c1df  xor     ecx, ecx; FramesToSkip
0x14003c1e1  movups  xmmword ptr [rsp+78h+BackTrace], xmm0
0x14003c1e6  call    cs:__imp_RtlCaptureStackBackTrace
0x14003c1ed  nop     dword ptr [rax+rax+00h]
0x14003c1f2  mov     r10, cs:WPP_GLOBAL_Control
0x14003c1f9  lea     rax, WPP_GLOBAL_Control
0x14003c200  cmp     r10, rax
0x14003c203  jz      loc_1400127D9
0x14003c209  test    dword ptr [r10+2Ch], 100000h
0x14003c211  jz      loc_1400127D9
0x14003c217  cmp     byte ptr [r10+29h], 2
0x14003c21c  jb      loc_1400127D9
0x14003c222  mov     rax, [rsp+78h+var_18]
0x14003c227  lea     rcx, [rbx+1]
0x14003c22b  mov     [rsp+78h+var_38], rax
0x14003c230  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14003c237  mov     rax, [rsp+78h+BackTrace+8]
0x14003c23c  mov     edx, 23h ; '#'
0x14003c241  mov     [rsp+78h+var_40], rax
0x14003c246  mov     r9, rdi
0x14003c249  mov     rax, [rsp+78h+BackTrace]
0x14003c24e  mov     [rsp+78h+var_48], rax
0x14003c253  mov     [rsp+78h+var_50], rbx
0x14003c258  mov     [rsp+78h+var_58], rcx
0x14003c25d  mov     rcx, [r10+18h]
0x14003c261  call    WPP_SF_qPPqqq
0x14003c266  nop
0x14003c267  jmp     loc_1400127D9
```
