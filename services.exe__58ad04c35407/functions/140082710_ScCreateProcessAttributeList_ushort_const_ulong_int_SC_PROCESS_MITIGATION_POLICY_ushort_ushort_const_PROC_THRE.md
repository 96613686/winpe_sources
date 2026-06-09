# ScCreateProcessAttributeList(ushort const *,ulong,int,_SC_PROCESS_MITIGATION_POLICY *,ushort,ushort const *,_PROC_THREAD_ATTRIBUTE_LIST * *)

- ea: `0x140082710`
- end: `0x140082bc8`
- name: `?ScCreateProcessAttributeList@@YAKPEBGKHPEAU_SC_PROCESS_MITIGATION_POLICY@@G0PEAPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z`
- size: `1208`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, int, struct _SC_PROCESS_MITIGATION_POLICY *, unsigned __int16, PVOID lpValue, struct _PROC_THREAD_ATTRIBUTE_LIST **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14003ae4c`

## callees

- `0x140003e54`
- `0x1400188fc`
- `0x140082710`
- `0x140083a78`
- `0x140083b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400827f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400828d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008294a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400829c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140082a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140082ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140082b49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400827f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400828d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008294a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400829c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140082a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140082ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140082b49`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x140082b83`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x140082b83`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400828cd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140082940`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400829b6`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140082a28`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140082aa9`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140082b3f`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400828cd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140082940`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400829b6`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140082a28`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140082aa9`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140082b3f`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400827e9`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400827e9`
- `ntdll!RtlFreeHeap` at `0x140082b9b`
- `ntdll!RtlFreeHeap` at `0x140082b9b`
- `ntdll!RtlAllocateHeap` at `0x1400827bb`
- `ntdll!RtlAllocateHeap` at `0x1400827bb`

## pseudocode

```c
__int64 __fastcall ScCreateProcessAttributeList(
        const unsigned __int16 *a1,
        unsigned int a2,
        int a3,
        struct _SC_PROCESS_MITIGATION_POLICY *a4,
        unsigned __int16 a5,
        _WORD *lpValue,
        struct _PROC_THREAD_ATTRIBUTE_LIST **a7)
{
  unsigned __int16 v7; // r13
  __int64 v8; // r12
  int v11; // r10d
  int v12; // ecx
  DWORD v13; // eax
  DWORD v14; // r14d
  unsigned int v15; // ebx
  struct _PROC_THREAD_ATTRIBUTE_LIST *Heap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v17; // rsi
  ULONG_PTR v18; // rdi
  DWORD LastError; // eax
  DWORD v20; // eax
  PRPC_ASYNC_STATE v21; // rcx
  int v22; // edx
  __int64 v23; // rax
  DWORD v24; // eax
  int v25; // r8d
  DWORD v26; // eax
  int v27; // r8d
  ULONG_PTR Size; // [rsp+98h] [rbp+20h] BYREF

  v7 = a5;
  v8 = a2;
  v11 = (a2 != 0) + 1;
  if ( !a5 )
    v11 = a2 != 0;
  v12 = v11 + 1;
  if ( !lpValue )
    v12 = v11;
  if ( *(_QWORD *)a4 || *((_QWORD *)a4 + 1) )
    ++v12;
  v13 = v12 + 1;
  if ( !*((_DWORD *)a4 + 4) )
    v13 = v12;
  v14 = v13 + 1;
  if ( a3 != 1 )
    v14 = v13;
  if ( v14 )
  {
    v15 = 8;
    Size = 24 * (v14 + 1);
    Heap = (struct _PROC_THREAD_ATTRIBUTE_LIST *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size + 40);
    v17 = Heap;
    if ( !Heap )
      return v15;
    v18 = (ULONG_PTR)Heap + Size;
    v15 = 0;
    if ( !InitializeProcThreadAttributeList(Heap, v14, 0, &Size) )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          46,
          (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
          (_DWORD)a1,
          LastError);
      goto LABEL_62;
    }
    if ( !(_DWORD)v8 )
      goto LABEL_67;
    if ( (_DWORD)v8 != 1 && (_DWORD)v8 != 2 && (unsigned int)(v8 - 3) >= 2 )
    {
      v15 = 87;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 47, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, a1);
      goto LABEL_61;
    }
    if ( UpdateProcThreadAttribute(v17, 0, 0x2000Bu, &dword_1400BAF04[3 * v8], 4u, 0, 0) )
    {
LABEL_67:
      if ( !v7
        || (*(_WORD *)(v18 + 32) = v7 - 1, UpdateProcThreadAttribute(v17, 0, 0x20004u, (PVOID)(v18 + 32), 2u, 0, 0)) )
      {
        if ( !lpValue )
          goto LABEL_42;
        v23 = -1;
        do
          ++v23;
        while ( lpValue[v23] );
        if ( UpdateProcThreadAttribute(v17, 0, 0x20008u, lpValue, 2 * v23, 0, 0) )
        {
LABEL_42:
          *(_OWORD *)v18 = *(_OWORD *)a4;
          if ( (*(_QWORD *)v18 || *(_QWORD *)(v18 + 8))
            && !UpdateProcThreadAttribute(v17, 0, 0x20007u, (PVOID)v18, 0x10u, 0, 0) )
          {
            v24 = GetLastError();
            v15 = v24;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_iiSD(
                WPP_GLOBAL_Control->StubInfo,
                (unsigned int)&WPP_GLOBAL_Control,
                v25,
                *(_QWORD *)(v18 + 8),
                *(_QWORD *)v18,
                (__int64)a1,
                v24);
            }
            goto LABEL_61;
          }
          if ( !*((_DWORD *)a4 + 4)
            || (*(_DWORD *)(v18 + 36) = 1, UpdateProcThreadAttribute(v17, 0, 0x2000Eu, (PVOID)(v18 + 36), 4u, 0, 0)) )
          {
            *(_OWORD *)(v18 + 16) = 0;
            if ( a3 )
              *(_QWORD *)(v18 + 24) |= 0x110000000uLL;
            if ( !*(_QWORD *)(v18 + 24) || UpdateProcThreadAttribute(v17, 0, 0x20018u, (PVOID)(v18 + 16), 0x10u, 0, 0) )
            {
              *a7 = v17;
              return v15;
            }
            v26 = GetLastError();
            v15 = v26;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_iSD(
                WPP_GLOBAL_Control->StubInfo,
                (unsigned int)&WPP_GLOBAL_Control,
                v27,
                *(_QWORD *)(v18 + 24),
                (__int64)a1,
                v26);
            }
            goto LABEL_61;
          }
          v20 = GetLastError();
          v15 = v20;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
LABEL_61:
            DeleteProcThreadAttributeList(v17);
LABEL_62:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
            return v15;
          }
          v22 = 52;
        }
        else
        {
          v20 = GetLastError();
          v15 = v20;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_61;
          }
          v22 = 50;
        }
      }
      else
      {
        v20 = GetLastError();
        v15 = v20;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_61;
        }
        v22 = 49;
      }
    }
    else
    {
      v20 = GetLastError();
      v15 = v20;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_61;
      v22 = 48;
    }
    WPP_SF_Sd(v21->StubInfo, v22, (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, (_DWORD)a1, v20);
    goto LABEL_61;
  }
  return 0;
}

```

## disassembly

```asm
0x140082710  mov     [rsp+arg_0], rbx
0x140082715  mov     [rsp+arg_10], r8d
0x14008271a  push    rbp
0x14008271b  push    rsi
0x14008271c  push    rdi
0x14008271d  push    r12
0x14008271f  push    r13
0x140082721  push    r14
0x140082723  push    r15
0x140082725  sub     rsp, 40h
0x140082729  movzx   r13d, [rsp+78h+arg_20]
0x140082732  xor     edi, edi
0x140082734  test    edx, edx
0x140082736  mov     r12d, edx
0x140082739  mov     eax, edi
0x14008273b  mov     rbp, rcx
0x14008273e  setnz   al
0x140082741  mov     r15, r9
0x140082744  test    r13w, r13w
0x140082748  lea     r10d, [rax+1]
0x14008274c  cmovz   r10d, eax
0x140082750  cmp     [rsp+78h+lpValue], rdi
0x140082758  lea     ecx, [r10+1]
0x14008275c  cmovz   ecx, r10d
0x140082760  cmp     [r9], rdi
0x140082763  jnz     short loc_14008276B
0x140082765  cmp     [r9+8], rdi
0x140082769  jz      short loc_14008276D
0x14008276b  inc     ecx
0x14008276d  cmp     [r9+10h], edi
0x140082771  lea     eax, [rcx+1]
0x140082774  cmovz   eax, ecx
0x140082777  cmp     r8d, 1
0x14008277b  lea     r14d, [rax+1]
0x14008277f  cmovnz  r14d, eax
0x140082783  test    r14d, r14d
0x140082786  jnz     short loc_14008278F
0x140082788  mov     ebx, edi
0x14008278a  jmp     loc_140082BAE
0x14008278f  lea     eax, [r14+1]
0x140082793  mov     ebx, 8
0x140082798  lea     r8d, [rax+rax*2]
0x14008279c  mov     edx, ebx; Flags
0x14008279e  shl     r8d, 3
0x1400827a2  mov     [rsp+78h+Size], r8
0x1400827aa  add     r8, 28h ; '('; Size
0x1400827ae  mov     rcx, gs:60h
0x1400827b7  mov     rcx, [rcx+30h]; HeapHandle
0x1400827bb  call    cs:__imp_RtlAllocateHeap
0x1400827c1  mov     rsi, rax
0x1400827c4  test    rax, rax
0x1400827c7  jz      loc_140082BAE
0x1400827cd  mov     rdi, [rsp+78h+Size]
0x1400827d5  lea     r9, [rsp+78h+Size]; lpSize
0x1400827dd  xor     r8d, r8d; dwFlags
0x1400827e0  mov     edx, r14d; dwAttributeCount
0x1400827e3  mov     rcx, rax; lpAttributeList
0x1400827e6  add     rdi, rax
0x1400827e9  call    cs:__imp_InitializeProcThreadAttributeList
0x1400827ef  xor     ebx, ebx
0x1400827f1  test    eax, eax
0x1400827f3  jnz     short loc_14008283F
0x1400827f5  call    cs:__imp_GetLastError
0x1400827fb  mov     ebx, eax
0x1400827fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140082804  lea     rdx, WPP_GLOBAL_Control
0x14008280b  cmp     rcx, rdx
0x14008280e  jz      loc_140082B89
0x140082814  test    byte ptr [rcx+1Ch], 1
0x140082818  jz      loc_140082B89
0x14008281e  mov     rcx, [rcx+10h]
0x140082822  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x140082829  mov     edx, 2Eh ; '.'
0x14008282e  mov     dword ptr [rsp+78h+cbSize], eax
0x140082832  mov     r9, rbp
0x140082835  call    WPP_SF_Sd
0x14008283a  jmp     loc_140082B89
0x14008283f  test    r12d, r12d
0x140082842  jz      loc_14008290A
0x140082848  mov     eax, r12d
0x14008284b  sub     eax, 1
0x14008284e  jz      short loc_1400828A0
0x140082850  sub     eax, 1
0x140082853  jz      short loc_1400828A0
0x140082855  sub     eax, 1
0x140082858  jz      short loc_1400828A0
0x14008285a  cmp     eax, 1
0x14008285d  jz      short loc_1400828A0
0x14008285f  mov     ebx, 57h ; 'W'
0x140082864  mov     rcx, cs:WPP_GLOBAL_Control
0x14008286b  lea     rdx, WPP_GLOBAL_Control
0x140082872  cmp     rcx, rdx
0x140082875  jz      loc_140082B80
0x14008287b  test    byte ptr [rcx+1Ch], 1
0x14008287f  jz      loc_140082B80
0x140082885  mov     rcx, [rcx+10h]
0x140082889  lea     edx, [rbx-28h]
0x14008288c  mov     r9, rbp
0x14008288f  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x140082896  call    WPP_SF_S
0x14008289b  jmp     loc_140082B80
0x1400828a0  lea     rcx, [r12+r12*2]
0x1400828a4  mov     [rsp+78h+lpReturnSize], rbx; lpReturnSize
0x1400828a9  lea     rax, dword_1400BAF04
0x1400828b0  mov     [rsp+78h+lpPreviousValue], rbx; lpPreviousValue
0x1400828b5  lea     r9, [rax+rcx*4]; lpValue
0x1400828b9  mov     [rsp+78h+cbSize], 4; cbSize
0x1400828c2  mov     rcx, rsi; lpAttributeList
0x1400828c5  xor     edx, edx; dwFlags
0x1400828c7  mov     r8d, 2000Bh; Attribute
0x1400828cd  call    cs:__imp_UpdateProcThreadAttribute
0x1400828d3  test    eax, eax
0x1400828d5  jnz     short loc_14008290A
0x1400828d7  call    cs:__imp_GetLastError
0x1400828dd  mov     ebx, eax
0x1400828df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400828e6  lea     rdx, WPP_GLOBAL_Control
0x1400828ed  cmp     rcx, rdx
0x1400828f0  jz      loc_140082B80
0x1400828f6  test    byte ptr [rcx+1Ch], 1
0x1400828fa  jz      loc_140082B80
0x140082900  mov     edx, 30h ; '0'
0x140082905  jmp     loc_140082AE1
0x14008290a  mov     r14d, 1
0x140082910  test    r13w, r13w
0x140082914  jz      short loc_14008297C
0x140082916  lea     r9, [rdi+20h]; lpValue
0x14008291a  mov     [rsp+78h+lpReturnSize], rbx; lpReturnSize
0x14008291f  sub     r13w, r14w
0x140082923  mov     [rsp+78h+lpPreviousValue], rbx; lpPreviousValue
0x140082928  xor     edx, edx; dwFlags
0x14008292a  mov     [r9], r13w
0x14008292e  mov     r8d, 20004h; Attribute
0x140082934  mov     [rsp+78h+cbSize], 2; cbSize
0x14008293d  mov     rcx, rsi; lpAttributeList
0x140082940  call    cs:__imp_UpdateProcThreadAttribute
0x140082946  test    eax, eax
0x140082948  jnz     short loc_14008297C
0x14008294a  call    cs:__imp_GetLastError
0x140082950  mov     ebx, eax
0x140082952  mov     rcx, cs:WPP_GLOBAL_Control
0x140082959  lea     rdx, WPP_GLOBAL_Control
0x140082960  cmp     rcx, rdx
0x140082963  jz      loc_140082B80
0x140082969  test    [rcx+1Ch], r14b
0x14008296d  jz      loc_140082B80
0x140082973  lea     edx, [r14+30h]
0x140082977  jmp     loc_140082AE1
0x14008297c  mov     rcx, [rsp+78h+lpValue]
0x140082984  test    rcx, rcx
0x140082987  jz      short loc_1400829F3
0x140082989  or      rax, 0FFFFFFFFFFFFFFFFh
0x14008298d  inc     rax
0x140082990  cmp     [rcx+rax*2], bx
0x140082994  jnz     short loc_14008298D
0x140082996  add     rax, rax
0x140082999  mov     [rsp+78h+lpReturnSize], rbx; lpReturnSize
0x14008299e  mov     r9, rcx; lpValue
0x1400829a1  mov     [rsp+78h+lpPreviousValue], rbx; lpPreviousValue
0x1400829a6  mov     rcx, rsi; lpAttributeList
0x1400829a9  mov     [rsp+78h+cbSize], rax; cbSize
0x1400829ae  xor     edx, edx; dwFlags
0x1400829b0  mov     r8d, 20008h; Attribute
0x1400829b6  call    cs:__imp_UpdateProcThreadAttribute
0x1400829bc  test    eax, eax
0x1400829be  jnz     short loc_1400829F3
0x1400829c0  call    cs:__imp_GetLastError
0x1400829c6  mov     ebx, eax
0x1400829c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400829cf  lea     rdx, WPP_GLOBAL_Control
0x1400829d6  cmp     rcx, rdx
0x1400829d9  jz      loc_140082B80
0x1400829df  test    [rcx+1Ch], r14b
0x1400829e3  jz      loc_140082B80
0x1400829e9  mov     edx, 32h ; '2'
0x1400829ee  jmp     loc_140082AE1
0x1400829f3  movups  xmm0, xmmword ptr [r15]
0x1400829f7  mov     r12d, 10h
0x1400829fd  movups  xmmword ptr [rdi], xmm0
0x140082a00  cmp     [rdi], rbx
0x140082a03  jnz     short loc_140082A0B
0x140082a05  cmp     [rdi+8], rbx
0x140082a09  jz      short loc_140082A7E
0x140082a0b  mov     [rsp+78h+lpReturnSize], rbx; lpReturnSize
0x140082a10  mov     r9, rdi; lpValue
0x140082a13  mov     [rsp+78h+lpPreviousValue], rbx; lpPreviousValue
0x140082a18  xor     edx, edx; dwFlags
0x140082a1a  mov     r8d, 20007h; Attribute
0x140082a20  mov     [rsp+78h+cbSize], r12; cbSize
0x140082a25  mov     rcx, rsi; lpAttributeList
0x140082a28  call    cs:__imp_UpdateProcThreadAttribute
0x140082a2e  test    eax, eax
0x140082a30  jnz     short loc_140082A7E
0x140082a32  call    cs:__imp_GetLastError
0x140082a38  mov     ebx, eax
0x140082a3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140082a41  lea     rdx, WPP_GLOBAL_Control
0x140082a48  cmp     rcx, rdx
0x140082a4b  jz      loc_140082B80
0x140082a51  test    [rcx+1Ch], r14b
0x140082a55  jz      loc_140082B80
0x140082a5b  mov     r9, [rdi+8]
0x140082a5f  mov     rcx, [rcx+10h]
0x140082a63  mov     dword ptr [rsp+78h+lpReturnSize], eax
0x140082a67  mov     rax, [rdi]
0x140082a6a  mov     [rsp+78h+lpPreviousValue], rbp
0x140082a6f  mov     [rsp+78h+cbSize], rax
0x140082a74  call    WPP_SF_iiSD
0x140082a79  jmp     loc_140082B80
0x140082a7e  cmp     [r15+10h], ebx
0x140082a82  jz      short loc_140082AFD
0x140082a84  lea     r9, [rdi+24h]; lpValue
0x140082a88  mov     [rsp+78h+lpReturnSize], rbx; lpReturnSize
0x140082a8d  mov     [rsp+78h+lpPreviousValue], rbx; lpPreviousValue
0x140082a92  xor     edx, edx; dwFlags
0x140082a94  mov     r8d, 2000Eh; Attribute
0x140082a9a  mov     [r9], r14d
0x140082a9d  mov     rcx, rsi; lpAttributeList
0x140082aa0  mov     [rsp+78h+cbSize], 4; cbSize
0x140082aa9  call    cs:__imp_UpdateProcThreadAttribute
0x140082aaf  test    eax, eax
0x140082ab1  jnz     short loc_140082AFD
0x140082ab3  call    cs:__imp_GetLastError
0x140082ab9  mov     ebx, eax
0x140082abb  mov     rcx, cs:WPP_GLOBAL_Control
0x140082ac2  lea     rdx, WPP_GLOBAL_Control
0x140082ac9  cmp     rcx, rdx
0x140082acc  jz      loc_140082B80
0x140082ad2  test    [rcx+1Ch], r14b
0x140082ad6  jz      loc_140082B80
0x140082adc  mov     edx, 34h ; '4'
0x140082ae1  mov     rcx, [rcx+10h]
0x140082ae5  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x140082aec  mov     r9, rbp
0x140082aef  mov     dword ptr [rsp+78h+cbSize], eax
0x140082af3  call    WPP_SF_Sd
0x140082af8  jmp     loc_140082B80
0x140082afd  lea     r9, [rdi+10h]; lpValue
0x140082b01  xorps   xmm0, xmm0
0x140082b04  movups  xmmword ptr [r9], xmm0
0x140082b08  cmp     [rsp+78h+arg_10], ebx
0x140082b0f  jz      short loc_140082B1F
0x140082b11  mov     rax, 110000000h
0x140082b1b  or      [rdi+18h], rax
0x140082b1f  cmp     [rdi+18h], rbx
0x140082b23  jz      short loc_140082BA3
0x140082b25  mov     [rsp+78h+lpReturnSize], rbx; lpReturnSize
0x140082b2a  xor     edx, edx; dwFlags
0x140082b2c  mov     [rsp+78h+lpPreviousValue], rbx; lpPreviousValue
0x140082b31  mov     r8d, 20018h; Attribute
0x140082b37  mov     rcx, rsi; lpAttributeList
0x140082b3a  mov     [rsp+78h+cbSize], r12; cbSize
0x140082b3f  call    cs:__imp_UpdateProcThreadAttribute
0x140082b45  test    eax, eax
0x140082b47  jnz     short loc_140082BA3
0x140082b49  call    cs:__imp_GetLastError
0x140082b4f  mov     ebx, eax
0x140082b51  mov     rcx, cs:WPP_GLOBAL_Control
0x140082b58  lea     rdx, WPP_GLOBAL_Control
0x140082b5f  cmp     rcx, rdx
0x140082b62  jz      short loc_140082B80
0x140082b64  test    [rcx+1Ch], r14b
0x140082b68  jz      short loc_140082B80
0x140082b6a  mov     r9, [rdi+18h]
0x140082b6e  mov     rcx, [rcx+10h]
0x140082b72  mov     dword ptr [rsp+78h+lpPreviousValue], eax
0x140082b76  mov     [rsp+78h+cbSize], rbp
0x140082b7b  call    WPP_SF_iSD
0x140082b80  mov     rcx, rsi; lpAttributeList
0x140082b83  call    cs:__imp_DeleteProcThreadAttributeList
0x140082b89  mov     rcx, gs:60h
0x140082b92  mov     r8, rsi; P
0x140082b95  xor     edx, edx; Flags
0x140082b97  mov     rcx, [rcx+30h]; HeapHandle
0x140082b9b  call    cs:__imp_RtlFreeHeap
0x140082ba1  jmp     short loc_140082BAE
0x140082ba3  mov     rax, [rsp+78h+arg_30]
0x140082bab  mov     [rax], rsi
0x140082bae  mov     eax, ebx
0x140082bb0  mov     rbx, [rsp+78h+arg_0]
0x140082bb8  add     rsp, 40h
0x140082bbc  pop     r15
0x140082bbe  pop     r14
0x140082bc0  pop     r13
0x140082bc2  pop     r12
0x140082bc4  pop     rdi
0x140082bc5  pop     rsi
0x140082bc6  pop     rbp
0x140082bc7  retn
```
