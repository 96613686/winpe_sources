# InitTrustletDumpSupport

- ea: `0x18002c778`
- end: `0x18002c902`
- name: `InitTrustletDumpSupport`
- size: `394`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014fa4`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x18002c368`
- `0x18002c778`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002c8db`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002c8db`
- `ntdll!RtlAllocateHeap` at `0x18002c7b0`
- `ntdll!RtlAllocateHeap` at `0x18002c86b`
- `ntdll!RtlAllocateHeap` at `0x18002c7b0`
- `ntdll!RtlAllocateHeap` at `0x18002c86b`
- `ntdll!RtlInitUnicodeString` at `0x18002c813`
- `ntdll!RtlInitUnicodeString` at `0x18002c813`
- `ntdll!NtAlpcCreatePort` at `0x18002c84a`
- `ntdll!NtAlpcCreatePort` at `0x18002c84a`

## pseudocode

```c
__int64 __fastcall InitTrustletDumpSupport(int a1)
{
  PVOID Heap; // rax
  signed __int64 v3; // rdi
  int v4; // ebx
  PVOID v5; // rax
  HANDLE Thread; // rax
  signed __int32 v8[8]; // [rsp+0h] [rbp-99h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-69h] BYREF
  _QWORD v10[4]; // [rsp+40h] [rbp-59h] BYREF
  __int128 v11; // [rsp+60h] [rbp-39h]
  int v12; // [rsp+70h] [rbp-29h] BYREF
  __int64 v13; // [rsp+74h] [rbp-25h]
  __int16 v14; // [rsp+7Ch] [rbp-1Dh]
  __int64 v15; // [rsp+80h] [rbp-19h]

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xC88u);
  v3 = (signed __int64)Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0xC88u);
    memset_0(&v12, 0, 0x48u);
    v13 = 12;
    v14 = 257;
    v15 = 0xFFFF;
    DestinationString = 0;
    v12 = 16842752;
    RtlInitUnicodeString(&DestinationString, L"\\IUM_TRUSTLET_DUMP_SERVER");
    v10[0] = 48;
    v10[1] = 0;
    v10[3] = 64;
    v10[2] = &DestinationString;
    v11 = 0;
    v4 = NtAlpcCreatePort(v3, v10, &v12);
    if ( v4 >= 0 )
    {
      v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x10000u);
      *(_QWORD *)(v3 + 24) = v5;
      if ( v5
        && (*(_QWORD *)(v3 + 40) = -1,
            *(_QWORD *)(v3 + 16) = IumCrashReport,
            *(_DWORD *)(v3 + 8) = a1,
            _InterlockedOr(v8, 0),
            Thread = CreateThread(0, 0, IdpTrustletServerLoop, (LPVOID)v3, 0, 0),
            (*(_QWORD *)(v3 + 32) = Thread) != 0) )
      {
        if ( !_InterlockedCompareExchange64(&TrustletDumpServer, v3, 0) )
          return 0;
        v4 = -1073741790;
      }
      else
      {
        v4 = -1073741801;
      }
    }
    IdpTrustletDumpSupportServerStop(v3);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002c778  push    rbp
0x18002c77a  push    rbx
0x18002c77b  push    rsi
0x18002c77c  push    rdi
0x18002c77d  lea     rbp, [rsp-3Fh]
0x18002c782  sub     rsp, 0D8h
0x18002c789  mov     rax, cs:__security_cookie
0x18002c790  xor     rax, rsp
0x18002c793  mov     [rbp+57h+var_30], rax
0x18002c797  mov     esi, ecx
0x18002c799  mov     ebx, 0C88h
0x18002c79e  mov     rcx, gs:60h
0x18002c7a7  mov     r8d, ebx; Size
0x18002c7aa  xor     edx, edx; Flags
0x18002c7ac  mov     rcx, [rcx+30h]; HeapHandle
0x18002c7b0  call    cs:__imp_RtlAllocateHeap
0x18002c7b6  mov     rdi, rax
0x18002c7b9  test    rax, rax
0x18002c7bc  jnz     short loc_18002C7C8
0x18002c7be  mov     ebx, 0C0000017h
0x18002c7c3  jmp     loc_18002C887
0x18002c7c8  mov     r8, rbx; Size
0x18002c7cb  xor     edx, edx; Val
0x18002c7cd  mov     rcx, rdi; void *
0x18002c7d0  call    memset_0
0x18002c7d5  xor     edx, edx; Val
0x18002c7d7  lea     rcx, [rbp+57h+var_80]; void *
0x18002c7db  lea     r8d, [rdx+48h]; Size
0x18002c7df  call    memset_0
0x18002c7e4  xorps   xmm0, xmm0
0x18002c7e7  mov     [rbp+57h+var_7C], 0Ch
0x18002c7ef  lea     rdx, aIumTrustletDum; "\\IUM_TRUSTLET_DUMP_SERVER"
0x18002c7f6  mov     [rbp+57h+var_74], 101h
0x18002c7fc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002c800  mov     [rbp+57h+var_70], 0FFFFh
0x18002c808  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002c80c  mov     [rbp+57h+var_80], 1010000h
0x18002c813  call    cs:__imp_RtlInitUnicodeString
0x18002c819  xor     eax, eax
0x18002c81b  mov     [rbp+57h+var_B0], 30h ; '0'
0x18002c823  mov     [rbp+57h+var_A8], rax
0x18002c827  lea     r8, [rbp+57h+var_80]
0x18002c82b  lea     rax, [rbp+57h+DestinationString]
0x18002c82f  mov     [rbp+57h+var_98], 40h ; '@'
0x18002c837  xorps   xmm0, xmm0
0x18002c83a  mov     [rbp+57h+var_A0], rax
0x18002c83e  lea     rdx, [rbp+57h+var_B0]
0x18002c842  mov     rcx, rdi
0x18002c845  movdqu  [rbp+57h+var_90], xmm0
0x18002c84a  call    cs:__imp_NtAlpcCreatePort
0x18002c850  mov     ebx, eax
0x18002c852  test    eax, eax
0x18002c854  js      short loc_18002C87F
0x18002c856  mov     rcx, gs:60h
0x18002c85f  xor     edx, edx; Flags
0x18002c861  mov     r8d, 10000h; Size
0x18002c867  mov     rcx, [rcx+30h]; HeapHandle
0x18002c86b  call    cs:__imp_RtlAllocateHeap
0x18002c871  mov     [rdi+18h], rax
0x18002c875  test    rax, rax
0x18002c878  jnz     short loc_18002C8A1
0x18002c87a  mov     ebx, 0C0000017h
0x18002c87f  mov     rcx, rdi
0x18002c882  call    IdpTrustletDumpSupportServerStop
0x18002c887  mov     eax, ebx
0x18002c889  mov     rcx, [rbp+57h+var_30]
0x18002c88d  xor     rcx, rsp; StackCookie
0x18002c890  call    __security_check_cookie
0x18002c895  add     rsp, 0D8h
0x18002c89c  pop     rdi
0x18002c89d  pop     rsi
0x18002c89e  pop     rbx
0x18002c89f  pop     rbp
0x18002c8a0  retn
0x18002c8a1  lea     rax, ?IumCrashReport@@YAKPEAU_IUM_DUMP_REPORT_INFO@@PEA_W@Z; IumCrashReport(_IUM_DUMP_REPORT_INFO *,wchar_t *)
0x18002c8a8  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18002c8b0  mov     [rdi+10h], rax
0x18002c8b4  mov     [rdi+8], esi
0x18002c8b7  lock or [rsp+0F0h+var_F0], 0
0x18002c8bc  mov     [rsp+0F0h+lpThreadId], 0; lpThreadId
0x18002c8c5  lea     r8, IdpTrustletServerLoop; lpStartAddress
0x18002c8cc  mov     r9, rdi; lpParameter
0x18002c8cf  mov     [rsp+0F0h+dwCreationFlags], 0; dwCreationFlags
0x18002c8d7  xor     edx, edx; dwStackSize
0x18002c8d9  xor     ecx, ecx; lpThreadAttributes
0x18002c8db  call    cs:__imp_CreateThread
0x18002c8e1  mov     [rdi+20h], rax
0x18002c8e5  test    rax, rax
0x18002c8e8  jz      short loc_18002C87A
0x18002c8ea  xor     eax, eax
0x18002c8ec  lock cmpxchg cs:TrustletDumpServer, rdi
0x18002c8f5  jz      short loc_18002C8FE
0x18002c8f7  mov     ebx, 0C0000022h
0x18002c8fc  jmp     short loc_18002C87F
0x18002c8fe  xor     ebx, ebx
0x18002c900  jmp     short loc_18002C887
```
