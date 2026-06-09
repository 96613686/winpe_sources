# RndisDevHostAcquireOperationByIndex

- ea: `0x1401a866c`
- end: `0x1401a88e4`
- name: `RndisDevHostAcquireOperationByIndex`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401ab23c`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x140046f1c`
- `0x14007a890`
- `0x14008497c`
- `0x1400a0ef8`
- `0x1401a866c`
- `0x1401bbcb0`
- `0x1401bbe80`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401a879a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401a8892`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401a879a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401a8892`
- `ntoskrnl!InitializeSListHead` at `0x1401a86ae`
- `ntoskrnl!InitializeSListHead` at `0x1401a86ae`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401a87c6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401a88ad`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401a87c6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401a88ad`

## pseudocode

```c
__int64 __fastcall RndisDevHostAcquireOperationByIndex(_QWORD *a1, __int64 a2, unsigned int a3, PSLIST_ENTRY *a4)
{
  __int64 v5; // rbp
  int v7; // edx
  union _SLIST_HEADER *v8; // rdi
  unsigned int v9; // ebx
  int v10; // edx
  int v11; // r8d
  int v12; // edx
  int v13; // r8d
  int v14; // edx
  PSLIST_ENTRY v15; // rax
  int v16; // edx
  PSLIST_ENTRY v17; // rcx
  PSLIST_ENTRY v18; // rax
  int v19; // edx
  struct _SLIST_ENTRY *v20; // rax
  union _SLIST_HEADER SListHead; // [rsp+50h] [rbp-48h] BYREF

  v5 = a3;
  *a4 = 0;
  SListHead = 0;
  InitializeSListHead(&SListHead);
  if ( (unsigned int)v5 < 5 )
  {
    v8 = (union _SLIST_HEADER *)(a1 - 500598);
    if ( ((unsigned __int8 (__fastcall *)(_QWORD, _QWORD))*(a1 - 2))(*a1, 0) )
    {
      while ( !*a4 )
      {
        v15 = ExpInterlockedPopEntrySList(v8 + 306);
        if ( !v15 )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v16,
            19,
            23,
            (__int64)WPP_73b674cdc296383cdca7632fcc353cea_Traceguids,
            (__int64)"!\"NULL slistEntry.\"");
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
          v9 = -2147483631;
          LOBYTE(v19) = 2;
          WPP_RECORDER_SF_id(
            VmsIfrLog,
            v19,
            20,
            24,
            (__int64)WPP_73b674cdc296383cdca7632fcc353cea_Traceguids,
            (_BYTE)a1 + 112,
            17);
          goto LABEL_12;
        }
        v17 = v15 - 58;
        v15->Next = 0;
        if ( &v15[-58] == (struct _SLIST_ENTRY *)&v8[61 * v5 + 1] )
        {
          *a4 = v17;
          *((_DWORD *)&v17[57].Next + 2) = 0;
          v18 = *a4;
          v9 = 0;
          *((_BYTE *)&v18[60].Next + 10) = 1;
          goto LABEL_14;
        }
        ExpInterlockedPushEntrySList(&SListHead, v15);
      }
      v9 = -1073741275;
LABEL_12:
      ((void (__fastcall *)(_QWORD, _QWORD))v8[250298].Region)(*a1, 0);
    }
    else
    {
      v9 = -1073741436;
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v14, 20, 22, (__int64)WPP_73b674cdc296383cdca7632fcc353cea_Traceguids, 132);
    }
  }
  else
  {
    v8 = 0;
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v7,
      19,
      20,
      (__int64)WPP_73b674cdc296383cdca7632fcc353cea_Traceguids,
      (__int64)"!\"Index value too large.\"");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v9 = -1073741823;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_LLd(VmsIfrLog, v10, v11, 21, (__int64)WPP_73b674cdc296383cdca7632fcc353cea_Traceguids, 5, v5, 1);
  }
  WPP_RECORDER_SF_qLdd(
    VmsIfrLog,
    v12,
    v13,
    25,
    (__int64)WPP_73b674cdc296383cdca7632fcc353cea_Traceguids,
    (char)a1,
    1,
    v5,
    v9);
LABEL_14:
  while ( 1 )
  {
    v20 = ExpInterlockedPopEntrySList(&SListHead);
    if ( !v20 )
      break;
    ExpInterlockedPushEntrySList(v8 + 306, v20);
  }
  return v9;
}

```

## disassembly

```asm
0x1401a866c  mov     [rsp+arg_8], rbx
0x1401a8671  mov     [rsp+arg_10], rbp
0x1401a8676  push    rsi
0x1401a8677  push    rdi
0x1401a8678  push    r12
0x1401a867a  push    r14
0x1401a867c  push    r15
0x1401a867e  sub     rsp, 70h
0x1401a8682  mov     rax, cs:__security_cookie
0x1401a8689  xor     rax, rsp
0x1401a868c  mov     [rsp+98h+var_38], rax
0x1401a8691  mov     r14, rcx
0x1401a8694  mov     ebp, r8d
0x1401a8697  xorps   xmm0, xmm0
0x1401a869a  mov     qword ptr [r9], 0
0x1401a86a1  lea     rcx, [rsp+98h+SListHead]; SListHead
0x1401a86a6  mov     rbx, r9
0x1401a86a9  movups  xmmword ptr [rsp+98h+SListHead], xmm0
0x1401a86ae  call    cs:__imp_InitializeSListHead
0x1401a86b5  nop     dword ptr [rax+rax+00h]
0x1401a86ba  cmp     ebp, 5
0x1401a86bd  jb      short loc_1401A8723
0x1401a86bf  xor     edi, edi
0x1401a86c1  mov     rcx, cs:VmsIfrLog
0x1401a86c8  lea     rax, aIndexValueTooL; "!\"Index value too large.\""
0x1401a86cf  mov     [rsp+98h+var_70], rax
0x1401a86d4  lea     rsi, WPP_73b674cdc296383cdca7632fcc353cea_Traceguids
0x1401a86db  lea     r9d, [rdi+14h]
0x1401a86df  mov     [rsp+98h+var_78], rsi
0x1401a86e4  lea     r8d, [rdi+13h]
0x1401a86e8  call    WPP_RECORDER_SF_s
0x1401a86ed  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"Index value too large."")
0x1401a86f2  mov     ebx, 0C0000001h
0x1401a86f7  mov     rcx, cs:VmsIfrLog
0x1401a86fe  lea     r9d, [rdi+15h]
0x1401a8702  mov     [rsp+98h+var_60], ebx
0x1401a8706  mov     dl, 2
0x1401a8708  mov     [rsp+98h+var_68], ebp
0x1401a870c  mov     dword ptr [rsp+98h+var_70], 5
0x1401a8714  mov     [rsp+98h+var_78], rsi
0x1401a8719  call    WPP_RECORDER_SF_LLd
0x1401a871e  jmp     loc_1401A8861
0x1401a8723  mov     rcx, [r14]
0x1401a8726  lea     rdi, [r14-3D1BB0h]
0x1401a872d  mov     rax, [rdi+3D1BA0h]
0x1401a8734  xor     edx, edx
0x1401a8736  call    _guard_dispatch_icall
0x1401a873b  test    al, al
0x1401a873d  jnz     short loc_1401A8771
0x1401a873f  mov     ebx, 0C0000184h
0x1401a8744  mov     rcx, cs:VmsIfrLog
0x1401a874b  lea     rsi, WPP_73b674cdc296383cdca7632fcc353cea_Traceguids
0x1401a8752  mov     r9d, 16h
0x1401a8758  mov     dword ptr [rsp+98h+var_70], ebx
0x1401a875c  mov     dl, 2
0x1401a875e  mov     [rsp+98h+var_78], rsi
0x1401a8763  lea     r8d, [r9-2]
0x1401a8767  call    WPP_RECORDER_SF_d
0x1401a876c  jmp     loc_1401A8861
0x1401a8771  imul    r12, rbp, 3D0h
0x1401a8778  add     r12, 10h
0x1401a877c  add     r12, rdi
0x1401a877f  cmp     qword ptr [rbx], 0
0x1401a8783  lea     rsi, WPP_73b674cdc296383cdca7632fcc353cea_Traceguids
0x1401a878a  jnz     loc_1401A884B
0x1401a8790  lea     r15, [rdi+1320h]
0x1401a8797  mov     rcx, r15; ListHead
0x1401a879a  call    cs:__imp_ExpInterlockedPopEntrySList
0x1401a87a1  nop     dword ptr [rax+rax+00h]
0x1401a87a6  test    rax, rax
0x1401a87a9  jz      short loc_1401A87F2
0x1401a87ab  lea     rcx, [rax-3A0h]
0x1401a87b2  mov     qword ptr [rax], 0
0x1401a87b9  cmp     rcx, r12
0x1401a87bc  jz      short loc_1401A87D4
0x1401a87be  mov     rdx, rax; ListEntry
0x1401a87c1  lea     rcx, [rsp+98h+SListHead]; ListHead
0x1401a87c6  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401a87cd  nop     dword ptr [rax+rax+00h]
0x1401a87d2  jmp     short loc_1401A877F
0x1401a87d4  mov     [rbx], rcx
0x1401a87d7  mov     dword ptr [rcx+398h], 0
0x1401a87e1  mov     rax, [rbx]
0x1401a87e4  xor     ebx, ebx
0x1401a87e6  mov     byte ptr [rax+3CAh], 1
0x1401a87ed  jmp     loc_1401A888D
0x1401a87f2  mov     rcx, cs:VmsIfrLog
0x1401a87f9  lea     rax, aNullSlistentry; "!\"NULL slistEntry.\""
0x1401a8800  mov     r9d, 17h
0x1401a8806  mov     [rsp+98h+var_70], rax
0x1401a880b  mov     [rsp+98h+var_78], rsi
0x1401a8810  lea     r8d, [r9-4]
0x1401a8814  call    WPP_RECORDER_SF_s
0x1401a8819  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"NULL slistEntry."")
0x1401a881e  mov     ebx, 80000011h
0x1401a8823  mov     rcx, cs:VmsIfrLog
0x1401a882a  mov     r9d, 18h
0x1401a8830  mov     [rsp+98h+var_68], ebx
0x1401a8834  mov     dl, 2
0x1401a8836  mov     [rsp+98h+var_70], r15
0x1401a883b  mov     [rsp+98h+var_78], rsi
0x1401a8840  lea     r8d, [r9-4]
0x1401a8844  call    WPP_RECORDER_SF_id
0x1401a8849  jmp     short loc_1401A8850
0x1401a884b  mov     ebx, 0C0000225h
0x1401a8850  mov     rax, [rdi+3D1BA8h]
0x1401a8857  xor     edx, edx
0x1401a8859  mov     rcx, [r14]
0x1401a885c  call    _guard_dispatch_icall
0x1401a8861  mov     rcx, cs:VmsIfrLog
0x1401a8868  mov     r9d, 19h
0x1401a886e  mov     [rsp+98h+var_58], ebx
0x1401a8872  mov     [rsp+98h+var_60], ebp
0x1401a8876  mov     [rsp+98h+var_68], 1
0x1401a887e  mov     [rsp+98h+var_70], r14
0x1401a8883  mov     [rsp+98h+var_78], rsi
0x1401a8888  call    WPP_RECORDER_SF_qLdd
0x1401a888d  lea     rcx, [rsp+98h+SListHead]; ListHead
0x1401a8892  call    cs:__imp_ExpInterlockedPopEntrySList
0x1401a8899  nop     dword ptr [rax+rax+00h]
0x1401a889e  test    rax, rax
0x1401a88a1  jz      short loc_1401A88BB
0x1401a88a3  lea     rcx, [rdi+1320h]; ListHead
0x1401a88aa  mov     rdx, rax; ListEntry
0x1401a88ad  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401a88b4  nop     dword ptr [rax+rax+00h]
0x1401a88b9  jmp     short loc_1401A888D
0x1401a88bb  mov     eax, ebx
0x1401a88bd  mov     rcx, [rsp+98h+var_38]
0x1401a88c2  xor     rcx, rsp; StackCookie
0x1401a88c5  call    __security_check_cookie
0x1401a88ca  lea     r11, [rsp+98h+var_28]
0x1401a88cf  mov     rbx, [r11+38h]
0x1401a88d3  mov     rbp, [r11+40h]
0x1401a88d7  mov     rsp, r11
0x1401a88da  pop     r15
0x1401a88dc  pop     r14
0x1401a88de  pop     r12
0x1401a88e0  pop     rdi
0x1401a88e1  pop     rsi
0x1401a88e2  retn
```
