# VidTriggerIoctlCreate

- ea: `0x1400973f8`
- end: `0x14009769d`
- name: `VidTriggerIoctlCreate`
- size: `677`
- prototype: `__int64 __fastcall(__int64, _OWORD *, _QWORD *, HANDLE *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140035698`

## callees

- `0x140024754`
- `0x140030790`
- `0x1400307d0`
- `0x140038630`
- `0x1400973f8`
- `0x140097c54`
- `0x140097f1c`
- `0x140097f7c`
- `0x1400ef710`

## import_xrefs

- `ntoskrnl!ExEventObjectType` at `0x14009753c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140097557`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140097557`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400974c6`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400974c6`
- `ntoskrnl!ExCreateDpcEvent` at `0x1400974f9`
- `ntoskrnl!ExCreateDpcEvent` at `0x1400974f9`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140097651`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140097651`
- `ntoskrnl!ExQueueDpcEventWait` at `0x140097663`
- `ntoskrnl!ExQueueDpcEventWait` at `0x140097663`
- `ntoskrnl!ZwClose` at `0x140097606`
- `ntoskrnl!ZwClose` at `0x140097606`
- `ntoskrnl!KeInitializeDpc` at `0x1400974e0`
- `ntoskrnl!KeInitializeDpc` at `0x1400974e0`
- `ntoskrnl!ExAllocatePool2` at `0x140097462`
- `ntoskrnl!ExAllocatePool2` at `0x140097462`

## string_xrefs

- `0x140097441`: `VidTriggerIoctlCreate`
- `0x140097483`: `VidTriggerIoctlCreate`
- `0x140097518`: `VidTriggerIoctlCreate`
- `0x140097576`: `VidTriggerIoctlCreate`
- `0x1400975a4`: `VidTriggerIoctlCreate`
- `0x1400975e8`: `VidTriggerIoctlCreate`
- `0x14009763f`: `VidTriggerIoctlCreate`

## pseudocode

```c
__int64 __fastcall VidTriggerIoctlCreate(__int64 a1, _OWORD *a2, _QWORD *a3, HANDLE *a4)
{
  struct _EX_RUNDOWN_REF *Pool2; // rdi
  NTSTATUS Entry; // ebx
  __int128 v10; // xmm1
  HANDLE v11; // rcx
  HANDLE Handle; // [rsp+40h] [rbp-68h] BYREF
  PVOID Object; // [rsp+48h] [rbp-60h] BYREF
  _QWORD v15[11]; // [rsp+50h] [rbp-58h] BYREF

  Pool2 = 0;
  Object = 0;
  v15[0] = 0;
  Handle = 0;
  Entry = VidTriggerpValidateParameters(a2);
  if ( Entry >= 0 )
  {
    Pool2 = (struct _EX_RUNDOWN_REF *)ExAllocatePool2(64, 200, 1917084758);
    if ( Pool2 )
    {
      Pool2->Count = *(ULONG_PTR *)(a1 + 648);
      *(_OWORD *)&Pool2[13].Count = *a2;
      v10 = a2[1];
      LODWORD(Pool2[17].Count) |= 0xFFFFFFu;
      Pool2[20].Count = -1;
      *(_OWORD *)&Pool2[15].Count = v10;
      ExInitializeRundownProtection(Pool2 + 11);
      KeInitializeDpc((PRKDPC)&Pool2[3], VidTriggerpDpcRoutine, Pool2);
      Entry = ExCreateDpcEvent(&Pool2[2], &Object, &Pool2[3]);
      if ( Entry >= 0 )
      {
        Entry = ObOpenObjectByPointer(Object, 0, 0, 2u, (POBJECT_TYPE)ExEventObjectType, 0, &Handle);
        if ( Entry >= 0 )
        {
          if ( *(_DWORD *)a2 == 3 && (Entry = VidTriggerpCreatePort(Pool2), Entry < 0) )
          {
            VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 259);
          }
          else
          {
            VidLockAcquireExclusive(a1 + 3368);
            Entry = VidHandleTableAllocateEntry(a1 + 3336, Pool2, v15);
            if ( Entry >= 0 )
            {
              ExAcquireRundownProtection(Pool2 + 11);
              ExQueueDpcEventWait(Pool2[2].Count, 0);
              VidLockRelease(a1 + 3368);
              Entry = 0;
              *a3 = v15[0];
              *a4 = Handle;
              return (unsigned int)Entry;
            }
            VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 272);
            VidLockRelease(a1 + 3368);
          }
        }
        else
        {
          VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 247);
        }
      }
      else
      {
        VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 233);
      }
    }
    else
    {
      VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 220);
    }
  }
  else
  {
    VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 213);
  }
  v11 = Handle;
  if ( Handle )
    ZwClose(Handle);
  if ( Pool2 )
    VidTriggerpFree(v11, Pool2);
  if ( Entry < 0 )
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidTriggerIoctlCreate",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidtrigger.c",
      313,
      Entry,
      a1 + 656);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x1400973f8  push    rbx
0x1400973fa  push    rbp
0x1400973fb  push    rsi
0x1400973fc  push    rdi
0x1400973fd  push    r12
0x1400973ff  push    r13
0x140097401  push    r14
0x140097403  push    r15
0x140097405  sub     rsp, 68h
0x140097409  xor     edi, edi
0x14009740b  mov     rbp, rcx
0x14009740e  mov     rcx, rdx
0x140097411  mov     [rsp+0A8h+Object], rdi
0x140097416  mov     [rsp+0A8h+var_58], rdi
0x14009741b  mov     r14, r9
0x14009741e  mov     [rsp+0A8h+var_68], rdi
0x140097423  mov     r15, r8
0x140097426  mov     rsi, rdx
0x140097429  call    VidTriggerpValidateParameters
0x14009742e  mov     ebx, eax
0x140097430  test    eax, eax
0x140097432  jns     short loc_140097452
0x140097434  mov     r8d, 0D5h
0x14009743a  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097441  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x140097448  call    VidTraceErrorInternal0
0x14009744d  jmp     loc_1400975FC
0x140097452  mov     edx, 0C8h
0x140097457  mov     ecx, 40h ; '@'
0x14009745c  mov     r8d, 72446456h
0x140097462  call    cs:__imp_ExAllocatePool2
0x140097469  nop     dword ptr [rax+rax+00h]
0x14009746e  mov     rdi, rax
0x140097471  test    rax, rax
0x140097474  jnz     short loc_140097494
0x140097476  mov     r8d, 0DCh
0x14009747c  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097483  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x14009748a  call    VidTraceErrorInternal0
0x14009748f  jmp     loc_1400975FC
0x140097494  mov     rax, [rbp+288h]
0x14009749b  lea     rcx, [rdi+58h]; RunRef
0x14009749f  mov     [rdi], rax
0x1400974a2  movups  xmm0, xmmword ptr [rsi]
0x1400974a5  movups  xmmword ptr [rdi+68h], xmm0
0x1400974a9  movups  xmm1, xmmword ptr [rsi+10h]
0x1400974ad  or      dword ptr [rdi+88h], 0FFFFFFh
0x1400974b7  mov     qword ptr [rdi+0A0h], 0FFFFFFFFFFFFFFFFh
0x1400974c2  movups  xmmword ptr [rdi+78h], xmm1
0x1400974c6  call    cs:__imp_ExInitializeRundownProtection
0x1400974cd  nop     dword ptr [rax+rax+00h]
0x1400974d2  mov     r8, rdi; DeferredContext
0x1400974d5  lea     rdx, VidTriggerpDpcRoutine; DeferredRoutine
0x1400974dc  lea     rcx, [rdi+18h]; Dpc
0x1400974e0  call    cs:__imp_KeInitializeDpc
0x1400974e7  nop     dword ptr [rax+rax+00h]
0x1400974ec  lea     r8, [rdi+18h]
0x1400974f0  lea     rdx, [rsp+0A8h+Object]
0x1400974f5  lea     rcx, [rdi+10h]
0x1400974f9  call    cs:__imp_ExCreateDpcEvent
0x140097500  nop     dword ptr [rax+rax+00h]
0x140097505  mov     ebx, eax
0x140097507  test    eax, eax
0x140097509  jns     short loc_140097529
0x14009750b  mov     r8d, 0E9h
0x140097511  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097518  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x14009751f  call    VidTraceErrorInternal0
0x140097524  jmp     loc_1400975FC
0x140097529  lea     rax, [rsp+0A8h+var_68]
0x14009752e  mov     r9d, 2; DesiredAccess
0x140097534  mov     [rsp+0A8h+Handle], rax; Handle
0x140097539  xor     r8d, r8d; PassedAccessState
0x14009753c  mov     rax, cs:ExEventObjectType
0x140097543  xor     edx, edx; HandleAttributes
0x140097545  mov     [rsp+0A8h+AccessMode], 0; AccessMode
0x14009754a  mov     rcx, [rax]
0x14009754d  mov     [rsp+0A8h+ObjectType], rcx; ObjectType
0x140097552  mov     rcx, [rsp+0A8h+Object]; Object
0x140097557  call    cs:__imp_ObOpenObjectByPointer
0x14009755e  nop     dword ptr [rax+rax+00h]
0x140097563  mov     ebx, eax
0x140097565  test    eax, eax
0x140097567  jns     short loc_140097584
0x140097569  mov     r8d, 0F7h
0x14009756f  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097576  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x14009757d  call    VidTraceErrorInternal0
0x140097582  jmp     short loc_1400975FC
0x140097584  cmp     dword ptr [rsi], 3
0x140097587  jnz     short loc_1400975B2
0x140097589  mov     rcx, rdi
0x14009758c  call    VidTriggerpCreatePort
0x140097591  mov     ebx, eax
0x140097593  test    eax, eax
0x140097595  jns     short loc_1400975B2
0x140097597  mov     r8d, 103h
0x14009759d  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x1400975a4  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x1400975ab  call    VidTraceErrorInternal0
0x1400975b0  jmp     short loc_1400975FC
0x1400975b2  lea     rsi, [rbp+0D28h]
0x1400975b9  mov     rcx, rsi
0x1400975bc  call    VidLockAcquireExclusive
0x1400975c1  lea     rcx, [rbp+0D08h]
0x1400975c8  mov     rdx, rdi
0x1400975cb  lea     r8, [rsp+0A8h+var_58]
0x1400975d0  call    VidHandleTableAllocateEntry
0x1400975d5  mov     ebx, eax
0x1400975d7  test    eax, eax
0x1400975d9  jns     short loc_14009764D
0x1400975db  mov     r8d, 110h
0x1400975e1  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x1400975e8  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x1400975ef  call    VidTraceErrorInternal0
0x1400975f4  mov     rcx, rsi
0x1400975f7  call    VidLockRelease
0x1400975fc  mov     rcx, [rsp+0A8h+var_68]; Handle
0x140097601  test    rcx, rcx
0x140097604  jz      short loc_140097612
0x140097606  call    cs:__imp_ZwClose
0x14009760d  nop     dword ptr [rax+rax+00h]
0x140097612  test    rdi, rdi
0x140097615  jz      short loc_14009761F
0x140097617  mov     rdx, rdi
0x14009761a  call    VidTriggerpFree
0x14009761f  test    ebx, ebx
0x140097621  jns     short loc_140097689
0x140097623  lea     rax, [rbp+290h]
0x14009762a  mov     r9d, ebx
0x14009762d  mov     r8d, 139h
0x140097633  mov     [rsp+0A8h+ObjectType], rax
0x140097638  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x14009763f  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x140097646  call    VidTraceErrorStatusPartitionInternal0
0x14009764b  jmp     short loc_140097689
0x14009764d  lea     rcx, [rdi+58h]; RunRef
0x140097651  call    cs:__imp_ExAcquireRundownProtection
0x140097658  nop     dword ptr [rax+rax+00h]
0x14009765d  mov     rcx, [rdi+10h]
0x140097661  xor     edx, edx
0x140097663  call    cs:__imp_ExQueueDpcEventWait
0x14009766a  nop     dword ptr [rax+rax+00h]
0x14009766f  mov     rcx, rsi
0x140097672  call    VidLockRelease
0x140097677  mov     rax, [rsp+0A8h+var_58]
0x14009767c  xor     ebx, ebx
0x14009767e  mov     [r15], rax
0x140097681  mov     rax, [rsp+0A8h+var_68]
0x140097686  mov     [r14], rax
0x140097689  mov     eax, ebx
0x14009768b  add     rsp, 68h
0x14009768f  pop     r15
0x140097691  pop     r14
0x140097693  pop     r13
0x140097695  pop     r12
0x140097697  pop     rdi
0x140097698  pop     rsi
0x140097699  pop     rbp
0x14009769a  pop     rbx
0x14009769b  retn
```
