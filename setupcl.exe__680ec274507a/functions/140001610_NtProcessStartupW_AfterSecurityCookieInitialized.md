# NtProcessStartupW_AfterSecurityCookieInitialized

- ea: `0x140001610`
- end: `0x1400018bd`
- name: `NtProcessStartupW_AfterSecurityCookieInitialized`
- size: `685`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1400015f0`

## callees

- `0x14000127c`
- `0x140001610`

## import_xrefs

- `ntdll!NtTerminateProcess` at `0x1400018a6`
- `ntdll!NtTerminateProcess` at `0x1400018a6`
- `ntdll!iswspace` at `0x1400016b7`
- `ntdll!iswspace` at `0x1400016fb`
- `ntdll!iswspace` at `0x1400017de`
- `ntdll!iswspace` at `0x140001823`
- `ntdll!iswspace` at `0x1400016b7`
- `ntdll!iswspace` at `0x1400016fb`
- `ntdll!iswspace` at `0x1400017de`
- `ntdll!iswspace` at `0x140001823`
- `ntdll!RtlAllocateHeap` at `0x14000178a`
- `ntdll!RtlAllocateHeap` at `0x14000178a`
- `ntdll!RtlNormalizeProcessParams` at `0x140001636`
- `ntdll!RtlNormalizeProcessParams` at `0x140001636`

## pseudocode

```c
NTSTATUS __fastcall NtProcessStartupW_AfterSecurityCookieInitialized(__int64 a1)
{
  __int64 v1; // r14
  PRTL_USER_PROCESS_PARAMETERS v2; // rax
  unsigned __int64 v3; // rdx
  PWSTR Environment; // rcx
  __int64 *v5; // r15
  PRTL_USER_PROCESS_PARAMETERS v6; // r13
  ULONG DebugFlags; // ebp
  UNICODE_STRING *p_CommandLine; // rsi
  unsigned int v9; // r12d
  __int64 v10; // r8
  wint_t *Buffer; // rbx
  int Length; // edi
  wint_t *v13; // r14
  __int64 v15; // rax
  SIZE_T v16; // r15
  __int64 v17; // rsi
  char **Heap; // rax
  char **v19; // r14
  NTSTATUS v20; // eax
  char *v21; // r12
  char *v22; // rsi
  char *v23; // r15
  __int64 v27; // [rsp+80h] [rbp+18h]
  __int64 v28; // [rsp+88h] [rbp+20h] BYREF

  v1 = a1;
  v28 = 0;
  v2 = RtlNormalizeProcessParams(*(PRTL_USER_PROCESS_PARAMETERS *)(a1 + 32));
  v5 = &v28;
  v6 = v2;
  if ( !v2 )
  {
    DebugFlags = 0;
LABEL_60:
    v20 = wmain(Environment, v3, v5, DebugFlags);
    return NtTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, v20);
  }
  DebugFlags = v2->DebugFlags;
  p_CommandLine = &v2->CommandLine;
  v9 = 1;
  v10 = 0;
  v27 = 0;
  if ( v2->CommandLine.Buffer && p_CommandLine->Length
    || (p_CommandLine = &v2->ImagePathName, Buffer = 0, Length = 0, v2->ImagePathName.Buffer) )
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
            v10 = v27;
            goto LABEL_14;
          }
          if ( !iswspace(*Buffer) )
            break;
          ++Buffer;
          Length -= 2;
        }
        while ( Length );
        v10 = v27;
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
          v10 = v27 + 2 * (Buffer - v13) + 2;
          v27 = v10;
        }
      }
      while ( Length );
      v1 = a1;
    }
  }
  Environment = v6->Environment;
  v3 = 0;
  if ( Environment )
  {
    while ( *Environment )
    {
      ++Environment;
      v3 = (unsigned int)(v3 + 1);
      while ( *Environment++ )
        ;
    }
  }
  v15 = v9 + (_DWORD)v3 + 1;
  if ( (unsigned int)v15 > 2 )
  {
    if ( v9 > 1 )
    {
      Buffer = p_CommandLine->Buffer;
      Length = p_CommandLine->Length;
    }
    v16 = v10 + 8 * v15;
    v17 = (unsigned int)v15;
    Heap = (char **)RtlAllocateHeap(*(PVOID *)(v1 + 48), 0, v16);
    v19 = Heap;
    if ( !Heap )
    {
      v20 = -1073741801;
      v5 = &v28;
      goto LABEL_55;
    }
    if ( v9 > 1 )
    {
      v21 = (char *)Heap + v16;
      v22 = (char *)&Heap[v17];
      while ( Length && v22 < v21 && *Buffer )
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
          *v19++ = v22;
          do
          {
            v23 = v22;
            *(_WORD *)v22 = *Buffer++;
            v22 += 2;
            Length -= 2;
            if ( !Length )
              break;
            if ( v22 >= v21 )
              goto LABEL_47;
          }
          while ( !iswspace(*Buffer) );
          if ( v22 < v21 )
          {
            *(_WORD *)v22 = 0;
            v22 += 2;
            continue;
          }
LABEL_47:
          v22 = v23;
          *(_WORD *)v23 = 0;
        }
      }
    }
LABEL_48:
    *v19 = 0;
    v5 = (__int64 *)(v19 + 1);
    Environment = v6->Environment;
    v3 = (unsigned __int64)(v19 + 1);
    if ( Environment )
    {
      while ( *Environment )
      {
        *(_QWORD *)v3 = Environment;
        v3 += 8LL;
        ++Environment;
        while ( *Environment++ )
          ;
      }
    }
    *(_QWORD *)v3 = 0;
  }
  v20 = 0;
LABEL_55:
  if ( DebugFlags )
    __debugbreak();
  if ( v20 >= 0 )
    goto LABEL_60;
  return NtTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, v20);
}

```

## disassembly

```asm
0x140001610  mov     rax, rsp
0x140001613  mov     [rax+8], rcx
0x140001617  push    rbx
0x140001618  push    rbp
0x140001619  push    rsi
0x14000161a  push    rdi
0x14000161b  push    r12
0x14000161d  push    r13
0x14000161f  push    r14
0x140001621  push    r15
0x140001623  sub     rsp, 28h
0x140001627  mov     r14, rcx
0x14000162a  mov     qword ptr [rax+20h], 0
0x140001632  mov     rcx, [rcx+20h]; ProcessParameters
0x140001636  call    cs:__imp_RtlNormalizeProcessParams
0x14000163c  xor     r9d, r9d
0x14000163f  lea     r15, [rsp+68h+arg_18]
0x140001647  mov     r13, rax
0x14000164a  test    rax, rax
0x14000164d  jz      loc_140001892
0x140001653  mov     ebp, [rax+0Ch]
0x140001656  lea     rsi, [rax+70h]
0x14000165a  lea     r12d, [r9+1]
0x14000165e  mov     r8d, r9d
0x140001661  mov     [rsp+68h+arg_10], r9
0x140001669  mov     [rsp+68h+arg_8], r9d
0x14000166e  cmp     [rsi+8], r9
0x140001672  jz      short loc_14000167A
0x140001674  cmp     [rsi], r9w
0x140001678  jnz     short loc_14000168E
0x14000167a  lea     rsi, [rax+60h]
0x14000167e  mov     rbx, r9
0x140001681  mov     edi, r9d
0x140001684  cmp     [rsi+8], r9
0x140001688  jz      loc_140001736
0x14000168e  movzx   edi, word ptr [rsi]
0x140001691  mov     rbx, [rsi+8]
0x140001695  test    edi, edi
0x140001697  jz      loc_140001736
0x14000169d  cmp     [rbx], r9w
0x1400016a1  jz      loc_140001731
0x1400016a7  test    edi, edi
0x1400016a9  jz      loc_140001731
0x1400016af  movzx   ecx, word ptr [rbx]; C
0x1400016b2  test    cx, cx
0x1400016b5  jz      short loc_1400016DB
0x1400016b7  call    cs:__imp_iswspace
0x1400016bd  xor     r9d, r9d
0x1400016c0  test    eax, eax
0x1400016c2  jz      short loc_1400016CD
0x1400016c4  add     rbx, 2
0x1400016c8  add     edi, 0FFFFFFFEh
0x1400016cb  jnz     short loc_1400016AF
0x1400016cd  mov     r8, [rsp+68h+arg_10]
0x1400016d5  test    edi, edi
0x1400016d7  jz      short loc_140001731
0x1400016d9  jmp     short loc_1400016E3
0x1400016db  mov     r8, [rsp+68h+arg_10]
0x1400016e3  cmp     [rbx], r9w
0x1400016e7  jz      short loc_140001729
0x1400016e9  inc     r12d
0x1400016ec  mov     r14, rbx
0x1400016ef  add     rbx, 2
0x1400016f3  add     edi, 0FFFFFFFEh
0x1400016f6  jz      short loc_140001708
0x1400016f8  movzx   ecx, word ptr [rbx]; C
0x1400016fb  call    cs:__imp_iswspace
0x140001701  xor     r9d, r9d
0x140001704  test    eax, eax
0x140001706  jz      short loc_1400016EF
0x140001708  mov     r8, [rsp+68h+arg_10]
0x140001710  mov     rax, rbx
0x140001713  sub     rax, r14
0x140001716  sar     rax, 1
0x140001719  lea     r8, [r8+rax*2]
0x14000171d  add     r8, 2
0x140001721  mov     [rsp+68h+arg_10], r8
0x140001729  test    edi, edi
0x14000172b  jnz     loc_14000169D
0x140001731  mov     r14, [rsp+68h+arg_0]
0x140001736  mov     rcx, [r13+80h]
0x14000173d  mov     edx, r9d
0x140001740  test    rcx, rcx
0x140001743  jz      short loc_14000175F
0x140001745  jmp     short loc_140001759
0x140001747  add     rcx, 2
0x14000174b  inc     edx
0x14000174d  movzx   eax, word ptr [rcx]
0x140001750  add     rcx, 2
0x140001754  test    ax, ax
0x140001757  jnz     short loc_14000174D
0x140001759  cmp     [rcx], r9w
0x14000175d  jnz     short loc_140001747
0x14000175f  lea     eax, [rdx+1]
0x140001762  add     eax, r12d
0x140001765  cmp     eax, 2
0x140001768  jbe     loc_140001883
0x14000176e  cmp     r12d, 1
0x140001772  jbe     short loc_14000177B
0x140001774  mov     rbx, [rsi+8]
0x140001778  movzx   edi, word ptr [rsi]
0x14000177b  mov     rcx, [r14+30h]; HeapHandle
0x14000177f  lea     r15, [r8+rax*8]
0x140001783  mov     r8, r15; Size
0x140001786  mov     esi, eax
0x140001788  xor     edx, edx; Flags
0x14000178a  call    cs:__imp_RtlAllocateHeap
0x140001790  xor     r9d, r9d
0x140001793  mov     r14, rax
0x140001796  test    rax, rax
0x140001799  jnz     short loc_1400017AD
0x14000179b  mov     eax, 0C0000017h
0x1400017a0  lea     r15, [rsp+68h+arg_18]
0x1400017a8  jmp     loc_140001887
0x1400017ad  cmp     r12d, 1
0x1400017b1  jbe     loc_14000184B
0x1400017b7  lea     r12, [r15+rax]
0x1400017bb  lea     rsi, [rax+rsi*8]
0x1400017bf  test    edi, edi
0x1400017c1  jz      loc_14000184B
0x1400017c7  cmp     rsi, r12
0x1400017ca  jnb     short loc_14000184B
0x1400017cc  cmp     [rbx], r9w
0x1400017d0  jz      short loc_14000184B
0x1400017d2  test    edi, edi
0x1400017d4  jz      short loc_14000184B
0x1400017d6  movzx   ecx, word ptr [rbx]; C
0x1400017d9  test    cx, cx
0x1400017dc  jz      short loc_1400017F8
0x1400017de  call    cs:__imp_iswspace
0x1400017e4  xor     r9d, r9d
0x1400017e7  test    eax, eax
0x1400017e9  jz      short loc_1400017F4
0x1400017eb  add     rbx, 2
0x1400017ef  add     edi, 0FFFFFFFEh
0x1400017f2  jnz     short loc_1400017D6
0x1400017f4  test    edi, edi
0x1400017f6  jz      short loc_14000184B
0x1400017f8  cmp     [rbx], r9w
0x1400017fc  jz      short loc_1400017BF
0x1400017fe  mov     [r14], rsi
0x140001801  add     r14, 8
0x140001805  movzx   eax, word ptr [rbx]
0x140001808  mov     r15, rsi
0x14000180b  mov     [rsi], ax
0x14000180e  add     rbx, 2
0x140001812  add     rsi, 2
0x140001816  add     edi, 0FFFFFFFEh
0x140001819  jz      short loc_140001830
0x14000181b  cmp     rsi, r12
0x14000181e  jnb     short loc_14000183F
0x140001820  movzx   ecx, word ptr [rbx]; C
0x140001823  call    cs:__imp_iswspace
0x140001829  xor     r9d, r9d
0x14000182c  test    eax, eax
0x14000182e  jz      short loc_140001805
0x140001830  cmp     rsi, r12
0x140001833  jnb     short loc_14000183F
0x140001835  mov     [rsi], r9w
0x140001839  add     rsi, 2
0x14000183d  jmp     short loc_1400017BF
0x14000183f  mov     rsi, r15
0x140001842  mov     [r15], r9w
0x140001846  jmp     loc_1400017BF
0x14000184b  mov     [r14], r9
0x14000184e  lea     r15, [r14+8]
0x140001852  mov     rcx, [r13+80h]
0x140001859  mov     rdx, r15
0x14000185c  test    rcx, rcx
0x14000185f  jz      short loc_140001880
0x140001861  jmp     short loc_14000187A
0x140001863  mov     [rdx], rcx
0x140001866  add     rdx, 8
0x14000186a  add     rcx, 2
0x14000186e  movzx   eax, word ptr [rcx]
0x140001871  add     rcx, 2
0x140001875  test    ax, ax
0x140001878  jnz     short loc_14000186E
0x14000187a  cmp     [rcx], r9w
0x14000187e  jnz     short loc_140001863
0x140001880  mov     [rdx], r9
0x140001883  mov     eax, [rsp+68h+arg_8]
0x140001887  test    ebp, ebp
0x140001889  jz      short loc_14000188C
0x14000188b  int     3; Trap to Debugger
0x14000188c  test    eax, eax
0x14000188e  js      short loc_1400018A0
0x140001890  jmp     short loc_140001895
0x140001892  mov     ebp, r9d
0x140001895  mov     r9d, ebp
0x140001898  mov     r8, r15
0x14000189b  call    wmain
0x1400018a0  mov     edx, eax; ExitStatus
0x1400018a2  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400018a6  call    cs:__imp_NtTerminateProcess
0x1400018ac  add     rsp, 28h
0x1400018b0  pop     r15
0x1400018b2  pop     r14
0x1400018b4  pop     r13
0x1400018b6  pop     r12
0x1400018b8  pop     rdi
0x1400018b9  pop     rsi
0x1400018ba  pop     rbp
0x1400018bb  pop     rbx
0x1400018bc  retn
```
