# NtProcessStartupW_AfterSecurityCookieInitialized

- ea: `0x140003390`
- end: `0x14000367c`
- name: `NtProcessStartupW_AfterSecurityCookieInitialized`
- size: `748`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140003370`

## callees

- `0x1400028a4`
- `0x140003390`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140003521`
- `ntdll!RtlAllocateHeap` at `0x140003521`
- `ntdll!NtTerminateProcess` at `0x140003665`
- `ntdll!NtTerminateProcess` at `0x140003665`
- `ntdll!iswspace` at `0x14000344b`
- `ntdll!iswspace` at `0x14000348f`
- `ntdll!iswspace` at `0x14000357f`
- `ntdll!iswspace` at `0x1400035cb`
- `ntdll!iswspace` at `0x14000344b`
- `ntdll!iswspace` at `0x14000348f`
- `ntdll!iswspace` at `0x14000357f`
- `ntdll!iswspace` at `0x1400035cb`
- `ntdll!RtlNormalizeProcessParams` at `0x1400033b5`
- `ntdll!RtlNormalizeProcessParams` at `0x1400033b5`

## pseudocode

```c
NTSTATUS __fastcall NtProcessStartupW_AfterSecurityCookieInitialized(__int64 a1)
{
  __int64 v1; // r14
  PRTL_USER_PROCESS_PARAMETERS v2; // rax
  __int64 *v3; // rcx
  PRTL_USER_PROCESS_PARAMETERS v4; // r13
  __int64 *v5; // r15
  unsigned int v6; // eax
  ULONG DebugFlags; // ebp
  UNICODE_STRING *p_CommandLine; // rsi
  unsigned int v9; // r12d
  __int64 v10; // r8
  wint_t *Buffer; // rbx
  int Length; // edi
  wint_t *v13; // r14
  PWSTR Environment; // rcx
  int v15; // edx
  __int64 v17; // rax
  SIZE_T v18; // r15
  __int64 v19; // rsi
  char **Heap; // rax
  char **v21; // r14
  NTSTATUS v22; // eax
  char *v23; // r12
  char *v24; // rsi
  char *v25; // r15
  PWSTR v26; // rcx
  _QWORD *v27; // rdx
  __int64 v30; // [rsp+20h] [rbp-58h] BYREF
  __int64 *v31; // [rsp+28h] [rbp-50h]
  unsigned int v33; // [rsp+88h] [rbp+10h]
  __int64 v34; // [rsp+98h] [rbp+20h]

  v1 = a1;
  v30 = 0;
  v2 = RtlNormalizeProcessParams(*(PRTL_USER_PROCESS_PARAMETERS *)(a1 + 32));
  v3 = &v30;
  v4 = v2;
  v31 = &v30;
  v5 = &v30;
  v6 = 0;
  v33 = 0;
  if ( !v4 )
  {
    DebugFlags = 0;
    goto LABEL_60;
  }
  DebugFlags = v4->DebugFlags;
  p_CommandLine = &v4->CommandLine;
  v9 = 1;
  v10 = 0;
  v34 = 0;
  if ( v4->CommandLine.Buffer && p_CommandLine->Length
    || (p_CommandLine = &v4->ImagePathName, Buffer = 0, Length = 0, v4->ImagePathName.Buffer) )
  {
    Length = p_CommandLine->Length;
    Buffer = p_CommandLine->Buffer;
    if ( p_CommandLine->Length )
    {
      do
      {
        if ( !*Buffer || !Length )
          break;
        do
        {
          if ( !*Buffer )
          {
            v10 = v34;
            goto LABEL_14;
          }
          if ( !iswspace(*Buffer) )
            break;
          ++Buffer;
          Length -= 2;
        }
        while ( Length );
        v10 = v34;
        if ( !Length )
          break;
LABEL_14:
        if ( *Buffer )
        {
          ++v9;
          v13 = Buffer;
          do
          {
            ++Buffer;
            Length -= 2;
          }
          while ( Length && !iswspace(*Buffer) );
          v10 = v34 + 2 * (Buffer - v13) + 2;
          v34 = v10;
        }
      }
      while ( Length );
      v1 = a1;
    }
  }
  Environment = v4->Environment;
  v15 = 0;
  if ( Environment )
  {
    while ( *Environment )
    {
      ++Environment;
      ++v15;
      while ( *Environment++ )
        ;
    }
  }
  v17 = v9 + v15 + 1;
  if ( (unsigned int)v17 > 2 )
  {
    if ( v9 > 1 )
    {
      Buffer = p_CommandLine->Buffer;
      Length = p_CommandLine->Length;
    }
    v18 = v10 + 8 * v17;
    v19 = (unsigned int)v17;
    Heap = (char **)RtlAllocateHeap(*(PVOID *)(v1 + 48), 0, v18);
    v21 = Heap;
    if ( !Heap )
    {
      v22 = -1073741801;
      v5 = &v30;
      goto LABEL_55;
    }
    v31 = (__int64 *)Heap;
    if ( v9 > 1 )
    {
      v23 = (char *)Heap + v18;
      v24 = (char *)&Heap[v19];
      while ( Length && v24 < v23 && *Buffer )
      {
        while ( *Buffer )
        {
          if ( iswspace(*Buffer) )
          {
            ++Buffer;
            Length -= 2;
            if ( Length )
              continue;
          }
          if ( !Length )
            goto LABEL_48;
          break;
        }
        if ( *Buffer )
        {
          *v21++ = v24;
          ++v33;
          do
          {
            v25 = v24;
            *(_WORD *)v24 = *Buffer++;
            v24 += 2;
            Length -= 2;
            if ( !Length )
              break;
            if ( v24 >= v23 )
              goto LABEL_47;
          }
          while ( !iswspace(*Buffer) );
          if ( v24 < v23 )
          {
            *(_WORD *)v24 = 0;
            v24 += 2;
            continue;
          }
LABEL_47:
          v24 = v25;
          *(_WORD *)v25 = 0;
        }
      }
    }
LABEL_48:
    *v21 = 0;
    v5 = (__int64 *)(v21 + 1);
    v26 = v4->Environment;
    v27 = v21 + 1;
    if ( v26 )
    {
      while ( *v26 )
      {
        *v27++ = v26++;
        while ( *v26++ )
          ;
      }
    }
    *v27 = 0;
  }
  v22 = 0;
LABEL_55:
  if ( DebugFlags )
    __debugbreak();
  if ( v22 >= 0 )
  {
    v6 = v33;
    v3 = v31;
LABEL_60:
    v22 = wmain(v6, v3, v5, DebugFlags, v30);
  }
  return NtTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, v22);
}

```

## disassembly

```asm
0x140003390  mov     [rsp+arg_0], rcx
0x140003395  push    rbx
0x140003396  push    rbp
0x140003397  push    rsi
0x140003398  push    rdi
0x140003399  push    r12
0x14000339b  push    r13
0x14000339d  push    r14
0x14000339f  push    r15
0x1400033a1  sub     rsp, 38h
0x1400033a5  mov     r14, rcx
0x1400033a8  mov     [rsp+78h+var_58], 0
0x1400033b1  mov     rcx, [rcx+20h]; ProcessParameters
0x1400033b5  call    cs:__imp_RtlNormalizeProcessParams
0x1400033bb  xor     r9d, r9d
0x1400033be  lea     rcx, [rsp+78h+var_58]
0x1400033c3  mov     r13, rax
0x1400033c6  mov     [rsp+78h+var_50], rcx
0x1400033cb  lea     r15, [rsp+78h+var_58]
0x1400033d0  mov     eax, r9d
0x1400033d3  mov     [rsp+78h+arg_8], eax
0x1400033da  test    r13, r13
0x1400033dd  jz      loc_14000364C
0x1400033e3  mov     ebp, [r13+0Ch]
0x1400033e7  lea     rsi, [r13+70h]
0x1400033eb  lea     r12d, [r9+1]
0x1400033ef  mov     r8d, r9d
0x1400033f2  mov     [rsp+78h+arg_18], r9
0x1400033fa  mov     [rsp+78h+arg_10], r9d
0x140003402  cmp     [rsi+8], r9
0x140003406  jz      short loc_14000340E
0x140003408  cmp     [rsi], r9w
0x14000340c  jnz     short loc_140003422
0x14000340e  lea     rsi, [r13+60h]
0x140003412  mov     rbx, r9
0x140003415  mov     edi, r9d
0x140003418  cmp     [rsi+8], r9
0x14000341c  jz      loc_1400034CD
0x140003422  movzx   edi, word ptr [rsi]
0x140003425  mov     rbx, [rsi+8]
0x140003429  test    edi, edi
0x14000342b  jz      loc_1400034CD
0x140003431  cmp     [rbx], r9w
0x140003435  jz      loc_1400034C5
0x14000343b  test    edi, edi
0x14000343d  jz      loc_1400034C5
0x140003443  movzx   ecx, word ptr [rbx]; C
0x140003446  test    cx, cx
0x140003449  jz      short loc_14000346F
0x14000344b  call    cs:__imp_iswspace
0x140003451  xor     r9d, r9d
0x140003454  test    eax, eax
0x140003456  jz      short loc_140003461
0x140003458  add     rbx, 2
0x14000345c  add     edi, 0FFFFFFFEh
0x14000345f  jnz     short loc_140003443
0x140003461  mov     r8, [rsp+78h+arg_18]
0x140003469  test    edi, edi
0x14000346b  jz      short loc_1400034C5
0x14000346d  jmp     short loc_140003477
0x14000346f  mov     r8, [rsp+78h+arg_18]
0x140003477  cmp     [rbx], r9w
0x14000347b  jz      short loc_1400034BD
0x14000347d  inc     r12d
0x140003480  mov     r14, rbx
0x140003483  add     rbx, 2
0x140003487  add     edi, 0FFFFFFFEh
0x14000348a  jz      short loc_14000349C
0x14000348c  movzx   ecx, word ptr [rbx]; C
0x14000348f  call    cs:__imp_iswspace
0x140003495  xor     r9d, r9d
0x140003498  test    eax, eax
0x14000349a  jz      short loc_140003483
0x14000349c  mov     r8, [rsp+78h+arg_18]
0x1400034a4  mov     rax, rbx
0x1400034a7  sub     rax, r14
0x1400034aa  sar     rax, 1
0x1400034ad  lea     r8, [r8+rax*2]
0x1400034b1  add     r8, 2
0x1400034b5  mov     [rsp+78h+arg_18], r8
0x1400034bd  test    edi, edi
0x1400034bf  jnz     loc_140003431
0x1400034c5  mov     r14, [rsp+78h+arg_0]
0x1400034cd  mov     rcx, [r13+80h]
0x1400034d4  mov     edx, r9d
0x1400034d7  test    rcx, rcx
0x1400034da  jz      short loc_1400034F6
0x1400034dc  jmp     short loc_1400034F0
0x1400034de  add     rcx, 2
0x1400034e2  inc     edx
0x1400034e4  movzx   eax, word ptr [rcx]
0x1400034e7  add     rcx, 2
0x1400034eb  test    ax, ax
0x1400034ee  jnz     short loc_1400034E4
0x1400034f0  cmp     [rcx], r9w
0x1400034f4  jnz     short loc_1400034DE
0x1400034f6  lea     eax, [rdx+1]
0x1400034f9  add     eax, r12d
0x1400034fc  cmp     eax, 2
0x1400034ff  jbe     loc_14000362E
0x140003505  cmp     r12d, 1
0x140003509  jbe     short loc_140003512
0x14000350b  mov     rbx, [rsi+8]
0x14000350f  movzx   edi, word ptr [rsi]
0x140003512  mov     rcx, [r14+30h]; HeapHandle
0x140003516  lea     r15, [r8+rax*8]
0x14000351a  mov     r8, r15; Size
0x14000351d  mov     esi, eax
0x14000351f  xor     edx, edx; Flags
0x140003521  call    cs:__imp_RtlAllocateHeap
0x140003527  xor     r9d, r9d
0x14000352a  mov     r14, rax
0x14000352d  test    rax, rax
0x140003530  jnz     short loc_140003541
0x140003532  mov     eax, 0C0000017h
0x140003537  lea     r15, [rsp+78h+var_58]
0x14000353c  jmp     loc_140003635
0x140003541  mov     [rsp+78h+var_50], rax
0x140003546  cmp     r12d, 1
0x14000354a  jbe     loc_1400035F6
0x140003550  lea     r12, [r15+rax]
0x140003554  lea     rsi, [rax+rsi*8]
0x140003558  test    edi, edi
0x14000355a  jz      loc_1400035F6
0x140003560  cmp     rsi, r12
0x140003563  jnb     loc_1400035F6
0x140003569  cmp     [rbx], r9w
0x14000356d  jz      loc_1400035F6
0x140003573  test    edi, edi
0x140003575  jz      short loc_1400035F6
0x140003577  movzx   ecx, word ptr [rbx]; C
0x14000357a  test    cx, cx
0x14000357d  jz      short loc_140003599
0x14000357f  call    cs:__imp_iswspace
0x140003585  xor     r9d, r9d
0x140003588  test    eax, eax
0x14000358a  jz      short loc_140003595
0x14000358c  add     rbx, 2
0x140003590  add     edi, 0FFFFFFFEh
0x140003593  jnz     short loc_140003577
0x140003595  test    edi, edi
0x140003597  jz      short loc_1400035F6
0x140003599  cmp     [rbx], r9w
0x14000359d  jz      short loc_140003558
0x14000359f  mov     [r14], rsi
0x1400035a2  add     r14, 8
0x1400035a6  inc     [rsp+78h+arg_8]
0x1400035ad  movzx   eax, word ptr [rbx]
0x1400035b0  mov     r15, rsi
0x1400035b3  mov     [rsi], ax
0x1400035b6  add     rbx, 2
0x1400035ba  add     rsi, 2
0x1400035be  add     edi, 0FFFFFFFEh
0x1400035c1  jz      short loc_1400035D8
0x1400035c3  cmp     rsi, r12
0x1400035c6  jnb     short loc_1400035EA
0x1400035c8  movzx   ecx, word ptr [rbx]; C
0x1400035cb  call    cs:__imp_iswspace
0x1400035d1  xor     r9d, r9d
0x1400035d4  test    eax, eax
0x1400035d6  jz      short loc_1400035AD
0x1400035d8  cmp     rsi, r12
0x1400035db  jnb     short loc_1400035EA
0x1400035dd  mov     [rsi], r9w
0x1400035e1  add     rsi, 2
0x1400035e5  jmp     loc_140003558
0x1400035ea  mov     rsi, r15
0x1400035ed  mov     [r15], r9w
0x1400035f1  jmp     loc_140003558
0x1400035f6  mov     [r14], r9
0x1400035f9  lea     r15, [r14+8]
0x1400035fd  mov     rcx, [r13+80h]
0x140003604  mov     rdx, r15
0x140003607  test    rcx, rcx
0x14000360a  jz      short loc_14000362B
0x14000360c  jmp     short loc_140003625
0x14000360e  mov     [rdx], rcx
0x140003611  add     rdx, 8
0x140003615  add     rcx, 2
0x140003619  movzx   eax, word ptr [rcx]
0x14000361c  add     rcx, 2
0x140003620  test    ax, ax
0x140003623  jnz     short loc_140003619
0x140003625  cmp     [rcx], r9w
0x140003629  jnz     short loc_14000360E
0x14000362b  mov     [rdx], r9
0x14000362e  mov     eax, [rsp+78h+arg_10]
0x140003635  test    ebp, ebp
0x140003637  jz      short loc_14000363A
0x140003639  int     3; Trap to Debugger
0x14000363a  test    eax, eax
0x14000363c  js      short loc_14000365F
0x14000363e  mov     eax, [rsp+78h+arg_8]
0x140003645  mov     rcx, [rsp+78h+var_50]
0x14000364a  jmp     short loc_14000364F
0x14000364c  mov     ebp, r9d
0x14000364f  mov     rdx, rcx
0x140003652  mov     r9d, ebp
0x140003655  mov     ecx, eax
0x140003657  mov     r8, r15
0x14000365a  call    wmain
0x14000365f  mov     edx, eax; ExitStatus
0x140003661  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140003665  call    cs:__imp_NtTerminateProcess
0x14000366b  add     rsp, 38h
0x14000366f  pop     r15
0x140003671  pop     r14
0x140003673  pop     r13
0x140003675  pop     r12
0x140003677  pop     rdi
0x140003678  pop     rsi
0x140003679  pop     rbp
0x14000367a  pop     rbx
0x14000367b  retn
```
