# LaunchShellHostAsVirtualAccount(ulong,void *,ushort *,_VIRTUAL_ACCOUNT_CONTEXT const * *,_PROCESS_INFORMATION *)

- ea: `0x1800269c4`
- end: `0x180026b98`
- name: `?LaunchShellHostAsVirtualAccount@@YAJKPEAXPEAGPEAPEBU_VIRTUAL_ACCOUNT_CONTEXT@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `468`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, void *@<rdx>, unsigned __int16 *@<r8>, const struct _VIRTUAL_ACCOUNT_CONTEXT **@<r9>, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004732c`

## callees

- `0x1800269c4`
- `0x180026d04`
- `0x180026d78`
- `0x180064068`
- `0x18006f1c9`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b20`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180026b16`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180026b16`
- `ntdll!RtlAllocateHeap` at `0x180026a5c`
- `ntdll!RtlAllocateHeap` at `0x180026a5c`
- `ntdll!RtlFreeHeap` at `0x180026b74`
- `ntdll!RtlFreeHeap` at `0x180026b74`
- `profapi!__imp_CreateEnvBlock` at `0x180026ab7`
- `profapi!__imp_CreateEnvBlock` at `0x180026ab7`
- `profapi!__imp_DestroyEnvBlock` at `0x180026b57`
- `profapi!__imp_DestroyEnvBlock` at `0x180026b57`

## pseudocode

```c
__int64 __fastcall LaunchShellHostAsVirtualAccount(
        ULONG a1,
        void *a2,
        unsigned __int16 *a3,
        const struct _VIRTUAL_ACCOUNT_CONTEXT **a4,
        struct _PROCESS_INFORMATION *lpProcessInformation)
{
  unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rbx
  unsigned __int16 *Heap; // rax
  WCHAR *v13; // rsi
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v16; // eax
  struct _VIRTUAL_ACCOUNT_CONTEXT *v17; // rdi
  signed int LastError; // eax
  struct _STARTUPINFOW StartupInfo; // [rsp+60h] [rbp-98h] BYREF
  struct _VIRTUAL_ACCOUNT_CONTEXT *lpMem; // [rsp+110h] [rbp+18h] BYREF
  LPVOID lpEnvironment; // [rsp+118h] [rbp+20h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  lpEnvironment = 0;
  lpMem = 0;
  *a4 = 0;
  if ( !a3 )
    goto LABEL_6;
  v9 = a3;
  v10 = 0x7FFFFFFF;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v11 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
  if ( !v10 )
LABEL_6:
    v11 = 0;
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v11 + 2);
  v13 = Heap;
  if ( !Heap )
  {
    v14 = -2147024882;
    goto LABEL_19;
  }
  StringCchCopyW(Heap, v11 + 1, a3);
  v16 = CreateAndLogonVirtualAccountUserContext(v15, a1, a2, &lpMem);
  v17 = lpMem;
  v14 = v16;
  if ( v16 >= 0 )
  {
    LastError = CreateEnvBlock(&lpEnvironment, *((_QWORD *)lpMem + 6), 0);
    if ( LastError > 0 )
    {
LABEL_15:
      v14 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_17;
    }
    if ( LastError )
    {
      v14 = LastError;
      goto LABEL_17;
    }
    StartupInfo.cb = 104;
    if ( !CreateProcessAsUserW(
            *((HANDLE *)v17 + 6),
            0,
            v13,
            0,
            0,
            0,
            0x400u,
            lpEnvironment,
            0,
            &StartupInfo,
            lpProcessInformation) )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError <= 0 )
        goto LABEL_17;
      goto LABEL_15;
    }
    *a4 = v17;
    v17 = 0;
  }
LABEL_17:
  if ( v17 )
    FreeVirtualAccountUserContext((PCWSTR *)v17);
LABEL_19:
  if ( lpEnvironment )
    DestroyEnvBlock();
  if ( v13 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
  return v14;
}

```

## disassembly

```asm
0x1800269c4  mov     [rsp+arg_0], rbx
0x1800269c9  mov     [rsp+arg_8], rbp
0x1800269ce  push    rsi
0x1800269cf  push    rdi
0x1800269d0  push    r12
0x1800269d2  push    r14
0x1800269d4  push    r15
0x1800269d6  sub     rsp, 0D0h
0x1800269dd  mov     rbp, rdx
0x1800269e0  mov     rdi, r8
0x1800269e3  xor     edx, edx; Val
0x1800269e5  mov     r15d, ecx
0x1800269e8  lea     rcx, [rsp+0F8h+StartupInfo]; void *
0x1800269ed  mov     r14, r9
0x1800269f0  lea     r8d, [rdx+68h]; Size
0x1800269f4  call    memset_0
0x1800269f9  xor     r12d, r12d
0x1800269fc  mov     [rsp+0F8h+arg_18], r12
0x180026a04  mov     [rsp+0F8h+lpMem], r12
0x180026a0c  mov     [r14], r12
0x180026a0f  test    rdi, rdi
0x180026a12  jz      short loc_180026A42
0x180026a14  mov     edx, 7FFFFFFFh
0x180026a19  mov     rax, rdi
0x180026a1c  mov     ecx, edx
0x180026a1e  cmp     [rax], r12w
0x180026a22  jz      short loc_180026A2E
0x180026a24  add     rax, 2
0x180026a28  sub     rcx, 1
0x180026a2c  jnz     short loc_180026A1E
0x180026a2e  sub     rdx, rcx
0x180026a31  mov     rax, rcx
0x180026a34  neg     rax
0x180026a37  sbb     rbx, rbx
0x180026a3a  and     rbx, rdx
0x180026a3d  test    rcx, rcx
0x180026a40  jnz     short loc_180026A45
0x180026a42  mov     rbx, r12
0x180026a45  mov     rcx, gs:60h
0x180026a4e  lea     r8, ds:2[rbx*2]; Size
0x180026a56  xor     edx, edx; Flags
0x180026a58  mov     rcx, [rcx+30h]; HeapHandle
0x180026a5c  call    cs:__imp_RtlAllocateHeap
0x180026a62  mov     rsi, rax
0x180026a65  test    rax, rax
0x180026a68  jnz     short loc_180026A74
0x180026a6a  mov     ebx, 8007000Eh
0x180026a6f  jmp     loc_180026B4A
0x180026a74  lea     rdx, [rbx+1]; unsigned __int64
0x180026a78  mov     r8, rdi; unsigned __int16 *
0x180026a7b  mov     rcx, rsi; unsigned __int16 *
0x180026a7e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026a83  lea     r9, [rsp+0F8h+lpMem]; struct _VIRTUAL_ACCOUNT_CONTEXT **
0x180026a8b  mov     r8, rbp; void *
0x180026a8e  mov     edx, r15d; unsigned int
0x180026a91  call    ?CreateAndLogonVirtualAccountUserContext@@YAJKKPEAXPEAPEBU_VIRTUAL_ACCOUNT_CONTEXT@@@Z; CreateAndLogonVirtualAccountUserContext(ulong,ulong,void *,_VIRTUAL_ACCOUNT_CONTEXT const * *)
0x180026a96  mov     rdi, [rsp+0F8h+lpMem]
0x180026a9e  mov     ebx, eax
0x180026aa0  test    eax, eax
0x180026aa2  js      loc_180026B3D
0x180026aa8  mov     rdx, [rdi+30h]
0x180026aac  lea     rcx, [rsp+0F8h+arg_18]
0x180026ab4  xor     r8d, r8d
0x180026ab7  call    cs:__imp_CreateEnvBlock
0x180026abd  test    eax, eax
0x180026abf  jg      short loc_180026B2C
0x180026ac1  jz      short loc_180026AC7
0x180026ac3  mov     ebx, eax
0x180026ac5  jmp     short loc_180026B3D
0x180026ac7  mov     rax, [rsp+0F8h+arg_20]
0x180026acf  xor     r9d, r9d; lpProcessAttributes
0x180026ad2  mov     [rsp+0F8h+lpProcessInformation], rax; lpProcessInformation
0x180026ad7  mov     r8, rsi; lpCommandLine
0x180026ada  lea     rax, [rsp+0F8h+StartupInfo]
0x180026adf  mov     [rsp+0F8h+StartupInfo.cb], 68h ; 'h'
0x180026ae7  mov     rcx, [rdi+30h]; hToken
0x180026aeb  xor     edx, edx; lpApplicationName
0x180026aed  mov     [rsp+0F8h+lpStartupInfo], rax; lpStartupInfo
0x180026af2  mov     rax, [rsp+0F8h+arg_18]
0x180026afa  mov     [rsp+0F8h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180026aff  mov     [rsp+0F8h+lpEnvironment], rax; lpEnvironment
0x180026b04  mov     [rsp+0F8h+dwCreationFlags], 400h; dwCreationFlags
0x180026b0c  mov     [rsp+0F8h+bInheritHandles], r12d; bInheritHandles
0x180026b11  mov     [rsp+0F8h+lpThreadAttributes], r12; lpThreadAttributes
0x180026b16  call    cs:__imp_CreateProcessAsUserW
0x180026b1c  test    eax, eax
0x180026b1e  jnz     short loc_180026B37
0x180026b20  call    cs:__imp_GetLastError
0x180026b26  mov     ebx, eax
0x180026b28  test    eax, eax
0x180026b2a  jle     short loc_180026B3D
0x180026b2c  movzx   ebx, ax
0x180026b2f  or      ebx, 80070000h
0x180026b35  jmp     short loc_180026B3D
0x180026b37  mov     [r14], rdi
0x180026b3a  mov     rdi, r12
0x180026b3d  test    rdi, rdi
0x180026b40  jz      short loc_180026B4A
0x180026b42  mov     rcx, rdi; lpMem
0x180026b45  call    ?FreeVirtualAccountUserContext@@YAJPEBU_VIRTUAL_ACCOUNT_CONTEXT@@@Z; FreeVirtualAccountUserContext(_VIRTUAL_ACCOUNT_CONTEXT const *)
0x180026b4a  mov     rcx, [rsp+0F8h+arg_18]
0x180026b52  test    rcx, rcx
0x180026b55  jz      short loc_180026B5D
0x180026b57  call    cs:__imp_DestroyEnvBlock
0x180026b5d  test    rsi, rsi
0x180026b60  jz      short loc_180026B7A
0x180026b62  mov     rcx, gs:60h
0x180026b6b  mov     r8, rsi; P
0x180026b6e  xor     edx, edx; Flags
0x180026b70  mov     rcx, [rcx+30h]; HeapHandle
0x180026b74  call    cs:__imp_RtlFreeHeap
0x180026b7a  lea     r11, [rsp+0F8h+var_28]
0x180026b82  mov     eax, ebx
0x180026b84  mov     rbx, [r11+30h]
0x180026b88  mov     rbp, [r11+38h]
0x180026b8c  mov     rsp, r11
0x180026b8f  pop     r15
0x180026b91  pop     r14
0x180026b93  pop     r12
0x180026b95  pop     rdi
0x180026b96  pop     rsi
0x180026b97  retn
```
