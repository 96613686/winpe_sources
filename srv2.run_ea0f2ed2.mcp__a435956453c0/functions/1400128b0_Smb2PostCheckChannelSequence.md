# Smb2PostCheckChannelSequence

- ea: `0x1400128b0`
- end: `0x140012bdf`
- name: `Smb2PostCheckChannelSequence`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140076130`

## callees

- `0x140004960`
- `0x140005070`
- `0x1400128b0`
- `0x140028d34`
- `0x140038490`
- `0x140080a10`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140012b85`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140012b85`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012af4`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012af4`
- `ntoskrnl!KeSetEvent` at `0x1400129ac`
- `ntoskrnl!KeSetEvent` at `0x1400129ac`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c28a`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c28a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140012ba0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140012ba0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012b26`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012b26`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012b10`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012b10`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140012912`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140012912`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001294b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012990`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001294b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012990`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012a37`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012a37`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012a8d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012a8d`

## string_xrefs

- `0x140012b66`: `Srv2PostToThreadPool`

## pseudocode

```c
void __fastcall Smb2PostCheckChannelSequence(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rcx
  _DWORD *v4; // rax
  __int64 v5; // rdx
  _QWORD *v6; // rdi
  __int64 v7; // r14
  __m128i v8; // xmm2
  __m128i v9; // xmm2
  __int64 v10; // rsi
  KIRQL v11; // bp
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdi
  signed __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  bool v18; // zf
  __int64 v19; // rbx
  __int64 v20; // rbx
  int v21; // [rsp+20h] [rbp-88h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-58h] BYREF
  PVOID BackTrace[2]; // [rsp+68h] [rbp-40h] BYREF
  __int64 v24; // [rsp+78h] [rbp-30h]

  v1 = *(_QWORD *)(a1 + 560);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( *(_BYTE *)(v1 + 6) )
  {
    v2 = *(_QWORD *)(v1 + 72);
    if ( v2 )
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v2 + 112), &LockHandle);
      v3 = *(_QWORD *)(v1 + 72);
      if ( *(_WORD *)(v1 + 12) == *(_WORD *)(v3 + 864) )
        --*(_DWORD *)(v3 + 868);
      else
        --*(_DWORD *)(v3 + 872);
      v4 = *(_DWORD **)(v1 + 72);
      if ( v4[3] == 220 || v4[217] || v4[218] )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      else
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        KeSetEvent((PRKEVENT)(*(_QWORD *)(v1 + 72) + 880LL), 0, 0);
        v5 = *(_QWORD *)(v1 + 72);
        v6 = (_QWORD *)(v5 + 904);
        v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 64) + 160LL) + 2184LL);
        v8 = _mm_add_epi32(
               _mm_unpacklo_epi16(
                 _mm_unpacklo_epi8(_mm_cvtsi32_si128(*(_DWORD *)(v5 + 924)), (__m128i)0LL),
                 (__m128i)0LL),
               _mm_unpacklo_epi16(
                 _mm_unpacklo_epi8(_mm_cvtsi32_si128(*(_DWORD *)(v5 + 920)), (__m128i)0LL),
                 (__m128i)0LL));
        v9 = _mm_add_epi32(v8, _mm_srli_si128(v8, 8));
        v10 = *(_QWORD *)(v7 + 56)
            + 32LL * ((unsigned int)_mm_cvtsi128_si32(_mm_add_epi32(v9, _mm_srli_si128(v9, 4))) % *(_DWORD *)v7);
        if ( (*(_DWORD *)(v10 + 12) & 1) != 0 )
        {
          v11 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v10);
        }
        else
        {
          v11 = 0;
          ExAcquirePushLockExclusiveEx(v10, 0);
        }
        v12 = (_QWORD *)*v6;
        if ( (_QWORD *)*v6 != v6 )
        {
          if ( (_QWORD *)v12[1] != v6 || (v13 = (_QWORD *)v6[1], (_QWORD *)*v13 != v6) )
            __fastfail(3u);
          *v13 = v12;
          v12[1] = v13;
          v6[1] = v6;
          *v6 = v6;
          _InterlockedDecrement((volatile signed __int32 *)(v7 + 8));
          --*(_DWORD *)(v10 + 8);
        }
        if ( (*(_DWORD *)(v10 + 12) & 1) != 0 )
          ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v10, v11);
        else
          ExReleasePushLockExclusiveEx(v10, 0);
        v14 = *(_QWORD *)(v1 + 72);
        v15 = _InterlockedDecrement64((volatile signed __int64 *)v14);
        if ( v15 == -1 )
          __int2c();
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
        {
          v24 = 0;
          *(_OWORD *)BackTrace = 0;
          RtlCaptureStackBackTrace(0, 3u, BackTrace, 0);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qPPqqq(
              WPP_GLOBAL_Control->AttachedDevice,
              35,
              &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
              v14,
              v15 + 1,
              v15,
              BackTrace[0],
              BackTrace[1],
              v24);
          }
        }
        if ( !v15 )
        {
          if ( KeGetCurrentIrql() )
          {
            v18 = *(_DWORD *)(v14 + 8) == 5;
            *(_QWORD *)(v14 + 48) = Smb2FreeFile;
            *(_DWORD *)(v14 + 72) = 1;
            if ( v18 )
            {
              LOBYTE(v21) = 1;
              LOBYTE(v16) = 1;
              SRV2_PERF_ENTER_EX(v14 + 584, v16, 391, "Srv2PostToThreadPool", v21);
            }
            v19 = *(_QWORD *)(*(_QWORD *)(v14 + 64) + 144LL);
            v20 = *(_QWORD *)(v19 + 8LL * KeGetCurrentNodeNumber() + 8);
            if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v20, (PSLIST_ENTRY)(v14 + 32)) )
            {
              if ( *(_WORD *)(v20 + 66) )
                RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v20);
            }
          }
          else
          {
            Smb2FreeFile((char *)v14, v16, v17);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1400128b0  push    rbx
0x1400128b2  sub     rsp, 0A0h
0x1400128b9  mov     rax, cs:__security_cookie
0x1400128c0  xor     rax, rsp
0x1400128c3  mov     [rsp+0A8h+var_28], rax
0x1400128cb  mov     rbx, [rcx+230h]
0x1400128d2  xor     eax, eax
0x1400128d4  xorps   xmm0, xmm0
0x1400128d7  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x1400128dc  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x1400128e1  cmp     [rbx+6], al
0x1400128e4  jnz     short loc_140012900
0x1400128e6  mov     rcx, [rsp+0A8h+var_28]
0x1400128ee  xor     rcx, rsp; StackCookie
0x1400128f1  call    __security_check_cookie
0x1400128f6  add     rsp, 0A0h
0x1400128fd  pop     rbx
0x1400128fe  retn
0x140012900  mov     rcx, [rbx+48h]
0x140012904  test    rcx, rcx
0x140012907  jz      short loc_1400128E6
0x140012909  add     rcx, 70h ; 'p'; SpinLock
0x14001290d  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x140012912  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140012919  nop     dword ptr [rax+rax+00h]
0x14001291e  mov     rcx, [rbx+48h]
0x140012922  movzx   eax, word ptr [rcx+360h]
0x140012929  cmp     [rbx+0Ch], ax
0x14001292d  jnz     loc_140012B37
0x140012933  dec     dword ptr [rcx+364h]
0x140012939  mov     rax, [rbx+48h]
0x14001293d  cmp     dword ptr [rax+0Ch], 0DCh
0x140012944  jnz     short loc_140012959
0x140012946  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14001294b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140012952  nop     dword ptr [rax+rax+00h]
0x140012957  jmp     short loc_1400128E6
0x140012959  cmp     dword ptr [rax+364h], 0
0x140012960  jnz     short loc_140012946
0x140012962  cmp     dword ptr [rax+368h], 0
0x140012969  jnz     short loc_140012946
0x14001296b  mov     [rsp+0A8h+arg_10], rsi
0x140012973  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140012978  mov     [rsp+0A8h+var_10], rdi
0x140012980  mov     [rsp+0A8h+var_18], r14
0x140012988  mov     [rsp+0A8h+arg_8], rbp
0x140012990  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140012997  nop     dword ptr [rax+rax+00h]
0x14001299c  mov     rcx, [rbx+48h]
0x1400129a0  xor     r8d, r8d; Wait
0x1400129a3  add     rcx, 370h; Event
0x1400129aa  xor     edx, edx; Increment
0x1400129ac  call    cs:__imp_KeSetEvent
0x1400129b3  nop     dword ptr [rax+rax+00h]
0x1400129b8  mov     rdx, [rbx+48h]
0x1400129bc  xorps   xmm0, xmm0
0x1400129bf  mov     rax, [rdx+40h]
0x1400129c3  lea     rdi, [rdx+388h]
0x1400129ca  movd    xmm2, dword ptr [rdx+39Ch]
0x1400129d2  movd    xmm1, dword ptr [rdx+398h]
0x1400129da  xor     edx, edx
0x1400129dc  punpcklbw xmm2, xmm0
0x1400129e0  mov     rcx, [rax+0A0h]
0x1400129e7  punpcklwd xmm2, xmm0
0x1400129eb  punpcklbw xmm1, xmm0
0x1400129ef  punpcklwd xmm1, xmm0
0x1400129f3  mov     r14, [rcx+888h]
0x1400129fa  paddd   xmm2, xmm1
0x1400129fe  movdqa  xmm0, xmm2
0x140012a02  psrldq  xmm0, 8
0x140012a07  paddd   xmm2, xmm0
0x140012a0b  movdqa  xmm0, xmm2
0x140012a0f  psrldq  xmm0, 4
0x140012a14  paddd   xmm2, xmm0
0x140012a18  movd    eax, xmm2
0x140012a1c  div     dword ptr [r14]
0x140012a1f  mov     esi, edx
0x140012a21  shl     rsi, 5
0x140012a25  add     rsi, [r14+38h]
0x140012a29  mov     rcx, rsi; SpinLock
0x140012a2c  mov     eax, [rsi+0Ch]
0x140012a2f  test    al, 1
0x140012a31  jz      loc_140012B21
0x140012a37  call    cs:__imp_ExAcquireSpinLockExclusive
0x140012a3e  nop     dword ptr [rax+rax+00h]
0x140012a43  movzx   ebp, al
0x140012a46  mov     rax, [rdi]
0x140012a49  cmp     rax, rdi
0x140012a4c  jz      short loc_140012A7B
0x140012a4e  cmp     [rax+8], rdi
0x140012a52  jnz     loc_140012BD1
0x140012a58  mov     rcx, [rdi+8]
0x140012a5c  cmp     [rcx], rdi
0x140012a5f  jnz     loc_140012BD1
0x140012a65  mov     [rcx], rax
0x140012a68  mov     [rax+8], rcx
0x140012a6c  mov     [rdi+8], rdi
0x140012a70  mov     [rdi], rdi
0x140012a73  lock dec dword ptr [r14+8]
0x140012a78  dec     dword ptr [rsi+8]
0x140012a7b  mov     eax, [rsi+0Ch]
0x140012a7e  mov     rcx, rsi; SpinLock
0x140012a81  test    al, 1
0x140012a83  jz      loc_140012B0E
0x140012a89  movzx   edx, bpl; OldIrql
0x140012a8d  call    cs:__imp_ExReleaseSpinLockExclusive
0x140012a94  nop     dword ptr [rax+rax+00h]
0x140012a99  mov     rdi, [rbx+48h]
0x140012a9d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140012aa4  lock xadd [rdi], rbx
0x140012aa9  dec     rbx
0x140012aac  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140012ab0  jnb     loc_140012BD8
0x140012ab6  mov     rax, cs:WPP_GLOBAL_Control
0x140012abd  test    dword ptr [rax+2Ch], 100000h
0x140012ac4  jnz     loc_14003C26C
0x140012aca  test    rbx, rbx
0x140012acd  jz      short loc_140012AF4
0x140012acf  mov     rbp, [rsp+0A8h+arg_8]
0x140012ad7  mov     rsi, [rsp+0A8h+arg_10]
0x140012adf  mov     rdi, [rsp+0A8h+var_10]
0x140012ae7  mov     r14, [rsp+0A8h+var_18]
0x140012aef  jmp     loc_1400128E6
0x140012af4  call    cs:__imp_KeGetCurrentIrql
0x140012afb  nop     dword ptr [rax+rax+00h]
0x140012b00  test    al, al
0x140012b02  jnz     short loc_140012B42
0x140012b04  mov     rcx, rdi; P
0x140012b07  call    Smb2FreeFile
0x140012b0c  jmp     short loc_140012ACF
0x140012b0e  xor     edx, edx
0x140012b10  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140012b17  nop     dword ptr [rax+rax+00h]
0x140012b1c  jmp     loc_140012A99
0x140012b21  xor     bpl, bpl
0x140012b24  xor     edx, edx
0x140012b26  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140012b2d  nop     dword ptr [rax+rax+00h]
0x140012b32  jmp     loc_140012A46
0x140012b37  dec     dword ptr [rcx+368h]
0x140012b3d  jmp     loc_140012939
0x140012b42  cmp     dword ptr [rdi+8], 5
0x140012b46  lea     rax, Smb2FreeFile
0x140012b4d  mov     [rdi+30h], rax
0x140012b51  mov     dword ptr [rdi+48h], 1
0x140012b58  jnz     short loc_140012B7A
0x140012b5a  lea     rcx, [rdi+248h]
0x140012b61  mov     byte ptr [rsp+0A8h+var_88], 1
0x140012b66  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140012b6d  mov     r8d, 187h
0x140012b73  mov     dl, 1
0x140012b75  call    SRV2_PERF_ENTER_EX
0x140012b7a  mov     rax, [rdi+40h]
0x140012b7e  mov     rbx, [rax+90h]
0x140012b85  call    cs:__imp_KeGetCurrentNodeNumber
0x140012b8c  nop     dword ptr [rax+rax+00h]
0x140012b91  movzx   eax, ax
0x140012b94  lea     rdx, [rdi+20h]; ListEntry
0x140012b98  mov     rbx, [rbx+rax*8+8]
0x140012b9d  mov     rcx, rbx; ListHead
0x140012ba0  call    cs:__imp_ExpInterlockedPushEntrySList
0x140012ba7  nop     dword ptr [rax+rax+00h]
0x140012bac  test    rax, rax
0x140012baf  jnz     loc_140012ACF
0x140012bb5  movzx   eax, word ptr [rbx+42h]
0x140012bb9  xor     ecx, ecx
0x140012bbb  cmp     cx, ax
0x140012bbe  jz      loc_140012ACF
0x140012bc4  mov     rcx, rbx
0x140012bc7  call    RfspThreadPoolNodeWakeIdleWorker
0x140012bcc  jmp     loc_140012ACF
0x140012bd1  mov     ecx, 3
0x140012bd6  int     29h; Win8: RtlFailFast(ecx)
0x140012bd8  int     2Ch; Windows NT - assertion failure
0x140012bda  jmp     loc_140012AB6
0x14003c26c  xorps   xmm0, xmm0
0x14003c26f  lea     r8, [rsp+0A8h+BackTrace]; BackTrace
0x14003c274  xor     eax, eax
0x14003c276  xor     r9d, r9d; BackTraceHash
0x14003c279  mov     edx, 3; FramesToCapture
0x14003c27e  mov     [rsp+0A8h+var_30], rax
0x14003c283  xor     ecx, ecx; FramesToSkip
0x14003c285  movups  xmmword ptr [rsp+0A8h+BackTrace], xmm0
0x14003c28a  call    cs:__imp_RtlCaptureStackBackTrace
0x14003c291  nop     dword ptr [rax+rax+00h]
0x14003c296  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c29d  lea     rax, WPP_GLOBAL_Control
0x14003c2a4  cmp     rcx, rax
0x14003c2a7  jz      loc_140012ACA
0x14003c2ad  test    dword ptr [rcx+2Ch], 100000h
0x14003c2b4  jz      loc_140012ACA
0x14003c2ba  cmp     byte ptr [rcx+29h], 2
0x14003c2be  jb      loc_140012ACA
0x14003c2c4  mov     rax, [rsp+0A8h+var_30]
0x14003c2c9  lea     r8, [rbx+1]
0x14003c2cd  mov     rcx, [rcx+18h]
0x14003c2d1  mov     edx, 23h ; '#'
0x14003c2d6  mov     [rsp+0A8h+var_68], rax
0x14003c2db  mov     r9, rdi
0x14003c2de  mov     rax, [rsp+0A8h+BackTrace+8]
0x14003c2e3  mov     [rsp+0A8h+var_70], rax
0x14003c2e8  mov     rax, [rsp+0A8h+BackTrace]
0x14003c2ed  mov     [rsp+0A8h+var_78], rax
0x14003c2f2  mov     [rsp+0A8h+var_80], rbx
0x14003c2f7  mov     [rsp+0A8h+var_88], r8
0x14003c2fc  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14003c303  call    WPP_SF_qPPqqq
0x14003c308  nop
0x14003c309  jmp     loc_140012ACA
```
