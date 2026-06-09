# StorAdapterDlrmSystemThread

- ea: `0x140141310`
- end: `0x140141558`
- name: `StorAdapterDlrmSystemThread`
- size: `584`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1401401b0`
- `0x140140250`
- `0x14014036c`
- `0x140140808`
- `0x140140894`
- `0x140141310`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401413e1`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14014149e`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401414ae`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401413e1`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14014149e`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401414ae`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140141479`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140141479`
- `ntoskrnl!ExFreePoolWithTag` at `0x140141448`
- `ntoskrnl!ExFreePoolWithTag` at `0x140141448`
- `ntoskrnl!KeWaitForSingleObject` at `0x140141367`
- `ntoskrnl!KeWaitForSingleObject` at `0x14014151e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140141367`
- `ntoskrnl!KeWaitForSingleObject` at `0x14014151e`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140141467`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140141467`
- `ntoskrnl!PsTerminateSystemThread` at `0x14014153e`
- `ntoskrnl!PsTerminateSystemThread` at `0x14014153e`

## pseudocode

```c
void __fastcall StorAdapterDlrmSystemThread(char *StartContext)
{
  char v2; // si
  NTSTATUS v3; // edx
  unsigned int Flink; // eax
  ULONGLONG UnbiasedInterruptTime; // rax
  unsigned __int64 v6; // rcx
  PLIST_ENTRY v7; // rax
  PLIST_ENTRY v8; // rdi
  ULONGLONG v9; // rax
  unsigned int v10; // edx
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // edx
  __int64 v14; // rcx
  signed __int32 v15[8]; // [rsp+0h] [rbp-68h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+70h] [rbp+8h] BYREF

  Timeout.QuadPart = 0;
  if ( StartContext )
  {
    if ( *(_QWORD *)StartContext )
    {
      if ( *((_QWORD *)StartContext + 1) )
      {
        Timeout.QuadPart = -50000000;
        v2 = 0;
        v3 = KeWaitForSingleObject(StartContext + 40, Executive, 0, 0, &Timeout);
        _InterlockedOr(v15, 0);
        while ( (*((_DWORD *)StartContext + 19) & 1) == 0 )
        {
          if ( v3 == 258 )
          {
            DlrmHandleIdleTimeout(StartContext);
          }
          else
          {
            while ( 1 )
            {
              v7 = ExInterlockedRemoveHeadList((PLIST_ENTRY)(StartContext + 232), (PKSPIN_LOCK)StartContext + 31);
              v8 = v7;
              if ( !v7 )
                break;
              Flink = (unsigned int)v7[1].Flink;
              switch ( LODWORD(v8[1].Flink) )
              {
                case 1:
                case 3:
                  DlrmHandleScaleAction(StartContext, Flink);
                  v2 = 1;
                  break;
                case 4:
                case 5:
                case 6:
                  DlrmHandlePowerStateAction(StartContext, Flink);
                  break;
                case 7:
                  DlrmRecordPciGenerationTime(StartContext, *((unsigned int *)StartContext + 16));
                  break;
                case 8:
                  *((_DWORD *)StartContext + 8) = 1;
                  if ( _interlockedbittestandreset((volatile signed __int32 *)StartContext + 19, 1u) )
                  {
                    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
                    v6 = _InterlockedExchange64((volatile __int64 *)StartContext + 63, 0);
                    if ( v6 )
                    {
                      if ( UnbiasedInterruptTime > v6 )
                        *((_QWORD *)StartContext + 64) += UnbiasedInterruptTime - v6;
                    }
                  }
                  *((_QWORD *)StartContext + 12) = 0;
                  break;
              }
              if ( (BYTE4(v8[1].Flink) & 1) != 0 )
                ExFreePoolWithTag(v8, 0x4D4C6152u);
              else
                ExInterlockedInsertTailList((PLIST_ENTRY)StartContext + 13, v8, (PKSPIN_LOCK)StartContext + 28);
            }
            DlrmUpdateLinkInformation(StartContext);
            if ( v2 )
            {
              *((_QWORD *)StartContext + 10) = KeQueryUnbiasedInterruptTime();
              v9 = KeQueryUnbiasedInterruptTime();
              v10 = 0;
              *((_QWORD *)StartContext + 11) = v9;
              if ( *((_DWORD *)StartContext + 6) )
              {
                do
                {
                  v11 = v10++;
                  *(_QWORD *)(*((_QWORD *)StartContext + 2) + 16 * v11) = 0;
                  v12 = *((_DWORD *)StartContext + 6);
                }
                while ( v10 < v12 );
                v13 = 0;
                if ( v12 )
                {
                  do
                  {
                    v14 = v13++;
                    *(_QWORD *)(*((_QWORD *)StartContext + 2) + 16 * v14 + 8) = 0;
                  }
                  while ( v13 < *((_DWORD *)StartContext + 6) );
                }
              }
              *((_DWORD *)StartContext + 18) = 0;
              v2 = 0;
            }
          }
          v3 = KeWaitForSingleObject(StartContext + 40, Executive, 0, 0, &Timeout);
          _InterlockedOr(v15, 0);
        }
      }
    }
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140141310  mov     r11, rsp
0x140141313  push    rbx
0x140141314  push    rbp
0x140141315  push    rsi
0x140141316  push    rdi
0x140141317  push    r14
0x140141319  push    r15
0x14014131b  sub     rsp, 38h
0x14014131f  mov     qword ptr [r11+8], 0
0x140141327  mov     rbx, rcx
0x14014132a  test    rcx, rcx
0x14014132d  jz      loc_14014153C
0x140141333  cmp     qword ptr [rcx], 0
0x140141337  jz      loc_14014153C
0x14014133d  cmp     qword ptr [rcx+8], 0
0x140141342  jz      loc_14014153C
0x140141348  lea     rax, [r11+8]
0x14014134c  mov     qword ptr [r11+8], 0FFFFFFFFFD050F80h
0x140141354  xor     sil, sil
0x140141357  mov     [r11-48h], rax
0x14014135b  xor     r9d, r9d; Alertable
0x14014135e  xor     r8d, r8d; WaitMode
0x140141361  xor     edx, edx; WaitReason
0x140141363  add     rcx, 28h ; '('; Object
0x140141367  call    cs:__imp_KeWaitForSingleObject
0x14014136e  nop     dword ptr [rax+rax+00h]
0x140141373  mov     edx, eax
0x140141375  lock or [rsp+68h+var_68], 0
0x14014137a  mov     ecx, [rbx+4Ch]
0x14014137d  test    cl, 1
0x140141380  jnz     loc_14014153C
0x140141386  cmp     edx, 102h
0x14014138c  jnz     short loc_14014139B
0x14014138e  mov     rcx, rbx
0x140141391  call    DlrmHandleIdleTimeout
0x140141396  jmp     loc_140141508
0x14014139b  lea     rbp, [rbx+0F8h]
0x1401413a2  lea     r14, [rbx+0E8h]
0x1401413a9  jmp     loc_140141473
0x1401413ae  mov     eax, [rdi+10h]
0x1401413b1  mov     edx, eax
0x1401413b3  sub     edx, 1
0x1401413b6  jz      short loc_14014142D
0x1401413b8  sub     edx, 2
0x1401413bb  jz      short loc_14014142D
0x1401413bd  sub     edx, 1
0x1401413c0  jz      short loc_140141421
0x1401413c2  sub     edx, 1
0x1401413c5  jz      short loc_140141421
0x1401413c7  sub     edx, 1
0x1401413ca  jz      short loc_140141421
0x1401413cc  sub     edx, 1
0x1401413cf  jz      short loc_140141414
0x1401413d1  cmp     edx, 1
0x1401413d4  jnz     short loc_14014143A
0x1401413d6  mov     [rbx+20h], edx
0x1401413d9  lock btr dword ptr [rbx+4Ch], 1
0x1401413df  jnb     short loc_14014140A
0x1401413e1  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1401413e8  nop     dword ptr [rax+rax+00h]
0x1401413ed  xor     ecx, ecx
0x1401413ef  xchg    rcx, [rbx+1F8h]
0x1401413f6  test    rcx, rcx
0x1401413f9  jz      short loc_14014140A
0x1401413fb  cmp     rax, rcx
0x1401413fe  jbe     short loc_14014140A
0x140141400  sub     rax, rcx
0x140141403  add     [rbx+200h], rax
0x14014140a  mov     qword ptr [rbx+60h], 0
0x140141412  jmp     short loc_14014143A
0x140141414  mov     edx, [rbx+40h]
0x140141417  mov     rcx, rbx
0x14014141a  call    DlrmRecordPciGenerationTime
0x14014141f  jmp     short loc_14014143A
0x140141421  mov     edx, eax
0x140141423  mov     rcx, rbx
0x140141426  call    DlrmHandlePowerStateAction
0x14014142b  jmp     short loc_14014143A
0x14014142d  mov     edx, eax
0x14014142f  mov     rcx, rbx
0x140141432  call    DlrmHandleScaleAction
0x140141437  mov     sil, 1
0x14014143a  test    byte ptr [rdi+14h], 1
0x14014143e  jz      short loc_140141456
0x140141440  mov     edx, 4D4C6152h; Tag
0x140141445  mov     rcx, rdi; P
0x140141448  call    cs:__imp_ExFreePoolWithTag
0x14014144f  nop     dword ptr [rax+rax+00h]
0x140141454  jmp     short loc_140141473
0x140141456  lea     r8, [rbx+0E0h]; Lock
0x14014145d  mov     rdx, rdi; ListEntry
0x140141460  lea     rcx, [rbx+0D0h]; ListHead
0x140141467  call    cs:__imp_ExInterlockedInsertTailList
0x14014146e  nop     dword ptr [rax+rax+00h]
0x140141473  mov     rdx, rbp; Lock
0x140141476  mov     rcx, r14; ListHead
0x140141479  call    cs:__imp_ExInterlockedRemoveHeadList
0x140141480  nop     dword ptr [rax+rax+00h]
0x140141485  mov     rdi, rax
0x140141488  test    rax, rax
0x14014148b  jnz     loc_1401413AE
0x140141491  mov     rcx, rbx
0x140141494  call    DlrmUpdateLinkInformation
0x140141499  test    sil, sil
0x14014149c  jz      short loc_140141508
0x14014149e  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1401414a5  nop     dword ptr [rax+rax+00h]
0x1401414aa  mov     [rbx+50h], rax
0x1401414ae  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1401414b5  nop     dword ptr [rax+rax+00h]
0x1401414ba  xor     edx, edx
0x1401414bc  mov     [rbx+58h], rax
0x1401414c0  cmp     [rbx+18h], edx
0x1401414c3  jbe     short loc_1401414FE
0x1401414c5  mov     rax, [rbx+10h]
0x1401414c9  mov     ecx, edx
0x1401414cb  inc     edx
0x1401414cd  add     rcx, rcx
0x1401414d0  mov     qword ptr [rax+rcx*8], 0
0x1401414d8  mov     eax, [rbx+18h]
0x1401414db  cmp     edx, eax
0x1401414dd  jb      short loc_1401414C5
0x1401414df  xor     edx, edx
0x1401414e1  test    eax, eax
0x1401414e3  jz      short loc_1401414FE
0x1401414e5  mov     rax, [rbx+10h]
0x1401414e9  mov     ecx, edx
0x1401414eb  inc     edx
0x1401414ed  add     rcx, rcx
0x1401414f0  mov     qword ptr [rax+rcx*8+8], 0
0x1401414f9  cmp     edx, [rbx+18h]
0x1401414fc  jb      short loc_1401414E5
0x1401414fe  mov     dword ptr [rbx+48h], 0
0x140141505  xor     sil, sil
0x140141508  lea     rax, [rsp+68h+arg_0]
0x14014150d  xor     r9d, r9d; Alertable
0x140141510  xor     r8d, r8d; WaitMode
0x140141513  mov     [rsp+68h+Timeout], rax; Timeout
0x140141518  xor     edx, edx; WaitReason
0x14014151a  lea     rcx, [rbx+28h]; Object
0x14014151e  call    cs:__imp_KeWaitForSingleObject
0x140141525  nop     dword ptr [rax+rax+00h]
0x14014152a  mov     edx, eax
0x14014152c  lock or [rsp+68h+var_68], 0
0x140141531  mov     eax, [rbx+4Ch]
0x140141534  test    al, 1
0x140141536  jz      loc_140141386
0x14014153c  xor     ecx, ecx; ExitStatus
0x14014153e  call    cs:__imp_PsTerminateSystemThread
0x140141545  nop     dword ptr [rax+rax+00h]
0x14014154a  add     rsp, 38h
0x14014154e  pop     r15
0x140141550  pop     r14
0x140141552  pop     rdi
0x140141553  pop     rsi
0x140141554  pop     rbp
0x140141555  pop     rbx
0x140141556  retn
```
