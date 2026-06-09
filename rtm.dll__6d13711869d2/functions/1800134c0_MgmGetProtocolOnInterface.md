# MgmGetProtocolOnInterface

- ea: `0x1800134c0`
- end: `0x1800136c0`
- name: `MgmGetProtocolOnInterface`
- size: `512`
- prototype: `DWORD __stdcall(DWORD dwIfIndex, DWORD dwIfNextHopAddr, PDWORD pdwIfProtocolId, PDWORD pdwIfComponentId)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800134c0`
- `0x180014bfc`
- `0x180014f98`
- `0x180015040`
- `0x180015100`
- `0x18001bc4c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x18001363b`
- `rtutils!RouterLogEventA` at `0x18001363b`

## string_xrefs

- `0x18001352d`: `ENTERED MgmGetProtocolOnInterface : Interface %x, %x`
- `0x180013660`: `LEAVING MgmGetProtocolOnInterface : %x\n`

## pseudocode

```c
DWORD __stdcall MgmGetProtocolOnInterface(
        DWORD dwIfIndex,
        DWORD dwIfNextHopAddr,
        PDWORD pdwIfProtocolId,
        PDWORD pdwIfComponentId)
{
  __int64 v9; // rdi
  char *v10; // rbx
  __int64 v11; // rcx
  DWORD v12; // ebx
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
  {
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, L"ENTERED MgmGetProtocolOnInterface : Interface %x, %x", dwIfIndex, dwIfNextHopAddr);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v14);
  }
  v9 = 32LL * (dwIfIndex % dword_18002B92C);
  v10 = (char *)qword_18002B9E8 + v9;
  AcquireReadLock((char *)qword_18002B9E8 + v9 + 16);
  v13 = 0;
  if ( (unsigned int)FindIfEntry(v10, dwIfIndex, dwIfNextHopAddr, &v13) && (v11 = v13) != 0 )
  {
    v12 = 0;
    *pdwIfProtocolId = *(_DWORD *)(v13 + 24);
    *pdwIfComponentId = *(_DWORD *)(v11 + 28);
  }
  else
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"No interface entry present for interface %x, %x", dwIfIndex, dwIfNextHopAddr);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v14);
    }
    v12 = 1168;
    if ( (unsigned int)dword_18002BA54 >= 2 )
      RouterLogEventA(qword_18002BA58, 2u, 0xC35Fu, 0, 0, 0x490u);
  }
  ReleaseReadLock((char *)qword_18002B9E8 + v9 + 16);
  if ( qword_18002B8A8 )
  {
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, L"LEAVING MgmGetProtocolOnInterface : %x\n", v12);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v14);
  }
  LeaveMgmWorker();
  return v12;
}

```

## disassembly

```asm
0x1800134c0  push    rbp
0x1800134c2  push    rbx
0x1800134c3  push    rsi
0x1800134c4  push    rdi
0x1800134c5  push    r12
0x1800134c7  push    r14
0x1800134c9  push    r15
0x1800134cb  lea     rbp, [rsp-750h]
0x1800134d3  sub     rsp, 850h
0x1800134da  mov     rax, cs:__security_cookie
0x1800134e1  xor     rax, rsp
0x1800134e4  mov     [rbp+780h+var_40], rax
0x1800134eb  mov     r15, r8
0x1800134ee  mov     r14d, edx
0x1800134f1  mov     esi, ecx
0x1800134f3  xor     eax, eax
0x1800134f5  xor     edx, edx; Val
0x1800134f7  mov     [rsp+880h+var_840], eax
0x1800134fb  mov     r8d, 7FCh; Size
0x180013501  lea     rcx, [rsp+880h+var_83C]; void *
0x180013506  mov     r12, r9
0x180013509  call    memset_0
0x18001350e  call    EnterMgmAPI
0x180013513  test    eax, eax
0x180013515  jnz     short loc_180013521
0x180013517  mov     eax, 3EBh
0x18001351c  jmp     loc_18001369F
0x180013521  cmp     cs:qword_18002B8A8, 0
0x180013529  jz      short loc_180013568
0x18001352b  xor     eax, eax
0x18001352d  lea     rdx, aEnteredMgmgetp; "ENTERED MgmGetProtocolOnInterface : Int"...
0x180013534  mov     r9d, r14d
0x180013537  mov     word ptr [rsp+880h+var_840], ax
0x18001353c  mov     r8d, esi
0x18001353f  lea     rcx, [rsp+880h+var_840]
0x180013544  call    FormatRRASErrorString
0x180013549  mov     rdx, cs:qword_18002B8A8
0x180013550  lea     r8, [rsp+880h+var_840]
0x180013555  mov     rcx, cs:gMgmEtwContext
0x18001355c  mov     rax, cs:gMgmTemplateFunc
0x180013563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013568  mov     rbx, cs:qword_18002B9E8
0x18001356f  xor     edx, edx
0x180013571  mov     eax, esi
0x180013573  div     cs:dword_18002B92C
0x180013579  mov     edi, edx
0x18001357b  shl     rdi, 5
0x18001357f  add     rbx, rdi
0x180013582  lea     rcx, [rbx+10h]
0x180013586  call    AcquireReadLock
0x18001358b  lea     r9, [rsp+880h+var_850]
0x180013590  mov     [rsp+880h+var_850], 0
0x180013599  mov     r8d, r14d
0x18001359c  mov     edx, esi
0x18001359e  mov     rcx, rbx
0x1800135a1  call    FindIfEntry
0x1800135a6  test    eax, eax
0x1800135a8  jz      short loc_1800135C5
0x1800135aa  mov     rcx, [rsp+880h+var_850]
0x1800135af  test    rcx, rcx
0x1800135b2  jz      short loc_1800135C5
0x1800135b4  mov     eax, [rcx+18h]
0x1800135b7  xor     ebx, ebx
0x1800135b9  mov     [r15], eax
0x1800135bc  mov     eax, [rcx+1Ch]
0x1800135bf  mov     [r12], eax
0x1800135c3  jmp     short loc_180013641
0x1800135c5  cmp     cs:qword_18002B8A8, 0
0x1800135cd  jz      short loc_18001360C
0x1800135cf  xor     eax, eax
0x1800135d1  lea     rdx, aNoInterfaceEnt; "No interface entry present for interfac"...
0x1800135d8  mov     r9d, r14d
0x1800135db  mov     word ptr [rsp+880h+var_840], ax
0x1800135e0  mov     r8d, esi
0x1800135e3  lea     rcx, [rsp+880h+var_840]
0x1800135e8  call    FormatRRASErrorString
0x1800135ed  mov     rdx, cs:qword_18002B8A8
0x1800135f4  lea     r8, [rsp+880h+var_840]
0x1800135f9  mov     rcx, cs:gMgmEtwContext
0x180013600  mov     rax, cs:gMgmTemplateFunc
0x180013607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001360c  mov     edx, 2; dwEventType
0x180013611  mov     ebx, 490h
0x180013616  cmp     cs:dword_18002BA54, edx
0x18001361c  jb      short loc_180013641
0x18001361e  mov     rcx, cs:qword_18002BA58; hLogHandle
0x180013625  xor     r9d, r9d; dwSubStringCount
0x180013628  mov     [rsp+880h+dwErrorCode], ebx; dwErrorCode
0x18001362c  mov     r8d, 0C35Fh; dwMessageId
0x180013632  mov     [rsp+880h+plpszSubStringArray], 0; plpszSubStringArray
0x18001363b  call    cs:__imp_RouterLogEventA
0x180013641  mov     rcx, cs:qword_18002B9E8
0x180013648  add     rcx, 10h
0x18001364c  add     rcx, rdi
0x18001364f  call    ReleaseReadLock
0x180013654  cmp     cs:qword_18002B8A8, 0
0x18001365c  jz      short loc_180013698
0x18001365e  xor     eax, eax
0x180013660  lea     rdx, aLeavingMgmgetp; "LEAVING MgmGetProtocolOnInterface : %x"...
0x180013667  mov     r8d, ebx
0x18001366a  mov     word ptr [rsp+880h+var_840], ax
0x18001366f  lea     rcx, [rsp+880h+var_840]
0x180013674  call    FormatRRASErrorString
0x180013679  mov     rdx, cs:qword_18002B8A8
0x180013680  lea     r8, [rsp+880h+var_840]
0x180013685  mov     rcx, cs:gMgmEtwContext
0x18001368c  mov     rax, cs:gMgmTemplateFunc
0x180013693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013698  call    LeaveMgmWorker
0x18001369d  mov     eax, ebx
0x18001369f  mov     rcx, [rbp+780h+var_40]
0x1800136a6  xor     rcx, rsp; StackCookie
0x1800136a9  call    __security_check_cookie
0x1800136ae  add     rsp, 850h
0x1800136b5  pop     r15
0x1800136b7  pop     r14
0x1800136b9  pop     r12
0x1800136bb  pop     rdi
0x1800136bc  pop     rsi
0x1800136bd  pop     rbx
0x1800136be  pop     rbp
0x1800136bf  retn
```
