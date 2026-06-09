# CreatetCallClient

- ea: `0x180003f58`
- end: `0x180004434`
- name: `CreatetCallClient`
- size: `1244`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, int, int, int, _QWORD *, int)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x180003498`
- `0x180003d8c`
- `0x18000c5a0`
- `0x18000ebb0`
- `0x18000fe60`
- `0x180017be0`

## callees

- `0x180001f50`
- `0x180003f58`
- `0x18001bb04`
- `0x18001f620`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e2f0`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000400e`
- `KERNEL32!HeapAlloc` at `0x18000400e`
- `KERNEL32!LeaveCriticalSection` at `0x180004090`
- `KERNEL32!LeaveCriticalSection` at `0x180004114`
- `KERNEL32!LeaveCriticalSection` at `0x1800042c0`
- `KERNEL32!LeaveCriticalSection` at `0x18000436e`
- `KERNEL32!LeaveCriticalSection` at `0x1800043fc`
- `KERNEL32!LeaveCriticalSection` at `0x180004090`
- `KERNEL32!LeaveCriticalSection` at `0x180004114`
- `KERNEL32!LeaveCriticalSection` at `0x1800042c0`
- `KERNEL32!LeaveCriticalSection` at `0x18000436e`
- `KERNEL32!LeaveCriticalSection` at `0x1800043fc`
- `KERNEL32!EnterCriticalSection` at `0x180004163`
- `KERNEL32!EnterCriticalSection` at `0x180004391`
- `KERNEL32!EnterCriticalSection` at `0x180004163`
- `KERNEL32!EnterCriticalSection` at `0x180004391`

## string_xrefs

- `0x180003f8c`: `CreatetCallClient: enter, ptCall=%p,`
- `0x180004038`: `CreatetCallClient: calling NewObject, ptCallClient = [%p]`
- `0x180004328`: `CreatetCallClient: exit, new ptCallClient=%p`

## pseudocode

```c
__int64 __fastcall CreatetCallClient(
        unsigned __int64 a1,
        unsigned __int64 a2,
        int a3,
        int a4,
        int a5,
        _QWORD *a6,
        int a7)
{
  __int64 v10; // rdx
  _DWORD *v11; // rdi
  _DWORD *v12; // r14
  unsigned int v13; // r13d
  __int64 v14; // rcx
  int v15; // eax
  __int64 v17; // r15
  __int64 v18; // rax
  __int64 v19; // rcx
  BOOL v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  _OWORD *v23; // rcx
  int v24; // r9d
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  BOOL v29; // [rsp+3Ch] [rbp-8Ch]
  unsigned __int64 v30; // [rsp+40h] [rbp-88h]
  unsigned __int64 v31; // [rsp+60h] [rbp-68h]
  _DWORD *v32; // [rsp+78h] [rbp-50h]

  TRACELogPrint(524290, "CreatetCallClient: enter, ptCall=%p,", (const void *)a1);
  if ( !(unsigned int)WaitForExclusivetCallAccess(a1, a4 != 0 ? 1280065859 : 1279345481) )
    return 2147483720LL;
  v10 = *(int *)(a1 + 184);
  if ( (int)v10 >= 2 )
  {
    v11 = HeapAlloc(ghTapisrvHeap, 8u, 0xD8u);
    if ( !v11 )
    {
LABEL_9:
      LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4)));
      return 2147483716LL;
    }
    v13 = 0;
    v12 = (_DWORD *)(a1 + 188);
  }
  else
  {
    v11 = (_DWORD *)(a1 + 216 * v10 + 192);
    *(_DWORD *)(a1 + 184) = v10 + 1;
    v12 = (_DWORD *)(a1 + 188);
    ++*(_DWORD *)(a1 + 188);
    v13 = 1;
  }
  TRACELogPrint(262146, "CreatetCallClient: calling NewObject, ptCallClient = [%p]", v11);
  v15 = NewObject(v14, v11, v13);
  v11[22] = v15;
  if ( !v15 )
  {
    if ( v13 )
    {
      --*v12;
      --*(_DWORD *)(a1 + 184);
    }
    else
    {
      ServerFree(v11);
    }
    goto LABEL_9;
  }
  v17 = 0;
  if ( a3 == 4 )
    ++*(_DWORD *)(a1 + 64);
  else
    ++*(_DWORD *)(a1 + 68);
  v18 = *(_QWORD *)(a1 + 8);
  v32 = v11 + 14;
  *((_QWORD *)v11 + 7) = v18;
  if ( v18 )
    *(_QWORD *)(v18 + 48) = v11;
  *(_QWORD *)(a1 + 8) = v11;
  v31 = a1 >> 4;
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a1 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  *((_QWORD *)v11 + 2) = a2;
  *((_QWORD *)v11 + 3) = a1;
  v11[8] = a3;
  *((_BYTE *)v11 + 44) = a7 != 0;
  v30 = a2 >> 4;
  EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a2 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  v20 = *(_DWORD *)a2 == 1229734732;
  v29 = v20;
  if ( *(_DWORD *)a2 == 1229734732 )
  {
    v21 = ReferenceObject(v19, *(unsigned int *)(a2 + 24), 1229734732);
    v17 = v21;
    v20 = v21 && a2 == v21 && v29;
  }
  if ( v20 )
  {
    *((_QWORD *)v11 + 1) = *(_QWORD *)(a2 + 8);
    v22 = *(_QWORD *)(a2 + 48);
    *((_QWORD *)v11 + 9) = v22;
    if ( v22 )
      *(_QWORD *)(v22 + 64) = v11;
    *(_QWORD *)(a2 + 48) = v11;
    if ( v17 )
      DereferenceObject(v19, *(unsigned int *)(v17 + 24), 1);
    v23 = v11 + 23;
    if ( *(_DWORD *)(*(_QWORD *)(a2 + 16) + 48LL) > 0x30000u )
    {
      *v23 = *(_OWORD *)(a2 + 168);
      *(_OWORD *)(v11 + 27) = *(_OWORD *)(a2 + 184);
      *(_OWORD *)(v11 + 31) = *(_OWORD *)(a2 + 200);
      *(_OWORD *)(v11 + 35) = *(_OWORD *)(a2 + 216);
      *(_OWORD *)(v11 + 39) = *(_OWORD *)(a2 + 232);
      *(_OWORD *)(v11 + 43) = *(_OWORD *)(a2 + 248);
      *(_OWORD *)(v11 + 47) = *(_OWORD *)(a2 + 264);
      *(_OWORD *)(v11 + 50) = *(_OWORD *)(a2 + 276);
    }
    else
    {
      memset_0(v23, 255, 0x7Cu);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v30 & gdwPointerToLockTableIndexBits));
    *v11 = a4 != 0 ? 1229734723 : 1279476553;
    if ( a5 )
    {
      v24 = 2048;
      if ( a3 != 4 )
        v24 = 0x2000;
      SendMsgToCallClients(a1, (_DWORD)v11, 1, v24, 0, 0);
    }
    *a6 = v11;
    TRACELogPrint(524290, "CreatetCallClient: exit, new ptCallClient=%p", v11);
    return 0;
  }
  else
  {
    if ( v17 )
      DereferenceObject(v19, *(unsigned int *)(v17 + 24), 1);
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v30 & gdwPointerToLockTableIndexBits));
    EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v31 & gdwPointerToLockTableIndexBits));
    if ( a3 == 4 )
      --*(_DWORD *)(a1 + 64);
    else
      --*(_DWORD *)(a1 + 68);
    if ( *(_QWORD *)v32 )
      *(_QWORD *)(*(_QWORD *)v32 + 48LL) = *((_QWORD *)v11 + 6);
    v25 = *((_QWORD *)v11 + 6);
    v26 = *((_QWORD *)v11 + 7);
    if ( v25 )
      *(_QWORD *)(v25 + 56) = v26;
    else
      *(_QWORD *)(a1 + 8) = v26;
    if ( v13 )
      --*v12;
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v31 & gdwPointerToLockTableIndexBits));
    DereferenceObject(v27, (unsigned int)v11[22], 1);
    return 2147483691LL;
  }
}

```

## disassembly

```asm
0x180003f58  mov     rax, rsp
0x180003f5b  mov     [rax+20h], r9d
0x180003f5f  mov     [rax+18h], r8d
0x180003f63  mov     [rax+10h], rdx
0x180003f67  mov     [rax+8], rcx
0x180003f6b  push    rbx
0x180003f6c  push    rsi
0x180003f6d  push    rdi
0x180003f6e  push    r13
0x180003f70  push    r14
0x180003f72  push    r15
0x180003f74  sub     rsp, 98h
0x180003f7b  mov     edi, r9d
0x180003f7e  mov     [rsp+0C8h+var_98], r9d
0x180003f83  mov     rsi, rdx
0x180003f86  mov     rbx, rcx
0x180003f89  mov     r8, rcx
0x180003f8c  lea     rdx, aCreatetcallcli_0; "CreatetCallClient: enter, ptCall=%p,"
0x180003f93  mov     ecx, 80002h
0x180003f98  call    TRACELogPrint
0x180003f9d  mov     eax, edi
0x180003f9f  neg     eax
0x180003fa1  sbb     edx, edx
0x180003fa3  and     edx, 0AFDFAh
0x180003fa9  add     edx, 4C414349h
0x180003faf  mov     rcx, rbx
0x180003fb2  call    WaitForExclusivetCallAccess
0x180003fb7  test    eax, eax
0x180003fb9  jz      loc_18000441E
0x180003fbf  movsxd  rdx, dword ptr [rbx+0B8h]
0x180003fc6  cmp     edx, 2
0x180003fc9  jge     short loc_180003FFC
0x180003fcb  imul    rdi, rdx, 0D8h
0x180003fd2  add     rdi, 0C0h
0x180003fd9  add     rdi, rbx
0x180003fdc  mov     [rsp+0C8h+var_80], rdi
0x180003fe1  lea     eax, [rdx+1]
0x180003fe4  mov     [rbx+0B8h], eax
0x180003fea  lea     r14, [rbx+0BCh]
0x180003ff1  inc     dword ptr [r14]
0x180003ff4  mov     r13d, 1
0x180003ffa  jmp     short loc_18000402B
0x180003ffc  mov     edx, 8; dwFlags
0x180004001  mov     r8d, 0D8h; dwBytes
0x180004007  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18000400e  call    cs:__imp_HeapAlloc
0x180004014  mov     rdi, rax
0x180004017  mov     [rsp+0C8h+var_80], rax
0x18000401c  test    rax, rax
0x18000401f  jz      short loc_180004074
0x180004021  xor     r13d, r13d
0x180004024  lea     r14, [rbx+0BCh]
0x18000402b  mov     [rsp+0C8h+var_70], r14
0x180004030  mov     [rsp+0C8h+var_90], r13d
0x180004035  mov     r8, rdi
0x180004038  lea     rdx, aCreatetcallcli_1; "CreatetCallClient: calling NewObject, p"...
0x18000403f  mov     ecx, 40002h
0x180004044  call    TRACELogPrint
0x180004049  mov     r8d, r13d
0x18000404c  mov     rdx, rdi
0x18000404f  call    NewObject
0x180004054  lea     rcx, [rdi+58h]
0x180004058  mov     [rsp+0C8h+var_40], rcx
0x180004060  mov     [rcx], eax
0x180004062  test    eax, eax
0x180004064  jnz     short loc_1800040AA
0x180004066  test    r13d, r13d
0x180004069  jz      short loc_1800040A0
0x18000406b  dec     dword ptr [r14]
0x18000406e  dec     dword ptr [rbx+0B8h]
0x180004074  shr     rbx, 4
0x180004078  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18000407e  and     rbx, rax
0x180004081  lea     rcx, [rbx+rbx*4]
0x180004085  mov     rax, cs:gLockTable
0x18000408c  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180004090  call    cs:__imp_LeaveCriticalSection
0x180004096  mov     eax, 80000044h
0x18000409b  jmp     loc_180004423
0x1800040a0  mov     rcx, rdi; lpMem
0x1800040a3  call    ServerFree
0x1800040a8  jmp     short loc_180004074
0x1800040aa  xor     r15d, r15d
0x1800040ad  mov     [rsp+0C8h+var_78], r15
0x1800040b2  cmp     [rsp+0C8h+arg_10], 4
0x1800040ba  jnz     short loc_1800040C1
0x1800040bc  inc     dword ptr [rbx+40h]
0x1800040bf  jmp     short loc_1800040C4
0x1800040c1  inc     dword ptr [rbx+44h]
0x1800040c4  lea     rcx, [rbx+8]
0x1800040c8  mov     [rsp+0C8h+var_48], rcx
0x1800040d0  mov     rax, [rcx]
0x1800040d3  lea     rdx, [rdi+38h]
0x1800040d7  mov     [rsp+0C8h+var_50], rdx
0x1800040dc  mov     [rdx], rax
0x1800040df  test    rax, rax
0x1800040e2  jz      short loc_1800040E8
0x1800040e4  mov     [rax+30h], rdi
0x1800040e8  mov     [rcx], rdi
0x1800040eb  mov     rcx, rbx
0x1800040ee  shr     rcx, 4
0x1800040f2  mov     [rsp+0C8h+var_68], rcx
0x1800040f7  mov     [rsp+0C8h+var_60], rcx
0x1800040fc  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180004102  and     rax, rcx
0x180004105  lea     rcx, [rax+rax*4]
0x180004109  mov     rax, cs:gLockTable
0x180004110  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180004114  call    cs:__imp_LeaveCriticalSection
0x18000411a  mov     [rdi+10h], rsi
0x18000411e  mov     [rdi+18h], rbx
0x180004122  mov     eax, [rsp+0C8h+arg_10]
0x180004129  mov     [rdi+20h], eax
0x18000412c  cmp     [rsp+0C8h+arg_30], r15d
0x180004134  setnz   al
0x180004137  mov     [rdi+2Ch], al
0x18000413a  mov     rcx, rsi
0x18000413d  shr     rcx, 4
0x180004141  mov     [rsp+0C8h+var_88], rcx
0x180004146  mov     [rsp+0C8h+var_58], rcx
0x18000414b  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180004151  and     rax, rcx
0x180004154  lea     rcx, [rax+rax*4]
0x180004158  mov     rax, cs:gLockTable
0x18000415f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180004163  call    cs:__imp_EnterCriticalSection
0x180004169  nop
0x18000416a  xor     eax, eax
0x18000416c  mov     r8d, 494C434Ch
0x180004172  cmp     [rsi], r8d
0x180004175  setz    al
0x180004178  mov     [rsp+0C8h+var_8C], eax
0x18000417c  mov     [rsp+0C8h+var_94], eax
0x180004180  jnz     short loc_1800041A8
0x180004182  mov     edx, [rsi+18h]
0x180004185  call    ReferenceObject
0x18000418a  mov     r15, rax
0x18000418d  mov     [rsp+0C8h+var_78], rax
0x180004192  test    rax, rax
0x180004195  jz      short loc_18000419C
0x180004197  cmp     rsi, rax
0x18000419a  jz      short loc_1800041A4
0x18000419c  xor     eax, eax
0x18000419e  mov     [rsp+0C8h+var_94], eax
0x1800041a2  jmp     short loc_1800041A8
0x1800041a4  mov     eax, [rsp+0C8h+var_8C]
0x1800041a8  jmp     short loc_1800041F3
0x1800041aa  xor     eax, eax
0x1800041ac  mov     [rsp+0C8h+var_94], eax
0x1800041b0  mov     ecx, [rsp+0C8h+arg_18]
0x1800041b7  mov     [rsp+0C8h+var_98], ecx
0x1800041bb  mov     rsi, [rsp+0C8h+arg_8]
0x1800041c3  mov     rbx, [rsp+0C8h+arg_0]
0x1800041cb  mov     r13d, [rsp+0C8h+var_90]
0x1800041d0  mov     rdi, [rsp+0C8h+var_80]
0x1800041d5  mov     r15, [rsp+0C8h+var_78]
0x1800041da  mov     r14, [rsp+0C8h+var_70]
0x1800041df  mov     rcx, [rsp+0C8h+var_60]
0x1800041e4  mov     [rsp+0C8h+var_68], rcx
0x1800041e9  mov     rcx, [rsp+0C8h+var_58]
0x1800041ee  mov     [rsp+0C8h+var_88], rcx
0x1800041f3  test    eax, eax
0x1800041f5  jz      loc_180004340
0x1800041fb  mov     rax, [rsi+8]
0x1800041ff  mov     [rdi+8], rax
0x180004203  mov     rax, [rsi+30h]
0x180004207  mov     [rdi+48h], rax
0x18000420b  test    rax, rax
0x18000420e  jz      short loc_180004214
0x180004210  mov     [rax+40h], rdi
0x180004214  mov     [rsi+30h], rdi
0x180004218  test    r15, r15
0x18000421b  jz      short loc_18000422C
0x18000421d  mov     r8d, 1
0x180004223  mov     edx, [r15+18h]
0x180004227  call    DereferenceObject
0x18000422c  lea     rcx, [rdi+5Ch]; void *
0x180004230  mov     rax, [rsi+10h]
0x180004234  cmp     dword ptr [rax+30h], 30000h
0x18000423b  ja      short loc_18000424F
0x18000423d  mov     edx, 0FFh; Val
0x180004242  mov     r8d, 7Ch ; '|'; Size
0x180004248  call    memset_0
0x18000424d  jmp     short loc_1800042A6
0x18000424f  movups  xmm0, xmmword ptr [rsi+0A8h]
0x180004256  movups  xmmword ptr [rcx], xmm0
0x180004259  movups  xmm1, xmmword ptr [rsi+0B8h]
0x180004260  movups  xmmword ptr [rcx+10h], xmm1
0x180004264  movups  xmm0, xmmword ptr [rsi+0C8h]
0x18000426b  movups  xmmword ptr [rcx+20h], xmm0
0x18000426f  movups  xmm1, xmmword ptr [rsi+0D8h]
0x180004276  movups  xmmword ptr [rcx+30h], xmm1
0x18000427a  movups  xmm0, xmmword ptr [rsi+0E8h]
0x180004281  movups  xmmword ptr [rcx+40h], xmm0
0x180004285  movups  xmm1, xmmword ptr [rsi+0F8h]
0x18000428c  movups  xmmword ptr [rcx+50h], xmm1
0x180004290  movups  xmm0, xmmword ptr [rsi+108h]
0x180004297  movups  xmmword ptr [rcx+60h], xmm0
0x18000429b  movups  xmm1, xmmword ptr [rsi+114h]
0x1800042a2  movups  xmmword ptr [rcx+6Ch], xmm1
0x1800042a6  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800042ac  and     rax, [rsp+0C8h+var_88]
0x1800042b1  lea     rcx, [rax+rax*4]
0x1800042b5  mov     rax, cs:gLockTable
0x1800042bc  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800042c0  call    cs:__imp_LeaveCriticalSection
0x1800042c6  neg     [rsp+0C8h+var_98]
0x1800042ca  sbb     eax, eax
0x1800042cc  and     eax, 0FD08FFFAh
0x1800042d1  add     eax, 4C434349h
0x1800042d6  mov     [rdi], eax
0x1800042d8  cmp     [rsp+0C8h+arg_20], 0
0x1800042e0  jz      short loc_18000431A
0x1800042e2  mov     eax, 2000h
0x1800042e7  mov     r9d, 800h
0x1800042ed  cmp     [rsp+0C8h+arg_10], 4
0x1800042f5  cmovnz  r9d, eax
0x1800042f9  mov     [rsp+0C8h+var_A0], 0
0x180004301  mov     [rsp+0C8h+var_A8], 0
0x180004309  mov     r8d, 1
0x18000430f  mov     rdx, rdi
0x180004312  mov     rcx, rbx
0x180004315  call    SendMsgToCallClients
0x18000431a  mov     rax, [rsp+0C8h+arg_28]
0x180004322  mov     [rax], rdi
0x180004325  mov     r8, rdi
0x180004328  lea     rdx, aCreatetcallcli; "CreatetCallClient: exit, new ptCallClie"...
0x18000432f  mov     ecx, 80002h
0x180004334  call    TRACELogPrint
0x180004339  xor     eax, eax
0x18000433b  jmp     loc_180004423
0x180004340  test    r15, r15
0x180004343  jz      short loc_180004354
0x180004345  mov     r8d, 1
0x18000434b  mov     edx, [r15+18h]
0x18000434f  call    DereferenceObject
0x180004354  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18000435a  and     rax, [rsp+0C8h+var_88]
0x18000435f  lea     rcx, [rax+rax*4]
0x180004363  mov     rax, cs:gLockTable
0x18000436a  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18000436e  call    cs:__imp_LeaveCriticalSection
0x180004374  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18000437a  mov     rsi, [rsp+0C8h+var_68]
0x18000437f  and     rax, rsi
0x180004382  lea     rcx, [rax+rax*4]
0x180004386  mov     rax, cs:gLockTable
0x18000438d  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180004391  call    cs:__imp_EnterCriticalSection
0x180004397  cmp     [rsp+0C8h+arg_10], 4
0x18000439f  jnz     short loc_1800043A6
0x1800043a1  dec     dword ptr [rbx+40h]
0x1800043a4  jmp     short loc_1800043A9
0x1800043a6  dec     dword ptr [rbx+44h]
0x1800043a9  mov     rcx, [rsp+0C8h+var_50]
0x1800043ae  mov     rcx, [rcx]
0x1800043b1  test    rcx, rcx
0x1800043b4  jz      short loc_1800043BE
0x1800043b6  mov     rax, [rdi+30h]
0x1800043ba  mov     [rcx+30h], rax
0x1800043be  mov     rcx, [rdi+30h]
0x1800043c2  mov     rax, [rdi+38h]
0x1800043c6  test    rcx, rcx
0x1800043c9  jz      short loc_1800043D1
0x1800043cb  mov     [rcx+38h], rax
0x1800043cf  jmp     short loc_1800043DC
0x1800043d1  mov     rcx, [rsp+0C8h+var_48]
0x1800043d9  mov     [rcx], rax
0x1800043dc  test    r13d, r13d
0x1800043df  jz      short loc_1800043E4
0x1800043e1  dec     dword ptr [r14]
0x1800043e4  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800043ea  and     rax, rsi
0x1800043ed  lea     rcx, [rax+rax*4]
0x1800043f1  mov     rax, cs:gLockTable
0x1800043f8  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800043fc  call    cs:__imp_LeaveCriticalSection
0x180004402  mov     r8d, 1
0x180004408  mov     rdx, [rsp+0C8h+var_40]
0x180004410  mov     edx, [rdx]
0x180004412  call    DereferenceObject
0x180004417  mov     eax, 8000002Bh
0x18000441c  jmp     short loc_180004423
0x18000441e  mov     eax, 80000048h
0x180004423  add     rsp, 98h
0x18000442a  pop     r15
0x18000442c  pop     r14
0x18000442e  pop     r13
0x180004430  pop     rdi
0x180004431  pop     rsi
0x180004432  pop     rbx
0x180004433  retn
```
