# ScCreateImageRecord(_IMAGE_RECORD * *,ushort const *,ushort const *,ushort const *,ulong,void *,void *,void *,ulong,_SC_SERVICE_CHANNEL_CONTEXT *,ulong,ulong,unsigned __int64,void *)

- ea: `0x1400703f4`
- end: `0x140070697`
- name: `?ScCreateImageRecord@@YAKPEAPEAU_IMAGE_RECORD@@PEBG11KPEAX22KPEAU_SC_SERVICE_CHANNEL_CONTEXT@@KK_K2@Z`
- size: `675`
- prototype: `unsigned int(struct _IMAGE_RECORD **, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, void *, void *, unsigned int, struct _SC_SERVICE_CHANNEL_CONTEXT *, unsigned int, unsigned int, unsigned __int64, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003ae4c`
- `0x14007a510`

## callees

- `0x140004c58`
- `0x14000cee0`
- `0x14001f99c`
- `0x1400575b0`
- `0x1400703f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400705c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400705c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400705b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400705b7`
- `ntdll!RtlAcquireResourceExclusive` at `0x14007062d`
- `ntdll!RtlAcquireResourceExclusive` at `0x14007062d`
- `ntdll!RtlReleaseResource` at `0x140070668`
- `ntdll!RtlReleaseResource` at `0x140070668`
- `ntdll!RtlFreeHeap` at `0x14007060d`
- `ntdll!RtlFreeHeap` at `0x14007060d`
- `ntdll!RtlCopyLuid` at `0x140070592`
- `ntdll!RtlCopyLuid` at `0x140070592`
- `ntdll!RtlAllocateHeap` at `0x14007048f`
- `ntdll!RtlAllocateHeap` at `0x14007048f`

## pseudocode

```c
__int64 __fastcall ScCreateImageRecord(
        struct _IMAGE_RECORD **a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        void *a6,
        HANDLE TokenHandle,
        void *a8,
        unsigned int a9,
        struct _SC_SERVICE_CHANNEL_CONTEXT *a10,
        unsigned int a11,
        unsigned int a12,
        unsigned __int64 a13,
        void *a14)
{
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned int v19; // r14d
  int v20; // edi
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v22; // rbx
  __int64 v24; // r10
  __int64 v25; // r11
  __int64 v26; // r10
  DWORD LastError; // eax
  __int64 v28; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-50h] BYREF
  struct _LUID SourceLuid; // [rsp+38h] [rbp-48h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v32; // [rsp+70h] [rbp-10h]

  v32 = 0;
  v17 = -1;
  ReturnLength = 0;
  v18 = -1;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  do
    ++v18;
  while ( a2[v18] );
  v19 = 2 * v18 + 2;
  if ( a4 )
  {
    do
      ++v17;
    while ( a4[v17] );
    v20 = 2 * v17 + 138;
  }
  else
  {
    v20 = 136;
  }
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v19 + v20);
  v22 = Heap;
  if ( !Heap )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 14, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids);
    return 8;
  }
  *(_DWORD *)Heap = 909206355;
  StringCbCopyW(Heap + 68, v19, a2);
  *((_QWORD *)v22 + 3) = v24;
  *((_QWORD *)v22 + 4) = 0;
  if ( a4 )
    StringCbCopyW((unsigned __int16 *)(v25 + v24), (unsigned int)(v20 - 136), a4);
  else
    v26 = 0;
  *((_QWORD *)v22 + 11) = v26;
  *((_DWORD *)v22 + 10) = a5;
  *((_QWORD *)v22 + 6) = a6;
  *((_QWORD *)v22 + 10) = a8;
  *((_QWORD *)v22 + 7) = a14;
  *((_DWORD *)v22 + 26) = a9;
  *((_QWORD *)v22 + 12) = a10;
  *((_DWORD *)v22 + 27) = a11;
  *((_QWORD *)v22 + 15) = a13;
  *((_QWORD *)v22 + 2) = 0;
  *((_DWORD *)v22 + 11) = 1;
  *((_QWORD *)v22 + 8) = TokenHandle;
  *((_DWORD *)v22 + 32) = 0;
  if ( !TokenHandle )
  {
    SourceLuid = (struct _LUID)999LL;
    RtlCopyLuid((PLUID)v22 + 9, &SourceLuid);
LABEL_23:
    RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
    *((_QWORD *)v22 + 2) = qword_1400BC300;
    *((_QWORD *)v22 + 1) = &ImageDatabase;
    qword_1400BC300 = (struct _IMAGE_RECORD *)v22;
    v28 = *((_QWORD *)v22 + 2);
    if ( v28 )
      *(_QWORD *)(v28 + 8) = v22;
    *a1 = (struct _IMAGE_RECORD *)v22;
    RtlReleaseResource(&ScServiceRecordLock);
    return 0;
  }
  if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
  {
    *((_QWORD *)v22 + 9) = *((_QWORD *)&TokenInformation[0] + 1);
    goto LABEL_23;
  }
  LastError = GetLastError();
  ReturnLength = LastError;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 15, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, LastError);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
  return ReturnLength;
}

```

## disassembly

```asm
0x1400703f4  mov     [rsp-38h+arg_10], rbx
0x1400703f9  push    rbp
0x1400703fa  push    rsi
0x1400703fb  push    rdi
0x1400703fc  push    r12
0x1400703fe  push    r13
0x140070400  push    r14
0x140070402  push    r15
0x140070404  mov     rbp, rsp
0x140070407  sub     rsp, 80h
0x14007040e  mov     rax, cs:__security_cookie
0x140070415  xor     rax, rsp
0x140070418  mov     [rbp+var_8], rax
0x14007041c  mov     r12, [rbp+TokenHandle]
0x140070420  xor     eax, eax
0x140070422  xorps   xmm0, xmm0
0x140070425  mov     [rbp+var_10], rax
0x140070429  mov     r15, rdx
0x14007042c  mov     r13, rcx
0x14007042f  xor     edx, edx
0x140070431  mov     rsi, r9
0x140070434  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140070438  mov     [rbp+var_50], edx
0x14007043b  mov     rax, rcx
0x14007043e  movups  [rbp+TokenInformation], xmm0
0x140070442  movups  [rbp+var_30], xmm0
0x140070446  movups  [rbp+var_20], xmm0
0x14007044a  inc     rax
0x14007044d  cmp     [r15+rax*2], dx
0x140070452  jnz     short loc_14007044A
0x140070454  lea     r14d, ds:2[rax*2]
0x14007045c  test    rsi, rsi
0x14007045f  jz      short loc_140070474
0x140070461  inc     rcx
0x140070464  cmp     [r9+rcx*2], dx
0x140070469  jnz     short loc_140070461
0x14007046b  lea     edi, ds:8Ah[rcx*2]
0x140070472  jmp     short loc_140070479
0x140070474  mov     edi, 88h
0x140070479  mov     rcx, gs:60h
0x140070482  lea     r8d, [r14+rdi]; Size
0x140070486  mov     edx, 8; Flags
0x14007048b  mov     rcx, [rcx+30h]; HeapHandle
0x14007048f  call    cs:__imp_RtlAllocateHeap
0x140070495  mov     rbx, rax
0x140070498  test    rax, rax
0x14007049b  jnz     short loc_1400704D3
0x14007049d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400704a4  lea     rdx, WPP_GLOBAL_Control
0x1400704ab  cmp     rcx, rdx
0x1400704ae  jz      short loc_1400704C9
0x1400704b0  test    byte ptr [rcx+1Ch], 4
0x1400704b4  jz      short loc_1400704C9
0x1400704b6  mov     rcx, [rcx+10h]
0x1400704ba  lea     edx, [rax+0Eh]
0x1400704bd  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x1400704c4  call    WPP_SF_
0x1400704c9  mov     eax, 8
0x1400704ce  jmp     loc_140070670
0x1400704d3  lea     r10, [rax+88h]
0x1400704da  mov     edx, r14d; unsigned __int64
0x1400704dd  mov     rcx, r10; unsigned __int16 *
0x1400704e0  mov     dword ptr [rax], 36316353h
0x1400704e6  mov     r8, r15; unsigned __int16 *
0x1400704e9  mov     r11d, r14d
0x1400704ec  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400704f1  xor     r14d, r14d
0x1400704f4  mov     [rbx+18h], r10
0x1400704f8  mov     [rbx+20h], r14
0x1400704fc  test    rsi, rsi
0x1400704ff  jz      short loc_140070517
0x140070501  add     r10, r11
0x140070504  lea     edx, [rdi-88h]; unsigned __int64
0x14007050a  mov     rcx, r10; unsigned __int16 *
0x14007050d  mov     r8, rsi; unsigned __int16 *
0x140070510  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140070515  jmp     short loc_14007051A
0x140070517  mov     r10, r14
0x14007051a  mov     eax, [rbp+arg_20]
0x14007051d  mov     [rbx+58h], r10
0x140070521  mov     [rbx+28h], eax
0x140070524  mov     rax, [rbp+arg_28]
0x140070528  mov     [rbx+30h], rax
0x14007052c  mov     rax, [rbp+arg_38]
0x140070530  mov     [rbx+50h], rax
0x140070534  mov     rax, [rbp+arg_68]
0x14007053b  mov     [rbx+38h], rax
0x14007053f  mov     eax, [rbp+arg_40]
0x140070545  mov     [rbx+68h], eax
0x140070548  mov     rax, [rbp+arg_48]
0x14007054f  mov     [rbx+60h], rax
0x140070553  mov     eax, [rbp+arg_50]
0x140070559  mov     [rbx+6Ch], eax
0x14007055c  mov     rax, [rbp+arg_60]
0x140070563  mov     [rbx+78h], rax
0x140070567  mov     [rbx+10h], r14
0x14007056b  mov     dword ptr [rbx+2Ch], 1
0x140070572  mov     [rbx+40h], r12
0x140070576  mov     [rbx+80h], r14d
0x14007057d  test    r12, r12
0x140070580  jnz     short loc_14007059D
0x140070582  lea     rcx, [rbx+48h]; DestinationLuid
0x140070586  mov     qword ptr [rbp+SourceLuid.LowPart], 3E7h
0x14007058e  lea     rdx, [rbp+SourceLuid]; SourceLuid
0x140070592  call    cs:__imp_RtlCopyLuid
0x140070598  jmp     loc_140070624
0x14007059d  mov     r9d, 38h ; '8'; TokenInformationLength
0x1400705a3  lea     rax, [rbp+var_50]
0x1400705a7  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400705ab  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1400705b0  mov     rcx, r12; TokenHandle
0x1400705b3  lea     edx, [r9-2Eh]; TokenInformationClass
0x1400705b7  call    cs:__imp_GetTokenInformation
0x1400705bd  test    eax, eax
0x1400705bf  jnz     short loc_140070618
0x1400705c1  call    cs:__imp_GetLastError
0x1400705c7  mov     [rbp+var_50], eax
0x1400705ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400705d1  lea     rdx, WPP_GLOBAL_Control
0x1400705d8  cmp     rcx, rdx
0x1400705db  jz      short loc_1400705FB
0x1400705dd  test    byte ptr [rcx+1Ch], 1
0x1400705e1  jz      short loc_1400705FB
0x1400705e3  mov     rcx, [rcx+10h]
0x1400705e7  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x1400705ee  mov     edx, 0Fh
0x1400705f3  mov     r9d, eax
0x1400705f6  call    WPP_SF_d
0x1400705fb  mov     rcx, gs:60h
0x140070604  mov     r8, rbx; P
0x140070607  xor     edx, edx; Flags
0x140070609  mov     rcx, [rcx+30h]; HeapHandle
0x14007060d  call    cs:__imp_RtlFreeHeap
0x140070613  mov     eax, [rbp+var_50]
0x140070616  jmp     short loc_140070670
0x140070618  mov     eax, dword ptr [rbp+TokenInformation+8]
0x14007061b  mov     [rbx+48h], eax
0x14007061e  mov     eax, dword ptr [rbp+TokenInformation+0Ch]
0x140070621  mov     [rbx+4Ch], eax
0x140070624  mov     dl, 1; Wait
0x140070626  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14007062d  call    cs:__imp_RtlAcquireResourceExclusive
0x140070633  mov     rax, cs:qword_1400BC300
0x14007063a  mov     [rbx+10h], rax
0x14007063e  lea     rax, ?ImageDatabase@@3U_IMAGE_RECORD@@A; _IMAGE_RECORD ImageDatabase
0x140070645  mov     [rbx+8], rax
0x140070649  mov     cs:qword_1400BC300, rbx
0x140070650  mov     rax, [rbx+10h]
0x140070654  test    rax, rax
0x140070657  jz      short loc_14007065D
0x140070659  mov     [rax+8], rbx
0x14007065d  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140070664  mov     [r13+0], rbx
0x140070668  call    cs:__imp_RtlReleaseResource
0x14007066e  xor     eax, eax
0x140070670  mov     rcx, [rbp+var_8]
0x140070674  xor     rcx, rsp; StackCookie
0x140070677  call    __security_check_cookie
0x14007067c  mov     rbx, [rsp+80h+arg_10]
0x140070684  add     rsp, 80h
0x14007068b  pop     r15
0x14007068d  pop     r14
0x14007068f  pop     r13
0x140070691  pop     r12
0x140070693  pop     rdi
0x140070694  pop     rsi
0x140070695  pop     rbp
0x140070696  retn
```
