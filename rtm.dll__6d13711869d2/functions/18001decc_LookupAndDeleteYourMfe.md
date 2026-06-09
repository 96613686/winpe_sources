# LookupAndDeleteYourMfe

- ea: `0x18001decc`
- end: `0x18001e36c`
- name: `LookupAndDeleteYourMfe`
- size: `1184`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x1800155fc`
- `0x180016d00`
- `0x18001b9ac`

## callees

- `0x180007220`
- `0x18000a670`
- `0x18000aa60`
- `0x180014d2c`
- `0x180015178`
- `0x1800157ec`
- `0x18001d1ec`
- `0x18001db88`
- `0x18001dbd0`
- `0x18001de20`
- `0x18001de98`
- `0x18001decc`
- `0x18001f334`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `ntdll!RtlDeleteTimer` at `0x18001e17a`
- `ntdll!RtlDeleteTimer` at `0x18001e17a`
- `KERNEL32!HeapFree` at `0x18001e2c1`
- `KERNEL32!HeapFree` at `0x18001e325`
- `KERNEL32!HeapFree` at `0x18001e2c1`
- `KERNEL32!HeapFree` at `0x18001e325`

## string_xrefs

- `0x18001dfbc`: `LookupAndDeleteYourMfe : Could not find group entry%x, %x`
- `0x18001e04b`: `LookupAndDeleteYourMfe : Could not find source entry%x, %x`

## pseudocode

```c
__int64 __fastcall LookupAndDeleteYourMfe(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        _DWORD *a6,
        __int64 a7,
        int a8)
{
  unsigned int v11; // edx
  __int64 v12; // r13
  __int64 GroupEntry; // rax
  __int64 v14; // rdi
  __int64 v15; // r12
  unsigned int v16; // edx
  __int64 SourceEntry; // rax
  __int64 v18; // rbx
  _DWORD *v20; // rcx
  _QWORD **v21; // rsi
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  unsigned int *v24; // rsi
  DWORD MostSpecificDestination; // eax
  DWORD OpaqueInformationPointer; // eax
  __int64 v27; // r14
  int v28; // r8d
  void *v29; // r8
  _QWORD *v30; // rax
  LPVOID *v31; // rcx
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+30h] [rbp-D0h]
  PVOID OpaqueInfoPointer; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h]
  struct _RTM_DEST_INFO DestInfo; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTM_NET_ADDRESS DestAddress; // [rsp+B0h] [rbp-50h] BYREF
  int v39; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v40[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v36 = a7;
  memset(&DestAddress, 0, sizeof(DestAddress));
  memset_0(&DestInfo, 0, sizeof(DestInfo));
  OpaqueInfoPointer = 0;
  lpMem = 0;
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  if ( a3 )
    v11 = a3 % (dword_18002B930 - 1) + 1;
  else
    v11 = 0;
  v12 = 32LL * v11;
  AcquireWriteLock((char *)qword_18002BA40 + v12 + 16);
  GroupEntry = GetGroupEntry((char *)qword_18002BA40 + v12, a3);
  v14 = GroupEntry;
  if ( !GroupEntry )
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"LookupAndDeleteYourMfe : Could not find group entry%x, %x", a3, a4);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v39);
    }
    return ReleaseWriteLock((char *)qword_18002BA40 + v12 + 16);
  }
  v33 = 0;
  v15 = GroupEntry + 40;
  AcquireWriteLock(GroupEntry + 40);
  if ( a1 )
    v16 = a1 % (dword_18002B934 - 1) + 1;
  else
    v16 = 0;
  SourceEntry = GetSourceEntry(v14 + 16LL * v16 + 88, a1);
  v18 = SourceEntry;
  if ( !SourceEntry )
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"LookupAndDeleteYourMfe : Could not find source entry%x, %x", a3, a4);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v39);
    }
LABEL_13:
    ReleaseWriteLock(v15);
    goto LABEL_14;
  }
  if ( a6 )
  {
    v20 = (_DWORD *)v36;
    *a6 = *(_DWORD *)(SourceEntry + 112);
    *v20 = *(_DWORD *)(SourceEntry + 116);
  }
  v21 = (_QWORD **)(SourceEntry + 88);
  while ( 1 )
  {
    v22 = *v21;
    if ( *v21 == v21 )
      break;
    if ( (_QWORD **)v22[1] != v21 )
      goto LABEL_41;
    v23 = (_QWORD *)*v22;
    if ( *(_QWORD **)(*v22 + 8LL) != v22 )
      goto LABEL_41;
    *v21 = v23;
    v23[1] = v21;
    *v22 = v22;
    v22[1] = v22;
    DeleteOutInterfaceEntry();
  }
  *(_QWORD *)(v18 + 112) = 0;
  *(_QWORD *)(v18 + 136) = -1;
  if ( *(_DWORD *)(v18 + 144) )
    DeleteMfeFromForwarder(v14, v18);
  if ( *(_QWORD *)(v18 + 152) )
  {
    RtlDeleteTimer(*((HANDLE *)qword_18002BA48 + a3 % dword_18002B95C), *(HANDLE *)(v18 + 152), 0);
    if ( a8 )
      goto LABEL_46;
    v24 = *(unsigned int **)(v18 + 160);
    if ( !v24 )
      goto LABEL_46;
    *(_DWORD *)DestAddress.AddrBits = *v24;
    *(_DWORD *)&DestAddress.AddressFamily = 2097154;
    MostSpecificDestination = RtmGetMostSpecificDestination(g_hRtmHandle, &DestAddress, 0, 2u, &DestInfo);
    if ( MostSpecificDestination )
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"No Route to source %x, %d", *v24, MostSpecificDestination);
LABEL_32:
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v39);
      }
    }
    else
    {
      v33 = 1;
      OpaqueInformationPointer = RtmGetOpaqueInformationPointer(g_hRtmHandle, DestInfo.DestHandle, &OpaqueInfoPointer);
      if ( !OpaqueInformationPointer )
      {
        v27 = *(_QWORD *)OpaqueInfoPointer;
        if ( *(_QWORD *)OpaqueInfoPointer )
        {
          AcquireWriteLock(v27 + 16);
          if ( (unsigned int)FindRefEntry(v27, *v24, v28, v24[2], v32, (__int64)&lpMem) )
          {
            v29 = lpMem;
            v30 = *(_QWORD **)lpMem;
            if ( *(LPVOID *)(*(_QWORD *)lpMem + 8LL) != lpMem || (v31 = (LPVOID *)*((_QWORD *)lpMem + 1), *v31 != lpMem) )
LABEL_41:
              __fastfail(3u);
            *v31 = v30;
            v30[1] = v31;
            HeapFree(hHeap, 0, v29);
          }
          else if ( qword_18002B8A8 )
          {
            LOWORD(v39) = 0;
            FormatRRASErrorString(&v39, L"Reference does not exist for source %x", *v24);
            ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v39);
          }
          ReleaseWriteLock(v27 + 16);
        }
        HeapFree(hHeap, 0, v24);
        *(_QWORD *)(v18 + 160) = 0;
        goto LABEL_46;
      }
      if ( qword_18002B8A8 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"Failed to retrieve opaque pointer %x", OpaqueInformationPointer);
        goto LABEL_32;
      }
    }
LABEL_46:
    *(_QWORD *)(v18 + 152) = 0;
  }
  if ( *(_QWORD *)(v18 + 48) == v18 + 48 )
  {
    DeleteSourceEntry(v18);
    --*(_DWORD *)(v14 + 48);
  }
  if ( *(_DWORD *)(v14 + 48) )
    goto LABEL_13;
  ReleaseWriteLock(v15);
  DeleteGroupEntry(v14);
LABEL_14:
  if ( v33 )
    RtmReleaseDestInfo(g_hRtmHandle, &DestInfo);
  return ReleaseWriteLock((char *)qword_18002BA40 + v12 + 16);
}

```

## disassembly

```asm
0x18001decc  mov     [rsp-8+arg_8], rbx
0x18001ded1  push    rbp
0x18001ded2  push    rsi
0x18001ded3  push    rdi
0x18001ded4  push    r12
0x18001ded6  push    r13
0x18001ded8  push    r14
0x18001deda  push    r15
0x18001dedc  lea     rbp, [rsp-7E0h]
0x18001dee4  sub     rsp, 8E0h
0x18001deeb  mov     rax, cs:__security_cookie
0x18001def2  xor     rax, rsp
0x18001def5  mov     [rbp+810h+var_40], rax
0x18001defc  mov     rax, [rbp+810h+arg_30]
0x18001df03  mov     r14d, r8d
0x18001df06  mov     rsi, [rbp+810h+arg_28]
0x18001df0d  mov     ebx, ecx
0x18001df0f  mov     [rsp+910h+var_8C8], rax
0x18001df14  lea     rcx, [rsp+910h+DestInfo]; void *
0x18001df19  xor     eax, eax
0x18001df1b  xorps   xmm0, xmm0
0x18001df1e  xor     edx, edx; Val
0x18001df20  mov     dword ptr [rbp+810h+DestAddress.AddrBits+0Ch], eax
0x18001df23  mov     r15d, r9d
0x18001df26  movups  xmmword ptr [rbp+810h+DestAddress.AddressFamily], xmm0
0x18001df2a  lea     r8d, [rax+58h]; Size
0x18001df2e  call    memset_0
0x18001df33  xor     r12d, r12d
0x18001df36  lea     rcx, [rbp+810h+var_83C]; void *
0x18001df3a  xor     edx, edx; Val
0x18001df3c  mov     [rsp+910h+OpaqueInfoPointer], r12
0x18001df41  mov     r8d, 7FCh; Size
0x18001df47  mov     [rsp+910h+lpMem], r12
0x18001df4c  mov     [rbp+810h+var_840], r12d
0x18001df50  call    memset_0
0x18001df55  test    r14d, r14d
0x18001df58  jz      short loc_18001DF6D
0x18001df5a  mov     ecx, cs:dword_18002B930
0x18001df60  xor     edx, edx
0x18001df62  dec     ecx
0x18001df64  mov     eax, r14d
0x18001df67  div     ecx
0x18001df69  inc     edx
0x18001df6b  jmp     short loc_18001DF70
0x18001df6d  mov     edx, r12d
0x18001df70  mov     rcx, cs:qword_18002BA40
0x18001df77  mov     r13d, edx
0x18001df7a  add     rcx, 10h
0x18001df7e  shl     r13, 5
0x18001df82  add     rcx, r13
0x18001df85  call    AcquireWriteLock
0x18001df8a  mov     rcx, cs:qword_18002BA40
0x18001df91  mov     edx, r14d
0x18001df94  add     rcx, r13
0x18001df97  call    GetGroupEntry
0x18001df9c  mov     rdi, rax
0x18001df9f  test    rax, rax
0x18001dfa2  jnz     short loc_18001DFEF
0x18001dfa4  cmp     cs:qword_18002B8A8, r12
0x18001dfab  jz      loc_18001E09C
0x18001dfb1  mov     r9d, r15d
0x18001dfb4  mov     word ptr [rbp+810h+var_840], r12w
0x18001dfb9  mov     r8d, r14d
0x18001dfbc  lea     rdx, aLookupanddelet; "LookupAndDeleteYourMfe : Could not find"...
0x18001dfc3  lea     rcx, [rbp+810h+var_840]
0x18001dfc7  call    FormatRRASErrorString
0x18001dfcc  mov     rdx, cs:qword_18002B8A8
0x18001dfd3  lea     r8, [rbp+810h+var_840]
0x18001dfd7  mov     rcx, cs:gMgmEtwContext
0x18001dfde  mov     rax, cs:gMgmTemplateFunc
0x18001dfe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfea  jmp     loc_18001E09C
0x18001dfef  mov     [rsp+910h+var_8E0], r12d
0x18001dff4  lea     r12, [rax+28h]
0x18001dff8  mov     rcx, r12
0x18001dffb  call    AcquireWriteLock
0x18001e000  test    ebx, ebx
0x18001e002  jz      short loc_18001E016
0x18001e004  mov     ecx, cs:dword_18002B934
0x18001e00a  xor     edx, edx
0x18001e00c  dec     ecx
0x18001e00e  mov     eax, ebx
0x18001e010  div     ecx
0x18001e012  inc     edx
0x18001e014  jmp     short loc_18001E018
0x18001e016  xor     edx, edx
0x18001e018  mov     ecx, edx
0x18001e01a  mov     edx, ebx
0x18001e01c  shl     rcx, 4
0x18001e020  add     rcx, 58h ; 'X'
0x18001e024  add     rcx, rdi
0x18001e027  call    GetSourceEntry
0x18001e02c  mov     rbx, rax
0x18001e02f  test    rax, rax
0x18001e032  jnz     loc_18001E0D9
0x18001e038  cmp     cs:qword_18002B8A8, rax
0x18001e03f  jz      short loc_18001E079
0x18001e041  mov     r9d, r15d
0x18001e044  mov     word ptr [rbp+810h+var_840], ax
0x18001e048  mov     r8d, r14d
0x18001e04b  lea     rdx, aLookupanddelet_0; "LookupAndDeleteYourMfe : Could not find"...
0x18001e052  lea     rcx, [rbp+810h+var_840]
0x18001e056  call    FormatRRASErrorString
0x18001e05b  mov     rdx, cs:qword_18002B8A8
0x18001e062  lea     r8, [rbp+810h+var_840]
0x18001e066  mov     rcx, cs:gMgmEtwContext
0x18001e06d  mov     rax, cs:gMgmTemplateFunc
0x18001e074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e079  xor     r15d, r15d
0x18001e07c  mov     rcx, r12
0x18001e07f  call    ReleaseWriteLock
0x18001e084  cmp     [rsp+910h+var_8E0], r15d
0x18001e089  jz      short loc_18001E09C
0x18001e08b  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x18001e092  lea     rdx, [rsp+910h+DestInfo]; DestInfo
0x18001e097  call    RtmReleaseDestInfo
0x18001e09c  mov     rcx, cs:qword_18002BA40
0x18001e0a3  add     rcx, 10h
0x18001e0a7  add     rcx, r13
0x18001e0aa  call    ReleaseWriteLock
0x18001e0af  mov     rcx, [rbp+810h+var_40]
0x18001e0b6  xor     rcx, rsp; StackCookie
0x18001e0b9  call    __security_check_cookie
0x18001e0be  mov     rbx, [rsp+910h+arg_8]
0x18001e0c6  add     rsp, 8E0h
0x18001e0cd  pop     r15
0x18001e0cf  pop     r14
0x18001e0d1  pop     r13
0x18001e0d3  pop     r12
0x18001e0d5  pop     rdi
0x18001e0d6  pop     rsi
0x18001e0d7  pop     rbp
0x18001e0d8  retn
0x18001e0d9  xor     r15d, r15d
0x18001e0dc  test    rsi, rsi
0x18001e0df  jz      short loc_18001E0F0
0x18001e0e1  mov     eax, [rax+70h]
0x18001e0e4  mov     rcx, [rsp+910h+var_8C8]
0x18001e0e9  mov     [rsi], eax
0x18001e0eb  mov     eax, [rbx+74h]
0x18001e0ee  mov     [rcx], eax
0x18001e0f0  lea     rsi, [rbx+58h]
0x18001e0f4  mov     rcx, [rsi]
0x18001e0f7  cmp     rcx, rsi
0x18001e0fa  jz      short loc_18001E128
0x18001e0fc  cmp     [rcx+8], rsi
0x18001e100  jnz     loc_18001E2C9
0x18001e106  mov     rax, [rcx]
0x18001e109  cmp     [rax+8], rcx
0x18001e10d  jnz     loc_18001E2C9
0x18001e113  mov     [rsi], rax
0x18001e116  mov     [rax+8], rsi
0x18001e11a  mov     [rcx], rcx
0x18001e11d  mov     [rcx+8], rcx
0x18001e121  call    DeleteOutInterfaceEntry
0x18001e126  jmp     short loc_18001E0F4
0x18001e128  mov     [rbx+70h], r15
0x18001e12c  mov     qword ptr [rbx+88h], 0FFFFFFFFFFFFFFFFh
0x18001e137  cmp     [rbx+90h], r15d
0x18001e13e  jz      short loc_18001E14B
0x18001e140  mov     rdx, rbx
0x18001e143  mov     rcx, rdi
0x18001e146  call    DeleteMfeFromForwarder
0x18001e14b  mov     rcx, [rbx+98h]
0x18001e152  test    rcx, rcx
0x18001e155  jz      loc_18001E339
0x18001e15b  xor     edx, edx
0x18001e15d  mov     eax, r14d
0x18001e160  div     cs:dword_18002B95C
0x18001e166  xor     r8d, r8d; CompletionEvent
0x18001e169  mov     r9d, edx
0x18001e16c  mov     rdx, rcx; Timer
0x18001e16f  mov     rcx, cs:qword_18002BA48
0x18001e176  mov     rcx, [rcx+r9*8]; TimerQueue
0x18001e17a  call    cs:__imp_RtlDeleteTimer
0x18001e180  cmp     [rbp+810h+arg_38], r15d
0x18001e187  jnz     loc_18001E332
0x18001e18d  mov     rsi, [rbx+0A0h]
0x18001e194  test    rsi, rsi
0x18001e197  jz      loc_18001E332
0x18001e19d  mov     eax, [rsi]
0x18001e19f  lea     rdx, [rbp+810h+DestAddress]; DestAddress
0x18001e1a3  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x18001e1aa  mov     r9d, 2; TargetViews
0x18001e1b0  mov     dword ptr [rbp+810h+DestAddress.AddrBits], eax
0x18001e1b3  xor     r8d, r8d; ProtocolId
0x18001e1b6  lea     rax, [rsp+910h+DestInfo]
0x18001e1bb  mov     dword ptr [rbp+810h+DestAddress.AddressFamily], 200002h
0x18001e1c2  mov     [rsp+910h+var_8F0], rax; DestInfo
0x18001e1c7  call    RtmGetMostSpecificDestination
0x18001e1cc  test    eax, eax
0x18001e1ce  jz      short loc_18001E21B
0x18001e1d0  cmp     cs:qword_18002B8A8, r15
0x18001e1d7  jz      loc_18001E332
0x18001e1dd  mov     word ptr [rbp+810h+var_840], r15w
0x18001e1e2  lea     rdx, aNoRouteToSourc_0; "No Route to source %x, %d"
0x18001e1e9  mov     r8d, [rsi]
0x18001e1ec  lea     rcx, [rbp+810h+var_840]
0x18001e1f0  mov     r9d, eax
0x18001e1f3  call    FormatRRASErrorString
0x18001e1f8  mov     rdx, cs:qword_18002B8A8
0x18001e1ff  lea     r8, [rbp+810h+var_840]
0x18001e203  mov     rcx, cs:gMgmEtwContext
0x18001e20a  mov     rax, cs:gMgmTemplateFunc
0x18001e211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e216  jmp     loc_18001E332
0x18001e21b  mov     rdx, [rsp+910h+DestInfo.DestHandle]; DestHandle
0x18001e220  lea     r8, [rsp+910h+OpaqueInfoPointer]; OpaqueInfoPointer
0x18001e225  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x18001e22c  mov     [rsp+910h+var_8E0], 1
0x18001e234  call    RtmGetOpaqueInformationPointer
0x18001e239  test    eax, eax
0x18001e23b  jz      short loc_18001E264
0x18001e23d  cmp     cs:qword_18002B8A8, r15
0x18001e244  jz      loc_18001E332
0x18001e24a  mov     r8d, eax
0x18001e24d  mov     word ptr [rbp+810h+var_840], r15w
0x18001e252  lea     rdx, aFailedToRetrie; "Failed to retrieve opaque pointer %x"
0x18001e259  lea     rcx, [rbp+810h+var_840]
0x18001e25d  call    FormatRRASErrorString
0x18001e262  jmp     short loc_18001E1F8
0x18001e264  mov     rax, [rsp+910h+OpaqueInfoPointer]
0x18001e269  mov     r14, [rax]
0x18001e26c  test    r14, r14
0x18001e26f  jz      loc_18001E319
0x18001e275  lea     rcx, [r14+10h]
0x18001e279  call    AcquireWriteLock
0x18001e27e  mov     edx, [rsi]
0x18001e280  lea     rax, [rsp+910h+lpMem]
0x18001e285  mov     r9d, [rsi+8]
0x18001e289  mov     rcx, r14
0x18001e28c  mov     [rsp+910h+var_8E8], rax
0x18001e291  call    FindRefEntry
0x18001e296  test    eax, eax
0x18001e298  jz      short loc_18001E2D0
0x18001e29a  mov     r8, [rsp+910h+lpMem]; lpMem
0x18001e29f  mov     rax, [r8]
0x18001e2a2  cmp     [rax+8], r8
0x18001e2a6  jnz     short loc_18001E2C9
0x18001e2a8  mov     rcx, [r8+8]
0x18001e2ac  cmp     [rcx], r8
0x18001e2af  jnz     short loc_18001E2C9
0x18001e2b1  mov     [rcx], rax
0x18001e2b4  xor     edx, edx; dwFlags
0x18001e2b6  mov     [rax+8], rcx
0x18001e2ba  mov     rcx, cs:hHeap; hHeap
0x18001e2c1  call    cs:__imp_HeapFree
0x18001e2c7  jmp     short loc_18001E310
0x18001e2c9  mov     ecx, 3
0x18001e2ce  int     29h; Win8: RtlFailFast(ecx)
0x18001e2d0  cmp     cs:qword_18002B8A8, r15
0x18001e2d7  jz      short loc_18001E310
0x18001e2d9  xor     eax, eax
0x18001e2db  lea     rdx, aReferenceDoesN; "Reference does not exist for source %x"
0x18001e2e2  mov     word ptr [rbp+810h+var_840], ax
0x18001e2e6  lea     rcx, [rbp+810h+var_840]
0x18001e2ea  mov     r8d, [rsi]
0x18001e2ed  call    FormatRRASErrorString
0x18001e2f2  mov     rdx, cs:qword_18002B8A8
0x18001e2f9  lea     r8, [rbp+810h+var_840]
0x18001e2fd  mov     rcx, cs:gMgmEtwContext
0x18001e304  mov     rax, cs:gMgmTemplateFunc
0x18001e30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e310  lea     rcx, [r14+10h]
0x18001e314  call    ReleaseWriteLock
0x18001e319  mov     rcx, cs:hHeap; hHeap
0x18001e320  mov     r8, rsi; lpMem
0x18001e323  xor     edx, edx; dwFlags
0x18001e325  call    cs:__imp_HeapFree
0x18001e32b  mov     [rbx+0A0h], r15
0x18001e332  mov     [rbx+98h], r15
0x18001e339  lea     rax, [rbx+30h]
0x18001e33d  cmp     [rax], rax
0x18001e340  jnz     short loc_18001E34D
0x18001e342  mov     rcx, rbx
0x18001e345  call    DeleteSourceEntry
0x18001e34a  dec     dword ptr [rdi+30h]
0x18001e34d  cmp     [rdi+30h], r15d
0x18001e351  jnz     loc_18001E07C
0x18001e357  mov     rcx, r12
0x18001e35a  call    ReleaseWriteLock
0x18001e35f  mov     rcx, rdi
0x18001e362  call    DeleteGroupEntry
0x18001e367  jmp     loc_18001E084
```
