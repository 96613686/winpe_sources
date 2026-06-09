# Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(ushort const *,_EVENT_TRACE_PROPERTIES const *,ushort const *,ulong,void *)

- ea: `0x18000e450`
- end: `0x18000e7f2`
- name: `?StartTraceW@CEtwPrivateLogger@Performance@Windows@Microsoft@@QEAAJPEBGPEBU_EVENT_TRACE_PROPERTIES@@0KPEAX@Z`
- size: `930`
- prototype: `__int64 __usercall@<rax>(PTRACEHANDLE TraceHandle@<rcx>, const unsigned __int16 *@<rdx>, const struct _EVENT_TRACE_PROPERTIES *@<r8>, const unsigned __int16 *@<r9>, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000bef8`

## callees

- `0x180001d66`
- `0x180008bf4`
- `0x18000abfc`
- `0x18000e450`
- `0x1800319ae`
- `0x1800319f0`

## import_xrefs

- `msvcrt!malloc` at `0x18000e5c2`
- `msvcrt!malloc` at `0x18000e5c2`
- `msvcrt!free` at `0x18000e74c`
- `msvcrt!free` at `0x18000e789`
- `msvcrt!free` at `0x18000e74c`
- `msvcrt!free` at `0x18000e789`
- `ole32!CoCreateGuid` at `0x18000e4f2`
- `ole32!CoCreateGuid` at `0x18000e6c6`
- `ole32!CoCreateGuid` at `0x18000e6e5`
- `ole32!CoCreateGuid` at `0x18000e4f2`
- `ole32!CoCreateGuid` at `0x18000e6c6`
- `ole32!CoCreateGuid` at `0x18000e6e5`
- `ole32!StringFromGUID2` at `0x18000e50d`
- `ole32!StringFromGUID2` at `0x18000e50d`
- `ADVAPI32!RegisterTraceGuidsW` at `0x18000e72c`
- `ADVAPI32!RegisterTraceGuidsW` at `0x18000e72c`
- `ADVAPI32!StartTraceW` at `0x18000e773`
- `ADVAPI32!StartTraceW` at `0x18000e773`
- `ADVAPI32!UnregisterTraceGuids` at `0x18000e79d`
- `ADVAPI32!UnregisterTraceGuids` at `0x18000e79d`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(
        PTRACEHANDLE TraceHandle,
        const unsigned __int16 *a2,
        const struct _EVENT_TRACE_PROPERTIES *a3,
        const unsigned __int16 *a4,
        unsigned int Size,
        void *a6)
{
  __int64 result; // rax
  __int64 v9; // r14
  OLECHAR *v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // r9
  unsigned int v13; // edi
  int v14; // ecx
  size_t v15; // r12
  unsigned __int64 v16; // rax
  unsigned int v17; // esi
  void *v18; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm2
  __int128 v21; // xmm3
  __int128 v22; // xmm4
  __int128 v23; // xmm5
  __int128 v24; // xmm6
  __int64 v25; // xmm7_8
  ULONG64 v26; // rax
  _WORD *v27; // rax
  _WORD *v28; // rcx
  HRESULT Guid; // edi
  ULONG64 v30; // rax
  ULONG v31; // eax
  ULONG started; // edi
  _QWORD pguid[3]; // [rsp+50h] [rbp-91h] BYREF
  OLECHAR sz[8]; // [rsp+68h] [rbp-79h] BYREF
  __int128 v36; // [rsp+78h] [rbp-69h]
  __int128 v37; // [rsp+88h] [rbp-59h]
  _OWORD v38[2]; // [rsp+98h] [rbp-49h]

  if ( Size && !a6 )
    return 2147942487LL;
  *(_OWORD *)sz = *(_OWORD *)L"{28ad2447-105b-4fe2-9599-e59b2aa9a634}";
  v37 = *(_OWORD *)L"fe2-9599-e59b2aa9a634}";
  v36 = *(_OWORD *)L"7-105b-4fe2-9599-e59b2aa9a634}";
  v38[0] = *(_OWORD *)L"-e59b2aa9a634}";
  *(_OWORD *)((char *)v38 + 14) = *(_OWORD *)L"a9a634}";
  *(_OWORD *)&pguid[1] = 0;
  CoCreateGuid((GUID *)&pguid[1]);
  StringFromGUID2((const GUID *const)&pguid[1], sz, 39);
  v9 = 1024;
  v10 = sz;
  v11 = 1024;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  result = v11 == 0 ? 0x80070057 : 0;
  v12 = (1024 - v11) & -(__int64)(v11 != 0);
  if ( !v11 )
    return result;
  if ( v12 > 0xFFFFFFFF )
    return 2147942934LL;
  v13 = Size + 120;
  if ( Size >= 0xFFFFFF88 )
    return 2147942934LL;
  if ( (v13 & 1) != 0 )
  {
    v14 = v13 & 1;
    if ( v13 - v14 + 2 >= v13 )
    {
      v13 = v13 - v14 + 2;
      goto LABEL_13;
    }
    return 2147942934LL;
  }
LABEL_13:
  v15 = (unsigned int)v12;
  v16 = 2LL * (unsigned int)v12;
  if ( v16 > 0xFFFFFFFF )
    return 2147942934LL;
  v17 = v16 + v13;
  if ( (unsigned int)v16 + v13 < v13 || v17 + 2048 < v17 )
    return 2147942934LL;
  pguid[1] = v17 + 2048;
  v18 = malloc(pguid[1]);
  TraceHandle[1] = (ULONG64)v18;
  if ( !v18 )
    return 2147942414LL;
  memset_0(v18, 0, pguid[1]);
  v19 = *(_OWORD *)&a3->Wnode.CountLost;
  v20 = *(_OWORD *)a3->Wnode.Guid.Data4;
  v21 = *(_OWORD *)&a3->BufferSize;
  v22 = *(_OWORD *)&a3->LogFileMode;
  v23 = *(_OWORD *)&a3->NumberOfBuffers;
  v24 = *(_OWORD *)&a3->LogBuffersLost;
  v25 = *(_QWORD *)&a3->LogFileNameOffset;
  v26 = TraceHandle[1];
  *(_OWORD *)v26 = *(_OWORD *)&a3->Wnode.BufferSize;
  *(_OWORD *)(v26 + 16) = v19;
  *(_OWORD *)(v26 + 32) = v20;
  *(_OWORD *)(v26 + 48) = v21;
  *(_OWORD *)(v26 + 64) = v22;
  *(_OWORD *)(v26 + 80) = v23;
  *(_OWORD *)(v26 + 96) = v24;
  *(_QWORD *)(v26 + 112) = v25;
  *(_DWORD *)TraceHandle[1] = v17 + 2048;
  *(_DWORD *)(TraceHandle[1] + 44) = 0x20000;
  *(_DWORD *)(TraceHandle[1] + 116) = v13;
  *(_DWORD *)(TraceHandle[1] + 112) = v17;
  if ( a6 )
    memcpy_0((void *)(TraceHandle[1] + 120), a6, Size);
  StringCchCopyNW((STRSAFE_LPWSTR)(TraceHandle[1] + v13), v15, sz, v15);
  v27 = (_WORD *)(TraceHandle[1] + v17);
  do
  {
    if ( !*a2 )
      break;
    *v27++ = *a2++;
    --v9;
  }
  while ( v9 );
  v28 = v27 - 1;
  if ( v9 )
    v28 = v27;
  *v28 = 0;
  Guid = CoCreateGuid((GUID *)TraceHandle + 2);
  if ( Guid < 0 || (Guid = CoCreateGuid((GUID *)TraceHandle + 3), Guid < 0) )
  {
    v30 = TraceHandle[1];
LABEL_29:
    free((void *)v30);
    result = (unsigned int)Guid;
    TraceHandle[1] = 0;
    return result;
  }
  TraceHandle[3] = 0;
  TraceHandle[2] = (ULONG64)(TraceHandle + 6);
  v31 = RegisterTraceGuidsW(
          Microsoft::Windows::Performance::CEtwPrivateLogger::ControlCallback,
          0,
          (LPCGUID)TraceHandle + 2,
          1u,
          (PTRACE_GUID_REGISTRATION)TraceHandle + 1,
          0,
          0,
          TraceHandle + 8);
  Guid = ATL::AtlHresultFromWin32(v31);
  v30 = TraceHandle[1];
  if ( Guid < 0 )
    goto LABEL_29;
  *(_OWORD *)(v30 + 24) = *((_OWORD *)TraceHandle + 2);
  started = StartTraceW(TraceHandle, sz, (PEVENT_TRACE_PROPERTIES)TraceHandle[1]);
  if ( started )
  {
    free((void *)TraceHandle[1]);
    TraceHandle[1] = 0;
    if ( !UnregisterTraceGuids(TraceHandle[8]) )
      TraceHandle[8] = -1;
  }
  return ATL::AtlHresultFromWin32(started);
}

```

## disassembly

```asm
0x18000e450  mov     rax, rsp
0x18000e453  push    rbp
0x18000e454  push    rbx
0x18000e455  push    rsi
0x18000e456  push    rdi
0x18000e457  push    r12
0x18000e459  push    r13
0x18000e45b  push    r14
0x18000e45d  push    r15
0x18000e45f  lea     rbp, [rax-4Fh]
0x18000e463  sub     rsp, 0E8h
0x18000e46a  movaps  xmmword ptr [rax-58h], xmm6
0x18000e46e  movaps  xmmword ptr [rax-68h], xmm7
0x18000e472  mov     rax, cs:__security_cookie
0x18000e479  xor     rax, rsp
0x18000e47c  mov     [rbp+47h+var_70], rax
0x18000e480  mov     r13d, dword ptr [rbp+47h+Size]
0x18000e484  xor     edi, edi
0x18000e486  mov     rax, [rbp+47h+arg_28]
0x18000e48a  mov     r15, rdx
0x18000e48d  mov     [rsp+120h+var_E0], r8
0x18000e492  mov     rbx, rcx
0x18000e495  mov     qword ptr [rsp+120h+pguid], rax
0x18000e49a  test    r13d, r13d
0x18000e49d  jz      short loc_18000E4AE
0x18000e49f  test    rax, rax
0x18000e4a2  jnz     short loc_18000E4AE
0x18000e4a4  mov     eax, 80070057h
0x18000e4a9  jmp     loc_18000E7C3
0x18000e4ae  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f; "{28ad2447-105b-4fe2-9599-e59b2aa9a634}"
0x18000e4b5  lea     rcx, [rsp+120h+pguid+8]; pguid
0x18000e4ba  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+10h; "7-105b-4fe2-9599-e59b2aa9a634}"
0x18000e4c1  movaps  xmmword ptr [rbp+47h+sz], xmm0
0x18000e4c5  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f+20h; "fe2-9599-e59b2aa9a634}"
0x18000e4cc  movaps  [rbp+47h+var_A0], xmm0
0x18000e4d0  movups  xmm0, xmmword ptr cs:a28ad2447105b4f+3Eh; "a9a634}"
0x18000e4d7  movaps  [rbp+47h+var_B0], xmm1
0x18000e4db  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+30h; "-e59b2aa9a634}"
0x18000e4e2  movaps  xmmword ptr [rbp+47h+var_90], xmm1
0x18000e4e6  movups  xmmword ptr [rbp+47h+var_90+0Eh], xmm0
0x18000e4ea  xorps   xmm0, xmm0
0x18000e4ed  movups  xmmword ptr [rsp+120h+pguid+8], xmm0
0x18000e4f2  call    cs:__imp_CoCreateGuid
0x18000e4f9  nop     dword ptr [rax+rax+00h]
0x18000e4fe  mov     r8d, 27h ; '''; cchMax
0x18000e504  lea     rdx, [rbp+47h+sz]; lpsz
0x18000e508  lea     rcx, [rsp+120h+pguid+8]; rguid
0x18000e50d  call    cs:__imp_StringFromGUID2
0x18000e514  nop     dword ptr [rax+rax+00h]
0x18000e519  mov     r14d, 400h
0x18000e51f  lea     rax, [rbp+47h+sz]
0x18000e523  mov     r8d, r14d
0x18000e526  cmp     [rax], di
0x18000e529  jz      short loc_18000E535
0x18000e52b  add     rax, 2
0x18000e52f  sub     r8, 1
0x18000e533  jnz     short loc_18000E526
0x18000e535  mov     rax, r8
0x18000e538  mov     rdx, r14
0x18000e53b  neg     rax
0x18000e53e  mov     rcx, r8
0x18000e541  sbb     eax, eax
0x18000e543  sub     rdx, r8
0x18000e546  not     eax
0x18000e548  and     eax, 80070057h
0x18000e54d  neg     rcx
0x18000e550  sbb     r9, r9
0x18000e553  and     r9, rdx
0x18000e556  test    r8, r8
0x18000e559  jz      loc_18000E7C3
0x18000e55f  mov     edx, 0FFFFFFFFh
0x18000e564  cmp     r9, rdx
0x18000e567  ja      loc_18000E7BE
0x18000e56d  lea     edi, [r13+78h]
0x18000e571  cmp     edi, 78h ; 'x'
0x18000e574  jb      loc_18000E7BE
0x18000e57a  mov     ecx, edi
0x18000e57c  and     ecx, 1
0x18000e57f  jz      short loc_18000E592
0x18000e581  mov     eax, edi
0x18000e583  sub     eax, ecx
0x18000e585  add     eax, 2
0x18000e588  cmp     eax, edi
0x18000e58a  jb      loc_18000E7BE
0x18000e590  mov     edi, eax
0x18000e592  mov     r12d, r9d
0x18000e595  lea     rax, [r12+r12]
0x18000e599  cmp     rax, rdx
0x18000e59c  ja      loc_18000E7BE
0x18000e5a2  lea     esi, [rax+rdi]
0x18000e5a5  cmp     esi, edi
0x18000e5a7  jb      loc_18000E7BE
0x18000e5ad  lea     eax, [rsi+800h]
0x18000e5b3  cmp     eax, esi
0x18000e5b5  jb      loc_18000E7BE
0x18000e5bb  mov     ecx, eax; Size
0x18000e5bd  mov     qword ptr [rsp+120h+pguid+8], rax
0x18000e5c2  call    cs:__imp_malloc
0x18000e5c9  nop     dword ptr [rax+rax+00h]
0x18000e5ce  mov     [rbx+8], rax
0x18000e5d2  test    rax, rax
0x18000e5d5  jnz     short loc_18000E5E1
0x18000e5d7  mov     eax, 8007000Eh
0x18000e5dc  jmp     loc_18000E7C3
0x18000e5e1  mov     r8, qword ptr [rsp+120h+pguid+8]; Size
0x18000e5e6  xor     edx, edx; Val
0x18000e5e8  mov     rcx, rax; void *
0x18000e5eb  call    memset_0
0x18000e5f0  mov     rax, [rsp+120h+var_E0]
0x18000e5f5  lea     ecx, [rsi+800h]
0x18000e5fb  mov     rdx, qword ptr [rsp+120h+pguid]; Src
0x18000e600  movaps  xmm0, xmmword ptr [rax]
0x18000e603  movaps  xmm1, xmmword ptr [rax+10h]
0x18000e607  movaps  xmm2, xmmword ptr [rax+20h]
0x18000e60b  movaps  xmm3, xmmword ptr [rax+30h]
0x18000e60f  movaps  xmm4, xmmword ptr [rax+40h]
0x18000e613  movaps  xmm5, xmmword ptr [rax+50h]
0x18000e617  movaps  xmm6, xmmword ptr [rax+60h]
0x18000e61b  movsd   xmm7, qword ptr [rax+70h]
0x18000e620  mov     rax, [rbx+8]
0x18000e624  movups  xmmword ptr [rax], xmm0
0x18000e627  movups  xmmword ptr [rax+10h], xmm1
0x18000e62b  movups  xmmword ptr [rax+20h], xmm2
0x18000e62f  movups  xmmword ptr [rax+30h], xmm3
0x18000e633  movups  xmmword ptr [rax+40h], xmm4
0x18000e637  movups  xmmword ptr [rax+50h], xmm5
0x18000e63b  movups  xmmword ptr [rax+60h], xmm6
0x18000e63f  movsd   qword ptr [rax+70h], xmm7
0x18000e644  mov     rax, [rbx+8]
0x18000e648  mov     [rax], ecx
0x18000e64a  mov     rax, [rbx+8]
0x18000e64e  mov     dword ptr [rax+2Ch], 20000h
0x18000e655  mov     rax, [rbx+8]
0x18000e659  mov     [rax+74h], edi
0x18000e65c  mov     rax, [rbx+8]
0x18000e660  mov     [rax+70h], esi
0x18000e663  test    rdx, rdx
0x18000e666  jz      short loc_18000E678
0x18000e668  mov     rcx, [rbx+8]
0x18000e66c  mov     r8, r13; Size
0x18000e66f  add     rcx, 78h ; 'x'; void *
0x18000e673  call    memcpy_0
0x18000e678  mov     ecx, edi
0x18000e67a  lea     r8, [rbp+47h+sz]; pszSrc
0x18000e67e  add     rcx, [rbx+8]; pszDest
0x18000e682  mov     r9, r12; cchToCopy
0x18000e685  mov     rdx, r12; cchDest
0x18000e688  call    StringCchCopyNW
0x18000e68d  mov     eax, esi
0x18000e68f  add     rax, [rbx+8]
0x18000e693  xor     r12d, r12d
0x18000e696  movzx   ecx, word ptr [r15]
0x18000e69a  test    cx, cx
0x18000e69d  jz      short loc_18000E6B0
0x18000e69f  mov     [rax], cx
0x18000e6a2  add     r15, 2
0x18000e6a6  add     rax, 2
0x18000e6aa  sub     r14, 1
0x18000e6ae  jnz     short loc_18000E696
0x18000e6b0  lea     rcx, [rax-2]
0x18000e6b4  test    r14, r14
0x18000e6b7  lea     rsi, [rbx+20h]
0x18000e6bb  cmovnz  rcx, rax
0x18000e6bf  mov     [rcx], r12w
0x18000e6c3  mov     rcx, rsi; pguid
0x18000e6c6  call    cs:__imp_CoCreateGuid
0x18000e6cd  nop     dword ptr [rax+rax+00h]
0x18000e6d2  mov     edi, eax
0x18000e6d4  test    eax, eax
0x18000e6d6  jns     short loc_18000E6DE
0x18000e6d8  mov     rax, [rbx+8]
0x18000e6dc  jmp     short loc_18000E749
0x18000e6de  lea     r14, [rbx+30h]
0x18000e6e2  mov     rcx, r14; pguid
0x18000e6e5  call    cs:__imp_CoCreateGuid
0x18000e6ec  nop     dword ptr [rax+rax+00h]
0x18000e6f1  mov     edi, eax
0x18000e6f3  test    eax, eax
0x18000e6f5  js      short loc_18000E6D8
0x18000e6f7  lea     rcx, [rbx+10h]
0x18000e6fb  mov     [rbx+18h], r12
0x18000e6ff  lea     rax, [rbx+40h]
0x18000e703  mov     [rcx], r14
0x18000e706  mov     [rsp+120h+RegistrationHandle], rax; RegistrationHandle
0x18000e70b  mov     r9d, 1; GuidCount
0x18000e711  mov     [rsp+120h+MofResourceName], r12; MofResourceName
0x18000e716  mov     r8, rsi; ControlGuid
0x18000e719  mov     [rsp+120h+MofImagePath], r12; MofImagePath
0x18000e71e  xor     edx, edx; RequestContext
0x18000e720  mov     [rsp+120h+TraceGuidReg], rcx; TraceGuidReg
0x18000e725  lea     rcx, ?ControlCallback@CEtwPrivateLogger@Performance@Windows@Microsoft@@CAKW4WMIDPREQUESTCODE@@PEAXPEAK1@Z; RequestAddress
0x18000e72c  call    cs:__imp_RegisterTraceGuidsW
0x18000e733  nop     dword ptr [rax+rax+00h]
0x18000e738  mov     ecx, eax; unsigned int
0x18000e73a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000e73f  mov     edi, eax
0x18000e741  mov     rax, [rbx+8]
0x18000e745  test    edi, edi
0x18000e747  jns     short loc_18000E760
0x18000e749  mov     rcx, rax; Block
0x18000e74c  call    cs:__imp_free
0x18000e753  nop     dword ptr [rax+rax+00h]
0x18000e758  mov     eax, edi
0x18000e75a  mov     [rbx+8], r12
0x18000e75e  jmp     short loc_18000E7C3
0x18000e760  movups  xmm0, xmmword ptr [rsi]
0x18000e763  lea     rdx, [rbp+47h+sz]; InstanceName
0x18000e767  mov     rcx, rbx; TraceHandle
0x18000e76a  movdqu  xmmword ptr [rax+18h], xmm0
0x18000e76f  mov     r8, [rbx+8]; Properties
0x18000e773  call    cs:__imp_StartTraceW
0x18000e77a  nop     dword ptr [rax+rax+00h]
0x18000e77f  mov     edi, eax
0x18000e781  test    eax, eax
0x18000e783  jz      short loc_18000E7B5
0x18000e785  mov     rcx, [rbx+8]; Block
0x18000e789  call    cs:__imp_free
0x18000e790  nop     dword ptr [rax+rax+00h]
0x18000e795  mov     [rbx+8], r12
0x18000e799  mov     rcx, [rbx+40h]; RegistrationHandle
0x18000e79d  call    cs:__imp_UnregisterTraceGuids
0x18000e7a4  nop     dword ptr [rax+rax+00h]
0x18000e7a9  test    eax, eax
0x18000e7ab  jnz     short loc_18000E7B5
0x18000e7ad  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x18000e7b5  mov     ecx, edi; unsigned int
0x18000e7b7  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000e7bc  jmp     short loc_18000E7C3
0x18000e7be  mov     eax, 80070216h
0x18000e7c3  mov     rcx, [rbp+47h+var_70]
0x18000e7c7  xor     rcx, rsp; StackCookie
0x18000e7ca  call    __security_check_cookie
0x18000e7cf  lea     r11, [rsp+120h+var_38]
0x18000e7d7  movaps  xmm6, xmmword ptr [r11-18h]
0x18000e7dc  movaps  xmm7, xmmword ptr [r11-28h]
0x18000e7e1  mov     rsp, r11
0x18000e7e4  pop     r15
0x18000e7e6  pop     r14
0x18000e7e8  pop     r13
0x18000e7ea  pop     r12
0x18000e7ec  pop     rdi
0x18000e7ed  pop     rsi
0x18000e7ee  pop     rbx
0x18000e7ef  pop     rbp
0x18000e7f0  retn
```
