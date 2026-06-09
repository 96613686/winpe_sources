# UbpmpAcquireJobBackgroundMode

- ea: `0x18001fa6c`
- end: `0x18001fbf2`
- name: `UbpmpAcquireJobBackgroundMode`
- size: `390`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18001ea6c`
- `0x18001f9c4`
- `0x180032aa0`

## callees

- `0x18001f94c`
- `0x18001fa6c`
- `0x18001fd00`
- `0x18002046c`
- `0x1800204cc`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001facc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001facc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001fb95`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001fb95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fad2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fad2`

## pseudocode

```c
__int64 __fastcall UbpmpAcquireJobBackgroundMode(unsigned int a1, int a2, int a3, struct _LIST_ENTRY ***a4)
{
  unsigned int v8; // edi
  struct _LIST_ENTRY *i; // rax
  struct _LIST_ENTRY **p_Blink; // rbx
  unsigned int v11; // eax
  struct _LIST_ENTRY **v13; // [rsp+20h] [rbp-59h] BYREF
  _QWORD v14[3]; // [rsp+30h] [rbp-49h] BYREF
  int v15; // [rsp+4Ch] [rbp-2Dh]
  int v16; // [rsp+50h] [rbp-29h]
  char v17; // [rsp+54h] [rbp-25h]
  __int64 v18; // [rsp+60h] [rbp-19h]
  __int64 v19; // [rsp+88h] [rbp+Fh]

  memset_0(v14, 0, 0x68u);
  v13 = 0;
  if ( a1 >= 3 )
    return 87;
  v8 = 0;
  RtlAcquireSRWLockExclusive(&g_TaskHostJobObjectLock);
  dword_18004CF88 = GetCurrentThreadId();
  for ( i = g_leJobObjectContextsHead.Flink; i != &g_leJobObjectContextsHead; i = i->Flink )
  {
    p_Blink = &i[-1].Blink;
    v13 = &i[-1].Blink;
    if ( LODWORD(i[1].Blink) == a2 && *((_DWORD *)p_Blink + 9) == a1 )
      goto LABEL_9;
  }
  v11 = CreateJobObjectContext(a1, a2, &v13);
  p_Blink = v13;
  v8 = v11;
  if ( v11 )
    goto LABEL_13;
LABEL_9:
  if ( a3 == -1 )
    goto LABEL_24;
  v14[1] = p_Blink;
  v14[0] = UbpmpResetTaskJobModeCallback;
  v15 = 1;
  v17 = 0;
  v16 = a3;
  v18 = 0;
  v19 = 0;
  v8 = UbpmUtilsSubmitThreadPoolTimer((struct _UBPM_UTILS_TIMER_INPARAMS *)v14, 0);
  if ( !v8 )
  {
LABEL_24:
    if ( *((_DWORD *)p_Blink + 1) || (v8 = UbpmpSetJobBackgroundMode(p_Blink[3])) == 0 )
    {
      ++*((_DWORD *)p_Blink + 1);
      if ( a4 )
        *a4 = p_Blink;
      p_Blink = 0;
    }
  }
LABEL_13:
  if ( p_Blink && !*(_DWORD *)p_Blink && !*((_DWORD *)p_Blink + 1) )
    DestroyJobObjectContext(p_Blink);
  dword_18004CF88 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostJobObjectLock);
  return v8;
}

```

## disassembly

```asm
0x18001fa6c  mov     [rsp-8+arg_0], rbx
0x18001fa71  mov     [rsp-8+arg_8], rsi
0x18001fa76  push    rbp
0x18001fa77  push    rdi
0x18001fa78  push    r12
0x18001fa7a  push    r14
0x18001fa7c  push    r15
0x18001fa7e  lea     rbp, [rsp-37h]
0x18001fa83  sub     rsp, 0B0h
0x18001fa8a  mov     rax, cs:__security_cookie
0x18001fa91  xor     rax, rsp
0x18001fa94  mov     [rbp+57h+var_30], rax
0x18001fa98  mov     r15d, edx
0x18001fa9b  mov     r12d, r8d
0x18001fa9e  xor     edx, edx; Val
0x18001faa0  mov     esi, ecx
0x18001faa2  lea     rcx, [rbp+57h+var_A0]; void *
0x18001faa6  mov     r14, r9
0x18001faa9  lea     r8d, [rdx+68h]; Size
0x18001faad  call    memset_0
0x18001fab2  mov     [rbp+57h+var_B0], 0
0x18001faba  cmp     esi, 3
0x18001fabd  jnb     loc_18001FBD1
0x18001fac3  lea     rcx, ?g_TaskHostJobObjectLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TaskHostJobObjectLock
0x18001faca  xor     edi, edi
0x18001facc  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001fad2  call    cs:__imp_GetCurrentThreadId
0x18001fad8  mov     cs:dword_18004CF88, eax
0x18001fade  mov     rax, cs:?g_leJobObjectContextsHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leJobObjectContextsHead
0x18001fae5  lea     rcx, ?g_leJobObjectContextsHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leJobObjectContextsHead
0x18001faec  cmp     rax, rcx
0x18001faef  jz      short loc_18001FB0B
0x18001faf1  lea     rbx, [rax-8]
0x18001faf5  mov     [rbp+57h+var_B0], rbx
0x18001faf9  cmp     [rbx+20h], r15d
0x18001fafd  jz      short loc_18001FB04
0x18001faff  mov     rax, [rax]
0x18001fb02  jmp     short loc_18001FAE5
0x18001fb04  cmp     [rbx+24h], esi
0x18001fb07  jnz     short loc_18001FAFF
0x18001fb09  jmp     short loc_18001FB23
0x18001fb0b  lea     r8, [rbp+57h+var_B0]
0x18001fb0f  mov     edx, r15d
0x18001fb12  mov     ecx, esi
0x18001fb14  call    CreateJobObjectContext
0x18001fb19  mov     rbx, [rbp+57h+var_B0]
0x18001fb1d  mov     edi, eax
0x18001fb1f  test    eax, eax
0x18001fb21  jnz     short loc_18001FB7F
0x18001fb23  cmp     r12d, 0FFFFFFFFh
0x18001fb27  jz      short loc_18001FB68
0x18001fb29  lea     rax, UbpmpResetTaskJobModeCallback
0x18001fb30  mov     [rbp+57h+var_98], rbx
0x18001fb34  xor     edx, edx; void **
0x18001fb36  mov     [rbp+57h+var_A0], rax
0x18001fb3a  lea     rcx, [rbp+57h+var_A0]; struct _UBPM_UTILS_TIMER_INPARAMS *
0x18001fb3e  mov     [rbp+57h+var_84], 1
0x18001fb45  mov     [rbp+57h+var_7C], 0
0x18001fb49  mov     [rbp+57h+var_80], r12d
0x18001fb4d  mov     [rbp+57h+var_70], 0
0x18001fb55  mov     [rbp+57h+var_48], 0
0x18001fb5d  call    ?UbpmUtilsSubmitThreadPoolTimer@@YAKPEAU_UBPM_UTILS_TIMER_INPARAMS@@PEAPEAX@Z; UbpmUtilsSubmitThreadPoolTimer(_UBPM_UTILS_TIMER_INPARAMS *,void * *)
0x18001fb62  mov     edi, eax
0x18001fb64  test    eax, eax
0x18001fb66  jnz     short loc_18001FB7F
0x18001fb68  cmp     dword ptr [rbx+4], 0
0x18001fb6c  jnz     short loc_18001FBC5
0x18001fb6e  mov     rcx, [rbx+18h]; hJob
0x18001fb72  mov     dl, 1
0x18001fb74  call    UbpmpSetJobBackgroundMode
0x18001fb79  mov     edi, eax
0x18001fb7b  test    eax, eax
0x18001fb7d  jz      short loc_18001FBC5
0x18001fb7f  test    rbx, rbx
0x18001fb82  jnz     short loc_18001FBDD
0x18001fb84  lea     rcx, ?g_TaskHostJobObjectLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TaskHostJobObjectLock
0x18001fb8b  mov     cs:dword_18004CF88, 0
0x18001fb95  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001fb9b  mov     eax, edi
0x18001fb9d  mov     rcx, [rbp+57h+var_30]
0x18001fba1  xor     rcx, rsp; StackCookie
0x18001fba4  call    __security_check_cookie
0x18001fba9  lea     r11, [rsp+0D0h+var_20]
0x18001fbb1  mov     rbx, [r11+30h]
0x18001fbb5  mov     rsi, [r11+38h]
0x18001fbb9  mov     rsp, r11
0x18001fbbc  pop     r15
0x18001fbbe  pop     r14
0x18001fbc0  pop     r12
0x18001fbc2  pop     rdi
0x18001fbc3  pop     rbp
0x18001fbc4  retn
0x18001fbc5  inc     dword ptr [rbx+4]
0x18001fbc8  test    r14, r14
0x18001fbcb  jnz     short loc_18001FBD8
0x18001fbcd  xor     ebx, ebx
0x18001fbcf  jmp     short loc_18001FB7F
0x18001fbd1  mov     eax, 57h ; 'W'
0x18001fbd6  jmp     short loc_18001FB9D
0x18001fbd8  mov     [r14], rbx
0x18001fbdb  jmp     short loc_18001FBCD
0x18001fbdd  cmp     dword ptr [rbx], 0
0x18001fbe0  jnz     short loc_18001FB84
0x18001fbe2  cmp     dword ptr [rbx+4], 0
0x18001fbe6  jnz     short loc_18001FB84
0x18001fbe8  mov     rcx, rbx
0x18001fbeb  call    DestroyJobObjectContext
0x18001fbf0  jmp     short loc_18001FB84
```
