# LaunchProcessAsUser(ushort *,void *,_PROCESS_INFORMATION *)

- ea: `0x180026ba0`
- end: `0x180026cfc`
- name: `?LaunchProcessAsUser@@YAKPEAGPEAXPEAU_PROCESS_INFORMATION@@@Z`
- size: `348`
- prototype: `unsigned int __fastcall(unsigned __int16 *, HANDLE hToken, LPPROCESS_INFORMATION lpProcessInformation)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180046dd4`
- `0x18004732c`

## callees

- `0x180026ba0`
- `0x180026d04`
- `0x18006f1c9`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026cb2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180026ca8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180026ca8`
- `ntdll!RtlAllocateHeap` at `0x180026c23`
- `ntdll!RtlAllocateHeap` at `0x180026c23`
- `ntdll!RtlFreeHeap` at `0x180026ce4`
- `ntdll!RtlFreeHeap` at `0x180026ce4`
- `profapi!__imp_CreateEnvBlock` at `0x180026c56`
- `profapi!__imp_CreateEnvBlock` at `0x180026c56`
- `profapi!__imp_DestroyEnvBlock` at `0x180026cc7`
- `profapi!__imp_DestroyEnvBlock` at `0x180026cc7`

## pseudocode

```c
__int64 __fastcall LaunchProcessAsUser(unsigned __int16 *a1, HANDLE hToken, LPPROCESS_INFORMATION lpProcessInformation)
{
  unsigned __int16 *v6; // rax
  __int64 v7; // r8
  __int64 v8; // rbx
  unsigned __int16 *Heap; // rax
  WCHAR *v10; // rdi
  DWORD LastError; // ebx
  struct _STARTUPINFOW StartupInfo; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID lpEnvironment; // [rsp+110h] [rbp+8h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  lpEnvironment = 0;
  if ( !a1 )
    goto LABEL_6;
  v6 = a1;
  v7 = 0x7FFFFFFF;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v7;
  }
  while ( v7 );
  v8 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
  if ( !v7 )
LABEL_6:
    v8 = 0;
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v8 + 2);
  v10 = Heap;
  if ( Heap )
  {
    StringCchCopyW(Heap, v8 + 1, a1);
    LastError = CreateEnvBlock(&lpEnvironment, hToken, 0);
    if ( !LastError )
    {
      StartupInfo.cb = 104;
      if ( !CreateProcessAsUserW(hToken, 0, v10, 0, 0, 0, 0x400u, lpEnvironment, 0, &StartupInfo, lpProcessInformation) )
        LastError = GetLastError();
    }
  }
  else
  {
    LastError = 14;
  }
  if ( lpEnvironment )
    DestroyEnvBlock();
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  return LastError;
}

```

## disassembly

```asm
0x180026ba0  push    rbx
0x180026ba2  push    rbp
0x180026ba3  push    rsi
0x180026ba4  push    rdi
0x180026ba5  push    r14
0x180026ba7  push    r15
0x180026ba9  sub     rsp, 0D8h
0x180026bb0  mov     rbp, rdx
0x180026bb3  mov     r14, r8
0x180026bb6  xor     edx, edx; Val
0x180026bb8  mov     rsi, rcx
0x180026bbb  lea     rcx, [rsp+108h+StartupInfo]; void *
0x180026bc0  lea     r8d, [rdx+68h]; Size
0x180026bc4  call    memset_0
0x180026bc9  xor     r15d, r15d
0x180026bcc  mov     [rsp+108h+arg_0], r15
0x180026bd4  test    rsi, rsi
0x180026bd7  jz      short loc_180026C09
0x180026bd9  mov     r9d, 7FFFFFFFh
0x180026bdf  mov     rax, rsi
0x180026be2  mov     r8d, r9d
0x180026be5  cmp     [rax], r15w
0x180026be9  jz      short loc_180026BF5
0x180026beb  add     rax, 2
0x180026bef  sub     r8, 1
0x180026bf3  jnz     short loc_180026BE5
0x180026bf5  sub     r9, r8
0x180026bf8  mov     rax, r8
0x180026bfb  neg     rax
0x180026bfe  sbb     rbx, rbx
0x180026c01  and     rbx, r9
0x180026c04  test    r8, r8
0x180026c07  jnz     short loc_180026C0C
0x180026c09  mov     rbx, r15
0x180026c0c  mov     rcx, gs:60h
0x180026c15  lea     r8, ds:2[rbx*2]; Size
0x180026c1d  xor     edx, edx; Flags
0x180026c1f  mov     rcx, [rcx+30h]; HeapHandle
0x180026c23  call    cs:__imp_RtlAllocateHeap
0x180026c29  mov     rdi, rax
0x180026c2c  test    rax, rax
0x180026c2f  jnz     short loc_180026C39
0x180026c31  lea     ebx, [rax+0Eh]
0x180026c34  jmp     loc_180026CBA
0x180026c39  lea     rdx, [rbx+1]; unsigned __int64
0x180026c3d  mov     r8, rsi; unsigned __int16 *
0x180026c40  mov     rcx, rdi; unsigned __int16 *
0x180026c43  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026c48  xor     r8d, r8d
0x180026c4b  lea     rcx, [rsp+108h+arg_0]
0x180026c53  mov     rdx, rbp
0x180026c56  call    cs:__imp_CreateEnvBlock
0x180026c5c  mov     ebx, eax
0x180026c5e  test    eax, eax
0x180026c60  jnz     short loc_180026CBA
0x180026c62  mov     rcx, [rsp+108h+arg_0]
0x180026c6a  lea     rax, [rsp+108h+StartupInfo]
0x180026c6f  mov     [rsp+108h+lpProcessInformation], r14; lpProcessInformation
0x180026c74  xor     r9d, r9d; lpProcessAttributes
0x180026c77  mov     [rsp+108h+lpStartupInfo], rax; lpStartupInfo
0x180026c7c  mov     r8, rdi; lpCommandLine
0x180026c7f  mov     [rsp+108h+lpCurrentDirectory], r15; lpCurrentDirectory
0x180026c84  xor     edx, edx; lpApplicationName
0x180026c86  mov     [rsp+108h+lpEnvironment], rcx; lpEnvironment
0x180026c8b  mov     rcx, rbp; hToken
0x180026c8e  mov     [rsp+108h+dwCreationFlags], 400h; dwCreationFlags
0x180026c96  mov     [rsp+108h+bInheritHandles], r15d; bInheritHandles
0x180026c9b  mov     [rsp+108h+lpThreadAttributes], r15; lpThreadAttributes
0x180026ca0  mov     [rsp+108h+StartupInfo.cb], 68h ; 'h'
0x180026ca8  call    cs:__imp_CreateProcessAsUserW
0x180026cae  test    eax, eax
0x180026cb0  jnz     short loc_180026CBA
0x180026cb2  call    cs:__imp_GetLastError
0x180026cb8  mov     ebx, eax
0x180026cba  mov     rcx, [rsp+108h+arg_0]
0x180026cc2  test    rcx, rcx
0x180026cc5  jz      short loc_180026CCD
0x180026cc7  call    cs:__imp_DestroyEnvBlock
0x180026ccd  test    rdi, rdi
0x180026cd0  jz      short loc_180026CEA
0x180026cd2  mov     rcx, gs:60h
0x180026cdb  mov     r8, rdi; P
0x180026cde  xor     edx, edx; Flags
0x180026ce0  mov     rcx, [rcx+30h]; HeapHandle
0x180026ce4  call    cs:__imp_RtlFreeHeap
0x180026cea  mov     eax, ebx
0x180026cec  add     rsp, 0D8h
0x180026cf3  pop     r15
0x180026cf5  pop     r14
0x180026cf7  pop     rdi
0x180026cf8  pop     rsi
0x180026cf9  pop     rbp
0x180026cfa  pop     rbx
0x180026cfb  retn
```
