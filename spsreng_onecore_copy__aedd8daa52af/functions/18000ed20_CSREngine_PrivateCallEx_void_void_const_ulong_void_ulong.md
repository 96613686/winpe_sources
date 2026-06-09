# CSREngine::PrivateCallEx(void *,void const *,ulong,void * *,ulong *)

- ea: `0x18000ed20`
- end: `0x18000ef0c`
- name: `?PrivateCallEx@CSREngine@@UEAAJPEAXPEBXKPEAPEAXPEAK@Z`
- size: `492`
- prototype: `__int64 __usercall@<rax>(CSREngine *__hidden this@<rcx>, void *@<rdx>, const void *@<r8>, unsigned int@<r9d>, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007eec`
- `0x180008d6c`
- `0x180009cd0`
- `0x18000aeb0`
- `0x18000c808`
- `0x18000cbd8`
- `0x18000e4c0`
- `0x18000e5c0`
- `0x18000ed20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000ed3d`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000ed5b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000ed3d`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000ed5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ed34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ed52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ed67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000eeed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ed34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ed52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ed67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000eeed`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000ed72`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000eef9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000ed72`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000eef9`

## pseudocode

```c
__int64 __fastcall CSREngine::PrivateCallEx(
        CSREngine *this,
        void *a2,
        unsigned __int16 *a3,
        ULONG a4,
        void **a5,
        unsigned int *a6)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r14d
  HANDLE v11; // rax
  int v12; // ebx
  HANDLE v13; // rax
  unsigned int v14; // ebx
  int Alternates_M; // eax
  HANDLE v16; // rax

  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( *((_DWORD *)this + 233) != 0x7FFFFFFF )
  {
    v11 = GetCurrentThread();
    GetThreadPriority(v11);
    v12 = *((_DWORD *)this + 233);
    v13 = GetCurrentThread();
    SetThreadPriority(v13, v12);
  }
  *a5 = 0;
  *a6 = 0;
  if ( a3 )
  {
    switch ( *(_DWORD *)a3 )
    {
      case 0x15:
        Alternates_M = CSREngine::Execute_GetAlternates_M(this, (struct MSASRX_CORRECTION *)a3, a4, a5, a6);
        break;
      case 0x16:
        Alternates_M = CSREngine::Execute_Commit_M(this, a3, a4, a5, a6);
        break;
      case 0x17:
        v14 = -2147467263;
        goto LABEL_31;
      case 0x1F:
        Alternates_M = CSREngine::GetDefaultTrigramStoreSettings(this, a5, a6);
        break;
      case 0x28:
        Alternates_M = CSREngine::Execute_Commit_Text_M(this, a3, a4, a5, a6);
        break;
      case 0x2E:
        Alternates_M = CSREngine::PrepareGrammar(this, (const struct SPBINARYGRAMMAR *)a3 + 1, a5, a6);
        break;
      case 0x2F:
        Alternates_M = CSREngine::PrepareGrammarInProc(
                         this,
                         *((const struct SPBINARYGRAMMAR **)a3 + 1),
                         *((struct IStream **)a3 + 2));
        break;
      case 0x30:
        if ( a3[4] && a3[4] != *((_DWORD *)this + 64) )
        {
          v14 = -2147200898;
          goto LABEL_31;
        }
        Alternates_M = CSREngine::GetTNResults(this, *((_DWORD *)a3 + 1), a3 + 8, *((_DWORD *)a3 + 3), a5, a6);
        break;
      case 0x31:
        if ( a3[2] && a3[2] != *((_DWORD *)this + 64) )
        {
          v14 = -2147200931;
          goto LABEL_31;
        }
        Alternates_M = CSREngine::GetWordPronunciations(this, a3 + 6, *((_DWORD *)a3 + 2), a5, a6);
        break;
      default:
        v14 = -2147418113;
        goto LABEL_31;
    }
    v14 = Alternates_M;
    goto LABEL_31;
  }
  v14 = -2147024809;
LABEL_31:
  v16 = GetCurrentThread();
  SetThreadPriority(v16, ThreadPriority);
  return v14;
}

```

## disassembly

```asm
0x18000ed20  push    rbx
0x18000ed22  push    rbp
0x18000ed23  push    rsi
0x18000ed24  push    rdi
0x18000ed25  push    r14
0x18000ed27  sub     rsp, 30h
0x18000ed2b  mov     ebp, r9d
0x18000ed2e  mov     rdi, r8
0x18000ed31  mov     rsi, rcx
0x18000ed34  call    cs:__imp_GetCurrentThread
0x18000ed3a  mov     rcx, rax; hThread
0x18000ed3d  call    cs:__imp_GetThreadPriority
0x18000ed43  cmp     dword ptr [rsi+3A4h], 7FFFFFFFh
0x18000ed4d  mov     r14d, eax
0x18000ed50  jz      short loc_18000ED78
0x18000ed52  call    cs:__imp_GetCurrentThread
0x18000ed58  mov     rcx, rax; hThread
0x18000ed5b  call    cs:__imp_GetThreadPriority
0x18000ed61  mov     ebx, [rsi+3A4h]
0x18000ed67  call    cs:__imp_GetCurrentThread
0x18000ed6d  mov     rcx, rax; hThread
0x18000ed70  mov     edx, ebx; nPriority
0x18000ed72  call    cs:__imp_SetThreadPriority
0x18000ed78  mov     r10, [rsp+58h+arg_20]
0x18000ed80  xor     edx, edx
0x18000ed82  mov     r9, [rsp+58h+arg_28]; unsigned int *
0x18000ed8a  mov     [r10], rdx
0x18000ed8d  mov     [r9], edx
0x18000ed90  test    rdi, rdi
0x18000ed93  jnz     short loc_18000ED9F
0x18000ed95  mov     ebx, 80070057h
0x18000ed9a  jmp     loc_18000EEED
0x18000ed9f  mov     ecx, [rdi]
0x18000eda1  sub     ecx, 15h
0x18000eda4  jz      loc_18000EED5
0x18000edaa  sub     ecx, 1
0x18000edad  jz      loc_18000EEBD
0x18000edb3  sub     ecx, 1
0x18000edb6  jz      loc_18000EEB6
0x18000edbc  sub     ecx, 8
0x18000edbf  jz      loc_18000EEA6
0x18000edc5  sub     ecx, 9
0x18000edc8  jz      loc_18000EE8E
0x18000edce  sub     ecx, 6
0x18000edd1  jz      loc_18000EE7D
0x18000edd7  sub     ecx, 1
0x18000edda  jz      loc_18000EE6B
0x18000ede0  sub     ecx, 1
0x18000ede3  jz      short loc_18000EE2D
0x18000ede5  cmp     ecx, 1
0x18000ede8  jz      short loc_18000EDF4
0x18000edea  mov     ebx, 8000FFFFh
0x18000edef  jmp     loc_18000EEED
0x18000edf4  cmp     [rdi+4], dx
0x18000edf8  jz      short loc_18000EE10
0x18000edfa  movzx   eax, word ptr [rdi+4]
0x18000edfe  cmp     eax, [rsi+100h]
0x18000ee04  jz      short loc_18000EE10
0x18000ee06  mov     ebx, 8004505Dh
0x18000ee0b  jmp     loc_18000EEED
0x18000ee10  mov     r8d, [rdi+8]; unsigned int
0x18000ee14  lea     rdx, [rdi+0Ch]; unsigned __int16 *
0x18000ee18  mov     [rsp+58h+var_38], r9; unsigned int *
0x18000ee1d  mov     rcx, rsi; this
0x18000ee20  mov     r9, r10; void **
0x18000ee23  call    ?GetWordPronunciations@CSREngine@@QEAAJPEBGKPEAPEAXPEAK@Z; CSREngine::GetWordPronunciations(ushort const *,ulong,void * *,ulong *)
0x18000ee28  jmp     loc_18000EEEB
0x18000ee2d  cmp     [rdi+8], dx
0x18000ee31  jz      short loc_18000EE49
0x18000ee33  movzx   eax, word ptr [rdi+8]
0x18000ee37  cmp     eax, [rsi+100h]
0x18000ee3d  jz      short loc_18000EE49
0x18000ee3f  mov     ebx, 8004507Eh
0x18000ee44  jmp     loc_18000EEED
0x18000ee49  mov     edx, [rdi+4]; int
0x18000ee4c  lea     r8, [rdi+10h]; Src
0x18000ee50  mov     [rsp+58h+var_30], r9; unsigned int *
0x18000ee55  mov     rcx, rsi; this
0x18000ee58  mov     r9d, [rdi+0Ch]; int
0x18000ee5c  mov     [rsp+58h+var_38], r10; void **
0x18000ee61  call    ?GetTNResults@CSREngine@@QEAAJHPEBGHPEAPEAXPEAK@Z; CSREngine::GetTNResults(int,ushort const *,int,void * *,ulong *)
0x18000ee66  jmp     loc_18000EEEB
0x18000ee6b  mov     r8, [rdi+10h]; struct IStream *
0x18000ee6f  mov     rcx, rsi; this
0x18000ee72  mov     rdx, [rdi+8]; struct SPBINARYGRAMMAR *
0x18000ee76  call    ?PrepareGrammarInProc@CSREngine@@QEAAJPEBUSPBINARYGRAMMAR@@PEAUIStream@@@Z; CSREngine::PrepareGrammarInProc(SPBINARYGRAMMAR const *,IStream *)
0x18000ee7b  jmp     short loc_18000EEEB
0x18000ee7d  lea     rdx, [rdi+4]; struct SPBINARYGRAMMAR *
0x18000ee81  mov     r8, r10; void **
0x18000ee84  mov     rcx, rsi; this
0x18000ee87  call    ?PrepareGrammar@CSREngine@@QEAAJPEBUSPBINARYGRAMMAR@@PEAPEAXPEAK@Z; CSREngine::PrepareGrammar(SPBINARYGRAMMAR const *,void * *,ulong *)
0x18000ee8c  jmp     short loc_18000EEEB
0x18000ee8e  mov     [rsp+58h+var_38], r9; unsigned int *
0x18000ee93  mov     r8d, ebp; unsigned int
0x18000ee96  mov     r9, r10; void **
0x18000ee99  mov     rdx, rdi; void *
0x18000ee9c  mov     rcx, rsi; this
0x18000ee9f  call    ?Execute_Commit_Text_M@CSREngine@@QEAAJPEBXKPEAPEAXPEAK@Z; CSREngine::Execute_Commit_Text_M(void const *,ulong,void * *,ulong *)
0x18000eea4  jmp     short loc_18000EEEB
0x18000eea6  mov     r8, r9; unsigned int *
0x18000eea9  mov     rdx, r10; void **
0x18000eeac  mov     rcx, rsi; this
0x18000eeaf  call    ?GetDefaultTrigramStoreSettings@CSREngine@@AEAAJPEAPEAXPEAK@Z; CSREngine::GetDefaultTrigramStoreSettings(void * *,ulong *)
0x18000eeb4  jmp     short loc_18000EEEB
0x18000eeb6  mov     ebx, 80004001h
0x18000eebb  jmp     short loc_18000EEED
0x18000eebd  mov     [rsp+58h+var_38], r9; unsigned int *
0x18000eec2  mov     r8d, ebp; unsigned int
0x18000eec5  mov     r9, r10; void **
0x18000eec8  mov     rdx, rdi; void *
0x18000eecb  mov     rcx, rsi; this
0x18000eece  call    ?Execute_Commit_M@CSREngine@@QEAAJPEBXKPEAPEAXPEAK@Z; CSREngine::Execute_Commit_M(void const *,ulong,void * *,ulong *)
0x18000eed3  jmp     short loc_18000EEEB
0x18000eed5  mov     [rsp+58h+var_38], r9; unsigned int *
0x18000eeda  mov     r8d, ebp; unsigned int
0x18000eedd  mov     r9, r10; void **
0x18000eee0  mov     rdx, rdi; struct MSASRX_CORRECTION *
0x18000eee3  mov     rcx, rsi; this
0x18000eee6  call    ?Execute_GetAlternates_M@CSREngine@@QEAAJPEAUMSASRX_CORRECTION@@KPEAPEAXPEAK@Z; CSREngine::Execute_GetAlternates_M(MSASRX_CORRECTION *,ulong,void * *,ulong *)
0x18000eeeb  mov     ebx, eax
0x18000eeed  call    cs:__imp_GetCurrentThread
0x18000eef3  mov     rcx, rax; hThread
0x18000eef6  mov     edx, r14d; nPriority
0x18000eef9  call    cs:__imp_SetThreadPriority
0x18000eeff  mov     eax, ebx
0x18000ef01  add     rsp, 30h
0x18000ef05  pop     r14
0x18000ef07  pop     rdi
0x18000ef08  pop     rsi
0x18000ef09  pop     rbp
0x18000ef0a  pop     rbx
0x18000ef0b  retn
```
