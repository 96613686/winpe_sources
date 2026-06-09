# CGenericFileHandle::s_CreateInstance(FileHandleType,void *,ushort const *,ulong,ulong,ulong,ulong,MCFFLAGS,IFileHandle * *)

- ea: `0x18001c61c`
- end: `0x18001c7c0`
- name: `?s_CreateInstance@CGenericFileHandle@@SAJW4FileHandleType@@PEAXPEBGKKKKW4MCFFLAGS@@PEAPEAUIFileHandle@@@Z`
- size: `420`
- prototype: `static int __high(enum FileHandleType, void *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, enum MCFFLAGS, struct IFileHandle **)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800238b8`
- `0x18003c490`
- `0x180085410`

## callees

- `0x18001c61c`
- `0x18001c7c8`
- `0x18001c82c`
- `0x18001c858`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001c66c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001c66c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c771`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001c793`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001c793`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGenericFileHandle::s_CreateInstance(
        int a1,
        void *a2,
        wchar_t *a3,
        DWORD a4,
        DWORD a5,
        unsigned int a6,
        DWORD a7,
        unsigned int a8,
        _QWORD *a9)
{
  _QWORD *v13; // r14
  void **v14; // rdi
  HANDLE MutexW; // rax
  struct _SECURITY_ATTRIBUTES *v16; // r9
  int v17; // ecx
  char v18; // dl
  char v19; // al
  int Error; // eax
  int v21; // esi
  HANDLE CurrentProcess; // rbx
  HANDLE v24; // rax
  void *dwOptions; // [rsp+30h] [rbp-68h]

  v13 = a9;
  *a9 = 0;
  Microsoft::WRL::Details::Make<CGenericFileHandle,>(&a9);
  v14 = (void **)a9;
  if ( !a9 )
  {
    v21 = 0;
    Error = -2147024882;
    goto LABEL_12;
  }
  MutexW = CreateMutexW(0, 0, 0);
  v14[19] = MutexW;
  if ( !MutexW )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_22;
  }
  if ( a2 == (void *)-1LL )
  {
    v17 = (a8 >> 5) & 1;
    v18 = v17 | 2;
    if ( (a8 & 0x40) == 0 )
      v18 = v17;
    v19 = v18 | 4;
    if ( (a8 & 0x200) == 0 )
      v19 = v18;
    Error = CreateFileWithUsnSourceInfo(a3, a4, a5, v16, a6, a7, dwOptions, v19, 0, v14 + 16);
    v21 = Error;
  }
  else
  {
    v21 = 0;
    CurrentProcess = GetCurrentProcess();
    v24 = GetCurrentProcess();
    if ( DuplicateHandle(v24, a2, CurrentProcess, v14 + 16, 0, 0, 2u) )
      goto LABEL_10;
    Error = ResultFromKnownLastError();
  }
  if ( Error < 0 )
  {
LABEL_22:
    v21 = Error;
    goto LABEL_12;
  }
LABEL_10:
  *((_DWORD *)v14 + 34) = a4;
  *((_DWORD *)v14 + 36) = a1;
  if ( v21 < 0 )
    Error = v21;
  else
    Error = (*(__int64 (__fastcall **)(void **, GUID *, _QWORD *))*v14)(
              v14,
              &GUID_5e0ebc87_bece_4f2a_8d36_3673758f6c55,
              v13);
LABEL_12:
  if ( Error < 0 )
    v21 = Error;
  if ( v14 )
    (*((void (__fastcall **)(void **))*v14 + 2))(v14);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18001c61c  mov     rax, rsp
0x18001c61f  push    rbx
0x18001c620  push    rbp
0x18001c621  push    rsi
0x18001c622  push    rdi
0x18001c623  push    r12
0x18001c625  push    r13
0x18001c627  push    r14
0x18001c629  push    r15
0x18001c62b  sub     rsp, 58h
0x18001c62f  mov     r15d, r9d
0x18001c632  mov     rbx, r8
0x18001c635  mov     rbp, rdx
0x18001c638  mov     r13d, ecx
0x18001c63b  mov     r14, [rsp+98h+arg_40]
0x18001c643  mov     qword ptr [r14], 0
0x18001c64a  lea     rcx, [rax+48h]
0x18001c64e  call    ??$Make@VCGenericFileHandle@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCGenericFileHandle@@@12@XZ; Microsoft::WRL::Details::Make<CGenericFileHandle,>(void)
0x18001c653  nop
0x18001c654  mov     rdi, [rsp+98h+arg_40]
0x18001c65c  test    rdi, rdi
0x18001c65f  jz      loc_18001C759
0x18001c665  xor     r8d, r8d; lpName
0x18001c668  xor     edx, edx; bInitialOwner
0x18001c66a  xor     ecx, ecx; lpMutexAttributes
0x18001c66c  call    cs:__imp_CreateMutexW
0x18001c672  mov     [rdi+98h], rax
0x18001c679  test    rax, rax
0x18001c67c  jz      loc_18001C7AB
0x18001c682  lea     r12, [rdi+80h]
0x18001c689  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18001c68d  jnz     loc_18001C766
0x18001c693  mov     r8d, [rsp+98h+arg_38]
0x18001c69b  mov     ecx, r8d
0x18001c69e  shr     ecx, 5
0x18001c6a1  and     ecx, 1
0x18001c6a4  mov     edx, ecx
0x18001c6a6  or      edx, 2
0x18001c6a9  test    r8b, 40h
0x18001c6ad  cmovz   edx, ecx
0x18001c6b0  mov     eax, edx
0x18001c6b2  or      eax, 4
0x18001c6b5  bt      r8d, 9
0x18001c6ba  cmovnb  eax, edx
0x18001c6bd  mov     [rsp+98h+var_50], r12; void **
0x18001c6c2  mov     [rsp+98h+var_58], 0; unsigned int
0x18001c6ca  mov     [rsp+98h+var_60], eax; unsigned int
0x18001c6ce  mov     eax, [rsp+98h+arg_30]
0x18001c6d5  mov     [rsp+98h+bInheritHandle], eax; DWORD
0x18001c6d9  mov     eax, [rsp+98h+arg_28]
0x18001c6e0  mov     [rsp+98h+dwDesiredAccess], eax; unsigned int
0x18001c6e4  mov     r8d, [rsp+98h+arg_20]; unsigned int
0x18001c6ec  mov     edx, r15d; unsigned int
0x18001c6ef  mov     rcx, rbx; Str
0x18001c6f2  call    ?CreateFileWithUsnSourceInfo@@YAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXKKPEAPEAX@Z; CreateFileWithUsnSourceInfo(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,ulong,void * *)
0x18001c6f7  mov     esi, eax
0x18001c6f9  test    eax, eax
0x18001c6fb  js      loc_18001C7B8
0x18001c701  mov     [rdi+88h], r15d
0x18001c708  mov     [rdi+90h], r13d
0x18001c70f  test    esi, esi
0x18001c711  js      short loc_18001C762
0x18001c713  mov     rax, [rdi]
0x18001c716  mov     r8, r14
0x18001c719  lea     rdx, _GUID_5e0ebc87_bece_4f2a_8d36_3673758f6c55
0x18001c720  mov     rcx, rdi
0x18001c723  mov     rax, [rax]
0x18001c726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c72b  nop
0x18001c72c  test    eax, eax
0x18001c72e  cmovs   esi, eax
0x18001c731  test    rdi, rdi
0x18001c734  jz      short loc_18001C746
0x18001c736  mov     rdx, [rdi]
0x18001c739  mov     rcx, rdi
0x18001c73c  mov     rax, [rdx+10h]
0x18001c740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c745  nop
0x18001c746  mov     eax, esi
0x18001c748  add     rsp, 58h
0x18001c74c  pop     r15
0x18001c74e  pop     r14
0x18001c750  pop     r13
0x18001c752  pop     r12
0x18001c754  pop     rdi
0x18001c755  pop     rsi
0x18001c756  pop     rbp
0x18001c757  pop     rbx
0x18001c758  retn
0x18001c759  xor     esi, esi
0x18001c75b  mov     eax, 8007000Eh
0x18001c760  jmp     short loc_18001C72C
0x18001c762  mov     eax, esi
0x18001c764  jmp     short loc_18001C72C
0x18001c766  xor     esi, esi
0x18001c768  call    cs:__imp_GetCurrentProcess
0x18001c76e  mov     rbx, rax
0x18001c771  call    cs:__imp_GetCurrentProcess
0x18001c777  mov     dword ptr [rsp+98h+dwOptions], 2; dwOptions
0x18001c77f  mov     [rsp+98h+bInheritHandle], esi; bInheritHandle
0x18001c783  mov     [rsp+98h+dwDesiredAccess], esi; dwDesiredAccess
0x18001c787  mov     r9, r12; lpTargetHandle
0x18001c78a  mov     r8, rbx; hTargetProcessHandle
0x18001c78d  mov     rdx, rbp; hSourceHandle
0x18001c790  mov     rcx, rax; hSourceProcessHandle
0x18001c793  call    cs:__imp_DuplicateHandle
0x18001c799  test    eax, eax
0x18001c79b  jnz     loc_18001C701
0x18001c7a1  call    ResultFromKnownLastError
0x18001c7a6  jmp     loc_18001C6F9
0x18001c7ab  call    ResultFromKnownLastError
0x18001c7b0  test    eax, eax
0x18001c7b2  jns     loc_18001C682
0x18001c7b8  mov     esi, eax
0x18001c7ba  jmp     loc_18001C72C
```
