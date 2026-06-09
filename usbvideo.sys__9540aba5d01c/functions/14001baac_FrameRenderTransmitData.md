# FrameRenderTransmitData

- ea: `0x14001baac`
- end: `0x14001bdf6`
- name: `FrameRenderTransmitData`
- size: `842`
- prototype: `__int64 __fastcall(PKSPIN Pin)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14001ba04`
- `0x14001c1d0`
- `0x14001ca10`
- `0x14001cc0c`

## callees

- `0x14001baac`
- `0x14001c768`
- `0x14001cd64`
- `0x14001d0cc`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14001baf1`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14001baf1`
- `ntoskrnl!KeSetEvent` at `0x14001bdca`
- `ntoskrnl!KeSetEvent` at `0x14001bdca`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x14001bda8`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x14001bda8`
- `ks!KsStreamPointerClone` at `0x14001bc05`
- `ks!KsStreamPointerClone` at `0x14001bc05`
- `ks!KsStreamPointerUnlock` at `0x14001bd48`
- `ks!KsStreamPointerUnlock` at `0x14001bd48`
- `ks!KsPinGetLeadingEdgeStreamPointer` at `0x14001bb2e`
- `ks!KsPinGetLeadingEdgeStreamPointer` at `0x14001bb2e`
- `ks!KsStreamPointerDelete` at `0x14001bbd5`
- `ks!KsStreamPointerDelete` at `0x14001bbd5`

## pseudocode

```c
__int64 __fastcall FrameRenderTransmitData(PKSPIN Pin)
{
  char *Context; // r15
  PKSPIN v2; // r12
  __int64 v3; // rbx
  struct _LIST_ENTRY *v4; // r13
  char v5; // al
  _DWORD *v6; // rsi
  unsigned int v7; // r14d
  PKSSTREAM_POINTER LeadingEdgeStreamPointer; // rax
  struct _KSSTREAM_POINTER *v9; // rbp
  struct _KSSTREAM_POINTER *v10; // rdi
  PKSSTREAM_HEADER StreamHeader; // r14
  _QWORD *v12; // rdi
  struct _KSSTREAM_POINTER *v13; // rcx
  bool v14; // zf
  int v15; // eax
  int v16; // r12d
  int v17; // edi
  __int64 v18; // rdx
  char v21; // [rsp+78h] [rbp+10h] BYREF
  char v22; // [rsp+80h] [rbp+18h]

  Context = (char *)Pin->Context;
  v2 = Pin;
  v21 = 0;
  v3 = *((_QWORD *)Context + 12);
  if ( *(_DWORD *)(v3 + 8) )
  {
    --*(_DWORD *)(v3 + 60);
    v4 = ExInterlockedRemoveHeadList((PLIST_ENTRY)(v3 + 304), (PKSPIN_LOCK)(v3 + 272));
    if ( v4 )
    {
      v5 = 0;
      v6 = (_DWORD *)(v3 + 100);
      v22 = 0;
      v7 = 0;
      while ( 1 )
      {
        if ( v5 )
          return v7;
        LeadingEdgeStreamPointer = KsPinGetLeadingEdgeStreamPointer(v2, KSSTREAM_POINTER_STATE_LOCKED);
        v9 = LeadingEdgeStreamPointer;
        if ( LeadingEdgeStreamPointer )
          break;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            24,
            WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids,
            Context,
            v4);
        v10 = *(struct _KSSTREAM_POINTER **)(v3 + 176);
        if ( !v10 )
        {
          ExInterlockedInsertHeadList((PLIST_ENTRY)(v3 + 304), v4, (PKSPIN_LOCK)(v3 + 272));
          if ( ++*(_DWORD *)(v3 + 60) == 4 )
            KeSetEvent((PRKEVENT)(Context + 128), 0, 0);
          return 0;
        }
        *(_DWORD *)(v3 + 20) = 1;
        (*(void (__fastcall **)(_QWORD, _QWORD, PVOID, _QWORD, int))(**((_QWORD **)Context + 49) + 136LL))(
          *((_QWORD *)Context + 49),
          *((_QWORD *)Context + 2),
          v10->StreamHeader->Data,
          v10->StreamHeader->DataUsed,
          1);
LABEL_29:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            25,
            WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids,
            Context,
            v4);
        v7 = FrameRenderPrepareDataBuffer(v4, v10, (unsigned int)*v6, &v21);
        v16 = *(_DWORD *)(v3 + 68);
        v17 = v10->StreamHeader->DataUsed - *v6;
        LOBYTE(v18) = v17 == v16;
        if ( Pin->ClientState == KSSTATE_PAUSE || *(_DWORD *)(v3 + 20) )
          LOBYTE(v18) = 0;
        if ( v9 )
        {
          if ( (v9->StreamHeader->OptionsFlags & 4) != 0 )
          {
            if ( (_BYTE)v18 )
            {
              *(_DWORD *)(v3 + 16) = 0;
            }
            else if ( v17 == v16 && *(_DWORD *)(v3 + 20) || !*v6 )
            {
              *(_DWORD *)(v3 + 16) = 1;
            }
          }
          KsStreamPointerUnlock(v9, v18);
        }
        if ( v17 == v16 )
          *v6 = 0;
        else
          *v6 += *(_DWORD *)(v3 + 68);
        *(_DWORD *)(v3 + 68) = 0;
        if ( v21 )
        {
          v7 = FrameRenderSubmitDataBuffer(v4, v18);
          v5 = 1;
          v22 = 1;
        }
        else
        {
          v5 = v22;
        }
        v2 = Pin;
      }
      if ( !*v6 )
      {
        StreamHeader = LeadingEdgeStreamPointer->StreamHeader;
        v12 = (_QWORD *)(v3 + 176);
        v13 = *(struct _KSSTREAM_POINTER **)(v3 + 176);
        if ( v13 )
        {
          KsStreamPointerDelete(v13);
          *v12 = 0;
        }
        if ( (StreamHeader->OptionsFlags & 0x200) == 0
          && KsStreamPointerClone(v9, FrameRenderCancelCallback, 8u, (PKSSTREAM_POINTER *)(v3 + 176)) >= 0 )
        {
          **(_QWORD **)*v12 = v3;
        }
        if ( v2->ClientState == KSSTATE_PAUSE )
          (*(void (__fastcall **)(_QWORD, _QWORD, PVOID, _QWORD, int))(**((_QWORD **)Context + 49) + 136LL))(
            *((_QWORD *)Context + 49),
            *((_QWORD *)Context + 2),
            v9->StreamHeader->Data,
            v9->StreamHeader->DataUsed,
            1);
      }
      if ( (v9->StreamHeader->OptionsFlags & 4) != 0 )
      {
        if ( *(_DWORD *)(v3 + 16) || !*v6 )
          goto LABEL_27;
        v14 = *(_QWORD *)(v3 + 176) == 0;
      }
      else
      {
        if ( !*(_DWORD *)(v3 + 20) )
          goto LABEL_27;
        v14 = *v6 == 0;
      }
      if ( !v14 )
      {
        v10 = *(struct _KSSTREAM_POINTER **)(v3 + 176);
        v15 = 1;
LABEL_28:
        *(_DWORD *)(v3 + 20) = v15;
        goto LABEL_29;
      }
LABEL_27:
      v10 = v9;
      v15 = 0;
      goto LABEL_28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001baac  mov     [rsp+arg_18], rbx
0x14001bab1  mov     [rsp+arg_0], rcx
0x14001bab6  push    rbp
0x14001bab7  push    rsi
0x14001bab8  push    rdi
0x14001bab9  push    r12
0x14001babb  push    r13
0x14001babd  push    r14
0x14001babf  push    r15
0x14001bac1  sub     rsp, 30h
0x14001bac5  mov     r15, [rcx+10h]
0x14001bac9  xor     edi, edi
0x14001bacb  mov     r12, rcx
0x14001bace  mov     [rsp+68h+arg_8], dil
0x14001bad3  mov     rbx, [r15+60h]
0x14001bad7  cmp     [rbx+8], edi
0x14001bada  jz      loc_14001BDD6
0x14001bae0  dec     dword ptr [rbx+3Ch]
0x14001bae3  lea     rdx, [rbx+110h]; Lock
0x14001baea  lea     rcx, [rbx+130h]; ListHead
0x14001baf1  call    cs:__imp_ExInterlockedRemoveHeadList
0x14001baf8  nop     dword ptr [rax+rax+00h]
0x14001bafd  mov     r13, rax
0x14001bb00  test    rax, rax
0x14001bb03  jz      loc_14001BDD6
0x14001bb09  mov     al, dil
0x14001bb0c  lea     rsi, [rbx+64h]
0x14001bb10  mov     [rsp+68h+arg_10], al
0x14001bb17  mov     r14d, edi
0x14001bb1a  test    al, al
0x14001bb1c  jnz     loc_14001BDF1
0x14001bb22  mov     r14d, 1
0x14001bb28  mov     rcx, r12; Pin
0x14001bb2b  mov     edx, r14d; State
0x14001bb2e  call    cs:__imp_KsPinGetLeadingEdgeStreamPointer
0x14001bb35  nop     dword ptr [rax+rax+00h]
0x14001bb3a  mov     rbp, rax
0x14001bb3d  test    rax, rax
0x14001bb40  jnz     short loc_14001BBBA
0x14001bb42  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb49  lea     rax, WPP_GLOBAL_Control
0x14001bb50  cmp     rcx, rax
0x14001bb53  jz      short loc_14001BB76
0x14001bb55  cmp     byte ptr [rcx+29h], 5
0x14001bb59  jb      short loc_14001BB76
0x14001bb5b  mov     rcx, [rcx+18h]
0x14001bb5f  lea     edx, [rbp+18h]
0x14001bb62  mov     r9, r15
0x14001bb65  mov     [rsp+68h+var_48], r13
0x14001bb6a  lea     r8, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids
0x14001bb71  call    WPP_SF_qq
0x14001bb76  mov     rdi, [rbx+0B0h]
0x14001bb7d  test    rdi, rdi
0x14001bb80  jz      loc_14001BD97
0x14001bb86  mov     [rbx+14h], r14d
0x14001bb8a  mov     r8, [rdi+10h]
0x14001bb8e  mov     rcx, [r15+188h]
0x14001bb95  mov     rdx, [r15+10h]
0x14001bb99  mov     dword ptr [rsp+68h+var_48], r14d
0x14001bb9e  mov     r9d, [r8+24h]
0x14001bba2  mov     rax, [rcx]
0x14001bba5  mov     r8, [r8+28h]
0x14001bba9  mov     rax, [rax+88h]
0x14001bbb0  call    _guard_dispatch_icall
0x14001bbb5  jmp     loc_14001BC97
0x14001bbba  cmp     [rsi], edi
0x14001bbbc  jnz     loc_14001BC5C
0x14001bbc2  mov     r14, [rax+10h]
0x14001bbc6  lea     rdi, [rbx+0B0h]
0x14001bbcd  mov     rcx, [rdi]; StreamPointer
0x14001bbd0  test    rcx, rcx
0x14001bbd3  jz      short loc_14001BBE8
0x14001bbd5  call    cs:__imp_KsStreamPointerDelete
0x14001bbdc  nop     dword ptr [rax+rax+00h]
0x14001bbe1  mov     qword ptr [rdi], 0
0x14001bbe8  test    dword ptr [r14+30h], 200h
0x14001bbf0  jnz     short loc_14001BC1E
0x14001bbf2  mov     r9, rdi; CloneStreamPointer
0x14001bbf5  lea     rdx, FrameRenderCancelCallback; CancelCallback
0x14001bbfc  mov     r8d, 8; ContextSize
0x14001bc02  mov     rcx, rbp; StreamPointer
0x14001bc05  call    cs:__imp_KsStreamPointerClone
0x14001bc0c  nop     dword ptr [rax+rax+00h]
0x14001bc11  test    eax, eax
0x14001bc13  js      short loc_14001BC1E
0x14001bc15  mov     rax, [rdi]
0x14001bc18  mov     rcx, [rax]
0x14001bc1b  mov     [rcx], rbx
0x14001bc1e  cmp     dword ptr [r12+80h], 2
0x14001bc27  mov     r14d, 1
0x14001bc2d  jnz     short loc_14001BC5A
0x14001bc2f  mov     r8, [rbp+10h]
0x14001bc33  mov     rcx, [r15+188h]
0x14001bc3a  mov     rdx, [r15+10h]
0x14001bc3e  mov     dword ptr [rsp+68h+var_48], r14d
0x14001bc43  mov     r9d, [r8+24h]
0x14001bc47  mov     rax, [rcx]
0x14001bc4a  mov     r8, [r8+28h]
0x14001bc4e  mov     rax, [rax+88h]
0x14001bc55  call    _guard_dispatch_icall
0x14001bc5a  xor     edi, edi
0x14001bc5c  mov     rax, [rbp+10h]
0x14001bc60  mov     ecx, [rax+30h]
0x14001bc63  test    cl, 4
0x14001bc66  jnz     short loc_14001BC71
0x14001bc68  cmp     [rbx+14h], edi
0x14001bc6b  jz      short loc_14001BC8F
0x14001bc6d  cmp     [rsi], edi
0x14001bc6f  jmp     short loc_14001BC81
0x14001bc71  cmp     [rbx+10h], edi
0x14001bc74  jnz     short loc_14001BC8F
0x14001bc76  cmp     [rsi], edi
0x14001bc78  jbe     short loc_14001BC8F
0x14001bc7a  cmp     [rbx+0B0h], rdi
0x14001bc81  jz      short loc_14001BC8F
0x14001bc83  mov     rdi, [rbx+0B0h]
0x14001bc8a  mov     eax, r14d
0x14001bc8d  jmp     short loc_14001BC94
0x14001bc8f  mov     rdi, rbp
0x14001bc92  xor     eax, eax
0x14001bc94  mov     [rbx+14h], eax
0x14001bc97  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc9e  lea     rax, WPP_GLOBAL_Control
0x14001bca5  cmp     rcx, rax
0x14001bca8  jz      short loc_14001BCCD
0x14001bcaa  cmp     byte ptr [rcx+29h], 5
0x14001bcae  jb      short loc_14001BCCD
0x14001bcb0  mov     rcx, [rcx+18h]
0x14001bcb4  lea     r8, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids
0x14001bcbb  mov     edx, 19h
0x14001bcc0  mov     [rsp+68h+var_48], r13
0x14001bcc5  mov     r9, r15
0x14001bcc8  call    WPP_SF_qq
0x14001bccd  mov     r8d, [rsi]
0x14001bcd0  lea     r9, [rsp+68h+arg_8]
0x14001bcd5  mov     rdx, rdi
0x14001bcd8  mov     rcx, r13
0x14001bcdb  call    FrameRenderPrepareDataBuffer
0x14001bce0  mov     rcx, [rdi+10h]
0x14001bce4  mov     r14d, eax
0x14001bce7  mov     r8d, [rsi]
0x14001bcea  mov     r12d, [rbx+44h]
0x14001bcee  mov     rax, [rsp+68h+arg_0]
0x14001bcf3  mov     edi, [rcx+24h]
0x14001bcf6  sub     edi, r8d
0x14001bcf9  cmp     edi, r12d
0x14001bcfc  setz    dl
0x14001bcff  cmp     dword ptr [rax+80h], 2
0x14001bd06  jz      short loc_14001BD0E
0x14001bd08  cmp     dword ptr [rbx+14h], 0
0x14001bd0c  jz      short loc_14001BD10
0x14001bd0e  xor     dl, dl; Eject
0x14001bd10  test    rbp, rbp
0x14001bd13  jz      short loc_14001BD54
0x14001bd15  mov     rax, [rbp+10h]
0x14001bd19  mov     ecx, [rax+30h]
0x14001bd1c  test    cl, 4
0x14001bd1f  jz      short loc_14001BD45
0x14001bd21  test    dl, dl
0x14001bd23  jz      short loc_14001BD2E
0x14001bd25  mov     dword ptr [rbx+10h], 0
0x14001bd2c  jmp     short loc_14001BD45
0x14001bd2e  cmp     edi, r12d
0x14001bd31  jnz     short loc_14001BD39
0x14001bd33  cmp     dword ptr [rbx+14h], 0
0x14001bd37  jnz     short loc_14001BD3E
0x14001bd39  test    r8d, r8d
0x14001bd3c  jnz     short loc_14001BD45
0x14001bd3e  mov     dword ptr [rbx+10h], 1
0x14001bd45  mov     rcx, rbp; StreamPointer
0x14001bd48  call    cs:__imp_KsStreamPointerUnlock
0x14001bd4f  nop     dword ptr [rax+rax+00h]
0x14001bd54  cmp     edi, r12d
0x14001bd57  jnz     short loc_14001BD5F
0x14001bd59  xor     edi, edi
0x14001bd5b  mov     [rsi], edi
0x14001bd5d  jmp     short loc_14001BD66
0x14001bd5f  mov     eax, [rbx+44h]
0x14001bd62  add     [rsi], eax
0x14001bd64  xor     edi, edi
0x14001bd66  mov     [rbx+44h], edi
0x14001bd69  cmp     [rsp+68h+arg_8], dil
0x14001bd6e  jz      short loc_14001BD86
0x14001bd70  mov     rcx, r13
0x14001bd73  call    FrameRenderSubmitDataBuffer
0x14001bd78  mov     r14d, eax
0x14001bd7b  mov     al, 1
0x14001bd7d  mov     [rsp+68h+arg_10], al
0x14001bd84  jmp     short loc_14001BD8D
0x14001bd86  mov     al, [rsp+68h+arg_10]
0x14001bd8d  mov     r12, [rsp+68h+arg_0]
0x14001bd92  jmp     loc_14001BB1A
0x14001bd97  lea     r8, [rbx+110h]; Lock
0x14001bd9e  mov     rdx, r13; ListEntry
0x14001bda1  lea     rcx, [rbx+130h]; ListHead
0x14001bda8  call    cs:__imp_ExInterlockedInsertHeadList
0x14001bdaf  nop     dword ptr [rax+rax+00h]
0x14001bdb4  add     [rbx+3Ch], r14d
0x14001bdb8  cmp     dword ptr [rbx+3Ch], 4
0x14001bdbc  jnz     short loc_14001BDD6
0x14001bdbe  lea     rcx, [r15+80h]; Event
0x14001bdc5  xor     r8d, r8d; Wait
0x14001bdc8  xor     edx, edx; Increment
0x14001bdca  call    cs:__imp_KeSetEvent
0x14001bdd1  nop     dword ptr [rax+rax+00h]
0x14001bdd6  xor     eax, eax
0x14001bdd8  mov     rbx, [rsp+68h+arg_18]
0x14001bde0  add     rsp, 30h
0x14001bde4  pop     r15
0x14001bde6  pop     r14
0x14001bde8  pop     r13
0x14001bdea  pop     r12
0x14001bdec  pop     rdi
0x14001bded  pop     rsi
0x14001bdee  pop     rbp
0x14001bdef  retn
0x14001bdf1  mov     eax, r14d
0x14001bdf4  jmp     short loc_14001BDD8
```
