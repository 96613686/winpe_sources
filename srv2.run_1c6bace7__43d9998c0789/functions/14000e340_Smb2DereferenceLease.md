# Smb2DereferenceLease

- ea: `0x14000e340`
- end: `0x14000e464`
- name: `Smb2DereferenceLease`
- size: `292`
- prototype: ``
- caller_count: `27`
- callee_count: `6`
- tags: ``

## callers

- `0x14000ac30`
- `0x14000ad08`
- `0x14000c680`
- `0x14000ca00`
- `0x14000cdf0`
- `0x14000dfb0`
- `0x14000f420`
- `0x140010150`
- `0x1400101f0`
- `0x140014120`
- `0x1400159d0`
- `0x140019450`
- `0x14001c2d0`
- `0x1400219d4`
- `0x140021b20`
- `0x14002c820`
- `0x14002cdb0`
- `0x14002d904`
- `0x14002e27c`
- `0x14002ead4`
- `0x14002eb84`
- `0x14002edbc`
- `0x140076130`
- `0x140079130`
- `0x1400792e0`
- `0x140079c80`
- `0x140085d90`

## callees

- `0x140004960`
- `0x140005070`
- `0x14000e340`
- `0x140022a10`
- `0x140038490`
- `0x1400852b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000e413`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000e413`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e3b6`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e3b6`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b3eb`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b3eb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000e42e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000e42e`

## string_xrefs

- `0x14000e3f4`: `Srv2PostToThreadPool`

## pseudocode

```c
int __fastcall Smb2DereferenceLease(char *P)
{
  signed __int64 v2; // rbx
  PSLIST_ENTRY v3; // rax
  __int64 v4; // rdx
  bool v5; // zf
  __int64 v6; // rbx
  union _SLIST_HEADER *v7; // rbx
  int v9; // [rsp+20h] [rbp-78h]
  PVOID BackTrace[2]; // [rsp+60h] [rbp-38h] BYREF
  __int128 v11; // [rsp+70h] [rbp-28h]
  __int64 v12; // [rsp+80h] [rbp-18h]

  v2 = _InterlockedDecrement64((volatile signed __int64 *)P);
  if ( v2 == -1 )
    __int2c();
  LODWORD(v3) = (_DWORD)WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0 )
  {
    v12 = 0;
    *(_OWORD *)BackTrace = 0;
    v11 = 0;
    RtlCaptureStackBackTrace(1u, 5u, BackTrace, 0);
    v3 = (PSLIST_ENTRY)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      LODWORD(v3) = WPP_SF_qPPqqqqq(
                      WPP_GLOBAL_Control->AttachedDevice,
                      15,
                      WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids,
                      P,
                      v2 + 1,
                      v2,
                      BackTrace[0],
                      BackTrace[1],
                      v11,
                      *((_QWORD *)&v11 + 1),
                      v12);
    }
  }
  if ( !v2 )
  {
    if ( KeGetCurrentIrql() >= 2u )
    {
      v5 = *((_DWORD *)P + 2) == 5;
      *((_QWORD *)P + 6) = Smb2LeaseFree;
      *((_DWORD *)P + 18) = 0;
      if ( v5 )
      {
        LOBYTE(v9) = 1;
        LOBYTE(v4) = 1;
        SRV2_PERF_ENTER_EX(P + 584, v4, 391, "Srv2PostToThreadPool", v9);
      }
      v6 = *(_QWORD *)(*((_QWORD *)P + 8) + 136LL);
      v7 = *(union _SLIST_HEADER **)(v6 + 8LL * KeGetCurrentNodeNumber() + 8);
      v3 = ExpInterlockedPushEntrySList(v7, (PSLIST_ENTRY)P + 2);
      if ( !v3 && *((_WORD *)&v7[4].Header8 + 1) )
        LODWORD(v3) = RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v7);
    }
    else
    {
      LODWORD(v3) = Smb2LeaseFree(P);
    }
  }
  return (int)v3;
}

```

## disassembly

```asm
0x14000e340  mov     [rsp+arg_8], rbx
0x14000e345  push    rdi
0x14000e346  sub     rsp, 90h
0x14000e34d  mov     rax, cs:__security_cookie
0x14000e354  xor     rax, rsp
0x14000e357  mov     [rsp+98h+var_10], rax
0x14000e35f  mov     rdi, rcx
0x14000e362  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14000e369  lock xadd [rcx], rbx
0x14000e36e  dec     rbx
0x14000e371  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000e375  jnb     loc_14000E45D
0x14000e37b  mov     rax, cs:WPP_GLOBAL_Control
0x14000e382  test    dword ptr [rax+2Ch], 40000000h
0x14000e389  jnz     loc_14003B3C2
0x14000e38f  test    rbx, rbx
0x14000e392  jz      short loc_14000E3B6
0x14000e394  mov     rcx, [rsp+98h+var_10]
0x14000e39c  xor     rcx, rsp; StackCookie
0x14000e39f  call    __security_check_cookie
0x14000e3a4  mov     rbx, [rsp+98h+arg_8]
0x14000e3ac  add     rsp, 90h
0x14000e3b3  pop     rdi
0x14000e3b4  retn
0x14000e3b6  call    cs:__imp_KeGetCurrentIrql
0x14000e3bd  nop     dword ptr [rax+rax+00h]
0x14000e3c2  cmp     al, 2
0x14000e3c4  jnb     short loc_14000E3D0
0x14000e3c6  mov     rcx, rdi; P
0x14000e3c9  call    Smb2LeaseFree
0x14000e3ce  jmp     short loc_14000E394
0x14000e3d0  cmp     dword ptr [rdi+8], 5
0x14000e3d4  lea     rax, Smb2LeaseFree
0x14000e3db  mov     [rdi+30h], rax
0x14000e3df  mov     dword ptr [rdi+48h], 0
0x14000e3e6  jnz     short loc_14000E408
0x14000e3e8  lea     rcx, [rdi+248h]
0x14000e3ef  mov     byte ptr [rsp+98h+var_78], 1
0x14000e3f4  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14000e3fb  mov     r8d, 187h
0x14000e401  mov     dl, 1
0x14000e403  call    SRV2_PERF_ENTER_EX
0x14000e408  mov     rax, [rdi+40h]
0x14000e40c  mov     rbx, [rax+88h]
0x14000e413  call    cs:__imp_KeGetCurrentNodeNumber
0x14000e41a  nop     dword ptr [rax+rax+00h]
0x14000e41f  movzx   eax, ax
0x14000e422  lea     rdx, [rdi+20h]; ListEntry
0x14000e426  mov     rbx, [rbx+rax*8+8]
0x14000e42b  mov     rcx, rbx; ListHead
0x14000e42e  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000e435  nop     dword ptr [rax+rax+00h]
0x14000e43a  test    rax, rax
0x14000e43d  jnz     loc_14000E394
0x14000e443  movzx   ecx, word ptr [rbx+42h]
0x14000e447  cmp     ax, cx
0x14000e44a  jz      loc_14000E394
0x14000e450  mov     rcx, rbx
0x14000e453  call    RfspThreadPoolNodeWakeIdleWorker
0x14000e458  jmp     loc_14000E394
0x14000e45d  int     2Ch; Windows NT - assertion failure
0x14000e45f  jmp     loc_14000E37B
0x14003b3c2  xorps   xmm0, xmm0
0x14003b3c5  lea     r8, [rsp+98h+BackTrace]; BackTrace
0x14003b3ca  xor     eax, eax
0x14003b3cc  xor     r9d, r9d; BackTraceHash
0x14003b3cf  mov     edx, 5; FramesToCapture
0x14003b3d4  mov     [rsp+98h+var_18], rax
0x14003b3dc  mov     ecx, 1; FramesToSkip
0x14003b3e1  movups  xmmword ptr [rsp+98h+BackTrace], xmm0
0x14003b3e6  movups  [rsp+98h+var_28], xmm0
0x14003b3eb  call    cs:__imp_RtlCaptureStackBackTrace
0x14003b3f2  nop     dword ptr [rax+rax+00h]
0x14003b3f7  mov     r10, cs:WPP_GLOBAL_Control
0x14003b3fe  lea     rax, WPP_GLOBAL_Control
0x14003b405  cmp     r10, rax
0x14003b408  jz      loc_14000E38F
0x14003b40e  test    dword ptr [r10+2Ch], 40000000h
0x14003b416  jz      loc_14000E38F
0x14003b41c  cmp     byte ptr [r10+29h], 4
0x14003b421  jb      loc_14000E38F
0x14003b427  mov     rax, [rsp+98h+var_18]
0x14003b42f  lea     rcx, [rbx+1]
0x14003b433  mov     [rsp+98h+var_48], rax
0x14003b438  lea     r8, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids
0x14003b43f  mov     rax, qword ptr [rsp+98h+var_28+8]
0x14003b444  mov     edx, 0Fh
0x14003b449  mov     qword ptr [rsp+98h+var_58+8], rax
0x14003b44e  mov     r9, rdi
0x14003b451  mov     rax, qword ptr [rsp+98h+var_28]
0x14003b456  mov     qword ptr [rsp+98h+var_58], rax
0x14003b45b  mov     rax, [rsp+98h+BackTrace+8]
0x14003b460  mov     [rsp+98h+var_60], rax
0x14003b465  mov     rax, [rsp+98h+BackTrace]
0x14003b46a  mov     [rsp+98h+var_68], rax
0x14003b46f  mov     [rsp+98h+var_70], rbx
0x14003b474  mov     [rsp+98h+var_78], rcx
0x14003b479  mov     rcx, [r10+18h]
0x14003b47d  call    WPP_SF_qPPqqqqq
0x14003b482  nop
0x14003b483  jmp     loc_14000E38F
```
