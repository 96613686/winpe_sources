# UdfPrepareMediaEjectWorker

- ea: `0x1400379c0`
- end: `0x140037b9f`
- name: `UdfPrepareMediaEjectWorker`
- size: `479`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x140007aec`
- `0x14000b128`
- `0x14000ca54`
- `0x140031d9c`
- `0x1400379c0`
- `0x14003aa44`
- `0x14004ce50`
- `0x140054560`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140037b3a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037b5f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037b3a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037b5f`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140037ab8`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140037ab8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140037a2b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140037a2b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140037b81`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140037b81`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140037b75`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140037b75`

## pseudocode

```c
void __fastcall UdfPrepareMediaEjectWorker(_QWORD *Entry)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  struct _FILE_OBJECT *v4; // rcx
  __int64 v5; // rcx
  __int128 v6; // [rsp+50h] [rbp-38h] BYREF
  __int64 v7; // [rsp+60h] [rbp-28h]

  v6 = 0;
  v7 = 0;
  v2 = Entry[2];
  UdfSetThreadContext(Entry, &v6);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20) != 0 )
  {
    WPP_SF_q(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      11,
      WPP_047ffe7159223357a68106d654fa515d_Traceguids,
      v2);
  }
  KeEnterCriticalRegion();
  UdfAcquireResource(Entry, v2 + 1480, 0, 0);
  if ( *(_DWORD *)(v2 + 52) == 2 )
  {
    UdfAcquireResource(Entry, v2 + 2024, 0, 0);
    if ( (*(_DWORD *)(v2 + 2128) & 0x16) == 0x10 )
    {
      if ( (*(_DWORD *)(v2 + 48) & 0x200000) != 0 )
      {
        v3 = Entry[1];
        if ( v3 )
          v4 = *(struct _FILE_OBJECT **)(*(_QWORD *)(v3 + 184) + 48LL);
        else
          v4 = *(struct _FILE_OBJECT **)(*(_QWORD *)(v2 + 288) + 504LL);
        if ( v4 )
          FsRtlNotifyVolumeEvent(v4, 0xCu);
        UdfSeqCacheCloseSession((_DWORD)Entry);
      }
      else
      {
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20) != 0 )
        {
          WPP_SF_q(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            12,
            WPP_047ffe7159223357a68106d654fa515d_Traceguids,
            v2);
        }
        UdfStopBackgroundFormat(Entry, v2);
      }
      UdfPerformDevIoCtrl(v5, 2967560, *(_QWORD *)(v2 + 24), 0, 0, 0, 0);
    }
    *(_DWORD *)(v2 + 2128) &= ~0x20u;
    ExReleaseResourceLite((PERESOURCE)(v2 + 2024));
  }
  ExReleaseResourceLite((PERESOURCE)(v2 + 1480));
  ExFreeToNPagedLookasideList(&UdfIrpContextLookasideList, Entry);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400379c0  mov     r11, rsp
0x1400379c3  mov     [r11+18h], rbx
0x1400379c7  mov     [r11+8], rcx
0x1400379cb  push    rsi
0x1400379cc  push    rdi
0x1400379cd  push    r14
0x1400379cf  sub     rsp, 70h
0x1400379d3  mov     rsi, rcx
0x1400379d6  xorps   xmm0, xmm0
0x1400379d9  xor     eax, eax
0x1400379db  movups  [rsp+88h+var_38], xmm0
0x1400379e0  mov     [r11-28h], rax
0x1400379e4  mov     rbx, [rcx+10h]
0x1400379e8  mov     [rsp+88h+arg_8], rbx
0x1400379f0  lea     rdx, [r11-38h]
0x1400379f4  call    UdfSetThreadContext
0x1400379f9  lea     rdi, WPP_GLOBAL_Control
0x140037a00  mov     rcx, cs:WPP_GLOBAL_Control
0x140037a07  cmp     rcx, rdi
0x140037a0a  jz      short loc_140037A2B
0x140037a0c  mov     eax, [rcx+2Ch]
0x140037a0f  test    al, 20h
0x140037a11  jz      short loc_140037A2B
0x140037a13  mov     edx, 0Bh
0x140037a18  mov     r9, rbx
0x140037a1b  lea     r8, WPP_047ffe7159223357a68106d654fa515d_Traceguids
0x140037a22  mov     rcx, [rcx+18h]
0x140037a26  call    WPP_SF_q
0x140037a2b  call    cs:__imp_KeEnterCriticalRegion
0x140037a32  nop     dword ptr [rax+rax+00h]
0x140037a37  nop
0x140037a38  lea     rdx, [rbx+5C8h]
0x140037a3f  xor     r9d, r9d
0x140037a42  xor     r8d, r8d
0x140037a45  mov     rcx, rsi
0x140037a48  call    UdfAcquireResource
0x140037a4d  cmp     dword ptr [rbx+34h], 2
0x140037a51  jnz     loc_140037B46
0x140037a57  lea     r14, [rbx+7E8h]
0x140037a5e  xor     r9d, r9d
0x140037a61  xor     r8d, r8d
0x140037a64  mov     rdx, r14
0x140037a67  mov     rcx, rsi
0x140037a6a  call    UdfAcquireResource
0x140037a6f  mov     eax, [rbx+850h]
0x140037a75  and     al, 16h
0x140037a77  cmp     al, 10h
0x140037a79  jnz     loc_140037B30
0x140037a7f  test    dword ptr [rbx+30h], 200000h
0x140037a86  jz      short loc_140037AD0
0x140037a88  mov     rax, [rsi+8]
0x140037a8c  xor     edi, edi
0x140037a8e  test    rax, rax
0x140037a91  jz      short loc_140037AA0
0x140037a93  mov     rax, [rax+0B8h]
0x140037a9a  mov     rcx, [rax+30h]
0x140037a9e  jmp     short loc_140037AAE
0x140037aa0  mov     rax, [rbx+120h]
0x140037aa7  mov     rcx, [rax+1F8h]; FileObject
0x140037aae  test    rcx, rcx
0x140037ab1  jz      short loc_140037AC4
0x140037ab3  mov     edx, 0Ch; EventCode
0x140037ab8  call    cs:__imp_FsRtlNotifyVolumeEvent
0x140037abf  nop     dword ptr [rax+rax+00h]
0x140037ac4  xor     edx, edx
0x140037ac6  mov     rcx, rsi
0x140037ac9  call    UdfSeqCacheCloseSession
0x140037ace  jmp     short loc_140037B08
0x140037ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x140037ad7  cmp     rcx, rdi
0x140037ada  jz      short loc_140037AFB
0x140037adc  mov     eax, [rcx+2Ch]
0x140037adf  test    al, 20h
0x140037ae1  jz      short loc_140037AFB
0x140037ae3  mov     edx, 0Ch
0x140037ae8  mov     r9, rbx
0x140037aeb  lea     r8, WPP_047ffe7159223357a68106d654fa515d_Traceguids
0x140037af2  mov     rcx, [rcx+18h]
0x140037af6  call    WPP_SF_q
0x140037afb  mov     rdx, rbx
0x140037afe  mov     rcx, rsi
0x140037b01  call    UdfStopBackgroundFormat
0x140037b06  xor     edi, edi
0x140037b08  mov     [rsp+88h+var_40], rdi
0x140037b0d  mov     [rsp+88h+var_48], dil
0x140037b12  mov     [rsp+88h+var_58], edi
0x140037b16  mov     [rsp+88h+var_60], rdi
0x140037b1b  mov     [rsp+88h+var_68], edi
0x140037b1f  xor     r9d, r9d
0x140037b22  mov     r8, [rbx+18h]
0x140037b26  mov     edx, 2D4808h
0x140037b2b  call    UdfPerformDevIoCtrl
0x140037b30  and     dword ptr [rbx+850h], 0FFFFFFDFh
0x140037b37  mov     rcx, r14; Resource
0x140037b3a  call    cs:__imp_ExReleaseResourceLite
0x140037b41  nop     dword ptr [rax+rax+00h]
0x140037b46  jmp     short loc_140037B58
0x140037b48  mov     rsi, [rsp+88h+arg_0]
0x140037b50  mov     rbx, [rsp+88h+arg_8]
0x140037b58  lea     rcx, [rbx+5C8h]; Resource
0x140037b5f  call    cs:__imp_ExReleaseResourceLite
0x140037b66  nop     dword ptr [rax+rax+00h]
0x140037b6b  mov     rdx, rsi; Entry
0x140037b6e  lea     rcx, UdfIrpContextLookasideList; Lookaside
0x140037b75  call    cs:__imp_ExFreeToNPagedLookasideList
0x140037b7c  nop     dword ptr [rax+rax+00h]
0x140037b81  call    cs:__imp_KeLeaveCriticalRegion
0x140037b88  nop     dword ptr [rax+rax+00h]
0x140037b8d  mov     rbx, [rsp+88h+arg_10]
0x140037b95  add     rsp, 70h
0x140037b99  pop     r14
0x140037b9b  pop     rdi
0x140037b9c  pop     rsi
0x140037b9d  retn
0x14005c107  push    rbp
0x14005c109  sub     rsp, 50h
0x14005c10d  mov     rbp, rdx
0x14005c110  mov     rdx, rcx
0x14005c113  mov     rcx, [rbp+90h]
0x14005c11a  call    UdfExceptionFilter
0x14005c11f  nop
0x14005c120  add     rsp, 50h
0x14005c124  pop     rbp
0x14005c125  retn
```
