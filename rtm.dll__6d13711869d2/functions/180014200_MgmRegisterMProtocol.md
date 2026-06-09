# MgmRegisterMProtocol

- ea: `0x180014200`
- end: `0x180014577`
- name: `MgmRegisterMProtocol`
- size: `887`
- prototype: `DWORD __stdcall(PROUTING_PROTOCOL_CONFIG prpiInfo, DWORD dwProtocolId, DWORD dwComponentId, HANDLE *phProtocol)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180014200`
- `0x180014d2c`
- `0x180014f98`
- `0x180015040`
- `0x180015178`
- `0x18001b548`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x18001fa10`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180014380`
- `KERNEL32!HeapAlloc` at `0x180014380`
- `rtutils!RouterLogEventA` at `0x180014349`
- `rtutils!RouterLogEventA` at `0x180014403`
- `rtutils!RouterLogEventA` at `0x18001447b`
- `rtutils!RouterLogEventA` at `0x180014349`
- `rtutils!RouterLogEventA` at `0x180014403`
- `rtutils!RouterLogEventA` at `0x18001447b`

## string_xrefs

- `0x180014274`: `ENTERED MgmRegisterMProtocol %x, %x`
- `0x1800142e4`: `Entry already present for protocol : %x, %x`
- `0x180014415`: `Failed to create protocol entry %x`
- `0x180014517`: `LEAVING MgmRegisterMProtocol : %x\n`
- `0x1800143a5`: `CreateProtocolEntry : Could not allocate protocol entry %x`

## pseudocode

```c
DWORD __stdcall MgmRegisterMProtocol(
        PROUTING_PROTOCOL_CONFIG prpiInfo,
        DWORD dwProtocolId,
        DWORD dwComponentId,
        HANDLE *phProtocol)
{
  DWORD v9; // ebx
  __int64 v10; // rax
  __int128 v11; // xmm0
  __int64 *v12; // rcx
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[2044]; // [rsp+34h] [rbp-CCh] BYREF
  int v15; // [rsp+830h] [rbp+730h] BYREF
  _BYTE v16[2044]; // [rsp+834h] [rbp+734h] BYREF

  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"ENTERED MgmRegisterMProtocol %x, %x", dwProtocolId, dwComponentId);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v13);
  }
  AcquireWriteLock(&qword_18002B9B8);
  if ( GetProtocolEntry(&qword_18002B9A8, dwProtocolId, dwComponentId) )
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"Entry already present for protocol : %x, %x", dwProtocolId, dwComponentId);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v13);
    }
    if ( dword_18002BA54 )
      RouterLogEventA(qword_18002BA58, 1u, 0xC35Bu, 0, 0, dwProtocolId);
    v9 = 183;
  }
  else
  {
    v15 = 0;
    memset_0(v16, 0, sizeof(v16));
    v10 = (__int64)HeapAlloc(hHeap, 0, 0x78u);
    if ( v10 )
    {
      *(_QWORD *)(v10 + 8) = v10;
      *(_QWORD *)v10 = v10;
      *(_DWORD *)(v10 + 16) = dwProtocolId;
      *(_DWORD *)(v10 + 20) = dwComponentId;
      *(_DWORD *)(v10 + 24) = 0;
      *(_OWORD *)(v10 + 32) = *(_OWORD *)&prpiInfo->dwCallbackFlags;
      *(_OWORD *)(v10 + 48) = *(_OWORD *)&prpiInfo->pfnCreationAlertCallback;
      *(_OWORD *)(v10 + 64) = *(_OWORD *)&prpiInfo->pfnJoinAlertCallback;
      *(_OWORD *)(v10 + 80) = *(_OWORD *)&prpiInfo->pfnLocalJoinCallback;
      v11 = *(_OWORD *)&prpiInfo->pfnDisableIgmpCallback;
      *(_DWORD *)(v10 + 112) = 1296518512;
      *(_OWORD *)(v10 + 96) = v11;
      v12 = (__int64 *)qword_18002B9B0;
      if ( *(__int64 **)qword_18002B9B0 != &qword_18002B9A8 )
        __fastfail(3u);
      *(_QWORD *)v10 = &qword_18002B9A8;
      *(_QWORD *)(v10 + 8) = v12;
      *v12 = v10;
      ++dword_18002B9A0;
      qword_18002B9B0 = v10;
      *phProtocol = (HANDLE)(v10 ^ 0x474D6300);
      v9 = 0;
    }
    else
    {
      v9 = 8;
      if ( qword_18002B8A8 )
      {
        LOWORD(v15) = 0;
        FormatRRASErrorString(&v15, L"CreateProtocolEntry : Could not allocate protocol entry %x", 8);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v15);
      }
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
      if ( qword_18002B8A8 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"Failed to create protocol entry %x", 8);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v13);
      }
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC35Cu, 0, 0, 8u);
    }
  }
  ReleaseWriteLock(&qword_18002B9B8);
  LeaveMgmWorker();
  if ( qword_18002B8A8 )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"LEAVING MgmRegisterMProtocol : %x\n", v9);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v13);
  }
  return v9;
}

```

## disassembly

```asm
0x180014200  mov     [rsp-8+arg_0], rbx
0x180014205  push    rbp
0x180014206  push    rsi
0x180014207  push    rdi
0x180014208  push    r12
0x18001420a  push    r14
0x18001420c  lea     rbp, [rsp-0F40h]
0x180014214  mov     eax, 1040h
0x180014219  call    _alloca_probe
0x18001421e  sub     rsp, rax
0x180014221  mov     rax, cs:__security_cookie
0x180014228  xor     rax, rsp
0x18001422b  mov     [rbp+0F60h+var_30], rax
0x180014232  mov     edi, r8d
0x180014235  mov     ebx, edx
0x180014237  mov     rsi, rcx
0x18001423a  xor     eax, eax
0x18001423c  xor     edx, edx; Val
0x18001423e  mov     [rsp+1060h+var_1030], eax
0x180014242  mov     r8d, 7FCh; Size
0x180014248  lea     rcx, [rsp+1060h+var_102C]; void *
0x18001424d  mov     r14, r9
0x180014250  call    memset_0
0x180014255  call    EnterMgmAPI
0x18001425a  test    eax, eax
0x18001425c  jnz     short loc_180014268
0x18001425e  mov     eax, 3EBh
0x180014263  jmp     loc_180014551
0x180014268  cmp     cs:qword_18002B8A8, 0
0x180014270  jz      short loc_1800142AF
0x180014272  xor     eax, eax
0x180014274  lea     rdx, aEnteredMgmregi; "ENTERED MgmRegisterMProtocol %x, %x"
0x18001427b  mov     r9d, edi
0x18001427e  mov     word ptr [rsp+1060h+var_1030], ax
0x180014283  mov     r8d, ebx
0x180014286  lea     rcx, [rsp+1060h+var_1030]
0x18001428b  call    FormatRRASErrorString
0x180014290  mov     rdx, cs:qword_18002B8A8
0x180014297  lea     r8, [rsp+1060h+var_1030]
0x18001429c  mov     rcx, cs:gMgmEtwContext
0x1800142a3  mov     rax, cs:gMgmTemplateFunc
0x1800142aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142af  lea     rcx, qword_18002B9B8
0x1800142b6  call    AcquireWriteLock
0x1800142bb  lea     r12, qword_18002B9A8
0x1800142c2  mov     r8d, edi
0x1800142c5  mov     rcx, r12
0x1800142c8  mov     edx, ebx
0x1800142ca  call    GetProtocolEntry
0x1800142cf  test    rax, rax
0x1800142d2  jz      loc_180014359
0x1800142d8  cmp     cs:qword_18002B8A8, 0
0x1800142e0  jz      short loc_18001431F
0x1800142e2  xor     eax, eax
0x1800142e4  lea     rdx, aEntryAlreadyPr; "Entry already present for protocol : %x"...
0x1800142eb  mov     r9d, edi
0x1800142ee  mov     word ptr [rsp+1060h+var_1030], ax
0x1800142f3  mov     r8d, ebx
0x1800142f6  lea     rcx, [rsp+1060h+var_1030]
0x1800142fb  call    FormatRRASErrorString
0x180014300  mov     rdx, cs:qword_18002B8A8
0x180014307  lea     r8, [rsp+1060h+var_1030]
0x18001430c  mov     rcx, cs:gMgmEtwContext
0x180014313  mov     rax, cs:gMgmTemplateFunc
0x18001431a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001431f  cmp     cs:dword_18002BA54, 1
0x180014326  jb      short loc_18001434F
0x180014328  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001432f  xor     r9d, r9d; dwSubStringCount
0x180014332  mov     [rsp+1060h+dwErrorCode], ebx; dwErrorCode
0x180014336  mov     r8d, 0C35Bh; dwMessageId
0x18001433c  mov     [rsp+1060h+plpszSubStringArray], 0; plpszSubStringArray
0x180014345  lea     edx, [r9+1]; dwEventType
0x180014349  call    cs:__imp_RouterLogEventA
0x18001434f  mov     ebx, 0B7h
0x180014354  jmp     loc_1800144FA
0x180014359  xor     edx, edx; Val
0x18001435b  mov     [rbp+0F60h+var_830], eax
0x180014361  mov     r8d, 7FCh; Size
0x180014367  lea     rcx, [rbp+0F60h+var_82C]; void *
0x18001436e  call    memset_0
0x180014373  mov     rcx, cs:hHeap; hHeap
0x18001437a  xor     edx, edx; dwFlags
0x18001437c  lea     r8d, [rdx+78h]; dwBytes
0x180014380  call    cs:__imp_HeapAlloc
0x180014386  test    rax, rax
0x180014389  jnz     loc_180014483
0x18001438f  cmp     cs:qword_18002B8A8, rax
0x180014396  lea     ebx, [rax+8]
0x180014399  jz      short loc_1800143D9
0x18001439b  mov     r8d, ebx
0x18001439e  mov     word ptr [rbp+0F60h+var_830], ax
0x1800143a5  lea     rdx, aCreateprotocol; "CreateProtocolEntry : Could not allocat"...
0x1800143ac  lea     rcx, [rbp+0F60h+var_830]
0x1800143b3  call    FormatRRASErrorString
0x1800143b8  mov     rdx, cs:qword_18002B8A8
0x1800143bf  lea     r8, [rbp+0F60h+var_830]
0x1800143c6  mov     rcx, cs:gMgmEtwContext
0x1800143cd  mov     rax, cs:gMgmTemplateFunc
0x1800143d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143d9  cmp     cs:dword_18002BA54, 1
0x1800143e0  jb      short loc_180014409
0x1800143e2  mov     rcx, cs:qword_18002BA58; hLogHandle
0x1800143e9  xor     r9d, r9d; dwSubStringCount
0x1800143ec  mov     [rsp+1060h+dwErrorCode], ebx; dwErrorCode
0x1800143f0  mov     r8d, 0C353h; dwMessageId
0x1800143f6  mov     [rsp+1060h+plpszSubStringArray], 0; plpszSubStringArray
0x1800143ff  lea     edx, [r9+1]; dwEventType
0x180014403  call    cs:__imp_RouterLogEventA
0x180014409  cmp     cs:qword_18002B8A8, 0
0x180014411  jz      short loc_18001444D
0x180014413  xor     eax, eax
0x180014415  lea     rdx, aFailedToCreate; "Failed to create protocol entry %x"
0x18001441c  mov     r8d, ebx
0x18001441f  mov     word ptr [rsp+1060h+var_1030], ax
0x180014424  lea     rcx, [rsp+1060h+var_1030]
0x180014429  call    FormatRRASErrorString
0x18001442e  mov     rdx, cs:qword_18002B8A8
0x180014435  lea     r8, [rsp+1060h+var_1030]
0x18001443a  mov     rcx, cs:gMgmEtwContext
0x180014441  mov     rax, cs:gMgmTemplateFunc
0x180014448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001444d  cmp     cs:dword_18002BA54, 1
0x180014454  jb      loc_1800144FA
0x18001445a  mov     rcx, cs:qword_18002BA58; hLogHandle
0x180014461  xor     r9d, r9d; dwSubStringCount
0x180014464  mov     [rsp+1060h+dwErrorCode], ebx; dwErrorCode
0x180014468  mov     r8d, 0C35Ch; dwMessageId
0x18001446e  mov     [rsp+1060h+plpszSubStringArray], 0; plpszSubStringArray
0x180014477  lea     edx, [r9+1]; dwEventType
0x18001447b  call    cs:__imp_RouterLogEventA
0x180014481  jmp     short loc_1800144FA
0x180014483  mov     [rax+8], rax
0x180014487  mov     [rax], rax
0x18001448a  mov     [rax+10h], ebx
0x18001448d  mov     [rax+14h], edi
0x180014490  mov     dword ptr [rax+18h], 0
0x180014497  movups  xmm0, xmmword ptr [rsi]
0x18001449a  movups  xmmword ptr [rax+20h], xmm0
0x18001449e  movups  xmm1, xmmword ptr [rsi+10h]
0x1800144a2  movups  xmmword ptr [rax+30h], xmm1
0x1800144a6  movups  xmm0, xmmword ptr [rsi+20h]
0x1800144aa  movups  xmmword ptr [rax+40h], xmm0
0x1800144ae  movups  xmm1, xmmword ptr [rsi+30h]
0x1800144b2  movups  xmmword ptr [rax+50h], xmm1
0x1800144b6  movups  xmm0, xmmword ptr [rsi+40h]
0x1800144ba  mov     dword ptr [rax+70h], 4D474D70h
0x1800144c1  movups  xmmword ptr [rax+60h], xmm0
0x1800144c5  mov     rcx, cs:qword_18002B9B0
0x1800144cc  cmp     [rcx], r12
0x1800144cf  jz      short loc_1800144D8
0x1800144d1  mov     ecx, 3
0x1800144d6  int     29h; Win8: RtlFailFast(ecx)
0x1800144d8  mov     [rax], r12
0x1800144db  mov     [rax+8], rcx
0x1800144df  mov     [rcx], rax
0x1800144e2  inc     cs:dword_18002B9A0
0x1800144e8  mov     cs:qword_18002B9B0, rax
0x1800144ef  xor     rax, 474D6300h
0x1800144f5  mov     [r14], rax
0x1800144f8  xor     ebx, ebx
0x1800144fa  lea     rcx, qword_18002B9B8
0x180014501  call    ReleaseWriteLock
0x180014506  call    LeaveMgmWorker
0x18001450b  cmp     cs:qword_18002B8A8, 0
0x180014513  jz      short loc_18001454F
0x180014515  xor     ecx, ecx
0x180014517  lea     rdx, aLeavingMgmregi; "LEAVING MgmRegisterMProtocol : %x\n"
0x18001451e  mov     word ptr [rsp+1060h+var_1030], cx
0x180014523  mov     r8d, ebx
0x180014526  lea     rcx, [rsp+1060h+var_1030]
0x18001452b  call    FormatRRASErrorString
0x180014530  mov     rdx, cs:qword_18002B8A8
0x180014537  lea     r8, [rsp+1060h+var_1030]
0x18001453c  mov     rcx, cs:gMgmEtwContext
0x180014543  mov     rax, cs:gMgmTemplateFunc
0x18001454a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001454f  mov     eax, ebx
0x180014551  mov     rcx, [rbp+0F60h+var_30]
0x180014558  xor     rcx, rsp; StackCookie
0x18001455b  call    __security_check_cookie
0x180014560  mov     rbx, [rsp+1060h+arg_0]
0x180014568  add     rsp, 1040h
0x18001456f  pop     r14
0x180014571  pop     r12
0x180014573  pop     rdi
0x180014574  pop     rsi
0x180014575  pop     rbp
0x180014576  retn
```
