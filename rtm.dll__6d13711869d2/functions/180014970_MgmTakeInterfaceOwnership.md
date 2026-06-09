# MgmTakeInterfaceOwnership

- ea: `0x180014970`
- end: `0x180014bf4`
- name: `MgmTakeInterfaceOwnership`
- size: `644`
- prototype: `DWORD __stdcall(HANDLE hProtocol, DWORD dwIfIndex, DWORD dwIfNextHopAddr)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180014970`
- `0x180014bfc`
- `0x180014d2c`
- `0x180014f98`
- `0x180015040`
- `0x180015100`
- `0x180015178`
- `0x18001b588`
- `0x18001b840`
- `0x18001bc4c`
- `0x18001be6c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x180014b38`
- `rtutils!RouterLogEventA` at `0x180014b38`

## string_xrefs

- `0x180014acc`: `MgmTakeInterfaceOwnership : Already owned by routing protocol : %d, %d`

## pseudocode

```c
DWORD __stdcall MgmTakeInterfaceOwnership(HANDLE hProtocol, DWORD dwIfIndex, DWORD dwIfNextHopAddr)
{
  unsigned __int64 v7; // rdi
  DWORD v8; // ebx
  __int64 v9; // r15
  int v10; // r12d
  int v11; // r8d
  DWORD IfEntry; // eax
  int v13; // ecx
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v14 = 0;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
  {
    LOWORD(v15) = 0;
    FormatRRASErrorString(&v15, L"ENTERED MgmTakeInterfaceOwnership : Interface %x, %x", dwIfIndex, dwIfNextHopAddr);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v15);
  }
  AcquireReadLock(&qword_18002B9B8);
  v7 = (unsigned __int64)hProtocol ^ 0x474D6300;
  v8 = VerifyProtocolHandle(v7);
  if ( !v8 )
  {
    v9 = 32LL * (dwIfIndex % dword_18002B92C);
    AcquireWriteLock((char *)qword_18002B9E8 + v9 + 16);
    v10 = v9 + (_DWORD)qword_18002B9E8;
    if ( (unsigned int)FindIfEntry((char *)qword_18002B9E8 + v9, dwIfIndex, dwIfNextHopAddr, &v14) )
    {
      if ( *(_DWORD *)(v7 + 16) == 10 )
      {
        *(_WORD *)(v14 + 32) |= 0x8000u;
        goto LABEL_20;
      }
      if ( *(_DWORD *)(v14 + 24) != 10 )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v15) = 0;
          FormatRRASErrorString(
            &v15,
            L"MgmTakeInterfaceOwnership : Already owned by routing protocol : %d, %d",
            *(unsigned int *)(v14 + 24),
            *(unsigned int *)(v14 + 28));
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v15);
        }
        v8 = 183;
        if ( (unsigned int)dword_18002BA54 < 2 )
          goto LABEL_21;
        RouterLogEventA(qword_18002BA58, 2u, 0xC35Eu, 0, 0, 0xB7u);
LABEL_19:
        if ( v8 )
        {
LABEL_21:
          ReleaseWriteLock((char *)qword_18002B9E8 + v9 + 16);
          goto LABEL_22;
        }
LABEL_20:
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 24));
        goto LABEL_21;
      }
      IfEntry = TransferInterfaceOwnershipToProtocol(v7, v14);
    }
    else
    {
      v13 = v14;
      if ( !v14 )
        v13 = v10;
      IfEntry = CreateIfEntry(v13, dwIfIndex, v11, *(_DWORD *)(v7 + 16), *(_DWORD *)(v7 + 20));
    }
    v8 = IfEntry;
    goto LABEL_19;
  }
LABEL_22:
  ReleaseReadLock(&qword_18002B9B8);
  if ( qword_18002B8A8 )
  {
    LOWORD(v15) = 0;
    FormatRRASErrorString(&v15, L"LEAVING MgmTakeInterfaceOwnership %x\n", v8);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v15);
  }
  LeaveMgmWorker();
  return v8;
}

```

## disassembly

```asm
0x180014970  push    rbp
0x180014972  push    rbx
0x180014973  push    rsi
0x180014974  push    rdi
0x180014975  push    r12
0x180014977  push    r14
0x180014979  push    r15
0x18001497b  lea     rbp, [rsp-750h]
0x180014983  sub     rsp, 850h
0x18001498a  mov     rax, cs:__security_cookie
0x180014991  xor     rax, rsp
0x180014994  mov     [rbp+780h+var_40], rax
0x18001499b  mov     r14d, r8d
0x18001499e  mov     [rsp+880h+var_850], 0
0x1800149a7  mov     esi, edx
0x1800149a9  mov     rdi, rcx
0x1800149ac  xor     eax, eax
0x1800149ae  lea     rcx, [rsp+880h+var_83C]; void *
0x1800149b3  xor     edx, edx; Val
0x1800149b5  mov     [rsp+880h+var_840], eax
0x1800149b9  mov     r8d, 7FCh; Size
0x1800149bf  call    memset_0
0x1800149c4  call    EnterMgmAPI
0x1800149c9  test    eax, eax
0x1800149cb  jnz     short loc_1800149D7
0x1800149cd  mov     eax, 3EBh
0x1800149d2  jmp     loc_180014BD3
0x1800149d7  cmp     cs:qword_18002B8A8, 0
0x1800149df  jz      short loc_180014A1E
0x1800149e1  xor     eax, eax
0x1800149e3  lea     rdx, aEnteredMgmtake; "ENTERED MgmTakeInterfaceOwnership : Int"...
0x1800149ea  mov     r9d, r14d
0x1800149ed  mov     word ptr [rsp+880h+var_840], ax
0x1800149f2  mov     r8d, esi
0x1800149f5  lea     rcx, [rsp+880h+var_840]
0x1800149fa  call    FormatRRASErrorString
0x1800149ff  mov     rdx, cs:qword_18002B8A8
0x180014a06  lea     r8, [rsp+880h+var_840]
0x180014a0b  mov     rcx, cs:gMgmEtwContext
0x180014a12  mov     rax, cs:gMgmTemplateFunc
0x180014a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a1e  lea     rcx, qword_18002B9B8
0x180014a25  call    AcquireReadLock
0x180014a2a  xor     rdi, 474D6300h
0x180014a31  mov     rcx, rdi
0x180014a34  call    VerifyProtocolHandle
0x180014a39  mov     ebx, eax
0x180014a3b  test    eax, eax
0x180014a3d  jnz     loc_180014B7C
0x180014a43  mov     rcx, cs:qword_18002B9E8
0x180014a4a  xor     edx, edx
0x180014a4c  mov     eax, esi
0x180014a4e  add     rcx, 10h
0x180014a52  div     cs:dword_18002B92C
0x180014a58  mov     r15d, edx
0x180014a5b  shl     r15, 5
0x180014a5f  add     rcx, r15
0x180014a62  call    AcquireWriteLock
0x180014a67  mov     r12, cs:qword_18002B9E8
0x180014a6e  lea     r9, [rsp+880h+var_850]
0x180014a73  add     r12, r15
0x180014a76  mov     r8d, r14d
0x180014a79  mov     rcx, r12
0x180014a7c  mov     edx, esi
0x180014a7e  call    FindIfEntry
0x180014a83  test    eax, eax
0x180014a85  jz      loc_180014B40
0x180014a8b  cmp     dword ptr [rdi+10h], 0Ah
0x180014a8f  jnz     short loc_180014AA4
0x180014a91  mov     rax, [rsp+880h+var_850]
0x180014a96  mov     ecx, 8000h
0x180014a9b  or      [rax+20h], cx
0x180014a9f  jmp     loc_180014B65
0x180014aa4  mov     r8, [rsp+880h+var_850]
0x180014aa9  cmp     dword ptr [r8+18h], 0Ah
0x180014aae  jnz     short loc_180014AC0
0x180014ab0  mov     rdx, r8
0x180014ab3  mov     rcx, rdi
0x180014ab6  call    TransferInterfaceOwnershipToProtocol
0x180014abb  jmp     loc_180014B5F
0x180014ac0  cmp     cs:qword_18002B8A8, 0
0x180014ac8  jz      short loc_180014B09
0x180014aca  xor     eax, eax
0x180014acc  lea     rdx, aMgmtakeinterfa_0; "MgmTakeInterfaceOwnership : Already own"...
0x180014ad3  mov     word ptr [rsp+880h+var_840], ax
0x180014ad8  lea     rcx, [rsp+880h+var_840]
0x180014add  mov     r9d, [r8+1Ch]
0x180014ae1  mov     r8d, [r8+18h]
0x180014ae5  call    FormatRRASErrorString
0x180014aea  mov     rdx, cs:qword_18002B8A8
0x180014af1  lea     r8, [rsp+880h+var_840]
0x180014af6  mov     rcx, cs:gMgmEtwContext
0x180014afd  mov     rax, cs:gMgmTemplateFunc
0x180014b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b09  mov     edx, 2; dwEventType
0x180014b0e  mov     ebx, 0B7h
0x180014b13  cmp     cs:dword_18002BA54, edx
0x180014b19  jb      short loc_180014B69
0x180014b1b  mov     rcx, cs:qword_18002BA58; hLogHandle
0x180014b22  xor     r9d, r9d; dwSubStringCount
0x180014b25  mov     [rsp+880h+dwErrorCode], ebx; dwErrorCode
0x180014b29  mov     r8d, 0C35Eh; dwMessageId
0x180014b2f  mov     [rsp+880h+plpszSubStringArray], 0; plpszSubStringArray
0x180014b38  call    cs:__imp_RouterLogEventA
0x180014b3e  jmp     short loc_180014B61
0x180014b40  mov     rcx, [rsp+880h+var_850]
0x180014b45  mov     edx, esi
0x180014b47  mov     eax, [rdi+14h]
0x180014b4a  mov     r9d, [rdi+10h]
0x180014b4e  mov     dword ptr [rsp+880h+plpszSubStringArray], eax
0x180014b52  test    rcx, rcx
0x180014b55  jnz     short loc_180014B5A
0x180014b57  mov     rcx, r12
0x180014b5a  call    CreateIfEntry
0x180014b5f  mov     ebx, eax
0x180014b61  test    ebx, ebx
0x180014b63  jnz     short loc_180014B69
0x180014b65  lock inc dword ptr [rdi+18h]
0x180014b69  mov     rcx, cs:qword_18002B9E8
0x180014b70  add     rcx, 10h
0x180014b74  add     rcx, r15
0x180014b77  call    ReleaseWriteLock
0x180014b7c  lea     rcx, qword_18002B9B8
0x180014b83  call    ReleaseReadLock
0x180014b88  cmp     cs:qword_18002B8A8, 0
0x180014b90  jz      short loc_180014BCC
0x180014b92  xor     eax, eax
0x180014b94  lea     rdx, aLeavingMgmtake; "LEAVING MgmTakeInterfaceOwnership %x\n"
0x180014b9b  mov     r8d, ebx
0x180014b9e  mov     word ptr [rsp+880h+var_840], ax
0x180014ba3  lea     rcx, [rsp+880h+var_840]
0x180014ba8  call    FormatRRASErrorString
0x180014bad  mov     rdx, cs:qword_18002B8A8
0x180014bb4  lea     r8, [rsp+880h+var_840]
0x180014bb9  mov     rcx, cs:gMgmEtwContext
0x180014bc0  mov     rax, cs:gMgmTemplateFunc
0x180014bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bcc  call    LeaveMgmWorker
0x180014bd1  mov     eax, ebx
0x180014bd3  mov     rcx, [rbp+780h+var_40]
0x180014bda  xor     rcx, rsp; StackCookie
0x180014bdd  call    __security_check_cookie
0x180014be2  add     rsp, 850h
0x180014be9  pop     r15
0x180014beb  pop     r14
0x180014bed  pop     r12
0x180014bef  pop     rdi
0x180014bf0  pop     rsi
0x180014bf1  pop     rbx
0x180014bf2  pop     rbp
0x180014bf3  retn
```
