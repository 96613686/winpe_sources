# MgmReleaseInterfaceOwnership

- ea: `0x180014580`
- end: `0x180014969`
- name: `MgmReleaseInterfaceOwnership`
- size: `1001`
- prototype: `DWORD __stdcall(HANDLE hProtocol, DWORD dwIfIndex, DWORD dwIfNextHopAddr)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180014580`
- `0x180014bfc`
- `0x180014d2c`
- `0x180014f98`
- `0x180015040`
- `0x180015100`
- `0x180015178`
- `0x18001958c`
- `0x18001b548`
- `0x18001b588`
- `0x18001b9ac`
- `0x18001ba30`
- `0x18001bc4c`
- `0x18001bce0`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800147f0`
- `KERNEL32!HeapFree` at `0x1800147f0`
- `rtutils!RouterLogEventA` at `0x1800148c3`
- `rtutils!RouterLogEventA` at `0x1800148c3`

## pseudocode

```c
DWORD __stdcall MgmReleaseInterfaceOwnership(HANDLE hProtocol, DWORD dwIfIndex, DWORD dwIfNextHopAddr)
{
  unsigned int *plpszSubStringArray; // rbx
  unsigned __int64 v8; // r12
  unsigned __int64 ProtocolEntry; // rsi
  DWORD v10; // edi
  __int64 v11; // r13
  int v12; // ecx
  __int16 v13; // ax
  unsigned int v14; // r15d
  __int16 v15; // ax
  _QWORD *v16; // r14
  char *v17; // rcx
  LPSTR v18; // rax
  LPSTR *v19; // rcx
  LPVOID lpMem[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  char v22[2044]; // [rsp+44h] [rbp-BCh] BYREF

  plpszSubStringArray = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
  {
    LOWORD(v21) = 0;
    FormatRRASErrorString(&v21, L"ENTERED MgmReleaseInterfaceOwnership : Interface %x, %x", dwIfIndex, dwIfNextHopAddr);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v21);
  }
  v8 = 0;
  AcquireReadLock(&qword_18002B9B8);
  ProtocolEntry = (unsigned __int64)hProtocol ^ 0x474D6300;
  v10 = VerifyProtocolHandle(ProtocolEntry);
  if ( !v10 )
  {
    v11 = 32LL * (dwIfIndex % dword_18002B92C);
    AcquireWriteLock((char *)qword_18002B9E8 + v11 + 16);
    lpMem[0] = 0;
    if ( !(unsigned int)FindIfEntry((char *)qword_18002B9E8 + v11, dwIfIndex, dwIfNextHopAddr, lpMem)
      || (plpszSubStringArray = (unsigned int *)lpMem[0]) == 0 )
    {
      if ( (unsigned int *)qword_18002B8A8 != plpszSubStringArray )
      {
        LOWORD(v21) = (_WORD)plpszSubStringArray;
        FormatRRASErrorString(&v21, L"Interface entry %d, %x not found ", dwIfIndex, dwIfNextHopAddr);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v21);
      }
      goto LABEL_39;
    }
    v12 = *(_DWORD *)(ProtocolEntry + 16);
    if ( v12 == 10 )
    {
      if ( *((__int16 *)lpMem[0] + 16) >= 0 )
      {
        if ( !qword_18002B8A8 )
        {
LABEL_13:
          plpszSubStringArray = 0;
LABEL_39:
          v10 = 87;
          if ( (unsigned int)dword_18002BA54 >= 2 )
            RouterLogEventA(qword_18002BA58, 2u, 0xC35Fu, 0, (LPSTR *)plpszSubStringArray, 0x57u);
          goto LABEL_41;
        }
        LOWORD(v21) = 0;
        FormatRRASErrorString(
          &v21,
          L"IGMP not running on interface %x, %x",
          *((unsigned int *)lpMem[0] + 4),
          *((unsigned int *)lpMem[0] + 5));
LABEL_12:
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v21);
        goto LABEL_13;
      }
    }
    else if ( v12 != *((_DWORD *)lpMem[0] + 6) || *(_DWORD *)(ProtocolEntry + 20) != *((_DWORD *)lpMem[0] + 7) )
    {
      if ( !qword_18002B8A8 )
        goto LABEL_13;
      LOWORD(v21) = 0;
      FormatRRASErrorString(
        &v21,
        L"Routing protcol not running on interface %x, %x",
        *((unsigned int *)lpMem[0] + 4),
        *((unsigned int *)lpMem[0] + 5));
      goto LABEL_12;
    }
    v13 = *((_WORD *)lpMem[0] + 16);
    v8 = ProtocolEntry;
    if ( v12 == 10 )
    {
      v14 = 1;
      v15 = v13 & 0x7FFF;
      *((_WORD *)lpMem[0] + 16) = v15;
      if ( (v15 & 0x4000) != 0 )
        ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, plpszSubStringArray[6], plpszSubStringArray[7]);
      else
        DeleteInInterfaceRefs(plpszSubStringArray + 14);
      v16 = plpszSubStringArray + 14;
    }
    else
    {
      if ( v13 < 0 )
      {
        v10 = TransferInterfaceOwnershipToIGMP(ProtocolEntry, (__int64)lpMem[0]);
LABEL_23:
        plpszSubStringArray = 0;
LABEL_41:
        ReleaseWriteLock((__int64)qword_18002B9E8 + v11 + 16);
        goto LABEL_42;
      }
      v16 = (char *)lpMem[0] + 56;
      v14 = 0;
      v17 = (char *)lpMem[0] + 56;
      *((_WORD *)lpMem[0] + 16) = v13 & 0xBFFF;
      DeleteInInterfaceRefs(v17);
    }
    DeleteOutInterfaceRefs(ProtocolEntry, plpszSubStringArray, v14);
    if ( *((__int16 *)plpszSubStringArray + 16) >= 0 && (plpszSubStringArray[8] & 0x4000) == 0 )
    {
      if ( *((unsigned int **)plpszSubStringArray + 5) != plpszSubStringArray + 10 || (_QWORD *)*v16 != v16 )
      {
        plpszSubStringArray = 0;
        v10 = 1003;
        if ( qword_18002B8A8 )
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
            gMgmEtwContext,
            qword_18002B8A8,
            L"References remain for interface");
        goto LABEL_41;
      }
      v18 = *(LPSTR *)plpszSubStringArray;
      if ( *(unsigned int **)(*(_QWORD *)plpszSubStringArray + 8LL) != plpszSubStringArray
        || (v19 = (LPSTR *)*((_QWORD *)plpszSubStringArray + 1), *v19 != (LPSTR)plpszSubStringArray) )
      {
        __fastfail(3u);
      }
      *v19 = v18;
      *((_QWORD *)v18 + 1) = v19;
      HeapFree(hHeap, 0, plpszSubStringArray);
    }
    goto LABEL_23;
  }
LABEL_42:
  InvokeOutstandingCallbacks();
  if ( !v10 )
    _InterlockedDecrement((volatile signed __int32 *)(v8 + 24));
  ReleaseReadLock((__int64)&qword_18002B9B8);
  if ( (unsigned int *)qword_18002B8A8 != plpszSubStringArray )
  {
    LOWORD(v21) = (_WORD)plpszSubStringArray;
    FormatRRASErrorString(&v21, L"LEAVING MgmReleaseInterfaceOwnership %x\n", v10);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v21);
  }
  LeaveMgmWorker();
  return v10;
}

```

## disassembly

```asm
0x180014580  mov     [rsp-8+arg_18], rbx
0x180014585  push    rbp
0x180014586  push    rsi
0x180014587  push    rdi
0x180014588  push    r12
0x18001458a  push    r13
0x18001458c  push    r14
0x18001458e  push    r15
0x180014590  lea     rbp, [rsp-750h]
0x180014598  sub     rsp, 850h
0x18001459f  mov     rax, cs:__security_cookie
0x1800145a6  xor     rax, rsp
0x1800145a9  mov     [rbp+780h+var_40], rax
0x1800145b0  mov     r15d, r8d
0x1800145b3  mov     r14d, edx
0x1800145b6  mov     rsi, rcx
0x1800145b9  xor     ebx, ebx
0x1800145bb  xor     edx, edx; Val
0x1800145bd  mov     [rsp+880h+var_840], ebx
0x1800145c1  mov     r8d, 7FCh; Size
0x1800145c7  lea     rcx, [rsp+880h+var_83C]; void *
0x1800145cc  call    memset_0
0x1800145d1  call    EnterMgmAPI
0x1800145d6  test    eax, eax
0x1800145d8  jnz     short loc_1800145E4
0x1800145da  mov     eax, 3EBh
0x1800145df  jmp     loc_18001493F
0x1800145e4  cmp     cs:qword_18002B8A8, rbx
0x1800145eb  jz      short loc_180014628
0x1800145ed  mov     r9d, r15d
0x1800145f0  mov     word ptr [rsp+880h+var_840], bx
0x1800145f5  mov     r8d, r14d
0x1800145f8  lea     rdx, aEnteredMgmrele; "ENTERED MgmReleaseInterfaceOwnership : "...
0x1800145ff  lea     rcx, [rsp+880h+var_840]
0x180014604  call    FormatRRASErrorString
0x180014609  mov     rdx, cs:qword_18002B8A8
0x180014610  lea     r8, [rsp+880h+var_840]
0x180014615  mov     rcx, cs:gMgmEtwContext
0x18001461c  mov     rax, cs:gMgmTemplateFunc
0x180014623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014628  lea     rcx, qword_18002B9B8
0x18001462f  mov     r12, rbx
0x180014632  call    AcquireReadLock
0x180014637  xor     rsi, 474D6300h
0x18001463e  mov     rcx, rsi
0x180014641  call    VerifyProtocolHandle
0x180014646  mov     edi, eax
0x180014648  test    eax, eax
0x18001464a  jnz     loc_1800148DC
0x180014650  mov     rcx, cs:qword_18002B9E8
0x180014657  xor     edx, edx
0x180014659  mov     eax, r14d
0x18001465c  add     rcx, 10h
0x180014660  div     cs:dword_18002B92C
0x180014666  mov     r13d, edx
0x180014669  shl     r13, 5
0x18001466d  add     rcx, r13
0x180014670  call    AcquireWriteLock
0x180014675  mov     rcx, cs:qword_18002B9E8
0x18001467c  lea     r9, [rsp+880h+lpMem]
0x180014681  add     rcx, r13
0x180014684  mov     [rsp+880h+lpMem], rbx
0x180014689  mov     r8d, r15d
0x18001468c  mov     edx, r14d
0x18001468f  call    FindIfEntry
0x180014694  test    eax, eax
0x180014696  jz      loc_180014853
0x18001469c  mov     rbx, [rsp+880h+lpMem]
0x1800146a1  xor     edx, edx
0x1800146a3  test    rbx, rbx
0x1800146a6  jz      loc_180014853
0x1800146ac  mov     ecx, [rsi+10h]
0x1800146af  cmp     ecx, 0Ah
0x1800146b2  jnz     short loc_180014707
0x1800146b4  cmp     [rbx+20h], dx
0x1800146b8  jl      short loc_18001471C
0x1800146ba  cmp     cs:qword_18002B8A8, rdx
0x1800146c1  jz      short loc_180014700
0x1800146c3  mov     word ptr [rsp+880h+var_840], dx
0x1800146c8  lea     rdx, aIgmpNotRunning; "IGMP not running on interface %x, %x"
0x1800146cf  mov     r8d, [rbx+10h]
0x1800146d3  lea     rcx, [rsp+880h+var_840]
0x1800146d8  mov     r9d, [rbx+14h]
0x1800146dc  call    FormatRRASErrorString
0x1800146e1  mov     rdx, cs:qword_18002B8A8
0x1800146e8  lea     r8, [rsp+880h+var_840]
0x1800146ed  mov     rcx, cs:gMgmEtwContext
0x1800146f4  mov     rax, cs:gMgmTemplateFunc
0x1800146fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014700  xor     ebx, ebx
0x180014702  jmp     loc_180014897
0x180014707  cmp     ecx, [rbx+18h]
0x18001470a  jnz     loc_180014835
0x180014710  mov     eax, [rbx+1Ch]
0x180014713  cmp     [rsi+14h], eax
0x180014716  jnz     loc_180014835
0x18001471c  movzx   eax, word ptr [rbx+20h]
0x180014720  mov     r12, rsi
0x180014723  cmp     ecx, 0Ah
0x180014726  jnz     short loc_180014768
0x180014728  mov     ecx, 7FFFh
0x18001472d  mov     r15d, 1
0x180014733  and     ax, cx
0x180014736  bt      ax, 0Eh
0x18001473b  mov     [rbx+20h], ax
0x18001473f  jb      short loc_18001474C
0x180014741  lea     rcx, [rbx+38h]
0x180014745  call    DeleteInInterfaceRefs
0x18001474a  jmp     short loc_180014762
0x18001474c  mov     r8d, [rbx+1Ch]
0x180014750  lea     rcx, qword_18002B9A8
0x180014757  mov     edx, [rbx+18h]
0x18001475a  call    GetProtocolEntry
0x18001475f  mov     rsi, rax
0x180014762  lea     r14, [rbx+38h]
0x180014766  jmp     short loc_18001479C
0x180014768  test    ax, ax
0x18001476b  jns     short loc_180014781
0x18001476d  mov     rdx, rbx
0x180014770  mov     rcx, rsi
0x180014773  call    TransferInterfaceOwnershipToIGMP
0x180014778  mov     edi, eax
0x18001477a  xor     ebx, ebx
0x18001477c  jmp     loc_1800148C9
0x180014781  mov     ecx, 0BFFFh
0x180014786  lea     r14, [rbx+38h]
0x18001478a  and     ax, cx
0x18001478d  mov     r15d, edx
0x180014790  mov     rcx, r14
0x180014793  mov     [rbx+20h], ax
0x180014797  call    DeleteInInterfaceRefs
0x18001479c  mov     r8d, r15d
0x18001479f  mov     rdx, rbx
0x1800147a2  mov     rcx, rsi
0x1800147a5  call    DeleteOutInterfaceRefs
0x1800147aa  xor     eax, eax
0x1800147ac  cmp     [rbx+20h], ax
0x1800147b0  jl      short loc_18001477A
0x1800147b2  mov     eax, 4000h
0x1800147b7  test    [rbx+20h], ax
0x1800147bb  jnz     short loc_18001477A
0x1800147bd  lea     rax, [rbx+28h]
0x1800147c1  cmp     [rax], rax
0x1800147c4  jnz     short loc_1800147FF
0x1800147c6  cmp     [r14], r14
0x1800147c9  jnz     short loc_1800147FF
0x1800147cb  mov     rax, [rbx]
0x1800147ce  cmp     [rax+8], rbx
0x1800147d2  jnz     short loc_1800147F8
0x1800147d4  mov     rcx, [rbx+8]
0x1800147d8  cmp     [rcx], rbx
0x1800147db  jnz     short loc_1800147F8
0x1800147dd  mov     [rcx], rax
0x1800147e0  mov     r8, rbx; lpMem
0x1800147e3  mov     [rax+8], rcx
0x1800147e7  xor     edx, edx; dwFlags
0x1800147e9  mov     rcx, cs:hHeap; hHeap
0x1800147f0  call    cs:__imp_HeapFree
0x1800147f6  jmp     short loc_18001477A
0x1800147f8  mov     ecx, 3
0x1800147fd  int     29h; Win8: RtlFailFast(ecx)
0x1800147ff  mov     rdx, cs:qword_18002B8A8
0x180014806  xor     ebx, ebx
0x180014808  mov     edi, 3EBh
0x18001480d  test    rdx, rdx
0x180014810  jz      loc_1800148C9
0x180014816  mov     rcx, cs:gMgmEtwContext
0x18001481d  lea     r8, aReferencesRema; "References remain for interface"
0x180014824  mov     rax, cs:gMgmTemplateFunc
0x18001482b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014830  jmp     loc_1800148C9
0x180014835  cmp     cs:qword_18002B8A8, rdx
0x18001483c  jz      loc_180014700
0x180014842  mov     word ptr [rsp+880h+var_840], dx
0x180014847  lea     rdx, aRoutingProtcol; "Routing protcol not running on interfac"...
0x18001484e  jmp     loc_1800146CF
0x180014853  cmp     cs:qword_18002B8A8, rbx
0x18001485a  jz      short loc_180014897
0x18001485c  mov     r9d, r15d
0x18001485f  mov     word ptr [rsp+880h+var_840], bx
0x180014864  mov     r8d, r14d
0x180014867  lea     rdx, aInterfaceEntry; "Interface entry %d, %x not found "
0x18001486e  lea     rcx, [rsp+880h+var_840]
0x180014873  call    FormatRRASErrorString
0x180014878  mov     rdx, cs:qword_18002B8A8
0x18001487f  lea     r8, [rsp+880h+var_840]
0x180014884  mov     rcx, cs:gMgmEtwContext
0x18001488b  mov     rax, cs:gMgmTemplateFunc
0x180014892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014897  cmp     cs:dword_18002BA54, 2
0x18001489e  mov     eax, 57h ; 'W'
0x1800148a3  mov     edi, eax
0x1800148a5  jb      short loc_1800148C9
0x1800148a7  mov     rcx, cs:qword_18002BA58; hLogHandle
0x1800148ae  lea     edx, [rax-55h]; dwEventType
0x1800148b1  mov     [rsp+880h+dwErrorCode], eax; dwErrorCode
0x1800148b5  xor     r9d, r9d; dwSubStringCount
0x1800148b8  mov     r8d, 0C35Fh; dwMessageId
0x1800148be  mov     [rsp+880h+plpszSubStringArray], rbx; plpszSubStringArray
0x1800148c3  call    cs:__imp_RouterLogEventA
0x1800148c9  mov     rcx, cs:qword_18002B9E8
0x1800148d0  add     rcx, 10h
0x1800148d4  add     rcx, r13
0x1800148d7  call    ReleaseWriteLock
0x1800148dc  call    InvokeOutstandingCallbacks
0x1800148e1  test    edi, edi
0x1800148e3  jnz     short loc_1800148EB
0x1800148e5  lock dec dword ptr [r12+18h]
0x1800148eb  lea     rcx, qword_18002B9B8
0x1800148f2  call    ReleaseReadLock
0x1800148f7  cmp     cs:qword_18002B8A8, rbx
0x1800148fe  jz      short loc_180014938
0x180014900  mov     r8d, edi
0x180014903  mov     word ptr [rsp+880h+var_840], bx
0x180014908  lea     rdx, aLeavingMgmrele; "LEAVING MgmReleaseInterfaceOwnership %x"...
0x18001490f  lea     rcx, [rsp+880h+var_840]
0x180014914  call    FormatRRASErrorString
0x180014919  mov     rdx, cs:qword_18002B8A8
0x180014920  lea     r8, [rsp+880h+var_840]
0x180014925  mov     rcx, cs:gMgmEtwContext
0x18001492c  mov     rax, cs:gMgmTemplateFunc
0x180014933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014938  call    LeaveMgmWorker
0x18001493d  mov     eax, edi
0x18001493f  mov     rcx, [rbp+780h+var_40]
0x180014946  xor     rcx, rsp; StackCookie
0x180014949  call    __security_check_cookie
0x18001494e  mov     rbx, [rsp+880h+arg_18]
0x180014956  add     rsp, 850h
0x18001495d  pop     r15
0x18001495f  pop     r14
0x180014961  pop     r13
0x180014963  pop     r12
0x180014965  pop     rdi
0x180014966  pop     rsi
0x180014967  pop     rbp
0x180014968  retn
```
