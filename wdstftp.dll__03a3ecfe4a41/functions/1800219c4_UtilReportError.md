# UtilReportError

- ea: `0x1800219c4`
- end: `0x180021b0c`
- name: `UtilReportError`
- size: `328`
- prototype: ``
- caller_count: `39`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001074c`
- `0x180010b50`
- `0x1800112ac`
- `0x180011c80`
- `0x180012470`
- `0x1800124ec`
- `0x180012744`
- `0x1800147dc`
- `0x180018044`
- `0x18001847c`
- `0x18001a874`
- `0x18001d20c`
- `0x18001d3a4`
- `0x18001d7c8`
- `0x18001da04`
- `0x18001dea8`
- `0x18001dfe0`
- `0x18001e57c`
- `0x18001eb80`
- `0x18001edf0`
- `0x18001ef28`
- `0x18001f178`
- `0x18001f288`
- `0x18001f74c`
- `0x18001fc2c`
- `0x18001ff30`
- `0x180020a08`
- `0x180020cc8`
- `0x180021260`
- `0x180021748`
- `0x18002188c`
- `0x180021bf4`
- `0x180022010`
- `0x180022930`
- `0x180023d60`
- `0x180023f00`
- `0x180024050`
- `0x180024644`
- `0x1800250c4`

## callees

- `0x1800100c8`
- `0x18002188c`
- `0x1800219c4`
- `0x18003f578`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180021ae1`
- `KERNEL32!HeapFree` at `0x180021ae1`
- `KERNEL32!GetCurrentThreadId` at `0x180021a27`
- `KERNEL32!GetCurrentThreadId` at `0x180021a27`
- `KERNEL32!GetLastError` at `0x1800219f5`
- `KERNEL32!GetLastError` at `0x1800219f5`
- `KERNEL32!SetLastError` at `0x180021abc`
- `KERNEL32!SetLastError` at `0x180021abc`
- `KERNEL32!GetProcessHeap` at `0x180021acd`
- `KERNEL32!GetProcessHeap` at `0x180021acd`
- `ntdll!RtlAcquireResourceShared` at `0x180021a3e`
- `ntdll!RtlAcquireResourceShared` at `0x180021a3e`
- `ntdll!RtlReleaseResource` at `0x180021a75`
- `ntdll!RtlReleaseResource` at `0x180021a75`

## pseudocode

```c
__int64 __fastcall UtilReportError(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  void *v4; // rbx
  unsigned int v8; // edi
  DWORD LastError; // r14d
  int v10; // esi
  DWORD CurrentThreadId; // ebp
  _DWORD *i; // rax
  int v13; // eax
  HANDLE ProcessHeap; // rax
  void *v16; // [rsp+68h] [rbp+10h] BYREF

  v4 = 0;
  v16 = 0;
  v8 = 0;
  LastError = GetLastError();
  v10 = 0;
  if ( (int)WimLazyInitialize(InitializeGlobalRwLock_Callback, DeleteGlobalRwLock_Callback, 0, &dword_18007788C) < 0 )
    goto LABEL_9;
  CurrentThreadId = GetCurrentThreadId();
  RtlAcquireResourceShared(&Resource, 1u);
  for ( i = off_180077048; i != (_DWORD *)&off_180077048; i = *(_DWORD **)i )
  {
    if ( i[4] == CurrentThreadId )
    {
      v10 = 1;
      break;
    }
  }
  RtlReleaseResource(&Resource);
  if ( !v10 )
  {
LABEL_9:
    v13 = StrAllocatingPrintf(&v16, L"%s:(%d)", a1, a3);
    v4 = v16;
    v8 = v13;
    if ( v13 >= 0 )
      WIMSendMessage(0, 38263, a4, (_DWORD)v16);
  }
  SetLastError(LastError);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  return v8;
}

```

## disassembly

```asm
0x1800219c4  mov     rax, rsp
0x1800219c7  mov     [rax+8], rbx
0x1800219cb  mov     [rax+18h], rbp
0x1800219cf  mov     [rax+20h], rsi
0x1800219d3  mov     [rax+10h], rdx
0x1800219d7  push    rdi
0x1800219d8  push    r12
0x1800219da  push    r13
0x1800219dc  push    r14
0x1800219de  push    r15
0x1800219e0  sub     rsp, 30h
0x1800219e4  xor     ebx, ebx
0x1800219e6  movsxd  r15, r9d
0x1800219e9  mov     [rax+10h], rbx
0x1800219ed  mov     r12d, r8d
0x1800219f0  mov     r13, rcx
0x1800219f3  xor     edi, edi
0x1800219f5  call    cs:__imp_GetLastError
0x1800219fc  nop     dword ptr [rax+rax+00h]
0x180021a01  lea     r9, dword_18007788C
0x180021a08  xor     r8d, r8d
0x180021a0b  lea     rdx, DeleteGlobalRwLock_Callback
0x180021a12  mov     r14d, eax
0x180021a15  lea     rcx, InitializeGlobalRwLock_Callback
0x180021a1c  xor     esi, esi
0x180021a1e  call    WimLazyInitialize
0x180021a23  test    eax, eax
0x180021a25  js      short loc_180021A85
0x180021a27  call    cs:__imp_GetCurrentThreadId
0x180021a2e  nop     dword ptr [rax+rax+00h]
0x180021a33  mov     dl, 1; Wait
0x180021a35  lea     rcx, Resource; Resource
0x180021a3c  mov     ebp, eax
0x180021a3e  call    cs:__imp_RtlAcquireResourceShared
0x180021a45  nop     dword ptr [rax+rax+00h]
0x180021a4a  mov     rax, cs:off_180077048
0x180021a51  lea     rcx, off_180077048
0x180021a58  jmp     short loc_180021A62
0x180021a5a  cmp     [rax+10h], ebp
0x180021a5d  jz      short loc_180021A69
0x180021a5f  mov     rax, [rax]
0x180021a62  cmp     rax, rcx
0x180021a65  jnz     short loc_180021A5A
0x180021a67  jmp     short loc_180021A6E
0x180021a69  mov     esi, 1
0x180021a6e  lea     rcx, Resource; Resource
0x180021a75  call    cs:__imp_RtlReleaseResource
0x180021a7c  nop     dword ptr [rax+rax+00h]
0x180021a81  test    esi, esi
0x180021a83  jnz     short loc_180021AB9
0x180021a85  mov     r9d, r12d
0x180021a88  lea     rdx, aSD; "%s:(%d)"
0x180021a8f  mov     r8, r13
0x180021a92  lea     rcx, [rsp+58h+arg_8]
0x180021a97  call    StrAllocatingPrintf
0x180021a9c  mov     rbx, [rsp+58h+arg_8]
0x180021aa1  mov     edi, eax
0x180021aa3  test    eax, eax
0x180021aa5  js      short loc_180021AB9
0x180021aa7  mov     r8, r15
0x180021aaa  mov     r9, rbx
0x180021aad  mov     edx, 9577h
0x180021ab2  xor     ecx, ecx
0x180021ab4  call    WIMSendMessage
0x180021ab9  mov     ecx, r14d; dwErrCode
0x180021abc  call    cs:__imp_SetLastError
0x180021ac3  nop     dword ptr [rax+rax+00h]
0x180021ac8  test    rbx, rbx
0x180021acb  jz      short loc_180021AED
0x180021acd  call    cs:__imp_GetProcessHeap
0x180021ad4  nop     dword ptr [rax+rax+00h]
0x180021ad9  mov     r8, rbx; lpMem
0x180021adc  xor     edx, edx; dwFlags
0x180021ade  mov     rcx, rax; hHeap
0x180021ae1  call    cs:__imp_HeapFree
0x180021ae8  nop     dword ptr [rax+rax+00h]
0x180021aed  mov     rbx, [rsp+58h+arg_0]
0x180021af2  mov     eax, edi
0x180021af4  mov     rbp, [rsp+58h+arg_10]
0x180021af9  mov     rsi, [rsp+58h+arg_18]
0x180021afe  add     rsp, 30h
0x180021b02  pop     r15
0x180021b04  pop     r14
0x180021b06  pop     r13
0x180021b08  pop     r12
0x180021b0a  pop     rdi
0x180021b0b  retn
```
