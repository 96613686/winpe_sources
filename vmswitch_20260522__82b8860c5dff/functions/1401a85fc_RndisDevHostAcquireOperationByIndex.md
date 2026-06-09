# RndisDevHostAcquireOperationByIndex

- ea: `0x1401a85fc`
- end: `0x1401a8874`
- name: `RndisDevHostAcquireOperationByIndex`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401ab1cc`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x140046f1c`
- `0x14007a890`
- `0x14008497c`
- `0x1400a0ef8`
- `0x1401a85fc`
- `0x1401bbc40`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401a872a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401a8822`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401a872a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401a8822`
- `ntoskrnl!InitializeSListHead` at `0x1401a863e`
- `ntoskrnl!InitializeSListHead` at `0x1401a863e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401a8756`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401a883d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401a8756`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401a883d`

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
0x1401a85fc  mov     [rsp+arg_8], rbx
0x1401a8601  mov     [rsp+arg_10], rbp
0x1401a8606  push    rsi
0x1401a8607  push    rdi
0x1401a8608  push    r12
0x1401a860a  push    r14
0x1401a860c  push    r15
0x1401a860e  sub     rsp, 70h
0x1401a8612  mov     rax, cs:__security_cookie
0x1401a8619  xor     rax, rsp
0x1401a861c  mov     [rsp+98h+var_38], rax
0x1401a8621  mov     r14, rcx
0x1401a8624  mov     ebp, r8d
0x1401a8627  xorps   xmm0, xmm0
0x1401a862a  mov     qword ptr [r9], 0
0x1401a8631  lea     rcx, [rsp+98h+SListHead]; SListHead
0x1401a8636  mov     rbx, r9
0x1401a8639  movups  xmmword ptr [rsp+98h+SListHead], xmm0
0x1401a863e  call    cs:__imp_InitializeSListHead
0x1401a8645  nop     dword ptr [rax+rax+00h]
0x1401a864a  cmp     ebp, 5
0x1401a864d  jb      short loc_1401A86B3
0x1401a864f  xor     edi, edi
0x1401a8651  mov     rcx, cs:VmsIfrLog
0x1401a8658  lea     rax, aIndexValueTooL; "!\"Index value too large.\""
0x1401a865f  mov     [rsp+98h+var_70], rax
0x1401a8664  lea     rsi, WPP_73b674cdc296383cdca7632fcc353cea_Traceguids
0x1401a866b  lea     r9d, [rdi+14h]
0x1401a866f  mov     [rsp+98h+var_78], rsi
0x1401a8674  lea     r8d, [rdi+13h]
0x1401a8678  call    WPP_RECORDER_SF_s
0x1401a867d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"Index value too large."")
0x1401a8682  mov     ebx, 0C0000001h
0x1401a8687  mov     rcx, cs:VmsIfrLog
0x1401a868e  lea     r9d, [rdi+15h]
0x1401a8692  mov     [rsp+98h+var_60], ebx
0x1401a8696  mov     dl, 2
0x1401a8698  mov     [rsp+98h+var_68], ebp
0x1401a869c  mov     dword ptr [rsp+98h+var_70], 5
0x1401a86a4  mov     [rsp+98h+var_78], rsi
0x1401a86a9  call    WPP_RECORDER_SF_LLd
0x1401a86ae  jmp     loc_1401A87F1
0x1401a86b3  mov     rcx, [r14]
0x1401a86b6  lea     rdi, [r14-3D1BB0h]
0x1401a86bd  mov     rax, [rdi+3D1BA0h]
0x1401a86c4  xor     edx, edx
0x1401a86c6  call    _guard_dispatch_icall
0x1401a86cb  test    al, al
0x1401a86cd  jnz     short loc_1401A8701
0x1401a86cf  mov     ebx, 0C0000184h
0x1401a86d4  mov     rcx, cs:VmsIfrLog
0x1401a86db  lea     rsi, WPP_73b674cdc296383cdca7632fcc353cea_Traceguids
0x1401a86e2  mov     r9d, 16h
0x1401a86e8  mov     dword ptr [rsp+98h+var_70], ebx
0x1401a86ec  mov     dl, 2
0x1401a86ee  mov     [rsp+98h+var_78], rsi
0x1401a86f3  lea     r8d, [r9-2]
0x1401a86f7  call    WPP_RECORDER_SF_d
0x1401a86fc  jmp     loc_1401A87F1
0x1401a8701  imul    r12, rbp, 3D0h
0x1401a8708  add     r12, 10h
0x1401a870c  add     r12, rdi
0x1401a870f  cmp     qword ptr [rbx], 0
0x1401a8713  lea     rsi, WPP_73b674cdc296383cdca7632fcc353cea_Traceguids
0x1401a871a  jnz     loc_1401A87DB
0x1401a8720  lea     r15, [rdi+1320h]
0x1401a8727  mov     rcx, r15; ListHead
0x1401a872a  call    cs:__imp_ExpInterlockedPopEntrySList
0x1401a8731  nop     dword ptr [rax+rax+00h]
0x1401a8736  test    rax, rax
0x1401a8739  jz      short loc_1401A8782
0x1401a873b  lea     rcx, [rax-3A0h]
0x1401a8742  mov     qword ptr [rax], 0
0x1401a8749  cmp     rcx, r12
0x1401a874c  jz      short loc_1401A8764
0x1401a874e  mov     rdx, rax; ListEntry
0x1401a8751  lea     rcx, [rsp+98h+SListHead]; ListHead
0x1401a8756  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401a875d  nop     dword ptr [rax+rax+00h]
0x1401a8762  jmp     short loc_1401A870F
0x1401a8764  mov     [rbx], rcx
0x1401a8767  mov     dword ptr [rcx+398h], 0
0x1401a8771  mov     rax, [rbx]
0x1401a8774  xor     ebx, ebx
0x1401a8776  mov     byte ptr [rax+3CAh], 1
0x1401a877d  jmp     loc_1401A881D
0x1401a8782  mov     rcx, cs:VmsIfrLog
0x1401a8789  lea     rax, aNullSlistentry; "!\"NULL slistEntry.\""
0x1401a8790  mov     r9d, 17h
0x1401a8796  mov     [rsp+98h+var_70], rax
0x1401a879b  mov     [rsp+98h+var_78], rsi
0x1401a87a0  lea     r8d, [r9-4]
0x1401a87a4  call    WPP_RECORDER_SF_s
0x1401a87a9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"NULL slistEntry."")
0x1401a87ae  mov     ebx, 80000011h
0x1401a87b3  mov     rcx, cs:VmsIfrLog
0x1401a87ba  mov     r9d, 18h
0x1401a87c0  mov     [rsp+98h+var_68], ebx
0x1401a87c4  mov     dl, 2
0x1401a87c6  mov     [rsp+98h+var_70], r15
0x1401a87cb  mov     [rsp+98h+var_78], rsi
0x1401a87d0  lea     r8d, [r9-4]
0x1401a87d4  call    WPP_RECORDER_SF_id
0x1401a87d9  jmp     short loc_1401A87E0
0x1401a87db  mov     ebx, 0C0000225h
0x1401a87e0  mov     rax, [rdi+3D1BA8h]
0x1401a87e7  xor     edx, edx
0x1401a87e9  mov     rcx, [r14]
0x1401a87ec  call    _guard_dispatch_icall
0x1401a87f1  mov     rcx, cs:VmsIfrLog
0x1401a87f8  mov     r9d, 19h
0x1401a87fe  mov     [rsp+98h+var_58], ebx
0x1401a8802  mov     [rsp+98h+var_60], ebp
0x1401a8806  mov     [rsp+98h+var_68], 1
0x1401a880e  mov     [rsp+98h+var_70], r14
0x1401a8813  mov     [rsp+98h+var_78], rsi
0x1401a8818  call    WPP_RECORDER_SF_qLdd
0x1401a881d  lea     rcx, [rsp+98h+SListHead]; ListHead
0x1401a8822  call    cs:__imp_ExpInterlockedPopEntrySList
0x1401a8829  nop     dword ptr [rax+rax+00h]
0x1401a882e  test    rax, rax
0x1401a8831  jz      short loc_1401A884B
0x1401a8833  lea     rcx, [rdi+1320h]; ListHead
0x1401a883a  mov     rdx, rax; ListEntry
0x1401a883d  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401a8844  nop     dword ptr [rax+rax+00h]
0x1401a8849  jmp     short loc_1401A881D
0x1401a884b  mov     eax, ebx
0x1401a884d  mov     rcx, [rsp+98h+var_38]
0x1401a8852  xor     rcx, rsp; StackCookie
0x1401a8855  call    __security_check_cookie
0x1401a885a  lea     r11, [rsp+98h+var_28]
0x1401a885f  mov     rbx, [r11+38h]
0x1401a8863  mov     rbp, [r11+40h]
0x1401a8867  mov     rsp, r11
0x1401a886a  pop     r15
0x1401a886c  pop     r14
0x1401a886e  pop     r12
0x1401a8870  pop     rdi
0x1401a8871  pop     rsi
0x1401a8872  retn
```
