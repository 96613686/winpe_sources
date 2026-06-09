# BasepGetFileRedirectionStatus

- ea: `0x14001b450`
- end: `0x14001b673`
- name: `BasepGetFileRedirectionStatus`
- size: `547`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14001a3fc`
- `0x14001b33c`
- `0x14001b67c`

## callees

- `0x140019a5c`
- `0x14001b450`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001b56b`
- `ntdll!RtlAllocateHeap` at `0x14001b56b`
- `ntdll!RtlFreeHeap` at `0x14001b623`
- `ntdll!RtlFreeHeap` at `0x14001b645`
- `ntdll!RtlFreeHeap` at `0x14001b623`
- `ntdll!RtlFreeHeap` at `0x14001b645`
- `ntdll!NtQueryInformationFile` at `0x14001b515`
- `ntdll!NtQueryInformationFile` at `0x14001b515`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14001b49c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14001b49c`
- `ntdll!_wcsnicmp` at `0x14001b4be`
- `ntdll!_wcsnicmp` at `0x14001b4d7`
- `ntdll!_wcsnicmp` at `0x14001b5c2`
- `ntdll!_wcsnicmp` at `0x14001b5db`
- `ntdll!_wcsnicmp` at `0x14001b5fc`
- `ntdll!_wcsnicmp` at `0x14001b4be`
- `ntdll!_wcsnicmp` at `0x14001b4d7`
- `ntdll!_wcsnicmp` at `0x14001b5c2`
- `ntdll!_wcsnicmp` at `0x14001b5db`
- `ntdll!_wcsnicmp` at `0x14001b5fc`

## pseudocode

```c
__int64 __fastcall BasepGetFileRedirectionStatus(__int64 a1, void *a2)
{
  __int64 result; // rax
  unsigned int FinalPathNameByHandleW; // eax
  unsigned int v5; // ebx
  const wchar_t *Heap; // rax
  const wchar_t *v7; // rbx
  wchar_t *v8; // r14
  unsigned int v9; // edi
  unsigned int v10; // esi
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *Str1; // [rsp+38h] [rbp-C8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE FileInformation[16]; // [rsp+50h] [rbp-B0h] BYREF
  char v15; // [rsp+D0h] [rbp-30h] BYREF

  v11 = 0;
  Str1 = 0;
  result = RtlDosPathNameToNtPathName_U_WithStatus(a1, &v11, 0, 0);
  if ( (int)result < 0 )
    return result;
  if ( !_wcsnicmp(Str1, L"\\??\\UNC\\", 8u) || !_wcsnicmp(Str1, L"\\\\?\\UNC\\", 8u) )
  {
    IoStatusBlock = 0;
    memset_0(FileInformation, 0, 0x74u);
    NtQueryInformationFile(a2, &IoStatusBlock, FileInformation, 0x74u, FileRemoteProtocolInformation);
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(a2);
  if ( !FinalPathNameByHandleW )
    goto LABEL_6;
  if ( FinalPathNameByHandleW <= 0x104 )
  {
    v8 = 0;
    v7 = (const wchar_t *)&v15;
    goto LABEL_11;
  }
  Heap = (const wchar_t *)RtlAllocateHeap(
                            *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                            KernelBaseGlobalData,
                            2LL * FinalPathNameByHandleW);
  v7 = Heap;
  if ( Heap )
  {
    v8 = (wchar_t *)Heap;
LABEL_11:
    v9 = GetFinalPathNameByHandleW(a2);
    if ( v9 )
    {
      if ( v9 > 4 )
      {
        if ( !_wcsnicmp(v7, L"\\\\?\\", 4u) || (v10 = 0, !_wcsnicmp(v7, L"\\??\\", 4u)) )
          v10 = 4;
        v5 = _wcsnicmp(Str1 + 4, &v7[v10], v9 - v10) != 0 ? 0xC000050B : 0;
      }
      else
      {
        v5 = -1073741767;
      }
    }
    else
    {
      v5 = -1073741801;
    }
    if ( v8 )
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v8);
    goto LABEL_21;
  }
LABEL_6:
  v5 = -1073741801;
LABEL_21:
  if ( Str1 )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Str1);
  return v5;
}

```

## disassembly

```asm
0x14001b450  mov     [rsp-8+arg_10], rbx
0x14001b455  push    rbp
0x14001b456  push    rsi
0x14001b457  push    rdi
0x14001b458  push    r14
0x14001b45a  push    r15
0x14001b45c  lea     rbp, [rsp-1F0h]
0x14001b464  sub     rsp, 2F0h
0x14001b46b  mov     rax, cs:__security_cookie
0x14001b472  xor     rax, rsp
0x14001b475  mov     [rbp+210h+var_30], rax
0x14001b47c  mov     r15, rdx
0x14001b47f  mov     [rsp+310h+var_2E0], 0
0x14001b488  lea     rdx, [rsp+310h+var_2E0]
0x14001b48d  mov     [rsp+310h+Str1], 0
0x14001b496  xor     r9d, r9d
0x14001b499  xor     r8d, r8d
0x14001b49c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14001b4a2  test    eax, eax
0x14001b4a4  js      loc_14001B64D
0x14001b4aa  mov     rcx, [rsp+310h+Str1]; Str1
0x14001b4af  lea     rdx, aUnc; "\\??\\UNC\\"
0x14001b4b6  mov     esi, 8
0x14001b4bb  mov     r8d, esi; MaxCount
0x14001b4be  call    cs:__imp__wcsnicmp
0x14001b4c4  test    eax, eax
0x14001b4c6  jz      short loc_14001B4E1
0x14001b4c8  mov     rcx, [rsp+310h+Str1]; Str1
0x14001b4cd  lea     rdx, aUnc_1; "\\\\?\\UNC\\"
0x14001b4d4  mov     r8d, esi; MaxCount
0x14001b4d7  call    cs:__imp__wcsnicmp
0x14001b4dd  test    eax, eax
0x14001b4df  jnz     short loc_14001B528
0x14001b4e1  xorps   xmm0, xmm0
0x14001b4e4  lea     rcx, [rsp+310h+FileInformation]; void *
0x14001b4e9  mov     ebx, 74h ; 't'
0x14001b4ee  xor     edx, edx; Val
0x14001b4f0  mov     r8d, ebx; Size
0x14001b4f3  movups  xmmword ptr [rsp+310h+IoStatusBlock], xmm0
0x14001b4f8  call    memset_0
0x14001b4fd  mov     r9d, ebx; Length
0x14001b500  mov     [rsp+310h+FileInformationClass], 37h ; '7'; FileInformationClass
0x14001b508  lea     r8, [rsp+310h+FileInformation]; FileInformation
0x14001b50d  mov     rcx, r15; FileHandle
0x14001b510  lea     rdx, [rsp+310h+IoStatusBlock]; IoStatusBlock
0x14001b515  call    cs:__imp_NtQueryInformationFile
0x14001b51b  test    eax, eax
0x14001b51d  js      short loc_14001B528
0x14001b51f  xor     edi, edi
0x14001b521  test    [rsp+310h+var_2B0], 1
0x14001b526  jnz     short loc_14001B52A
0x14001b528  mov     edi, esi
0x14001b52a  mov     r9d, edi
0x14001b52d  xor     r8d, r8d
0x14001b530  xor     edx, edx
0x14001b532  mov     rcx, r15; Handle
0x14001b535  call    GetFinalPathNameByHandleW
0x14001b53a  mov     esi, eax
0x14001b53c  test    eax, eax
0x14001b53e  jnz     short loc_14001B54A
0x14001b540  mov     ebx, 0C0000017h
0x14001b545  jmp     loc_14001B629
0x14001b54a  cmp     esi, 104h
0x14001b550  jbe     short loc_14001B57E
0x14001b552  mov     rcx, gs:60h
0x14001b55b  mov     r8, rsi
0x14001b55e  mov     edx, cs:KernelBaseGlobalData; Flags
0x14001b564  add     r8, r8; Size
0x14001b567  mov     rcx, [rcx+30h]; HeapHandle
0x14001b56b  call    cs:__imp_RtlAllocateHeap
0x14001b571  mov     rbx, rax
0x14001b574  test    rax, rax
0x14001b577  jz      short loc_14001B540
0x14001b579  mov     r14, rax
0x14001b57c  jmp     short loc_14001B585
0x14001b57e  xor     r14d, r14d
0x14001b581  lea     rbx, [rbp+210h+var_240]
0x14001b585  mov     r9d, edi
0x14001b588  mov     r8d, esi
0x14001b58b  mov     rdx, rbx
0x14001b58e  mov     rcx, r15; Handle
0x14001b591  call    GetFinalPathNameByHandleW
0x14001b596  mov     edi, eax
0x14001b598  test    eax, eax
0x14001b59a  jnz     short loc_14001B5A3
0x14001b59c  mov     ebx, 0C0000017h
0x14001b5a1  jmp     short loc_14001B60C
0x14001b5a3  mov     r15d, 4
0x14001b5a9  cmp     edi, r15d
0x14001b5ac  ja      short loc_14001B5B5
0x14001b5ae  mov     ebx, 0C0000039h
0x14001b5b3  jmp     short loc_14001B60C
0x14001b5b5  mov     r8, r15; MaxCount
0x14001b5b8  lea     rdx, asc_140029038; "\\\\?\\"
0x14001b5bf  mov     rcx, rbx; Str1
0x14001b5c2  call    cs:__imp__wcsnicmp
0x14001b5c8  test    eax, eax
0x14001b5ca  jz      short loc_14001B5E5
0x14001b5cc  mov     r8, r15; MaxCount
0x14001b5cf  lea     rdx, asc_140026F90; "\\??\\"
0x14001b5d6  mov     rcx, rbx; Str1
0x14001b5d9  xor     esi, esi
0x14001b5db  call    cs:__imp__wcsnicmp
0x14001b5e1  test    eax, eax
0x14001b5e3  jnz     short loc_14001B5E8
0x14001b5e5  mov     esi, r15d
0x14001b5e8  mov     rcx, [rsp+310h+Str1]
0x14001b5ed  sub     edi, esi
0x14001b5ef  mov     eax, esi
0x14001b5f1  add     rcx, 8; Str1
0x14001b5f5  mov     r8d, edi; MaxCount
0x14001b5f8  lea     rdx, [rbx+rax*2]; Str2
0x14001b5fc  call    cs:__imp__wcsnicmp
0x14001b602  neg     eax
0x14001b604  sbb     ebx, ebx
0x14001b606  and     ebx, 0C000050Bh
0x14001b60c  test    r14, r14
0x14001b60f  jz      short loc_14001B629
0x14001b611  mov     rcx, gs:60h
0x14001b61a  mov     r8, r14; BaseAddress
0x14001b61d  xor     edx, edx; Flags
0x14001b61f  mov     rcx, [rcx+30h]; HeapHandle
0x14001b623  call    cs:__imp_RtlFreeHeap
0x14001b629  cmp     [rsp+310h+Str1], 0
0x14001b62f  jz      short loc_14001B64B
0x14001b631  mov     rcx, gs:60h
0x14001b63a  xor     edx, edx; Flags
0x14001b63c  mov     r8, [rsp+310h+Str1]; BaseAddress
0x14001b641  mov     rcx, [rcx+30h]; HeapHandle
0x14001b645  call    cs:__imp_RtlFreeHeap
0x14001b64b  mov     eax, ebx
0x14001b64d  mov     rcx, [rbp+210h+var_30]
0x14001b654  xor     rcx, rsp; StackCookie
0x14001b657  call    __security_check_cookie
0x14001b65c  mov     rbx, [rsp+310h+arg_10]
0x14001b664  add     rsp, 2F0h
0x14001b66b  pop     r15
0x14001b66d  pop     r14
0x14001b66f  pop     rdi
0x14001b670  pop     rsi
0x14001b671  pop     rbp
0x14001b672  retn
```
